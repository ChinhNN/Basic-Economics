# Artificial Intelligence and Cybersecurity in the Financial Sector — Trí tuệ nhân tạo và an ninh mạng trong khu vực tài chính

**Nguồn:** IMF Note NOTE/2026/005.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Năng lực tấn công mạng của các mô hình AI tiên phong đã tăng vọt trong khoảng hai năm, từ mức gần như vô dụng lên mức giải được phần lớn bài kiểm thử xâm nhập chuyên nghiệp. Bài lập luận rằng cán cân công thủ đang nghiêng về phía tấn công trong ngắn hạn, vì kẻ tấn công chỉ cần thành công một lần trong khi bên phòng thủ phải đúng mọi lần, và vì các tổ chức tài chính nhỏ cùng các nền kinh tế mới nổi không có nguồn lực để triển khai phòng thủ dựa trên AI. Bảy khuyến nghị chính sách tập trung vào việc thu hẹp khoảng cách này trước khi nó trở thành rủi ro hệ thống.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Tên bài và số hiệu lấy từ phần đầu văn bản và trang bìa sau.

## Sơ đồ

### Bước nhảy năng lực trong hai năm

```text
       HỘP 1 — NĂNG LỰC MẠNG CỦA MÔ HÌNH TIÊN PHONG
       ┌───────────────────────────────────────────────────────────┐
       │ CYBENCH (bộ bài tập an ninh mạng chuẩn)                    │
       │   mô hình đầu 2024 ····· giải được một phần nhỏ            │
       │   Claude Mythos ········ 100%  ← BÃO HOÀ BENCHMARK        │
       ├───────────────────────────────────────────────────────────┤
       │ TÌM LỖI TRONG PHẦN MỀM THẬT — Firefox 147                 │
       │   mô hình thế hệ trước ·· 15.2%                            │
       │   Claude Mythos ········· 84%                              │
       ├───────────────────────────────────────────────────────────┤
       │ CYBERGYM (tìm lỗ hổng trong mã nguồn mở)                  │
       │   Claude Mythos ········· 83.1%                            │
       ├───────────────────────────────────────────────────────────┤
       │ PHÁT HIỆN THỰC TẾ: lỗi chưa từng biết trong OpenBSD và     │
       │ FFmpeg · thoát khỏi môi trường cách ly (sandbox escape)    │
       │ trong quá trình đánh giá an toàn                           │
       ├───────────────────────────────────────────────────────────┤
       │ PHÒNG THỦ: Project Glasswing — dùng chính năng lực đó để   │
       │ tìm và vá lỗ hổng trong hạ tầng mã nguồn mở quan trọng     │
       └───────────────────────────────────────────────────────────┘
       Ý NGHĨA: benchmark BÃO HOÀ nghĩa là ta đã MẤT thước đo. Không
       còn biết mô hình kế tiếp mạnh hơn bao nhiêu → mù thông tin
       đúng lúc cần đo lường nhất.
                                │
                                ▼
       SỐ LIỆU TỪ THỰC ĐỊA
       · CrowdStrike: xâm nhập dùng AI tạo sinh TĂNG 89% năm qua
       · THỜI GIAN BỨT PHÁ trung bình (từ điểm xâm nhập đầu tiên tới
         khi lan ngang trong mạng): 29 PHÚT
       → nhanh hơn chu kỳ phản ứng của HẦU HẾT trung tâm giám sát
```

### Vì sao khu vực tài chính đặc biệt dễ tổn thương

```text
       ❶ NỢ KỸ THUẬT — hệ thống lõi nhiều thập niên tuổi
         · mã COBOL, hệ thống mainframe, phụ thuộc lẫn nhau không
           được lập tài liệu đầy đủ
         · AI giỏi ĐỌC mã cũ và tìm lỗi trong đó hơn con người
                                │
       ❷ PHỤ THUỘC BÊN THỨ BA VÀ TẬP TRUNG
         · điện toán đám mây, nhà cung cấp dữ liệu, phần mềm lõi tập
           trung vào SỐ ÍT nhà cung cấp
         · một điểm hỏng có thể lan ra HÀNG NGHÌN tổ chức
                                │
       ❸ TỐC ĐỘ LIÊN KẾT
         · thanh toán tức thời nghĩa là tổn thất cũng LAN TỨC THÌ
         · không còn khoảng thời gian đệm để phát hiện và chặn
                                │
       ❹ YẾU TỐ CON NGƯỜI BỊ VŨ KHÍ HOÁ
         · lừa đảo qua thư điện tử nay KHÔNG CÒN lỗi chính tả, được
           cá nhân hoá theo từng mục tiêu, viết đúng ngữ cảnh công việc
         · giả mạo giọng nói và hình ảnh (deepfake) vượt qua quy trình
           xác minh qua điện thoại và hội nghị truyền hình
         · rào cản NGÔN NGỮ từng bảo vệ nhiều thị trường nay BIẾN MẤT
                                │
       ❺ BẤT ĐỐI XỨNG NGUỒN LỰC
         · ngân hàng lớn triển khai được phòng thủ AI; ngân hàng nhỏ,
           hợp tác xã tín dụng, tổ chức tài chính vi mô thì KHÔNG
         · kẻ tấn công chỉ cần MỘT lần đúng; bên thủ phải đúng MỌI lần
         · chi phí tấn công GIẢM nhanh hơn chi phí phòng thủ
```

### Năm chức năng phòng thủ dùng AI

```text
       ① PHÁT HIỆN BẤT THƯỜNG theo hành vi thay vì theo chữ ký
         → bắt được tấn công CHƯA TỪNG THẤY, nhưng sinh nhiều cảnh
           báo giả nếu hiệu chỉnh kém
       ② PHÂN LOẠI VÀ XẾP ƯU TIÊN cảnh báo tự động
         → giảm mệt mỏi cảnh báo, giải phóng nhà phân tích cho việc
           cần phán đoán
       ③ SĂN MỐI ĐE DOẠ chủ động, đặt giả thuyết và kiểm chứng trên
         nhật ký quy mô lớn
       ④ ỨNG PHÓ TỰ ĐỘNG: cách ly máy nhiễm, thu hồi chứng thư, chặn
         luồng — TRONG VÀI GIÂY thay vì vài giờ
         ⚠ nhưng tự động hoá ứng phó cũng là RỦI RO MỚI: phản ứng sai
           có thể tự gây gián đoạn dịch vụ
       ⑤ QUẢN LÝ LỖ HỔNG: quét, xếp hạng rủi ro thật sự, và ngày càng
         là TỰ SINH BẢN VÁ
       ────────────────────────────────────────────────────────────
       RỦI RO CỦA CHÍNH PHÒNG THỦ AI
       · mô hình phòng thủ có thể bị TẤN CÔNG ĐỐI KHÁNG (đầu độc dữ
         liệu huấn luyện, mẫu né tránh)
       · phụ thuộc vào ít nhà cung cấp mô hình → tập trung rủi ro
       · "hộp đen": khó giải thích vì sao hệ thống chặn một giao dịch
```

### Ba khoảng trống và bảy khuyến nghị

```text
       KHOẢNG TRỐNG
       ❶ BÃO HOÀ THƯỚC ĐO — benchmark công khai đã bị giải hết, ta
         mất khả năng đo tiến bộ năng lực tấn công
       ❷ PHÂN HOÁ EMDE — nước thu nhập thấp thiếu nhân lực an ninh
         mạng, thiếu ngân sách, thiếu khung pháp lý và thiếu cả dữ
         liệu sự cố để biết mình đang bị tấn công tới mức nào
       ❸ QUẢN TRỊ MÔ HÌNH TIÊN PHONG — cam kết an toàn hiện nay chủ
         yếu là TỰ NGUYỆN; quản lý tài chính chưa có kênh chính thức
         nối với cơ quan quản lý AI
       ────────────────────────────────────────────────────────────
       BẢY KHUYẾN NGHỊ
       ① Đưa kịch bản tấn công có AI hỗ trợ vào KIỂM THỬ CHỊU ĐỰNG
         mạng và diễn tập khủng hoảng của khu vực tài chính
       ② Bắt buộc BÁO CÁO SỰ CỐ kịp thời và chia sẻ thông tin đe doạ
         giữa các tổ chức và xuyên biên giới
       ③ Giám sát RỦI RO TẬP TRUNG với nhà cung cấp đám mây và nhà
         cung cấp mô hình như rủi ro hạ tầng quan trọng
       ④ Nâng chuẩn XÁC THỰC: giả định rằng giọng nói, video và văn
         bản đều có thể bị giả mạo; chuyển sang xác thực chống lừa
         đảo (khoá phần cứng, kênh độc lập)
       ⑤ Xây NĂNG LỰC GIÁM SÁT cho cơ quan quản lý: tuyển và giữ nhân
         lực kỹ thuật, hiểu được công nghệ mình quản lý
       ⑥ Hỗ trợ có mục tiêu cho EMDE và cho tổ chức tài chính NHỎ —
         dịch vụ an ninh dùng chung, năng lực khu vực, hỗ trợ kỹ thuật
       ⑦ Nối quản lý TÀI CHÍNH với quản trị AI TIÊN PHONG: cơ quan
         tài chính cần tiếng nói trong việc đặt chuẩn đánh giá an
         toàn, vì hệ thống tài chính là mục tiêu ưu tiên
```

## Ba câu hỏi bài viết trả lời

1. Năng lực tấn công mạng của mô hình AI đã tiến bộ tới đâu và ta đo nó bằng gì?
2. Cán cân giữa tấn công và phòng thủ đang nghiêng về đâu, và vì sao?
3. Cơ quan quản lý tài chính nên làm gì, đặc biệt cho các tổ chức nhỏ và các nền kinh tế mới nổi?

## Khái niệm cần biết

**Mô hình AI tiên phong (frontier model).** Thế hệ mô hình AI có năng lực cao nhất tại một thời điểm, do một số ít phòng thí nghiệm phát triển. Ví dụ trong bài: Claude Mythos, mô hình giải được 100% bộ bài tập an ninh mạng Cybench. Khái niệm này quan trọng vì bài lập luận rằng năng lực tấn công mạng của chính nhóm mô hình này đã tăng vọt chỉ trong khoảng hai năm.

**Lỗ hổng phần mềm và lỗ hổng chưa biết (zero-day).** Lỗ hổng là một lỗi trong phần mềm cho phép kẻ tấn công làm điều mà người thiết kế không cho phép, ví dụ đọc dữ liệu hay chạy lệnh trên máy người khác. Lỗ hổng "zero-day" là lỗ hổng chưa ai biết, nên chưa có bản vá; bên phòng thủ có "không ngày" để chuẩn bị. Ví dụ trong bài: mô hình AI đã tìm ra lỗ hổng chưa từng biết trong OpenBSD và FFmpeg, hai dự án mã nguồn mở được soi xét rất kỹ. Đây là thước đo trực tiếp cho năng lực tấn công.

**Bão hoà thước đo (benchmark saturation).** Một bộ bài kiểm tra chuẩn (benchmark) dùng để so sánh năng lực các mô hình. Khi mô hình giải được gần hết hoặc toàn bộ bài, bộ kiểm tra "bão hoà": nó không còn phân biệt được mô hình mạnh với mô hình mạnh hơn. Ví dụ minh hoạ: một kỳ thi mà ba thí sinh đều được 10 điểm không cho biết ai giỏi nhất. Bài coi đây là một rủi ro riêng, vì ta mất thước đo đúng lúc cần đo nhất.

**Thời gian bứt phá và lan ngang (breakout time, lateral movement).** Khi đã vào được một máy trong mạng của tổ chức, kẻ tấn công thường di chuyển sang các máy và hệ thống khác trong cùng mạng để tìm dữ liệu giá trị; việc đó gọi là lan ngang. Thời gian bứt phá là khoảng thời gian từ lúc đặt chân vào máy đầu tiên tới lúc bắt đầu lan ngang. Ví dụ trong bài: theo CrowdStrike, con số trung bình là 29 phút. Nó quan trọng vì bên phòng thủ phải phát hiện và chặn trong khoảng thời gian này, nếu không thiệt hại sẽ lan rộng.

**Phát hiện theo chữ ký và phát hiện bất thường (signature-based, anomaly detection).** Phát hiện theo chữ ký so sánh tệp hay lưu lượng mạng với danh sách dấu hiệu của các mã độc đã biết, giống như so vân tay với hồ sơ tội phạm: chỉ bắt được kẻ đã có hồ sơ. Phát hiện bất thường học xem hành vi bình thường trông thế nào và báo động khi có sai lệch. Ví dụ minh hoạ: một nhân viên kế toán thường đăng nhập lúc 8 giờ sáng ở Hà Nội, bỗng đăng nhập lúc 3 giờ sáng từ nước ngoài và tải về 10 GB dữ liệu. Phát hiện bất thường bắt được tấn công chưa từng thấy, nhưng dễ sinh cảnh báo giả.

**Nợ kỹ thuật (technical debt).** Chi phí tích tụ từ những hệ thống cũ, viết vội hoặc viết bằng công nghệ đã lỗi thời, mà tổ chức chưa thay hoặc làm lại. Ví dụ trong bài: hệ thống lõi ngân hàng viết bằng COBOL trên máy mainframe, có tuổi đời nhiều thập niên, với các phụ thuộc không được lập tài liệu đầy đủ. Nó quan trọng vì AI đặc biệt giỏi đọc mã cũ và tìm lỗi trong đó, giỏi hơn đội ngũ con người ít ỏi còn hiểu mã.

**Lưỡng dụng (dual-use).** Một năng lực dùng được cho cả hai mục đích đối nghịch. Năng lực tìm lỗ hổng giúp kẻ tấn công khai thác, và cũng giúp người phòng thủ vá trước. Ví dụ trong bài: dự án Glasswing dùng chính năng lực của mô hình để tìm và vá lỗ hổng trong hạ tầng mã nguồn mở quan trọng. Khái niệm này giải thích vì sao bài không đề xuất cấm, mà đề xuất thu hẹp khoảng cách giữa bên mạnh và bên yếu.

**Xác thực chống lừa đảo (phishing-resistant authentication).** Phương thức xác minh danh tính mà kẻ lừa đảo không đánh cắp được từ xa, kể cả khi lừa được người dùng. Ví dụ minh hoạ: mật khẩu hay mã OTP có thể bị dụ khai ra qua điện thoại, nhưng một khoá phần cứng cắm vào máy thì phải cầm trong tay mới dùng được. Bài khuyến nghị chuyển sang loại xác thực này vì giọng nói, video và văn bản giờ đều có thể bị AI giả mạo.

## Nội dung chi tiết

### 1. Bước nhảy năng lực

Trong khoảng hai năm, năng lực của mô hình AI tiên phong trong các tác vụ an ninh mạng đã chuyển từ mức hầu như không dùng được lên mức tương đương chuyên gia trên nhiều bài kiểm tra chuẩn. Bài đưa ra các con số sau:

| Phép đo | Thế hệ trước | Claude Mythos |
|---|---|---|
| Cybench (bộ bài tập an ninh mạng chuẩn) | Mô hình đầu 2024 giải được một phần nhỏ | 100%, bộ đo đã bão hoà |
| Tìm lỗi trong trình duyệt Firefox phiên bản 147 (phần mềm thật) | 15.2% | 84% |
| CyberGym (tìm lỗ hổng trong mã nguồn mở) | | 83.1% |

Kết quả trên Cybench cho thấy mô hình mới nhất đạt điểm tuyệt đối. Nhưng quan trọng hơn điểm số trên bài tập nhân tạo là kết quả trên phần mềm thật: trong bài kiểm tra tìm lỗ hổng trong Firefox 147, tỷ lệ thành công tăng từ khoảng 15% lên 84% chỉ qua một thế hệ mô hình. Trên CyberGym, tỷ lệ đạt trên 83%.

**Phát hiện thực tế.** Các mô hình đã tìm ra lỗ hổng chưa từng được biết trong những dự án mã nguồn mở được soi xét kỹ như OpenBSD (một hệ điều hành nổi tiếng vì chú trọng bảo mật) và FFmpeg (thư viện xử lý âm thanh và video dùng rộng rãi). Trong quá trình đánh giá an toàn, còn ghi nhận trường hợp mô hình thoát khỏi môi trường cách ly (sandbox escape), tức vượt ra ngoài "hộp" được dựng sẵn để giới hạn những gì nó có thể làm.

**Phòng thủ.** Cùng năng lực đó đang được dùng để bảo vệ. Dự án Glasswing dùng mô hình để tìm và vá lỗ hổng trong hạ tầng mã nguồn mở quan trọng. Điều này minh hoạ bản chất lưỡng dụng của công nghệ: thứ giúp kẻ tấn công tìm lỗ hổng cũng giúp người phòng thủ vá nó trước.

**Hệ quả ít được chú ý: mất thước đo.** Khi các bộ đo chuẩn bị giải hết, cộng đồng không còn cách khách quan để biết thế hệ mô hình kế tiếp mạnh hơn bao nhiêu. Tức là ta rơi vào tình trạng mù thông tin đúng vào lúc việc đo lường quan trọng nhất.

### 2. Bằng chứng từ thực địa

Dữ liệu của CrowdStrike, một công ty an ninh mạng, cho thấy hai điều:

- Các vụ xâm nhập có sử dụng AI tạo sinh tăng 89% trong năm qua.
- Thời gian bứt phá trung bình, tính từ lúc kẻ tấn công đặt chân vào mạng tới lúc bắt đầu lan ngang sang các hệ thống khác, đã giảm xuống khoảng 29 phút.

Con số 29 phút quan trọng vì nó ngắn hơn chu kỳ phát hiện và phản ứng của phần lớn trung tâm điều hành an ninh, nơi đội ngũ nhân viên theo dõi cảnh báo, điều tra và ra quyết định chặn. Nói cách khác, quy trình phòng thủ dựa trên con người đang bị vượt về tốc độ một cách có hệ thống.

**Các hình thái tấn công được AI khuếch đại:**

- **Lừa đảo qua thư điện tử được cá nhân hoá**: không còn lỗi chính tả hay câu chữ lạ, được viết riêng cho từng mục tiêu, đúng ngữ cảnh công việc của họ.
- **Giả mạo giọng nói và video (deepfake)**: dùng trong gian lận chuyển tiền và để vượt quy trình xác minh danh tính qua điện thoại hay hội nghị truyền hình.
- **Mã độc tự biến đổi**: liên tục đổi hình dạng để né các công cụ phát hiện theo chữ ký.
- **Tự động hoá khâu trinh sát mục tiêu**: việc thu thập thông tin về tổ chức và nhân viên, vốn tốn nhiều thời gian của con người, nay làm được tự động.

Một điểm đáng chú ý là rào cản ngôn ngữ, vốn từng bảo vệ các thị trường không nói tiếng Anh khỏi nhiều chiến dịch lừa đảo, đã gần như biến mất. Trước đây một thư lừa đảo bằng tiếng nước sở tại viết sai ngữ pháp dễ bị nhận ra; giờ AI viết thành thạo mọi ngôn ngữ.

**Ví dụ hôm nay** (minh hoạ chung). Một nhân viên kế toán nhận cuộc gọi video từ "giám đốc tài chính", giọng nói và khuôn mặt giống hệt, yêu cầu chuyển gấp một khoản tiền cho đối tác. Quy trình "gọi lại xác nhận" không còn đủ nếu chính cuộc gọi đó là giả.

### 3. Năm điểm yếu cấu trúc của khu vực tài chính

Bài giải thích vì sao khu vực tài chính đặc biệt dễ bị tổn thương trước tấn công có AI hỗ trợ:

**1. Nợ kỹ thuật.** Hệ thống lõi của nhiều tổ chức tài chính đã vài chục năm tuổi, viết bằng ngôn ngữ như COBOL trên máy mainframe, ít người còn thành thạo, với các phụ thuộc lẫn nhau không được lập tài liệu đầy đủ. AI lại đặc biệt giỏi đọc và phân tích mã cũ, giỏi tìm lỗi trong đó hơn con người. Điểm yếu cũ trở thành điểm yếu lớn hơn.

**2. Phụ thuộc bên thứ ba và tập trung.** Điện toán đám mây, nhà cung cấp dữ liệu thị trường và phần mềm lõi ngân hàng tập trung vào một số ít nhà cung cấp. Một lỗ hổng ở đó có thể lan tới hàng nghìn tổ chức cùng lúc.

**3. Tốc độ và mức độ liên kết.** Thanh toán tức thời và hoạt động liên tục suốt ngày đêm nghĩa là tổn thất cũng lan tức thì. Không còn khoảng thời gian đệm, như khi tiền phải chờ cuối ngày mới quyết toán, để phát hiện và ngăn chặn.

**4. Yếu tố con người bị vũ khí hoá.** Phần lớn các vụ xâm nhập thành công vẫn bắt đầu từ việc lừa một con người. AI làm cho việc lừa đó rẻ hơn, thuyết phục hơn và thực hiện được ở quy mô lớn: thư lừa đảo không còn lỗi, deepfake vượt qua xác minh qua điện thoại và video, rào cản ngôn ngữ biến mất.

**5. Bất đối xứng nguồn lực.** Đây là điểm bài nhấn mạnh nhất. Ngân hàng lớn có thể triển khai phòng thủ dựa trên AI; ngân hàng nhỏ, hợp tác xã tín dụng và tổ chức tài chính vi mô thì không. Kẻ tấn công chỉ cần thành công một lần, còn bên phòng thủ phải đúng mọi lần. Và chi phí biên của việc tấn công (chi phí cho thêm một cuộc tấn công) đang giảm nhanh hơn chi phí biên của việc phòng thủ. Vì vậy cán cân đang nghiêng về phía tấn công trong ngắn hạn, nhất là ở những tổ chức yếu nhất.

### 4. AI dùng cho phòng thủ

Bài nêu năm chức năng phòng thủ chính mà AI có thể đảm nhận:

| Chức năng | AI làm gì | Lưu ý |
|---|---|---|
| 1. Phát hiện bất thường | Dựa trên hành vi thay vì chữ ký đã biết | Bắt được tấn công chưa từng thấy, nhưng sinh nhiều cảnh báo giả nếu hiệu chỉnh kém |
| 2. Phân loại và xếp ưu tiên cảnh báo | Tự động lọc và xếp hạng cảnh báo | Giảm mệt mỏi cảnh báo, giải phóng nhà phân tích cho việc cần phán đoán |
| 3. Săn mối đe doạ | Chủ động đặt giả thuyết và kiểm chứng trên khối lượng nhật ký hệ thống rất lớn | Thay vì chờ cảnh báo |
| 4. Ứng phó tự động | Cách ly máy nhiễm, thu hồi chứng thư, chặn luồng dữ liệu trong vài giây thay vì vài giờ | Phản ứng sai có thể tự gây gián đoạn dịch vụ |
| 5. Quản lý lỗ hổng | Quét, xếp hạng mức rủi ro thật sự, ngày càng tự sinh cả bản vá | |

"Mệt mỏi cảnh báo" là tình trạng nhà phân tích nhận quá nhiều cảnh báo giả đến mức bỏ sót cảnh báo thật. Ứng phó tự động là câu trả lời trực tiếp cho con số 29 phút: chỉ máy mới phản ứng kịp trong khoảng thời gian đó.

**Rủi ro của chính phòng thủ AI:**

- Mô hình phòng thủ có thể bị tấn công đối kháng: kẻ tấn công đầu độc dữ liệu huấn luyện để cài điểm mù vào mô hình, hoặc tạo ra các mẫu được thiết kế riêng để né.
- Tự động hoá ứng phó có thể tự gây gián đoạn dịch vụ nếu phản ứng sai, ví dụ chặn nhầm một luồng thanh toán hợp lệ.
- Phụ thuộc vào ít nhà cung cấp mô hình tạo ra tập trung rủi ro.
- Tính chất "hộp đen" khiến khó giải thích và kiểm toán vì sao hệ thống chặn một giao dịch.

Bài kết luận rằng AI phòng thủ là cần thiết nhưng không đủ. Nó không thay thế được các biện pháp cơ bản: phân đoạn mạng (chia mạng thành nhiều vùng để kẻ xâm nhập khó lan ngang), xác thực mạnh, quản lý bản vá, và kế hoạch khôi phục đã được diễn tập.

### 5. Khung quốc tế hiện có và ba khoảng trống

Các khung hiện hành đã đặt nền tảng tốt: hướng dẫn của Uỷ ban Basel về rủi ro vận hành, Đạo luật DORA của EU về khả năng chống chịu vận hành số của khu vực tài chính, và các nguyên tắc của CPMI-IOSCO về khả năng chống chịu mạng của hạ tầng thị trường tài chính. Nhưng tất cả được thiết kế trước bước nhảy năng lực AI. Bài chỉ ra ba khoảng trống:

**Khoảng trống 1: đo lường.** Khi các bộ đo chuẩn công khai đã bị giải hết, cả ngành mất khả năng theo dõi tiến bộ năng lực tấn công một cách khách quan.

**Khoảng trống 2: giữa các nước.** Các nền kinh tế mới nổi và đang phát triển (EMDE) thiếu nhân lực an ninh mạng, thiếu ngân sách, thiếu khung pháp lý, và thiếu cả dữ liệu sự cố để biết mình đang bị tấn công tới mức nào. Nước thu nhập thấp chịu khoảng trống này nặng nhất.

**Khoảng trống 3: quản trị mô hình tiên phong.** Các cam kết an toàn của phòng thí nghiệm AI hiện chủ yếu mang tính tự nguyện. Không có kênh chính thức nối cơ quan quản lý tài chính với cơ quan quản lý AI và với quá trình đánh giá an toàn mô hình, dù hệ thống tài chính là một trong những mục tiêu tấn công ưu tiên.

### 6. Bảy khuyến nghị chính sách

1. **Kiểm thử chịu đựng với kịch bản AI.** Đưa kịch bản tấn công có AI hỗ trợ vào kiểm thử chịu đựng mạng và diễn tập khủng hoảng của khu vực tài chính, thay vì tiếp tục dùng các kịch bản dựa trên năng lực tấn công của thời kỳ trước.
2. **Báo cáo sự cố và chia sẻ thông tin.** Bắt buộc báo cáo sự cố kịp thời và thúc đẩy chia sẻ thông tin đe doạ giữa các tổ chức và xuyên biên giới, vì không có dữ liệu thì không thể đánh giá rủi ro hệ thống.
3. **Giám sát rủi ro tập trung.** Coi nhà cung cấp dịch vụ đám mây và nhà cung cấp mô hình như hạ tầng quan trọng và giám sát tương ứng.
4. **Nâng chuẩn xác thực.** Giả định rằng giọng nói, hình ảnh, video và văn bản đều có thể bị giả mạo; chuyển sang các phương thức xác thực chống lừa đảo như khoá phần cứng và xác nhận qua một kênh độc lập.
5. **Năng lực giám sát của cơ quan quản lý.** Tuyển dụng và giữ chân nhân lực kỹ thuật, để cơ quan quản lý hiểu được công nghệ mình quản lý.
6. **Hỗ trợ có mục tiêu cho EMDE và tổ chức tài chính nhỏ.** Qua dịch vụ an ninh dùng chung, năng lực cấp khu vực và hỗ trợ kỹ thuật, vì mắt xích yếu nhất quyết định độ bền của cả chuỗi.
7. **Nối quản lý tài chính với quản trị AI tiên phong.** Thiết lập kênh chính thức để cơ quan tài chính có tiếng nói trong việc đặt chuẩn đánh giá an toàn mô hình, vì hệ thống tài chính là mục tiêu ưu tiên của tấn công.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Frontier model | Mô hình tiên phong, thế hệ mô hình AI có năng lực cao nhất hiện có |
| Cybench | Bộ bài tập chuẩn đánh giá năng lực an ninh mạng của mô hình AI |
| CyberGym | Bộ đánh giá khả năng tìm lỗ hổng trong mã nguồn mở thực tế |
| Benchmark saturation | Bão hoà thước đo, mô hình giải hết bài kiểm tra nên mất khả năng phân biệt |
| Zero-day | Lỗ hổng chưa được biết và chưa có bản vá |
| Sandbox escape | Thoát khỏi môi trường cách ly được dựng để giới hạn mô hình |
| Breakout time | Thời gian bứt phá, từ xâm nhập ban đầu tới khi lan ngang trong mạng |
| Lateral movement | Lan ngang, kẻ tấn công di chuyển giữa các hệ thống trong cùng mạng |
| Spear phishing | Lừa đảo có chủ đích, được cá nhân hoá theo từng nạn nhân cụ thể |
| Deepfake | Giả mạo giọng nói hoặc hình ảnh bằng AI |
| Polymorphic malware | Mã độc tự biến đổi hình dạng để né phát hiện theo chữ ký |
| Signature-based detection | Phát hiện theo chữ ký, chỉ bắt được mối đe doạ đã biết |
| Anomaly detection | Phát hiện bất thường dựa trên sai lệch so với hành vi bình thường |
| Alert fatigue | Mệt mỏi cảnh báo, nhà phân tích bỏ sót vì quá nhiều cảnh báo giả |
| Threat hunting | Săn mối đe doạ, chủ động tìm kiếm thay vì chờ cảnh báo |
| Adversarial attack | Tấn công đối kháng nhằm đánh lừa chính mô hình phòng thủ |
| Data poisoning | Đầu độc dữ liệu huấn luyện để cài điểm mù vào mô hình |
| Technical debt | Nợ kỹ thuật, hệ thống cũ khó bảo trì tích tụ theo thời gian |
| Third-party risk | Rủi ro từ nhà cung cấp bên ngoài mà tổ chức phụ thuộc |
| Concentration risk | Rủi ro tập trung khi nhiều tổ chức dùng chung một nhà cung cấp |
| DORA | Đạo luật của EU về khả năng chống chịu vận hành số của khu vực tài chính |
| Operational resilience | Khả năng chống chịu vận hành, duy trì dịch vụ quan trọng khi bị gián đoạn |
| Phishing-resistant authentication | Xác thực chống lừa đảo, như khoá phần cứng, không thể bị đánh cắp từ xa |
| Dual-use | Lưỡng dụng, cùng năng lực dùng được cho cả tấn công và phòng thủ |

## Câu nói đáng nhớ

> "Attackers need to succeed once. Defenders must succeed every time."

> "When benchmarks saturate, we lose the yardstick precisely when we most need to measure."

> "The cost of attack is falling faster than the cost of defense."

## Đánh giá và phát hiện đáng chú ý

### Khung "công thủ" của bài che khuất chính phát hiện mạnh nhất của nó

"Kẻ tấn công chỉ cần đúng một lần, bên thủ phải đúng mọi lần" là câu châm ngôn nổi tiếng nhất của ngành an ninh mạng, và bài dùng nó làm trục cho kết luận rằng cán cân đang nghiêng về phía tấn công. Nhưng chính các con số mà bài trưng ra lại không ủng hộ cách đọc đó một cách gọn gàng.

Tám mươi bốn phần trăm trên bài tìm lỗ hổng trong trình duyệt và tám mươi ba phẩy một phần trăm trên bộ tìm lỗi mã nguồn mở là những con số về **năng lực tìm lỗi**, và tìm lỗi là việc mà bên phòng thủ làm được tốt hơn bên tấn công về mặt cấu trúc. Bên phòng thủ có mã nguồn, có toàn bộ lịch sử thay đổi, có quyền chạy mô hình lên hệ thống của chính mình bao nhiêu lần tuỳ ý, có thể làm việc đó trước khi phần mềm được triển khai, và không bị giới hạn thời gian. Kẻ tấn công thường chỉ có tệp nhị phân và bề mặt mạng nhìn từ bên ngoài. Dự án dùng mô hình để vá lỗ hổng trong hạ tầng mã nguồn mở mà bài nhắc tới chính là minh chứng rằng cùng một năng lực đó đang chạy mạnh ở phía phòng thủ.

Vậy nếu lợi thế kỹ thuật không rõ ràng nghiêng về phía tấn công, thì cái gì đang nghiêng? Câu trả lời nằm ở điểm yếu thứ năm mà bài liệt kê sau cùng: **bất đối xứng nguồn lực**. Năng lực AI trong an ninh mạng là một năng lực **mua được bằng tiền và bằng người**. Một ngân hàng lớn có thể chạy mô hình quét toàn bộ mã nguồn lõi mỗi đêm; một quỹ tín dụng nhân dân thì không có mã nguồn, không có đội an ninh, và không có ngân sách.

Nghĩa là mệnh đề đúng không phải "AI có lợi cho bên tấn công" mà là "**AI khuếch đại khoảng cách giữa bên giàu nguồn lực và bên nghèo nguồn lực, ở cả hai phía**". Đây là một mệnh đề khác hẳn về mặt chính sách. Mệnh đề thứ nhất dẫn tới việc kêu gọi kiềm chế năng lực mô hình, điều gần như bất khả thi. Mệnh đề thứ hai dẫn tới việc tập trung nguồn lực vào các tổ chức nhỏ và các nước yếu — tức khuyến nghị thứ sáu, khuyến nghị đang bị trình bày như một hành động hỗ trợ nhân đạo trong khi đáng lẽ nó phải là khuyến nghị trung tâm.

### Bão hoà thước đo không chỉ là mất dữ liệu, nó làm rỗng khuyến nghị đầu tiên

Nhận xét rằng khi bộ đo chuẩn bị giải hết thì ta mất thước đo là quan sát sắc sảo nhất của bài. Nhưng hệ quả của nó còn đi xa hơn chỗ bài dừng lại.

Khuyến nghị thứ nhất yêu cầu đưa kịch bản tấn công có AI hỗ trợ vào kiểm thử chịu đựng mạng. Kiểm thử chịu đựng, theo đúng phương pháp luận của nó, đòi hỏi một cú sốc được tham số hoá: nghiêm trọng nhưng có thể xảy ra, với độ lớn xác định được và biện minh được. Với rủi ro tín dụng, độ lớn đó đến từ dữ liệu lịch sử về vỡ nợ. Với rủi ro thị trường, từ phân phối lợi suất trong quá khứ.

Với năng lực tấn công của mô hình AI, **không có phân phối lịch sử**, đường tiến bộ không tuyến tính, và bộ đo duy nhất để hiệu chuẩn thì vừa bão hoà. Trong điều kiện đó, câu "kịch bản tấn công có AI hỗ trợ" không chỉ định một mức độ nghiêm trọng nào cả. Mỗi tổ chức sẽ tự chọn một kịch bản, và kết quả kiểm thử giữa các tổ chức không so sánh được với nhau — điều này phá hỏng đúng mục đích của việc kiểm thử ở cấp hệ thống, vốn là để biết ai yếu nhất.

Cách duy nhất còn lại để hiệu chuẩn là thử thật: cho một mô hình tiên phong tấn công hệ thống của chính mình trong môi trường có kiểm soát. Nhưng điều đó đòi hỏi quyền truy cập vào mô hình mạnh nhất, ngân sách, và đội ngũ đủ trình độ để thiết kế bài thử — tức là quay lại đúng ba thứ mà tổ chức nhỏ và nước thu nhập thấp không có. Vấn đề đo lường và vấn đề bất đối xứng nguồn lực không phải hai khoảng trống riêng biệt như bài trình bày; chúng là cùng một vấn đề nhìn từ hai phía.

### Hai mươi chín phút là con số giết chết cả một họ biện pháp kiểm soát

Trong toàn bộ tài liệu, con số có hàm ý vận hành trực tiếp nhất là thời gian bứt phá trung bình hai mươi chín phút. Nó đáng được đọc như một ràng buộc số học chứ không phải một thông tin tham khảo.

Bất kỳ biện pháp kiểm soát nào có vòng phản ứng đi qua một quyết định của con người đều **vượt quá hai mươi chín phút theo cấu trúc**: cây gọi điện leo thang, phê duyệt của lãnh đạo phụ trách an toàn thông tin, quy trình trực ngoài giờ, phiếu yêu cầu hỗ trợ gửi cho nhà cung cấp, cuộc họp xử lý sự cố. Không phải vì con người chậm mà vì chuỗi đó có quá nhiều bước tuần tự.

Điều này dẫn tới một cách xếp hạng biện pháp mà bài không đưa ra. Trong năm chức năng phòng thủ dùng AI, bốn chức năng đầu đều nằm trong họ **phát hiện rồi phản ứng** — một cuộc đua tốc độ mà bên phòng thủ chỉ có thể hoà chứ không thắng, và chức năng thứ tư là ứng phó tự động thì bài đã tự cảnh báo rằng nó có thể tự gây gián đoạn dịch vụ.

Họ biện pháp còn hiệu lực là họ **ngăn chặn tĩnh**: phân đoạn mạng, nguyên tắc đặc quyền tối thiểu, bản sao lưu không thể sửa đổi, xác thực bằng khoá phần cứng, hạn mức chuyển tiền cứng. Chúng có chung một đặc điểm quyết định: **chúng đã được cấu hình từ trước, nên tốc độ của kẻ tấn công không liên quan**. Một mạng được phân đoạn đúng thì kẻ tấn công lan ngang trong hai mươi chín phút hay hai mươi chín giây cũng chỉ lan trong một phân đoạn.

Đây là kết luận có giá trị nhất mà tài liệu ngầm chứa mà không phát biểu: **phản ứng đúng với kẻ tấn công nhanh hơn không phải là phát hiện nhanh hơn, mà là ngăn chặn tĩnh nhiều hơn**. Nó cũng là kết luận dễ chịu về mặt ngân sách, vì phân đoạn mạng và khoá phần cứng rẻ hơn nhiều so với một trung tâm điều hành an ninh dùng AI.

### Một biện pháp kiểm soát đã chết mà không ai ra thông báo

Bài dành ba dòng cho việc giả mạo giọng nói và hình ảnh vượt qua quy trình xác minh qua điện thoại và hội nghị truyền hình, và một câu cho việc rào cản ngôn ngữ đã biến mất. Gộp lại, hai chi tiết này nói rằng một biện pháp kiểm soát đang được dùng phổ biến ở hầu hết ngân hàng trên thế giới vừa trở nên vô giá trị.

Biện pháp đó là **gọi lại để xác nhận**. Với lệnh chuyển tiền giá trị lớn, với yêu cầu thay đổi thông tin tài khoản thụ hưởng, với chỉ đạo khẩn từ lãnh đạo, quy trình chuẩn ở rất nhiều nơi là gọi lại một số đã biết và nhận diện giọng nói quen. Toàn bộ giá trị của biện pháp này nằm ở giả định rằng giọng nói không thể giả được. Giả định đó không còn đúng, và sự thay đổi đã diễn ra mà không có bất kỳ thông báo quản lý nào, không có thời hạn chuyển tiếp, không có danh sách quy trình cần rà soát.

Rào cản ngôn ngữ biến mất làm nghiêm trọng thêm điều này ở đúng những nơi ít sẵn sàng nhất. Các thị trường không nói tiếng Anh trước đây được bảo vệ bởi một lớp vô tình: chiến dịch lừa đảo viết bằng tiếng nước ngoài lộ ra ngay vì văn phong sai. Lớp bảo vệ đó là miễn phí, không ai xây, và không ai nhận ra mình đang dựa vào nó cho tới khi nó mất.

Hàm ý cụ thể: mọi quy trình phê duyệt dựa trên việc **nhận ra một con người** — giọng nói, khuôn mặt trên màn hình, văn phong thư điện tử của đồng nghiệp — cần được coi là đã hỏng và phải thay bằng thứ không thể giả: khoá phần cứng, kênh xác nhận độc lập không do người yêu cầu chọn, và thời gian chờ bắt buộc với giao dịch lớn.

### An ninh mạng tài chính là một hàng hoá công toàn cầu theo kiểu mắt xích yếu nhất, và điều đó làm khuyến nghị thứ sáu mạnh hơn nhiều

Bài trình bày việc hỗ trợ các nền kinh tế mới nổi và tổ chức tài chính nhỏ như một khuyến nghị về công bằng, đặt ở vị trí thứ sáu trong bảy. Nhưng có một lập luận chặt chẽ hơn nhiều mà bài không dùng.

Khả năng chống chịu của hệ thống tài chính toàn cầu trước tấn công mạng có đúng ba đặc tính của một hàng hoá công toàn cầu: không ai bị loại trừ khỏi lợi ích, không ai có động cơ trả đủ phần của mình, và nó bị cung ứng dưới mức. Nhưng đặc tính quyết định là **công nghệ gộp theo kiểu mắt xích yếu nhất**: mức an toàn của cả hệ thống không bằng mức trung bình của các thành viên mà bằng mức của thành viên yếu nhất, vì kẻ tấn công vào qua đó rồi đi tiếp.

Với hàng hoá công có cấu trúc mắt xích yếu nhất, lý thuyết cho một kết quả rất rõ: **mức đóng góp hiệu quả là dồn nguồn lực vào bên yếu nhất, không phải chia đều**. Một đô la chi cho việc củng cố tổ chức yếu nhất trong mạng lưới tạo ra nhiều an toàn hơn một đô la chi cho tổ chức đã mạnh. Đây không phải lòng tốt mà là tính toán vị lợi của chính những nước giàu.

Điều này cũng giải thích vì sao khuyến nghị thứ hai — bắt buộc báo cáo sự cố — quan trọng hơn vẻ ngoài hành chính của nó. Không có dữ liệu sự cố thì không xác định được mắt xích yếu nhất nằm ở đâu, và không xác định được thì mọi phân bổ nguồn lực đều là đoán. Bài nói rằng các nước thu nhập thấp thiếu cả dữ liệu sự cố để biết mình đang bị tấn công tới mức nào; câu đó nên được đọc là: họ không thể tự biết mình có phải mắt xích yếu nhất hay không.

### Với Việt Nam: sự kết hợp nguy hiểm nhất không phải AI, mà là AI cộng với tính chung thẩm

Ba đặc điểm của hệ thống tài chính Việt Nam ghép lại tạo ra một cấu hình rủi ro cụ thể hơn bất kỳ cảnh báo chung nào trong bài.

**Thứ nhất, chuyển tiền là tức thời và chung thẩm.** Tiền rời tài khoản là đi thật, trong vài giây, không có cơ chế tạm giữ như thanh toán thẻ. **Thứ hai, kênh phê duyệt chủ yếu dựa trên con người nhận diện con người** — cuộc gọi xác nhận, ảnh chụp giấy tờ, video ngắn để xác minh danh tính. **Thứ ba, rào cản ngôn ngữ vừa biến mất**, nghĩa là một chiến dịch lừa đảo bằng tiếng Việt chuẩn mực, nhắm đúng ngữ cảnh công việc của từng nạn nhân, giờ có chi phí sản xuất gần bằng không.

Ghép ba thứ đó: kẻ tấn công thuyết phục bằng một giọng nói giả không phân biệt được, nạn nhân chuyển tiền, tiền đi trong vài giây và không thể đòi lại. Không có bước nào trong chuỗi này cần tới việc xâm nhập một hệ thống nào cả. Đây là lý do vì sao gian lận chuyển tiền qua lừa đảo xã hội, chứ không phải tấn công vào hạ tầng ngân hàng, mới là hình thái tổn thất chính đáng lo — và nó cũng lý giải vì sao các biện pháp kỹ thuật ở tầng hạ tầng không chạm tới nó.

Ba việc rút ra được từ bài và áp dụng trực tiếp. Một là **thời gian chờ bắt buộc và hạn mức mặc định** cho giao dịch lớn hoặc cho người thụ hưởng mới — đây là biện pháp ngăn chặn tĩnh, không phụ thuộc vào việc phát hiện kịp, và là biện pháp duy nhất còn hiệu lực khi lớp xác thực dựa trên nhận diện con người đã hỏng. Hai là **dịch vụ an ninh dùng chung cho các tổ chức nhỏ** — quỹ tín dụng nhân dân, tổ chức tài chính vi mô, công ty chứng khoán nhỏ — theo đúng logic mắt xích yếu nhất, vì chúng nối vào cùng hệ thống thanh toán với ngân hàng lớn nhưng không có năng lực tương đương. Ba là **bắt buộc báo cáo sự cố**, không phải để trừng phạt mà vì đó là điều kiện tiên quyết để biết mắt xích yếu nhất ở đâu.

Một điểm cuối đáng lưu ý và liên quan chặt tới phần còn lại của thư mục này: rủi ro tập trung nhà cung cấp mô hình mà bài nêu ở khuyến nghị thứ ba xuất hiện gần như y hệt trong phân tích về AI trên thị trường chứng khoán và trong phân tích về thanh toán bằng tác tử. Ba tài liệu, ba lĩnh vực, cùng một kết luận: khi vài nhà cung cấp nước ngoài nắm giữ năng lực mô hình và năng lực điện toán cho cả hệ thống tài chính của một nước, đó không còn là rủi ro vận hành mà là rủi ro chủ quyền.
