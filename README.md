Requirements
This project relies on Linux with full support for Bluetooth Low Energy (BLE) and Bluetooth Classic.
Below are the detailed requirements to ensure the tool works properly:

1. Operating System
Linux Distribution: Ubuntu 20.04+, Debian 11+, Fedora 35+, Arch Linux, or any modern Linux distribution with systemd support.

Kernel: Linux Kernel 5.0 or newer (for reliable BLE stack support).

DBus: System D-Bus must be available and running (usually enabled by default in modern Linux).

2. Hardware
A Bluetooth adapter with BLE (Bluetooth 4.0 or higher) support.

The adapter must support advertising mode and Low Energy scanning (commonly found in USB Bluetooth 4.0+ dongles or built-in adapters in laptops).

Make sure the adapter is enabled:

bash
Copiar
Editar
hciconfig hci0 up
3. Bluetooth Stack
BlueZ version 5.43 or newer (required for full BLE support and D-Bus interface).

Check your BlueZ version:

bash
Copiar
Editar
bluetoothctl -v
Ensure the Bluetooth daemon is running:

bash
Copiar
Editar
sudo systemctl status bluetooth
4. Python Environment
Python Version: Python 3.8 or newer.

Pip and venv (for isolated environment).

Required Python packages:

bluepy – for Bluetooth Low Energy scanning.

pydbus – for interacting with BlueZ via D-Bus and simulating BLE advertising.

PyGObject (python3-gi) – for GLib main loop support.

Install dependencies (Debian/Ubuntu example):

bash
Copiar
Editar
sudo apt update
sudo apt install python3 python3-pip python3-gi python3-venv bluetooth bluez bluez-tools
pip3 install bluepy pydbus
5. Permissions
Root privileges or proper udev rules are required to access Bluetooth Low Energy interfaces and advertising.

You can run the program directly with:

bash
Copiar
Editar
sudo python3 main.py
Alternatively, add the current user to the bluetooth group to avoid using sudo:

bash
Copiar
Editar
sudo usermod -aG bluetooth $USER
(logout/login required for changes to take effect)

6. D-Bus Requirements
The system D-Bus must be running because BLE advertisement simulation uses BlueZ D-Bus API:

bash
Copiar
Editar
systemctl status dbus
If using containers or minimal Linux environments, ensure D-Bus is available or the code will not work.

7. Optional Tools (For Testing)
bluetoothctl – for debugging and manual scanning.

hcitool and hciconfig – for low-level Bluetooth interface testing.

gdbus (from glib2.0-bin) – for checking D-Bus methods.

8. Known Limitations
Does not work on Windows or macOS because the tool directly interacts with the BlueZ stack.

Requires physical hardware (it will not work properly in most virtualized environments unless passthrough USB Bluetooth is configured).

BLE advertisement spoofing may not work if the adapter does not support peripheral role.

