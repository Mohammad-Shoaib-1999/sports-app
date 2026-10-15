# Sports App 🏀⚽🎾

An adaptive Android application built with **Jetpack Compose** and **Material 3**. The app demonstrates modern Android design patterns and canonical adaptive layouts, seamlessly transitioning between single-pane list/detail navigation on mobile phones and a dual-pane side-by-side layout on tablets, foldables, and desktop displays.

---

## ✨ Features

- **Adaptive Canonical Layout**: Dynamically adjusts interface based on `WindowWidthSizeClass`:
  - **Compact Screens (< 600dp)**: Single-column list view with page navigation to sport details.
  - **Expanded Screens (≥ 840dp)**: Multi-pane side-by-side view showing list and details simultaneously.
- **Material 3 Design & Theming**: Integrated Material 3 color roles, dynamic light/dark mode support, and typography.
- **Unidirectional Data Flow (UDF)**: Clear separation of UI state (`SportsUiState`) managed by `SportsViewModel`.
- **Jetpack Compose Previews**: Complete preview support for compact and expanded form factors.
- **Accessibility & Localization**: Support for plural strings (`player_count_caption`), high-contrast text rendering, and scalable typography.

---

## 🛠️ Tech Stack & Architecture

- **Language**: Kotlin
- **UI Framework**: Jetpack Compose
- **Design System**: Material Design 3 (`androidx.compose.material3`)
- **Adaptive Layouts**: `androidx.compose.material3:material3-window-size-class`
- **Architecture**: MVVM + Unidirectional Data Flow (UDF)
- **State Management**: Kotlin Coroutines & `StateFlow`
- **Build System**: Gradle KTS

---

## 📐 Layout Behavior Across Form Factors

```
+---------------------------------+  +-----------------------------------------------------+
|        Compact (Phone)          |  |                 Expanded (Tablet/Desktop)           |
| +-----------------------------+ |  | +--------------------+ +--------------------------+ |
| | [Bar] Sports                | |  | | [Bar] Sports       | | [Detail Header]          | |
| +-----------------------------+ |  | +--------------------+ +--------------------------+ |
| | [Card] Baseball             | |  | | [Card] Baseball    | | Banner Image             | |
| | [Card] Badminton            | |  | | [Card] Badminton   | | Player Count / Olympic   | |
| | [Card] Basketball           | |  | | [Card] Basketball  | | Detailed Text Article... | |
| +-----------------------------+ |  | +--------------------+ +--------------------------+ |
+---------------------------------+  +-----------------------------------------------------+
```

---

## 📂 Project Structure

```
sports-app/
├── app/
│   └── src/main/java/com/example/sports/
│       ├── MainActivity.kt                # WindowSizeClass calculation & Activity entry
│       ├── data/
│       │   └── LocalSportsDataProvider.kt # Sports dataset provider
│       ├── model/
│       │   └── Sport.kt                   # Core Sport data model
│       ├── ui/
│       │   ├── SportsScreens.kt           # Adaptive Composables & Dual-Pane UI
│       │   ├── SportsViewModel.kt         # ViewModel holding SportsUiState
│       │   └── theme/                     # Material 3 Color, Theme, and Type tokens
│       └── utils/
│           └── WindowStateUtils.kt        # SportsContentType enum (ListOnly, ListAndDetail)
├── OVERVIEW.md                            # In-depth Architectural & Technical Analysis
└── README.md                              # Project documentation
```

---

## 🚀 Getting Started

### Prerequisites
- Android Studio Ladybug or newer
- JDK 17+
- Android SDK 35 (Compile SDK)
- Android device or emulator running API 24+

### Build & Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Mohammad-Shoaib-1999/sports-app.git
   ```
2. Open the project in Android Studio.
3. Sync project with Gradle files.
4. Select target device / Resizable Emulator and press **Run (Shift + F10)**.

---

## 📖 In-Depth Technical Analysis

For a deep architectural review covering software architecture patterns, code structure, product usability analysis, and Mermaid diagrams, check out [`OVERVIEW.md`](OVERVIEW.md).
