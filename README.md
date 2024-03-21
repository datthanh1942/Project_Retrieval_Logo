# Project_Retrieval_Logo
## Mã nguồn được thực hiện và chạy trên google colab với những thư viện yêu cầu cài đặt như:
- ultralytics
- CUDA (có thể không cần nhưng chạy và xử lý chậm hơn)
## Các file cần thiết để chạy đối với các chức năng:
- Dectect : file last.pt(kết quả train epoch cuối cùng) hoặc best.pt(kết quả train epoch tốt nhất)
- Retrieval: file new_cluster.pkl (file vector đặc trưng đã được gán nhãn của dataset)
(link tải về: https://drive.google.com/file/d/1---ViJ3rPYKDSVxjZY-VloY5Fpy8qruv/view?usp=drive_link)

* Thư mục "Train_YOLO" là source code và file dẫn đến dataset cần thiết để train YOLO "logo_detect_yolov8.yaml", cần vào theo đường dẫn sau lấy để lấy file .pt:
/Train_Yolo/runs/detect/train/weights.

* File "Normalize" là quá trình tiền xử lý dữ liệu đối với bộ dữ liệu train yolo

## Quy trình chạy của mã nguồn chính "Project" :
- Chạy 'detect logo' để thu được ảnh cắt logo từ ảnh đầu vào
- Sau đó tiến hành chạy các hàm để rút trích đặc trưng từ bộ dữ liệu (thư mục train)
- Gọi mô hình muốn sử dụng
- Gom cụm và gán nhãn bộ dữ liệu bằng thuật toán KMeans
- Lưu hoặc load lại các vector đặc trưng đã được gom cụm của bộ dữ liệu bằng .pkl
- Lấy ảnh logo đã được cắt từ 'detect logo' để rút trích đặc trưng và dự đoán nhãn
- Dùng vector đặc trưng của ảnh đầu vào đem so sánh với các ảnh có cùng nhãn
- Sắp xếp độ giống nhau theo chiều lớn đến nhỏ và lấy top_k kết quả
- In ra độ giống nhau và các ảnh giống nhau trong thư mục kết quả (thư mục Result_Img trên drive)


Để biết chi tiết về mã nguồn và các đầu vào, vui lòng đọc file chú thích "Chu_thich_ma_nguon.pdf"
