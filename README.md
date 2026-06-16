# Neo_Task2

My approach to Task 2 at NeoSOFT.

Problem 2:

Flatten, Classify & Deduplicate Nested List

Write a function flatten_typed(nested) that takes an arbitrarily nested list, flattens it, removes duplicates, 
and returns a dictionary of typed lists — one key per data type found. Also all lists must be sorted.
Each list must be sorted.


Rules
Flatten to any depth using recursion
Detect type using isinstance()— handle int, float, str, bool at minimum
Check bool before int — in Python, bool is a subclass of int , so order matters
Deduplicate within each type bucket independently
Raise TypeError with a message if an unsupported type (e.g. dict, None) is encountered

==========================================================================================

Test 1 — Integers only
Input: [1, [2, [3, 2]], 1, [4]]
Output dict:

"integers": [1, 2, 3, 4]

==============================================================================================

Test 2 — Mixed int, float, str
Input: [3, ["apple", 1.5], ["apple", [2, 1.5, "banana"]]]
Output dict:

"integers": [2,3]
"floats": [1.5]
"strings": ["apple", "banana"]

==============================================================================================

Test 3 — Bool vs int separation
Input: [True, 1, False, [True, 0, [2, False]]]
Output dict:

"integers": [0, 1, 2]
"booleans": [False, True]
Note: 1 and True are different buckets even though True == 1 in Python.

Test 4 — Unsupported type raises error
Input: [1, [2, {"key": "val"}]]
Raises TypeError: "Unsupported type: dict"
