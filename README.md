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

Designed with learners with ADHD in mind, the interface keeps each screen
minimal, with large buttons and obvious input fields.

**Learners**
- **Courses** — Maths (arithmetic, integers and rational numbers, algebraic
  equations), English (basic punctuation and vocabulary flash cards), and
  Chemistry (an interactive States of Matter lesson). Physics and Biology are
  listed as coming soon.
- **Mental Maths** — a 10-question game solving algebraic equations with an
  on-screen number pad
- **Spelling Bee** — a 10-question game where learners unscramble a word
  from its definition
- **Gold and shop** — games award gold based on score, which learners spend
  on profile icons
- **Leaderboards** — each game ranks players by their best score
- **Profile editing** — update account details and equip purchased icons

**Educators**
- Create classrooms and add learners by username
- View each classroom's learners alongside their Maths and English high scores

For a full walkthrough with screenshots, see the [User Guide](USER_GUIDE.md).

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
    usermasterlist.csv       — all registered users
    classrooms.csv           — classroom registry
    Leaderboard/             — mathGame.csv, engGame.csv
    Educator/ed1/            — account details and classrooms
    Learner/tone/            — account details and inventory
```

> [!WARNING]
> **Important Note:**
> This is a prototype. Everything you enter is saved in files on your own
> computer, and nothing is sent anywhere. Email addresses aren't verified, so
> any address will work. Names, emails and passwords are all saved in CSV files
> without encryption and can be read directly, so do NOT use your real name,
> email or password.

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
