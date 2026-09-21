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

## Dàn ý chi tiết

### 1. Bước nhảy năng lực

- Trong khoảng hai năm, năng lực của mô hình AI tiên phong trong các tác vụ an ninh mạng đã chuyển từ mức hầu như không dùng được lên mức tương đương chuyên gia trên nhiều bài kiểm tra chuẩn. Trên bộ bài tập Cybench, mô hình mới nhất đạt điểm tuyệt đối.
- Quan trọng hơn điểm số trên bài tập nhân tạo là kết quả trên phần mềm thật. Trong bài kiểm tra tìm lỗ hổng trong trình duyệt Firefox phiên bản 147, tỷ lệ thành công tăng từ khoảng 15% lên 84% chỉ qua một thế hệ mô hình. Trên bộ CyberGym, tỷ lệ đạt trên 83%.
- Các mô hình đã phát hiện lỗ hổng chưa từng được biết trong những dự án mã nguồn mở được soi xét kỹ như OpenBSD và FFmpeg. Trong quá trình đánh giá an toàn, đã ghi nhận trường hợp mô hình thoát khỏi môi trường cách ly.
- Cùng năng lực đó đang được dùng cho phòng thủ. Dự án Glasswing sử dụng mô hình để tìm và vá lỗ hổng trong hạ tầng mã nguồn mở quan trọng, minh hoạ bản chất lưỡng dụng của công nghệ này.
- Bài nhấn mạnh một hệ quả ít được chú ý: khi các bộ đo chuẩn bị giải hết, cộng đồng mất thước đo. Chúng ta không còn cách khách quan để biết thế hệ mô hình kế tiếp mạnh hơn bao nhiêu, đúng vào thời điểm việc đo lường quan trọng nhất.

### 2. Bằng chứng từ thực địa

- Dữ liệu của CrowdStrike cho thấy các vụ xâm nhập có sử dụng AI tạo sinh tăng 89% trong năm qua. Thời gian bứt phá trung bình, tính từ lúc kẻ tấn công đặt chân vào mạng tới lúc bắt đầu lan ngang, đã giảm xuống khoảng 29 phút.
- Con số này quan trọng vì nó ngắn hơn chu kỳ phát hiện và phản ứng của phần lớn trung tâm điều hành an ninh. Nói cách khác, quy trình phòng thủ dựa trên con người đang bị vượt về tốc độ một cách có hệ thống.
- Các hình thái tấn công được AI khuếch đại gồm: lừa đảo thư điện tử được cá nhân hoá và không còn dấu hiệu ngôn ngữ bất thường; giả mạo giọng nói và video dùng trong gian lận chuyển tiền và trong việc vượt quy trình xác minh danh tính; mã độc tự biến đổi để né phát hiện; và việc tự động hoá khâu trinh sát mục tiêu vốn trước đây tốn nhiều thời gian của con người.
- Một điểm đáng chú ý là rào cản ngôn ngữ, vốn từng bảo vệ các thị trường không nói tiếng Anh khỏi nhiều chiến dịch lừa đảo, đã gần như biến mất.

### 3. Năm điểm yếu cấu trúc của khu vực tài chính

- **Nợ kỹ thuật.** Hệ thống lõi của nhiều tổ chức tài chính đã vài chục năm tuổi, viết bằng ngôn ngữ ít người còn thành thạo, với các phụ thuộc không được lập tài liệu đầy đủ. AI lại đặc biệt giỏi đọc và phân tích mã cũ.
- **Phụ thuộc bên thứ ba và tập trung.** Điện toán đám mây, nhà cung cấp dữ liệu thị trường và phần mềm lõi ngân hàng tập trung vào một số ít nhà cung cấp. Một lỗ hổng ở đó lan tới hàng nghìn tổ chức cùng lúc.
- **Tốc độ và mức độ liên kết.** Thanh toán tức thời và hoạt động liên tục nghĩa là tổn thất cũng lan tức thì, không còn khoảng đệm để phát hiện và ngăn chặn.
- **Yếu tố con người.** Phần lớn xâm nhập thành công vẫn bắt đầu từ việc lừa một con người. AI làm cho việc lừa đó rẻ hơn, thuyết phục hơn và có thể thực hiện ở quy mô lớn.
- **Bất đối xứng nguồn lực.** Đây là điểm bài nhấn mạnh nhất. Ngân hàng lớn có thể triển khai phòng thủ dựa trên AI; các tổ chức nhỏ thì không. Và chi phí biên của việc tấn công đang giảm nhanh hơn chi phí biên của việc phòng thủ.

### 4. AI dùng cho phòng thủ

- Năm chức năng phòng thủ chính: phát hiện bất thường dựa trên hành vi thay vì dựa trên chữ ký đã biết; phân loại và xếp ưu tiên cảnh báo để giảm mệt mỏi cảnh báo; săn mối đe doạ chủ động trên khối lượng nhật ký lớn; ứng phó tự động trong vài giây; và quản lý lỗ hổng, ngày càng bao gồm cả việc tự sinh bản vá.
- Phòng thủ dựa trên AI cũng mang rủi ro riêng. Mô hình phòng thủ có thể bị tấn công đối kháng qua việc đầu độc dữ liệu huấn luyện hoặc qua các mẫu được thiết kế để né tránh. Việc tự động hoá ứng phó có thể tự gây gián đoạn dịch vụ nếu phản ứng sai. Và tính chất hộp đen của mô hình khiến việc giải thích và kiểm toán quyết định trở nên khó.
- Bài kết luận rằng AI phòng thủ là cần thiết nhưng không đủ, và không thể thay thế các biện pháp cơ bản như phân đoạn mạng, xác thực mạnh, quản lý bản vá và kế hoạch khôi phục đã được diễn tập.

### 5. Khung quốc tế hiện có và ba khoảng trống

- Các khung hiện hành như hướng dẫn của Uỷ ban Basel về rủi ro vận hành, Đạo luật DORA của EU về khả năng chống chịu vận hành số, và các nguyên tắc của CPMI-IOSCO về khả năng chống chịu mạng đã đặt nền tảng tốt. Nhưng chúng được thiết kế trước bước nhảy năng lực AI.
- **Khoảng trống đo lường:** khi các bộ đo chuẩn bão hoà, cả ngành mất khả năng theo dõi tiến bộ năng lực tấn công một cách khách quan.
- **Khoảng trống giữa các nước:** các nền kinh tế mới nổi và đang phát triển thiếu nhân lực an ninh mạng, ngân sách, khung pháp lý và cả dữ liệu sự cố để biết mình đang bị tấn công tới mức nào.
- **Khoảng trống quản trị mô hình tiên phong:** các cam kết an toàn của phòng thí nghiệm AI hiện chủ yếu mang tính tự nguyện, và không có kênh chính thức nối cơ quan quản lý tài chính với quá trình đánh giá an toàn mô hình, dù hệ thống tài chính là một trong những mục tiêu tấn công ưu tiên.

### 6. Bảy khuyến nghị chính sách

- Đưa kịch bản tấn công có AI hỗ trợ vào kiểm thử chịu đựng mạng và diễn tập khủng hoảng của khu vực tài chính, thay vì tiếp tục dùng các kịch bản dựa trên năng lực tấn công của thời kỳ trước.
- Bắt buộc báo cáo sự cố kịp thời và thúc đẩy chia sẻ thông tin đe doạ giữa các tổ chức và xuyên biên giới, vì không có dữ liệu thì không thể đánh giá rủi ro hệ thống.
- Giám sát rủi ro tập trung với nhà cung cấp dịch vụ đám mây và nhà cung cấp mô hình như giám sát hạ tầng quan trọng.
- Nâng chuẩn xác thực với giả định rằng giọng nói, hình ảnh và văn bản đều có thể bị giả mạo, chuyển sang các phương thức chống lừa đảo như khoá phần cứng và xác nhận qua kênh độc lập.
- Xây năng lực kỹ thuật cho chính cơ quan quản lý, gồm tuyển dụng và giữ chân nhân lực hiểu công nghệ.
- Hỗ trợ có mục tiêu cho các nền kinh tế mới nổi và các tổ chức tài chính nhỏ, qua dịch vụ an ninh dùng chung, năng lực cấp khu vực và hỗ trợ kỹ thuật, vì mắt xích yếu nhất quyết định độ bền của cả chuỗi.
- Thiết lập kênh chính thức giữa quản lý tài chính và quản trị AI tiên phong, để cơ quan tài chính có tiếng nói trong việc đặt chuẩn đánh giá an toàn.

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
