Aqui vai uma versão mais polida e visual, mantendo tudo em inglês e com um estilo mais moderno (com emojis e boa formatação):

---

# 🔵 Bluetooth Toolkit (BlueKill)

## 📖 Overview

**BlueKill** is an **experimental Bluetooth toolkit** designed for **scanning, simulating, and experimenting** with Bluetooth devices (both BLE and Classic).
Built in **Python**, it leverages the **Linux BlueZ stack** and **D-Bus** to enable advanced operations like BLE advertising and device interaction.

> ⚠ **Disclaimer**
> This tool is intended **for educational and research purposes only**.
> **Do NOT** use it for malicious activities or to harm other people's devices.
> **You are solely responsible** for any actions performed with this software.

---

## ⚡ Requirements & Setup

### 🖥 Operating System

* **Linux:** Debian, Ubuntu, Arch, Fedora, etc.
* **Android (Termux):** Root access **required** for Bluetooth features

### 📡 Bluetooth Hardware

* Adapter with **BLE (Bluetooth 4.0+)** support
* **BlueZ** service running (`bluetoothd`)

### 🐍 Python

* Python **3.8+**
* **pip** package manager

### 📦 Python Dependencies

* [`bluepy`](https://pypi.org/project/bluepy/) → BLE scanning
* [`pydbus`](https://pypi.org/project/pydbus/) → D-Bus control & BLE advertising
* [`PyGObject`](https://pygobject.readthedocs.io/en/latest/) → Required by pydbus

### 🔑 Permissions

* **Root access** *or* add your user to the `bluetooth` group

---

## 🛠 Step-by-Step Installation

### Debian/Ubuntu
```bash
sudo apt update
sudo apt install python3 python3-pip python3-gi bluetooth bluez bluez-tools
pip3 install bluepy pydbus
```

### Arch Linux
```bash
sudo pacman -Syu python python-pip python-gobject bluez bluez-utils
pip install bluepy pydbus
```

### Fedora
```bash
sudo dnf install python3 python3-pip python3-gobject bluez bluez-tools
pip3 install bluepy pydbus
```

### Termux (Android)
```bash
pkg update
pkg install python dbus bluez
pip install bluepy pydbus
```

⚠️ Disclaimer
This tool is designed for educational and research purposes only.
Do not use it for malicious activities or to harm others’ devices.
You are solely responsible for how you use this software.

✅ Quick Test
Run the program:

```bash
sudo python3 main.py
```

Make sure your Bluetooth adapter is enabled:            
```bash
hciconfig hci0 up
```

