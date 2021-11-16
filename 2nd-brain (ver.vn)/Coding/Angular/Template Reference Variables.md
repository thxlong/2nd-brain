# Template Reference Variables
tương tự như đặt ID cho element và dùng DOM để đặt giá trị

*html*
````html
 <input #inputQuantityElement type="number" class="quantity" [step]="product.quantity" [value]="product.quantity"

 (input)="updateQuantity(inputQuantityElement)" />
````

*ts*
````ts
 updateQuantity(element: any) {
	 let quantity = element.value;
		 if (quantity === '0') {
		 quantity = '';
		 } else {
		 return quantity;
	 }
 }
````