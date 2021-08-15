Ta có `data-driven-form.component.ts`, `app.module.ts`

- Import `FeactiveForm` vào `app.module.ts`

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

==Cách xem những tham số của From Group==
````ts
console.log(this.frmUser)
````


# Referrence code
- [Github: Reactive-forms](https://github.com/thxlong/Reactive-Forms/tree/master/reactive-form/src/app/data-driven-form)
- [Video: # 48. Forms : Reactive Forms](https://www.youtube.com/watch?v=ayhqLoK90J0&list=PLJ5qtRQovuENHYHqlQP5XT7zwbCA5Q5He&index=48&ab_channel=nghiepuit)