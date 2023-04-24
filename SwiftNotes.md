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

#### Merge sort

```swift
unc mergeSort(_ arr: [Int]) -> [Int] {
    guard arr.count > 1 else {
        return arr
    }
    
    let med = arr.count / 2
    print(med)
    
    let leftA = mergeSort(Array(arr[0..<med]))
    
    let rightA = mergeSort(Array(arr[med..<arr.count]))
    
    return mergeArrays(leftA, rightA)
                            
}

func mergeArrays(_ leftA: [Int], _ rightA: [Int]) -> [Int] {
    var leftIndex = 0
    var rightIndex = 0
    
    var newArray = [Int]()
    newArray.reserveCapacity(leftA.count + rightA.count)
    
        while leftIndex < leftA.count && rightIndex < rightA.count {
            
            if leftA[leftIndex] < rightA[rightIndex] {
                newArray.append(leftA[leftIndex])
                leftIndex += 1
            } else if rightA[rightIndex] < leftA[leftIndex] {
                newArray.append(rightA[rightIndex])
                rightIndex += 1
            }
            else {
                newArray.append(rightA[rightIndex])
                newArray.append(leftA[leftIndex])
                leftIndex += 1
                rightIndex += 1
            }
        }
    
    while leftIndex < leftA.count {
        newArray.append(leftA[leftIndex])
        leftIndex += 1
    }
    
    while rightIndex < rightA.count {
        newArray.append(rightA[rightIndex])
        rightIndex += 1
    }
        
    return newArray
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
