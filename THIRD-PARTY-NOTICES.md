# Third-Party Notices

Ektypos ("Print it. No typos.") is a single-file, offline Bluetooth printing tool. It includes or is based on the third-party work listed below. Each item shows its copyright holder and license. The full license texts are in the appendices at the end of this file.

This file covers version 3.3.2 of the tool. The tool's own code is Copyright (C) 2026 The Ektypos authors and licensed under the GNU Affero General Public License, version 3 or (at your option) any later version (AGPL-3.0-or-later); see the `LICENSE` file. The third-party components below keep their own licenses, all of which are compatible with distribution inside an AGPL-3.0 work.

> Upstream license files were checked on 13 November 2026 (qrcode-terminal, Octicons, zxing-cpp, 0xMH/fichero-printer, TeX Gyre Adventor readme). No open items remain.

## Contents

1. Software
2. Icons
3. Fonts
4. Data
5. Trademarks
6. Appendices: A MIT, B Apache 2.0, C SIL OFL 1.1, D GUST Font License, E CC BY 4.0

---

## 1. Software

### 1.1 QR Code encoder

- Copyright (c) 2009 Kazuhiko Arase, http://www.d-project.com/
- License: MIT (Appendix A)
- Included as a vendored copy taken from the `qrcode-terminal` package, modified to run in a browser and refactored. The original copyright header is kept in the source.
- Packaging and modifications by the `qrcode-terminal` project (https://github.com/gtanner/qrcode-terminal), licensed under the Apache License 2.0 (Appendix B). The project's LICENSE file gives no separate copyright line; its modifications are credited to the qrcode-terminal contributors. Further modified for Ektypos (browser port, refactoring).
- "QR Code" is a registered trademark of DENSO WAVE INCORPORATED.

### 1.2 Printer protocol (fichero-printer)

- Protocol documentation consulted: `0xMH/fichero-printer`, https://github.com/0xMH/fichero-printer (README and docs/PROTOCOL.md), together with Ektypos's own analysis of the Fichero Android app.

---

## 2. Icons

The tool embeds 9,793 icons from the three sets below, plus 80 built-in icons drawn for this tool. Brand and logo icons were left out of all sets from version 3.3.0. The embedded icons were converted from SVG files into a compact path-data format. **This is a change from the originals** and is indicated here as the Apache License and CC BY license require.

### 2.1 Material Design Icons

- Copyright: Pictogrammers, https://pictogrammers.com (7,205 icons)
- License: Apache License 2.0 (Appendix B)
- Changes: converted to a compact path format; the 242 icons tagged "Brand / Logo" were removed.

### 2.2 Font Awesome Free 7

- Font Awesome Free 7 by @fontawesome, https://fontawesome.com. Copyright Fonticons, Inc. (2,250 icons: 1,980 solid, 270 regular)
- Icons license: Creative Commons Attribution 4.0 International (CC BY 4.0), https://creativecommons.org/licenses/by/4.0/ (Appendix E). License details: https://fontawesome.com/license/free
- Changes: converted to a compact path format; the Font Awesome and Web Awesome logo icons were removed.

### 2.3 Octicons

- Copyright (c) 2026 GitHub Inc. (338 icons; the logo-github, mark-github, logo-gist and copilot marks are not included)
- License: MIT (Appendix A)
- The GitHub logo marks are trademarks of GitHub, Inc. and are subject to GitHub's logo policy. They are not licensed by the MIT license.

### 2.4 Built-in icons

80 icons drawn for this tool (only the Lucide data format was used as a model). They are part of the tool's own work, under the AGPL-3.0-or-later. The app icon is also Ektypos's own artwork.

### 2.5 Ektypos icon and logo

- The Ektypos app icon, its maskable variants and the Ektypos logos (light and dark) are original artwork made for this project. Copyright (C) 2026 The Ektypos authors. They are covered by the project license, AGPL-3.0-or-later (see `LICENSE`).
- The lettering of the logo ("Ektypos" and "PRINT IT. NO TYPOS.") is set in Poppins and converted to outlines. Poppins is under the SIL Open Font License 1.1 (Appendix C), which does not restrict artwork or documents made with the font. No font file is included in the logo.
- The name "Ektypos" and its logo identify this project. The software license lets you copy and modify the artwork, but please do not use the name or logo in a way that suggests a modified version or another product is the official Ektypos.

---

## 3. Fonts

The tool embeds 19 font files, converted to WOFF and reduced (subsetted) to about 330 Latin characters each. Copyright statements and license information are kept in each font file's metadata.

**Renamed Modified Versions.** Subsetting and format conversion make these Modified Versions under the SIL Open Font License. Because "Lora" and "Liberation" are Reserved Font Names, the modified files are renamed inside the font and in the tool:

| In Ektypos | Modified version of |
|---|---|
| Ektypos Book ("Book serif") | Lora |
| Ektypos Sans ("Sans") | Liberation Sans |
| Ektypos Serif ("Serif") | Liberation Serif |
| Ektypos Mono ("Mono") | Liberation Mono |

| Font | Copyright | License |
|---|---|---|
| Poppins (Regular, Medium, Bold, Italic, Bold Italic) | Copyright 2020 The Poppins Project Authors (https://github.com/itfoundry/Poppins) | SIL OFL 1.1 (Appendix C) |
| Lora v3.008 (variable, roman and italic) | Copyright 2011 The Lora Project Authors (https://github.com/cyrealtype/Lora-Cyrillic), with Reserved Font Name "Lora". | SIL OFL 1.1 (Appendix C) |
| Liberation Sans, Liberation Serif and Liberation Mono v2.1.5 (Regular, Bold) | Digitized data copyright (c) 2010 Google Corporation with Reserved Font Arimo, Tinos and Cousine. Copyright (c) 2012 Red Hat, Inc. with Reserved Font Name Liberation. | SIL OFL 1.1 (Appendix C) |
| TeX Gyre Heros Condensed (Regular, Bold), TeX Gyre Chorus (Regular), TeX Gyre Schola (Bold) | Copyright 2006, 2009 for TeX Gyre extensions by B. Jackowski and J.M. Nowacki (on behalf of TeX users groups). | GUST Font License (Appendix D) |
| TeX Gyre Adventor v2.501 (Regular, Bold) | Copyright 2007-2018 for TeX Gyre extensions by B. Jackowski, J.M. Nowacki, et al. (on behalf of TeX USERS GROUPS). Vietnamese characters were added by Han The Thanh. | GUST Font License (Appendix D). The font files' metadata does not state the license; README-TeX-Gyre-Adventor.txt in the TeX Gyre distribution states: "This work can be freely used and distributed under the GUST Font License". |

Notes:

- In the tool, the TeX Gyre fonts appear under the names "Heros Condensed", "Adventor", "Chorus" and "Schola". These are display names only.
- "Liberation" is a trademark of Red Hat, Inc.

---

## 4. Data

- **PDF417 codeword table:** the 7.4 KB codeword-pattern table used by the PDF417 encoder was extracted from zxing-cpp 2.2.1 (https://github.com/zxing-cpp/zxing-cpp), Copyright 2016 Nu-book Inc. and Copyright 2016 ZXing authors, Apache License 2.0 (Appendix B). Changes: converted to a compact embedded data format. The patterns themselves are defined by ISO/IEC 15438.
- **Emoji picker:** the picker uses Unicode emoji characters with their Unicode character names. No emoji artwork is embedded; emoji are drawn by the viewer's own system font. Unicode data is provided by Unicode, Inc. under the Unicode License, https://www.unicode.org/license.txt.

---

## 5. Trademarks

All product names, brand names and logos mentioned in or available through this tool belong to their respective owners, and their use does not imply endorsement. In particular:

- "QR Code" is a registered trademark of DENSO WAVE INCORPORATED.
- "Fichero" is a name used by the manufacturer and retailer of the printers this tool works with. It is used only to describe compatibility. This tool is not affiliated with them.
- Brand icons present in the Material Design Icons and Octicons sets are trademarks of their owners.

---

# Appendices: license texts

## Appendix A. MIT License

Applies to: QR Code encoder (1.1) and Octicons (2.3).

```text
Copyright (c) 2009 Kazuhiko Arase
Copyright (c) 2026 GitHub Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Appendix B. Apache License, Version 2.0

Applies to: Material Design Icons (2.1), the PDF417 codeword table (4) and the `qrcode-terminal` packaging (1.1).

```text

                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
      outstanding shares, or (iii) beneficial ownership of such entity.

      "You" (or "Your") shall mean an individual or Legal Entity
      exercising permissions granted by this License.

      "Source" form shall mean the preferred form for making modifications,
      including but not limited to software source code, documentation
      source, and configuration files.

      "Object" form shall mean any form resulting from mechanical
      transformation or translation of a Source form, including but
      not limited to compiled object code, generated documentation,
      and conversions to other media types.

      "Work" shall mean the work of authorship, whether in Source or
      Object form, made available under the License, as indicated by a
      copyright notice that is included in or attached to the work
      (an example is provided in the Appendix below).

      "Derivative Works" shall mean any work, whether in Source or Object
      form, that is based on (or derived from) the Work and for which the
      editorial revisions, annotations, elaborations, or other modifications
      represent, as a whole, an original work of authorship. For the purposes
      of this License, Derivative Works shall not include works that remain
      separable from, or merely link (or bind by name) to the interfaces of,
      the Work and Derivative Works thereof.

      "Contribution" shall mean any work of authorship, including
      the original version of the Work and any modifications or additions
      to that Work or Derivative Works thereof, that is intentionally
      submitted to Licensor for inclusion in the Work by the copyright owner
      or by an individual or Legal Entity authorized to submit on behalf of
      the copyright owner. For the purposes of this definition, "submitted"
      means any form of electronic, verbal, or written communication sent
      to the Licensor or its representatives, including but not limited to
      communication on electronic mailing lists, source code control systems,
      and issue tracking systems that are managed by, or on behalf of, the
      Licensor for the purpose of discussing and improving the Work, but
      excluding communication that is conspicuously marked or otherwise
      designated in writing by the copyright owner as "Not a Contribution."

      "Contributor" shall mean Licensor and any individual or Legal Entity
      on behalf of whom a Contribution has been received by Licensor and
      subsequently incorporated within the Work.

   2. Grant of Copyright License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      copyright license to reproduce, prepare Derivative Works of,
      publicly display, publicly perform, sublicense, and distribute the
      Work and such Derivative Works in Source or Object form.

   3. Grant of Patent License. Subject to the terms and conditions of
      this License, each Contributor hereby grants to You a perpetual,
      worldwide, non-exclusive, no-charge, royalty-free, irrevocable
      (except as stated in this section) patent license to make, have made,
      use, offer to sell, sell, import, and otherwise transfer the Work,
      where such license applies only to those patent claims licensable
      by such Contributor that are necessarily infringed by their
      Contribution(s) alone or by combination of their Contribution(s)
      with the Work to which such Contribution(s) was submitted. If You
      institute patent litigation against any entity (including a
      cross-claim or counterclaim in a lawsuit) alleging that the Work
      or a Contribution incorporated within the Work constitutes direct
      or contributory patent infringement, then any patent licenses
      granted to You under this License for that Work shall terminate
      as of the date such litigation is filed.

   4. Redistribution. You may reproduce and distribute copies of the
      Work or Derivative Works thereof in any medium, with or without
      modifications, and in Source or Object form, provided that You
      meet the following conditions:

      (a) You must give any other recipients of the Work or
          Derivative Works a copy of this License; and

      (b) You must cause any modified files to carry prominent notices
          stating that You changed the files; and

      (c) You must retain, in the Source form of any Derivative Works
          that You distribute, all copyright, patent, trademark, and
          attribution notices from the Source form of the Work,
          excluding those notices that do not pertain to any part of
          the Derivative Works; and

      (d) If the Work includes a "NOTICE" text file as part of its
          distribution, then any Derivative Works that You distribute must
          include a readable copy of the attribution notices contained
          within such NOTICE file, excluding those notices that do not
          pertain to any part of the Derivative Works, in at least one
          of the following places: within a NOTICE text file distributed
          as part of the Derivative Works; within the Source form or
          documentation, if provided along with the Derivative Works; or,
          within a display generated by the Derivative Works, if and
          wherever such third-party notices normally appear. The contents
          of the NOTICE file are for informational purposes only and
          do not modify the License. You may add Your own attribution
          notices within Derivative Works that You distribute, alongside
          or as an addendum to the NOTICE text from the Work, provided
          that such additional attribution notices cannot be construed
          as modifying the License.

      You may add Your own copyright statement to Your modifications and
      may provide additional or different license terms and conditions
      for use, reproduction, or distribution of Your modifications, or
      for any such Derivative Works as a whole, provided Your use,
      reproduction, and distribution of the Work otherwise complies with
      the conditions stated in this License.

   5. Submission of Contributions. Unless You explicitly state otherwise,
      any Contribution intentionally submitted for inclusion in the Work
      by You to the Licensor shall be under the terms and conditions of
      this License, without any additional terms or conditions.
      Notwithstanding the above, nothing herein shall supersede or modify
      the terms of any separate license agreement you may have executed
      with Licensor regarding such Contributions.

   6. Trademarks. This License does not grant permission to use the trade
      names, trademarks, service marks, or product names of the Licensor,
      except as required for reasonable and customary use in describing the
      origin of the Work and reproducing the content of the NOTICE file.

   7. Disclaimer of Warranty. Unless required by applicable law or
      agreed to in writing, Licensor provides the Work (and each
      Contributor provides its Contributions) on an "AS IS" BASIS,
      WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or
      implied, including, without limitation, any warranties or conditions
      of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A
      PARTICULAR PURPOSE. You are solely responsible for determining the
      appropriateness of using or redistributing the Work and assume any
      risks associated with Your exercise of permissions under this License.

   8. Limitation of Liability. In no event and under no legal theory,
      whether in tort (including negligence), contract, or otherwise,
      unless required by applicable law (such as deliberate and grossly
      negligent acts) or agreed to in writing, shall any Contributor be
      liable to You for damages, including any direct, indirect, special,
      incidental, or consequential damages of any character arising as a
      result of this License or out of the use or inability to use the
      Work (including but not limited to damages for loss of goodwill,
      work stoppage, computer failure or malfunction, or any and all
      other commercial damages or losses), even if such Contributor
      has been advised of the possibility of such damages.

   9. Accepting Warranty or Additional Liability. While redistributing
      the Work or Derivative Works thereof, You may choose to offer,
      and charge a fee for, acceptance of support, warranty, indemnity,
      or other liability obligations and/or rights consistent with this
      License. However, in accepting such obligations, You may act only
      on Your own behalf and on Your sole responsibility, not on behalf
      of any other Contributor, and only if You agree to indemnify,
      defend, and hold each Contributor harmless for any liability
      incurred by, or claims asserted against, such Contributor by reason
      of your accepting any such warranty or additional liability.

   END OF TERMS AND CONDITIONS

   APPENDIX: How to apply the Apache License to your work.

      To apply the Apache License to your work, attach the following
      boilerplate notice, with the fields enclosed by brackets "[]"
      replaced with your own identifying information. (Don't include
      the brackets!)  The text should be enclosed in the appropriate
      comment syntax for the file format. We also recommend that a
      file or class name and description of purpose be included on the
      same "printed page" as the copyright notice for easier
      identification within third-party archives.

   Copyright [yyyy] [name of copyright owner]

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```

## Appendix C. SIL Open Font License, Version 1.1

Applies to: Poppins, Lora, Liberation Serif, Liberation Mono. The copyright statements of each font are in section 3.

```text
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide
development of collaborative font projects, to support the font creation
efforts of academic and linguistic communities, and to provide a free and
open framework in which fonts may be shared and improved in partnership
with others.

The OFL allows the licensed fonts to be used, studied, modified and
redistributed freely as long as they are not sold by themselves. The
fonts, including any derivative works, can be bundled, embedded,
redistributed and/or sold with any software provided that any reserved
names are not used by derivative works. The fonts and derivatives,
however, cannot be released under any other type of license. The
requirement for fonts to remain under this license does not apply
to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright
Holder(s) under this license and clearly marked as such. This may
include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the
copyright statement(s).

"Original Version" refers to the collection of Font Software components as
distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting,
or substituting -- in part or in whole -- any of the components of the
Original Version, by changing formats or by porting the Font Software to a
new environment.

"Author" refers to any designer, engineer, programmer, technical
writer or other person who contributed to the Font Software.

PERMISSION & CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining
a copy of the Font Software, to use, study, copy, merge, embed, modify,
redistribute, and sell modified and unmodified copies of the Font
Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components,
in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled,
redistributed and/or sold with any software, provided that each copy
contains the above copyright notice and this license. These can be
included either as stand-alone text files, human-readable headers or
in the appropriate machine-readable metadata fields within text or
binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font
Name(s) unless explicit written permission is granted by the corresponding
Copyright Holder. This restriction only applies to the primary font name as
presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font
Software shall not be used to promote, endorse or advertise any
Modified Version, except to acknowledge the contribution(s) of the
Copyright Holder(s) and the Author(s) or with their explicit written
permission.

5) The Font Software, modified or unmodified, in part or in whole,
must be distributed entirely under this license, and must not be
distributed under any other license. The requirement for fonts to
remain under this license does not apply to any document created
using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are
not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT
OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE
COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL
DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM
OTHER DEALINGS IN THE FONT SOFTWARE.
```

## Appendix D. GUST Font License

Applies to: TeX Gyre Heros Condensed, Chorus, Schola and Adventor. The license text below is version 1.0 (22 June 2009), the current version published at https://tug.org/fonts/licenses/GUST-FONT-LICENSE.txt. The TeX Gyre distribution ships an earlier preliminary text (2006-09-30) that is identical apart from its first line and that points to this address for the most recent version. The license is an instance of the LaTeX Project Public License, version 1.3c or later: https://www.latex-project.org/lppl/lppl-1-3c/

```text
% This is version 1.0, dated 22 June 2009, of the GUST Font License.
% (GUST is the Polish TeX Users Group, http://www.gust.org.pl)
%
% For the most recent version of this license see
% http://www.gust.org.pl/fonts/licenses/GUST-FONT-LICENSE.txt
% or
% http://tug.org/fonts/licenses/GUST-FONT-LICENSE.txt
%
% This work may be distributed and/or modified under the conditions
% of the LaTeX Project Public License, either version 1.3c of this
% license or (at your option) any later version.
%
% Please also observe the following clause:
% 1) it is requested, but not legally required, that derived works be
%    distributed only after changing the names of the fonts comprising this
%    work and given in an accompanying "manifest", and that the
%    files comprising the Work, as listed in the manifest, also be given
%    new names. Any exceptions to this request are also given in the
%    manifest.
%
%    We recommend the manifest be given in a separate file named
%    MANIFEST-<fontid>.txt, where <fontid> is some unique identification
%    of the font family. If a separate "readme" file accompanies the Work,
%    we recommend a name of the form README-<fontid>.txt.
%
% The latest version of the LaTeX Project Public License is in
% http://www.latex-project.org/lppl.txt and version 1.3c or later
% is part of all distributions of LaTeX version 2006/05/20 or later.
```

## Appendix E. Creative Commons Attribution 4.0 International (CC BY 4.0)

Applies to: the Font Awesome Free icons (2.2). The full legal code is at https://creativecommons.org/licenses/legalcode (CC BY 4.0). In short, you may share and adapt the icons for any purpose, including commercially, as long as you give appropriate credit, provide a link to the license, and indicate if changes were made. Credit, link and change notice are given in section 2.2.
