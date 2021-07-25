## Đặc điểm của thành viên tĩnh 

> *Cô đọng: Static là một vùng nhớ liên,  khởi tạo 1 lần duy nhất và huỷ khi kết thúc chương trình. Gọi nó thông qua tên lớp.*

Bình thường các thuộc tính, phương thức sẽ có đặc điểm:

-   Chỉ có thể sử dụng sau khi khởi tạo đối tượng.
-   Dữ liệu thuộc về riêng mỗi đối tượng (xét cùng 1 thuộc tính thì các đối tượng khác nhau thì thuộc tính đó sẽ mang các giá trị khác nhau).
-   Được gọi thông qua tên của đối tượng.

Đôi lúc người lập trình mong muốn 1 thuộc tính nào đó được dùng chung cho mọi đối tượng (*chỉ được cấp phát 1 vùng nhớ duy nhất*). Từ đó khái niệm **thành viên tĩnh (*) ** ra đời.

Đặc điểm của thành viên tĩnh:

-   Được khởi tạo **1 lần duy nhất** ngay khi biên dịch chương trình.
-   Có thể **dùng chung** cho mọi đối tượng.
-   **Được gọi thông qua tên lớp**.
-   Được **huỷ khi kết thúc** chương trình.

Có 4 loại thành viên tĩnh chính:
-   thành viên tĩnh (static variable).
-   Phương thức tĩnh (static method).
-   Lớp tĩnh (static class).
-   Phương thức khởi tạo tĩnh (static constructor).

Để khai báo 1 **thành viên tĩnh** ta sử dụng từ khoá **static** đặt trước tên biên, tên phương thức hoặc tên lớp. Chi tiết sẽ được trình bày ngày sau đây.

## Biến tĩnh ()

### Cú pháp:
> **<phạm vi truy cập> static <kiểu dữ liệu> <tên biến> = <giá trị khởi tạo>;**

Trong đó:

-   **<phạm vi truy cập>** là các phạm vi đã trình bày trong bài **[CÁC LOẠI PHẠM VI TRUY CẬP TRONG C# OOP](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0h2RqtQXOCMMjSu5ZylZ2jUhs6uVeDQ7NOG2FhEaM63rXgWHBHu%2fU19BPtFdYX%2bHfwowZk2jwJM25P7gl4%2fNgkIWIIsOM%2biTdFuFXlcl1g7Nzegc34IVz%2f7TKbG75UDt3%2fVSJ6tl0tnrTbFZ31GNV45f17IQU7qdNn7NmMhzqMO7)**
-   **static** là từ khoá để khai báo thành viên tĩnh.
-   **<kiểu dữ liệu>** là kiểu dữ liệu của biến (đã được trình bày trong bài **[KIỂU DỮ LIỆU TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0jVmllsXWQo7b4H81o5di3E%2fwVj10QgA%2bTJG2s4vOi1C)**).
-   **<tên biến>** là tên biến do người dùng đặt và tuân thủ các quy tắc đặt tên biến (các quy tắc đặt tên biến đã trình bày trong bài **[BIẾN TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYH2ztT5H01j3ihV01MA5mug%2bR%2bcFnD0tnOjAuot5NCLyX2%2bh18FBrP0ifRJe8Zg4Kc%3d)**).
-   **<giá trị khởi tạo>** là giá trị ban đầu mà biến tĩnh này chứa. Nếu bạn không khai báo giá trị này thì C# thì tự gán giá trị mặc định và đưa ra 1 cảnh báo khi bạn biên dịch chương trình.

Bạn có thể hiểu **biến tĩnh** là:

-   Một biến dùng chung cho mọi đối tượng thuộc lớp.
-   Nó được khởi tạo vùng nhớ 1 lần duy nhất ngay khi chương trình được nạp vào bộ nhớ để thực thi và huỷ khi kết thúc chương trình.

Ngoài biến tĩnh ra thì hằng số cũng có thể được gọi thông qua tên lớp và không cần khởi tạo đối tượng nhưng biến tĩnh linh hoạt hơn đó là có thể thay đổi giá trị khi cần thiết.

Về cách sử dụng thì bạn thao tác hoàn toàn giống 1 biến bình thường chỉ cần lưu ý là phải gọi biến này thông qua tên lớp.

Ví dụ:
Ta muốn quản lý số lượng mèo đang có (giả sử 1 đối tượng được tạo ra là 1 con mèo)

````cs
class Cat
    {
        private int weight;
        /*
            Khai báo property tương ứng với thuộc tính.
            Mặc dù trong bài này mình không sử dụng tới nhưng mình vẫn khai báo để nhắc các bạn nhớ tuân thủ tính đóng gói.
         */
        public int Weight
        {
            get { return weight; }
            set { weight = value; }
        }
        private int height;
        public int Height
        {
            get { return height; }
            set { height = value; }
        }

        /*
            Khai báo 1 biến static tên Count để chứa số lượng mèo hiện tại.
            Mỗi lần có 1 đối tượng được tạo ra thì ta sẽ tăng Count lên.
        */

        public static int Count = 0;
     
        public Cat()
        {
            weight = 20;
            height = 500;
            /* Vì constructor chỉ được gọi khi có đối tượng được tạo ra nên ta sẽ tăng Count ở đây */
            Count++;
        }
    }
````

Trong hàm **main**: (tìm hiểu thêm về [[Instance]])

````cs
Console.WriteLine(" So luong meo ban dau: " + Cat.Count);
Cat BlackCat = new Cat(); // Tạo ra con mèo đầu tiên, BlackCat là 1 intance của Cat

Console.WriteLine(" So luong meo hien tai: " + Cat.Count);

Cat WhiteCat = new Cat(); // Tạo ra con mèo thứ 2, WhiteCat là 1 intance của Cat
Console.WriteLine(" So luong meo hien tai: " + Cat.Count);
````

Kết quả khi chạy đoạn code trên:

````cs
So luong meo ban dau: 0
So luong meo hien tai: 1
So luong meo hien tai: 2
````


## Phương thức tĩnh (static method)

### Cú pháp:

> **<phạm vi truy cập> static <kiểu trả về> <tên phương thức>**
{
 **// nội dung phương thức**
}

Trong đó:

-   **<phạm vi truy cập>** là các phạm vi đã trình bày trong bài [[Các loại phạm vi truy cập trong C Sharp]]
-   **static** là từ khoá để khai báo thành viên tĩnh.
-   **<kiểu trả về>** là kiểu trả về của phương thức (đã được trình bày trong bài **[HÀM TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0lthogs3xmFNd%2fmA%2beIi3HpefwGKmQoUyVOvzTYLwXwPFagHBQLWvFb%2feOJ6eoualVCqox5kJrTVoIcHe3GhjUVq%2fXiBziny%2b%2bjN2MluidbV)**).
-   **<tên phương thức>** là tên do người dùng đặt và tuân thủ các quy tắc đặt tên (các quy tắc đặt tên đã trình bày trong bài **[BIẾN TRONG C#](https://www.howkteam.vn/redirect?Id=Y%2fHKZv6fbvNJnzXtx4Ic0rZRqPOVzQSxG20E6RGIOYH2ztT5H01j3ihV01MA5mug%2bR%2bcFnD0tnOjAuot5NCLyX2%2bh18FBrP0ifRJe8Zg4Kc%3d)**).

**Hàm tĩnh** được sử dụng với 2 mục đích chính:

-   Hàm tĩnh là 1 hàm dùng chung của lớp. Được gọi thông qua tên lớp và không cần khởi tạo bất kỳ đối tượng nào, từ đó tránh việc lãng phí bộ nhớ.
-   Hỗ trợ trong việc viết các hàm tiện ích để sử dụng lại.

Về sử dụng thì bạn thao tác hoàn toàn giống 1 phương thức bình thường chỉ cần lưu ý là phải gọi phương thức này thông qua tên lớp.

### Ví dụ:
Bạn viết 1 hàm tiện ích đó là tính luỹ thừa của 1 số nguyên để hỗ trợ tính toán.

````cs
class TienIch
    {
        /*
            Khai báo và định nghĩa 1 phương thức tính luỹ thừa 2 số nguyên
         */

        public static long LuyThua(int CoSo, int SoMu)
        {
            long KetQua = 1;
            for (int i = 0; i < SoMu; i++)
            {
                KetQua *= CoSo;
            }

            return KetQua;
        }
    }
````

Trong hàm **main** ta thử gọi phương thức này ra dùng thử:

````cs
/*
Gọi phương thức thông qua tên lớp và không cần khởi tạo đối tượng.
*/
Console.WriteLine(TienIch.LuyThua(3, 3));


````

Kết quả khi chạy chương trình trên:

````cs
27
````

## Lớp tĩnh
### Cú pháp:
> **<phạm vi truy cập> static class <tên lớp>**
{
                    **// các thành phần của lớp**
}

Trong đó:

-   **<phạm vi truy cập>** là các phạm vi đã trình bày trong bài **[[Các loại phạm vi truy cập trong C Sharp]]**.
-   **static** là từ khoá để khai báo thành viên tĩnh.
-   **class** là từ khoá để khai báo lớp.
-   **<tên lớp>** là tên do người dùng đặt và tuân thủ các quy tắc đặt tên (các quy tắc đặt tên đã trình bày trong bài **[BIẾN TRONG C#](https://www.howkteam.vn/Course/Khoa-hoc-lap-trinh-C-can-ban/Bien-trong-C-52)**).


### Lớp tĩnh có các đặc điểm

-   Chỉ chứa các thành phần tĩnh (biến tĩnh, phương thức tĩnh).
-   **Không** thể khai báo, khởi tạo 1 đối tượng thuộc lớp tĩnh.

Với 2 đặc điểm trên có thể thấy lớp tĩnh thường được dùng với mục đích khai báo 1 lớp tiện ích chứa các hàm tiện ích hoặc hằng số vì:

-   Ràng buộc các thành phần bên trong lớp phải là **static**.
-   Không cho phép tạo ra các đối tượng dư thừa làm lãng phí bộ nhớ.
-   Mọi thứ đều được truy cập thông qua tên lớp.

Xét lại ví dụ trong phần hàm tĩnh. Rõ ràng là người có thể vô ý tạo ra đối tượng thuộc **TienIch**. Đối tượng này khá vô nghĩa vì không có gì để sử dụng. Để tránh điều này ta thêm từ khoá **static** vào trước khai báo lớp.

Trong C# có rất nhiều lớp tiện ích sử dụng lớp tĩnh, phương thức tĩnh để khai báo. Ví dụ điển hình đó là lớp **Math**.

Lớp **Math** chứa:

-   Các hằng số nhứ **PI**, **E**.
-   Các phương thức hỗ trợ tính toán như: **sin**, **cos**, **tan**, **sqrt**, **exp**, . . .

Bạn có thể tự khám phá chúng bằng cách gõ “**Math.**” để xem các thành phần của lớp **Math**.

![Từ khóa Static trong Lập trình hướng đối tượng](https://f.howkteam.vn/Upload/cke/images/2_IMAGE%20TUTORIAL/1_C%23_AutoC%23/4_C%23%20H%C6%B0%E1%BB%9Bng%20%C4%91%E1%BB%91i%20t%C6%B0%E1%BB%A3ng%20(OOP)/B04_T%C6%B0%CC%80%20kho%CC%81a%20Static%20trong%20L%C3%A2%CC%A3p%20tri%CC%80nh%20OOP/3_T%C6%B0%CC%80%20kho%CC%81a%20Static%20trong%20L%C3%A2%CC%A3p%20tri%CC%80nh%20h%C6%B0%C6%A1%CC%81ng%20%C4%91%C3%B4%CC%81i%20t%C6%B0%C6%A1%CC%A3ng_Howkteam_com.png)


## Phương thức khởi tạo tĩnh
### Cú pháp:

> **static <tên lớp>()**
{
                        **// nội dung của constructor**
}

Trong đó:

-   **static** là từ khoá để khai báo thành viên tĩnh.
-   **<tên lớp>** là tên của lớp chứa constructor này.

### Đặc điểm của constructor tĩnh
-   **Không được phép** khai báo phạm vi truy cập. Nếu cố tình làm điều này C# sẽ báo lỗi khi biên dịch.
-   Constructor tĩnh sẽ **được gọi 1 lần duy nhất** khi chương trình được nạp vào bộ nhớ để thực thi như là 1 cách để ta thiết lập một số thông số theo ý muốn trước khi có bất kỳ đối tượng nào được tạo ra.
-   Constructor tĩnh cũng giống phương thức tĩnh nên không thể gọi các thuộc tính không phải static.

Ví dụ: Giả sử như bạn có 1 biến tĩnh chỉ định màu sắc chủ đạo của ngày và màu sắc chủ đạo này phụ thuộc vào hôm nay là thứ mấy.
-   Thứ 2: màu xanh dương
-   Thứ 3: màu đỏ
-   Thứ 4: màu tím
-   Thứ 5: màu hồng
-   Thứ 6: màu đen
-   Thứ 7: màu xanh lá
-   Chủ nhật: màu vàng

Rõ ràng là bạn mong muốn khởi tạo giá trị cho biến tĩnh này nhưng:
-   Không thể khởi tạo bằng cách gán trực tiếp như thế này:

````cs
public static string MauChuDao = "Red";
````

Vì ngoài màu đỏ ra thì còn có màu tím và màu này phụ thuộc vào ngày hiện tại.

-   Không thể khởi tạo biến tĩnh này trong **constructor** bình thường được. Vì **constructor** bình thường chỉ được gọi khi có đối tượng được khởi tạo.

Trường hợp này thì **constructor tĩnh** là 1 giải pháp đơn giản nhưng hiệu quả.

````cs
class MauSac
    {
        /* Giả sử màu chủ đạo là 1 chuỗi ký tự lưu tên màu tương ứng */
        public static string MauChuDao;
        /* Dùng static constructor để kiểm tra ngày hiện tại và khởi tạo giá trị cho biến tĩnh MauChuDao */
        static MauSac()
        {
            /* Khai báo đối tượng ngày giờ và lấy ngày giờ hiện tại của hệ thống */
            DateTime now = DateTime.Now;

            /* lấy ra thứ của ngày hiện tại và so sánh với 7 ngày trong tuần */
            switch (now.DayOfWeek)
            {
                case DayOfWeek.Friday:
                    MauChuDao = "Black";
                    break;
                case DayOfWeek.Monday:
                    MauChuDao = "Blue";
                    break;
                case DayOfWeek.Saturday:
                    MauChuDao = "Green";
                    break;
                case DayOfWeek.Sunday:
                    MauChuDao = "Yellow";
                    break;
                case DayOfWeek.Thursday:
                    MauChuDao = "Pink";
                    break;
                case DayOfWeek.Tuesday:
                    MauChuDao = "Red";
                    break;
                case DayOfWeek.Wednesday:
                    MauChuDao = "Purple";
                    break;
            }
        }
    }


````

Trong hàm **main** ta thử kiểm tra xem bằng cách gọi thuộc tính MauChuDao ra:

````cs
/* In ra màn hình giá trị của thuộc tính màu chủ đạo */
Console.WriteLine(" Mau chu dao cua hom nay: " + MauSac.MauChuDao);
````

Kết quả khi chạy đoạn code trên:

-   Hôm nay đang là 04/02/2017 – Thứ 7

````cs
Mau chu dao cua hom nay: Green
````
---
# Reference
[Từ khóa Static trong Lập trình hướng đối tượng](https://www.howkteam.vn/course/lap-trinh-oop-voi-c/tu-khoa-static-trong-lap-trinh-huong-doi-tuong-1374)

---

(*) thành viên tĩnh = biến tĩnh