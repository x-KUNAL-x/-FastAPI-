# ⌨️ TYPING SPEED TEST

A simple **terminal-based typing speed test** built with Python using the `curses` library.

The program displays a random text passage and measures your typing speed in **Words Per Minute (WPM)** while showing incorrect characters in red and correct characters in green.

## ✨ Features

* ⌨️ Real-time typing test
* 📊 Calculates typing speed in WPM
* 🟢 Correct characters displayed in green
* 🔴 Incorrect characters displayed in red
* 🔄 Random text selection
* ⌫ Backspace support
* 🚪 ESC key to exit
* 🖥️ Terminal-based interface

## 🛠️ Technologies Used

* **Python 3**
* `curses`
* `time`
* `random`

## 📂 Project Structure

```text
TYPING-SPEED-TEST/
│
├── TYPING-SPEED-TEST/
│
├── WPM_Typing_Test.py
├── text.txt
└── README.md
```

## 🚀 How to Run

### 1. Install Python

Make sure Python 3 is installed.

Check your Python version:

```bash
python --version
```

### 2. Add Text

Create a file named:

```text
text.txt
```

Add one or more sentences to the file, with each passage on a separate line.

Example:

```text
Python is a powerful and easy to learn programming language.
Practice typing every day to improve your speed and accuracy.
Learning programming requires practice, patience, and consistency.
```

The program randomly selects one line from `text.txt`.

### 3. Run the Program

```bash
python main.py
```

## 🎮 How to Use

When the program starts, you will see:

```text
Welcome to the Speed Typing Test!
Press any key to begin!
```

Press any key to start.

The program will display a text passage. Type the displayed text as accurately and quickly as possible.

Your current speed will be displayed as:

```text
WPM: 45
```

### ⌨️ Keyboard Controls

| Key         | Action                        |
| ----------- | ----------------------------- |
| Normal keys | Type the text                 |
| Backspace   | Delete the previous character |
| ESC         | Exit the test                 |

## 📊 WPM Calculation

The program calculates WPM using the standard assumption that **5 typed characters = 1 word**.

The calculation is:

```python
wpm = round((len(current_text) / (time_elapsed / 60)) / 5)
```

Where:

* `len(current_text)` = number of characters typed
* `time_elapsed` = time spent typing
* `60` = converts seconds into minutes
* `5` = average characters per word

## 🎨 Character Feedback

The program provides real-time visual feedback.

### 🟢 Green

The character matches the target text.

### 🔴 Red

The character does not match the target text.

The colors are configured using:

```python
curses.init_pair(1, curses.COLOR_GREEN, curses.COLOR_BLACK)
curses.init_pair(2, curses.COLOR_RED, curses.COLOR_BLACK)
```

## 🔄 Random Text Selection

The program reads passages from `text.txt`:

```python
def load_text():
    with open("text.txt", "r") as f:
        lines = f.readlines()
        return random.choice(lines).strip()
```

`random.choice()` selects a random line for each typing test.

## 📚 Python Concepts Used

This project demonstrates:

* Functions
* Loops
* Lists
* File handling
* `random.choice()`
* Time calculation
* Exception handling
* Keyboard input
* Terminal interfaces
* Python modules
* Basic WPM calculation
* Real-time screen updates

## ⚠️ Platform Note

This project uses Python's `curses` library, which is primarily designed for Unix-like terminals.

On **Linux and macOS**, it can generally be run directly with Python.

On **Windows**, the standard `curses` module is not included with Python. A compatible implementation such as `windows-curses` may be required:

```bash
pip install windows-curses
```

Then run:

```bash
python main.py
```

## 🚀 Future Improvements

Possible improvements include:

* 📈 Accuracy percentage
* 🏆 High-score tracking
* ⏱️ Timed typing modes
* 📊 Average WPM
* 📋 More typing passages
* 🎯 Difficulty levels
* 📅 Personal typing statistics
* 🎨 Improved terminal interface

## 👨‍💻 Author

**Kunal Kumar**

A Python learning project focused on terminal applications, keyboard input, file handling, and typing-speed calculation.

---

⭐ **If you found this project useful, consider giving the repository a star!**
