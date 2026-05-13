# 📚 Namma Pustaka — Smart Library App

A complete Android app for managing rural school libraries. Built with Kotlin, Room DB, ML Kit QR Scanner, MVVM architecture.

---

## 🚀 How to Open in Android Studio

1. **Unzip** the project folder
2. Open **Android Studio** → `File → Open` → select the `NammaPustaka` folder
3. Wait for Gradle sync to complete (first time may take 2–5 minutes, needs internet)
4. Click ▶ **Run** (Shift+F10) on an emulator or real device (Android 7.0+)

---

## 📁 Project Structure

```
NammaPustaka/
├── app/
│   ├── build.gradle                  ← All dependencies here
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/nammapustaka/app/
│       │   ├── data/
│       │   │   ├── dao/              ← BookDao, StudentDao, TransactionDao
│       │   │   ├── database/         ← AppDatabase (Room)
│       │   │   ├── entities/         ← Book, Student, BookTransaction
│       │   │   └── repository/       ← LibraryRepository
│       │   ├── ui/
│       │   │   ├── activities/       ← All screens (8 activities)
│       │   │   ├── adapters/         ← RecyclerView adapters
│       │   │   └── viewmodels/       ← LibraryViewModel
│       │   └── utils/
│       │       └── QRCodeHelper.kt   ← QR code generation
│       └── res/
│           ├── layout/               ← All XML layouts (13 files)
│           ├── drawable/             ← Icons & backgrounds
│           ├── menu/                 ← Bottom nav menu
│           ├── values/               ← Colors, strings, themes, dimens
│           └── xml/                  ← file_paths.xml
├── build.gradle
├── settings.gradle
└── gradle.properties
```

---

## 📱 Screens

| Screen | Description |
|---|---|
| **Splash** | App logo with 2-second delay |
| **Login** | Admin login (Password: `admin`) |
| **Home/Dashboard** | Stats: Total, Available, Issued, Overdue books + Students |
| **Book Catalog** | Grid view of all books with search + category filter |
| **Issue Book** | Select book + search student → confirm issue |
| **Return Book** | Dialog with star rating + review |
| **QR Scanner** | Camera-based scan OR manual entry |
| **Leaderboard** | Students ranked by pages read |
| **Students** | Full student list with search |
| **Add Book** | Form with auto QR code generation |
| **Book Detail** | Full book info + QR image |

---

## ⚙️ Key Technologies

| Tech | Used For |
|---|---|
| **Room DB** | Local database (Books, Students, Transactions) |
| **MVVM + LiveData** | Architecture pattern |
| **ML Kit Barcode** | QR code scanning via camera |
| **CameraX** | Camera preview for QR scanning |
| **ZXing** | QR code generation (print & stick on books) |
| **ViewBinding** | Safe view references |
| **Coroutines** | Async DB operations |
| **Material Design** | UI components (Cards, Chips, FAB, BottomNav) |

---

## 🔑 Features

- ✅ Add books with auto-generated QR codes
- ✅ Issue books to students by scanning QR or manual entry
- ✅ 14-day return window — overdue text turns **RED** automatically
- ✅ Search books by title or author
- ✅ Filter books by category (ಕಥೆ, ವಿಜ್ಞಾನ, ಇತಿಹಾಸ...)
- ✅ Student reading leaderboard
- ✅ Star rating + review when returning a book
- ✅ Pre-loaded with 8 sample books and 5 sample students
- ✅ Kannada language support throughout

---

## 🗂️ Sample QR Codes (Pre-loaded Books)

```
NP-BOOK-001  →  ರಾಮಾಯಣ
NP-BOOK-002  →  ಚಂದ್ರಲೋಕದ ಯಾತ್ರೆ
NP-BOOK-003  →  ಕಿಚ್ಚು ಮತ್ತು ಗೆಳೆಯರು
NP-BOOK-004  →  ಗಣಿತ ಮ್ಯಾಜಿಕ್
NP-BOOK-005  →  ಭಾರತದ ಸ್ವಾತಂತ್ರ್ಯ ಹೋರಾಟ
NP-BOOK-006  →  The Little Prince
NP-BOOK-007  →  ಪ್ರಕೃತಿಯ ಅದ್ಭುತಗಳು
NP-BOOK-008  →  ಅಕ್ಬರ್ ಬೀರ್ಬಲ್
```

To test QR scanning: go to **Catalog → 📷 QR** and type any code above manually.

---

## 🐛 Troubleshooting

| Problem | Fix |
|---|---|
| Gradle sync fails | Check internet; File → Invalidate Caches → Restart |
| Camera permission denied | Go to phone Settings → Apps → NammaPustaka → Permissions |
| Build error about KSP | Make sure you use Android Studio Hedgehog or newer |
| `minSdk` error | Device must be Android 7.0 (API 24) or above |
