# IT108 - Session 09 - Bài7: Gỡ Lỗi Trang Hướng Dẫn Nộp Bài

## 1. Phần 1: Phân tích các lỗi cú pháp trong đoạn bản thảo

Đoạn mã mẫu của giảng viên chứa các lỗi sai cú pháp cụ thể và hậu quả khi hệ thống hiển thị (render) như sau:

* **Lỗi 1: Dính liền thẻ Heading với văn bản (Thiếu khoảng trắng)**
  * *Vị trí lỗi:* `###Lưu ý quan trọng`
  * *Hậu quả:* Do thiếu dấu cách sau dấu `#` (`### `), hệ thống Markdown không nhận diện đây là thẻ tiêu đề `H3` mà hiển thị nguyên văn chuỗi ký tự này thành văn bản thông thường, làm hỏng cấu trúc phân cấp.
* **Lỗi 2: Sai cú pháp danh sách (List) và định dạng in đậm (Bold)**
  * *Vị trí lỗi:* `-Bước 1: ...` và `**HNKS25CNTT1_IT101_Session08`
  * *Hậu quả:* 
    * Danh sách `-Bước 1:` thiếu dấu cách sau dấu gạch ngang (`- `), khiến trình duyệt giữ nguyên dạng chữ thường thay vì hiển thị thành danh mục gạch đầu dòng (bullet list).
    * Thẻ in đậm mở bằng `**` nhưng thiếu dấu `**` đóng ở cuối tên lớp, khiến toàn bộ các đoạn văn bản liền sau bị lỗi hiển thị định dạng.
* **Lỗi 3: Lỗi cú pháp liên kết (Link Syntax)**
  * *Vị trí lỗi:* `[GitHub]( [github.com](http://github.com/) )`
  * *Hậu quả:* Cấu trúc lồng ghép thừa khoảng trắng và định dạng không chuẩn khiến hệ thống trình duyệt không thể thiết lập siêu liên kết dẫn đến trang đích.
* **Lỗi 4: Lỗi định dạng chữ nghiêng, trích dẫn và thẻ đóng**
  * *Vị trí lỗi:* `*Portal*`, `*> Deadline: ...` và `*Nộp muộn sẽ bị trừ 50% điểm!**`
  * *Hậu quả:* Các thẻ định dạng bị sai lệch hoặc thiếu khép kín (ví dụ: mở bằng một dấu sao `*` nhưng đóng bằng hai dấu sao `**`), khiến kết quả render bị lỗi font chữ và khối trích dẫn.

---

## 2. Phần 2: Sửa lỗi cú pháp và Hoàn thiện mã nguồn

### 1. Đoạn mã Markdown đã sửa đúng chuẩn
```markdown
## Hướng Dẫn Nộp Bài Tập - Session 08

### Lưu ý quan trọng

Các bước nộp bài:
- Bước 1: Tạo tài khoản GitHub tại [GitHub](https://github.com)
- Bước 2: Tạo repository mới đặt tên theo định dạng **HNKS25CNTT1_IT101_Session08**
- Bước 3: Upload file .md của bài làm lên repository
- Bước 4: Copy đường dẫn và nộp lên *Portal*

> **Deadline:** Chủ nhật 23:59 — *Nộp muộn sẽ bị trừ 50% điểm!*