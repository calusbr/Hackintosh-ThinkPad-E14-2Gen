![GitHub followers](https://img.shields.io/github/followers/calusbr?style=social) ![GitHub User's stars](https://img.shields.io/github/stars/calusbr?style=social) ![Visitor](https://visitor-badge.laobi.icu/badge?page_id=calusbr.repoName)  <img src="https://shields.io/badge/MacOS--9cf?logo=Apple&style=social">
# <img src="https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=apple&logoColor=white"> Hackintosh ThinkPad E14 2Gen

<p align="center">
<img src="https://github.com/calusbr/Hackintosh-ThinkPad-E14-2Gen/blob/main/screenshots/hackintosh_thinkpad_e14_2gen_1.png?raw=true" alt="Size Limit CLI" width="1280">
<img src="https://img.shields.io/badge/Apple-MacBook_PRO_16,3_2020-999999?style=for-the-badge&logo=apple&logoColor=white">
</p>

# ⚙️ **Hardware**

<img src="https://github.com/educabox/educabox/blob/main/imagens/00%20-%20PROCESSADORES/S905X3.png?raw=true" align="right" alt="" width="120" height="120">

|Summary | Details|
---------|:--
S.O | MacOs Sequoia 15.1
SMBios | MacBook Pro 16,3
Laptop | Lenovo ThinkPad E14 Gen2 
CPU | AMD Ryzen 5 4300 2.7 GHz
GPU | AMD Radeon Graphics RX Renoir C4 1GB
Memória | 8GB DDR4 3200 MHz
Wifi/Bluetooth | Intel Wi-Fi 6 AX200
Ethernet | Realtek RTL8111
Audio | Realtek ALC257
SSD| KBG40ZNT256G TOSHIBA 256GB
USB | 3.1 AppleUSBXHCIPCI

# 🧰 **ACPI**

<a href="https://github.com/educabox/educabox/blob/main/instalacao/faq.md"><img src="https://github.com/calusbr/Hackintosh-ThinkPad-E14-2Gen/blob/main/icons/download_ssdt.png?raw=true&image_size=auto"/>

Order | Summary | Details
:--:|------| ----
1 | SSDT-EC.aml | OS-aware fake EC (laptop and desktop variants)
2 | SSDT-HPET.aml | Patches out IRQ conflicts
3 | SSDT-PLUG-ALT.aml | Sets plugin-type = 1 on CPU0/PR00
4 | SSDT-PMC.aml | Adds missing PMCR device for native 300-series NVRAM
5 | SSDT-PNLF.aml | Sets up a PNLF device for laptop backlight control
6 | SSDT-USB-Reset.aml | Returns a zero status for detected root hubs to allow hardware querying
7 | SSDT-USBX.aml | Provides generic USB power properties
8 | SSDT-XOSI.aml | OSI rename and patch to return true for a range of Windows versions - also checks for OSID
9 | SSDT-GPRW.aml | macOS will instant wake if either USB or power states change while sleeping

All necessary SSDTs are covered in this section. If necessary, follow the tutorial again to create your own SSDTs: [Link](https://dortania.github.io/Getting-Started-With-ACPI/Manual/dump.html) 

# 💾 **Kexts**

Order |Summary | Version| Details
:---:|---------|:--:| -
1 | Lilu | [1.6.9](https://github.com/acidanthera/Lilu)
2 | AppleALC | [1.9.2](https://chefkissinc.github.io/newsroom/applealc-sequoia/) | ✅ Fix Update ChefKiss  boot-args alcid=11
3 | VirtualSMC | [1.3.4](https://github.com/acidanthera/VirtualSMC)
4 | NootedRed | [1.0.0](https://chefkissinc.github.io/applehax/nootedred/)
5 | AMDRyzenCPUPowerManagement | [0.7.2](https://github.com/trulyspinach/SMCAMDProcessor)
6 | NVMeFix | [1.1.1](https://github.com/acidanthera/NVMeFix)
7 | ECEnabler | [1.0.5](https://github.com/1Revenger1/ECEnabler)
8 | AppleMCEReporterDisabler | [1.2.0](https://github.com/acidanthera/bugtracker/files/3703498/AppleMCEReporterDisabler.kext.zip)
9 | RestrictEvents | [1.1.5](https://github.com/acidanthera/RestrictEvents)
10 | FeatureUnlock | [1.1.7](https://github.com/acidanthera/FeatureUnlock)
11 | ForgedInvariant | [1.0.0](https://github.com/ChefKissInc/ForgedInvariant)
12 | GenericUSBXHCl | [1.3.0b2](https://github.com/RehabMan/OS-X-Generic-USB3)
13 | USBInjectAll | [0.7.1](https://github.com/RehabMan/OS-X-USB-Inject-All)
14 | BrcmFirmwareData | [2.6.9](https://github.com/acidanthera/BrcmPatchRAM) | 
15 | BrcmPatchRAM3 | [2.6.9](https://github.com/acidanthera/BrcmPatchRAM)
16 | IntelBluetoothFirmware | [2.4.0](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
17 | BlueToolFixup | [2.6.9](https://github.com/acidanthera/BrcmPatchRAM)
18 | IntelBTPatcher | [2.4.0](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
19 | itlwm | [2.3.0](https://github.com/OpenIntelWireless/itlwm) 
20 | RealtekRTL8111 | [2.4.2](https://github.com/Mieze/RTL8111_driver_for_OS_X)
21 | VoodooPS2Controller | [2.3.6](https://github.com/acidanthera/VoodooPS2) | ❌ Disable: VoodooInput 
22 | VoodooI2C | [2.9.1](https://github.com/VoodooI2C/VoodooI2C) | ✅ Enable Only: VoodooInput
23 | VoodooI2CHID | [1.0.0](https://github.com/VoodooI2C/VoodooI2CHID)
24 | VoodooI2CELAN | [1.0.0](https://github.com/VoodooI2C/VoodooI2CELAN)
25 | BrightnessKeys | [1.0.3](https://github.com/acidanthera/BrightnessKeys)
26 | SMCAMDProcessor | [1.0.0](https://github.com/trulyspinach/SMCAMDProcessor)
27 | SMCBatteryManager | [1.3.4](https://github.com/acidanthera/VirtualSMC)
28 | SMCLightSensor | [2.4.0](https://github.com/acidanthera/VirtualSMC)
29 | SMCProcessorAMD | [1.0.1](https://github.com/trulyspinach/SMCAMDProcessor)
30 | SMCRadeonSensors | [2.3.0](https://github.com/ChefKissInc/SMCRadeonSensors)
31 | HibernationFixup | [1.5.2](https://github.com/acidanthera/HibernationFixup)

# 💾 **Drives**

<a href="https://github.com/educabox/educabox/blob/main/instalacao/faq.md"><img src="https://github.com/calusbr/Hackintosh-ThinkPad-E14-2Gen/blob/main/icons/download_drivers.png?raw=true&image_size=auto"/>

Order | Summary | Details
:--:|------| ----
1 | HfsPlus.efi | Hierarchical File System Plus
2 | OpenRuntime.efi | Needed to boot macOS 11.0+
3 | OpenCanopy.efi | Optional graphical interface for OpenCore
4 | ResetNvramEntry.efi | Required to reset the system's NVRAM
5 | NvmExpressDxe.efi | Useful for users with limited free space within the DXE Driver Volume
6 | AudioDxe.efi | Enable audio startup
7 | UsbMouseDxe.efi | Provides generic USB properties
