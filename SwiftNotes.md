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

#### Kadane's algorithm

```swift
 func maxSubArray(_ nums: [Int]) -> Int {
        if nums.count == 1 { return nums[0] }
        var maxSum = nums[0]
        var tempSum = 0
        for i in nums {
            tempSum = max(i, tempSum + i)
            maxSum = max(tempSum, maxSum)
        }

        return maxSum
    }
```


### Time Complecity
#### unbalanced binary tree
h = height of binary search tree
best case: O(h)

worst case: n = h -> O(n)

####  balanced Search tree

h = log(n) -> O(logn)

### Debugger taks:
- breakpoints
- stepping
- expression evaluation
- view backtrace
