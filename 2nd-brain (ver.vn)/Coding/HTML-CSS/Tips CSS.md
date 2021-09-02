# Cách căn giữa đối với display inline block
#### Khi muốn căn giữa theo chiều ngang 1 khối block trong thẻ div, ta sử dụng:
`transform: translateX(-50%)`  và `left: 50%`:
	-  `left: 50%` để khối dịch ra giữa, nhưng khối block bắt đầu ở giữa
	- `transform: translateX(-50%)` dịch chuyển khối block vào 50% về bên trái 

````scss
.box{
display: inline-block;
width: 100px;
height: 100px;
position: absolute;
left: 50%;
transform: translateX(-50%);
}
````
 Bonus: nếu muốn đối tượng căn giữa tại trong tâm thêm thuộc tính `transform: translateY(-50%);` và `top: 50%`
 
# Cách trải đều khối block trong position
#### Khi muốn 1 khối trong block có chiều dài phủ từ trái sang phải, ta sử dụng:
- `left: 0`
- `right: 0`
````scss
.wrapper{
position: relative;

}
.boxed{
position: absolute
left: 0;
right: 0;
}

````

### Khi muốn 1 khối trong block có chiều dài phủ từ trên xuống dưới, ta sử dụng:
- `top: 0`
- `bottom: 0`

````scss
.wrapper{
position: relative;

}
.boxed{
position: absolute
top: 0;
bottom: 0;
}

````