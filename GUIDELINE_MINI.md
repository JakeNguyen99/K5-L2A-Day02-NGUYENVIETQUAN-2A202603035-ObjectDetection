# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | xe bốn bánh, mẫu Sedan hoặc SUV | xe con, sedan, SUV, taxi, xe bán tải |
| `truck` | xe bốn bánh, mẫu có khoang chứa đồ không che bằng thân xe | xe tải chở hàng, xe đầu kéo |
| `bus` | xe từ bốn bánh trở lên, thường dài và cao hơn những xe còn lại | xe buýt, minibus chở khách |
| `van` | xe bốn bánh, mẫu có khoang chứa đồ che bằng thân xe| xe van, minivan chở hàng hoặc chở người |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: box bao trọn vật thể
- Vật thể bị che khuất: gán nhãn nếu vật thể có thể thấy được từ 50% trở lên, còn lại bỏ qua
- Vật thể bị cắt bởi rìa ảnh: gán nhãn nếu vật thể có thể thấy được từ 50% trở lên, còn lại bỏ qua
- Vật thể rất nhỏ/mơ hồ: bỏ qua

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_001` | vật thể bị khuất đằng sau cột đề và xe SUV| không gán nhãn | vật thể nhìn giống xe van hoặc truck|
| `drive_003` | vật thể bị khuất và có đặc điểm của car và van| không gán nhãn| vật thể có đặc điểm của car và van|
| `drive_007` | vật thể bị khuất sau car | không gán nhãn | vật thể có đặc điểm của car và van |
| `drive_007` | hàng xe car nối đuôi nhau | gán nhãn xe đứng đầu | xe đứng đầu nhìn rõ |
| `drive_011` | hàng xe car nối đuôi nhau | gán nhãn xe đứng đầu | xe đứng đầu nhìn rõ |
| `drive_013` | vật thể bị khuất sau mép ảnh | không gán nhãn | có thể là xe van |
| `drive_018` | đuôi xe bị khuất | không gán nhãn | có thể là van hoặc car |
| `drive_...` | | | |
