# Level-08-Con-Tro-Dong
**Đoàn Thị Ngọc Lan**
**Báo cáo học Chuỗi ký tự**
=======================

## I.KHÁI NIỆM.
  + **Thế nào là một biến động??**
  
    > * Là các biến được tạo ra lúc chạy chương trình, tùy theo nhu cầu. Do vậy, mà số
biến này hoàn toàn không được xác định từ trước. Các biến được tạo ra như vậy
được gọi là các biến động. Các biến động không có tên .

  + **Các tạo và truy cập**
  
    > * Việc tạo ra biến động và xóa nó đi (để thu hồi lại bộ nhớ) được thực hiện nhờ các
hàm như malloc() và free() đã có sẵn trong stdlib.h
    > * Việc truy nhập đến biến động được tiến hành nhờ các biến con trỏ. Các biến con
trỏ được định nghĩa như các biến tĩnh và được dùng để chứa địa chỉ các biến động.
  
### II. CẤP PHÁT VÀ GIẢI PHÓNG BỘ NHỚ ĐỘNG.

   **1.Cấp phát bộ nhớ động bằng hàm malloc().**
   
   + Cú pháp:
   
      > `void *malloc(size_t size)`
    
      > * **Chức năng** : cấp phát một vùng nhớ có kích thước là size. 
    
      > - **Trong đó**:
          * size là một giá trị kiểu size_t (là một kiểu dữ liệu định sẵn
trong thư viện stdlib.h, ta có thể khai báo kiểu unsigned
cũng được).
          * Hàm này trả về con trỏ kiểu void chứa địa chỉ ô nhớ đầu
của vùng nhớ được cấp phát. Nếu không đủ vùng nhớ để
cấp phát nó sẽ trả về giá trị **NULL** , vì vậy ta phải kiểm tra
giá trị trả về khi sử dụng hàm malloc.
        
   + Ví dụ :
   
    ```
    # include <stdlib.h>
    # include <conio.h>
    void main ()
    {
      int *num;
      num=(int*)malloc(50*sizeof(int));
      if (num==NULL)
    {
      printf("Khong du bo nho");
    }
      printf("Bo nho da duoc cap phat");
    }
    ```  


   **2.Cấp phát bộ nhớ động bằng hàm calloc().**
   
   + Cú pháp:
   
      > `(datatype *) calloc(n, sizeof(object));`
    
      > * **Chức năng** : cấp phát bộ nhớ động cho các kiểu dữ liệu 
    
      > - **Trong đó**:
          * datatype *) là kiểu con trỏ trỏ tới kiểu dữ liệu datatype.
          * n là số lượng object thuộc kiểu datatype mà ta cần cấp phát bộ nhớ.
          * Kiểu datatype có thể là những kiểu dữ liệu mới do người lập trình
          sáng tạo ra
        
   + Ví dụ :
   
   
    
    ```
    #include <stdio.h> 
    #include <alloc.h>   
    #include <string.h> 
    int main(void)   
     {
      char *str = NULL;
      str = (char *) calloc(30, sizeof(char));  
      strcpy(str, "DoanThiNgocLan");  
      printf("Chuỗi ký tự là %s\n", str);       
      free(str);     
      return 0;  
      }
     ```  
     
    **3.Cấp phát bộ nhớ động bằng hàm  relloc().**  
    
     + Cú pháp:
   
      > `(datatype *) realloc(buf _p, newsize);`
    
      > * **Chức năng** : Hàm cấp phát lại bộ nhớ 
    
      > - **Trong đó**:
          * buf_p là con trỏ đang trỏ đến vùng ô nhớ đã được cấp phát từ trước.
          * newsize là kích thước mới cần cấp phát, có thể to hoặc nhỏ hơn.
         
   + Ví dụ :
   
   
    
    ```
    #include <stdio.h>
    #include <alloc.h>
    #include <string.h>
    int main(void)
    {
    char *str;
    str = (char *) malloc(10);
    strcpy(str, "Hello");
    printf("Chuỗi ký tự là %s\n Ðịa chỉ là %p\n", str, str);
    str = (char *) realloc(str, 20);
    printf("Chuỗi ký tự là %s\n Ðịa chỉ mới là %p\n", str, str);
    free(str);
    return 0;
    }
     ``` 
     
=============================================================
     
     
     
                                     **KẾT THÚC**
    
     

    
     
    


          
      
    
   
   
   
   
      

