
# Comprehensive System Information Script

This repository contains a powerful command-line script created by **Kamrul Hossain** that gathers detailed hardware and software information from a Windows machine using various WMIC and system commands. This script is designed to extract everything from CPU voltage and cache size to installed hotfixes, USB device statuses, network packets, battery health, and more.

---

## Table of Contents

- [Getting Started](#getting-started)
- [System Information Extracted](#system-information-extracted)
  - [CPU Information](#cpu-information)
  - [Memory Information](#memory-information)
  - [Disk Information](#disk-information)
  - [BIOS Information](#bios-information)
  - [Graphics Information](#graphics-information)
  - [Battery Information](#battery-information)
  - [Network Information](#network-information)
  - [USB Information](#usb-information)
  - [Hotfix and Update Information](#hotfix-and-update-information)
  - [Process Information](#process-information)
  - [Miscellaneous Information](#miscellaneous-information)
- [Usage](#usage)
- [Redirecting Output](#redirecting-output)
- [Contact](#contact)
- [License](#license)

---

## Getting Started

### Prerequisites

- This script works on **Windows** operating systems.
- You need **Administrator privileges** to access all system details.
- The script utilizes `WMIC` (Windows Management Instrumentation Command-line).

### How to Use

1. **Open Command Prompt as Administrator**:
   - Press `Ctrl + R` on your keyboard. This will open the "Run" dialog box.
   - In the box, type **`cmd`** and press **Enter**.
   - This will open the **Command Prompt** window.
   - **Important**: To gather full system information, right-click on the Command Prompt and select **Run as Administrator**.

2. **Run the Script**:
   - Once the Command Prompt is open, simply copy the command provided below and paste it into the Command Prompt window.
   - Press **Enter** to run the script.

3. **View the Output**:
   - The script will start collecting information about your system.
   - The output will be displayed in the Command Prompt window.

---

## System Information Extracted

This script gathers detailed system information, organized by category:

### CPU Information

- CPU Name, Maximum Clock Speed, Architecture
- Number of Physical Cores and Logical Processors
- CPU Load Percentage, Voltage
- L2 and L3 Cache Sizes

### Memory Information

- Memory Capacity (RAM), Speed
- Manufacturer, Part Number

### Disk Information

- Disk Model, Size, Status, Number of Partitions
- Plug and Play Device ID, Volume Name
- Disk Serial Number

### BIOS Information

- BIOS Release Date, Serial Number, Version
- Current BIOS Voltage

### Graphics Information

- GPU Name, Adapter RAM
- Driver Version, Driver Date
- Video Processor Information

### Battery Information

- Battery Name, Charge Percentage
- Battery Status (Charging/Discharging), Voltage
- Design Capacity, Full Charge Capacity
- Expected Battery Life, Time to Full Charge

### Network Information

- Network Adapter Name, Speed
- MAC Address, Packets Sent/Received
- Network Adapter Status

### USB Information

- USB Device ID, Manufacturer, Status
- USB Hub Information

### Hotfix and Update Information

- Hotfix ID, Description, Installed On (Date)

### Process Information

- Process Name, Process ID
- Thread Count, Working Set Size (Memory Usage)

### Miscellaneous Information

- System Manufacturer, Model, and Type
- Last Boot Time, Boot Device
- Installed OS Details (Version, Serial Number, Install Date)
- Thermal State, Power State

---

## Usage

### Step-by-Step Instructions

1. **Press `Ctrl + R`** on your keyboard to open the **Run** dialog box.
2. Type **`cmd`** and press **Enter** to open the Command Prompt.
3. **Right-click** on the Command Prompt icon and select **"Run as Administrator"** for full access.
4. Copy the following command and paste it into the Command Prompt:

   ```bash
   systeminfo & wmic bios get releasedate,serialnumber,version & wmic cpu get name, maxclockspeed,architecture,numberofcores,numberoflogicalprocessors,loadpercentage, currentvoltage, l2cachesize, l3cachesize & wmic diskdrive get model, size, status, pnpdeviceid, partitions & wmic memorychip get capacity, manufacturer, speed, partnumber & wmic baseboard get manufacturer, product, version, serialnumber & wmic path win32_videocontroller get caption, adapterram, driverversion, driverdate, name, videoprocessor & wmic nic get name, macaddress, speed, manufacturer, packetsreceived, packetssent & wmic sounddev get caption, manufacturer & wmic path Win32_Battery get Name, EstimatedChargeRemaining, BatteryStatus, DesignCapacity, FullChargeCapacity, Voltage, ExpectedBatteryLife, TimeToFullCharge & wmic csproduct get identifyingnumber, uuid & wmic logicaldisk get description,filesystem,freespace,size,volumename & wmic path Win32_USBController get DeviceID,Name, Manufacturer, status & wmic os get caption,serialnumber,version,buildnumber,installdate, lastbootuptime, numberofprocesses & wmic computersystem get manufacturer, model, systemtype, systemfamily, totalphysicalmemory, domain, partofdomain, powersupplystate & wmic bootconfig get caption & wmic os get bootdevice, lastbootuptime, localdatetime, servicepackmajorversion & wmic computersystem get powerstate, status, thermalstate & wmic path win32_bios get biosversion, smbiosbiosversion, currentvoltage & wmic qfe get hotfixid, description, installedon & wmic path win32_temperatureprobe get currentreading & wmic path win32_process get processid, name, threadcount, workingsetsize & wmic path win32_usbhub get deviceid, status & wmic path win32_portconnector get connectorpinout, internalreference & wmic path win32_networkadapter get description, macaddress, speed, netconnectionid & wmic path win32_physicalmedia get serialnumber
   ```

5. Press **Enter** and allow the script to gather all system information.

---

## Redirecting Output

If you'd like to save the output to a file (for later use), follow these steps:

1. **Redirect Output to a Text File**:
   - To save the output to a text file, append the following to the command:
   
   ```bash
   scriptname.bat > systeminfo.txt
   ```

   - This will create a text file named `systeminfo.txt` in the same directory where the script is run, containing all the gathered system information.

2. **Open the Saved Output**:
   - Open the `systeminfo.txt` file to review the system information at any time.

---

## Contact

- **Kamrul Hossain**
  - **Facebook**: [elitekamrul](https://www.facebook.com/elitekamrul)

---

## License

This repository is licensed under the **MIT License**. See the `LICENSE` file for more details.

---

This script provides comprehensive information about your system, useful for debugging, performance analysis, and system management.
