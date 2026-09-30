# ⏰ Alarm Clock (Python / Tkinter)

A lightweight desktop alarm clock built with Python's standard library. Choose an hour, minute and second from drop-down menus, press **Set Alarm**, and the app plays a sound when the system time reaches your chosen time. The waiting runs on a background thread, so the window never freezes.

**Author:** Pratik Arya | **Reg. No.:** 26BAI10137 | **Platform:** VITyarthi

## Features
- Simple Tkinter window (400x200) with hour / minute / second selectors
- Checks the time every second in a background thread
- Prints current time and alarm time in the console while waiting
- Plays a WAV sound when the alarm time is reached
- No third-party packages required

## Requirements

| Item | Details |
|---|---|
| Operating System | Windows (uses the `winsound` module) |
| Python | Python 3.x with Tkinter (included in the standard Windows installer) |
| Sound file | A WAV file named `sound.wav` in the same folder as the script |
| Extra packages | None |

## Project Structure
```
alarm-clock-python-tkinter/
├── Pratik Arya 26BAI10137 @ VITYARTHI.py   # main program
├── sound.wav                               # alarm sound (add your own)
├── README.md
└── docs/
    ├── 1_Problem_Statement.md
    └── 2_Project_Report.md
```

## Installation & Running
1. Install Python 3 from [python.org](https://www.python.org/) (tick **tcl/tk and IDLE** during installation).
2. Put the script and a file called `sound.wav` in the same folder.
3. Open Command Prompt in that folder and run:

```bash
python "Pratik Arya 26BAI10137 @ VITYARTHI.py"
```

## How to Use
1. Launch the program; the Alarm Clock window opens.
2. Pick the hour (00-23), minute (00-59) and second (00-59) in **24-hour format**.
3. Click **Set Alarm**.
4. Leave the program running. The console shows the current time and alarm time every second.
5. At the set time, `Time to wake up` is printed and `sound.wav` plays.

> Tip: 6:30 PM is hour `18`, minute `30`, second `00`.

## How It Works
- **tkinter** creates the window, labels and drop-down menus (`OptionMenu`).
- **threading.Thread** runs `alarm()` so the interface stays responsive.
- **datetime** gives the current time, formatted as `HH:MM:SS`.
- **time.sleep(1)** waits one second between checks.
- **winsound.PlaySound** plays `sound.wav` when the current time equals the alarm time.

### Key Functions

| Function | Description |
|---|---|
| `Threading()` | Called by the Set Alarm button; starts `alarm()` on a new thread. |
| `alarm()` | Loops every second, compares current time to the selected time, plays the sound on a match and exits. |

## Known Issues
- Works only on Windows.
- The hour menu contains `24` and the minute/second menus contain `60`; an alarm set with these will never ring.
- An alarm cannot be cancelled once set, and pressing Set Alarm repeatedly starts multiple alarm threads.
- If you close the window while an alarm is pending, the background thread may keep the program alive until it fires.
- If `sound.wav` is missing, Windows may play a default beep or show an error.

## Troubleshooting

| Problem | Fix |
|---|---|
| `ModuleNotFoundError: winsound` | You are not on Windows. Run on Windows or replace `winsound` with a cross-platform library. |
| `ModuleNotFoundError: tkinter` | Reinstall Python and enable tcl/tk support. |
| No sound plays | Check that `sound.wav` is in the same folder, is a valid WAV file, and system volume is on. |
| Alarm never rings | Do not choose 24 (hour) or 60 (minute/second); confirm the time is in 24-hour format. |

## Future Improvements
- Validate time options and add Stop / Snooze buttons.
- Show a live clock and alarm status inside the window.
- Support multiple alarms and custom sounds.
- Cross-platform audio support.

## Documentation
- [Problem Statement](docs/1_Problem_Statement.md)
- [Project Report](docs/2_Project_Report.md)

## Author
Pratik Arya - Registration No. 26BAI10137 - VITyarthi
