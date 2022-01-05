1. Tạo 1 service `EventEmitter` để giao tiếp giữa 2 components

*common.service.ts
````ts
export class CommonService {

 constructor() { }

 callLogin: EventEmitter<any> = new EventEmitter();
}
````

2. Tại component muốn truyền data ra, cho một `emit` trong function

*header.component.ts*
````ts
import { CommonService } from 'src/app/services/common.service';


export class HeaderComponent implements OnInit {
	
 public isLogin: boolean = false;
	
 constructor(public router: Router, private common: CommonService) { }

 clickLogin(): void {

 this.common.callLogin.emit(this.isLogin)

 }
````

3. Tại component muốn truyền data ra, nhận một `subcribe` trong `ngOninit`

````ts
import { Component, OnInit } from '@angular/core';

import { CommonService } from 'src/app/services/common.service';


@Component({

 selector: 'app-modal',

 templateUrl: './modal.component.html',

 styleUrls: ['./modal.component.scss']

})

export class ModalComponent implements OnInit {

 public isClose: boolean = true;

 constructor(private common: CommonService) { }

 closeModal() {

 this.isClose = true;

 }


 ngOnInit(): void {

 this.common.callLogin.subscribe(data => this.isClose = data);

 console.log(this.isClose);

 }

}
````