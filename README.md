# Bank Marketing Machine Learning Lab

Dự án nghiên cứu và xây dựng mô hình học máy (Machine Learning) dựa trên bộ dữ liệu **Bank Marketing** (UCI Machine Learning Repository).

## Giới thiệu dữ liệu
Dữ liệu liên quan đến các chiến dịch tiếp thị trực tiếp (qua điện thoại) của một tổ chức ngân hàng Bồ Đào Nha. Mục tiêu phân loại là dự đoán xem khách hàng có đăng ký tiền gửi có kỳ hạn hay không (biến mục tiêu `y`: `yes` / `no`).

Bộ dữ liệu bao gồm:
- **bank-additional-full.csv**: Gồm 41.188 bản ghi và 20 thuộc tính đầu vào, được sắp xếp theo thời gian (từ 05/2008 đến 11/2010).
- **bank-full.csv**: Phiên bản với 45.211 bản ghi và 17 thuộc tính đầu vào.
- Các tập dữ liệu mẫu nhỏ hơn (10%) để phục vụ thử nghiệm nhanh (`bank-additional.csv`, `bank.csv`).

## Cấu trúc thư mục
```text
bank-marketing-ml-lab/
├── bank+marketing/
│   ├── bank/
│   │   ├── bank-full.csv
│   │   ├── bank.csv
│   │   └── bank-names.txt
│   └── bank-additional/
│       └── bank-additional/
│           ├── bank-additional-full.csv
│           ├── bank-additional.csv
│           └── bank-additional-names.txt
├── requirements.txt
├── .gitignore
└── README.md
```

## Cài đặt môi trường
Khởi tạo và kích hoạt môi trường ảo:
```bash
python -m venv .venv
# Trên Windows:
.venv\Scripts\activate
# Trên Linux/macOS:
source .venv/bin/activate
```

Cài đặt các thư viện phụ thuộc:
```bash
pip install -r requirements.txt
```
