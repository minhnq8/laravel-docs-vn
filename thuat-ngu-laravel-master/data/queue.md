## Queue

**Queue**: là một phương pháp xử lý tác vụ theo nguyên tắc hàng đợi, thay vì phải xử lý trực tiếp trên trên request (điều này khiến các việc tiếp theo để xử lý request bị ngừng để chờ), thì đẩy việc xuống để làm ở background, để cho request có thể được tiếp tục xử lý. Điều này làm tối ưu hoá request và cải thiện performance cho ứng dụng web hơn.

Ví dụ: khi người dùng thực hiện đăng kí một tài khoản, thông thường thì người dùng sẽ phải chờ hơi lâu vì lúc đăng kí thì ứng dụng cần tạo dữ liệu user mới vào database, thực hiện kết nối một server để gửi email chào mừng, thực hiện gửi email xác nhận địa chỉ tới địa chỉ mail đăng kí của user, ... còn nhiều xử lý khác nữa.... Nếu mà phải xử lý hết tất cả các công việc này rồi mới trả lại response cho user, thì sẽ không tốt chút nào. Việc áp dụng queue ở đây sẽ cho phép những công việc bổ sung, như là gửi email, có thể được thực hiện tách rời ra khỏi request đang xử lý, và có thể thực hiện lúc khác, để có thể trả về response sớm cho user.

Laravel cung cấp hỗ trợ đẩy đủ các API cần thiết để làm việc với queue, hãy tham khảo [mục queue trong tài liệu của Laravel](https://github.com/petehouston/laravel-docs-vn/blob/master/queues.md).