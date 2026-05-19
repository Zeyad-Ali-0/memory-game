<div align="center">

# 🎮 Microcontroller Gaming Console
### Memory & Competitive Speed Game System

![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Arduino%20Uno-teal?style=flat-square)
![Language](https://img.shields.io/badge/Language-C%2B%2B-blue?style=flat-square)
![Module](https://img.shields.io/badge/Module-Computer%20Programming%20for%20EE-orange?style=flat-square)

</div>

---

## 👥 Team

| Name | Name |
|------|------|
| Youssef Hussein | Hamza Bassem |
| Mohammed Medhat | Zeyad Alaa |

---

## 📌 Overview

A compact, battery-powered gaming console built on an Arduino Uno that tests players' **memory and reaction speed** through LED pattern sequences. Supports solo and two-player modes, with real-time score tracking displayed on an LCD and audio feedback through a speaker.

---

## ⚡ System Design

```
[Push Buttons x8]  ──►  [Arduino Uno]  ──►  [LCD 16x2]
[LEDs x4]          ◄──               ──►  [Speaker]
[Power Switch]     ──►               ──►  [LED Indicators]
```

| Block | Component |
|-------|-----------|
| Controller | Arduino Uno |
| Display | 16×2 LCD (I2C) |
| Input | 8 Push Buttons (4 per player) |
| Output | 4 LEDs + Speaker |
| Audio | MP3-TF-16P + Micro SD |
| Power | 3× Battery pack with switch |

---

## 🕹️ Game Modes

### 1 — Solo Sprint
Player watches an LED pattern and must replicate it correctly within **15 seconds** across **5 rounds**. Correct answers increase difficulty; mistakes reset it.

### 2 — Duo Mode
Both players race to replicate the same LED pattern. Whoever does it faster wins the round. If one player makes a mistake, the other still has a chance to complete it.

### 3 — Challenger Mode
One player creates a custom LED sequence, the opponent must replicate it. If they fail, the creator must also replicate their own sequence — fail again and both lose.

---

## 🧠 Software Architecture

The system runs on a **finite state machine** with three states:

```
         ┌─────────────────────────┐
         │          MENU           │
         └────┬────────┬───────────┘
              │        │
    ┌─────────▼──┐  ┌──▼──────────────┐
    │   PLAYING  │  │  SCORE DISPLAY  │
    └────────────┘  └─────────────────┘
```

**Key software features:**
- `millis()`-based debouncing for reliable button input
- Difficulty scaling via faster LED timing
- Score tracking with reset after 5 rounds
- Sleep mode after 5 minutes of inactivity

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `*.ino` / source files | Arduino game code |
| `game_code_explanation.html` | Line-by-line code walkthrough |
| `Report.docx` | Full project report |

---

## 🔮 Future Improvements

- Menu navigation system
- Real-time clock integration
- Turn-based ranking leaderboard
- 3D-printed controller housing
- Wireless third-player support

---

<div align="center">

*Built with buttons, LEDs, and a lot of debouncing.*

</div>
