


<h1 align="center">🔍 APK Vulnerability Scanner</h1>

<p align="center">
  A powerful Python-based static analyzer for Android APK/XAPK files. Detect secrets, insecure cloud configurations, manifest flaws, and more.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Google%20Colab-yellow?logo=googlecolab" />
  <img src="https://img.shields.io/github/license/justinlplummer/DemoRepo?color=brightgreen" />
  <img src="https://img.shields.io/badge/Status-Active-blue" />
</p>

---

## ✨ Features

- **🔑 Secret Detection**  
  Scans for hardcoded API keys, OAuth tokens, secrets, and refresh credentials.

- **☁️ Cloud Endpoint Analysis**  
  Identifies and probes cloud provider URLs (Firebase, AWS, GCP, Azure, etc.) for misconfigurations.

- **📱 AndroidManifest.xml Checks**  
  Detects:
  - `android:debuggable="true"` in production
  - `android:usesCleartextTraffic="true"` allowing HTTP
  - Exported components lacking `permission` protection

- **🗄️ Insecure Data Storage Detection**  
  Searches for sensitive values (e.g., passwords, tokens) in app-shared XML or JSON config files.

- **🔐 Weak Crypto Detection**  
  Flags:
  - MD5, SHA1, DES, RC4
  - ECB mode
  - Hardcoded crypto keys

- **📑 HTML Reporting**  
  Clean, categorized, severity-tagged reports with clear remediation guidance.

---

## 🛡️ Vulnerabilities Checked

| Category                        | Examples & Checks |
|--------------------------------|-------------------|
| **Secrets & Keys**             | Google API keys, AWS creds, OAuth secrets |
| **Firebase Exposure**          | Open DBs, buckets, Firestore, Cloud Functions |
| **Cloud Storage**              | Misconfigured AWS S3, GCP, Azure, B2, Wasabi, MinIO, Cloudflare R2 |
| **Exposed Platform Configs**   | `.env` files, Netlify/Vercel outputs, Supabase, Heroku, Kinvey |
| **Android Misconfigurations**  | Debuggable builds, HTTP traffic, exported components |
| **Sensitive Data in Files**    | `password=`, `token:`, etc. in XML/JSON |
| **Weak Crypto**                | MD5, SHA1, DES, RC4, ECB, hardcoded keys |

---

## 📊 Report Output

All results are saved to the `/reports/` directory. For each scanned APK:
/reports/
└── com.example.app_report/
├── report.html

### Viewing the Report

1. Open the **Files** sidebar in Google Colab.
2. Navigate to `/content/reports/`.
3. Download any `report.html` file.
4. Open in your web browser for a styled, detailed vulnerability summary.

Each report includes:

- APK metadata
- Cloud services found
- All detected secrets
- Vulnerabilities with severity tags
- Clear remediation advice per issue

---

## 🚀 Run It Now

<div align="center">
  <a href="https://github.com/justinlplummer/DemoRepo/blob/master/APKVulnerabilityChecker.ipynb" target="_blank">
    <img src="https://img.shields.io/badge/Open%20in-Google%20Colab-blue?logo=googlecolab&style=for-the-badge" />
  </a>
</div>

---

## ⚠️ Disclaimer

This scanner uses **static heuristics only**. It does not perform dynamic analysis or network-layer testing. It may produce false positives or miss certain vulnerabilities. Use it responsibly, and **only analyze APKs you have legal permission to scan.**

---


## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for full terms.

Written and organized by JP Software Solutions


