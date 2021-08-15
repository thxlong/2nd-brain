Hook | Mục đích & thời điểm
------------ | ------------
ngOnChanges() | Thực thi khi Angular thiết lập các thuộc tính đầu vào ràng buộc dữ liệu. Được gọi trước `ngOnInit()` và bất cứ khi nào một hoặc nhiều thuộc tính đầu vào ràng buộc dữ liệu thay đổi.
ngOnInit() | Khởi tạo directive / component. Được gọi một lần, sau `ngOnChanges()` đầu tiên.
ngDoCheck()|Phát hiện và hành động theo những thay đổi mà Angular không thể hoặc sẽ không tự mình phát hiện. Được gọi trong mỗi lần chạy phát hiện thay đổi, ngay sau `ngOnChanges()` và `ngOnInit()`.
ngAfterContentInit()|Thực thi sau khi Angular thêm nội dung bên ngoài vào view của component / view mà directive được đưa vào. Được gọi một lần sau `ngDoCheck()` đầu tiên.
ngAfterContentChecked()|Thực thi sau khi Angular đã kiểm tra nội dung bên ngoài đã được đưa vào view của component. Được gọi sau `ngAfterContentInit()` và mọi `ngDoCheck()` tiếp theo.
ngAfterViewInit()|Thực thi sau khi Angular khởi tạo các view của component và các view con / view mà directive được đưa vào. Được gọi một lần sau `ngAfterContentChecked()` đầu tiên.
ngAfterViewChecked()|Thực thi sau khi Angular kiểm tra các view component và các view con / view mà directive được đưa vào. Được gọi sau `ngAfterViewInit()` và mọi `ngAfterContentChecked()` tiếp theo.
ngOnDestroy()|Dọn dẹp ngay trước khi Angular phá huỷ directive / component. Huỷ đang ký `Observables` và tách trình xử lý sự kiện để tránh bị rò rỉ bộ nhớ. Được gọi ngay trước khi Angular phá huỷ directive / component.


![[life-cycle-in-angular.png|400]]