# 🔥 HiddenEye 2025 – Fixed Version (Python 3.10 Compatible)

This repository contains a fully working version of HiddenEye tested in 2025.  
✅ Supports Python 3.10 only  
❌ Not compatible with Python 3.11, 3.12, or 3.13+

Made with 💻 by Hasnain Dark Net

---

<details>
<summary><strong>⚙️ Step 1: System Update & Install Required Packages</strong></summary>

<br>

```bash
sudo apt update
sudo apt install -y build-essential wget curl libssl-dev zlib1g-dev
```

</details>

---

<details>
<summary><strong>🐍 Step 2: Install Python 3.10</strong></summary>

<br>

```bash
cd /tmp
wget https://www.python.org/ftp/python/3.10.13/Python-3.10.13.tgz
tar -xf Python-3.10.13.tgz
cd Python-3.10.13
./configure --enable-optimizations
make -j$(nproc)
sudo make altinstall
```

</details>

---

<details>
<summary><strong>🔎 Step 3: Verify Python Installation</strong></summary>

<br>

```bash
python3.10 --version
```

✅ Output should be:
```
Python 3.10.13
```

</details>

---

<details>
<summary><strong>📦 Step 4: Install Python Modules</strong></summary>

<br>

```bash
python3.10 -m pip install requests pyngrok psutil colorama wget rich
```

</details>

---

<details>
<summary><strong>🛠️ Step 5: Fix "pgrep" Module Error</strong></summary>

<br>

Open the file:

```bash
nano ~/hiddeneye/HiddenEye_Legacy/Defs/ImportManager/unsorted_will_be_replaced.py
```

🔁 Replace this line:

```python
from pgrep import pgrep as check_process
```

✅ With this code:

```python
import psutil

def check_process(process_name):
    for proc in psutil.process_iter(['name']):
        if proc.info['name'] and process_name in proc.info['name']:
            return True
    return False
```

💾 Save it:
- Press `CTRL + O`, then `Enter`
- Exit with `CTRL + X`

</details>

---

<details>
<summary><strong>🚀 Step 6: Run HiddenEye</strong></summary>

<br>

```bash
cd ~/hiddeneye/HiddenEye_Legacy
python3.10 HiddenEye.py
```

</details>

---

<details>
<summary><strong>📜 Step 7: Accept License (EULA)</strong></summary>

<br>

When prompted:

```
HiddenEye EULA >>

[1] Accept  
[2] Decline  
```

👉 Type:

```bash
1
```

✅ Tool will now run.

</details>

---

<details>
<summary><strong>⚠️ Python Version Warning</strong></summary>

<br>

🚫 HiddenEye **does not work** with:

- Python 3.11  
- Python 3.12  
- Python 3.13+

✅ Only use:

```bash
Python 3.10.x
```

</details>

---

<details>
<summary><strong>🙌 Credits</strong></summary>

<br>

Fixed & Tested by **Hasnain Dark Net**  
📺 Subscribe, ⭐ Star this repo, and drop a comment if you need help.

</details>
