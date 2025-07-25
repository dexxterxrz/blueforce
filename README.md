## Requirements

- **Operating System**  
  - Linux (Debian, Ubuntu, Arch, Fedora, etc.)  
  - Termux (Android, with root privileges for Bluetooth access)

- **Bluetooth**  
  - Bluetooth adapter with BLE support (Bluetooth 4.0 or higher)  
  - BlueZ installed and running (`bluetoothd` active)

- **Python**  
  - Python 3.8+  
  - Pip for package installation

- **Python Packages**  
  - [bluepy](https://pypi.org/project/bluepy/) – BLE scanning  
  - [pydbus](https://pypi.org/project/pydbus/) – Bluetooth advertising via D-Bus  
  - [PyGObject](https://pygobject.readthedocs.io/en/latest/) – Required by pydbus

- **Permissions**  
  - Root access (or user added to the `bluetooth` group)  
  - On Termux: `pkg install python dbus bluez`

