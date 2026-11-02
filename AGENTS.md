# Hướng Dẫn Dành Cho AI Coding Agents

Tài liệu này quy định các nguyên tắc hoạt động cho các AI Coding Agent khi tương tác và làm việc trên repository `bank-marketing-ml-lab`.

## Nguyên Tắc Hoạt Động Cốt Lõi

1. **Kiểm tra trạng thái repository trước khi thao tác:** Luôn kiểm tra `git status`, cấu trúc thư mục và tài liệu hiện có trước khi thực hiện bất kỳ thay đổi nào.
2. **Tuân thủ phạm vi nhiệm vụ:** Chỉ thay đổi những tệp tin thuộc phạm vi công việc được giao. Không tự ý triển khai các bài học hoặc giai đoạn tiếp theo nếu chưa có yêu cầu từ người học.
3. **Người học tự phát triển thuật toán:** AI đóng vai trò hỗ trợ về mặt tổ chức dự án, cấu trúc mã nguồn, viết kiểm thử (testing) và review mã nguồn. Các phần thuật toán cốt lõi và suy luận phân tích do người học tự tay triển khai.
4. **Kỷ luật Machine Learning nghiêm ngặt:** Tuyệt đối không sử dụng tập kiểm tra (Test set) trong quá trình lựa chọn mô hình hoặc tinh chỉnh siêu tham số (Hyperparameter Tuning). Tránh rò rỉ dữ liệu (Data Leakage).
5. **Trung thực về dữ liệu & kết quả:** Không tạo hoặc báo cáo kết quả thực nghiệm giả (accuracy, F1, metrics chưa qua huấn luyện thực tế).
6. **Bảo toàn dữ liệu gốc:** Không bao giờ xóa hoặc thay đổi nội dung các tệp dữ liệu nguồn trong `data/source/` và `data/raw/`.

