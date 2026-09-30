# Problem Statement — Alarm Clock (Python / Tkinter)

**Student:** Pratik Arya | **Reg. No.:** 26BAI10137 | **Platform:** VITyarthi

## 1. Problem Statement
People often need a reminder at an exact time of day - to wake up, take medicine, attend a meeting or start a task. Phone alarms exist, but while working on a computer a lightweight desktop alarm is more convenient, especially one that needs no third-party software. The problem is to design and build a simple graphical alarm clock in Python that lets the user choose a time (hour, minute, second) and plays a sound when the system clock reaches that time, without freezing the interface while it waits.

## 2. Motivation
- Desktop users frequently miss time-based tasks while absorbed in work.
- Many alarm apps are heavy, ad-supported or need installation.
- Building one is a practical way to learn GUI programming, system time handling and multithreading in Python.

## 3. Objectives
- Provide a clean graphical interface for choosing an alarm time.
- Continuously compare the chosen time with the live system time.
- Play an audio alert when the times match.
- Keep the interface responsive while waiting by using a background thread.
- Use only Python's standard library.

## 4. Proposed Solution
A Tkinter window with three drop-down menus (hour, minute, second) and a **Set Alarm** button. When the button is pressed, a background thread checks the current time every second. When it equals the selected time, the program prints a message and plays a WAV sound using the `winsound` module.

## 5. Scope

| In scope | Out of scope (current version) |
|---|---|
| Single alarm | Multiple alarms |
| Time selection via drop-down menus | Snooze / cancel / repeat |
| Console log of current vs. alarm time | Date-based alarms |
| WAV sound alert on Windows | macOS and Linux support |

## 6. Requirements Summary

| Type | Requirement |
|---|---|
| Functional | Show window; select H/M/S; start alarm on button click; check time every second; play sound and stop at match. |
| Non-functional | Usable (3 selections + 1 button); responsive (threaded); simple (single file, no dependencies); runs on Windows. |
| Software | Python 3.x, Tkinter, Windows OS, `sound.wav` file |
| Hardware | Any PC with speakers/headphones |

## 7. Expected Outcome
A working desktop alarm clock that accepts a user-selected time and reliably plays an alert sound at that time while the window stays responsive.
