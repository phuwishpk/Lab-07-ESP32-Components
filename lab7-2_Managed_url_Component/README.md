# Lab 7-2: Managed Component from GitHub URL Demo

## คำอธิบาย
การทดลองนี้แสดงการใช้งาน managed component จาก GitHub Repository
ใช้ `Sensors` component จาก https://github.com/APPLICATIONS-OF-MICROCONTROLLERS/Lab7_Components

## ผลลัพธ์ที่คาดหวัง
- แสดงข้อความการเริ่มต้น sensor จาก GitHub component
- แสดงข้อมูล temperature และ humidity ทุก 4 วินาที
- แสดงสถานะการทำงานของ sensor
- แสดงแหล่งที่มาของ component (GitHub Repository)

## ความแตกต่างจาก Lab 7-1
- Lab 7-1: ใช้ local component (ในเครื่อง)
- Lab 7-2: ใช้ managed component จาก GitHub URL

## การใช้งาน
1. เข้าไปในโฟลเดอร์ lab7-2_Managed_url_Component
2. รันคำสั่ง `idf.py build` (จะดาวน์โหลด component จาก GitHub อัตโนมัติ)
3. ทดสอบด้วย QEMU

<
--- esp-idf-monitor 1.6.2 on socket://localhost:5555 115200
--- Quit: Ctrl+] | Menu: Ctrl+T | Help: Ctrl+T followed by Ctrl+H
I (11309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (11309) SENSOR: 🌡️  Temperature: 34.0°C
I (11309) SENSOR: 💧 Humidity: 86.8%
I (11309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (11309) SENSOR: 📈 All sensors operating normally
I (11309) LAB7-1: ----------------------------
I (14309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (14309) SENSOR: 🌡️  Temperature: 26.6°C
I (14309) SENSOR: 💧 Humidity: 63.8%
I (14309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (14309) SENSOR: 📈 All sensors operating normally
I (14309) LAB7-1: ----------------------------
I (17309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (17309) SENSOR: 🌡️  Temper ature: 35.4°C
I (17309) SENSOR: 💧 Humidity: 62.8%
I (17309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (17309) SENSOR: 📈 All sensors operating normally
I (17309) LAB7-1: ----------------------------
I (20309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (20309) SENSOR: 🌡️  Temperature: 26.7°C
I (20309) SENSOR: 💧 Humidity: 91.2%
I (20309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (20309) SENSOR: 📈 All sensors operating normally
I (20309) LAB7-1: ----------------------------
I (23309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (23309) SENSOR: 🌡️  Temperature: 25.6°C
I (23309) SENSOR: 💧 Humidity: 85.8%
I (23309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (23309) SENSOR: 📈 All sensors operating normally
I (23309) LAB7-1: ----------------------------
I (26309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (26309) SENSOR: 🌡️  Temperature: 26.7°C
I (26309) SENSOR: 💧 Humidity: 63.5%
I (26309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (26309) SENSOR: 📈 All sensors operating normally
I (26309) LAB7-1: ----------------------------
I (29309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (29309) SENSOR: 🌡️  Temperature: 25.8°C
I (29309) SENSOR: 💧 Humidity: 61.9%
I (29309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (29309) SENSOR: 📈 All sensors operating normally
I (29309) LAB7-1: ----------------------------
I (32309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (32309) SENSOR: 🌡️  Temperature: 27.3°C
I (32309) SENSOR: 💧 Humidity: 77.7%
I (32309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (32309) SENSOR: 📈 All sensors operating normally
I (32309) LAB7-1: ----------------------------
I (35309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (35309) SENSOR: 🌡️  Temperature: 33.7°C
I (35309) SENSOR: 💧 Humidity: 68.4%
I (35309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (35309) SENSOR: 📈 All sensors operating normally
I (35309) LAB7-1: ----------------------------
I (38309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (38309) SENSOR: 🌡️  Temperature: 26.5°C
I (38309) SENSOR: 💧 Humidity: 68.9%
I (38309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (38309) SENSOR: 📈 All sensors operating normally
I (38309) LAB7-1: ----------------------------
I (41309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (41309) SENSOR: 🌡️  Temperatu re: 29.8°C
I (41309) SENSOR: 💧 Humidity: 86.9%
I (41309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (41309) SENSOR: 📈 All sensors operating normally
I (41309) LAB7-1: ----------------------------
I (44309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (44309) SENSOR: 🌡️  Temperature: 32.4°C
I (44309) SENSOR: 💧 Humidity: 75.7%
I (44309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (44309) SENSOR: 📈 All sensors operating normally
I (44309) LAB7-1: ----------------------------
I (47309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (47309) SENSOR: 🌡️  Temperature: 30.5°C
I (47309) SENSOR: 💧 Humidity: 91.5%
I (47309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (47309) SENSOR: 📈 All sensors operating normally
I (47309) LAB7-1: ----------------------------
I (50309) SENSOR: 📊 Reading sensor data from file: /project/components/Sensors/sensor.c, line: 18
I (50309) SENSOR: 🌡️  Temperature: 27. 3°C
I (50309) SENSOR: 💧 Humidity: 60.0%
I (50309) SENSOR: ✅ Sensor status check from file: /project/components/Sensors/sensor.c, line: 30
I (50309) SENSOR: 📈 All sensors operating normally
I (50309) LAB7-1: ----------------------------
>