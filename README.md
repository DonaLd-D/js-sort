<h1>10大经典排序算法</h1>

### 1.冒泡排序
- 比较相邻的元素。如果第一个比第二个大，就交换他们两个。
- 对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。
- 这步做完后，最后的元素会是最大的数。
- 针对所有的元素重复以上的步骤，除了最后一个。
- 持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较。
```js
function bubbleSort(arr) {
    var len = arr.length;
    for (var i = 0; i < len - 1; i++) {
        for (var j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j+1]) {        // 相邻元素两两对比
                var temp = arr[j+1];        // 元素交换
                arr[j+1] = arr[j];
                arr[j] = temp;
            }
        }
    }
    return arr;
}
```
```js
function bubblesort(arr){
    if(!(Array.isArray(arr))){
        return arr
    }
    let i=0
    while(i<arr.length-1){
        for(let j=0;j<arr.length-1-i;j++){
            let temp=arr[j+1]
            if(arr[j]>arr[j+1]){
                arr[j+1]=arr[j]
                arr[j]=temp
            }
            i++
        }
    }
    return arr
}
```

### 2. 选择排序
- 首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置。
- 再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。
- 重复第二步，直到所有元素均排序完毕。

```js
function selectionSort(arr) {
    var len = arr.length;
    var minIndex, temp;
    for (var i = 0; i < len - 1; i++) {
        minIndex = i;
        for (var j = i + 1; j < len; j++) {
            if (arr[j] < arr[minIndex]) {     // 寻找最小的数
                minIndex = j;                 // 将最小数的索引保存
            }
        }
        temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    }
    return arr;
}
```

### 3. 插入排序
- 将第一待排序序列第一个元素看做一个有序序列，把第二个元素到最后一个元素当成是未排序序列。
- 从头到尾依次扫描未排序序列，将扫描到的每个元素插入有序序列的适当位置。（如果待插入的元素与有序序列中的某个元素相等，则将待插入元素插入到相等元素的后面。）

```js
function insertionSort(arr) {
    var len = arr.length;
    var preIndex, current;
    for (var i = 1; i < len; i++) {
        preIndex = i - 1;
        current = arr[i];
        while(preIndex >= 0 && arr[preIndex] > current) {
            arr[preIndex+1] = arr[preIndex];
            preIndex--;
        }
        arr[preIndex+1] = current;
    }
    return arr;
}
```

### 4. 希尔排序
### 5. 归并排序
### 6. 快速排序
```js
function quicksort(arr){
    if(!(arr instanceof Array)){
        return arr
    }
    let base=Math.floor(arr.length/2)
    let baseIndex=arr.splice(base,1)[0]
    let left=[]
    let right=[]
    for(let i=0;i<arr.length;i++){
        arr[i]>baseIndex?right.push(arr[i]):left.push(arr[i])
    }
    //return quicksort(left).concat([baseIndex],quicksort(right))
    return [...quicksort(left),baseIndex,...quicksort(right)]
}
```
### 7. 堆排序
### 8. 计数排序
### 9. 桶排序
### 10. 基数排序
