# SEND MAIL

## 1. Use EmailJS account for sending emails.
Bước 1. Truy cập link: https://www.emailjs.com/ để đăng ký và đăng nhập.

Bước 2. Tạo Email Services:
    - Sau khi đăng nhập, bạn sẽ thấy phần "Email Services" trong dashboard của EmailJS. 
    - Bạn cần thêm dịch vụ gửi email (ví dụ: tạo Gmail, mục Name ghi tên email để kết nối dịch vụ).
    - Khi tạo ES, EmailJS sẽ cung cấp một services_id.
    
Bước 3. Tạo một template email:
    - Trong phần "Email Templates", bạn có thể tạo các mẫu email. 
    - Tạo email theo cấu trúc bạn mong muốn (ví dụ: subject, content, to email, from name, from email, reply to ...).
    - Khi tạo template, EmailJS sẽ cung cấp một template_id.
    
Bước 4. Lấy các thông tin cần thiết:
    - Service ID: ID của dịch vụ email bạn đã kết nối.
    - Template ID: ID của mẫu email mà bạn đã tạo.
    - publicKey và privateKey ở phần Account trong dashboard của EmailJS.

##2. Install EmailJS SDK: $ flutter pub add emailjs

##3. Thay đổi code trong main.dart(Service ID,Template ID, publicKey và privateKey ):
![image](https://github.com/user-attachments/assets/a1846ec9-8aee-4333-b19f-6c7c6bbed1f9)
        await emailjs.send(
        '...', //YOUR_SERVICE_ID
        '...', //YOUR_TEMPLATE_ID
        {
        },
        const emailjs.Options(
            publicKey: '...',  //YOUR_PUBLIC_KEY
            privateKey: '...',  //YOUR_PRIVATE_KEY
            limitRate: const emailjs.LimitRate(
              id: 'app',
              throttle: 10000,
            )),


