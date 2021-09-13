# Promise

Promise giúp xử lý các thao tác bất đồng bộ, ra đời giúp để giải quyết vấn đề #callback-hell 

Có 3 trạng thái:
-   pending: initial state, neither fulfilled nor rejected.
-   fulfilled: meaning that the operation was completed successfully.
-   ejected: meaning that the operation failed.

*Example:*
````js
var promise = new Promise(
 // Executor

 function (resolve, reject) {
 // Logic
 // Thành công: resolve()
 // Thất bại: reject()

 resolve();
 }
);
	
// Sau khi thực thì sẽ trả ra giá trị
promise.then(function(){
console.log("Successfully!")
}).catch(function(){
console.log("Fail!")
}).finally(function(){
// sau khi thực thi (thành công hoặc thất bại)
console.log("Done!")
});

// Output expected: "Successfully!"
// Output expected: "Done!"
	
````


*or way:*

````js
var promise = new Promise(
 // Executor

 function (resolve, reject) {
 // Logic
 // Thành công: resolve()
 // Thất bại: reject()

 reject();
 }
);
	
// Sau khi thực thì sẽ trả ra giá trị
promise.then(
 function () {
 console.log("Successfully!");
 },
 function () {
 console.log("Fail!");
 }
);

// Output expected: "Fail!"
	
````



