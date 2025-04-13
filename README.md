# 📱 Essential & Jailbreak Bypass Tools for iOS

This repository lists essential tools and jailbreak detection bypass utilities for iOS, compatible with jailbreaks like **unc0ver**, **Taurine**, **Palera1n**, **Dopamine**, **Dopamine RootHide**, and **Bootstrap**.

---

## 🧰 Essential Tools



| No. | Tool                          | Repository / Notes |
|-----|-------------------------------|--------------------|
| 1   | **Filza File Manager**        | https://tigisoftware.com/cydia/ |
| 2   | **OpenSSH**                   | https://repo.procurs.us/ <br> http://apt.thebigboss.org/repofiles/cydia/ |
| 3   | **Darwin CC Tools**, `otool`, `nm`, `strings` | https://apt.binger.com |
| 4   | **AppSync Unified**           | https://cydia.akemi.ai/ <br> http://apt.saurik.com/cydia/ |
| 5   | **Apple File Conduit "2" / afc2add** | https://cydia.akemi.ai/ <br> http://apt.saurik.com/cydia/ <br> http://apt.thebigboss.org/repofiles/cydia/ |
| 6   | **Frida**                     | https://build.frida.re/ |
| 7   | **LLDB**                      | https://repo.procurs.us/ <br> https://apt.procurs.us/ |
| 8   | **Cycript**                   | https://apt.binger.com/ |
| 9   | **PowerSelector**            | https://cydia.ichitaso.com/ <br> https://ichitaso.com/apt/ |
| 10  | **SSL Bypass**                | https://github.com/evilpenguin/SSLBypass/blob/main/packages/com.evilpenguin.sslbypass_1.0-5%2Bdebug_iphoneos-arm.deb |
| 11  | **SSL Kill Switch 2**         | https://julioverne.github.io/ |
| 12  | **SSL Kill Switch 3**         | https://repo.misty.moe/apt <br> https://github.com/NyaMisty/ssl-kill-switch3/releases/tag/v1.5.1 |
| 13  | **Location Faker**            | https://ios.tweaks.fun/ |
| 14  | **CCPower** *(iOS 15+)*       | http://apt.thebigboss.org/repofiles/cydia/ |
| 15  | **NewTerm 2 / 3 / 3 beta**    | https://repo.chariz.com/ |
| 16  | **CrackerXL+**                | http://cydia.iphonecake.com |
| 17  | **TrollDecrypt**              | https://github.com/donato-fiore/TrollDecrypt/releases |
| 18  | **Flex 3**                    | https://getdelta.co |



---

## 🛡️ Jailbreak Detection Bypass Tools

<details>
<summary>Click to expand</summary>

| No. | Tool                 | Repository / Notes |
|-----|----------------------|--------------------|
| 1   | **Shadow**           | https://ios.jjolano.me/ |
| 2   | **HideJB**           | http://apt.thebigboss.org/repofiles/cydia/ |
| 3   | **AJB**              | http://apt.thebigboss.org/repofiles/cydia/ |
| 4   | **Hestia**           | https://havoc.app/ |
| 5   | **Liberty Lite**     | https://ryleyangus.com/repo/ |
| 6   | **A-Bypass**         | https://repo.co.kr/ |
| 7   | **Kern Bypass**      | https://repo.misty.moe/apt/ <br> https://cydia.ichitaso.com/ |
| 8   | **unsub**            | https://repo.hackyouriphone.org/ |
| 9   | **VnodeBypass**      | https://cydia.ichitaso.com/ <br> *Disable to use Cydia* |
| 10  | **JailProtect**      | https://julioverne.github.io/ |
| 11  | **Choicy**           | http://apt.thebigboss.org/repofiles/cydia/ |
| 12  | **FlyJB X**          | https://mrepo.org/ <br> *Enable Dobby in Tweaks app* |
| 13  | **iHide**            | https://repo.kc57.com/ |
| 14  | **bypassJB** *(SniperBypassJB)* | http://apt.thebigboss.org/repofiles/cydia/ |

</details>

---

### 💡 Manual Installation Tip

If a tool requires a `.deb` file to be manually installed, use the following:

```sh
dpkg -i yourpackage.deb
uicache -a
