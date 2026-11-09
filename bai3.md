# Bài 3 : Sử dụng AI an toàn khi xử lý lỗi phần mềm
## bối cảnh: bạn hỏi AI cách sửa lỗi "Path not found". AI đưa ra một câu lệnh gạch đầu dòng bảo bạn dán vào terminal, nhưng lệnh này trông rất lạ và có thể can thiệp sâu vào hệ thống
Input
AI đưa ra câu trả lời lệnh rm -lf trên linux/macOS, lệnh remove item trên terminal 
Process
- phân tích cứu pháp lệnh: đọc kỹ lệnh, xác định lệnh tác động đến thư mục nào.
- tra cứu kiểm chứng lệnh: 
site:stackoverflow.com "python" "Path not found"
đối chiếu xem giải pháp có được cộng đồng vote hay accep không
Output
kiểm chứng mức độ an toàn
an toàn : khi câu lệnh chỉ bổ sung đường dẫn python vào biến môi trường, mà không xóa bất kỳ dữ liệu nào 
không an toàn : khi câu lệnh can thiệp ghi đè toàn bộ path hệ thống, xóa thư mục hệ thống, tải scrip từ URL không rõ nguồn góc 
## thiết kế một câu lệnh "hỏi ngươc lại" AI để yêu cầu nó giải thích độ an toàn của câu lệnh trước khi bạn thực thi 
trước khi thực hiện lệnh này trên terminal , hãy giải thích chi tiết cho tôi .câu lệnh:

with open(os.path.join(os.path.dirname(__file__), 'Pickles', name + '_' + date.strftime('%y-%b-%d')), 'rb') as f:
    obj = pickle.load(f)

chính xác đang thực hiện những thao tác gì trên hệ thống của tôi.Có tác động hay xóa dữ liệu ở thư mục nào không. lệnh này áp dụng cho hệ điều hành nào. Nếu lệnh này lỗi hoặc làm hỏng cấu hình hệ thống, làm cách nào để khôi phục 
