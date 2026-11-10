# BÀI LÀM –(CHỦ ĐỀ QUẢN LÝ MODEL AI)

- **Mã đề:**
- **Họ tên:** Nguyễn Vũ Long
- **Lớp:** HN-KS26-CNTT3
- **Link repository:** [GitHub](https://github.com/vulong1712/HN-KS26-CNTT3-Nguyen_Vu_Long-SS23-Test)
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -Force
mv .\tai_lieu_ban_giao.txt .\docs\
mkdir backup
cp .\data\chi_phi_model_thang_11.xlsx .\backup\
rm -r .\model_cache_01.tmp
cd .\logs\
ls -Force
cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text

    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/11/2026   1:49 PM                backup
d-----        10/11/2026   1:50 PM                data
d-----        10/11/2026   1:49 PM                docs
d-----        10/11/2026   1:44 PM                evidence
d-----        10/11/2026   1:50 PM                logs
d-----        10/11/2026   1:42 PM                web
-a----        10/11/2026   1:42 PM             96 .env
-a----        10/11/2026   1:54 PM           2808 bai_lam.md


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/11/2026   1:42 PM           5815 chi_phi_model_thang_11.xlsx


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/11/2026   1:42 PM           5815 chi_phi_model_thang_11.xlsx


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/11/2026   1:42 PM            204 tai_lieu_ban_giao.txt


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/11/2026   1:42 PM           1234 inference.log


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/11/2026   1:42 PM                images
-a----        10/11/2026   1:42 PM            644 app.js
-a----        10/11/2026   1:42 PM            567 index.html
-a----        10/11/2026   1:42 PM            460 style.css


    Directory: D:\BAI-TAP-THUC-HANH-CUA-VU-LONG\nhap_mon_cong_nghe_thong_tin\MiniPrjoect\starte
    r-kit\quan-ly-model-ai\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/11/2026   1:42 PM            339 logo-ai-hub.png


```

## 4.3. Lọc log vận hành Model AI

### a) Lệnh lọc các dòng ERROR

```shell
Get-Content .\logs\inference.log | Select-String "ERROR">.\logs\loi_model.txt
```

### 2 dòng đầu tiên trong logs/loi_model.txt

```text

2026-11-10 08:27:45 ERROR POST /v1/chat/completions model=CLAUDE-35
2026-11-10 08:31:12 ERROR POST /v1/audio/transcriptions model=WHISPER-V3

```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
(Get-Content .\logs\inference.log | Select-String "WARNING").Count
```

```text
5
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO VAN HANH MODEL AI ===

2026-11-10 08:09:18 WARNING POST /v1/embeddings model=LLAMA-2-OLD
2026-11-10 08:16:05 WARNING GET /v1/fine-tune/jobs-legacy
2026-11-10 08:38:29 WARNING GET /images/model-card-v1.png
2026-11-10 09:01:44 WARNING POST /v1/completions model=DAVINCI-002
2026-11-10 09:14:02 WARNING GET /v1/quota/expired-key


6


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [X] README.md: Heading 1, hình ảnh (`![Alt](path)`), mô tả có **in đậm**, _in nghiêng_ và `inline code`, bảng, code block, task list, blockquote
- [X] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [X] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |               NetWork             |             Tên logo bị sai                |       Sửa lại đường dẫn của logo         |
| 2   |                      Console      |                  Sai đường dẫn cuối            |        Sửa lại đường dẫn cuối ở file app.js        |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** Không hiện hình ảnh logo và bảng dữ liệu trong index.html
- **Expected:** Sửa được lỗi, Developer Tools không báo lỗi
- **Actual:** Lỗi chưa được sửa, file logo hiện hình ảnh lỗi và không hiển thị bảng dữ liệu trên web
- **Log:** GET file:///D:/BAI-TAP-THUC-HANH-CUA-VU-LONG/nhap_mon_cong_nghe_thong_tin/MiniPrjoect/starter-kit/quan-ly-model-ai/web/images/logo-ai-hu.png net::ERR_FILE_NOT_FOUND
app.js:18 Uncaught ReferenceError: hienThiBangModel is not defined

### Câu tìm kiếm Google

```text
site:stackoverflow.com "ERR_FILE_NOT_FOUND"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/chi_phi_model_thang_11.xlsx`, không cần ghi vào đây.
