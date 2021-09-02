# Slice
Cắt mảng và **không làm thay đổi giá trị mảng ban đầu** và trả ra một mảng mới với kết quả được `slice`

### Syntax
> 
slice()
slice(start)
slice(start, end)


*Example*:
````js
let arr = ['a', 'b', 'c', 'd', 'e']

// cắt 2 phần tử đầu
console.log(arr.slice(2))  		// Output: ['c', 'd', 'e']

// cắt 2 phần tử đầu và phần tử thứ 4 trở đi
console.log(arr.slice(2,4)) 	// Output: ['c', 'd']

// lấy ra 2 phần tử cuối
console.log(arr.slice(-2))		// Output: ['d', 'e']

// lấy ra phần tử cuối
console.log(arr.slice(-1))		// Output: ['e']
````

# Splice
Thay đổi nội dung của một mảng bằng cách loại bỏ hoặc thay thế các phần tử hiện có hoặc thêm các phần tử mới vào vị trí **thay đổi giá trị mảng ban đầu** và trả ra một mảng mới với kết quả được `splice`

### Syntax
>
splice(start)
splice(start, deleteCount)
splice(start, deleteCount, item1)
splice(start, deleteCount, item1, item2, itemN)


*example*
````js
/* splice(start) */
const monthDemo1 = ['Jan', 'March', 'April', 'June'];
// Cắt ra index đầu tiên
console.log(monthDemo1.splice(0)); 				// Output: ['Jan']
// Giá trị mảng còn lại
console.log(monthDemo1);						// Output: ['March', 'April', 'June']

/* splice(start, deleteCount) */
const monthDemo2 = ['Jan', 'March', 'April', 'June'];
// Cắt ra index thứ 2 và xoá đến phần tử 3
console.log(monthDemo2.splice(1, 3));			// Output: ['March', 'April', 'June']
// Giá trị mảng còn lại
console.log(monthDemo2);						// Output: ['Jan']

/* splice(start, deleteCount, item1) */
const monthDemo3 = ['Jan', 'March', 'April', 'June'];
// Cắt ra phần tử index cuối cùng, xoá nó và thêm vào 1 phần tử mới
console.log(monthDemo3.splice(-1, 1, 'Dec'));	// Output: ['Jun']
// Giá trị mảng còn lại
console.log(monthDemo3);						// Output: ['Jan', 'March', 'April', 'Dec']

````



# Reverce
Đảo ngược một mảng tại chỗ. Phần tử mảng đầu tiên trở thành phần tử cuối cùng và phần tử mảng cuối cùng trở thành phần tử đầu tiên, **làm thay đổi giá trị ban đầu của mảng**

### Syntax
> reverse()

*example*
````js
const array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// expected output: "array1:" Array ["one", "two", "three"]

const reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]

// Careful: reverse is destructive -- it changes the original array.
console.log('array1:', array1);
// expected output: "array1:" Array ["three", "two", "one"]
````


# Concat
Để hợp nhất hai hoặc nhiều mảng. Phương thức này **không thay đổi các mảng hiện** có mà thay vào đó **trả về một mảng mới**.

### Syntax
>
concat()
concat(value0)
concat(value0, value1)
concat(value0, value1, ... , valueN)

*Example*
````js
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
// expected output: Array ["a", "b", "c", "d", "e", "f"]

// Bằng với
const sameConcat = [...array1, ...array2]
console.log(sameConcat);
// expected output: Array ["a", "b", "c", "d", "e", "f"]
````

# Join

*Example*
````js
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"
````

# forEach
- Thực thi vòng lặp cho mỗi phần tử mảng
- return value: undefined.


### Syntax
>
// Arrow function
forEach((element) => { ... } )
forEach((element, index) => { ... } )
forEach((element, index, array) => { ... } )


*Example for `forEach((element) => { ... } )` *
````js
const movements = [200, 450, -400, 3000, -650, -130];
 
 /* Dùng forEach */
 movements.forEach(function (movement) {
 movement > 0
 ? console.log(`You deposited: ${movement}`)
 : console.log(`You withdrew: ${Math.abs(movement)}`);
 });
}

/* Dùng for - the same above */
for (const movement of movements) {
 	if (movement > 0) {
 		console.log("You deposited: ${movement}");
	} else {
 		console.log("You withdrew: ${Math.abs(movement)}");
 }

 // Or
 for (const movement of movements) {
	 movement > 0
 	? console.log(`You deposited: ${movement}`)
	 : console.log(`You withdrew: ${Math.abs(movement)}`);
 }

/* Expected output: 
"You deposited: 200"
"You deposited: 450"
"You withdrew: 400"
"You deposited: 3000"
"You withdrew: 650"
"You withdrew: 130"
*/
````


*Example for `forEach((element, index) => { ... } )` 
tương tự `forEach((element, index, array) => { ... } )`, `array` trả lại giá trị mảng đã duyệt qua* 

````js
const movements = [200, 450, -400, 3000, -650, -130];
/* Dùng forEach */
movements.forEach(function (movement, index, array) {
 movement > 0
 ? console.log(`Movement ${index} You deposited: ${movement}`)
 : console.log(`Movement ${index} You withdrew: ${Math.abs(movement)}`);
});

/* Expected output: 
"Movement 0 You deposited: 200, Mảng đã duyệt: 200,450,-400,3000,-650,-130"
"Movement 1 You deposited: 450, Mảng đã duyệt: 200,450,-400,3000,-650,-130"
"Movement 2 You withdrew: 400"
"Movement 3 You deposited: 3000, Mảng đã duyệt: 200,450,-400,3000,-650,-130"
"Movement 4 You withdrew: 650"
"Movement 5 You withdrew: 130"
*/

/* Dùng for: the same above*/
for (const [index, movement] of movements.entries()){
movement > 0
 ? console.log(`Movement ${index} You deposited: ${movement}`)
 : console.log(`Movement ${index} You withdrew: ${Math.abs(movement)}`);
}

````


# Reduce


### Syntax
> 
// Arrow function
reduce((previousValue, currentValue) => { ... } )
reduce((previousValue, currentValue, currentIndex) => { ... } )
reduce((previousValue, currentValue, currentIndex, array) => { ... } )
reduce((previousValue, currentValue, currentIndex, array) => { ... }, initialValue)



