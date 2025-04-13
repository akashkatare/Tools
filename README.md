# 📱 iOS Application Penetration Testing Essentials: Tool Setup Guide

A complete setup guide for essential tools used in iOS application security testing — including sideloading apps, setting up Frida, jailbreak tweaks, and jailbreak detection bypass utilities.

---

## 🧾 Apple Account Setup

- 🔗 [Create Apple ID](https://account.apple.com/account)
- 🔗 [Create Apple Developer Account (same email)](https://account.apple.com/account?appId=632&returnUrl=https%3A%2F%2Fdeveloper.apple.com%2Faccount%2F)

---

## 📦 Sideloading Tools

- 🔗 [Sideloadly](https://sideloadly.io/#download)
- Follow below-mentioned steps for fresh installations: (Windows)
#### iTunes: Download iTunes
- https://www.apple.com/itunes/download/win64.
- Right-click on `iTunes64Setup.exe` and run as administrator.

#### iCloud: Download iCloud
- https://updates.cdn-apple.com/2020/windows/001-39935-20200911-1A70AA56-F448-11EA-8CC0-99D41950005E/iCloudSetup.exe.
- Right-click on `iCloudSetup.exe` and run as administrator.

#### Install Sideloadly:
- Download Sideloadly
- https://sideloadly.io/SideloadlySetup64.exe.
- Right-click on `SideloadlySetup64.exe` and run as administrator.
- Launch Sideloadly:
- Run Sideloadly as an administrator. It will prompt you to Download Anisette—click "Yes."
- Now, Sideloadly should function properly.
Note: If you don't have a developer account, register for one. Note that apps installed with a free account will expire after 7 days, requiring a refresh or reinstallation. A paid developer account allows for a 365-day validity.

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
