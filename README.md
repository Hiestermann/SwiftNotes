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


Character to Ascii value
```Swift
let char:Character = "c"
let asciiValue = char.asciiValue // output: 99
```

Ascii value to Character

```Swift
let value = 99
let c = UnicodeScalar(99) // output: c
```
