
## Class trong C# là gì?
1. Class trong C# chính là cách thể hiện khái niệm về lớp trong lập trình hướng đối tượng.

2. Một class trong C# có các thành phần như:

	+   Thuộc tính: là các thành phần dữ liệu hay còn gọi là các biến.
	+   Phương thức: là các hàm thành phần thể hiện các hành vi của một đối tượng thuộc lớp.
	+   Phương thức khởi tạo.
	+   Phương thức huỷ bỏ.

3. Class trong C# thực chất là một kiểu dữ liệu mới do người dùng tự định nghĩa.
## Khai báo, khởi tạo và sử dụng class trong C#

1. Cú pháp

```` cs
class <tên lớp>
{
	<phạm vi truy cập> <Các thành phần của lớp>
}
````

*Trong đó:*

- <tên lớp> là tên do người dùng đặt và tuân theo quy tắc đặt tên đã trình bày trong bài BIẾN TRONG C#.
- <Phạm vi truy cập> bao gồm các từ khoá như [[public]], [[protected]], [[private]], [[static]],...
- <Các thành phần của lớp> bao gồm các biến, phương thức của lớp.

Ví dụ:

````cs
class Animal
    {
        public double Weight;
        public double Height;

        public void Run()
        {
            Console.WriteLine("Animal is running...");
        }
    }
````

2. Khởi tạo:
- Bạn có thể khởi tạo 1 đối tượng thuộc lớp thông qua toán tử `new`
- Class là kiểu dữ liệu tham chiếu vì thế đối tượng dữ liệu thực sự được lưu trên ==HEAP==
Ví dụ:

````cs
Animal Dog = new Animal()
````

3. Sử dụng:

Ở đây mình muốn tập trung vào cách bạn khai báo và sử dụng phương thức bên trong lớp như thế nào. Xét bài toán đơn giản sau: Khởi tạo các đối tượng thuộc lớp Animal lần lượt gọi phương thức in ra chiều cao và cân nặng của các loài động vật.

```cs
class Animal
    {
        public double Weight;
        public double Height;

        public void Info()
        {
            /*
			  Các phương thức bên trong lớp có thể gọi đến các thành phần khác (bao gồm thuộc tính và phương thức) trong lớp đó.
              Giá trị của các thuộc tính này có thể được khởi tạo đâu đó trong lớp hoặc từ bên ngoài truyền vào.
             */
            Console.WriteLine(" Height: " + Height + " Weight: " + Weight); // Height: 50  Weight: 2 /n Height: 30  Weight: 1
        }
    }
```

trong hàm **main**:
````cs 
	/*
	Khởi tạo 2 đối tượng thuộc lớp Animal là:
	+ Dog có chiều cao 50cm và cân nặng 2kg.
	+ Cat có chiều cao 30cm và cân nặng 1kg.
	*/
            Animal Dog = new Animal();
            Dog.Weight = 2; // gán giá trị cho các thuộc tính của đối tượng
            Dog.Height = 50;


            Animal Cat = new Animal();
            Cat.Weight = 1;
            Cat.Height = 30;


            Dog.Info(); // gọi phương thức của đối tượng
            Cat.Info();
````

*Xuất kết quả*
````cs
Height: 50  Weight: 2 
Height: 30  Weight: 1
````


## Phương thức khởi tạo, phương thức huỷ bỏ (Constructor, Deconstructor)


Trong thế giới thực khi 1 sự vật nào đó được sinh ra thì nó sẽ mang sẵn trong mình những đặc điểm nhất định và mọi sự vật cùng loài với nó đều như vậy.

Vì lập trình hướng đối tượng là phương pháp giúp ánh xạ thế giới thực vào thế giới lập trình một cách dễ dàng nên từ đó đã xuất hiện 2 khái niệm **phương thức khởi tạo** và **phương thức huỷ bỏ** để thể hiện ý trên.

### Phương thức khởi tạo

1. **Phương thức khởi tạo** (Constructor) là những phương thức đặc biệt được gọi đến ngay khi khởi tạo 1 đối tượng nào đó.

2. Có 2 phương thức khởi tạo:
- Phương thức khởi tạo không đối số, là phương thức khởi tạo ko có tham số truyền vào. Thường dùng để khởi tạo cá giá trị mặc định.
- Phương thức khởi tạo có đối số, là phương thức có tham số truyền vào.


Ví dụ:

````cs
class Cat
    {
        public double Weight;
        public double Height;

        /* Constructor không có tham số */
        public Cat()
        {
            Weight = 800;
            Height = 10;
        }

        /* Constructor có tham số*/
        public Cat(int w, int h)
        {
            Weight = w;
            Height = h;
        }

        public void Info()
        {
            Console.WriteLine(" Height: " + Height + " Weight: " + Weight);
        }
    }
````


Trong hàm **main**:

````cs
			/*
			 Để ý khi bạn new Cat bạn không truyền tham số vào thì constructor mặc định (constructor không tham số)
			 sẽ tự động được gọi để khởi tạo các giá trị mặc định cho các thuộc tính của đối tượng BlackCat.
			 */
            Cat BlackCat = new Cat();

            BlackCat.Info(); // In ra thông tin Weight, Height có thực sự được khởi tạo giá trị chưa.

            /*
             Lần này ta khởi tạo đối tượng và có truyền 2 tham số như vậy constructor có tham số sẽ được gọi.
             Như vậy các thuộc tính Weight, Height sẽ không mang giá trị mặc định nữa mà sẽ được gán theo giá trị mà người dùng
             truyền vào.
             */
            Cat WhiteCat = new Cat(1200, 30);
            WhiteCat.Info(); // In ra thông tin Weight, Height để xem có theo mong muốn chưa.
````

Kết quả khi chạy đoạn code trên:

````cs
Height: 10 Weight: 800
Height: 30 Weight: 1200
````


### Phương thức huỷ bỏ

**Phương thức huỷ bỏ** (destructor) là phương thức đặc biệt được gọi đến trước khi 1 đối tượng bị thu hồi.

#### Đặc điểm

-   Có tên trùng với tên lớp nhưng để phân biệt với constructor thì ta thêm dấu “**~**” vào trước tên lớp.
-   Không có kiểu trả về.
-   Được tự động gọi khi 1 đối tượng thuộc lớp kết thúc “vòng đời” của nó thông qua bộ thu dọn rác tự động GC (Garbage Collection).
-   Nếu bạn không khai báo destructor thì C# sẽ tự động tạo ra 1 destructor mặc định và không có nội dung gì.
-   Chỉ có 1 destructor duy nhất trong 1 lớp.

Ví dụ:
````cs
~ Cat()
	{
		Console.WriteLine("Huỷ!") // Huỷ (sau khi kết thúc chạy hàm)
	}
````

## So sánh giữa Struct và Class
Nhìn chung **struct** và **class** có khá nhiều điểm chung nhưng class có phần mạnh hơn. Hãy còn xem tại sao class lại mạnh hơn và mạnh hơn ở điểm nào nhé!

Ngoài ra nếu 1 class là tham số truyền vào thì mọi thay đổi bên trong hàm sẽ tự động cập nhật ra bên ngoài cho dù không có từ khoá out hoặc ref (xem lại bài **[TỪ KHÓA REF VÀ OUT](https://www.howkteam.vn/Course/Khoa-hoc-lap-trinh-C-can-ban/Tu-khoa-ref-va-out-trong-C-96)**) còn struct thì không.

![Class trong Lập trình hướng đối tượng](https://f.howkteam.vn/Upload/cke/images/2_IMAGE%20TUTORIAL/1_C%23_AutoC%23/4_C%23%20H%C6%B0%E1%BB%9Bng%20%C4%91%E1%BB%91i%20t%C6%B0%E1%BB%A3ng%20(OOP)/B02_Class%20trong%20L%C3%A2%CC%A3p%20tri%CC%80nh%20OOP/3_Class%20trong%20L%C3%A2%CC%A3p%20tri%CC%80nh%20h%C6%B0%C6%A1%CC%81ng%20%C4%91%C3%B4%CC%81i%20t%C6%B0%C6%A1%CC%A3ng_Howkteam_com.png)

---
## Reference:
[Bài 2: Class | HowKteam](https://www.howkteam.vn/course/lap-trinh-oop-voi-c/class-trong-lap-trinh-huong-doi-tuong-1370)
