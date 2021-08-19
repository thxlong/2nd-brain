## Precondition
Ta có `data-driven-form.component.ts`, `data-driven-form.component.html`, `app.module.ts`

## Step implement 
- Import `ReactiveForm` vào `app.module.ts`

*app.module.ts*
````ts
import { ReactiveFormsModule } from '@angular/forms';
````

- Import  `FormBuilder`, `FormGroup` vào `data-driven-form.component.ts`
- thêm `private _formBuilder` vào đầu vào của `constructor`

````ts
import { FormBuilder, FormGroup } from '@angular/forms';

 constructor(private _formBuilder: FormBuilder) {}
````

- `Inject` constructor

````ts
 constructor(private _formBuilder: FormBuilder){}
````

- tạo một tham số cho FromGroup

````ts
public frmUser : FormGroup | any;
````
- ValueChanges - sử dụng `subscribe` để trong input để bắt sự kiện change

*data-driven-form.component.ts*
````ts
  this.frmUser.valueChanges.subscribe((data: any)=>{
    console.log(data);
 });
````

- Validition Email 

Cách 1: sử dụng  `formBuilder` thông qua `Validators.email`

*data-driven-form.component.ts*
````ts
email: ['', [Validators.required, Validators.email]],
````

thuộc tính trong FormGroup: `frmUser.controls.email.errors?.email`

Cách 2: sử dụng thông qua `Validators.pattern`
*data-driven-form.component.ts*
````ts
 email: ['', [Validators.required, Validators.pattern('[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,4}$')]],
````
thuộc tính trong FormGroup: `frmUser.controls.email.errors?.pattern`

- Sau đó ta tạo một function createFrom(), trong đó gán `frmUser` = `_formBuilder.group`
- Tạo function `onSubmit` cho button submitForm

````ts
createForm(): void {
 this.frmUser = this._formBuilder.group({
 })
}

 onSubmit() {
 console.log(this.frmUser);
 }
````

- tạo một thẻ `<form>` và tạo các input field cho nó
- gắn `[FormGroup]` vào `form`
- Truyền `formControlName` được tạo tại function `createForm` bên file `.ts` vào thẻ `input`
- gắn `ngsubmit="onSubmit()` để ngăn reload form

````html
````

==Cách xem những tham số của From Group==
````ts
console.log(this.frmUser)
````


# Referrence code
- [My demo Github: Reactive-forms](https://github.com/thxlong/Reactive-Forms/tree/master/reactive-form/src/app/data-driven-form)
- [NghiepUIT - Video:# 48. Forms : Reactive Forms](https://www.youtube.com/watch?v=ayhqLoK90J0&list=PLJ5qtRQovuENHYHqlQP5XT7zwbCA5Q5He&index=48&ab_channel=nghiepuit)