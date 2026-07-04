# 🛡️ Boot.fxd — Boot Integrity Monitor

![Platform](https://img.shields.io/badge/platform-Linux-blue)
![Language](https://img.shields.io/badge/backend-C++17-orange)
![Frontend](https://img.shields.io/badge/frontend-Python%20(PyQt6)-green)
![Security](https://img.shields.io/badge/security-SHA256-red)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

Boot.fxd is a lightweight Boot Integrity Monitoring tool designed to detect unauthorized modifications to critical boot components such as EFI files, GRUB configuration, and the Master Boot Record (MBR).

It uses SHA-256 cryptographic hashing to create a trusted baseline and later verify system integrity.

The system combines a high-performance C++ backend with a modern Python GUI frontend.

---

# 🚀 Features

✔ Detects boot mode automatically (UEFI or BIOS)  
✔ Hashes EFI bootloader files  
✔ Hashes GRUB bootloader configuration  
✔ Hashes MBR (BIOS systems)  
✔ Baseline creation and integrity verification  
✔ Detects modified boot files  
✔ Detects added boot files  
✔ Detects deleted boot files  
✔ Fast and lightweight  
✔ Secure SHA-256 hashing using OpenSSL  
✔ Modern GUI with dark/light theme toggle  
✔ Professional cybersecurity dashboard  

---

# 🏗️ Architecture

```text
┌─────────────────────┐
│ Python GUI          │
│ (PyQt6)             │
└──────────┬──────────┘
           │ JSON
┌──────────▼──────────┐
│ boot.fxd            │
│ C++ Backend         │
└──────────┬──────────┘
           │
┌──────────▼──────────┐
│ Linux Boot System   │
│ /boot/efi           │
│ /boot/grub          │
│ /dev/sda (MBR)      │
└─────────────────────┘
```

---

# 📂 Project Structure

```text
boot.fxd-MVP1.0.0/
│
├── gui/
│   └── gui.py
│
├── include/
│   ├── baseline.h
│   ├── compare.h
│   ├── hashing.h
│   └── scanner.h
│
├── src/
│   ├── baseline.cpp
│   ├── compare.cpp
│   ├── hashing.cpp
│   ├── main.cpp
│   └── scanner.cpp
│
├── output/
│   ├── baseline.json
│   └── result.json
│
└── LICENSE
```

---

# ⚙️ Requirements

## System

Linux (Ubuntu recommended)

Root privileges required for MBR scanning

Tested on:

- Ubuntu 22.04
- Ubuntu 24.04
- Ubuntu VM (VMware / VirtualBox)

---

# 🖥️ GUI Usage

Run GUI from project root:

```bash
python3 gui/gui.py
```

GUI Features:

- Dark theme (default)
- Light theme toggle
- Interactive dashboard
- Integrity status display
- Modern cybersecurity interface

---

# 🔐 How It Works

Boot.fxd scans and hashes critical boot components.

### UEFI Systems

Scans:

```text
/boot/efi/EFI/
/boot/grub/
/boot/grub2/
```

### BIOS Systems

Scans:

```text
MBR (/dev/sda)
/boot/grub/
/boot/grub2/
```

Hashes are stored in `baseline.json` and compared during integrity checks.

---

# 🧠 Threat Detection

Boot.fxd detects:

- Bootkits
- Rootkits modifying bootloader
- GRUB tampering
- EFI modification
- MBR modification
- Persistent boot malware

---

# ⚡ Performance

Typical scan time: **< 1 second**

Memory usage: **Very low**

CPU usage: **Minimal**

Designed to be fast and lightweight.

---

# 🛠️ Tech Stack

### Backend

- C++17
- OpenSSL SHA-256
- Linux filesystem APIs

### Frontend

- Python 3
- PyQt6

---

# 🎯 Use Cases

- Boot integrity monitoring
- Rootkit detection
- Security research
- Cybersecurity education
- Malware analysis

---

# ⚠️ Security Notes

Requires root privileges to access:

- `/dev/sda`
- `/boot`
- `/boot/efi`

Baseline should be created on a trusted system.

---

# 📜 License

MIT License

See `LICENSE` file for details.

---

# 👨‍💻 Authors

**Boot.fxd — Boot Integrity Monitor**  
Cybersecurity Integrity Monitoring Project

### Team Members

- **Shubh Kashyap**
- **Prakhar Katare**

---

# ⭐ Future Improvements

- Real-time monitoring
- TPM integration
- Secure baseline signing
- Automatic alerts
- Kernel-level monitoring

---

# 🛡️ Summary

Boot.fxd provides a lightweight, fast, and secure way to verify boot integrity and detect boot-level persistence mechanisms.

Designed for cybersecurity, research, and integrity monitoring.
