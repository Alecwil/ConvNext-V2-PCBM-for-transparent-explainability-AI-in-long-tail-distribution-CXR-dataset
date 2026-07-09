Chest X-ray Diagnostic System: ConvNeXt V2 + PCBM-h

1. Tổng quan Dự án

Hệ thống chẩn đoán đa nhãn (Multi-label) cho ảnh X-quang lồng ngực, dựa trên kiến trúc ConvNeXt V2 và tầng giải thích Post-hoc Concept Bottleneck Model (PCBM-h). Dự án tập trung vào việc cân bằng giữa hiệu suất phân loại (Performance) và tính minh bạch trong y tế (Interpretability).

2. Điểm nổi bật

Kiến trúc Hiện đại: Sử dụng ConvNeXt V2  để trích xuất đặc trưng với độ chính xác cao và tối ưu tài nguyên tính toán .

XAI: Tích hợp tầng PCBM-h giúp diễn giải lý do chẩn đoán dựa trên các "Khái niệm y khoa" (Concepts) thay vì là "Hộp đen" (Black-box).

Xử lý Dữ liệu Chuẩn mực: Áp dụng chiến lược U-Zeros để xử lý nhãn bất định (Uncertainty labels) trên tập dữ liệu CheXpert.

Tối ưu Kaggle: Code được thiết kế để chạy trên môi trường Kaggle/Colab với cơ chế Mixed Precision (AMP) và Gradient Accumulation.

3. Cấu trúc Dự án

├── data/               # (Đường dẫn Dataset)  
├── models/             # Định nghĩa kiến trúc (ConvNeXt, PCBM-h)  
├── notebooks/          # Kaggle Notebooks & Experiments  
├── utils/              # Tiền xử lý, U-Zeros, và các hàm hỗ trợ  
└── train.py            # Script huấn luyện chính   


4. Hướng dẫn Sử dụng

Để chạy huấn luyện mô hình, đảm bảo cấu trúc dữ liệu CheXpert đã được nạp vào /kaggle/input/ và sử dụng script:

python train.py --epochs 20 --batch_size 8 --lr 1e-4


5. Kết quả Dự kiến

Mô hình hướng tới mục tiêu đạt MACRO AUROC trên tập CheXpert cạnh tranh với các kiến trúc SOTA, đồng thời cung cấp biểu đồ phân tích "Concept Scores" cho từng ca bệnh cụ thể.

6. Trích dẫn & Bản quyền

Dự án này được phát triển cho mục đích nghiên cứu khoa học. Nếu sử dụng mã nguồn hoặc phương pháp luận từ dự án, vui lòng trích dẫn tác giả và các công trình nền tảng:

ConvNeXt V2 Paper

PCBM-h Paper

CheXpert Paper

Tác giả: Sần Dịch Anh
Cập nhật: Tháng 7/2026
