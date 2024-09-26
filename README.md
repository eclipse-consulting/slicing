# slicing

```
                +-----------------------------+
                | Start and Stop Slicing Guide |
                +-----------------------------+

start >= 0, stop >= 0       start < 0, stop >= 0       start >= 0, stop < 0       start < 0, stop < 0
     |                             |                          |                         |
     v                             v                          v                         v
+-------------------------+ +------------------------+ +------------------------+ +------------------------+
| Positive Index Slicing   | | Negative Start Index   | | Positive Start,        | | Negative Start and      |
| from 'start' to 'stop'   | | Positive Stop         | | Negative Stop          | | Negative Stop           |
|                         | |                       | |                        | |                        |
| - Slice begins at 'start'| | - Slice starts 'n'    | | - Slice starts at      | | - Slice starts 'n'      |
| - Stops just before 'stop'| | elements from the end| | 'start' index          | | elements from the end   |
|                         | |                       | | - Stops at 'stop'      | | - Stops at 'stop' index |
| Example:                | | Example:              | | elements before the end| | counting from the end   |
|                         | |                       | |                        | |                        |
|  x[2:5]                 | |  x[-3:5]              | | Example:               | | Example:               |
| (Start from index 2,    | | (Start 3 elements     | |                        | |                        |
| end before index 5)     | | from end, stop at 5)  | |  x[2:-2]               | |  x[-5:-2]              |
|                         | |                       | | (Start at 2, end 2     | | (Start 5 from the end,  |
| Result: [2, 3, 4]       | | Result: [-3, -2, 0, 1]| | from the end)          | | stop 2 from the end)    |
+-------------------------+ +------------------------+ +------------------------+ +------------------------+

                             Special Cases:
                             - If stop is omitted, the slice goes to the end of the sequence
                             - If start is omitted, the slice starts from the beginning of the sequence
                             - If both are omitted (e.g., `x[:]`), it returns the entire sequence

```
