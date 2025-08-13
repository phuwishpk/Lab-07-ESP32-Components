# Lab 7-1: Local Component Demo

## คำอธิบาย
การทดลองนี้แสดงการใช้งาน component ที่มีอยู่ในโฟลเดอร์ `components/Sensors/` ของ project


## สรุปคำสั่งที่ใช้ และผลลัพธ์ที่ได้

```Adding SPI flash device
ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (1068) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (1070) boot: compile time Aug 13 2025 04:21:31
I (1071) boot: Multicore bootloader
I (1507) boot: chip revision: v3.0
I (1512) boot.esp32: SPI Speed      : 40MHz
I (1514) boot.esp32: SPI Mode       : DIO
I (1514) boot.esp32: SPI Flash Size : 2MB
I (1590) boot: Enabling RNG early entropy source...
I (1659) boot: Partition Table:
I (1659) boot: ## Label            Usage          Type ST Offset   Length
I (1660) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (1661) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (1661) boot:  2 factory          factory app      00 00 00010000 00100000
I (1723) boot: End of partition table
I (2187) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=095c4h ( 38340) map
I (2428) esp_image: segment 1: paddr=000195ec vaddr=3ff80000 size=00024h (    36) load
I (2654) esp_image: segment 2: paddr=00019618 vaddr=3ffb0000 size=025e0h (  9696) load
I (2877) esp_image: segment 3: paddr=0001bc00 vaddr=40080000 size=04418h ( 17432) load
I (3114) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0f044h ( 61508) map
I (3338) esp_image: segment 5: paddr=0002f06c vaddr=40084418 size=08be8h ( 35816) load
I (4051) boot: Loaded app from partition at offset 0x10000
I (4052) boot: Disabling RNG early entropy source...
I (4127) cpu_start: Multicore app
I (7761) cpu_start: Pro cpu start user code
I (7763) cpu_start: cpu freq: 160000000 Hz
I (7764) app_init: Application information:
I (7764) app_init: Project name:     lab7-1
I (7765) app_init: App version:      4623c83-dirty
I (7765) app_init: Compile time:     Aug 13 2025 04:21:06
I (7765) app_init: ELF file SHA256:  ba0610cb2...
I (7766) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (7767) efuse_init: Min chip rev:     v0.0
I (7767) efuse_init: Max chip rev:     v3.99
I (7768) efuse_init: Chip rev:         v3.0
I (7770) heap_init: Initializing. RAM available for dynamic allocation:
I (7771) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (7773) heap_init: At 3FFB2EA8 len 0002D158 (180 KiB): DRAM
I (7773) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (7774) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (7774) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (7844) spi_flash: detected chip: winbond
I (7852) spi_flash: flash io: dio
I (7872) main_task: Started on CPU0
I (7882) main_task: Calling app_main()
I (7882) LAB7-1: 🚀 Lab 7-1: Local Component Demo Started
I (7882) SENSOR: 🔧 Sensor initialized from file: /project/components/Sensors/sensor.c, line: 12 
I (7892) SENSOR: 📡 Sensor module ready for operation
I (7892) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (7892) SENSOR: 🌡️  Temperature: 34.5°C
I (7902) SENSOR: 💧 Humidity: 99.3%
I (7902) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (7912) SENSOR: 📈 All sensors operating normally
I (7912) LAB7-1: ----------------------------
I (10912) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (10912) SENSOR: 🌡️  Temperature: 33.9°C
I (10912) SENSOR: 💧 Humidity: 80.4%
I (10912) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (10912) SENSOR: 📈 All sensors operating normally
I (10912) LAB7-1: ----------------------------
I (13912) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (13912) SENSOR: 🌡️  Temperature: 25.7°C
I (13912) SENSOR: 💧 Humidity: 79.8%
I (13912) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (13912) SENSOR: 📈 All sensors operating normally
I (13912) LAB7-1: ----------------------------
I (16912) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (16912) SENSOR: 🌡️  Temperature: 28.0°C
I (16912) SENSOR: 💧 Humidity: 62.1%
I (16912) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (16912) SENSOR: 📈 All sensors operating normally
I (16912) LAB7-1: ----------------------------
I (19922) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (19922) SENSOR: 🌡️  Temperature: 27.7°C
I (19922) SENSOR: 💧 Humidity: 69.3%
I (19922) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (19922) SENSOR: 📈 All sensors operating normally
I (19922) LAB7-1: ----------------------------
```
<img width="1102" height="810" alt="Screenshot 2025-08-13 114156" src="https://github.com/user-attachments/assets/4d8b30ae-948f-46ac-b156-7b2b84831a47" />
