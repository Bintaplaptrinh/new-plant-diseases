# NHẬN DIỆN BỆNH TRÊN LÁ CÂY THỰC VẬT (PLANT DISEASE DETECTION)

**Bộ môn:** Công nghệ Thông tin - Phân hiệu Trường Đại học Thủy Lợi  
**Môn học:** Machine Learning  
**Giảng viên hướng dẫn:** Ths. Vũ Thị Hạnh  

---

## Thành Viên Nhóm (Team Members)

| STT | Họ và Tên | Mã Sinh Viên (Student ID) |
|:---:|:---|:---|
| 1 | **Đoàn Anh Vũ** | 2351267280 |
| 2 | **Nguyễn Hữu Tuấn Phát** | 2351267274 |
| 3 | **Phạm Thị Quỳnh Giao** | 2351267259 |

**Lớp:** S26-65TTNT

---
## Giới Thiệu
Dự án này tập trung vào bài toán **Phân loại bệnh hại trên lá cây** sử dụng các kỹ thuật Học máy (Machine Learning) và Thị giác máy tính (Computer Vision). Mục tiêu của đề tài là xây dựng một mô hình có khả năng nhận diện và phân loại bệnh cây trồng thông qua hình ảnh lá cây, hỗ trợ việc chuyển đổi số trong nông nghiệp.

## Bộ Dữ Liệu
Dự án sử dụng bộ dữ liệu **New Plant Diseases Dataset** (phiên bản mở rộng của PlantVillage).
* **Quy mô:** Khoảng 87,907 hình ảnh chất lượng cao.
* **Phân lớp:** 38 lớp (classes) bao gồm cây khỏe mạnh và cây bị bệnh.
* **Đối tượng:** Bao gồm các loại cây như Táo, Nho, Ngô, Khoai tây, Cà chua, Đào, v.v.
* **Tiền xử lý:** Ảnh được resize về kích thước 256x256, chuẩn hóa (Normalize) và tăng cường dữ liệu (Data Augmentation) với các kỹ thuật: Lật ngang, xoay ngẫu nhiên, chỉnh độ sáng/tương phản.

## Phương Pháp & Mô Hình
Nhóm đã thử nghiệm và huấn luyện 3 mô hình Deep Learning hiện đại sử dụng kỹ thuật Transfer Learning:
1.  **MobileNetV3-Large:** Tối ưu cho tốc độ và thiết bị di động.
2.  **EfficientNet:** Tối ưu hóa cân bằng giữa độ chính xác và hiệu năng.
3.  **ResNet-18:** Cấu trúc mạng khối (residual blocks) giúp huấn luyện ổn định.

**Cấu hình huấn luyện:**
* **Loss Function:** CrossEntropyLoss (Label smoothing = 0.1).
* **Optimizer:** Adam.
* **Kỹ thuật:** Early Stopping, Mixed Precision (AMP) để tăng tốc độ huấn luyện.

## Kết Quả
Cả 3 mô hình đều đạt kết quả rất cao trên tập kiểm định (Validation set):

| Mô hình (Model) | Độ chính xác (Validation Accuracy) | Đánh giá |
|:---|:---:|:---|
| **MobileNetV3-Large** | **99.82%** | Tốc độ nhanh, phù hợp mobile. |
| **EfficientNet** | **99.92%** | Độ chính xác cao nhất. |
| **ResNet-18** | **99.90%** | Huấn luyện ổn định, hội tụ tốt. |

Thử nghiệm trên tập Test cho thấy các mô hình dự đoán chính xác 100% các mẫu được kiểm tra.

## Hướng Phát Triển

* Tăng cường Data Augmentation sát điều kiện thực tế (ánh sáng, rung, che khuất)

* Kiểm thử với ảnh chụp từ điện thoại, camera chất lượng thấp

* Tối ưu mô hình cho inference trên thiết bị di động

* Phát triển thành ứng dụng hỗ trợ chẩn đoán bệnh cây trồng
---

## Introduction
This project focuses on **Plant Leaf Disease Classification** using Machine Learning and Computer Vision techniques. The goal is to build a model capable of identifying and classifying crop diseases through leaf images, supporting digital transformation in agriculture.

## Dataset
We utilized the **New Plant Diseases Dataset** (an extended version of PlantVillage).
* **Scale:** Approximately 87,907 high-quality images.
* **Classes:** 38 classes covering both healthy and diseased plants.
* **Subjects:** Includes crops such as Apple, Grape, Corn, Potato, Tomato, Peach, etc.
* **Preprocessing:** Images are resized to 256x256, Normalized, and augmented using techniques like Random Horizontal Flip, Random Rotation, and Color Jitter.

## Methodology & Models
The team experimented with and trained 3 modern Deep Learning models using Transfer Learning:
1.  **MobileNetV3-Large:** Optimized for speed and mobile devices.
2.  **EfficientNet:** Optimized for the balance between accuracy and efficiency.
3.  **ResNet-18:** Utilizes residual blocks for stable training.

**Training Configuration:**
* **Loss Function:** CrossEntropyLoss (Label smoothing = 0.1).
* **Optimizer:** Adam.
* **Techniques:** Early Stopping, Mixed Precision (AMP) for faster training.

## Results
All three models achieved impressive performance on the Validation set:

| Model | Validation Accuracy | Evaluation |
|:---|:---:|:---|
| **MobileNetV3-Large** | **99.82%** | Fast speed, suitable for mobile. |
| **EfficientNet** | **99.92%** | Highest accuracy. |
| **ResNet-18** | **99.90%** | Stable training, good convergence. |

Testing on the Test set showed 100% prediction accuracy on the examined samples.

## Future Work
* Apply more realistic data augmentation (motion blur, perspective distortion, occlusion)

* Test models on images captured by low-quality smartphone cameras

* Optimize inference speed and memory usage for mobile deployment

* Develop a practical disease diagnosis support application for agriculture
