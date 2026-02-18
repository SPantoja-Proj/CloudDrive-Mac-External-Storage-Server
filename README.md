# CloudDrive — Mac External Storage Server

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![macOS](https://img.shields.io/badge/macOS-10.15%2B-blue)](https://www.apple.com/macos)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-2026--02--18-brightgreen)]

> A lightweight guide for turning a macOS device into a simple file-sharing "cloud-style" server using an external hard drive as the primary storage location.

This repository contains step-by-step instructions, configuration notes, and best practices for securely sharing files over a local network or remotely using macOS built-in tools.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Quick Start](#quick-start)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Remote Access Options](#remote-access-options)
- [Security Best Practices](#security-best-practices)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

---

## 📌 Overview

This project explains how to:

- ✅ Use an **external hard drive** as shared storage
- ✅ Configure **macOS file sharing** (SMB protocol)
- ✅ Allow access from other devices (Mac, Windows, Linux, mobile)
- ✅ Optionally enable **remote access** using iCloud, VPN, or port forwarding
- ✅ Maintain security and reliability

**Ideal for:** Home labs, small teams, or personal cloud storage without relying on third-party services.

---

## 📂 Requirements

| Requirement | Details |
|---|---|
| **macOS Device** | Intel or Apple Silicon (10.15+) |
| **External Drive** | HDD or SSD with 1TB+ recommended |
| **File System** | APFS, HFS+, or exFAT |
| **Network** | Local Wi-Fi or Ethernet |
| **User Privileges** | Admin account required |

---

## 🚀 Quick Start

1. **Connect your external drive** to your Mac
2. **Enable File Sharing** in System Settings → Sharing
3. **Add folders** from your external drive to shared folders
4. **Access from network** using SMB protocol
5. **(Optional)** Set up VPN for remote access

See [Installation & Setup](#installation--setup) for detailed steps.

---

## 🔧 Installation & Setup

### Step 1 — Connect & Prepare the External Drive

1. Plug in your external hard drive
2. Open **Disk Utility** if you need to reformat it
3. Rename the drive (optional but recommended)
4. Create folders you want to share (e.g., `/SharedFiles`, `/TeamDocs`)

### Step 2 — Enable File Sharing on macOS

1. Open **System Settings**
2. Navigate to **General → Sharing**
3. Enable **File Sharing**
4. Click the **ⓘ** icon next to File Sharing
5. Under **Shared Folders**, click **+**
6. Select the folder(s) on your external drive
7. Under **Users**, set permissions:
   - **Read & Write** for yourself
   - **Read Only** or **No Access** for others as needed

**Note:** File Sharing uses the SMB protocol for compatibility across platforms.

### Step 3 — Find Your Mac's IP Address

Go to: **System Settings → Wi-Fi → Details → IP Address**

---

## 🌐 Usage

### Accessing from Another Mac

1. Open **Finder**
2. Press `Command + K`
3. Enter: `smb://<your-mac-ip-address>`
4. Log in using your macOS username and password

### Accessing from Windows

1. Open File Explorer
2. Enter in the address bar: `\\<your-mac-ip-address>`
3. Log in with your macOS credentials
4. You may need to specify username as: `macusername`

### Accessing from Linux

1. Install `smbclient` or use a file manager with SMB support
2. Connect to: `smb://<your-mac-ip-address>`
3. Provide your macOS credentials

---

## 🌍 Remote Access Options

If you need to access your external drive from outside your home network:

### Option A — iCloud Drive + Folder Sync
- **Pros:** Easy setup, seamless integration
- **Cons:** Uses cloud storage space, may have bandwidth limits
- **Best for:** Small files and documents

### Option B — VPN (⭐ Recommended for Security)
- **Pros:** Secure, maintains local network speed, full access
- **Cons:** Requires VPN setup on router
- **Best for:** Business use, sensitive data

### Option C — Port Forwarding
- **Pros:** Simple configuration
- **Cons:** Security risk if not properly configured, requires strong passwords
- **Use case:** Emergency access only; not recommended for production

---

## 🔐 Security Best Practices

✅ **Do's:**
- Use strong, unique macOS account passwords
- Keep macOS and firmware updated
- Use VPN for any remote access
- Enable two-factor authentication on your Apple ID
- Regularly back up your external drive
- Monitor connected users

❌ **Don'ts:**
- Disable Guest access
- Avoid exposing SMB directly to the internet
- Don't use simple or default passwords
- Don't store sensitive credentials on the shared drive
- Don't leave the Mac unattended with file sharing enabled

---

## 🛠 Troubleshooting

| Issue | Solution |
|-------|----------|
| Cannot connect from Windows | Ensure SMB is enabled in Sharing settings; try `smb://username:password@ip-address` |
| External drive not visible | Check permissions in Shared Folders; verify drive is mounted |
| Slow transfer speeds | Use Ethernet instead of Wi-Fi; check for interference |
| Permission denied | Re-add user permissions in File Sharing panel; restart the service |
| Connection timeout | Verify Mac's firewall isn't blocking SMB port 445 |
| Drive disconnects frequently | Check USB cable; try different USB port; verify drive power supply |

**Still stuck?** See [Common Issues](#troubleshooting) or check Apple's [File Sharing support documentation](https://support.apple.com/en-us/HT204445).

---

## 📚 Additional Resources

- [Apple File Sharing Guide](https://support.apple.com/en-us/HT204445)
- [SMB Protocol Documentation](https://en.wikipedia.org/wiki/Server_Message_Block)
- [macOS Security Best Practices](https://support.apple.com/en-us/HT204344)

---

## 🤝 Contributing

We welcome contributions! To contribute:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/improvement`)
3. **Make** your changes with clear commit messages
4. **Test** your changes thoroughly
5. **Submit** a pull request with a detailed description

### Guidelines
- Keep explanations clear and beginner-friendly
- Include screenshots or diagrams where helpful
- Test on both Intel and Apple Silicon Macs
- Update the Table of Contents if adding sections

---

## 📝 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

**Attribution:** If you use this guide, a link back to this repository is appreciated!

---

## ⚠️ Disclaimer

This guide is provided "as-is" for educational and personal use. While we've made efforts to ensure accuracy, we are not responsible for:
- Data loss or corruption
- Security breaches (if not following best practices)
- System issues or incompatibilities

Always maintain regular backups of important data.