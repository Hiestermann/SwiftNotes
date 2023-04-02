# SwiftNotes

Enumeration of an array of chars:

``` Swift
for (index, char) in s.enumerated() { }
```


Enummerate backwards from an array:
``` Swift
let array = [Int]()

for i in stride(from: array.count - 1, through: 0, by: -1) { }
```
