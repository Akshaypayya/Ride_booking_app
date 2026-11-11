# Tuk Tuk — Auto Rickshaw Ride Booking & Dispatch Platform Suite

[![Flutter](https://img.shields.io/badge/Built%20With-Flutter-02569B?logo=flutter&logoColor=white)](#)
[![Riverpod](https://img.shields.io/badge/State%20Management-Riverpod%20Clean%20Architecture-00A6ED?logo=dart&logoColor=white)](#)
[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?logo=android&logoColor=white)](#)
[![Suite](https://img.shields.io/badge/Architecture-User%20%7C%20Captain%20%7C%20Admin-7952B3)](#)
[![Payments](https://img.shields.io/badge/Payments-Razorpay%20%7C%20UPI%20QR%20%7C%20Wallet-0C2340?logo=razorpay&logoColor=white)](#)
[![Maps](https://img.shields.io/badge/Location-Google%20Maps%20%26%20Directions-4285F4?logo=google-maps&logoColor=white)](#)
[![Backend](https://img.shields.io/badge/Backend-Firebase%20RTDB%20%26%20FCM-FFCA28?logo=firebase&logoColor=black)](#)

A full-stack, on-demand auto rickshaw mobility and dispatch platform built with **Flutter** and **Riverpod Clean Architecture** (`core/`, `data/`, `domain/`, `presentation/`). The platform connects passengers, auto captains (drivers), and fleet admins in real time over Firebase Realtime Database, Google Maps & Directions API, and Razorpay/UPI payments.

---

## 📱 Ecosystem Applications

The repository contains updated release APK builds (refactored to Riverpod Clean Architecture) for all three applications:

```
Ride_booking_app/
├── user/
│   └── auto_user-release.apk      # Tuk Tuk User (Passenger Booking App)
├── driver/
│   └── auto_driver-release.apk    # Tuk Tuk Captain (Driver Partner App)
├── admin/
│   └── auto_admin-release.apk     # Fleet Operations & Admin Console
├── .gitignore                     # Git ignore configuration
└── README.md                      # Project documentation
```

---

## 🏗️ Architecture Highlights (Riverpod Refactor)

All three apps were migrated from legacy stateful service/view code to a layered **Riverpod (`flutter_riverpod`) Clean Architecture**:
- **`core/`**: Theme constants, Google Directions/Places services, Razorpay & Wallet payment services, and map/vehicle helpers.
- **`domain/`**: Immutable data models (`UserModel`, `DriverModel`, `RideRequestModel`, `PaymentMethodModel`).
- **`data/`**: Firebase Auth, Realtime Database, and Cloud Storage repositories behind typed interfaces.
- **`presentation/`**: Reactive `StreamProvider`, `FutureProvider`, and `Notifier` providers driving modular screens and widgets (`ConsumerWidget` / `ConsumerStatefulWidget`).

---

## 🌟 Key Features

### 🚖 1. Passenger Booking App — **Tuk Tuk User** (`com.tuktuk.auto_user`)
- **Map Pin Picker & Smart Search**: Interactive Google Maps pin selection, location autocomplete, saved places (Home/Work/Favorites), and Google Directions route polylines with live distance and ETA.
- **Multi-Tier Auto Selection & Pricing**: Choose between **Regular Auto**, **Electric Auto (EV)**, and **Auto XL (4 Seater)** with transparent fare breakdowns and promo discounts.
- **Live Captain Tracking & 4-Digit OTP**: Reactive `activeRideStreamProvider` tracking incoming captains on the map, 4-digit ride start OTP verification, and persistent active-ride session recovery.
- **Flexible Checkout & Post-Ride Rating**: Pay via **TukTuk Wallet**, **Razorpay / Online UPI**, UPI QR, or **Cash on Delivery**, followed by driver rating and optional tipping.
- **Structured Cancellation & History**: Reason-based ride cancellation flow, trip receipt summaries, and full ride history.

### 🛺 2. Driver Partner App — **Tuk Tuk Captain** (`com.tuktuk.auto_driver`)
- **Default-Offline Duty Radar**: Captains start offline by default and toggle online/offline visibility on a real-time request radar backed by Riverpod stream providers.
- **KYC Onboarding & Verification**: Driver profile setup and document submission synced with Firebase Storage & RTDB, with an awaiting-approval KYC gate.
- **End-to-End Trip & OTP Workflow**: Accept incoming requests, mark arrival at pickup, verify the passenger's 4-digit OTP to start the trip, launch turn-by-turn Google Maps navigation, and broadcast live GPS updates.
- **UPI QR & Cash Settlement**: Generate a trip-specific **UPI QR code** (`qr_flutter`) or confirm cash collection at trip completion, plus track daily/total earnings and ride history.

### 🛠️ 3. Admin & Dispatch Console — **auto_admin** (`com.tuktuk.auto_admin`)
- **Fleet KPI Dashboard & Charts**: Real-time metrics for Total Revenue, Total Trips, Active Fleet, and Online Captains with interactive revenue charts (`fl_chart`).
- **Driver KYC Verification**: Review submitted captain documents and approve or manage driver verification status.
- **Live Active Rides & Fleet Monitoring**: Monitor ongoing trips and route statuses in real time.
- **Users & Reports**: Browse registered passengers/users and inspect operational reports.

---

## 📦 Application Release Specifications

| Component | APK Path | App Label | Package ID | Size | Key Stack |
|---|---|---|---|---|---|
| **Passenger App** | [`user/auto_user-release.apk`](user/auto_user-release.apk) | `Tuk Tuk User` | `com.tuktuk.auto_user` | ~61.9 MB | Flutter, Riverpod, Google Maps, Razorpay, UPI, Firebase |
| **Driver App** | [`driver/auto_driver-release.apk`](driver/auto_driver-release.apk) | `Tuk Tuk Captain` | `com.tuktuk.auto_driver` | ~65.7 MB | Flutter, Riverpod, Geolocator, QR Flutter, Firebase Storage & FCM |
| **Admin Console** | [`admin/auto_admin-release.apk`](admin/auto_admin-release.apk) | `auto_admin` | `com.tuktuk.auto_admin` | ~48.9 MB | Flutter, Riverpod, Google Maps, FL Chart, Firebase RTDB |

---

## 📲 Installation

To install a release build on an Android device:

1. Download the desired APK from the repository:
   - **Passenger App**: [`user/auto_user-release.apk`](user/auto_user-release.apk) (~61.9 MB)
   - **Driver App**: [`driver/auto_driver-release.apk`](driver/auto_driver-release.apk) (~65.7 MB)
   - **Admin Console**: [`admin/auto_admin-release.apk`](admin/auto_admin-release.apk) (~48.9 MB)
2. Enable **Install from Unknown Sources** in your Android device settings if prompted.
3. Open the downloaded `.apk` file and tap **Install**.

Alternatively, install via ADB:
```bash
# Install Passenger Booking App
adb install -r "user/auto_user-release.apk"

# Install Driver Partner App
adb install -r "driver/auto_driver-release.apk"

# Install Fleet Admin Console
adb install -r "admin/auto_admin-release.apk"
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

This repository contains proprietary release builds for the Tuk Tuk Auto Rickshaw Ride Booking Platform. All rights reserved.
