# 🔥 HiddenEye 2025 – Fixed Version (Python 3.10 Compatible)

This repository contains a fully working version of HiddenEye tested in 2025.  
✅ Supports Python 3.10 only  
❌ Not compatible with Python 3.11, 3.12, or 3.13+

Made with 💻 by Hasnain Dark Net

---

## ⚙️ Step 1: System Update & Dependencies

```bash
sudo apt update
sudo apt install -y build-essential wget curl libssl-dev zlib1g-dev


🐍 Step 2: Install Python 3.10 (Manual Build)
```bash
cd /tmp
wget https://www.python.org/ftp/python/3.10.13/Python-3.10.13.tgz
tar -xf Python-3.10.13.tgz
cd Python-3.10.13
./configure --enable-optimizations
make -j$(nproc)
sudo make altinstall


