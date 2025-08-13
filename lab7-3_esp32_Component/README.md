# Lab 7-3: Custom ESP32 Components (Sensor + Display)

## คำอธิบาย
การทดลองนี้แสดงการสร้าง component ใหม่ด้วยคำสั่ง `idf.py create-component`
สร้าง 2 components:
1. **Sensor Component** - อ่านค่า temperature, humidity และคำนวณ heat index
2. **Display Component** - แสดงผลข้อมูลในรูปแบบตาราง

## โครงสร้างโฟลเดอร์หลังใช้ create-component
lab7-3_esp32_Component/
├── CMakeLists.txt
├── components/
│   ├── sensor/
│   │   ├── CMakeLists.txt
│   │   ├── include/
│   │   │   └── sensor.h
│   │   └── sensor.c
│   └── display/
│       ├── CMakeLists.txt
│       ├── include/
│       │   └── display.h
│       └── display.c
├── main/
│   ├── CMakeLists.txt
│   └── lab7-3.c
├── build/
└── README.md
<
rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (1056) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (1058) boot: compile time Aug 13 2025 06:15:56
I (1059) boot: Multicore bootloader
I (1529) boot: chip revision: v3.0
I (1533) boot.esp32: SPI Speed      : 40MHz
I (1534) boot.esp32: SPI Mode       : DIO
I (1534) boot.esp32: SPI Flash Size : 2MB
I (1602) boot: Enabling RNG early entropy source...
I (1672) boot: Partition Table:
I (1672) boot: ## Label            Usage          Type ST Offset   Length
I (1673) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (1674) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (1674) boot:  2 factory          factory app      00 00 00010000 00100000
I (1738) boot: End of partition table
I (2178) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=0a0b4h ( 41140) map
I (2363) esp_image: segment 1: paddr=0001a0dc vaddr=3ff80000 size=00024h (    36) load
I (2572) esp_image: segment 2: paddr=0001a108 vaddr=3ffb0000 size=02600h (  9728) load
I (2772) esp_image: segment 3: paddr=0001c710 vaddr=40080000 size=03908h ( 14600) load
I (2951) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=10290h ( 66192) map
I (3144) esp_image: segment 5: paddr=000302b8 vaddr=40083908 size=096f8h ( 38648) load
I (3839) boot: Loaded app from partition at offset 0x10000
I (3840) boot: Disabling RNG early entropy source...
I (3909) cpu_start: Multicore app
I (7334) cpu_start: Pro cpu start user code
I (7335) cpu_start: cpu freq: 160000000 Hz
I (7336) app_init: Application information:
I (7336) app_init: Project name:     lab7-3
I (7336) app_init: App version:      e61aae9-dirty
I (7337) app_init: Compile time:     Aug 13 2025 06:15:19
I (7337) app_init: ELF file SHA256:  53d598b50...
I (7338) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (7339) efuse_init: Min chip rev:     v0.0
I (7339) efuse_init: Max chip rev:     v3.99
I (7340) efuse_init: Chip rev:         v3.0
I (7341) heap_init: Initializing. RAM available for dynamic allocation:
I (7344) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (7347) heap_init: At 3FFB2EC8 len 0002D138 (180 KiB): DRAM
I (7347) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (7348) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (7349) heap_init: At 4008D000 len 00013000 (76 KiB): IRAM
I (7421) spi_flash: detected chip: winbond
I (7427) spi_flash: flash io: dio
I (7450) main_task: Started on CPU0
I (7460) main_task: Calling app_main()
I (7460) LAB7-3: � Lab 7-3: Custom Components Demo (sensor + display) Started
I (7470) LAB7-3: 📦 Using components created with idf.py create-component
I (7470) ENHANCED_SENSOR: 🔧 Enhanced Sensor Component initialized
I (7470) ENHANCED_SENSOR: 📍 File: ./components/sensor/sensor.c, Line: 14
I (7470) ENHANCED_SENSOR: ✅ GPIO LED configured on pin 2
I (7470) DISPLAY: 🖥️  Display Component initialized
I (7470) DISPLAY: 📍 File: ./components/display/display.c, Line: 11
I (7470) DISPLAY: ✅ Virtual display ready for operation
I (7470) LAB7-3: 📋 Reading #1
I (7480) DISPLAY: 🧹 Display cleared
I (7480) DISPLAY:
I (7480) ENHANCED_SENSOR: 🌡️  Temperature: 38.60°C
I (7490) ENHANCED_SENSOR: 💧 Humidity: 60.50%
I (7490) LAB7-3: 🔥 Heat Index: 68.85
I (7490) DISPLAY: ┌─────────────────────────────────┐
I (7490) DISPLAY: │        SENSOR DATA DISPLAY      │
I (7490) DISPLAY: ├─────────────────────────────────┤
I (7490) DISPLAY: │ 🌡️  Temp erature:  38.60°C      │
I (7490) DISPLAY: │ 💧 Humidity:     60.50%       │
I (7500) DISPLAY: │ 🔥 Heat Index:   68.85        │
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) DISPLAY: ┌─────────────────────────────────┐
I (7500) DISPLAY: │         SYSTEM STATUS           │
I (7500) DISPLAY: ├─────────────────────────────────┤
I (7500) DISPLAY: │ Status: ✅ Comfortable         │
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) LAB7-3: ==========================================
I (13500) LAB7-3: 📋 Reading #2
I (13500) DISPLAY: 🧹 Display cleared
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) LAB7-3: ==========================================
I (13500) LAB7-3: 📋 Reading #2
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) LAB7-3: ==========================================
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) LAB7-3: ==========================================
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) DISPLAY: └─────────────────────────────────┘
I (7500) LAB7-3: ==========================================
I (13500) LAB7-3: 📋 Reading #2
I (13500) DISPLAY: 🧹 Display cleared
I (13500) DISPLAY:
I (13500) ENHANCED_SENSOR: 🌡️  Temperature: 21.00°C
I (13500) ENHANCED_SENSOR: 💧 Humidity: 45.00%
I (13500) LAB7-3: 🔥 Heat Index: 43.50
I (13500) DISPLAY: ┌─────────────────────────────────┐
I (13500) DISPLAY: │        SENSOR DATA DISPLAY      │
I (13500) DISPLAY: ├─────────────────────────────────┤
I (13500) DISPLAY: │ 🌡️  Temperature:  21.00°C      │
I (13500) DISPLAY: │ 💧 Humidity:     45.00%       │
I (13500) DISPLAY: │ 🔥 Heat Index:   43.50        │
I (13500) DISPLAY: └─────────────────────────────────┘
I (13500) DISPLAY: ┌─────────────────────────────────┐
I (13500) DISPLAY: │         SYSTEM STATUS           │
I (13510) DISPLAY: ├─────────────────────────────────┤
I (13510) DISPLAY: │ Status: ✅ Comfortable         │
I (13510) DISPLAY: └─────────────────────────────────┘
I (13510) LAB7-3: ==========================================
I (19510) LAB7-3: 📋 Reading #3
I (19510) DISPLAY: 🧹 Display cleared
I (19510) DISPLAY:
I (19510) ENHANCED_SENSOR: 🌡️  Temperature: 28.80°C
I (19510) ENHANCED_SENSOR: 💧 Humidity: 74.30%
I (19510) LAB7-3: 🔥 Heat Index: 65.95
I (19510) DISPLAY: ┌─────────────────────────────────┐
I (19510) DISPLAY: │        SENSOR DATA DISPLAY      │
I (19510) DISPLAY: ├─────────────────────────────────┤
I (19510) DISPLAY: │ 🌡️  Temperature:  28.80°C      │
I (19510) DISPLAY: │ 💧 Humidity:     74.30%       │
I (19510) DISPLAY: │ 🔥 Heat Index:   65.95        │
I (19510) DISPLAY: └─────────────────────────────────┘
I (19510) DISPLAY: ┌─────────────────────────────────┐
I (19520) DISPLAY: │         SYSTEM STATUS           │
I (19520) DISPLAY: ├─────────────────────────────────┤
I (19520) DISPLAY: │ Status: ✅ Comfortable         │
I (19520) DISPLAY: └─────────────────────────────────┘
I (19520) LAB7-3: ==========================================
I (25520) LAB7-3: 📋 Reading #4
I (25520) DISPLAY: 🧹 Display cleared
I (25520) DISPLAY:
I (25520) ENHANCED_SENSOR: 🌡️  Temperature: 32.50°C
I (25520) ENHANCED_SENSOR: 💧 Humidity: 64.00%
I (25520) LAB7-3: 🔥 Heat Index: 64.50
I (25520) DISPLAY: ┌─────────────────────────────────┐
I (25530) DISPLAY: │        SENSOR DATA DISPLAY      │
I (25540) DISPLAY: ├─────────────────────────────────┤
I (25540) DISPLAY: │ 🌡️  Temperature:  32.50°C      │
I (25540) DISPLAY: │ 💧 Humidity:     64.00%       │
I (25540) DISPLAY: │ 🔥 Heat Index:   64.50        │
I (25540) DISPLAY: └─────────────────────────────────┘
I (25540) DISPLAY: ┌─────────────────────────────────┐
I (25550) DISPLAY: │         SYSTEM STATUS           │
I (25560) DISPLAY: ├─────────────────────────────────┤
I (25560) DISPLAY: │ Status: ✅ Comfortable         │
I (25560) DISPLAY: └─────────────────────────────────┘
I (25560) LAB7-3: ==========================================
>