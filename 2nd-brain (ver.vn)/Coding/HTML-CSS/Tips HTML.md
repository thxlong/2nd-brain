# Cách đặt nút submit ngoài form

- Đặt `id` cho thẻ `<form>` trùng với `form` của thẻ `<button>` 


````html
<form [formGroup]="profileForm" id="form-profile" class="form-profile" ngSubmit="onSubmit()">
 	<div class='field-group'>
 		<label for="name">Name: </label>
 		<input id="name" type="text" formControlName="name" required>
 		<span *ngIf="profileForm.controls.name.invalid" class="errorMessage text-danger"> * Name is required field</span>
 	</div>
 	<div class='field-group'>
		<label for="age">Age: </label>
 		<input id="age" type="number" formControlName="age" required>
 		<span *ngIf="profileForm.controls.age.invalid" class="errorMessage text-danger"> * Age is required field</span>
	 </div>
 </form>

 <button form="form-profile" (click)="onSubmit()" class="btn btn-success" type="submit" [disabled]="!profileForm.valid">Submit</button>
````