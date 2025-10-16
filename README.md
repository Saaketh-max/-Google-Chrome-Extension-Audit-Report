# -Google-Chrome-Extension-Audit-Report
Linux-based audit of Google Chrome extensions inside a virtual machine. Includes shell commands, permission analysis, cleanup logs, and a reproducible markdown report for cybersecurity hygiene.


This repository documents a complete browser extension audit performed on Google Chrome running inside a Linux virtual machine. It includes:

    Manual and command-line inspection of installed extensions

    Extraction and analysis of manifest.json permissions

    Identification and removal of suspicious or unused extensions

    Browser performance validation post-cleanup

    Markdown report and log files for reproducibility and sharing

Ideal for cybersecurity learners, forensic analysts, and system hygiene enthusiasts. All steps are reproducible and designed for integration into automated audit scripts or GitHub portfolios.



📦 Audit Workflow (Markdown Code Block)

## 🔧 Chrome Extension Audit – Linux VM

This audit inspects and cleans Google Chrome extensions inside a Linux virtual machine. It extracts permissions, flags suspicious extensions, and generates a report for GitHub.

---

### 🧭 Step-by-Step Commands

#### 1. Navigate to Chrome extension directory
```bash
cd ~/.config/google-chrome/Default/Extensions/


2. Create audit folder

mkdir -p ~/chrome_extension_audit

3. List all extension IDs

ls -1 > ~/chrome_extension_audit/extension_ids.txt

4. Extract extension names and permissions

find . -name "manifest.json" -exec grep -H '"name"\|"permissions"' {} \; > ~/chrome_extension_audit/manifest_permissions.log

5. Identify and remove suspicious extensions

rm -rf ghbmnnjooekpmoecnnnilnnbdlolhkhi/
echo "ghbmnnjooekpmoecnnnilnnbdlolhkhi – Removed due to clipboard access" >> ~/chrome_extension_audit/removed_extensions.txt

6. Restart Chrome browser

pkill chrome && google-chrome &

7. Create audit report

nano ~/chrome_extension_audit/browser_extension_audit.md
Paste your markdown report inside this file.

🚀 Push to GitHub
mkdir ~/browser-extension-audit
mv ~/chrome_extension_audit/* ~/browser-extension-audit/
cd ~/browser-extension-audit
git init
git add .
git commit -m "Initial Chrome extension audit report"
gh repo create chrome-extension-audit --public --source=. --remote=origin
git push -u origin main

