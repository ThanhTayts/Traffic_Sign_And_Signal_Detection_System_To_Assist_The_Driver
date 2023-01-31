### - Hầu hết tất cả các vụ tai nạn xe cộ đều do lỗi con người và điều này có thể hạn chế và tránh được với các hệ thống hỗ trợ lái xe tiên tiến.
### - Nhận dạng biển báo và tín hiệu đèn giao thông là tính năng hữu ích, công dụng vượt trội của tính năng này đó là giúp tài xế dễ dàng nhận diện được các biển báo giao thông như giới hạn tốc độ, cấm vượt hay cấm quay đầu, … và hiển thị rõ nét ngay trên màn hình của xe từ đó tránh được các trường hợp không mong muốn như đi vào đường cấm, bị cảnh sát giao thông phạt, …
### - Tuy nhiên biển báo giao thông và đèn tín hiệu giao thông ở mỗi quốc gia có các đặc trưng riêng vì vậy, cần có hệ thống nhận dạng phân loại biển báo và tín hiệu
đèn giao thông để hỗ trợ cho người lái xe tại Việt Nam.
### - Hiện nay ở Việt Nam cũng đã có một số đề tài nghiên cứu về việc nhận dạng và phân loại biển báo giao thông, tuy nhiên đa số sử dụng phương pháp Haar Cascade, CNN tốc độ xử lý chậm và độ chính xác không cao, không phù hợp với hệ thống thời gian thực.
### - Chính vì thế tôi đã thực hiện đề tài **“Nghiên cứu xây dựng mô hình nhận dạng biển báo và tín hiệu đèn giao thông hỗ trợ người lái xe”** để phát hiện các loại biển báo và các mức tín hiệu đèn giao thông nhằm đưa ra nhắc nhở hỗ trợ người lái xe. Hệ thống sử dụng ngôn ngữ lập trình Python, mô hình YOLOv4, màn hình hiển thị kết quả và loa phát âm thanh nhắc nhở. Kết quả thực nghiệm sẽ được so sánh với các phương pháp khác để đánh giá hiệu quả của thuật toán cũng như khả năng ứng dụng thực tế.

#### - Các thành phần trong hệ thống
          * Phần mềm
            1. OpenCV 4.5.5
            2. Numpy 1.2.4
            3. Tensorflow 2.3.0
            4. YOLOv7 
          * Phần cứng
            1. Camera
            2. Jetson Nano B01
            3. Màn hình TFT
            5. Loa
   ![image](https://user-images.githubusercontent.com/92384494/215694512-c3a60beb-a1ec-4bec-8417-c6d812847a12.png)
   ![image](https://user-images.githubusercontent.com/92384494/215696425-a00fafa6-b0a7-4656-89da-75eb009c0c7d.png)
            
#### - Quá trình hoạt động của hệ thống
   ![image](https://user-images.githubusercontent.com/92384494/215694715-5979b500-9ec9-4ade-8bd6-640a585abe17.png)
   
  * Bắt đầu hệ thống sẽ khởi chạy các thư viện ,mô hình phát hiện đối tượng, khởi động camera và loa.
  * Bộ xử lý trung tâm thu nhận hình ảnh đầu vào từ camera sau đó tiến hành trích xuất, định dạng lại và tiến hành các quá trình tiền xử lý ảnh.
  * Ảnh sau khi được biến đổi và chuẩn hoá sẽ được được qua mô hình phát hiện đối tượng để dự đoán vị trí và xác xuất biển báo biển báo giao thông trong ảnh đầu vào, sau đó tiến hành gán nhãn cho đối tượng vừa được phát hiện và hiển thị lên màn hình. Nếu không phát hiện được bất kì đối tượng nào thì tiếp tục trích xuất hình ảnh từ camera.
  * Tiến hành so sánh tên biển báo giao thông tương ứng của đối tượng vừa phát hiện được, sau đó thông qua loa phát âm thanh cảm báo, nhắc nhở người lái xe.

#### - Kết quả 
    * Ban ngày.
   ![image](https://user-images.githubusercontent.com/92384494/215695320-dcfd0b2c-54a8-473a-8355-bc2c33f9abdc.png)
   ![image](https://user-images.githubusercontent.com/92384494/215695394-90ab99a7-84b1-4a73-9ea1-cc726aa45e72.png)
   
    * Ban đêm.
   ![image](https://user-images.githubusercontent.com/92384494/215695486-ac0417ba-74d5-4847-b66d-871072d84bd7.png)
   ![image](https://user-images.githubusercontent.com/92384494/215695582-f590bfa8-d96a-45bf-9860-4ccad180f66c.png)
   
    * Trời mưa
   ![image](https://user-images.githubusercontent.com/92384494/215695754-98f3b4bc-b9f6-4940-b778-5deaebc066ac.png)
#### * Link
   [Video Demo](https://www.youtube.com/watch?v=PS8wE31Du1Q)
