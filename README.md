# **HOUSING PRICE REPORT**
*Author: Nguyen Trong Nhan*
## **Mục tiêu:**
**HOUSING PRICE REPORT** giúp ta phân tích các yếu tố ảnh hưởng đến giá trị của bất động sản dựa trên các đặc điểm của nó, có thể là các mối quan hệ giữa giá nhà và diện tích, loại hình nhà, năm xây dựng, vị trí nhà và giá trị nhà. Từ đó, ta có thể xây dựng các mô hình học máy dự đoán giá nhà bằng cách áp dụng các thuật toán như Linear Regression hay K-means. Dự án phù hợp và hữu ích với nhà phân tích dữ liệu trong việc xây dựng mô hình dự báo cũng như kiểm tra các giả thuyết phân tích thống kê. 
## **Điều kiện tiên quyết** - Đảm bảo các yêu cầu sau:

**Đã cài đặt phiên bản Python mới nhất**

**Kỹ năng phân tích dữ liệu cơ bản:**
- Thu thập và làm sạch dữ liệu
- Khám phá dữ liệu (Exploratory data Analysis - EDA)

**Kiến thức về thống kê:**
- Thống kê mô tả
- Phân tích tương quan

**Học máy cơ bản:**
- Học máy giám sát - Hồi quy tuyến tính (Linear Regression): Làm quen với các phương pháp hồi quy tuyến tính để dự đoán giá nhà dựa trên các đặc điểm của nó.
- Học máy không giám sát - Phân cụm (K-means): Phân chia các ngôi nhà có cùng giá trị diện tích và giá cả lại với nhau thành từng nhóm

**Kỹ năng lập trình : Ngôn ngữ Python**
  
**Kỹ năng trực quan hóa dữ liệu**

**Hiểu biết cơ bản về ngành bất động sản**

**Cài đặt và yêu cầu: Python 3.13.1**

- Các thư viện cần thiết: *Pandas, Numpy, Scipy, Matplotlib, Seaborn, Plotly, Scikit-learn*
- Cài đặt các thư viện: Trong thẻ Terminal, thực hiện cài đặt các thư viện bằng cú pháp “pip install <Package>”
*Cách sử dụng*
- Để chạy mã phân tích: python Report_Housing_Price.py --input “Visual Studio Code/Housing_Price Data/housing.csv”
*Tập dữ liệu:*
Dữ liệu được lấy từ Kaggle Housing Dataset. Tập dữ liệu có các đặc trưng như diện tích, số phòng ngủ, và giá nhà 
(https://www.kaggle.com/datasets/sukhmandeepsinghbrar/housing-price-dataset) 
## **Các bước phân tích (Analysis Steps)**
### Làm sạch dữ liệu: 
Xử lý các giá trị thiếu, các giá trị trùng lặp, các giá trị ngoại lai, các giá trị null và NA.
### Khám phá dữ liệu (Exploratory Data Analysis - EDA): 
Mô tả và phân tích các đặc điểm của dữ liệu như phân phối, mối quan hệ giữa các biến. Mô tả và phân tích các đặc điểm của dữ liệu như phân phối giá, mối quan hệ giữa giá nhà và các yếu tố ảnh hưởng đến giá nhà
### Tiền xử lý dữ liệu: 
Xử lý các dữ liệu bị thiếu, chuẩn hóa dữ liệu.
### Xây dựng mô hình: 
Xây dựng mô hình Hồi quy tuyến tính và K-means để đánh giá các kết quả
Dự đoán giá nhà khi biết được diện tích cụ thể
Phân nhóm các ngôi nhà theo mức giá và diện tích
Phân nhóm ngôi nhà theo các đặc trưng chung: diện tích ngôi nhà
## Đánh giá mô hình: 
- Mô hình Hồi quy tuyến tính: Sử dụng các chỉ số như r2 score (Điểm phù hợp), MAE (sai số tuyệt đối trung bình), MAPE (sai số phần trăm tuyệt đối trung bình) để đánh giá hiệu quả mô hình.
- Mô hình phân cụm K-means: Phân cụm giá nhà các ngôi nhà có cùng diện tích 
## Kết quả (Results):
### Mô hình Hồi quy tuyến tính:
- R² = 0.76 là một chỉ số khá tốt, có nghĩa là 76% sự biến động của giá nhà được giải thích bởi mô hình, trong khi 24% còn lại là do các yếu tố ngoài mô hình như vị trí, kiểu nhà, v.v.
- Bên cạnh đó, có nhiều yếu tố không được đưa vào mô hình hoặc không thể đo lường một cách chính xác (như những yếu tố chủ quan như điều kiện sống, thị trường bất động sản, tâm lý người mua) nên không thể dự đoán chính xác được sự biến động của giá nhà.
- MAE = 125188.72855705574: Chỉ số thể hiện trung bình mỗi giá trị dự báo sai lệch khoảng 125,000 đơn vị giá. Điều này thể hiện độ chính xác mô hình chưa cao, cần cải thiện thêm vì giá nhà chịu ảnh hưởng bởi rất nhiều yếu tố ngoài diện tích.
- MAPE = 24.0%: Trung bình sai lệch giữa giá trị dự báo và giá trị thực tế là 24%. Cần cải thiện mô hình, thường đối với các mô hình dự báo giá nhà, MAPE dưới 10% sẽ là lý tưởng.
### Mô hình phân cụm K-means:
- Biểu đồ phân phối giá nhà được tạo ra từ dữ liệu đầu ra của mô hình.
- Biểu đồ phân cụm giá nhà cho thấy giá nhà và diện tích có thể được phân loại thành 3 nhóm: Nhà có diện tích nhỏ và giá thấp, nhà có diện tích và giá trung bình, nhà có diện tích lớn và giá cao. Việc quyết định lựa chọn ngôi nhà phụ thuộc vào nhu cầu và khả năng tài chính của mỗi cá nhân.
## Kết quả phân tích: 
**Dựa vào các kết quả phân tích:**
- Phân bổ giá nhà nằm trong khoảng 75,000 đến 1,640,000 đơn vị giá
- Giá nhà trung bình có sự giảm mạnh vào các giai đoạn khủng hoảng kinh tế (Thế chiến II, khủng hoảng tài chính toàn cầu 2007 - 2008
- Các ngôi nhà có tầng hầm và vị trí gần bờ sông thường có giá cao hơn các ngôi nhà khác nếu so cùng diện tích
- Loại hình nhà: Nhà 1 tầng và 2 tầng chiếm phần lớn trong tổng số nhà (chiếm 87,6%). Về giá, nhà 1 - 1,5 - 2 tầng có giá trung bình ổn định qua từng giai đoạn, trong khi các loại hình nhà khác đều có sự thay đổi bất thường ở từng giai đoạn. 
- Giá nhà sẽ tăng theo điểm đánh giá. Số lượng nhà ở thang điểm 3, 4 chiếm phần lớn trong tổng số nhà ( 91,33%)
- Giá nhà trung bình đối với những nhà có thực hiện cải tạo có biên độ dao động lớn hơn so với nhà không cải tạo.
## Khuyến nghị: 
- Giá nhà bị ảnh hưởng rất nhiều bởi các yếu tố khác nhau ngoài diện tích, nhất là vị trí, loại nhà và điểm đánh giá. Trong việc lựa chọn nhà để đầu tư hoặc sinh sống, khuyến khích quan tâm đến các ngôi nhà có điểm đánh giá cao (3-5 điểm) và các loại hình nhà có biên độ thay đổi giá ổn định qua từng giai đoạn ( 1 - 1,5 - 2 tầng). 
- Giá nhà cũng có thể bị ảnh hưởng bởi nhu cầu từ thị trường. Số lượng các kiểu nhà từ 2,5 tầng trở lên và có điểm đánh giá là 5 chiếm tỉ lệ rất nhỏ nên giá sẽ có thể chênh lệch rất lớn so với thực tế.
## Kết luận (Conclusion)
Dự án đã phần nào xây dựng mô hình dự đoán giá nhà và phân loại nhà theo nhiều yếu tố khác nhau, giúp các nhà đầu tư cũng như các hộ gia đình đưa ra quyết định tốt hơn trong việc lựa chọn khu vực để đầu tư hoặc sinh sống.
## Tài liệu tham khảo (References)
- "Kaggle Housing Price Dataset: (https://www.kaggle.com/datasets/sukhmandeepsinghbrar/housing-price-dataset) ."
- "Học máy cơ bản: (https://scikit-learn.org/)."
