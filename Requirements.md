# MeetFlow — Feature Requirements
MeetFlow là nền tảng họp trực tuyến real-time tương tự Zoom/Google Meet, được xây dựng bằng React, TypeScript, NestJS, Socket.IO và WebRTC.

## 1. Authentication & User Management
- [ ] [P0] Đăng ký tài khoản bằng email và mật khẩu
- [ ] [P0] Đăng nhập, đăng xuất bằng Access Token và Refresh Token
- [ ] [P1] Xem và chỉnh sửa thông tin cá nhân
- [ ] [P1] Đổi mật khẩu, quên mật khẩu qua email
- [ ] [P2] Quản lý các phiên đăng nhập và thu hồi Refresh Token

## 2. Meeting & Room Management
- [ ] [P0] Tạo phòng họp với Room ID duy nhất
- [ ] [P0] Tham gia phòng họp thông qua link hoặc Room ID
- [ ] [P0] Rời phòng và kết thúc cuộc họp
- [ ] [P0] Hiển thị danh sách người tham gia theo thời gian thực
- [ ] [P1] Phân quyền Host và Participant
- [ ] [P1] Đặt lịch họp trong tương lai
- [ ] [P1] Waiting Room — Host phê duyệt người tham gia
- [ ] [P1] Khóa phòng và giới hạn số người tham gia
- [ ] [P1] Host có thể kick người tham gia
- [ ] [P1] Lưu lịch sử cuộc họp

## 3. Real-time Video & Audio
- [ ] [P0] Video call 1–1 bằng WebRTC
- [ ] [P0] Video call nhiều người (3–4 người bằng P2P Mesh)
- [ ] [P0] Bật/tắt camera và microphone
- [ ] [P0] Hiển thị trạng thái camera, microphone của từng người
- [ ] [P1] Chia sẻ màn hình (Screen Sharing)
- [ ] [P1] Chọn camera, microphone và loa đầu ra
- [ ] [P1] Hiển thị trạng thái kết nối (Connecting, Connected, Disconnected)
- [ ] [P2] Hiển thị người đang nói (Active Speaker)
- [ ] [P2] Chuyển sang SFU để hỗ trợ phòng họp đông người

## 4. Real-time Chat & Collaboration
- [ ] [P0] Gửi và nhận tin nhắn tức thời bằng Socket.IO
- [ ] [P0] Hiển thị tên người gửi và thời gian gửi
- [ ] [P1] Lưu lịch sử chat để xem lại
- [ ] [P1] Gửi emoji reactions
- [ ] [P1] Raise Hand — yêu cầu phát biểu
- [ ] [P2] Gửi tin nhắn riêng trong phòng
- [ ] [P2] Chia sẻ tệp trong cuộc họp

## 5. Real-time Reliability
- [ ] [P0] Phát hiện người dùng mất kết nối
- [ ] [P0] Cập nhật trạng thái participant khi join/leave/disconnect
- [ ] [P1] Tự động kết nối lại khi WebSocket bị ngắt
- [ ] [P1] Đồng bộ lại Room State sau reconnect
- [ ] [P1] WebRTC ICE Restart khi kết nối media thất bại
- [ ] [P1] Ngăn chặn truy cập room trái phép và giả mạo user ID
- [ ] [P2] Redis quản lý presence trong hệ thống nhiều server
- [ ] [P2] Xử lý duplicate events và các tình huống race condition

## 6. Dashboard & Meeting History
- [ ] [P0] Dashboard với nút Create/Join Meeting
- [ ] [P1] Hiển thị các cuộc họp đã tham gia
- [ ] [P1] Xem chi tiết lịch sử cuộc họp
- [ ] [P1] Lọc lịch sử theo ngày, tên phòng và trạng thái
- [ ] [P2] Thống kê số cuộc họp và tổng thời lượng tham gia

## 7. Security & Access Control
- [ ] [P0] Hash mật khẩu an toàn
- [ ] [P0] JWT Authentication và bảo vệ API
- [ ] [P1] Authorization cho quyền Host/Participant
- [ ] [P1] Rate Limiting cho API và Socket.IO events
- [ ] [P0] Validate dữ liệu bằng DTO và ValidationPipe
- [ ] [P1] Kiểm tra quyền trước khi relay WebRTC signaling
- [ ] [P2] Bảo vệ cuộc họp bằng mật khẩu hoặc invitation token
- [ ] [P2] Audit logs cho những hành động quan trọng

## 8. Infrastructure, Testing & DevOps
- [ ] [P0] Database migration bằng Prisma
- [ ] [P1] API documentation với Swagger/OpenAPI
- [ ] [P1] Unit tests cho business logic
- [ ] [P1] Integration tests cho REST API và Socket.IO
- [ ] [P1] Docker Compose cho Backend, PostgreSQL và Redis khi cần
- [ ] [P1] CI/CD với GitHub Actions
- [ ] [P1] Deploy với HTTPS/WSS
- [ ] [P1] Structured Logging và Error Handling
- [ ] [P2] Health Checks và Monitoring
- [ ] [P2] Load Testing cho WebSocket connections
- [ ] [P2] Đo RTT, packet loss, jitter và thống kê chất lượng WebRTC