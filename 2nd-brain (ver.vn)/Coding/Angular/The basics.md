

# The basics
Sử dụng những thuộc tính:
-  ngIf
-  ngFor
-  binding
-  ngClass

*home.component.ts*
````ts
import { Component, OnInit, VERSION } from '@angular/core';
@Component({
 selector: 'app-home',
 templateUrl: './home.component.html',
 styleUrls: ['./home.component.scss']
})

export class HomeComponent implements OnInit {
 clicked = false;
 title = `Angular ${VERSION.full} is rad`;
 boats = [{
 name: 'Starfire',
 year: 1997,
 img: 'assets/img/boat.jpg',
 },
 {
 name: 'Oracle',
 year: 1998,
 img: 'assets/img/boat1.jpg',
 }]

 constructor() { }
 ngOnInit(): void {
 }
 handleClick = () => {
 this.clicked = true;
 }
}
````

*home.component.html*
````html
<h1>{{title}}</h1>
<br/>
<button [disabled]="clicked" (click)="handleClick()" style="text-transform: capitalize">Click me</button>

<div *ngIf="clicked">
 <h3>[ngClass]="{
 	'green': boat.name === 'Starfile',
	'red': boat.name ==='Oracle'}"</h3>
 <img [src] = "boat.img" alt="img" style="width: 200px">
 <p>Built in {{boat.year}}</p>
</div>

<div *ngFor="let boat of boats">
 <h3>{{boat.name}}</h3>
 <img [src] = "boat.img" alt="img" style="width: 200px">
 <p>Built in {{boat.year}}</p>
</div>
````

*home.component.scss*
````scss
.green{
color: green
}

.red{
color: red
}
````

Pipes: chuyển trực tiếp làm tròng số trong html `123.123 | number`

````html
{{1.23232323 | number}} //1.232
````

Cách generate ra một pipe: `ng generate pipe <namefile>`
````ts
import { Pipe, PipeTransform } from '@angular/core';
@Pipe({
 name: 'year'
})

export class YearPipe implements PipeTransform {
 transform(value: unknown, ...args: unknown[]): unknown {
 return null;
 }
}
````
Cùng tìm hiểu sâu hơn về [[Pipe]]
# Referrence
[Angular Components Beginner's Guide](https://www.youtube.com/watch?v=23o0evRtrFI&list=PL0vfts4VzfNiX5kG1Q8pg2JQ_SB0_ADM1&index=2&ab_channel=Fireship)