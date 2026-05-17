<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=32&pause=1000&color=F7F7F7&center=true&vCenter=true&width=900&lines=🧬+TGen-MIND+-+Mendelian+Inheritance+Learning+App" alt="Title" />
</div>

An interactive Android educational app designed to teach Mendelian Inheritance concepts through structured lessons, engaging quizzes, and progress tracking. Built with Kotlin and Jetpack Compose, and powered by Firebase for cloud-based authentication and progress storage.

---

### 📦 Stack
- Kotlin & Jetpack Compose
- Firebase Authentication
- Firebase Firestore
- Android Studio
- Material 3

---

### ✨ Quick Start
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/Gen-MIND.git

# Open the project in Android Studio
# File → Open → Select the Gen-MIND folder

# Add your google-services.json from Firebase Console
# Place it in the /app directory

# Build and run on an emulator or physical device
# Build → Make Project → Run
```
Ensure you have Android Studio installed, a Firebase project set up with Authentication and Firestore enabled, and your `google-services.json` placed in the `/app` directory.

---

### ⚙️ Features
- **User Authentication** — Secure sign-up and login via Firebase Authentication with real email addresses and password reset support.
- **10 Structured Lessons** — Progressive lesson system covering Genes, Chromosomes, DNA, Genetics, Gregor Mendel, Punnett Squares, Key Terms, Homozygous vs. Heterozygous, Examples, and Summary.
- **Interactive Quizzes** — Three distinct quiz types embedded in the lesson flow:
  - **Crossword Puzzle** (Lesson 4) — Fill-in vocabulary reinforcement
  - **Punnett Square** (Lesson 9) — Interactive genetic combination exercises
  - **Assessment Quiz** (Lesson 10) — 10-item multiple choice evaluation with scoring
- **Pretest** — Entry assessment with scoring to gauge prior knowledge before lessons begin.
- **Cloud Progress Tracking** — Lesson and quiz completion synced to Firebase Firestore, persisting across devices and app reinstalls.
- **Achievements System** — Visual progress bars tracking completed lessons (out of 10) and completed quizzes (out of 3).
- **Tasks Screen** — Overview of lesson completion progress.
- **Guest Mode** — Explore the app without an account (progress resets on close).
- **COMPLETE! Badge** — Homepage displays a completion badge when all 10 lessons are finished.

---

### 🛠️ How It Works
The app follows a single-activity architecture using Jetpack Compose for UI and Firebase for backend services:
- **Authentication**: Firebase Auth handles real email/password login, sign-up, and password reset via email links.
- **Progress Storage**: Firestore stores each user's `current_lesson`, `completed_lessons`, `completed_quizzes`, and `first_login` flag under a document keyed by their email.
- **Lesson Progression**: Lessons unlock sequentially. Lessons with quizzes (4, 9, 10) show a confirmation dialog before launching the quiz screen.
- **Quiz Validation**:
  - Crossword enforces exact character matching per cell.
  - Punnett Square uses case-sensitive validation (B ≠ b).
  - Assessment Quiz tallies correct answers and displays a final score.
- **Navigation**: Screen routing is managed in `MainActivity.kt` using a `when` block on a `currentScreen` state variable.

---

### 📁 Project Structure
```text
app/src/main/
├── assets/                         # Images and 3D icons used in lessons
│   ├── trophy_3d.png               # Trophy icon for Achievements screen
│   ├── task_3d.png                 # Task icon for Tasks screen
│   └── [lesson images].png         # Lesson-specific illustrations
├── java/com/example/gen_mind/
│   ├── MainActivity.kt             # Main entry point and screen router
│   ├── WelcomeScreen.kt            # Landing screen with login/sign-up/guest options
│   ├── LoginScreen.kt              # Email login with forgot password support
│   ├── SignUpScreen.kt             # New user registration
│   ├── SuccessScreen.kt            # First-time welcome screen
│   ├── PretestScreen.kt            # Entry quiz with scoring (5 questions)
│   ├── HomepageScreen.kt           # Lesson map with progress and icons
│   ├── LessonScreen.kt             # All 10 lesson content screens
│   ├── CrosswordScreen.kt          # Crossword puzzle quiz for Lesson 4
│   ├── PunnettSquareScreen.kt      # Punnett Square quiz for Lesson 9
│   ├── AssessmentQuizScreen.kt     # 10-item MCQ quiz for Lesson 10
│   ├── TasksScreen.kt              # Lesson completion tracker
│   ├── AchievementsScreen.kt       # Progress bars for lessons and quizzes
│   └── CredentialsManager.kt       # Firebase Auth and Firestore logic
├── res/
│   └── [standard Android resources]
└── google-services.json            # Firebase config (not included in repo)
```

---

### 📱 Screens Overview

| Screen | Description |
|--------|-------------|
| Welcome | Entry point with Login, Sign Up, and Guest options |
| Login | Email/password login with password reset |
| Sign Up | New account creation |
| Pretest | 5-question quiz before lessons start |
| Homepage | Lesson map showing progress and unlock status |
| Lesson 1–10 | Scrollable lesson content with images |
| Crossword | Vocabulary fill-in quiz (Lesson 4) |
| Punnett Square | Genetic cross quiz with 2 questions (Lesson 9) |
| Assessment Quiz | 10-item MCQ with score display (Lesson 10) |
| Achievements | Progress bars for lessons and quizzes |
| Tasks | Lesson completion checklist |

---

### 🧬 Quiz Answer Keys

**Crossword Puzzle (Lesson 4)**
| # | Direction | Answer |
|---|-----------|--------|
| 1 | Down | CHROMOSOMES |
| 2 | Down | HISTONES |
| 3 | Across | GENETICS |
| 4 | Down | GENES |
| 5 | Across | DNA |

**Punnett Square (Lesson 9)**
- Question 1 (BB × bb): All cells = `Bb`
- Question 2 (Bb × bb): `BB`, `Bb`, `Bb`, `bb`

**Assessment Quiz (Lesson 10)**
`B, A, C, B, D, C, A, C, A, D`

---

### 👤 Author
**Wayne** — [github.com/wayne2604](https://github.com/wayne2604)
