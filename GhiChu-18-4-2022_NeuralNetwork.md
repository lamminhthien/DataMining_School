Khi phân lớp phải tìm bộ dữ liệu huấn luyện
Tách thành 2 phần (Cột cuối cùng là cột nhãn label cho biết mỗi sample như vậy, mỗi đối tượng như vậy thuộc lớp nào)
Số lượng các lớp của tập dữ liệu huấn luyện lấy từ cột label
Ngoài cột nhãn ra, mình cần sưu tầm feautures bao nhiêu cột phía trước nữa (bao nhiêu thông tin mô tả object) ?
Họ tên, giới tính, cmnd, sdt, email, lớp học , nhiều quá, ta cần phân lớp những sinh viên đó theo kiểu gì , chứ ko phải lụm hết tất cả đặc 
 trưng vô. Vì vậy số lượng đặc trưng cần chọn lọc một vài cái ta thực sự cần phân tích thôi
PCA: dimension reduction. Vì số lượng result càng lớn thuật toán càng chậm dễ dấn đến sai lệch (outlier)
dữ liệu nhỏ vừa thì làm gì, dữ liệu lớn thì làm gì ?
Khai phá dữ liệu sử dụng một số kĩ thuật học máy.

------------------------------------------------------------------
Neural Network , Deep Learning, Convolutional Neural Network

SVM học cái gì, học cái qui luật phân bố của các dữ liệu, học vị trí của các phân bố của các điểm dữ liệu trong không gian vector. Kết quả 
là tìm ra siêu phẳng để tách dữ liệu thành 2 lớp.
Để tìm siêu phẳng, người ta  chỉnh bias, weight. SVM học sau đó dùng siêu phẳng nhận dữ liệu mới và nó sẽ dự đoán nằm bên + hay bên -

SVM không thể phân tách dữ liệu không có đường phân tách tuyến tính, không có bất cứ kẻ hở nào để kẻ đường phân cách giữa chúng.
Kernel chuyển từ  space này sang feauture space khác. (Tăng trục tọa độ lên thành không gian có số chiều lớn hơn ).

knn chỉ nhớ vị trí của các điểm dữ liệu mà thôi
còn phân lớp nó sẽ tính khoảng cách từ điểm mới đó đến k điểm gần nhất

Decision tree, từ 1 bảng dữ liệu huấn luyện
Bẻ bảng đó ra để tìm mối liên hệ mạnh yếu giữa cột này với các cột khác (Atromy để đo độ lợi thông tin, cao nhất, lấy làm gốc, theo từng layer)
Lấy nhãn gắn cho nó (nhãn nào nhiều hơn gắn vô).


---- Percepton -------
Từ 1 input, đo difference brror tới y output. Dùng cái sai số difference brror để điều chỉnh w sao cho input (x1,y1) gần y1,y label hơn)
Từ đó tìm được w đúng để còn dự đoán các x khác nhau. Người ta chỉ lấy 1 trong số nhiều vector xi. Sau đó lấy w1,w2,wn nhân với từng x11,x12,... x1n
Cộng hết từng giá trị tính được vào nhau bỏ vô hàm tạo ra yi recepton Yp 
Tạo thành y có nhãn y label. Percepton: xi  --> yi'
từ y1 có sẵn kiểm tra với y được dự đoán xem nó có lệch so với yp hay ko?
vector w là strength, thứ hai là hàm activation function. 
Bộ w1,..wn chọn đại nhân lại với nhau ra một con số kết quả nó là 1 cái lable reception mà nó đoán vector đầu vào (trong tập huấn luyện) có nhãn thực sự có gần giống với y của reception hay ko?
Reception chỉ có thể trong 1 khoảng.
Sigmoid: Những giá trị sau khi lấy w*x có thể nằm trong khoảng đồ thị.
Activation nó ép toàn bộ giá trị thành w*x không còn ngẫu nhiên (quá lớn hay quá bé nữa) vào 1 khoảng (0 đến 1 ) chẳng hạn 
nếu ko có activation thì khoảng giá trị đầu ra quá lộn xộn.
Lấy từng giá trị z trong tổng xích ma, bỏ trong hàm sigmoid để tính nhãn, số càng nhỏ thì nhãn  = 0.
Do mình quyết định chọn hàm sigmoid hay tanh
Hàm tanh (tan) f(z)=tanh(z)
Mỗi format activation chỉ phù hợp với mỗi loại dữ liệu nhất định mà thôi
reLU (restricted linear unit), z là cái tổng nhan 
if z <=0 relu = 0, nếu lớn hơn 0 thì nhãn là chính z luôn
Convolutional Neural Network chỉ dùng cho dữ liệu ảnh là tốt nhất
1 reception tính luôn cả giá trị đầu vô và 2 cái w luôn nhan
Yp - yi
Đạo hàm là tốc độ thay đổi dữ liệu tại một thời điểm thích hợp: Tính được sự thay đổi lim(f(x)-f)
Hàm đo độ hao hụt, gradient descent là giảm đạo hàm để mà giảm sai số cho bộ huấn luyện dữ liệu mà dùng w nào thì đồ thị giảm dần
