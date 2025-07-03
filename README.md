# HiddenEye-2025-Fixed
Fully working HiddenEye for Kali Linux | Python 3.10 Fix | 2025 Version



<details>
<summary><strong>📋 Full Setup Commands (Tested in 2025 – Python 3.10 Only)</strong></summary>

```bash
## ✅ Step 1: Update & install required system packages
sudo apt update
sudo apt install -y build-essential wget curl libssl-dev zlib1g-dev

# ✅ Step 2: Download and install Python 3.10 (HiddenEye works only on this version)
cd /tmp
wget https://www.python.org/ftp/python/3.10.13/Python-3.10.13.tgz
tar -xf Python-3.10.13.tgz
cd Python-3.10.13
./configure --enable-optimizations
make -j$(nproc)
sudo make altinstall

# ✅ Step 3: Confirm Python version
python3.10 --version

# ✅ Step 4: Install all required Python packages
python3.10 -m pip install requests pyngrok psutil colorama wget rich

# ✅ Step 5: Fix old 'pgrep' error in HiddenEye code
nano ~/hiddeneye/HiddenEye_Legacy/Defs/ImportManager/unsorted_will_be_replaced.py

# ❌ Remove this line (if found):
from pgrep import pgrep as check_process

# ✅ Paste this instead:
import psutil

def check_process(process_name):
    for proc in psutil.process_iter(['name']):
        if proc.info['name'] and process_name in proc.info['name']:
            return True
    return False

# ✅ Step 6: Run HiddenEye with correct version
cd ~/hiddeneye/HiddenEye_Legacy
python3.10 HiddenEye.py

# ⛔ NOTE:
# ❌ Do NOT use Python 3.11, 3.12, or 3.13
# ✅ Only Python 3.10 is supported

