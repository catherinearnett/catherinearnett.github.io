---
layout: default
title: Loading .txt Files
parent: Resources
nav_order: 8
permalink: /load_txt

---

# Loading .txt Files

One way to load a .txt file is to use the `open` function and create a for loop, reading in each line and appending it to the type of object you're creating. Here, I am creating a list of lines, `text`, but you could also save lines to a pandas dataframe or a dictionary. 

```
from io import open
import sys
import os

path = "file.txt"

text = []
with open(path, encoding="utf8") as infile:
    for line in infile:
        text.append(line)
        
print(text)
```
