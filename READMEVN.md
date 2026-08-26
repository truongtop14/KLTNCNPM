# KLTN-CMPN

# MCP cho Bảo mật

**MCP for Secure** là một dự án khóa luận tốt nghiệp nghiên cứu cách sử dụng **Model Context Protocol (MCP)** để xây dựng một cầu nối **an toàn, có khả năng kiểm soát và mở rộng** giữa các Mô hình Ngôn ngữ Lớn (Large Language Models – LLMs) với các công cụ, dịch vụ, API và nguồn dữ liệu bên ngoài.

Các LLM hiện đại có khả năng hiểu và xử lý ngôn ngữ tự nhiên mạnh mẽ. Tuy nhiên, LLM không nên được phép truy cập trực tiếp vào cơ sở dữ liệu nhạy cảm, tài nguyên hệ thống hoặc các dịch vụ bên ngoài nếu không có cơ chế kiểm soát phù hợp. Dự án này đề xuất một kiến trúc dựa trên MCP, trong đó **MCP Server đóng vai trò như một lớp bảo mật và kiểm soát** giữa trợ lý AI và các tài nguyên bên ngoài.

Kiến trúc đề xuất có quy trình như sau:

```text
Người dùng
    ↓
LLM / Trợ lý AI
    ↓
MCP Client
    ↓
MCP Server
    ↓
Lớp bảo mật
    ↓
Công cụ / API / Dữ liệu được cấp quyền
```

Thay vì cung cấp cho LLM quyền truy cập không giới hạn, MCP Server chỉ cung cấp các công cụ đã được định nghĩa trước. Mỗi công cụ xác định rõ chức năng, tham số được chấp nhận, quyền truy cập và tài nguyên được phép sử dụng. Nhờ đó, các yêu cầu có thể được kiểm tra và xác thực trước khi thực thi.

Dự án tập trung vào một số cơ chế bảo mật như **xác thực (authentication), phân quyền (authorization), kiểm tra dữ liệu đầu vào (input validation), kiểm soát quyền sử dụng công cụ, giới hạn tần suất truy cập (rate limiting), ghi nhật ký (logging) và kiểm toán (auditing)**. Các công cụ nhạy cảm có thể được giới hạn dựa trên vai trò của người dùng, trong khi các yêu cầu nguy hiểm hoặc không được cấp quyền có thể bị từ chối trước khi truy cập dịch vụ bên dưới.

Một số MCP Tool có thể được xây dựng gồm:

```text
search_document(query)
read_document(id)
search_database(query)
get_system_information()
call_external_api(service, parameters)
```

Phần thực nghiệm tập trung đánh giá cả **khả năng hoạt động và tính bảo mật** của hệ thống. Một bộ dữ liệu kiểm thử gồm các yêu cầu thông thường và các yêu cầu có khả năng gây nguy hiểm được xây dựng nhằm đánh giá khả năng hệ thống lựa chọn đúng công cụ, đồng thời ngăn chặn các thao tác không được cấp quyền.

Các chỉ số đánh giá chính bao gồm **độ chính xác lựa chọn công cụ (Tool Selection Accuracy), tỷ lệ hoàn thành tác vụ (Task Success Rate), tỷ lệ chặn yêu cầu trái phép (Unauthorized Request Blocking Rate), thời gian phản hồi (Response Time) và mức độ tuân thủ chính sách bảo mật (Security Policy Compliance)**.

Kết quả dự kiến của đề tài là một nguyên mẫu hoạt động hoàn chỉnh bao gồm **AI Assistant, MCP Client, MCP Server bảo mật, nhiều MCP Tool, các chính sách bảo mật, hệ thống audit log và bộ dữ liệu phục vụ đánh giá thực nghiệm**.

Thay vì chỉ phát triển thêm một chatbot độc lập, **MCP for Secure** nghiên cứu MCP như một **ranh giới bảo mật được chuẩn hóa cho quá trình giao tiếp giữa AI và các công cụ bên ngoài**.

Câu hỏi nghiên cứu trung tâm của đề tài là:

> **Model Context Protocol có thể được sử dụng như thế nào để cho phép các Mô hình Ngôn ngữ Lớn tương tác với các công cụ bên ngoài một cách an toàn, có kiểm soát và có khả năng kiểm toán?**

**Từ khóa:** Model Context Protocol, MCP, Mô hình Ngôn ngữ Lớn, Bảo mật AI, Tool Calling, Kiểm soát truy cập, Bảo mật LLM, Hệ thống AI an toàn.
