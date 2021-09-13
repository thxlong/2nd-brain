# Callback
Lý thuyết đơn giản, `callBack` là một hàm được gọi sau khi hàm trước được thực thi xong `fucntion()` thường được sử dụng trong #Async (bất đồng bộ).

*example:*
````js
setTimeout(function(){
	console.log(1);
}, 1000)
````


Vì bất đồng bộ, nên những callback có thể được gọi khi hàm trước đã thực thi xong. Nhưng nhiều callback được lồng vào nhau sẽ tạo thành 1 #callback-hell


