# QuickQuirk GameLab

A Java desktop application that lets learners study Maths, English, and
Chemistry through interactive lessons and games, while earning coins and
competing on leaderboards. Educators can create classrooms and manage their
learner lists from a separate login.

## About the project

QuickQuirk GameLab is a two-role learning platform built with Java Swing.
Learners work through subject content, play quiz games to earn coins, and
spend those coins in an in-app shop. Educators get a separate view to
organise their classes. All data is stored in CSV files, with each learner
and educator having their own folder in the project directory.

## Features

**Learner**
- Three subject modules: Maths, English, and Chemistry, with more marked as
  coming soon
- **Maths Course** — lessons on the four arithmetic operations and algebra,
  with worked examples
- **English Course** — punctuation lessons covering commas, periods, question
  marks, and exclamation marks
- **Chemistry Course** — an interactive States of Matter lesson where
  learners trigger state changes by heating and cooling a substance
- **Maths Game** — a timed mental maths quiz generating random arithmetic and
  algebra questions; answers submitted via an on-screen number pad
- **English Game** — a punctuation quiz
- **Coin system** — correct answers earn coins; coins are spent in the shop
  to unlock cosmetic items
- **Leaderboard** — scores for each game are saved and ranked
- **Profile editing** — learners can update their account details

**Educator**
- Create classrooms with a classroom code
- Add learners to classrooms by username
- View classroom learner lists

## Sample accounts

| Role | Username | Password |
|---|---|---|
| Learner | tone | t1ab-123 |
| Learner | adibsi | add1234 |
| Educator | ed1 | ed1-123 |
| Educator | ed2 | ed2-123 |

Passwords are stored in plain text in CSV files, which is appropriate for a
desktop prototype but not for a production system.

## Data storage

There is no database. Each user has their own folder under `Learner/` or
`Educator/`, containing an `accountDetails.csv` and an `inventory.csv`.
Classrooms live inside the educator's folder. Global files at the root
handle the user master list and leaderboard scores.

```
QuickQuirkGameLab/
├── usermasterlist.csv       — all registered users
├── classrooms.csv           — classroom registry
├── Leaderboard/             — mathGame.csv, engGame.csv
├── Educator/ed1/            — account details and classrooms
└── Learner/tone/            — account details and inventory
```


## Built with

Java SE and Java Swing, developed in NetBeans. UI layouts use the
NetBeans Form Editor (`.form` files) and the AbsoluteLayout library.

## Getting started

**In NetBeans:** open the project folder and run it. The main class is
`QuickQuirkGameLab.LoginPage`.

**From the command line,** with a JDK installed — run from the project
root folder, since all file paths are relative:

```bash
javac -d build/classes src/QuickQuirkGameLab/*.java src/img/
java -cp build/classes QuickQuirkGameLab.LoginPage
```

Log in with one of the sample accounts above, or register a new learner
account from the login screen.
