## Interface là gì? Tại sao lại sử dụng interface

> Cô đọng: Interface là một khuôn mẫu, đảm bảo mọi lớp thực thi được truyền dẫn đúng đắn.


**Interface** (nhiều tài liệu gọi là giao diện hoặc lớp giao tiếp) là 1 tập các thành phần chỉ có khai báo mà không có phần định nghĩa (giống phương thức thuần ảo đã trình bày ở bài **[ĐA HÌNH TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYGkJZSuYXwQaP8LTTGHNDzS%2bJ0rgkle8KugDrsLK9KChxZTQpZdKKvKo65LUWChMSFyIs0EBwIoBbHXmlgIZElyZGXaJ%2bKkVmhfB2Vz8Rn%2baw%3d%3d)**).

Các thành phần này có thể là:

-   Phương thức.
-   Property (đã trình bày trong bài **[CÁC LOẠI PHẠM VI TRUY CẬP TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYGkJZSuYXwQaP8LTTGHNDzS54fow40vAPSLNNKn6nDssirWHYqpuUlMjEJi6VJslaDfGk9Kvs7%2buLOXNZzcc8xjPNli27W0lRDN1p1triprF4ruqRVpY9kmPm80QA2kAK8%3d)**).
-   Event (sẽ được trình bày trong bài **EVENT TRONG C#**).
-   Indexers (sẽ được trình bày trong series **[LẬP TRÌNH C# NÂNG CAO](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0lthogs3xmFNd%2fmA%2beIi3HrLXkoJNxKQfs3CYsTGyVjjne6gqzN19lGRlCHks56Qkqa1PEu3nOa%2fpdb%2bV2KHPYI%3d)**).

Một interface được hiểu như là 1 khuôn mẫu mà mọi lớp thực thi nó đều phải tuân theo. Interface sẽ định nghĩa phần “**làm gì**” (khai báo) và những lớp thực thi interface này sẽ định nghĩa phần “**làm như thế nào**” (định nghĩa nội dung) tương ứng.

#### Đặc điểm của interface

-   Chỉ chứa khai báo không chứa phần định nghĩa (giống phương thức thuần ảo). Mặc dù giống phương thức thuần ảo nhưng bạn không cần phải khai báo từ khoá abstract.
-   Việc ghi đè 1 thành phần trong interface cũng không cần từ khoá override.
-   Không thể khai báo phạm vi truy cập cho các thành phần bên trong interface. Các thành phần này sẽ mặc định là public.
-   Interface không chứa các thuộc tính (các biến) dù là hằng số hay biến tĩnh vẫn không được.
-   Interface không có constructor cũng không có destructor.
-   Các lớp có thể thực thi nhiều interface cùng lúc (ở 1 góc độ nào đó có thể nó là phương án thay thế đa kế thừa).
-   Một interface có thể kế thừa nhiều interface khác nhưng không thể kế thừa bất kỳ lớp nào.

#### Mục đích sử dụng interface

-   Vì C# không hỗ trợ đa kế thừa nên interface ra đời như là 1 giải pháp cho việc đa kế thừa này.
-   Trong 1 hệ thống việc trao đổi thông tin giữa các thành phần cần được đồng bộ và có những thống nhất chung. Vì thế dùng interface sẽ giúp đưa ra những quy tắc chung mà bắt buộc các thành phần trong hệ thống này phải làm theo mới có thể trao đổi với nhau được.

## Khai báo và sử dụng interface
### Cú pháp:
>interface <tên interface>
    {
      // Khai báo các thành phần bên trong interface
    }
	
	
Trong đó:

-   **Interface** là từ khoá dùng để khai báo 1 interface.
-   **<tên interface>** là tên do người dùng đặt và tuân theo các quy tắc đặt tên đã trình bày trong bài **[BIẾN TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYH2ztT5H01j3ihV01MA5mug%2bR%2bcFnD0tnOjAuot5NCLyX2%2bh18FBrP0ifRJe8Zg4Kc%3d)**.
    -    **Lưu ý** là để tránh nhầm lẫn với lớp kế thừa thì khi đặt tên interface người ta thường thêm tiền tố “**I**” để nhận dạng.

Việc thực thi 1 interface hoàn toàn giống kế thừa từ 1 lớp (đã trình bày trong bài **[KẾ THỪA TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYGkJZSuYXwQaP8LTTGHNDzS%2fIwOxA38OLjoMrkmPaMB%2bB%2fMj%2b0%2bAY90qv70Dl0ZDyVkesndQWbBGT8rx1LaW0AWZgtpMyTp%2b%2fbyxk8tQ7ARVw%3d%3d)**).

Ví dụ:

````cs
interface ISpeak
    {
        /*
            Khai báo phương thức nhưng không định nghĩa nội dung
         */
        void Speak();
    }

    class Animal : ISpeak // lớp Animal thực thi interface ISpeak
    {
        /*
            Định nghĩa nội dung cho phương thức trong interface
	Phương thức Speak() phải có phạm vi là public vì phương thức Speak() trong interface mặc định là public rồi.
         */
        public void Speak()
        {
            Console.WriteLine("Animal is speaking. . ."); 
        }
    }

````

Trong hàm main ta thử phương thức **Speak()** xem có chạy được không:
````cs
Animal animal = new Animal();

animal.Speak();
````

Kết quả khi chạy chương trình:

````cs
Animal is speaking...
````

Vì việc thực thi interface rất giống với kế thừa nên ta hoàn toàn có thể sử dụng câu lệnh sau:
````cs
ISpeak animal = new Animal();
````

Khi đó chạy lại chương trình vẫn ra kết quả như ban đầu.

Việc thiết kế, sử dụng interface và abstract class chính là cách thể hiện tính trừu tượng trong lập trình hướng đối tượng.

>**Lưu ý**: bạn phải định nghĩa nội dung cho tất cả thành phần trong interface.

## So sánh giữa interface và lớp trừu tượng
Những điểm giống nhau giữa interface và abstract class:

-   Đều có thể chứa phương thức thuần ảo.
-   Đều không thể khởi tạo đối tượng.

Những điểm khác nhau:
![Interface trong Lập trình hướng đối tượng](https://f.howkteam.vn/Upload/cke/images/2_IMAGE%20TUTORIAL/1_C%23_AutoC%23/4_C%23%20H%C6%B0%E1%BB%9Bng%20%C4%91%E1%BB%91i%20t%C6%B0%E1%BB%A3ng%20(OOP)/B07_Interface%20trong%20L%E1%BA%ADp%20tr%C3%ACnh%20OOP/2_Interface%20trong%20L%E1%BA%ADp%20tr%C3%ACnh%20h%C6%B0%E1%BB%9Bng%20%C4%91%E1%BB%91i%20t%C6%B0%E1%BB%A3ng_Howkteam_com.png)

---
## Reference 
[# Bài 7: Interface | HowKteam](https://www.howkteam.vn/course/lap-trinh-oop-voi-c/interface-trong-lap-trinh-huong-doi-tuong-1396)
