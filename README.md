# GUARDX – Smart RFID Locker with App & Firebase Integration

A secure smart locker system that integrates RFID-based access control with a mobile application and Firebase, aimed at safeguarding personal valuables for hostel students and individual users.

## About

GUARDX is an IoT-based security system designed to provide users with controlled access to a physical locker box using an RFID card and a mobile app. Built around the ESP32 microcontroller, the system supports key functionalities such as card registration, arming/disarming the lock, intrusion detection (via IMU simulation), and real-time Firebase integration. It is ideal for hostel students, travelers, or anyone seeking compact and reliable personal security for storing valuable items.

## Features

- RFID-based authentication for locking and unlocking
- App-integrated arming/disarming and card registration
- Real-time Firebase Cloud Firestore sync for status and commands
- Motion simulation alert system (IMU) with tamper detection
- Unauthorized access attempts trigger buzzer and alert logs
- Master card reset and re-registration support
- Notification and activity log tracking through the app
- Modular, extensible, and user-friendly interface

## Requirements

- Microcontroller: ESP32 Dev Board
- RFID Module: MFRC522
- Cloud Backend: Firebase Firestore and Realtime Database
- App Stack: React Native / Expo (or web frontend using Firebase SDK)
- Libraries:
  - `MFRC522.h` for RFID
  - `WiFi.h` for ESP32 Wi-Fi control
  - `HTTPClient.h` and `ArduinoJson.h` for Firebase REST calls
- Power Supply: 5V USB / Battery Pack
- Development Tools:
  - Arduino IDE for firmware
  - Firebase Console
  - Expo CLI or VSCode for frontend

## System Architecture

```
         <img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/aceacef9-e8c7-4d43-8de2-80c7c23e8f84" />


<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/89c96c47-0d53-49b1-8641-77c6adefdd1e" />


<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/dc5e9fd6-ea74-491b-9ca8-aeb31701b34e" />

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/caf125e8-1bab-4d30-9519-5001f5ae70f3" />


         
```

## Output

#### Output1 - Card Registration

- User presses **Register Card** in app
- ESP32 enters `REGISTER_CARD` state
- Scans RFID → UID saved to Firebase
- Response:  "Master card registered"

#### Output2 - Arming and Alert

- User presses **Arm** in app
- ESP32 waits for master card
- After valid scan → Enters `ARMED` state
- If unauthorized card scanned → `ALERT` triggered
- App and buzzer notify the user

#### Output3 - Disarm Flow

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/0b5001c8-7511-4272-bfa6-95b2f2ce7414" />

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/d4a01717-5d13-47b0-ab4a-0dbd7edb7885" />


![WhatsApp Image 2025-12-27 at 8 18 25 AM](https://github.com/user-attachments/assets/1368ec42-4f9b-4f8b-ad92-c4acd1cfe3f5)

![WhatsApp Image 2025-12-27 at 8 17 49 AM](https://github.com/user-attachments/assets/db1431aa-ec96-4a47-a613-2fbcd111143d)

![WhatsApp Image 2025-12-27 at 8 17 48 AM](https://github.com/user-attachments/assets/aabce606-dba1-447c-b5e0-9080d3562273)



## Results and Impact

GUARDX provides a secure, affordable, and portable solution for protecting personal belongings. With seamless app integration and cloud control, it empowers users to monitor and control their physical security remotely. The RFID and Firebase combo allows tamper alerts, activity logs, and command history, ensuring transparency and safety in environments like hostels or shared accommodations.

This system serves as a blueprint for future smart-lock implementations in budget-constrained personal security domains.

## Articles published / References

1. M. Ayub, et al., “IoT-Based Smart Security System Using RFID and Mobile App,” *IJERT*, Vol. 10, Issue 3, 2023.  
2. P. K. Rout, “RFID Based Locker System Using NodeMCU,” *IEEE Xplore*, 2022.  
3. Firebase Docs: [https://firebase.google.com/docs](https://firebase.google.com/docs)  
4. MFRC522 Arduino Library: [https://github.com/miguelbalboa/rfid](https://github.com/miguelbalboa/rfid)
