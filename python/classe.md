---
title: Classe
description: 
published: true
date: 2023-05-07T12:39:02.504Z
tags: 
editor: markdown
dateCreated: 2023-05-07T12:39:00.375Z
---

# Classe
```python
class Clone_state():
    def __init__(self, pos: int, floor: int, direction: str):
        self.pos = pos
        self.floor = floor
        self.direction = direction
    
    def __str__(self):
        return f"Clone_state(pos={self.pos}, floor={self.floor}, direction='{self.direction}')"
    
    def give_list(self):
        return [self.pos, self.floor, self.direction]
```

`__init__` permet ceci:
```python
actual = Clone_state(10, 5, 'N')
```

`__str__(self)` permet ceci:
```python
print(str(actual))
#=> Clone_state(pos=10, floor=5, direction='N')
```

`give_list(self)` permet ceci:
```python
[10, 5, 'N']
```