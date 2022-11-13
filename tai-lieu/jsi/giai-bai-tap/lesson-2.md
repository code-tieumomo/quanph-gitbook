---
description: Giải bài tập tuần 2
---

# 2⃣ Lesson 2

## Các hàm mới

### Reduce

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce" %}
Hàm reduce()
{% endembed %}

### Split & Join

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join" %}
Hàm join()
{% endembed %}

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split" %}
Hàm split()
{% endembed %}

### Includes

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes" %}

## Giải bài tập

### Bài 1

Cho 2 mảng sau: `arr1 = [1,2,4,5,6]; arr2 = [1,6,8,9,0]`. Hãy lọc ra một mảng mới chứa 2 phần tử trùng nhau của 2 mảng cho bên trên. **(sử dụng filter())**

> Sử dụng filter(), trên mảng nào cũng được để lọc ra các item thỏa mãn điều kiện là phải nằm trong cả mảng còn lại (sử dụng hàm includes())

```javascript
arr1 = [1, 2, 4, 5, 6];
arr2 = [1, 6, 8, 9, 0];

let filteredArr1 = arr1.filter(function (item) {
    if (arr2.includes(item) == true) {
        return true;
    } else {
        return false;
    }
});

// Cách rút gọn hơn
// filteredArr1 = arr1.filter((item) => arr2.includes(item));
console.log(filteredArr1); // [1, 6]
```

### Bài 2

Sử dụng map() với `arr = [1,54,6,7]` để tạo ra một newArr có `newArr[i] = arr[i] + 5`.

```javascript
arr = [1, 54, 6, 7];
let newArr = arr.map(function (item) {
    return item + 5;
});
// Cách rút gọn hơn
// newArr = arr.map((item) => item + 5);
console.log(newArr); // [6, 59, 11, 12]
```

### Bài 3

Cho array sau: `m = [1,2,4,5,6,7]; n = [3,5,675,8,96]`. Hãy viết một hàm, duyệt cả các mảng m và n; loại bỏ đi phần tử có giá trị bằng **`1,8,10,96,7`**.

> Tạo 1 mảng `l = [1, 8, 10, 96, 7]`, sau đó chúng ta sẽ filter() trên 2 mảng m và n, và chỉ trả về các phần tử thỏa mãn điều kiện là không nằm trong mảng l **(sử dụng includes())**

```javascript
let m = [1, 2, 4, 5, 6, 7];
let n = [3, 5, 675, 8, 96];

const l = [1, 8, 10, 96, 7];
const mFiltered = m.filter(function (item) {
    if (l.includes(item) == true) {
        return false;
    } else {
        return true;
    }
});
console.log(mFiltered);

const nFiltered = n.filter(function (item) {
    if (l.includes(item) == true) {
        return false;
    } else {
        return true;
    }
});
console.log(nFiltered);
```

### Bài 4

Cho array1 như sau:&#x20;

```javascript
players = [
    { id: 11, name: "Messi", age: 33 },
    { id: 12, name: "Ronaldo", age: 34 },
    { id: 13, name: "Young", age: 35 },
    { id: 14, name: "Mane", age: 21 },
    { id: 15, name: "Salah", age: 24 },
];
```

Hãy chuyển đổi nó về array có dạng sau:&#x20;

```javascript
playersModified = {
    11: { id: 11, name: "Messi", age: 33 },
    12: { id: 12, name: "Ronaldo", age: 34 },
    13: { id: 13, name: "Young", age: 35 },
    14: { id: 14, name: "Mane", age: 21 },
    15: { id: 15, name: "Salah", age: 24 },
};
```

**Lưu ý: làm bằng 2 cách, trong đó có 1 cách sử dụng reduce.**

#### **Cách 1: dùng forEach**

```javascript
let players = [
    { id: 11, name: "Messi", age: 33 },
    { id: 12, name: "Ronaldo", age: 34 },
    { id: 13, name: "Young", age: 35 },
    { id: 14, name: "Mane", age: 21 },
    { id: 15, name: "Salah", age: 24 },
];

let playersModified = {};
players.forEach(function (item) {
    playersModified[item.id] = item;
});
console.log(playersModified); // ...
```

#### Cách 2: dùng reduce

```javascript
let players = [
    { id: 11, name: "Messi", age: 33 },
    { id: 12, name: "Ronaldo", age: 34 },
    { id: 13, name: "Young", age: 35 },
    { id: 14, name: "Mane", age: 21 },
    { id: 15, name: "Salah", age: 24 },
];

const playersModified = players.reduce(function (carry, item) {
    carry[item.id] = item;

    return carry;
}, {});
console.log(playersModified); // ...
```
