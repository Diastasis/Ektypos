# Fichero printers: protocol notes

Document version 1.0.0, 14 November 2026. Covers all seven Fichero models known to the Fichero app.

Bluetooth protocol notes for every printer that carries the Fichero name. The notes come from three sources:

- **Fichero Android app 1.1.17** (`com.lj.fichero`, LuckPrinter SDK `com.luckprinter.sdk_new`), read by disassembling its DEX bytecode and `libPrinterNative.so`, and from the model list the app ships (`assets/printer_model_list.json`).
- **Ektypos itself.** The command sequences in section 5.1 to 5.3 are exactly what Ektypos sends. All four printers it supports were tested on real hardware by the project author (November 2026) and print correctly.
- **0xMH/fichero-printer**, [docs/PROTOCOL.md](https://github.com/0xMH/fichero-printer/blob/main/docs/PROTOCOL.md), which documents the D11s. Read it for status bits and reply formats not repeated here.

Status words used below: **tested** means the project author printed with it on real hardware; **from app code** means read from the Fichero app and not yet tried on a printer.

## 1. All Fichero models

| Fichero model | Bluetooth name | SDK class | Command family | DPI | Print width | Paper | Ektypos |
|---|---|---|---|---|---|---|---|
| **D11s** label printer | `D11s_`, `FICHERO_5836` | `aiyin/D11s` | AiYin label | 203 | 96 dots (12 mm) | 12 to 15 mm labels: gaps, black marks, continuous | tested |
| **A4 6181** | `FICHERO_6181` | `aiyin/Fichero6181` | AiYin A4 | 203 | up to 1648 dots | A4 / fanfold, roll, label sheets | tested |
| **A4 4437** | `Fichero 4437` | `normal/a4/DP_L81H` | Lujiang A4 | 300 | up to 2496 dots | A4 / fanfold, roll, label sheets | tested |
| **A4 5622** | `Fichero 5622_`, `FICHERO_5622` | `normal/a4/MT81H` | Lujiang A4 | 300 | up to 2424 dots | A4 / fanfold, roll, label sheets, tattoo | tested |
| **4575** label printer | `Fichero 4575`, `Fichero_4575` | `normal/DP_D1H` | Lujiang label | 300 | 576 dots (50 mm class) | 50 mm labels (50×15, 50×30, 50×50), continuous | from app code |
| **3561** label printer | `Fichero 3561` | `normal/DP_D1` | Lujiang label | 203 | 384 dots (48 mm) | 50 mm labels (50×15, 50×30, 50×50), continuous | from app code |
| **5655** label printer | `FICHERO_5655` | `normal/MPC15` | Lujiang label | 203 | 96 dots (12 mm) | 12 to 15 mm labels | from app code |

Notes:

- In the app, the 4437 is listed as "Fichero A4". The 4575 and 3561 share the app's "D1" model entry. The D11s is the app's "MPL11" entry. The 6181 is the "D82" entry.
- `MULLER_6473` is another Bluetooth name that uses the same `D11s` class. It is a re-badged D11s, not a Fichero name.
- The app also knows the Crafts & Co names `CRAFTS&CO|4777`, `CRAFTS_CO_4777` and `C&Co 3128`. They belong to the same SDK but are not Fichero names and are not covered here.
- Ektypos recognises a printer by its Bluetooth name. The patterns are in `index.html` (`MODELS`): `^(D11s_|FICHERO_5836)`, `^FICHERO_6181`, `^(Fichero 4437|DP_L81H_)` and `^(Fichero 5622|FICHERO_5622|MT81H?_)`. The 4575, 3561 and 5655 appear in the Bluetooth picker (it filters on `FICHERO` and `Fichero`) but Ektypos has no profile for them yet.

### Print widths

203 dpi gives 8 dots per mm, 300 dpi gives 11.8. For the A4 printers the SDK uses a fixed table (`BaseA4Device.getPrintWidth`), in dots at 203 / 300 dpi:

| Paper width | 56 mm | 77 mm | 107 mm | 210 mm | 216 mm |
|---|---|---|---|---|---|
| Dots | 432 / 648 | 591 / 887 | 832 / 1248 | 1616 / 2400 | 1648 / 2496 |

The Lujiang label printers use 384 dots at 203 dpi and 576 dots at 300 dpi (`BaseDevice.getPrintWidth`). The D11s and 5655 are fixed at 96.

## 2. Bluetooth transport

Ektypos asks for service `ff00` first.

- Write characteristic `ff02` (write without response).
- Notifications on `ff01` (replies) and `ff03` (flow control).
- If `ff00` is not available it falls back to service `18f0`, the layout described in the 0xMH document.

`ff03` messages:

- `01 nn`: the printer grants `nn` write credits. Every Bluetooth packet uses one credit, and the sender must stop at 0.
- `02 LL HH`: the printer's MTU, little-endian (for example `02 B9 00` is 185). The packet payload is MTU − 3.

Replies on `ff01`:

- A job is finished when the printer sends `AA` or the text `OK`.
- Information queries (section 3) answer with text.

## 3. Commands

| Bytes | Meaning | Used by |
|---|---|---|
| `10 FF 10 00 nn` | Set density. Range: D11s 0 to 2, 6181 0 to 4, Lujiang 0 to 2 | all |
| `00` × 12 | Wake-up | all |
| `10 FF 20 F0` / `10 FF 20 F1` | Query model / firmware (text reply) | all |
| `10 FF 50 F1` | Query battery | all |
| `10 FF 40` | Query status (see the 0xMH document for the bits) | all |
| `1D 0C` | Feed to the next label or page | all |
| `10 FF FE 01` / `10 FF FE 45` | Enable print / stop print | AiYin (D11s, 6181) |
| `10 FF 84 nn` | Label paper: `0` gaps, `1` black marks, `2` continuous | AiYin label (D11s) |
| `10 FF 10 03 nn` | Paper: `3` fanfold (also `0`), `1` roll, `2` label, `4` tattoo | AiYin A4 (6181) |
| `10 FF F1 03` / `10 FF F1 45` | Enable print / stop print (stop waits up to 120 s for `AA` or `OK`) | Lujiang (4437, 5622, 4575, 3561, 5655) |
| `1F 80 01 tt` | Paper: `10` roll, `20` gap labels, `30` fanfold, `50` black marks | Lujiang |
| `1F 11 nn` | Auto position: `51` before, `50` after a fanfold or label page | Lujiang A4 |
| `1B 4A nn` | Feed `nn` dots. After a continuous job: 216 at 300 dpi, 144 at 203 dpi on A4 | Lujiang |
| `FC FF 00 02 24 HH LL xx` | Total page count (mark count), `xx` is the XOR of all preceding bytes. Sent before page 1 | 5622, 5655 |

## 4. Raster formats

**Plain** (`PrinterImageProcessor.getBitmapByteArray`), used by the AiYin printers and the Lujiang label printers:

`1D 76 30 00 wL wH hL hH` followed by the data. The width is in bytes, little-endian.

**Compressed** (`getBitmapByteArrayCompress`), used by the Lujiang A4 printers:

`1F 10 wH wL hH hL n3 n2 n1 n0` followed by a zlib stream. The width in bytes, the height and the compressed length are big-endian.

Pixel data: rows of `ceil(w/8)` bytes, most significant bit first, `1` means black. A pixel is black when (R+G+B)/3 is below 128.

zlib: `Compress.codeLihu` and `Compress.codeESC` are the same JNI wrappers around zlib 1.2.3 `compress2()` with `deflateInit2_(level −1, Z_DEFLATED, windowBits 10, memLevel 8)`. The stream therefore has a 1 KB window (header `28 xx`). The browser's `CompressionStream` uses a 32 KB window, so Ektypos writes its own zlib stream.

## 5. Print sequences

### 5.1 D11s (AiYin label), tested

```
10 FF 10 00 nn         density
10 FF 84 pp            paper: 0 gaps, 1 black marks, 2 continuous
00 × 12                wake-up
10 FF FE 01            enable
1D 76 30 00 …          raster
1D 0C                  feed to next label
10 FF FE 45            stop → wait for AA / "OK" (60 s)
```

### 5.2 A4 6181 (AiYin A4), tested

```
10 FF 10 00 nn         density
10 FF 10 03 pp         paper: 3 fanfold, 1 roll, 2 label
00 × 12                wake-up
10 FF FE 01            enable
1D 76 30 00 …          raster → wait for AA / "OK" (60 s)
1D 0C
10 FF FE 45            stop
```

### 5.3 A4 4437 and 5622 (Lujiang A4), tested

```
[5622, first page] FC FF 00 02 24 <count BE16> <xor>
10 FF 10 00 nn         density
10 FF F1 03            enable
00 × 12                wake-up
1F 80 01 30            paper: 30 fanfold, 20 label, 10 roll
1F 11 51               (fanfold and label)
1F 10 … <zlib>         compressed raster
1D 0C                  (fanfold and label)
1F 11 50               (fanfold and label)
10 FF F1 45            stop → wait for AA / "OK" (120 s)
```

For a roll, the `1F 11` and `1D 0C` steps are replaced by `1B 4A D8` (216 dots) before the stop command.

### 5.4 4575, 3561 and 5655 (Lujiang label printers), from app code

Not tested. This is what the Fichero app sends (`DP_D1.printTagOnce`, `MPC15.printTagOnce`, `MPC15.printBlackTagOnce`, `MPC15.printOnce`).

Gap labels:
```
[5655 only] FC FF 00 02 24 <count BE16> <xor>
10 FF F1 03            enable
00 × 12                wake-up
1F 80 01 20            paper: gap labels (black marks: 1F 80 01 50)
1D 76 30 00 …          raster
1D 0C                  feed to next label
10 FF F1 45            stop → wait for AA / "OK"
```

Continuous paper: enable, wake-up, raster, then `1B 4A nn`, then stop, with no paper command. The feed `nn` is 80 dots on the 384-dot printers, 120 on the others, and 180 on the 4575 (`DP_D1H.setEndLineDot`). The density is set separately with `10 FF 10 00 nn` (0 to 2).

## 6. Other models in the same SDK

The Fichero app is built on the LuckPrinter SDK, which also drives many printers sold under other names. The families, for future work (none of these carries the Fichero name and none has been tried):

- **AiYin**: `D11s`, `D12`, `D82S`, `D83`, `A40a`, `AiYinB24`, `AiYin4777`, `Fichero6181`. Commands as in 5.1 and 5.2.
- **Lujiang label printers** (`normal/*`): `DP_D1`, `DP_D1H`, `DP_L1`, `DP_L1S`, `DP_L2Pro`, `MPC15` and others. Commands as in 5.4.
- **Lujiang A4** (`normal/a4/*`): `DP_A4`, `DP_L80`, `DP_L81`, `DP_L81H`, `DP_A80`, `DP_A81`, `MT80` to `MT83`, `MT81H`, `APA40` to `APA49`, `APL86` and others. Commands as in 5.3.

The model list in the app (59 entries) gives, for each model, the Bluetooth names, paper sizes and supported paper types.

## 7. Adding a printer

1. Find the Bluetooth name the printer advertises.
2. Find the matching entry in the app's `PrinterEnum`; its SDK class tells you the family (AiYin, Lujiang label, Lujiang A4).
3. Add a profile in `MODELS` with the name pattern, DPI, print width, density range and paper types, then print a test page.
4. Update the table in section 1 and set the status to tested once it works on hardware.
