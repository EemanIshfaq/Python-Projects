# Hangman Game — Python Project

A modular, console-based Hangman game developed in Python. The application enables users to select thematic word categories, guess hidden terms using flexible inputs (individual letters, letter sequences, or complete words), and track game statistics. Each round automatically records performance data into timestamped log files.

---

## Key Features

- **Thematic Categories:** Choose between Animals, Fruits, English (General), and Science (or leave blank for random selection).
- **Flexible Guessing Modes:**
  - Single letter guesses
  - Letter sequences / clusters (e.g., `"ing"`)
  - Full-word guesses
- **Live Terminal Display:** Displays hidden word progression, previously chosen letters, and remaining attempts in real time.
- **Scoring & Performance Metrics:** Tracks session points, cumulative score, total matches, win count, loss count, and win rate percentage.
- **Automated Match Logging:** Automatically creates a uniquely indexed folder (`game1/`, `game2/`, etc.) with an audit report in `log.txt`.

---

## Scoring System

| Player Action | Points Awarded |
| :--- | :--- |
| Correct Single Letter | `+10` |
| Correct Letter Sequence | `+20` |
| Correct Full Word Guess | `+100` |
| Round Win Bonus | `+50` |

> **Note:** A player is allowed a maximum of **6 incorrect attempts** before the round ends in a loss.

---

## Directory Structure

```text
hangman_game/
│
├── main.py                     # Application entry point
│
├── game/
│   ├── engine.py               # Core game loop, logic, and evaluation
│   └── wordlist.py             # Word bank file loader
│
├── ui/
│   └── display.py              # Terminal user interface and state rendering
│
├── words/
│   └── categories/             # Word lists organized by subject
│       ├── animals.txt
│       ├── fruits.txt
│       ├── english_general.txt
│       └── science.txt
│
└── game_log/                   # Automated match history records
    ├── game1/
    │   └── log.txt
    ├── game2/
    │   └── log.txt
    └── ...
```

---

## How to Play

1. Run the script:
   ```bash
   python main.py
   ```
2. Select a category from the available options (`animals`, `fruits`, `english`, `science`) or press **Enter** for a random category.
3. Input your guess (a single letter, substring, or complete word).
4. Monitor your remaining attempts and revealed letters until the word is solved or attempts reach zero.

---

## Terminal Gameplay Example

```text
============================================================
                    WELCOME TO HANGMAN
============================================================
Categories: animals, fruits, english, science
Choose a category (or leave empty for random): fruits

Word: _ _ _ _ _ _
Guessed letters: None
Remaining wrong guesses: 6

Enter your guess: a
[✓] Correct sequence found!

Word: _ a _ a _ a
Guessed letters: a
Remaining wrong guesses: 6

Enter your guess: b
[✓] Correct sequence found!

Word: b a _ a _ a
Guessed letters: a, b
Remaining wrong guesses: 6

Enter your guess: banana
[★] Correct full word guess!

Word: b a n a n a

============================================================
                        ROUND OVER
============================================================
Status: VICTORY
Word: BANANA
Round Score: 180
Career Total Score: 180
Matches Played: 1 | Wins: 1 | Losses: 0 | Win Rate: 100.00%
Session log saved to: game_log/game1/log.txt
============================================================
```

---

## Match Log File Example

Each round generates an audit trail saved under `game_log/game<N>/log.txt`.

### Sample `log.txt`:
```text
========================================
             MATCH AUDIT LOG
========================================
Game ID: 1
Category: fruits
Word: banana
Word Length: 6

Guesses (in chronological order):
  1. 'a'      -> Correct (+10 pts)
  2. 'b'      -> Correct (+10 pts)
  3. 'banana' -> Correct Full Word (+100 pts)

Incorrect Guesses: None
Wrong Guesses Count: 0/6
Remaining Attempts: 6

Result: Win
Win Bonus: +50 pts
Round Score: 180 pts
Cumulative Score: 180 pts

Statistics:
  Games Played: 1
  Wins: 1
  Losses: 0
  Win Rate: 100.00%

Timestamp: 2026-09-20 15:30:00
========================================
```
