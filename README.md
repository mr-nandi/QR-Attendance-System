
# 📍 MarsAero Innovations – QR Attendance System

> **Verify your presence here. Zero hassle, always.**

A secure, real-time **QR-based attendance system** designed for modern offices by **MarsAero Innovations**.

---

## 🚀 Overview

This system uses **dynamic QR codes**, **Firebase**, and an **Android scanner app** to record employee attendance accurately while preventing fake or duplicate entries.

---

## 🧩 System Architecture

```

Office Web QR Display
↓
Firebase Realtime Database
↓
Android Attendance App
↓
Daily & Monthly Attendance Records

````

---

## 🖥️ Web Application (Office Side)

### Features
- Dynamic QR code generation
- Auto refresh every 30 seconds
- Countdown timer
- Firebase-backed secure tokens
- Clean & responsive UI

### QR Data Structure (Firebase)

```json
activeQR
 └── OFFICE_01
     ├── token: "OFFICE_01_1767262293228_o0lved"
     └── timestamp: 1767262264116
````

---

## 📱 Android Application (Employee Side)

### Main Modules

* Home / Dashboard
* QR Scanner
* Monthly Attendance Page

---

## 🔍 QR Scanner Features

* CameraX + ML Kit
* Firebase token validation
* Anti-fake QR protection
* Beep sound on scan
* Vibration on success
* Green background → Success
* Red background → Failure
* Auto close scanner after success

---

## 🧾 Attendance Logic

* **First scan** → Check-in
* **Second scan** → Check-out
* Prevents duplicate same-day entries
* Uses **server timestamp** (not device time)

### Attendance Data Structure

```json
attendance
 └── 9876543210
     └── 2026-01-01
         ├── checkIn: 1767262500000
         └── checkOut: 1767298500000
```

---

## 📊 Attendance Status Rules

| Condition            | Status    |
| -------------------- | --------- |
| No scan              | Absent    |
| Check-in only        | Present   |
| Check-in + Check-out | Completed |
| Sunday               | Holiday   |

---

## 📅 Monthly Attendance Page

### Displays

* Month & Year
* Employee ID
* Daily status list
* Day name (Mon, Tue, etc.)

### Summary Section

* Total Working Days
* Present Days
* Absent Days
* Holidays (Sundays)

### Navigation

* ⬅ Previous Month
* ➡ Next Month

---

## ⏰ Attendance Reminder Notification

### Purpose

Reminds employees to mark attendance **before 9:30 AM**

### Notification Message

> ⏰ Good Morning!
> Don’t forget to mark your attendance before **9:30 AM**

### Features

* Daily reminder
* Works after phone reboot
* Uses AlarmManager + BroadcastReceiver

---

## 🔔 Notification Components

* `AttendanceReminderReceiver`
* AlarmManager
* Notification Channel (Android 8+)
* BOOT_COMPLETED support

---

## 🛠️ Technologies Used

### Web

* HTML5
* CSS3
* JavaScript
* QRCode.js
* Firebase JS SDK

### Android

* Java
* CameraX
* ML Kit Barcode Scanner
* Firebase Realtime Database
* AlarmManager & Notifications

---

## 🔐 Security Highlights

* Dynamic & expiring QR tokens
* Firebase-side validation
* Server timestamp verification
* Duplicate scan prevention
* Office-specific QR codes

---

## 🏢 Company

**MarsAero Innovations**
*Engineering smart systems for a smarter workforce.*

---

## 📌 Future Enhancements

* Admin dashboard
* Late attendance detection
* Geo-fencing
* Export reports (PDF / Excel)
* Multi-office support

---

## 📄 License

© MarsAero Innovations
Internal use only. Unauthorized distribution prohibited.

