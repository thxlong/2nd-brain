- sử dụng `[routerLink]` để tạo ra path tuỳ biến (ex: https://localhost:4200/home)
- sử dụng `routerLinkActive="router-link-active"`




*app.component.html*
````html
<a [routerLink]="['/home']" routerLinkActive="router-link-active">homepage</a>
&nbsp;|
<a [routerLink]="['/about']" routerLinkActive="router-link-active">aboutpage</a>
&nbsp;|
<a [routerLink]="['/form']" routerLinkActive="router-link-active">form</a>
&nbsp;|
<a [routerLink]="['/reactiveform']" routerLinkActive="router-link-active">reactive form</a>
&nbsp;|
<a [routerLink]="['/driven-form']" routerLinkActive="router-link-active">driven form</a>
<router-outlet></router-outlet>
````

 - Trong `app-routing.module` tạo mảng Routes chứa các path liên kết
 
*app-routing.module.ts*
````ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';
import { FormComponent } from './form/form.component';
import { ReactiveFormComponent } from './reactive-form/reactive-form.component';
import { DataDrivenFormComponent } from './data-driven-form/data-driven-form.component';

const routes: Routes = [
 {path: '',component: HomeComponent},
 {path: 'home',component: HomeComponent},
 {path: 'about',component: AboutComponent},
 {path: 'form',component: FormComponent},
 {path: 'reactiveform',component: ReactiveFormComponent},
 {path: 'driven-form',component: DataDrivenFormComponent},
];

@NgModule({
 imports: [RouterModule.forRoot(routes)],
 exports: [RouterModule]
})

export class AppRoutingModule { }
````