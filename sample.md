---
title: Processing Student Scores
---

# Problem Statement

You are given a list of student records where each record contains a student's name and their corresponding score in a subject. The input will be taken from the `stdin`, and you will need to process the data to:

1. **Filter** students who scored above 50.
2. **Sort** the filtered list by score in descending order.
3. **Group** the students by their score range:
    - `Excellent` (score > 90)
    - `Good` (score between 70 and 90)
    - `Average` (score between 50 and 69)
    - `Poor` (score < 50)
4. **Output** the names of students in each category, sorted by their scores in descending order, to the `stdout` in the specified format.

#### Input:
The input consists of multiple lines. Each line contains a student name followed by their score, separated by a space. The input ends when an empty line is encountered.

Example input:
```
Alice 95
Bob 62
Charlie 45
David 88
Eve 72
Frank 50
Grace 48
Hannah 91
```

#### Output:
The output should list the students grouped by their score range, each category should have students listed in descending order of their score.

Example output:
```
Excellent:
Alice 95
Hannah 91

Good:
David 88
Eve 72

Average:
Bob 62
Frank 50

Poor:
Charlie 45
Grace 48
```

# Solution
```python test.py  -r 'python test.py'
<prefix>

</prefix>
<template>
def bar_graph_perimeter(heights):
    <los>...</los>
    <sol>
    outer = heights[0] + heights[-1] + 2*len(heights) # left, right, top and bottom
    return outer + sum(abs(h1-h2) for h1, h2 in zip(heights,heights[1:]))
    </sol>
    n = int(input())
    for i in range(n):
      print(bar_graph_perimeter(list(map(int, input().split()))))
</template>
<suffix>

</suffix>
<suffix_invisible>
{% include './utils.py.jinja' %}
</suffix_invisible>
```

# Public Test Cases

## Input 1
```
3 5 3 4 1 3 2 5 9 1 8 1 9 2 8 3
```

## Output 1
```
36
```


# Private Test Cases

## Input 1
```
height = [
    "Alice 95",
    "Bob 62",
    "Charlie 45",
    "David 88",
    "Eve 72",
    "Frank 50",
    "Grace 48",
    "Hannah 91"
]
is_equal(
    process_scores(height),
    "Excellent:\nAlice 95\nHannah 91\n\nGood:\nDavid 88\nEve 72\n\nAverage:\nBob 62\nFrank 50\n\nPoor:\nCharlie 45\nGrace 48\n"
)
```

## Output 1
```
"Excellent:\nAlice 95\nHannah 91\n\nGood:\nDavid 88\nEve 72\n\nAverage:\nBob 62\nFrank 50\n\nPoor:\nCharlie 45\nGrace 48\n"
```

