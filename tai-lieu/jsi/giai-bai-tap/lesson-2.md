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

## Bài tập luyện tập

### Bài 1

Cho array sau `arr1 = [1,2,3,5]`. Hãy duplicate array cho bên trên bằng ít nhất 2 cách; trong đó có 1 cách dùng Spread Operator.

### Bài 2

Cho 2 array như sau: `arrA = [“Hello”, “ Xin chào”]; arrB = [“Bonjour”, “Olá”]`. Hãy tạo ra một array mới có tên là waysToSayHello, trong array này sẽ chứa toàn bộ các phần tử của arrA và arrB. Làm bằng 2 cách; trong đó có 1 cách sử dụng Spread Operator.

### Bài 3

Cho `arrX = [0,1,2,3,4,5,6,7,8]`.

* Hãy tạo ra arrSquare, chứa các giá trị của phần tử trong arrX đã được bình phương.
* Hãy tạo ra arrOdds chứa các phần tử là số lẻ nằm trong arrX.

### Bài 4

Viết một hàm `filterRange(arr, a, b)`, với arr là 1 mảng có > 4 phần tử; `0<= a,b < arr.length`. Tìm kiếm giá trị các phần tử nằm giữa `arr[a]` và `arr[b]`. Chú ý, mảng cũ phải không bị thay đổi. VD: `arr= [1,5,4,6], a= 0, b = 2;` => `filteredArr = [1,5]`

### Bài 5

Tương tự **bài 4**, tuy nhiên sau khi chạy hàm `filterRange(arr, a,b)` sẽ hiển thị ra giá trị phần tử `> a` và `< b`. VD: `filteredArr = [1]`. Phải tạo ra mảng mới, mảng cũ không thay đổi. Không tạo ra mảng mới, mảng cũ bị thay đổi.

### Bài 6

Cho một mảng như sau

```javascript
let student = [{
	name: "Duong",
	age: 11,
	hobbies: ["video game", "sleep", "learn"]
}, {
	name: "Dong",
	age: 12,
	hobbies: ["video game", "sick", "study"]
}, {
	name: "Minh",
	age: 13,
	hobbies: ["video game", "sick", "learn"]
}, {
	name: "Thanh",
	age: 9,
	hobbies: ["play game", "sleep", "learn"]
}, {
	name: "Hung",
	age: 11,
	hobbies: ["play game", "sick", "study"]
}]
```

* In ra tên những người có tuổi bằng 11&#x20;
* In ra toàn bộ sở thích và name của những ai thích `video game`
* Lọc ra những ai có sở thích là `study` và in ra nó&#x20;
* Thay đổi toàn bộ những ai có tuổi 11 thành 15 **(sử dụng `map`)**
