# Security-Risks-of-Pre-Installed-Android-Apps

## Overview
This project explores the security risks associated with **pre-installed Android applications (bloatware)**. It focuses on analyzing pre-installed apps on an **Android emulator (Android x86)**, assessing their permissions, and identifying potential security threats using tools like:
- **ADB (Android Debug Bridge)**
- **MobSF (Mobile Security Framework)**
- **VirusTotal (Malware Detection)**

## Objectives
- Discover security vulnerabilities in pre-installed Android apps.
- Analyze permissions and behaviors of apps.
- Identify and remove unnecessary or malicious apps.
- Implement security best practices to mitigate risks.

## Tools Used
| Tool      | Purpose |
|-----------|---------|
| **ADB** | Extract and analyze app details, permissions |
| **MobSF** | Static and dynamic analysis of APK files |
| **VirusTotal** | Scan suspicious APK files for malware detection |
| **Android x86** | Virtual environment for testing & analysis |
| **Kali Linux** | For managing Android security assessments |


---

## **Analysis Process**
### Step 1️⃣: **Prepare Lab Environment**
1. Install **Android x86** as an emulator.
2. Set up **Kali Linux** for security assessments.
3. Connect Android x86 to Kali Linux using:
   ```bash
   adb connect <android-ip>:5555
   adb devices
   ```
### Step 2️⃣: Extract Installed Applications
1. Use ADB to list installed apps:
```bash
adb shell pm list packages
```
### Step 3️⃣: Analyze Suspicious Applications
1. Extract the APK from the Android emulator:
```bash
adb pull /data/app/com.suspiciousapp.apk ~/analysis/
```
2. Scan the extracted APK using MobSF:
```bash
mobsf -a ~/analysis/com.suspiciousapp.apk
```
3. Upload APK to VirusTotal for malware detection.
### Step 4️⃣: Uninstall Malicious Applications
1. If an app is found to be malicious, remove it using:
```bash
adb shell pm uninstall --user 0 com.metasploit.stage
```

## **Key Findings**
Some pre-installed apps request excessive permissions (Location, Camera, SMS).
Some applications use outdated libraries, making them vulnerable.
Certain apps were flagged as malicious by VirusTotal.
Persistence: Some apps re-enable themselves after system reboot.

## **Security Recommendations**

Review & Limit Permissions: Restrict unnecessary app permissions via Android settings.
Regular Updates: Keep software up to date to prevent vulnerabilities.
Uninstall Bloatware: Remove unnecessary pre-installed apps using ADB.
Use Security Tools: Leverage tools like MobSF, VirusTotal, and custom ROMs to enhance security.

## **📖 Full Report**
The detailed research report is available on Notion:

🔗 **[Security Risks of Pre-Installed Android Apps](https://www.notion.so/Security-Risks-of-Pre-Installed-Android-Apps-1ba7c5d196f480c18047e1528ed77791?pvs=4)**




