# 🦊 OrangeFox Recovery Builder

This project provides **Jupyter notebooks** for building [OrangeFox Recovery Project (OFRP)](https://orangefox.download/) on Google Colab, Kaggle. 
It automates setting up the build environment, syncing OrangeFox sources, cloning device trees, building recovery images, and downloading results.

---

## 🚀 Features
- 🔧 Automatic setup of Android build environment & repo tool  
- 🔄 Sync OrangeFox sources (supports `12.1` and `14.1`)  
- 🌲 Automatic clone and configure **device trees** directly from GitHub  
- 📋 Check available lunch combos for your device  
- 🏗️ Build OrangeFox for `boot`, `vendor_boot`, or `recovery` partition  
- 📥 One-click download of built `.img`, `.zip`, and other output files  

---

## ⚡ Usage

1. Open the notebook in **Google Colab**:  
   
   https://colab.research.google.com/github/chunix64/jupyter-orangefox-builder/blob/main/Orangefox_Builder.ipynb

2. Run each cell step by step:  
   - **Step 0**: Setup environment  
   - **Step 1**: Sync OrangeFox sources  
   - **Step 2**: Clone your device tree  
   - **Step 3**: Verify device/lunch combo  
   - **Step 4**: Build  
   - **Step 5**: Download results  

---

## 📂 Notebook Structure

1. **🛠️ Prepare Environment**  
   - Install dependencies, repo tool, and OrangeFox build scripts  
   - Configure fake GitHub identity  

2. **🔄 Sync Sources**  
   - Download OrangeFox source tree with `orangefox_sync.sh`  

3. **🌲 Add Device Tree**  
   - Automatic clone your device tree from GitHub  
   - Parse `device.mk` and `AndroidProducts.mk`  
   - Detect **device tree path** and **lunch names**

4. **🤔 Check Devices Available**  
   - Lists detected devices and lunch combos in table format  

5. **🏗️ Build OrangeFox**  
   - Configure build target (`vendorbootimage`, `bootimage`, or `recoveryimage`)  
   - Build using `mka`  

6. **📥 Download Files**  
   - Search and download `.img`, `.zip`, `.cpio`, `.lz4`, `.txt`, etc. from `/out` folder  

---

## ⚠️ Notes
- Colab has **limited storage ≈107GB** but **only ≈68GB free**. Building Android 14 may fail due to insufficient space.
- You can still build Android 14 devices on the **12.1 source** by lowering SDK version in `device.mk` (set `PLATFORM_SDK_VERSION := 31` or lower).  
- Always verify your **lunch name** (e.g. `twrp_CK6n-eng`) before building.  
- This notebook is intended for **testing** and may not produce stable recoveries.  
- Building in Google Colab may fail due to insufficient RAM and CPU, since Google Colab does not support swap. Try kaggle instead
- Kaggle requires account verification to enable internet access.

---

## 📝 TODOs
- Create a compact version for Kaggle (since Kaggle does not support the Colab-style UI form)  
- Improve build stability on Google Colab 

## 📜 License
Apache 2.0 — free and open source.

---

## 🙌 Credits
- [OrangeFox Recovery Project](https://orangefox.download/)  
- [OFRP Sync Scripts](https://gitlab.com/OrangeFox/sync)  
- [Original Notebook Author](https://github.com/chunix64)
