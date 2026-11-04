# Bank Marketing Machine Learning Lab

Dự án thực hành và nghiên cứu Machine Learning từ nền tảng đến nâng cao, dựa trên bộ dữ liệu **Bank Marketing** từ UCI Machine Learning Repository.

---

## 1. Mục Tiêu Học Tập
- Nắm vững các khái niệm nền tảng: **Underfitting**, **Overfitting**, **Bias–Variance Tradeoff**, **Regularization**, **Gradient Descent** và **Model Generalization**.
- Thực hành chuẩn chỉnh các kỹ thuật: **Data Preprocessing**, **Cross-Validation**, **Hyperparameter Tuning** và **Model Evaluation**.
- Xây dựng một dự án Machine Learning bài bản, chuẩn kỹ thuật phần mềm (Software Engineering) để đưa vào CV chuyên nghiệp.

---

## 2. Mô Tả Bài Toán
- **Loại bài toán:** Phân loại nhị phân (Binary Classification).
- **Mục tiêu:** Dự đoán xem khách hàng có đăng ký mở tài khoản tiền gửi có kỳ hạn (*term deposit*) hay không thông qua các chiến dịch tiếp thị trực tiếp qua điện thoại.
- **Biến mục tiêu (`y`):** Nhận giá trị `yes` (khách hàng đồng ý đăng ký) hoặc `no` (từ chối).

---

## 3. Nguồn Dữ Liệu
- **Nguồn gốc:** [UCI Machine Learning Repository - Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing).
- **Tập dữ liệu chuẩn của dự án:** `data/raw/bank-additional-full.csv` gồm **41.188 dòng** và **21 cột** (20 đặc trưng + 1 nhãn mục tiêu), chứa đầy đủ các chỉ số kinh tế vĩ mô và lịch sử liên lạc.

---

## 4. Hướng Dẫn Thiết Lập Môi Trường

Khởi tạo và kích hoạt môi trường ảo:
```bash
# Tạo môi trường ảo
python -m venv .venv

# Kích hoạt trên Windows (PowerShell):
.venv\Scripts\Activate.ps1

# Kích hoạt trên Linux/macOS:
source .venv/bin/activate
```

Cài đặt các gói thư viện cần thiết:
```bash
pip install -r requirements.txt
```

---

## 5. Cấu Trúc Repository

```text
bank-marketing-ml-lab/
├── .gitignore               # Cấu hình bỏ qua các tệp môi trường, cache và tạm
├── AGENTS.md                # Quy tắc và hướng dẫn hoạt động cho AI coding agents
├── README.md                # Tài liệu tổng quan dự án
├── requirements.txt         # Danh sách thư viện và phiên bản phụ thuộc
│
├── data/                    # Quản lý toàn bộ dữ liệu dự án
│   ├── raw/                 # Dữ liệu chính để phân tích (bank-additional-full.csv)
│   ├── reference/           # Tài liệu mô tả thuộc tính (bank-additional-names.txt)
│   ├── source/              # Tệp zip nguồn và thư mục giải nén nguyên bản
│   │   ├── bank+marketing.zip
│   │   └── extracted/
│   └── README.md            # Hướng dẫn chi tiết về cấu trúc và sử dụng dữ liệu
│
├── notebooks/               # Thư mục lưu trữ Jupyter Notebooks
│   ├── 01a_data_understanding.ipynb
│   ├── 01b_train_val_test_leakage.ipynb
│   └── 01c_overfitting_underfitting_tree.ipynb
├── src/                     # Mã nguồn chính của dự án (data loading, pipelines, models)
├── reports/                 # Báo cáo và hình ảnh trực quan hóa
│   └── figures/
└── tests/                   # Kiểm thử tự động (Unit tests, integration tests)
```

---

## 6. Trạng Thái Hiện Tại
- **Trạng thái:** `In Progress` (Đang triển khai các bài thực hành nền tảng).
- **Tiến trình:**
  - [x] **Bài 1A — Data Understanding & Khám Phá Dữ Liệu Ban Đầu** (`notebooks/01a_data_understanding.ipynb`)
  - [x] **Bài 1B — Train, Validation, Test Split & Phòng Chống Data Leakage** (`notebooks/01b_train_val_test_leakage.ipynb`)
  - [x] **Bài 1C — Underfitting, Overfitting & Model Complexity** (`notebooks/01c_overfitting_underfitting_tree.ipynb`)
  - [ ] **Giai đoạn tiếp theo:** Bài 2 — Data Preprocessing & Feature Engineering Pipeline.
