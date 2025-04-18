# 📱 iOS Application Penetration Testing Essentials: Tool Setup Guide

A complete setup guide for essential tools used in iOS application security testing — including sideloading apps, setting up Frida, jailbreak tweaks, and jailbreak detection bypass utilities.

---

## 🧾 Apple Account Setup

- 🔗 [Create Apple ID](https://account.apple.com/account)
- 🔗 [Create Apple Developer Account (same email)](https://account.apple.com/account?appId=632&returnUrl=https%3A%2F%2Fdeveloper.apple.com%2Faccount%2F)

---

## 📦 Sideloading Tools

### 🔸 Follow below-mentioned steps for fresh installations: (Windows)
Note: For Windows make sure you have the web version of iTunes & iCloud installed. You must uninstall Microsoft Store iTunes & iCloud (if present), then install the non Microsoft Store version from: 
- **iTunes: Download iTunes**
- https://www.apple.com/itunes/download/win64.
- Right-click on `iTunes64Setup.exe` and run as administrator.

- **iCloud: Download iCloud**
- https://updates.cdn-apple.com/2020/windows/001-39935-20200911-1A70AA56-F448-11EA-8CC0-99D41950005E/iCloudSetup.exe.
- Right-click on `iCloudSetup.exe` and run as administrator.

- **Install Sideloadly:**
- Download Sideloadly
- https://sideloadly.io/SideloadlySetup64.exe.
- Right-click on `SideloadlySetup64.exe` and run as administrator.
- Launch Sideloadly:
- Run Sideloadly as an administrator. It will prompt you to Download Anisette—click "Yes."
- Now, Sideloadly will function properly.
Note: If you don't have a developer account, register for one. Note that apps installed with a free account will expire after 7 days, requiring a refresh or reinstallation. A paid developer account allows for a 365-day validity.

**How many apps can I sideload?**
- On iOS 7, 8, 9, you can sideload unlimited apps. However, on iOS 10, 11, 12, 13, 14, 15, 16 and higher, a free Apple Developer account is limited to 3 sideloaded apps. A paid Apple Developer Account has no such limit. If you're on iOS 16.1.2 & lower, you can remove these limitations by using WDBRemoveThreeAppLimit.

### 🔸 Troubleshoot
- if you're experiencing issues installing Sideloadly or using it to install apps, please follow these steps to resolve them:
- **Uninstall Sideloadly:**
- Go to  `C:\\Users\\{YourUsername}\\AppData\\Roaming\\Microsoft\\Windows\\Start Menu\\Programs\\Sideloadly` and click on Uninstall.
- **Remove iCloud and iTunes:**
- Open Control Panel > Programs > Programs and Features.
- Uninstall iCloud and iTunes if they are installed.
- Check Microsoft Store: Search for "iCloud" and "iTunes." If they appear as installed, uninstall both.
- **Download Everything Tool:**
- https://www.voidtools.com/Everything-1.4.1.1026.x86-Setup.exe and install it.
- **Delete Temporary Sideloadly Files:**
- Launch Everything, search for Sideloadly, and delete any temporary installation files. Some directories may require administrative access.

For Other issues refer:
- https://sideloadly.io/#faq

### 🔹 AltServer (AltStore)
- 💻 [AltServer for Windows](https://cdn.altstore.io/file/altstore/altinstaller.zip)
- 🍎 [AltServer for macOS](https://cdn.altstore.io/file/altstore/altserver.zip)
- 🔗 [Official AltStore Website](https://altstore.io/)

---

## 🧙 TrollStore Setup

### 🔸 Install TrollStore 2 Without Jailbreak on All Devices - Full Guide  
🔗 [TrollStore GitHub Guide](https://github.com/iOSGuides/installing-trollstore)

### 🔸 On Jailbroken Devices

1. Open **Cydia**, **Sileo**, or **Zebra**
2. Search and install **TrollStore Helper**
3. Open **TrollStore Helper**
4. Tap **Install TrollStore**

---

## 🧰 3uTools

🔗 https://www.3u.com/

---

## 🧠 Frida & Objection Setup

> Make sure you have Python and pip installed.

### 📥 Install:

```bash
pip install frida
pip install frida-tools
pip install objection
```

🛠️ *Issue with latest version? Downgrade Frida:*

```bash
pip uninstall frida
pip install frida==16.5.1
```

### 🔄 Upgrade:

```bash
pip install frida --upgrade
pip install frida-tools --upgrade
pip install objection --upgrade
```

### ❌ Uninstall:

```bash
pip uninstall frida
pip uninstall frida-tools
pip uninstall objection
```

```Troubleshoot
# Create a virtual environment
python3 -m venv frida-env

# Activate the virtual environment
source frida-env/bin/activate

# Install the specific version of frida
pip install frida==16.5.1
```

---
# 🧠 How to Get the Decrypted IPA File of Installed iOS Apps

This guide explains how to set up a Linux environment (e.g., Kali) to decrypt and dump IPA files from a **jailbroken iOS device** using `usbfluxd` and `frida-ios-dump`.

---

## 📥 1. Install Dependencies

```bash
sudo apt update
sudo apt install -y avahi-daemon build-essential git libimobiledevice-1.0-6 \
libtool pkg-config python3-dev make usbmuxd libusbmuxd-tools autoconf automake
```

---

## 🛠️ 2. Build & Install `libplist` and `usbfluxd`

```bash
# Clone the required repositories
git clone https://github.com/libimobiledevice/libplist
git clone https://github.com/corellium/usbfluxd

# Build and install libplist
cd libplist
./autogen.sh
make
sudo make install
cd ..

# Build and install usbfluxd
cd usbfluxd
./autogen.sh
make
sudo make install
cd ..
```

---

## 🚀 3. Start Required Services

```bash
# Start usbmuxd service
sudo systemctl start usbmuxd

# Start Avahi daemon (for mDNS)
sudo avahi-daemon

# Run usbfluxd in foreground
sudo usbfluxd -f -n
```

> 📝 Keep `usbfluxd` running in the foreground or in a separate terminal window.

---

## 🔁 4. SSH Forwarding Over USB

```bash
# Forward local port 2222 to device port 22
iproxy 2222 22
```

> 💡 Your device must be jailbroken and have **OpenSSH** installed.

---

## 📦 5. Clone and Set Up `frida-ios-dump`

```bash
git clone https://github.com/AloneMonkey/frida-ios-dump.git
cd frida-ios-dump
pip3 install -r requirements.txt
```

---

## 📲 6. Dump the Decrypted IPA File

```bash
# Replace "AppName" with the actual app name as shown on the device
./dump.py "AppName"
```

> Example:
> ```bash
> ./dump.py "DVIA-v2"
> ```

---

## ✅ Notes

- The iOS device must be **jailbroken**.
- `frida-server` must be **running on the iOS device**, typically launched via SSH.
- Make sure `usbmuxd` and `usbfluxd` are running properly before starting the dump process.
- Use tools like `Filza`, `ssh`, or `Netatalk` to check device file structure if needed.

---

## 🔗 Resources

- [usbfluxd – Corellium](https://github.com/corellium/usbfluxd)
- [frida-ios-dump – AloneMonkey](https://github.com/AloneMonkey/frida-ios-dump)
- [Frida Project](https://frida.re)
- [Kali Linux Python Packaging Guide](https://www.kali.org/docs/general-use/python3-external-packages/)


---
## 🧰 Essential Tools for Jailbroken Devices

> These tools support **unc0ver**, **Taurine**, **Palera1n**, **Dopamine**, **RootHide**, etc.

| #  | Tool                       | Repo / Notes |
|----|----------------------------|--------------|
| 1  | **Filza File Manager**         | https://tigisoftware.com/cydia/ |
| 2  | **OpenSSH**                    | https://repo.procurs.us/ <br> http://apt.thebigboss.org/repofiles/cydia/ |
| 3  | **Darwin CC Tools** `otool`, `nm`, `strings` | https://apt.binger.com |
| 4  | **AppSync Unified**           | https://cydia.akemi.ai/ <br> http://apt.saurik.com/cydia/ |
| 5  | **Apple File Conduit 2**      | https://cydia.akemi.ai/ <br> http://apt.saurik.com/cydia/ <br> http://apt.thebigboss.org/repofiles/cydia/ |
| 6  | **Frida**                     | https://build.frida.re/ |
| 7  | **LLDB**                      | https://repo.procurs.us/ <br> https://apt.procurs.us/ |
| 8  | **Cycript**                   | https://apt.binger.com/ |
| 9  | **PowerSelector**             | https://cydia.ichitaso.com/ <br> https://ichitaso.com/apt/ |
| 10 | **SSL Bypass**                | https://github.com/evilpenguin/SSLBypass/blob/main/packages/com.evilpenguin.sslbypass_1.0-5%2Bdebug_iphoneos-arm.deb |
| 11 | **SSL Kill Switch 2**         | https://julioverne.github.io/ |
| 12 | **SSL Kill Switch 3**         | https://repo.misty.moe/apt <br> https://github.com/NyaMisty/ssl-kill-switch3/releases/tag/v1.5.1 |
| 13 | **Location Faker**            | https://ios.tweaks.fun/ |
| 14 | **CCPower (iOS 15+)**         | http://apt.thebigboss.org/repofiles/cydia/ |
| 15 | **NewTerm 2 / 3 / 3 beta**    | https://repo.chariz.com/ |
| 16 | **CrackerXL+**                | http://cydia.iphonecake.com |
| 17 | **TrollDecrypt**              | https://github.com/donato-fiore/TrollDecrypt/releases |
| 18 | **Flex 3**                    | https://getdelta.co |

---

## 🛡️ Jailbreak Detection Bypass Tools

| #  | Tool                      | Repo / Notes |
|----|---------------------------|--------------|
| 1  | **Shadow**                | https://ios.jjolano.me/ |
| 2  | **HideJB**                | http://apt.thebigboss.org/repofiles/cydia/ |
| 3  | **AJB**                   | http://apt.thebigboss.org/repofiles/cydia/ |
| 4  | **Hestia**                | https://havoc.app/ |
| 5  | **Liberty Lite**          | https://ryleyangus.com/repo/ |
| 6  | **A-Bypass**              | https://repo.co.kr/ |
| 7  | **Kern Bypass**           | https://repo.misty.moe/apt/ <br> https://cydia.ichitaso.com/ |
| 8  | **unsub**                 | https://repo.hackyouriphone.org/ |
| 9  | **VnodeBypass**           | https://cydia.ichitaso.com/ <br> *Disable to use Cydia* |
| 10 | **JailProtect**           | https://julioverne.github.io/ |
| 11 | **Choicy**                | http://apt.thebigboss.org/repofiles/cydia/ |
| 12 | **FlyJB X**               | https://mrepo.org/ <br> *Enable Dobby in Tweaks app* |
| 13 | **iHide**                 | https://repo.kc57.com/ |
| 14 | **bypassJB (SniperBypassJB)** | http://apt.thebigboss.org/repofiles/cydia/ |

---

## 💡 Manual Installation Tip

If a tool requires a `.deb` file to be manually installed, use the following:

```sh
dpkg -i yourpackage.deb
uicache -a
```

---
