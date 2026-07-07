# Digital GatePass System

An Android-based visitor management application that streamlines visitor entry and exit using Aadhaar OCR, QR-based digital gate passes, and Firebase. The app replaces manual gate registers with a secure, paperless solution while protecting sensitive information through SHA-256 hashing.

---

## Features

- Aadhaar scanning using Google ML Kit OCR
- SHA-256 hashing for privacy protection
- Verhoeff checksum validation for Aadhaar numbers
- Optional student verification
- Blacklist verification before pass generation
- QR code generation for digital gate passes
- QR-based visitor checkout
- Firebase Firestore cloud database
- Visitor history and search functionality
- Firebase Hosting for online gate pass viewing

---

## Tech Stack

| Category | Technologies |
|----------|--------------|
| Language | Java |
| IDE | Android Studio |
| Database | Firebase Firestore |
| Hosting | Firebase Hosting |
| OCR | Google ML Kit Text Recognition |
| Camera | CameraX |
| QR Code | ZXing |
| Security | SHA-256 Hashing, Verhoeff Validation |
| UI | Material Design 3 |

---

## How It Works

1. Scan the visitor's Aadhaar card using the device camera.
2. Extract details using Google ML Kit OCR.
3. Validate the Aadhaar number using the Verhoeff algorithm.
4. Check whether the visitor is blacklisted.
5. (Optional) Verify the student being visited.
6. Hash the Aadhaar number using SHA-256 before storage.
7. Store visitor details securely in Firebase Firestore.
8. Generate a unique QR-based digital gate pass.
9. Scan the QR code during checkout to update the visitor's exit status.

---

## Project Structure

```
app/src/main/java/com/example/gatepass/
 ├── activities/     # All screens (Main, Login, Dashboard, GatePassForm, Checkout, etc.)
 ├── adapters/        # RecyclerView adapters (Blacklist, Guard, LiveSearch, Visitor)
 ├── firebase/        # Firestore repository and constants
 ├── models/          # Data models (Guard, Visitor, SearchResult)
 ├── qr/               # QR code generation utilities
 ├── scanner/          # Aadhaar OCR scanning and blur detection
 ├── utils/            # Shared utilities (hashing, date/time, session, constants)
 └── validation/       # Verhoeff checksum and blacklist validation logic
```

---

## Security

- Aadhaar numbers are never stored in plain text.
- SHA-256 hashing protects visitor identity.
- Verhoeff checksum validation prevents invalid Aadhaar entries.
- Blacklist verification is performed before pass generation.

---

## Requirements

- Android 7.0 (API 24) or later
- Android Studio
- A Firebase project (Firestore + Hosting enabled)
- Internet connection

---

## Setup

1. Clone the repository.
   ```bash
   git clone https://github.com/itz-subham/Digital-GatePass-System.git
   ```
2. Open the project in Android Studio.
3. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com), register an Android app with package name `com.example.gatepass`, and download your own `google-services.json`.
4. Place `google-services.json` in the `app/` directory. This file is gitignored and **not included in the repo** — the app will not build without your own copy.
5. Sync Gradle.
6. Build and run the application.

---

## Future Improvements

- Admin dashboard
- Push notifications
- Visitor analytics
- Multi-campus support
- Role-based authentication

---

## Author

**Subham Singh**
BCA Student | Android Developer
GitHub: [github.com/itz-subham](https://github.com/itz-subham)
