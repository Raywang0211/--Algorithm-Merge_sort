# -Algorithm-Insert-sort

### 簡介：

將個別元素進行比較並且插入到對應位置，通常應用場景是將一個新的資料插入到已經排序好的資料當中。也可以是某個list要重新排列。

## 執行過程：

1. 從list中index 0 與 index1開始比較，記住index 1
2. 若0>1 則將 0填入 1的數值接著將已寄住的index1 放入 0的位置(對調)
3. 接著比 index1 以及 index2，記住index2
4. 若2>1，不做改變，若2<1 則需要做交換，交換完之後要再比較index0 與 1
5. 依此類推

### 舉例：

[9,8,7,6,5,4,3]

1. [9]
2. [8,9]依序比大小之後插入
3. [7,8,9]依序比大小之後插入
4. ……..[3,4,5,6,7,8,9]

## 注意：

## 複雜度：

時間複雜度

最差：O(n^2)

最佳：O(n)

平均：O(n^2)

空間複雜度

最差：O(n)

## 程式：

```python
data = [89, 34, 23, 78, 67, 100, 66, 29, 79, 55, 78, 88, 92, 96, 96, 23]

def InsertionSort(data):
    n = len(data)
    for i in range(n-1):
        key = data[i+1] #next value
        j = i
        while j >=0 and key < data[j] : #compare this and next value
                data[j+1] = data[j] #this bigger than next change
                j -= 1
        data[j+1] = key
    return data
        
print(InsertionSort(data))
```