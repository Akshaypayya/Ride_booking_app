# Auto Rickshaw Ride Booking & Dispatch Platform Suite

[![Flutter](https://img.shields.io/badge/Built%20With-Flutter-02569B?logo=flutter&logoColor=white)](#)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)](#)
[![Suite](https://img.shields.io/badge/Architecture-User%20%7C%20Driver%20%7C%20Admin-7952B3)](#)
[![Payments](https://img.shields.io/badge/Payments-Razorpay%20%7C%20UPI-0C2340?logo=razorpay&logoColor=white)](#)
[![Maps](https://img.shields.io/badge/Location-Google%20Maps%20%26%20GPS-4285F4?logo=google-maps&logoColor=white)](#)
[![Backend](https://img.shields.io/badge/Backend-Firebase%20FCM-FFCA28?logo=firebase&logoColor=black)](#)

A complete, production-ready on-demand auto rickshaw mobility and dispatch platform built with Flutter. The platform connects passengers, driver partners, and dispatch operators into an end-to-end ride hailing ecosystem.

---

## 📱 Ecosystem Applications

The repository contains release builds for all three core pillars of the ride hailing suite:

```
Ride_booking_app/
├── user/
│   └── app-release.apk    # Auto Passenger Booking App
├── driver/
│   └── app-release.apk    # Auto Driver Partner App
├── admin/
│   └── app-release.apk    # Fleet Operations & Admin Panel
├── .gitignore             # Git ignore configuration
└── README.md              # Project documentation
```

---

## 🌟 Key Features

### 🚖 1. Passenger Booking App (`com.example.auto_user`)
- **Map-Based Pickup & Drop Selection**: Real-time geolocation pin drop and destination search powered by Google Maps.
- **Instant Fare Estimation**: Automated distance calculation, time estimates, and transparent pricing.
- **Live Driver Tracking**: Real-time map visualization of approaching auto rickshaw with live ETA.
- **Integrated Digital Payments**: Instant cashless checkout via **Razorpay** and direct **UPI** chooser integration.
- **Push Alerts & Receipts**: Instant ride confirmation, driver arrival alerts, and digital trip receipts via Firebase Cloud Messaging.

### 🚗 2. Driver Partner App (`com.example.auto_driver`)
- **Instant Ride Requests**: Real-time push notifications of nearby ride opportunities with pickup distance and fare details.
- **One-Tap Trip Management**: Easy status toggles for Accept Ride, Arrived at Pickup, Start Trip, and Trip Completed.
- **Turn-by-Turn GPS Navigation**: Integrated navigation guidance to passenger pickup and destination spots.
- **Real-Time Location Broadcast**: Continuous background GPS tracking via Geolocator service for accurate dispatching.
- **Trip History & Earnings**: Detailed daily and weekly summaries of completed rides, cash collected, and digital payouts.

### 🛠️ 3. Admin & Dispatch Console (`com.example.autorikshaw_admin_panel`)
- **Driver Verification & Onboarding**: Review driver KYC, vehicle registration, and license documents.
- **Live Fleet Monitoring**: Real-time map overview of active, idle, and in-transit auto rickshaws.
- **Fare Matrix Management**: Customize base fares, per-kilometer rates, night surge, and platform commissions.
- **Dispute & Support Management**: Resolve rider/driver disputes and maintain marketplace compliance.

---

## 📦 Application Release Specifications

| Component | Directory | Application Name | Package ID | Key Technologies |
|---|---|---|---|---|
| **Passenger App** | [`user/app-release.apk`](user/app-release.apk) | `auto_user` | `com.example.auto_user` | Flutter, Google Maps, Razorpay, UPI, Firebase |
| **Driver App** | [`driver/app-release.apk`](driver/app-release.apk) | `auto_driver` | `com.example.auto_driver` | Flutter, Background GPS, Geolocator, Firebase FCM |
| **Admin Console** | [`admin/app-release.apk`](admin/app-release.apk) | `autorikshaw_admin_panel` | `com.example.autorikshaw_admin_panel` | Flutter, Firebase Auth, Google Maps Utils |

---

## 📲 Installation

To install the release build on an Android device:

1. Download the respective APK file from the repository or Releases section:
   - **Passenger App**: [`user/app-release.apk`](user/app-release.apk) (~98.3 MB)
   - **Driver App**: [`driver/app-release.apk`](driver/app-release.apk) (~94.1 MB)
   - **Admin Console**: [`admin/app-release.apk`](admin/app-release.apk) (~40.2 MB)
2. Enable **Install from Unknown Sources** in your Android device settings if prompted.
3. Open the downloaded `.apk` file and tap **Install**.

Alternatively, install via ADB:
```bash
# Install Passenger Booking App
adb install -r "user/app-release.apk"

# Install Driver Partner App
adb install -r "driver/app-release.apk"

# Install Fleet Admin Console
adb install -r "admin/app-release.apk"
```

---

## 🛠️ Repository Setup

### Cloning the Repository
```bash
git clone https://github.com/Akshaypayya/Ride_booking_app.git
cd Ride_booking_app
```

---

## 📄 License

This repository contains proprietary release builds for the Auto Rickshaw Ride Booking Platform. All rights reserved.
