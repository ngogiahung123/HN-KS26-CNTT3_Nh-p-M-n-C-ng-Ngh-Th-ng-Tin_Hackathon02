# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Ngô Gia Hưng
- **Lớp:** CNTT3
- **Link repository:** https://github.com/ngogiahung123/HN-KS26-CNTT3_Nh-p-M-n-C-ng-Ngh-Th-ng-Tin_Hackathon02
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv .\lich_lam_viec.txt .\docs
mkdir backup
cp .\data\hoa_don_spa_thang_7.xlsx .\backup
rm .\temp_707.tmp
cd .\logs
ls
cd ..
ls -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

    Directory: C:\Thi\starter-kit\spa-website


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
d-----        11/11/2026  10:52 SA                backup                        
d-----        11/11/2026  10:48 SA                data                          
d-----        11/11/2026  10:51 SA                docs                          
d-----        11/11/2026  10:45 SA                evidence                      
d-----        11/11/2026  10:48 SA                logs                          
d-----        03/11/2026   7:07 SA                web                           
-a----        03/11/2026   7:07 SA             75 .env                          
-a----        03/11/2026   7:07 SA           2412 bai_lam.md                    


    Directory: C:\Thi\starter-kit\spa-website\backup


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
-a----        03/11/2026   7:07 SA           6149 hoa_don_spa_thang_7.xlsx      


    Directory: C:\Thi\starter-kit\spa-website\data


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
-a----        03/11/2026   7:07 SA           6149 hoa_don_spa_thang_7.xlsx      


    Directory: C:\Thi\starter-kit\spa-website\docs


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
-a----        03/11/2026   7:07 SA            149 lich_lam_viec.txt             


    Directory: C:\Thi\starter-kit\spa-website\logs


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
-a----        03/11/2026   7:07 SA            939 service.log                   


    Directory: C:\Thi\starter-kit\spa-website\web


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
d-----        03/11/2026   7:07 SA                images                        
-a----        03/11/2026   7:07 SA            597 app.js                        
-a----        03/11/2026   7:07 SA            523 index.html                    
-a----        03/11/2026   7:07 SA            460 style.css                     


    Directory: C:\Thi\starter-kit\spa-website\web\images


Mode                 LastWriteTime         Length Name                          
----                 -------------         ------ ----                          
-a----        03/11/2026   7:07 SA           3091 logo-lotuscare.png            

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Get-Content .\logs\service.log | Select-String "status=500" > .\logs\loi_500.txt    
Get-Content .\logs\loi_500.txt -head 2

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:12:50 POST /api/dat-lich status=500
2026-07-28 08:19:23 POST /api/dat-lich status=500

```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-Content .\logs\service.log | Select-String "status=404").count

```

```text
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-07-28 08:16:12 GET /images/phong-spa-3.jpg status=404
2026-07-28 08:39:18 GET /uu-dai-cu status=404
2026-07-28 08:46:40 GET /tin-tuc status=404
2026-07-28 08:48:51 GET /tin-tuc status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 

```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Console | app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined | Thay đúng tên gọi ra là hienThiGoiSpa |
| 2 | Netword | logo.png | Điền lại đường liên kết đúng |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Tôi là sinh viên năm nhất tôi không biết cách sửa lỗi 
- **Expected:** Hãy sửa lỗi giúp tôi trong phần Console để hiển thị bảng
- **Actual:** Khi không thấy bảng tôi bấm F12 và phát hiện lỗi này app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined
- **Log:** app.js:18 Uncaught ReferenceError: hienThiGoiDichVu is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught Referenceerror"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
