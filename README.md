<div align="center">

<img width="1024" height="1024" alt="logo" src="https://github.com/user-attachments/assets/2492cc0d-12de-41a5-8a89-8a1fa18ffd57" />


# AutoPyPDF
### High-Performance AutoCAD ModelSpace Sheet Batch Extractor & PDF Merger

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![PyQt5](https://img.shields.io/badge/PyQt5-UI-green.svg)](https://pypi.org/project/PyQt5/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

*Automated AutoCAD ModelSpace sheet extractor, paper size detector, orientation normalizer, and PDF merger with a modern PyQt5 UI.*

</div>

---

## 🚀 Features

- **AutoCAD Integration:** Direct COM automation (`win32com.client`) to interact with active AutoCAD sessions and ModelSpace.
- **Smart Sheet Processing:** Automatically detects paper sizes, normalizes orientations, and handles multi-sheet extractions.
- **Batch & Single Mode:** Choose between batch processing all drawings or selecting a single target sheet.
- **PDF Merging:** Seamlessly merges multiple extracted PDF sheets into a single, cohesive document using `pypdf`.
- **Modern PyQt5 Interface:** Clean, user-friendly desktop GUI featuring a custom splash screen, status logs, and developer credits.
- **Standalone Executable:** Fully packaged via PyInstaller with bundled assets (`logo.png`, icons).

---

## 🛠️ Built With

This project is built using the following technologies and libraries:

- **Python** - Core programming language
- **PyQt5** - Modern desktop GUI framework
- **pywin32 (`win32com`, `pythoncom`)** - AutoCAD COM automation interface
- **pypdf** - PDF manipulation and merging
- **PyInstaller** - Standalone executable packaging

---

## 📥 Installation & Usage

 1. Download the standalone executable package directly from here: **[Download AutoPyPDF.zip](https://github.com/Mehrshad-Ghorbanzadeh/AutoPyPDF/releases/download/V1.0.0/Setup_AutoPyPDF.exe)**

   *(Make sure AutoCAD is installed and running on your system before launching the app).*

---

## 👨‍💻 Author

**Mehrshad Ghorbanzadeh**
- GitHub: [@Mehrshad-Ghorbanzadeh](https://github.com/Mehrshad-Ghorbanzadeh)
- LinkedIn: [Mehrshad Ghorbanzadeh](https://www.linkedin.com/in/mehrshad-ghorbanzadeh-999422227)

---

## 📄 License

This project is licensed under the terms of the **MIT License**.

## 🛠 AutoPyPDF User Guide

**AutoPyPDF** is a robust desktop automation tool built with **PyQt5** and **Python COM Automation** designed to help engineers and drafters instantly convert Model Space drawings in AutoCAD into individual, neatly organized, and merged PDF sheets.

### 1. AutoCAD Connection
* **Live COM Connection:** No need to open/close files from disk paths. The software automatically connects to the running instance of **AutoCAD** (`GetActiveObject`).
* **Active Drawing Management:** Lists all currently open drawings in AutoCAD, allowing you to select your target drawing seamlessly.

### 2. Title Block Selection
* **Smart Detection:** Scans all block references in Model Space matching your selected title block name.
* **Uniformity:** Assumes all project sheets follow a standardized title block. By picking the block name, the app extracts the `BoundingBox` coordinates of each instance to define individual sheet boundaries.

### 3. Batch PDF Export
* **Spatial Sorting:** Automatically sorts and numbers detected sheets from top-to-bottom and left-to-right (`Sheet_01`, `Sheet_02`, etc.).
* **Automated Plotting:** Sends scripted `-PLOT` commands to AutoCAD (using DWG To PDF.pc3, monochrome CTB, Fit, and Center settings) for every sheet.
* **Paper & Orientation Control:** Automatically detects or allows custom paper sizes (A0–A4) and orientations based on block dimensions.
* **Output Structure:** Saves individual sheets in a dedicated folder next to the DWG file and finally merges them into a single comprehensive, compressed bookmarked PDF (`_Combined.pdf`).

### 4. Single Sheet Export
* If you only need to update or export a single specific sheet without re-running the entire project, you can target and process that specific bounding box instantly.

### 5. Merge Feature
* A standalone utility to combine arbitrary PDF files with automatic or manual page orientation rotation (`AUTO`) for unifying final submittals and reports.

### 6. Robustness & System Safety
* **Idle Polling:** Monitors AutoCAD system variables (`CMDNAMES`) to ensure commands finish cleanly before proceeding.
* **File Lock Prevention:** Automatically terminates active PDF viewer processes (Acrobat, Edge, Foxit, etc.) prior to file overwrites to prevent permission errors.
