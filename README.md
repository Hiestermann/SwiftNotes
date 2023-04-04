# SwiftNotes

Enumeration of an array of chars:

``` Swift
for (index, char) in s.enumerated() { }
```


## Enummerate backwards from an array:
``` Swift
let array = [Int]()
for i in stride(from: array.count - 1, through: 0, by: -1) { }
```


## Character to Ascii value
```Swift
let char:Character = "c"
let asciiValue = char.asciiValue // output: 99
```

## Ascii value to Character

```Swift
let value = 99
let c = UnicodeScalar(99) // output: c
```

## Binary tree

```Swift
class Node {
    let value: Int
    var leftChild: Node?
    var rightChild: Node?

    init(value: Int, leftChild: Node?, rightChild: Node?) {
        self.value = value
        self.leftChild = leftChild
        self.rightChild = rightChild
    }
}
```
### Time Complecity
#### unbalanced binary tree
h = height of binary search tree
best case: O(h)

worst case: n = h -> O(n)

####  balanced Search tree

h = log(n) -> O(logn)

Debugger taks:
- breakpoints
- stepping
- expression evaluation
- view backtrace
