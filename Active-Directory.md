III. Cài đặt và cấu hình Active Directory trên Windows Server 2012:
Trong môi trường Windows Server 2012 thì lệnh dcpromo đã bị vô hiệu hóa, do vậy nếu muốn tạo Domain Controller thì phải cần đến ADDS (Active Directory Domain Services) từ giao diện quản lý - Server Manager.

Trước hết cần cấu hình IP tĩnh cho máy: 
Trên màn hình Dashboard của Server Manager, chọn Add roles and features: 
Ấn Next để giữ nguyên các cài đặt mặc định. Đến Select server roles -> Chọn Active Directory Domain Services (AD DS) và DNS Server: 
Tiếp theo ấn Next để giữ nguyên các cài đặt mặc định. Đến Confirm installation selections, bấm Install để cài đặt các dịch vụ cần thiết của Domain Controller: 
Sau khi cài đặt xong, tiến hành tạo Domain Controller. Chọn Promote this server to a domain controller: 
Trên màn hình Deployment Configuration, có 3 tùy chọn: Add a domain controller to an existing domain: Thêm một ADC vào domain có sẵn. Add a new domain to an existing forest: Xây dựng domain mới trong forest có sẵn. Add new forest: xây dựng máy DC đầu tiên của forest. Ở đây ta sẽ tạo một forest mới có tên là framgia.com: 
Ở màn hình Domain Controller Options, nhập mật khẩu tại ô Type the Directory Services Restore Mode (DSRM) password. Mật khẩu này sẽ được dùng để khôi phục AD ở chế độ Restore Mode: 
Click Next đến màn hình Addiontonal Options, chọn tên NetBIOS domain. Ở đây sẽ để mặc định: 
Tại màn hình Paths, chọn đường dẫn lưu database của PAD, logs, SYSVOL. Chọn mặc định: 
Ấn Next đến màn hình Prerequisites Check, tại đây sẽ kiểm tra các điều kiện để cài đặt DC. Chọn Install để bắt đầu cài đặt: 
Sau khi hoàn tất cài đặt, restart lại máy để hoàn thành quá trình xây dựng Active Directory Domain Services. Vậy là bây giờ chúng ta đã có thể tạo User, Group, GPO... trên DC. Trong các bài tiếp theo, mình sẽ giới thiệu về FSMO roles và các chức năng của FSMO roles.
