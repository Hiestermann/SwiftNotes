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
