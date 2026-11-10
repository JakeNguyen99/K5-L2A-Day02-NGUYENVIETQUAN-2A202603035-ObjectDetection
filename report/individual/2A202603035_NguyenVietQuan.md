# Báo cáo cá nhân — Ngày 2 Object Detection

[SUBMISSION.md](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Nguyễn Việt Quân
- MSSV: 2A202603035
- Email: 26ai.quannv3@vinuni.edu.vn
- Lớp: 2A-LAB-E402
- Link repo bài làm: https://github.com/JakeNguyen99/K5-L2A-Day02-NGUYENVIETQUAN-2A202603035-ObjectDetection.git
- Link Colab đã chạy: https://colab.research.google.com/drive/1eHzb8zDjf3BlnqKz1phZJpLZuT7S-RGo#scrollTo=6f78b880

## 2. Schema và mini guideline

[GUIDELINE_MINI.md](../../GUIDELINE_MINI.md).

## 3. Annotation và self-QC

- Số file nhãn train: 50
- Kết quả checker và lỗi đã xử lý:
- Danh sách ít nhất 10 ảnh đã rà bằng mắt: drive_010.jpg, drive_014.jpg, drive_023.jpg, drive_024.jpg, drive_026.jpg, drive_027.jpg, drive_029.jpg, drive_033.jpg, drive_039.jpg, drive_042.jpg, drive_045.jpg
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa: điều chỉnh hoặc gán nhãn lại
- Commit khóa nhãn ban đầu: add label for 50 pictures

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP | 441 | Không có rework |
| FP | 455 | Không có rework |
| FN | 212 | Không có rework |
| Precision | 0.4922 | Không có rework |
| Recall | 0.6753 | Không có rework |
| F1 | 0.5694 | Không có rework |
| mean_iou_of_matches | 0.8442 | Không có rework |
| passed | false| Không có rework |

[annotation_evaluation.json](../../outputs/annotation_evaluation.json).

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: Python-3.13.16, GPU T4, Ultralytics 8.4.208, torch-2.14.1+cu130
- Các tham số thay đổi so với notebook nếu có và lý do: 
- Đường dẫn best checkpoint trong phiên chạy: "/content/Day2-Lab/outputs/yolo26_runs/vehicle_annotation/weights/best.pt"

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision | 0.3156193471665181 |
| Recall | 0.30664893617021277 |
| mAP50 | 0.2739647516429376 |
| mAP50–95 | 0.20063156304965743 |

[eval_predictions](../../report/individual/assets/eval_predictions/)
[yolo26_runs](../../report/individual/assets/yolo26_runs/)
Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
   Lớp car. Ảnh minh họa: drive_055.jpg
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?
   Khi mAP50 cao nhưng mAP50-95 thấp thì có nghĩ là model có khả năng nhận diện tốt nhưng bounding box không khớp hoàn toàn vật thể. Cần kiểm tra lại Ground Truth.
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?
   Lỗi class van có thể liên quan đến guideline. Do guideline quy định chưa rõ ràng và người gán nhãn hiểu sai nên trong ảnh drive_051.jpg có xe con thuộc lớp car nhưng được xác định là thuộc lớp van.
5. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?
   Không dùng 10 ảnh eval để train vì dữ liệu này cần được giữ độc lập hoàn toàn với quá trình huấn luyện nhằm đánh giá khả năng tổng quát hóa của mô hình trên dữ liệu mới.

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| xác định vật thể cần được gán nhãn | vật thể có đặc điểm của 2 lớp khác nhau | tìm hiểu thật kỹ và phân biệt rõ ràng đặc điểm của 2 lớp đó | gán được nhãn cho vật thể đó |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.
