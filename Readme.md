# BÁO CÁO RÀ SOÁT AN TOÀN THÔNG TIN DỰ ÁN SMARTCAMPUS TRƯỚC KHI BÀN GIAO LÊN GITHUB

## PHẦN 1 – NHẬN DIỆN RỦI RO VÀ XỬ LÝ SỰ CỐ

### 1. Phân tích Tình huống 1 (Email cảnh báo khóa tài khoản GitHub)

* **Tên loại tấn công:** Đây là cuộc tấn công **Phishing (Tấn công giả mạo đánh cắp thông tin)** kết hợp với kỹ thuật **Typosquatting (Giả mạo tên miền bằng cách cố tình viết sai chính tả gần giống tên miền thật)**.

* **Chi tiết trong email cho thấy đây là giả mạo:**
  1. **Tên miền bị làm nhái (Typosquatting):** Đường dẫn trong email là `https://githuh-security.com/verify`. Kẻ tấn công đã cố tình thay chữ `b` ở cuối từ `github` thành chữ `h` (`githuh`) và nối thêm cụm `-security.com` để đánh lừa mắt người dùng khi đọc lướt qua. Tên miền chính thức của GitHub chỉ có duy nhất là `github.com`.
  2. **Đánh vào tâm lý hoảng sợ và yêu cầu nhập lại mật khẩu qua link lạ:** Email dùng tiêu đề khẩn cấp ("Tài khoản của bạn đã bị khóa") nhằm thúc giục nạn nhân bấm ngay vào đường dẫn đính kèm rồi nhập mật khẩu. Trên thực tế, GitHub không bao giờ yêu cầu người dùng truy cập sang một tên miền khác để nhập mật khẩu mở khóa tài khoản.

### 2. Phân tích Tình huống 2 (Tải phần mềm Crack Adobe Photoshop 2026)

* **Tên cạm bẫy:** Đây là **Cạm bẫy Mã độc ngụy trang trong phần mềm bẻ khóa (Malware / Trojan / Infostealer ẩn trong bản Crack)**.

* **Vì sao yêu cầu "tắt Windows Defender trước khi giải nén" là dấu hiệu cực kỳ nguy hiểm?**
  * **Windows Defender** là lớp lá chắn bảo vệ thời gian thực mặc định của hệ điều hành Windows, có nhiệm vụ tự động quét và chặn đứng các tệp chứa mã độc ngay khi chúng vừa được giải nén hoặc kích hoạt.
  * Kẻ phát tán bản Crack thực chất đã gắn kèm mã độc (như mã độc đánh cắp mật khẩu Infostealer, mã độc tống tiền Ransomware hoặc Trojan chiếm quyền điều khiển) vào bên trong tệp cài đặt. Khi giải nén, Windows Defender phát hiện ra mã độc thật nên sẽ lập tức xóa hoặc cách ly tệp đó để bảo vệ máy.
  * Lời hướng dẫn *"tắt Windows Defender để tránh bị xóa nhầm"* thực chất là cái bẫy tâm lý nhằm **dụ người dùng tự tay tắt hệ thống phòng vệ của chính mình**. Ngay khi Windows Defender bị tắt và người dùng chạy tệp Crack, mã độc sẽ toàn quyền xâm nhập vào hệ điều hành, âm thầm lấy cắp mật khẩu trình duyệt, phiên đăng nhập GitHub và mã nguồn dự án mà không gặp bất kỳ sự ngăn cản nào.

### 3. Đối chiếu 2 tình huống với Quy tắc 5 KHÔNG

Để bảo vệ an toàn thông tin cá nhân và dự án, thành viên trong nhóm cần ghi nhớ **Quy tắc 5 KHÔNG** dành cho lập trình viên (1. KHÔNG bấm link lạ / nhập mật khẩu vào web chưa rõ tên miền; 2. KHÔNG cài phần mềm Crack / tắt diệt virus; 3. KHÔNG dùng chung mật khẩu cho nhiều nơi; 4. KHÔNG bỏ qua 2FA / chia sẻ mã OTP; 5. KHÔNG hardcode hoặc đẩy Secrets lên Git) và áp dụng cụ thể cho 2 tình huống như sau:

* **Đối với Tình huống 1:** Áp dụng nguyên tắc **KHÔNG bấm vào đường link lạ trong email/tin nhắn khả nghi và KHÔNG nhập mật khẩu vào trang web chưa kiểm tra kỹ tên miền**. Khi nhận được thông báo bảo mật, thành viên phải xóa/báo cáo email lừa đảo, tự mở trình duyệt và gõ trực tiếp địa chỉ chuẩn `https://github.com` để kiểm tra.

* **Đối với Tình huống 2:** Áp dụng nguyên tắc **KHÔNG tải, cài đặt phần mềm bẻ khóa (Crack) không rõ nguồn gốc và tuyệt đối KHÔNG tắt phần mềm bảo vệ máy tính (Windows Defender)**. Nếu cần thiết kế hình ảnh cho dự án, nhóm nên dùng bản dùng thử chính hãng, gói ưu đãi sinh viên hoặc các phần mềm miễn phí/mã nguồn mở an toàn (như Figma, Photopea, GIMP, Canva).

### 4. Thứ tự 4 Bước Cấp cứu khi lỡ tải và chạy file Crack ở Tình huống 2

Nếu bạn cùng nhóm đã lỡ tắt Windows Defender và chạy tệp Crack, cần thực hiện ngay lập tức **Quy trình Cấp cứu 4 Bước** theo đúng thứ tự ưu tiên sau:

1. **Bước 1 — Ngắt kết nối mạng ngay lập tức (Cô lập thiết bị):** Lập tức tắt Wi-Fi hoặc rút dây mạng LAN khỏi máy tính (có thể tắt nguồn máy nếu thấy dấu hiệu bất thường). Việc này giúp cắt đứt ngay đường truyền giữa mã độc trong máy với máy chủ của hacker, ngăn không cho mã độc tiếp tục gửi mật khẩu và dữ liệu ra ngoài.

2. **Bước 2 — Đổi mật khẩu và hủy phiên đăng nhập trên một thiết bị sạch khác:** Dùng một chiếc điện thoại hoặc một máy tính khác **hoàn toàn sạch (không bị nhiễm mã độc)** để đăng nhập vào Email, GitHub, Vercel và các tài khoản quan trọng nhằm đổi ngay mật khẩu mới, đồng thời bấm chọn *"Đăng xuất khỏi tất cả các thiết bị khác"* (Revoke all sessions) và hủy/cấp lại các API Key của dự án. Tuyệt đối không đổi mật khẩu ngay trên chiếc máy vừa nhiễm độc vì mã độc có thể đang ghi lén bàn phím (Keylogger).

3. **Bước 3 — Quét sạch mã độc hoặc cài đặt lại hệ điều hành (Làm sạch thiết bị):** Bật lại Windows Defender trên máy bị nhiễm (khi vẫn đang ngắt mạng) để quét toàn diện (Full Scan / Offline Scan) và xóa bỏ toàn bộ tệp Crack cùng các chương trình lạ mới cài vào. Để an toàn tuyệt đối cho môi trường lập trình, phương án tốt nhất sau khi nhiễm mã độc từ bản Crack là sao lưu các tệp tài liệu thuần và cài đặt lại mới hoàn toàn hệ điều hành Windows.

4. **Bước 4 — Kiểm tra nhật ký bảo mật và thiết lập lại 2FA:** Kiểm tra lịch sử đăng nhập và nhật ký hoạt động (Security Log) trên GitHub, Email, Vercel xem hacker đã kịp thêm khóa truy cập lạ hay chỉnh sửa mã nguồn chưa; đồng thời bật hoặc tạo lại Xác thực 2 Yếu tố (2FA) trên toàn bộ tài khoản.

## PHẦN 2 – CHUYỂN SANG PASSWORD MANAGER

### 1. Hậu quả của việc dùng chung một mật khẩu và tên kiểu tấn công

* **Điều gì xảy ra nếu email nhóm bị lộ mật khẩu?**
  Theo ghi chú ở mục 3c, cả nhóm đang dùng chung duy nhất một mật khẩu `SmartCampus2026!` cho cả 3 nơi: Email nhóm, GitHub tổ chức và Vercel deploy. Nếu mật khẩu của Email nhóm bị lộ, kẻ tấn công sẽ lập tức thử dùng chính mật khẩu `SmartCampus2026!` đó để đăng nhập vào tài khoản **GitHub tổ chức** và **Vercel deploy**. Kết quả là cả 2 tài khoản còn lại sẽ bị chiếm đoạt ngay lập tức theo **Hiệu ứng Domino (Domino Effect)** — hacker vừa xóa hoặc đánh cắp được toàn bộ mã nguồn trên GitHub, vừa chiếm quyền điều khiển trang web đang chạy trên Vercel.

* **Tên kiểu tấn công có thể xảy ra:** Đây chính là tấn công **Credential Stuffing (Tấn công nhồi thông tin đăng nhập)** — hình thức kẻ tấn công lấy cặp tên đăng nhập và mật khẩu bị rò rỉ từ một dịch vụ này để tự động mang đi đăng nhập thử hàng loạt trên các dịch vụ khác.

### 2. Vì sao Zero-Knowledge Architecture giúp dữ liệu an toàn kể cả khi máy chủ Bitwarden bị hacker xâm nhập?

Kiến trúc **Zero-Knowledge (Không-Biết-Gì)** đảm bảo rằng nhà cung cấp dịch vụ (Bitwarden) hoàn toàn không biết mật khẩu chính (Master Passphrase) cũng như nội dung mật khẩu lưu bên trong két sắt của người dùng.

Cụ thể, mọi mật khẩu của nhóm đều được **mã hóa thành chuỗi ký tự vô nghĩa (Ciphertext) bằng thuật toán AES-256 bit ngay trên máy tính/điện thoại của thành viên (Client-side Encryption)** trước khi được gửi lên đám mây. Chìa khóa để giải mã được tạo ra từ Master Passphrase và không bao giờ rời khỏi thiết bị của người dùng. Do đó, kể cả khi hacker tấn công và lấy cắp được cơ sở dữ liệu trên máy chủ Bitwarden, chúng cũng chỉ thu được các khối dữ liệu đã bị khóa chặt bằng chuẩn AES-256 mà không có chìa khóa giải mã, nên mật khẩu của nhóm vẫn an toàn tuyệt đối.

### 3. Bảng thông số cấu hình công cụ Generator để tạo 3 mật khẩu mới, riêng biệt

Để thay thế mật khẩu dùng chung cũ, nhóm sử dụng công cụ Password Generator trong trình quản lý mật khẩu để sinh ra **3 mật khẩu hoàn toàn khác nhau** cho GitHub, Vercel và Email nhóm theo bảng cấu hình sau:

| Thông số | Giá trị cấu hình |
| ----- | ----- |
| **Độ dài** | **20 ký tự** (hoặc trong khoảng **16 – 32 ký tự**) |
| **Chữ hoa (A–Z)** | **Bật (Có)** — Bao gồm các chữ cái in hoa từ A đến Z |
| **Chữ thường (a–z)** | **Bật (Có)** — Bao gồm các chữ cái in thường từ a đến z |
| **Chữ số (0–9)** | **Bật (Có)** — Bao gồm các chữ số từ 0 đến 9 (tối thiểu 2 – 3 chữ số) |
| **Ký tự đặc biệt** | **Bật (Có)** — Bao gồm các ký tự đặc biệt `!@#$%^&*` (tối thiểu 2 – 3 ký tự) |

*(Lưu ý khi thực hiện: Sau khi thiết lập cấu hình trên, bấm nút tạo mới 3 lần riêng biệt để lấy 3 chuỗi mật khẩu ngẫu nhiên hoàn toàn độc lập cho từng tài khoản GitHub tổ chức, Vercel và Email nhóm).*

## PHẦN 3 – KÍCH HOẠT 2FA CHO TÀI KHOẢN GITHUB TỔ CHỨC

### 1. Vì sao nên dùng Authenticator App (TOTP) thay vì SMS OTP? (2 nhược điểm của SMS OTP)

Trưởng nhóm không nên dùng SMS OTP mà cần chuyển sang dùng **Authenticator App (thuật toán TOTP)** vì ứng dụng Authenticator tự sinh mã 6 số ngay trên điện thoại dựa vào Khóa bí mật (Shared Secret) và thời gian thực (đổi mã mỗi 30 giây), giúp khắc phục hoàn toàn **2 nhược điểm lớn của SMS OTP** sau đây:

1. **Kém an toàn trước tấn công chiếm đoạt SIM (SIM Swapping) và nghe lén mạng viễn thông:** Với SMS OTP, kẻ xấu có thể dùng kỹ nghệ xã hội (Social Engineering) lừa nhà mạng cấp lại SIM mới để cướp số điện thoại của trưởng nhóm (SIM Swapping), hoặc lợi dụng lỗ hổng giao thức viễn thông SS7 để chặn đọc tin nhắn SMS không được mã hóa đầu cuối trên đường truyền sóng di động.
2. **Phụ thuộc vào sóng nhà mạng và không dùng được khi Offline:** Khi trưởng nhóm ở khu vực mất sóng di động (tầng hầm, vùng sâu), đang ngồi trên máy bay bật Chế độ Máy bay, đi nước ngoài chưa mở chuyển vùng quốc tế hoặc khi nhà mạng bị nghẽn tin nhắn, SMS OTP sẽ không thể gửi về máy, làm cả nhóm không thể đăng nhập vào GitHub. Trong khi đó, ứng dụng Authenticator hoạt động 100% không cần mạng hay sóng SIM.

### 2. Thứ tự các bước kích hoạt 2FA bằng Google Authenticator cho tài khoản GitHub

Quy trình bật xác thực 2 yếu tố (2FA) trên GitHub bằng ứng dụng Google Authenticator gồm 5 bước theo đúng thứ tự sau:

1. **Bước 1 — Mở cài đặt bảo mật trên GitHub:** Đăng nhập vào tài khoản GitHub, bấm vào ảnh đại diện ở góc trên bên phải màn hình, chọn **Settings**, sau đó nhìn thanh menu bên trái và chọn mục **Password and authentication** (trong phần *Access*).
2. **Bước 2 — Khởi động thiết lập 2FA bằng ứng dụng:** Tại mục **Two-factor authentication**, bấm vào nút **Enable two-factor authentication** (nếu hệ thống yêu cầu xác nhận lại mật khẩu GitHub thì nhập mật khẩu hiện tại vào), sau đó chọn phương thức **Set up using an app** (Thiết lập bằng ứng dụng xác thực).
3. **Bước 3 — Quét mã QR trên ứng dụng Google Authenticator:** Mở ứng dụng **Google Authenticator** trên điện thoại, bấm vào nút dấu cộng (`+`) ở góc dưới màn hình, chọn **Quét mã QR (Scan a QR code)** và đưa camera điện thoại quét mã QR đang hiển thị trên trang cài đặt của GitHub.
4. **Bước 4 — Nhập mã 6 số để xác nhận liên kết:** Ngay sau khi quét mã QR, ứng dụng Google Authenticator sẽ hiển thị một **mã OTP gồm 6 chữ số** (kèm vòng tròn đếm ngược 30 giây). Nhập chính xác 6 chữ số này vào ô **Verify the code from the app** trên màn hình GitHub.
5. **Bước 5 — Lưu mã khôi phục dự phòng và hoàn tất:** Tải xuống hoặc chép lại bộ **Mã khôi phục (Recovery Codes)** mà GitHub cung cấp ra nơi an toàn, sau đó bấm nút **I have saved my recovery codes** để hoàn tất việc kích hoạt 2FA.

### 3. Nơi nên lưu trữ và nơi không nên lưu 10 mã khôi phục dự phòng (Recovery Codes)

* **Nơi NÊN lưu trữ bộ 10 mã khôi phục dự phòng:**
  1. Lưu vào mục **Ghi chú bảo mật (Secure Note)** bên trong Két sắt mật khẩu chuyên dụng có mã hóa (như **Bitwarden**).
  2. **In ra giấy hoặc ghi chép tay** rồi cất giữ trong két sắt vật lý hoặc ngăn tủ có khóa kín tại nhà riêng (tách biệt với túi đựng điện thoại hàng ngày).

* **Nơi KHÔNG NÊN lưu trữ bộ mã này:**
  1. **Không** chụp ảnh màn hình (Screenshot) lưu trong thư viện ảnh của chính chiếc điện thoại cài ứng dụng Authenticator (vì nếu mất hoặc hỏng điện thoại sẽ mất luôn cả ứng dụng lẫn ảnh chụp mã khôi phục).
  2. **Không** lưu thành tệp văn bản không mã hóa (như `recovery.txt`, file Word, Notepad) để hớ hênh trên màn hình Desktop máy tính, **không** gửi qua tin nhắn mạng xã hội (Zalo, Messenger) và **tuyệt đối không** để tệp chứa mã khôi phục nằm trong thư mục code đẩy lên GitHub.

## PHẦN 4 – BẢO VỆ SECRETS TRƯỚC KHI PUSH CODE

### 1. Chỉ ra chính xác 2 giá trị Secrets đang bị hardcode trong file `config.js`

Từ đoạn code ở mục 3b, 2 giá trị thông tin nhạy cảm (Secrets) đang bị viết cứng (hardcode) trực tiếp trong mã nguồn là:

1. Giá trị khóa API (`API_KEY`): **`"sk-proj-abc123456789"`**
2. Giá trị mật khẩu cơ sở dữ liệu (`DB_PASSWORD`): **`"SmartCampus@2026"`**

### 2. Viết lại đoạn code `config.js` đúng chuẩn (đọc qua `process.env`)

Đoạn mã trong file `config.js` sau khi loại bỏ hoàn toàn các giá trị thật và chuyển sang đọc từ biến môi trường:

```javascript
const API_KEY = process.env.API_KEY;
const DB_PASSWORD = process.env.DB_PASSWORD;

function connectDatabase() {
  return connect(DB_PASSWORD);
}
```

### 3. Nội dung đầy đủ của 3 file: `.env`, `.gitignore` và `.env.example`

**a) Nội dung file `.env` (chứa giá trị thật, chỉ lưu trên máy cá nhân để chạy chương trình):**

```env
API_KEY=sk-proj-abc123456789
DB_PASSWORD=SmartCampus@2026
```

**b) Nội dung file `.gitignore` (chặn Git không cho đẩy file `.env` lên GitHub):**

```gitignore
# Bỏ qua file chứa biến môi trường thật (Secrets)
.env
.env.local
.env.*.local

# Bỏ qua thư mục cài đặt thư viện
node_modules/
```

**c) Nội dung file `.env.example` (chỉ chứa tên biến làm mẫu chia sẻ an toàn lên GitHub cho các thành viên khác):**

```env
API_KEY=
DB_PASSWORD=
```

### 4. Áp dụng Quy tắc 4 Bước Kiểm tra trước khi Push (Pre-push Checklist)

Trước khi chạy lệnh `git push` lần cuối để đưa dự án SmartCampus lên kho GitHub công khai (Public Repository), người rà soát an toàn thông tin cần thực hiện tuần tự **4 Bước Kiểm tra** sau:

1. **Bước 1 — Kiểm tra lại toàn bộ mã nguồn (Soát lỗi Hardcode trong Code):** Mở kiểm tra file `config.js` và rà soát toàn bộ các file code trong dự án (có thể dùng công cụ tìm kiếm từ khóa như `sk-proj`, `PASSWORD`, `SECRET`, `KEY`) để chắc chắn không còn bất kỳ mật khẩu hay khóa API thật nào nằm trực tiếp trong code; tất cả đều phải được gọi qua `process.env`.

2. **Bước 2 — Kiểm tra nội dung file `.gitignore` và `.env.example`:**
   * Đảm bảo file `.gitignore` đã được tạo ở thư mục gốc của dự án và có ghi chính xác dòng `.env`.
   * Mở file `.env.example` kiểm tra để chắc chắn sau dấu `=` hoàn toàn để trống (không chứa giá trị thật).

3. **Bước 3 — Kiểm tra vùng chờ Commit bằng lệnh `git status` và `git diff`:**
   * Chạy lệnh `git status` trên Terminal để xem danh sách các file sắp được đưa vào Commit: tuyệt đối **không được có mặt file `.env`** trong danh sách này.
   * Chạy lệnh `git diff` (hoặc `git diff --staged`) để đọc lại từng dòng code thay đổi lần cuối trước khi đóng gói commit.

4. **Bước 4 — Kiểm tra lịch sử Commit (`git log`) và thu hồi khóa cũ nếu từng lỡ Commit:**
   * Kiểm tra lịch sử các lần commit trước đó bằng lệnh `git log` để xem có thành viên nào từng lỡ đẩy file `.env` hoặc đoạn code chứa `"sk-proj-abc123456789"` và `"SmartCampus@2026"` vào các commit cũ hay không.
   * Nếu các giá trị này từng xuất hiện trong lịch sử commit cũ (Git History), dù commit mới đã xóa đi thì người ngoài vẫn xem lại được trong lịch sử trên GitHub Public; khi đó bắt buộc phải xóa sạch lịch sử chứa Secret (hoặc khởi tạo lại kho Git sạch) và **đổi ngay mật khẩu Database mới + hủy/tạo lại API Key mới** trước khi công khai dự án.
