# MSF in Termux
> Installer script for **Metasploit Framework** on Termux (no root required).

A small helper/POC repo that documents a reproducible installer flow for running Metasploit Framework inside a proot-based Linux distribution on Termux.

## Purpose

This file contains a tested, step-by-step installer flow for installing Metasploit Framework inside a proot-based Linux distribution on Termux (Ubuntu used as example). It focuses on reproducibility and safety: review scripts, run in an isolated proot, and keep backups.

## Legal & ethical notice: 
Use Metasploit only on systems you own or where you have explicit, written permission to test. Unauthorized use is illegal and unethical. Always review installer scripts before running and prefer isolated testing environments.

---

## Prerequisites

* Termux installed on an Android device (no root required).
* Stable internet connection.
* At least 1.5–2 GB free storage (more recommended).
* Termux version - 0.118.3

---

## Quick install (example)

1. Install Termux 0.118.3 [Download Termux APK](https://f-droid.org/repo/com.termux_1002.apk) .
2. Update && upgrade Packages :
    ```bash
    pkg update -y && pkg upgrade -y
    ```
3. Install required packages :
   ```bash
   pkg install curl wget git proot-distro
   ```
4. Install Ubuntu using proot-distro :
   ```bash
   proot-distro install ubuntu
   ```
5. Iogin proot-distro :
    ```bash
   proot-distro login ubuntu
    ```
6. Install required packages :
   ```bash
   apt install -y curl wget git
   ```
7. Download the Metasploit installer script :
   ```bash
   curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msf-termux
   ```
8. Make the script executable
   ```bash
    chmod +x msfinstall
    ```
9. Run the installer script
    ```bash
    ./msfinstall
    ```
 
 ## When installation finishes, start Metasploit with:

```bash
msfconsole
```
---

## Security & ethics

Do not use Metasploit for unauthorized access, privacy breaches, or damage. Keep Termux and packages updated.

---

**Credits:** Metasploit Framework and the official installer wrappers — [**@Rapid7**](https://github.com/rapid7).

**License:** MIT — © 2025 IamTechyAnimesh
