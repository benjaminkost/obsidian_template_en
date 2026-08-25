---
"created date:": "<% tp.date.now("DD.MM.YYYY HH:mm") %>"
tags:
  - baby
aliases:
  - "<% tp.file.title.split(" - ")[1] %>"
parent: 
up: 
siblings: 
child: 
composed_of: 
requires:
required_by:
prev: 
next: 
correct: false
---


# Subtopics
```dataview
LIST FROM !#exercise 
WHERE contains(up, [[]]) OR contains(parent, [[]])
SORT file.ctime ASC
```
# Exercises
```dataview
LIST FROM [[]] AND #exercise 
SORT file.ctime ASC
```
# Sources
