# Quản Lý Dữ Liệu (Data Management)

Tài liệu hướng dẫn tổ chức, quản lý và sử dụng dữ liệu trong dự án `bank-marketing-ml-lab`.

---

## 1. Nguồn Gốc và Phiên Bản Dữ Liệu
- **Nguồn:** [UCI Machine Learning Repository - Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing)
- **Tác giả:** S. Moro, P. Cortez and P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, June 2014.
- **Mô tả:** Dữ liệu liên quan đến các chiến dịch tiếp thị qua điện thoại của một tổ chức ngân hàng Bồ Đào Nha.

---

## 2. Cấu Trúc Thư Mục Dữ Liệu

- **`data/source/`**: Lưu trữ tệp lưu trữ gốc (`bank+marketing.zip`) và thư mục trích xuất nguyên bản (`extracted/bank+marketing/`). Đây là nguồn tham chiếu bất biến (immutable) để đối chiếu và xác thực.
- **`data/raw/`**: Chứa tệp dữ liệu phân tích chính được sao chép trực tiếp từ nguồn, không qua chỉnh sửa cấu trúc hay nội dung.
- **`data/reference/`**: Chứa các tệp mô tả thuộc tính, tài liệu ghi chú dữ liệu từ nguồn gốc (`bank-additional-names.txt`).

---

## 3. Tập Dữ Liệu Mặc Định
- **Tập dữ liệu chính được sử dụng:** `data/raw/bank-additional-full.csv`
  - Số dòng: **41.188** bản ghi
  - Số cột: **21** cột (20 đặc trưng đầu vào + 1 cột nhãn mục tiêu `y`)
  - Ký tự phân cách (delimiter): dấu chấm phẩy (`;`)
  - Nhãn mục tiêu `y`: `yes` (khách hàng đồng ý gửi tiết kiệm kỳ hạn) hoặc `no` (từ chối).
  
*Lưu ý:* Dự án sử dụng `bank-additional-full.csv` (chứa đầy đủ các thuộc tính kinh tế vĩ mô và thời gian) làm tập dữ liệu chuẩn, không sử dụng `bank-full.csv`.

---

## 4. Cách Tái Tạo Dữ Liệu Từ ZIP Nguồn
Trong trường hợp cần tái tạo lại dữ liệu:
1. Giải nén `data/source/bank+marketing.zip` vào thư mục tạm hoặc `data/source/extracted/`.
2. Tiếp tục giải nén `bank-additional.zip` nằm bên trong.
3. Sao chép tệp `bank-additional-full.csv` vào `data/raw/`.
4. Sao chép tệp `bank-additional-names.txt` vào `data/reference/`.

---

## 5. Đường Dẫn Dữ Liệu Được Sử Dụng Bởi Chương Trình
Tất cả các script trong `src/` và notebook trong `notebooks/` phải truy cập dữ liệu chính thông qua đường dẫn tương đối:
```python
DATA_PATH = "data/raw/bank-additional-full.csv"
```
Khi đọc bằng pandas:
```python
import pandas as pd
df = pd.read_csv("data/raw/bank-additional-full.csv", sep=";")
```

---

## 6. Lưu Ý Quan Trọng Về Biến `duration`
- Biến `duration` biểu thị thời lượng cuộc gọi gần nhất tính bằng giây.
- **Cảnh báo về Data Leakage (Rò rỉ dữ liệu):** Thuộc tính này chỉ được biết sau khi cuộc gọi đã kết thúc. Nếu mục tiêu là xây dựng mô hình dự đoán khả thi trước khi thực hiện cuộc gọi (nhằm ưu tiên danh sách khách hàng tiềm năng), biến `duration` **không được phép sử dụng** làm biến đầu vào vì nó không tồn tại tại thời điểm ra quyết định.

