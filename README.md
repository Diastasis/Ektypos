**Ektypose**
The goal is to provide one universal, self-contained print tool that works with as many Bluetooth printers as possible. New models are added over time by working out how each one communicates, whether through existing open-source projects, analysis of the vendor’s official app, or testing against real hardware.

**Device support:**
Bluetooth connectivity and print protocols (commands, services, flow control, image encoding) for a growing list of printer models and brands. Devices currently supported:
- Fichero D11s label printer (identifies as FICHERO_5836) AiYin label familly.
- Fichero (identifies as FICHERO_6181, Fichero 4437 or Fichero 5622) AiYin A4 familly.

**Features:**
A single offline HTML application with a label and document designer, text, images, barcodes and QR codes, templates, batch printing from spreadsheet data, and multi-sheet layouts. It runs on desktop and mobile and in the future it will be able to be installed as a PWA or Android app.

**Usage:**
You can use the online instance or download and the self-contained html file that runs locally. In both cases, everything is local and runs in your browser with no cloud dependency. Please note that you need a chrome based browser to use the Bluetooth to connect to your device. In case a non chrome based browser is used, the tool can still be used to generate and export the labels but you cannot print direcly to your printer.
