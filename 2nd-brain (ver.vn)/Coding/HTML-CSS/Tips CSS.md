# Cách căn giữa đối với display inline block
Khi muốn căn giữa 1 khối block trong thẻ div, ta sử dụng `transform:stranslateX(-50%)`  và `left: 50%`:
	-  `left: 50%` để khối dịch ra giữa, nhưng khối block bắt đầu ở giữa
	- `transform:stranslateX(-50%)` dịch chuyển khối block vào 50% về bên trái 

````scss
.box{
display: inline-block;
width: 100px;
height: 100px;
position: relative;
top: 50px;
left: 50%;
transform: translateX(-50%);
}
````