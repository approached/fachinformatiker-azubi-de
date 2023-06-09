---
title: Python Autoclick
description: 
published: true
date: 2023-01-29T22:17:11.553Z
tags: 
editor: markdown
dateCreated: 2023-01-29T21:57:11.707Z
---

# Python Autoclick

Seite: https://orteil.dashnet.org/cookieclicker/
Plugin: `pip install pynput`

## Code
```python
import time
import threading
from pynput.mouse import Controller, Button
from pynput.keyboard import Listener, KeyCode

TOGGLE_KEY = KeyCode(char='t')

clicking = False
mouse = Controller()

def clicker():
    while True:
        if clicking:
            # print(clicking)
            mouse.click(Button.left, 1)
        time.sleep(0.00001)

def toggle_event(key):
    if key == TOGGLE_KEY:
        # print("foo")
        global clicking
        clicking = not clicking

click_thread = threading.Thread(target=clicker)
click_thread.start()

with Listener(on_press=toggle_event) as listener:
    listener.join()

```



## Notes

* Video: https://www.youtube.com/watch?v=4hdK9Gey76E