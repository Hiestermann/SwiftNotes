# SwiftNotes
[Merge Sort](https://github.com/Hiestermann/SwiftNotes/blob/main/SwiftNotes.md#merge-sort)


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

#### Kadane's algorithm (max subarray)

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

#### Merge Sort
```swift
    func mergeSort(_ nums: [Int]) -> [Int] {
        guard nums.count > 1 else { return nums }
        let mid = nums.count / 2
        var first = Array(nums[0..<mid])
        var second = Array(nums[mid..<nums.count])

        let leftArray = mergeSort(first)
        let rightArray = mergeSort(second)

        return merge(leftArray, rightArray)
        
    }

    func merge(_ first: [Int], _ second: [Int]) -> [int_fast16_t] { 
        var firstStart = 0
        var secondStart = 0

        var orderdArray = [Int]()
        while firstStart < first.count && secondStart < second.count {

            let firstElement = first[firstStart]
            let secondElement = second[secondStart]
                
            if firstElement < secondElement {
                orderdArray.append(firstElement)
                firstStart += 1
            } else if secondElement < firstElement {
                orderdArray.append(secondElement)
                secondStart += 1
            } else {
                orderdArray.append(secondElement)
                secondStart += 1
                
                orderdArray.append(firstElement)
                firstStart += 1
            }
        }

        while firstStart < first.count {
            orderdArray.append(first[firstStart])
                firstStart += 1
        } 

        while secondStart < second.count {
            orderdArray.append(second[secondStart])
                secondStart += 1
        } 

        return orderdArray
    }
```

#### Merge two sorted arrays

```swift
func mergeSort(_ arr: [Int]) -> [Int] {
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

#### sorted colors
```swift
while mid <= end {
            var item = nums[mid]
            if item == 0 {
                nums.swapAt(mid, start)
                start += 1
                mid += 1
            } else if item == 1 {
                mid += 1
            } else  if item == 2 {
                nums.swapAt(mid, end)
                end -= 1
            }
        }
```

#### three sum

```swift
    func threeSum(_ nums: [Int]) -> [[Int]] {
        var seen = [Int]()
        var elements = Set<[Int]>()
        
        for i in 0..<nums.count {
            seen = [Int]()
            let first = nums[i]
            for b in 0..<nums.count {
                if b != i {
                var calculation = 0 - first - nums[b]

                    if let e = seen.first { $0 == calculation } {
                        let ar = [first, nums[b], e]
                           elements.insert(ar.sorted())
                           break
                        }
                         seen.append(nums[b])
                    }
                    
            }
        
        }
        return Array(elements)
    }
```

#### trapping water

```swift
 func trap(_ height: [Int]) -> Int {
        var left = 0
        var right = height.count - 1
        var leftMax = height[left]
        var rightMax = height[right]
        var trappedWater = 0

        while left < right {
            if height[left] < height[right] {
                leftMax = max(leftMax, height[left])
                trappedWater += leftMax - height[left]
                left += 1
            } else {
                rightMax = max(rightMax, height[right])
                trappedWater += rightMax - height[right]
                right -= 1
            }
        }

        return trappedWater
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


### Power of two
| Power of 2 | Exact Value (x)   | Approx. Value |  X Bytes into MP, GB, etc. |
|------------|-------------------|---------------|----------------------------|
| 7          | 128               |               |                            |
| 8          | 256               |               |                            |
| 10         | 1024              | 1 thousand    | 1KB                        |
| 16         | 65,536            |               | 64KB                       |
| 20         | 1,048,576         | 1 million     | 1 MB                       |
| 30         | 1,073,741,824     | 1 billion     | 1 GB                       |
| 32         | 4,294,967,296     |               | 4 GB                       |
| 40         | 1,099,511,627,776 | 1 trillion    | 1 TB                       |



