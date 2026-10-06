# Harnessing Emerging Digital Technologies toward a New Frontier of Public Financial Management — Khai thác công nghệ số mới nổi hướng tới biên giới mới của quản lý tài chính công

**Nguồn:** IMF Technical Notes and Manuals TNM/2026/06.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 2, không có trang bìa và trang tác giả).
**Ý chính:** Gần như mọi quốc gia đều đã có hệ thống thông tin quản lý tài chính, nhưng phần lớn không còn đáp ứng được nhu cầu. Bài không khuyến nghị bất kỳ công nghệ cụ thể nào, mà đề xuất một cách tiếp cận tối đa hoá giá trị: nhân một điểm số về lợi ích tiềm năng với một điểm số về tính khả thi, rồi quyết định dựa trên kết quả. Thông điệp trung tâm là cạm bẫy lớn nhất không phải chọn sai công nghệ mà là tự động hoá một quy trình thủ công mà không thiết kế lại chính quy trình đó, và là để nhiệt tình đầu cơ dẫn dắt quyết định thay vì mục tiêu.

> **Lưu ý:** bản PDF bắt đầu từ trang 2 (phần Giới thiệu). Trang bìa, tóm tắt và danh sách tác giả không có trong bản này. Số hiệu tài liệu lấy từ trang bìa sau.
> - Ở phương án hợp đồng thông minh trên blockchain, bài ghi VM = 7,75 × 4,4 = **33**; phép nhân chính xác cho khoảng **34,1** (kết luận không đổi).
> - Điểm lợi ích G của hai phương án sau không kiểm được: với phương án A, G = 7,75 đúng bằng bình quân không trọng số của bốn điểm thành phần (9, 8, 7, 7); nếu phương án B kết hợp AI chỉ tăng 2 điểm trách nhiệm giải trình so với phương án B thì theo cùng cách tính G phải là 7,5 + 0,5 = **8,0**, không phải **8,75**. Bài không nêu điểm thành phần và trọng số của phương án B nên không biết số nào đúng.

## Sơ đồ

### Hiện trạng và vì sao cần thay đổi

```text
       HỆ THỐNG PFM CŨ ĐANG MẮC Ở ĐÂU
       · cài đặt TẠI CHỖ, phải cập nhật THỦ CÔNG
       · vận hành RỜI RẠC, không liên thông giữa các vụ, cục
       · hỗ trợ từ nhà cung cấp KHÔNG NHẤT QUÁN
       → chi phí vận hành CAO, hiệu quả THẤP
                                │
                                ▼
       ĐỘ PHỦ SỐ HOÁ THEO CHỨC NĂNG (World Bank GTMI, 12/2025)
       Hệ thống thông tin quản lý tài chính (FMIS) ···· 193 nước
       Hải quan ······································· 191
       Thuế ··········································· 187
       Hưu trí ········································ 184
       Quản lý nợ ····································· 179
       Tài khoản kho bạc duy nhất (TSA) ··············· 172
       Mua sắm điện tử ································ 166
       Trả lương ······································ 163
       Quản lý nhân sự ································ 163
       ★ QUẢN LÝ ĐẦU TƯ CÔNG ·························· 86 ◂── TỤT XA
                                │
                                ▼
       NĂM YẾU ĐIỂM DAI DẲNG
       ① dữ liệu KÉM CHẤT LƯỢNG, không đầy đủ, thiếu nhất quán
       ② SILO — không liên thông giữa cơ sở dữ liệu, hệ thống, cơ quan
       ③ kiến trúc công nghệ LỖI THỜI, ít linh hoạt, kém an toàn
       ④ RẤT ÍT dùng phương pháp phân tích dữ liệu hiện đại
       ⑤ báo cáo CHẬM và cồng kềnh, không giám sát thời gian thực
       ────────────────────────────────────────────────────────────
       ⚠ CON SỐ ĐÁNG SUY NGHĨ: 156 dự án FMIS do Ngân hàng Thế giới
       tài trợ từ 1984, tổng chi phí VƯỢT 6 TỶ ĐÔ LA — vậy mà phần
       lớn hệ thống vẫn không đáp ứng được nhu cầu đang thay đổi
```

### Ba tương lai có thể và bốn kiểu tổ chức

```text
       KHUNG "HÌNH NÓN TƯƠNG LAI" (Voros 2017)
       ┌──────────────────────────────────────────────────────────┐
       │ ❶ TƯƠNG LAI KHẢ DĨ NHẤT — "giữ nguyên như cũ"            │
       │   hệ thống cũ ở nguyên, cải tiến từng chút, chỉ phản ứng │
       │   khi có sức ép bên ngoài (thay đổi luật)                │
       │   → LỊCH SỬ cho thấy đây là kịch bản CHIẾM ƯU THẾ        │
       │   ⚠ nhưng hệ thống cũ TỐN KÉM để duy trì và DỄ BỊ TẤN    │
       │     CÔNG vì phải vá phần mềm lỗi thời                    │
       ├──────────────────────────────────────────────────────────┤
       │ ❷ TƯƠNG LAI HỢP LÝ — "hiện đại hoá tiệm tiến"            │
       │   nâng cấp công nghệ sẵn có, xử lý điểm đau cụ thể: an   │
       │   ninh mạng, tự động hoá một số quy trình, mở rộng liên  │
       │   thông, đưa phân tích dữ liệu và trợ lý AI vào          │
       │   ★ KHUYẾN NGHỊ CỦA BÀI cho ĐA SỐ nước: đây là lựa chọn  │
       │     TỐT THỨ HAI nhưng THỰC TẾ nhất                       │
       ├──────────────────────────────────────────────────────────┤
       │ ❸ TƯƠNG LAI CÓ THỂ — "đại tu chuyển đổi"                 │
       │   AI cho lập và báo cáo ngân sách · token hoá cho quản   │
       │   lý tài sản · hợp đồng thông minh cho lương, nợ, mua    │
       │   sắm · IoT cho kiểm kê và đầu tư công · Web3 cho định   │
       │   danh số · tiền số cho thu chi                          │
       │   → chỉ khả thi với nước đã có ĐỘ TRƯỞNG THÀNH SỐ cao    │
       └──────────────────────────────────────────────────────────┘
       ★ CÁCH TIẾP CẬN LAI cũng hợp lệ: đại tu một vài chức năng
         trọng điểm, phần còn lại đi theo hiện đại hoá tiệm tiến
       ────────────────────────────────────────────────────────────
       KHUNG THỜI GIAN CHO MỘT CUỘC ĐẠI TU (Hộp 1): 10–20 NĂM
       ① SẴN SÀNG CÔNG NGHỆ — tiến bộ đáng kể trong 5–10 năm
       ② Ý CHÍ CHÍNH TRỊ — nước chậm có thể mất HƠN 15 năm
       ③ NĂNG LỰC THỂ CHẾ — 5 đến HƠN 20 năm
       ④ NGUỒN LỰC — nước mong manh và xung đột khó đạt trong 10 năm
       ────────────────────────────────────────────────────────────
       BỐN KIỂU TỔ CHỨC (phỏng theo đường cong lan toả của Rogers 1983)
       NGƯỜI TIÊN PHONG ◂ chủ động tìm công nghệ mới, chấp nhận rủi ro
       ÁP DỤNG CHỦ ĐỘNG ◂ theo dõi xu hướng, áp dụng cái đã được thử
       ÁP DỤNG PHẢN ỨNG ◂ ngại rủi ro, chờ người khác chứng minh
       ÁP DỤNG THỤ ĐỘNG ◂ chỉ đổi khi luật bắt buộc
       (KHÔNG ÁP DỤNG)  ◂ vẫn chủ yếu thủ công
       → kiểu tổ chức KHÔNG CỐ ĐỊNH và có thể thay đổi theo thời gian
```

### Công thức tối đa hoá giá trị

```text
                          VM = G × F
       ┌───────────────────────────┬──────────────────────────────┐
       │ G — ĐIỂM LỢI ÍCH (1–10)   │ F — ĐIỂM KHẢ THI (1–10)      │
       │ tổng có trọng số của SÁU  │ tổng có trọng số của BỐN     │
       │ nhóm lợi ích:             │ yếu tố:                      │
       │                           │                              │
       │ ① QUY TRÌNH — tự động hoá │ ① KỸ THUẬT — công nghệ có    │
       │   việc lặp lại, tiết kiệm │   PHÙ HỢP MỤC ĐÍCH không?    │
       │   chi phí                 │   đã đủ trưởng thành? có     │
       │ ② ĐẦU RA — dữ liệu sẵn có │   tương thích với hệ thống   │
       │   hơn, đáng tin hơn       │   hiện có?                   │
       │ ③ KẾT QUẢ — ra quyết định │ ② KINH TẾ — chi phí ban đầu  │
       │   dựa trên dữ liệu, dịch  │   và bảo trì so với tiết     │
       │   vụ công tốt hơn         │   kiệm; tỷ suất hoàn vốn     │
       │ ④ TRÁCH NHIỆM GIẢI TRÌNH  │ ③ VẬN HÀNH — gián đoạn quy   │
       │   — minh bạch, ít khả     │   trình, nhu cầu đào tạo,    │
       │   năng bóp méo dữ liệu    │   thay đổi luật, quản lý     │
       │ ⑤ AN NINH — công nghệ cũ  │   thay đổi                   │
       │   hết hỗ trợ là lỗ hổng   │ ④ TIẾN ĐỘ — thời gian triển  │
       │ ⑥ SẴN SÀNG TƯƠNG LAI      │   khai có THỰC TẾ không?     │
       │                           │                              │
       │ TRỌNG SỐ do chính bộ tài  │ TRỌNG SỐ cũng do hoàn cảnh   │
       │ chính đặt, cộng lại = 1   │ quyết định: nước nợ cao đặt  │
       │ → gắn với CHIẾN LƯỢC      │ trọng số lớn cho KINH TẾ     │
       └───────────────────────────┴──────────────────────────────┘
       NGƯỠNG: G hoặc F ≤ 4 là THẤP, ≥ 7 là CAO
               VM < 30 là THẤP, > 50 là CAO
       ────────────────────────────────────────────────────────────
       MA TRẬN LỢI ÍCH – KHẢ THI
              Lợi ích CAO │ II. lợi ích cao,  │ I. lợi ích cao,
                          │    khả thi thấp   │    khả thi cao
                          │ ▸ CÂN NHẮC, THẬN  │ ▸ NÊN ÁP DỤNG
                          │   TRỌNG; làm thí  │   VM ≈ 30–100
                          │   điểm theo giai  │
                          │   đoạn · VM ≈5–50 │
              ────────────┼───────────────────┼──────────────────
              Lợi ích THẤP│ III. thấp – thấp  │ IV. lợi ích thấp,
                          │ ▸ CHỜ công nghệ   │     khả thi cao
                          │   trưởng thành,   │ ▸ ÁP DỤNG nhưng
                          │   hoặc cải cách   │   ĐỪNG KỲ VỌNG
                          │   thể chế trước   │   QUÁ NHIỀU
                          │   VM ≈ 1–25       │   VM ≈ 5–50
                          └───────────────────┴──────────────────
                            Khả thi THẤP        Khả thi CAO
```

### Ví dụ tính toán: hợp đồng thông minh cho thanh toán xây dựng

```text
       BỐI CẢNH: nước có nợ công cao, vừa công bố chiến lược chuyển
       đổi số 2024, bộ tài chính có Kế hoạch Năm năm hiện đại hoá
       PFM, nhưng KHÔNG SẴN SÀNG chấp nhận rủi ro lớn
       VẤN ĐỀ: thanh toán theo tiến độ công trình đang làm THỦ CÔNG,
       cán bộ mua sắm phải xác nhận từng mốc → chậm trễ và sai sót
                                │
                                ▼
       PHƯƠNG ÁN A — HỢP ĐỒNG THÔNG MINH TRÊN BLOCKCHAIN
       LỢI ÍCH: giảm 50% thời gian xử lý, tiết kiệm 15% chi phí hành
       chính · quy trình 9 · đầu ra 8 · kết quả 7 · trách nhiệm 7
       → G = 7,75
       KHẢ THI: không hệ thống nào hiện có dùng blockchain, công nghệ
       chưa trưởng thành (kỹ thuật 3) · chi phí ban đầu 100.000 đô,
       tiết kiệm 50.000/năm, chi phí tích hợp CHƯA RÕ (kinh tế 6) ·
       chưa có khung pháp lý cho hợp đồng thông minh (vận hành 3) ·
       cần hơn 18 tháng (tiến độ 4) · trọng số kinh tế 0,4
       → F = 4,4
       ★ VM = 7,75 × 4,4 ≈ 34 (bài ghi 33) → NẰM Ở GÓC PHẦN TƯ II
         QUYẾT ĐỊNH: CHƯA ÁP DỤNG, hợp tác với nhà cung cấp và viện
         nghiên cứu để lấp khoảng trống khả thi trước
                                │
                                ▼
       PHƯƠNG ÁN B — CHƯƠNG TRÌNH TỰ THỰC THI TRÊN NỀN TẢNG SẴN CÓ
       (nhà thầu báo mốc → hệ thống báo cán bộ → duyệt → kích hoạt
       thanh toán từ kho bạc; KHÔNG dùng blockchain)
       G = 7,5 (lợi ích quy trình thấp hơn chút vì vẫn duyệt thủ công,
       nhưng có nhật ký kiểm toán, phân quyền, chữ ký số)
       F = 7,6 (dễ tích hợp, công nghệ trưởng thành, không vướng pháp
       lý, triển khai nhanh)
       ★ VM = 57 → GÓC PHẦN TƯ I, ÁP DỤNG
                                │
                                ▼
       PHƯƠNG ÁN B + AI PHÁT HIỆN BẤT THƯỜNG
       AI so sánh tiến độ báo cáo với lịch trình và lịch sử nhà thầu,
       cảnh báo sai lệch, KIỂM TRA LẦN CUỐI trước khi tiền chuyển đi
       G = 8,75 (trách nhiệm giải trình +2 nhờ chống gian lận chủ động)
       F = 7,2 (kỹ thuật và tiến độ giảm mỗi thứ 1 điểm)
       ★ VM = 63 → CAO NHẤT, ÁP DỤNG CẢ HAI nhưng THEO GIAI ĐOẠN:
         làm hợp đồng tự thực thi trước, tích hợp AI sau
```

## Ba câu hỏi bài viết trả lời

1. Vì sao các hệ thống PFM số hiện có, dù đã tốn hàng tỷ đô la, vẫn không đáp ứng được nhu cầu?
2. Làm sao quyết định có nên áp dụng một công nghệ mới nổi hay không, khi thông tin còn thiếu và nhiệt tình thị trường đang cao?
3. Cần những điều kiện nào để việc áp dụng công nghệ là bền vững chứ không phải một dự án một lần?

## Khái niệm cần biết

**Quản lý tài chính công (public financial management, PFM).** Toàn bộ các khâu nhà nước dùng để quản lý tiền công: lập ngân sách, thu thuế, chi tiêu, mua sắm, trả lương, quản lý nợ, kế toán, báo cáo và kiểm toán. Mục tiêu của PFM có bốn: kỷ luật tài khoá (không chi quá khả năng), hiệu quả phân bổ (tiền đi đúng ưu tiên), hiệu quả vận hành (làm việc với chi phí thấp) và minh bạch, trách nhiệm giải trình. Bài nói bốn mục tiêu này không đổi; công nghệ chỉ thay đổi cách đạt được chúng.

**Hệ thống thông tin quản lý tài chính (FMIS).** Phần mềm lõi ghi lại và xử lý các giao dịch ngân sách của nhà nước: phân bổ dự toán, cam kết chi, thanh toán, kế toán và báo cáo. Theo khảo sát của Ngân hàng Thế giới tháng 12/2025, 193 nước có FMIS. Khái niệm này quan trọng vì bài xuất phát từ nghịch lý: gần như nước nào cũng có FMIS, đã có 156 dự án FMIS do Ngân hàng Thế giới tài trợ với tổng chi phí hơn 6 tỷ đô la, vậy mà phần lớn hệ thống không đáp ứng được nhu cầu.

**Số hoá theo thiết kế (digital by design).** Thay vì đưa nguyên quy trình giấy tờ cũ lên máy tính, người ta thiết kế lại quy trình từ đầu để tận dụng năng lực của công nghệ mới. Ví dụ minh hoạ: số hoá một tờ trình phải qua năm chữ ký thành năm lần bấm "duyệt" trên phần mềm vẫn là quy trình cũ; số hoá theo thiết kế là hỏi xem năm bước duyệt đó còn cần không khi hệ thống đã tự kiểm tra dữ liệu. Đây là thông điệp trung tâm của bài: cạm bẫy lớn nhất là tự động hoá quy trình thủ công mà không thiết kế lại nó.

**Hình nón tương lai (futures cone).** Một cách sắp xếp các kịch bản tương lai theo mức khả năng xảy ra, do Voros (2017) đề xuất: tương lai khả dĩ nhất (dễ xảy ra nhất nếu không ai làm gì khác), tương lai hợp lý (có cơ sở để xảy ra), tương lai có thể (xảy ra được nếu có nỗ lực lớn). Bài dùng khung này để đặt ba con đường cho PFM số: giữ nguyên như cũ, hiện đại hoá tiệm tiến, và đại tu chuyển đổi.

**Đường cong chữ S và chu kỳ kỳ vọng thổi phồng (S curve, hype cycle).** Đường cong chữ S mô tả hiệu năng của một công nghệ: lúc đầu tăng chậm, sau đó tăng nhanh và vượt công nghệ cũ, rồi chững lại. Chu kỳ kỳ vọng thổi phồng mô tả tâm lý thị trường: sau khi công nghệ xuất hiện, kỳ vọng tăng vọt lên đỉnh, rơi xuống vực vỡ mộng, rồi mới dần đi tới giai đoạn dùng thực tế. Ví dụ minh hoạ: một công nghệ được báo chí ca ngợi năm đầu, bị chê là vô dụng ba năm sau, và chỉ tạo giá trị ổn định sau năm, bảy năm. Hai khái niệm này giúp chính phủ tránh mua công nghệ khi nó đang ở đỉnh kỳ vọng nhưng chưa trưởng thành.

**Tối đa hoá giá trị (value maximization, VM = G × F).** Khung chấm điểm của bài: lấy điểm lợi ích G (từ 1 đến 10) nhân với điểm khả thi F (từ 1 đến 10), ra giá trị VM từ 1 đến 100. Ví dụ trong bài: một chương trình tự thực thi thanh toán xây dựng có G = 7,5 và F = 7,6, nên VM = 57, ở mức cao, nên áp dụng. Phép nhân có một tính chất quan trọng: chỉ cần một trong hai điểm thấp thì VM thấp, nên một công nghệ rất hấp dẫn nhưng không khả thi sẽ không được chọn.

**Trọng số và tổng có trọng số.** Khi gộp nhiều tiêu chí thành một điểm, mỗi tiêu chí được nhân với một trọng số thể hiện mức quan trọng, các trọng số cộng lại bằng 1. Ví dụ trong bài: điểm khả thi gồm bốn yếu tố kỹ thuật 3, kinh tế 6, vận hành 3, tiến độ 4; nếu kinh tế có trọng số 0,4 và ba yếu tố còn lại mỗi yếu tố 0,2 thì F = 3 × 0,2 + 6 × 0,4 + 3 × 0,2 + 4 × 0,2 = 4,4. Bài nhấn mạnh trọng số do chính bộ tài chính đặt theo chiến lược của mình; nước nợ cao đặt trọng số lớn cho yếu tố kinh tế.

**Phụ thuộc nhà cung cấp và bề mặt tấn công (vendor lock-in, attack surface).** Phụ thuộc nhà cung cấp là tình trạng một cơ quan dùng hệ thống độc quyền đến mức rất khó và rất tốn kém để chuyển sang nhà cung cấp khác. Bề mặt tấn công là tổng số điểm mà kẻ tấn công có thể lợi dụng để xâm nhập: mỗi chức năng, mỗi kết nối, mỗi dịch vụ đám mây thêm vào đều mở thêm một cửa. Hai khái niệm này là hai rủi ro dài hạn mà bài đặc biệt nhấn mạnh khi áp dụng công nghệ mới.

## Nội dung chi tiết

### 1. Tầm nhìn cho PFM số

**Mục tiêu không đổi, cách làm thay đổi.** Bốn mục tiêu của quản lý tài chính công vẫn như cũ: kỷ luật tài khoá, hiệu quả phân bổ, hiệu quả vận hành, và minh bạch cùng trách nhiệm giải trình. Điều thay đổi là phương tiện để đạt được chúng.

**Số hoá theo thiết kế.** Khái niệm trung tâm của tầm nhìn là thiết kế lại quy trình để tận dụng năng lực mới, thay vì chỉ số hoá quy trình cũ. Bài đưa ra bảy ví dụ cụ thể về cách làm này; tiêu biểu là: tác tử AI tự động hoá việc kiểm tra dữ liệu và phê duyệt trong khâu lập ngân sách; token hoá và tiền kỹ thuật số của ngân hàng trung ương (CBDC) cho việc phát hành và quyết toán công cụ nợ công; và AI phân tích để phát hiện bất thường trong kiểm soát nội bộ, thay cho cách lấy mẫu kiểm tra thủ công.

**Hiện trạng: hệ thống cũ mắc ở đâu.** Gần như mọi nước đều có một dạng hệ thống tự động hoá, thường là FMIS. Nhưng các hệ thống PFM cũ có những đặc điểm chung: cài đặt tại chỗ (trên máy chủ của cơ quan) và phải cập nhật thủ công; vận hành rời rạc, không liên thông giữa các vụ, cục; hỗ trợ từ nhà cung cấp không nhất quán. Kết quả là chi phí vận hành cao mà hiệu quả thấp.

Độ phủ số hoá rất khác nhau giữa các chức năng. Theo Chỉ số Trưởng thành Công nghệ Chính phủ (GTMI) của Ngân hàng Thế giới, cập nhật tháng 12/2025:

| Chức năng | Số nước có hệ thống |
|---|---|
| Hệ thống thông tin quản lý tài chính (FMIS) | 193 |
| Hải quan | 191 |
| Thuế | 187 |
| Hưu trí | 184 |
| Quản lý nợ | 179 |
| Tài khoản kho bạc duy nhất (TSA) | 172 |
| Mua sắm điện tử | 166 |
| Trả lương | 163 |
| Quản lý nhân sự | 163 |
| **Quản lý đầu tư công** | **86** |

Quản lý đầu tư công tụt xa nhất: chưa bằng một nửa số nước có FMIS. Đây là mảng chi tiêu lớn, nhiều rủi ro lãng phí, nhưng lại ít được số hoá nhất.

**Năm yếu điểm dai dẳng:**

1. Dữ liệu kém chất lượng, không đầy đủ, thiếu nhất quán.
2. Silo: không liên thông giữa các cơ sở dữ liệu, hệ thống và cơ quan.
3. Kiến trúc công nghệ lỗi thời, ít linh hoạt, kém an toàn.
4. Rất ít dùng phương pháp phân tích dữ liệu hiện đại.
5. Báo cáo chậm và cồng kềnh, không giám sát được theo thời gian thực.

Bài lưu ý rằng ở một số nơi dữ liệu có sẵn nhưng không được dùng, vì cơ quan thiếu công cụ, giấy phép phần mềm, năng lực hoặc chuyên môn để quản lý và diễn giải những cơ sở dữ liệu lớn.

Con số đáng suy nghĩ nhất: từ năm 1984, Ngân hàng Thế giới đã tài trợ 156 dự án FMIS với tổng chi phí vượt 6 tỷ đô la, vậy mà phần lớn hệ thống vẫn không đáp ứng được nhu cầu đang thay đổi. Vấn đề vì thế không nằm ở chỗ thiếu tiền đầu tư.

Các nước kém phát triển còn chịu thêm ràng buộc về nguồn lực tài chính, hạ tầng số và kỹ năng. Nếu không có biện pháp riêng, khoảng cách số giữa nước phát triển và nước đang phát triển có nguy cơ nới rộng.

### 2. Ba kịch bản tương lai và bốn kiểu tổ chức

**Khung hình nón tương lai.** Bài dùng khung hình nón tương lai của Voros (2017), phân loại kịch bản theo mức khả dĩ: khả dĩ nhất, hợp lý và có thể. Khung gốc còn một loại nữa là kịch bản "phi lý", nhưng bài bỏ qua để tập trung vào lời khuyên thực tiễn.

| Kịch bản | Nội dung | Đánh giá |
|---|---|---|
| Thứ nhất: Tương lai khả dĩ nhất, "giữ nguyên như cũ" | hệ thống cũ ở nguyên, cải tiến từng chút, chỉ thay đổi khi có sức ép bên ngoài như thay đổi luật | lịch sử cho thấy đây là kịch bản chiếm ưu thế; mang lại ổn định nhưng lợi ích hạn chế |
| Thứ hai: Tương lai hợp lý, "hiện đại hoá tiệm tiến" | nâng cấp công nghệ sẵn có, xử lý điểm đau cụ thể: an ninh mạng, tự động hoá một số quy trình, mở rộng liên thông, đưa phân tích dữ liệu và trợ lý AI vào | khuyến nghị cho đa số nước: lựa chọn tốt thứ hai nhưng thực tế nhất |
| Thứ ba: Tương lai có thể, "đại tu chuyển đổi" | AI cho lập và báo cáo ngân sách; token hoá cho quản lý tài sản; hợp đồng thông minh cho trả lương, nợ, mua sắm; Internet vạn vật (IoT) cho kiểm kê và đầu tư công; Web3 cho định danh số; tiền số cho thu chi | tiềm năng lớn nhất, nhưng chỉ khả thi với nước đã có độ trưởng thành số cao và năng lực quản lý thay đổi hiệu quả |

Bài cảnh báo rằng kịch bản giữ nguyên như cũ không an toàn như vẻ ngoài: hệ thống cũ tốn kém để duy trì và dễ bị tấn công mạng, vì phải vá liên tục phần mềm lỗi thời và thiếu các lớp bảo vệ có sẵn trong công nghệ mới.

Ngoài ba con đường thuần, **cách tiếp cận lai** cũng hợp lệ: đại tu một vài chức năng trọng điểm, chọn theo ưu tiên và theo điểm đau lớn nhất, còn phần còn lại đi theo hiện đại hoá tiệm tiến. Cách này có thể tạo tiến bộ đáng kể mà không đòi hỏi mọi điều kiện của một cuộc đại tu toàn diện.

**Khung thời gian cho một cuộc đại tu: 10–20 năm.** Bài ước tính một cuộc đại tu chuyển đổi cần 10–20 năm, vì phải hội đủ bốn điều kiện, mỗi điều kiện có tốc độ riêng:

| Điều kiện | Thời gian cần |
|---|---|
| Thứ nhất: Sẵn sàng công nghệ | tiến bộ đáng kể trong 5–10 năm |
| Thứ hai: Ý chí chính trị | nước chậm có thể mất hơn 15 năm |
| Thứ ba: Năng lực thể chế | từ 5 đến hơn 20 năm |
| Thứ tư: Nguồn lực | nước mong manh và xung đột khó đạt được trong 10 năm |

**Bốn kiểu tổ chức.** Phỏng theo đường cong lan toả đổi mới của Rogers (1983), bài xếp các cơ quan trên một phổ:

| Kiểu | Hành vi |
|---|---|
| Người tiên phong | chủ động tìm công nghệ mới, chấp nhận rủi ro |
| Áp dụng chủ động | theo dõi xu hướng, áp dụng cái đã được thử nghiệm |
| Áp dụng phản ứng | ngại rủi ro, chờ người khác chứng minh trước |
| Áp dụng thụ động | chỉ thay đổi khi luật bắt buộc |
| (Không áp dụng) | vẫn làm chủ yếu bằng tay |

Văn hoá tổ chức, nguồn lực sẵn có và nhận thức về rủi ro quyết định vị trí của một cơ quan trên phổ này. Điều quan trọng là các kiểu không loại trừ nhau và không cố định: một cơ quan có thể trở nên cởi mở hơn với đổi mới bằng cách tạo môi trường khuyến khích ý tưởng mới và nhìn rủi ro như cơ hội.

**Hai ví dụ tiên phong.**

- **Kho bạc Brazil** hiện đại hoá quanh nền tảng thanh toán tức thời Pix, thăm dò đồng tiền số Drex, và tổ chức một cuộc thi lập trình năm 2023 để phát triển giải pháp dùng chứng khoán chính phủ token hoá, với tinh thần "mắc lỗi, học hỏi và trưởng thành".
- **Kho bạc Philippines** bán lô trái phiếu token hoá đầu tiên cho nhà đầu tư tổ chức vào tháng 11/2023, huy động 270 triệu đô la. Kho bạc hướng tới việc dùng ứng dụng GCash, vốn rất phổ biến, để đưa trái phiếu token hoá tới nhà đầu tư nhỏ lẻ, những người trước đây không tiếp cận được chứng khoán chính phủ.

### 3. Xu hướng áp dụng và bản đồ công nghệ theo nhiệm vụ

**Chiến lược quốc gia.** Tính đến 2025, 112 trong số 198 nước được khảo sát đã có chiến lược quốc gia về công nghệ mới nổi, trải khắp mọi khu vực và mọi mức thu nhập, trong đó có Bangladesh, Benin, Rwanda, Uganda và Việt Nam. Hơn 100 nước đã phê duyệt chiến lược quốc gia về AI, và 20 nước nữa dự kiến làm điều đó trong ba năm tới.

**Trong chính mảng PFM, mức áp dụng còn thấp.** Khảo sát OECD năm 2022 cho thấy chưa tới một phần tư các vụ ngân sách và kế toán dùng AI, tự động hoá quy trình bằng robot (RPA) hay điện toán đám mây, dù đa số đang cân nhắc. Bằng chứng giai thoại cho thấy bộ tài chính chủ yếu thăm dò AI như một công cụ hỗ trợ, chưa phải để thay thế quy trình.

**Bản đồ công nghệ theo nhiệm vụ.** Thay vì liệt kê công nghệ, bài trình bày năm bảng ánh xạ từng công nghệ vào nhiệm vụ PFM cụ thể. Các ví dụ thực tế đáng chú ý:

| Nước | Ứng dụng |
|---|---|
| UAE | Bộ Tài chính tự động hoá 63 quy trình và quy trình con bằng robot |
| Brazil | dùng xử lý ngôn ngữ tự nhiên để phân loại chi tiêu theo chức năng, giảm thời gian từ 1.000 giờ xuống 8 giờ |
| Rwanda | thăm dò học máy để phân loại các dòng ngân sách chính xác hơn |
| Paraguay | xây hệ thống trên kiến trúc vi dịch vụ (chia hệ thống thành nhiều dịch vụ nhỏ độc lập) |
| Honduras | dùng Kubernetes để triển khai, và tích hợp kiểm tra an ninh vào quy trình phát triển (DevSecOps) |
| Georgia | Bộ Tài chính xây nguyên mẫu AI quản lý rủi ro thanh toán kho bạc, với 42 mô hình học máy phân tích dữ liệu lịch sử; khoản thanh toán rủi ro thấp đi "kênh xanh" tự động, còn "kênh đỏ" được rà soát kỹ hơn và chất lượng hơn |
| Kazakhstan | thí điểm CBDC cho một chương trình trợ cấp |
| Mexico | công bố danh mục đầu tư công trên nền tảng định vị địa lý |
| Nam Phi, Uruguay | công bố dữ liệu ngân sách theo chuẩn Open Fiscal Data Package |

Ví dụ của Brazil cho thấy quy mô lợi ích có thể rất lớn: một việc trước đây tốn 1.000 giờ người nay chỉ còn 8 giờ, tức giảm hơn 99%.

**Kiến trúc hệ thống.** Bài nhấn mạnh một điểm hạ tầng thường bị bỏ qua. Nếu hệ thống được xây từ các thành phần liên kết lỏng (mỗi phần độc lập, giao tiếp qua giao diện chuẩn) và tối ưu hoá đa đám mây (dùng nhiều nhà cung cấp đám mây), thì có thể hiện đại hoá liên tục từng phần thay vì phải thay cả hệ thống một lần. Cách này tránh tình trạng hệ thống lỗi thời theo khối, kéo theo chi phí bảo trì tăng và lỗ hổng an ninh.

### 4. Độ trưởng thành và nhiệt tình đầu cơ

**Độ trưởng thành.** Lý do thường gặp nhất khiến tổ chức từ chối công nghệ mới là công nghệ chưa trưởng thành. Công nghệ non trẻ có những khiếm khuyết vốn có, chỉ giảm dần khi nó trưởng thành.

**Đường cong chữ S.** Hiệu năng của một công nghệ tăng chậm khi mới ra đời, rồi tăng nhanh và vượt công nghệ đang dùng. Thách thức với chính phủ là chọn đúng thời điểm chuyển đổi trong giai đoạn gián đoạn này: chuyển quá sớm thì gánh khiếm khuyết của công nghệ non, chuyển quá muộn thì bỏ lỡ giá trị và tiếp tục trả chi phí cho công nghệ cũ.

**Chu kỳ kỳ vọng thổi phồng** bổ sung chiều tâm lý thị trường, gồm năm giai đoạn:

1. kích hoạt đổi mới;
2. đỉnh kỳ vọng thổi phồng;
3. vực vỡ mộng;
4. dốc khai sáng;
5. cao nguyên năng suất.

Bài cảnh báo rằng nhà cung cấp công nghệ có thể đưa ra lời hứa phóng đại và tạo cảm giác cấp bách để thúc đẩy việc mua sắm, đặc biệt khi công nghệ đang ở gần đỉnh kỳ vọng.

**Cảnh báo phương pháp.** Các phân tích dựa trên xu hướng chung của ngành công nghệ có thể bỏ sót đặc thù của PFM. Ví dụ: thị giác máy tính được xếp ở cao nguyên năng suất theo đánh giá chung, nhưng trong PFM nó vẫn có rất ít tình huống sử dụng và chưa đạt trạng thái đó. Một công nghệ trưởng thành ở nơi khác chưa chắc đã trưởng thành cho bộ tài chính.

### 5. Cách tiếp cận tối đa hoá giá trị

**Công thức.** Giá trị VM = G × F, trong đó G là điểm lợi ích và F là điểm khả thi, mỗi điểm từ 1 đến 10, nên VM từ 1 đến 100. Bài nói rõ công thức không bắt buộc áp dụng trong mọi trường hợp; nó là một khung khái niệm để cấu trúc và dẫn dắt việc ra quyết định.

**Điểm lợi ích G** là tổng có trọng số của sáu nhóm lợi ích:

| Nhóm lợi ích | Nội dung |
|---|---|
| Thứ nhất: Quy trình | tự động hoá việc lặp lại, tiết kiệm chi phí |
| Thứ hai: Đầu ra | dữ liệu sẵn có hơn, đáng tin hơn |
| Thứ ba: Kết quả | ra quyết định dựa trên dữ liệu, dịch vụ công tốt hơn |
| Thứ tư: Trách nhiệm giải trình | minh bạch hơn, ít khả năng bóp méo dữ liệu |
| Thứ năm: An ninh | thay công nghệ cũ đã hết hỗ trợ, vốn là lỗ hổng |
| Thứ sáu: Sẵn sàng tương lai | chuẩn bị cho các thay đổi tiếp theo |

Trọng số do chính bộ tài chính đặt, cộng lại bằng 1, và phải gắn với chiến lược của tổ chức. Nước muốn cải thiện minh bạch tài khoá sẽ đặt trọng số cao cho trách nhiệm giải trình; nước vừa bị lộ dữ liệu sẽ ưu tiên an ninh.

**Điểm khả thi F** là tổng có trọng số của bốn yếu tố:

| Yếu tố | Câu hỏi |
|---|---|
| Thứ nhất: Kỹ thuật | công nghệ có phù hợp mục đích không, đã đủ trưởng thành chưa, có tương thích với hệ thống hiện có không |
| Thứ hai: Kinh tế | chi phí ban đầu và bảo trì so với khoản tiết kiệm; tỷ suất hoàn vốn |
| Thứ ba: Vận hành | gián đoạn quy trình, nhu cầu đào tạo, thay đổi luật, quản lý thay đổi |
| Thứ tư: Tiến độ | thời gian triển khai có thực tế không |

Trọng số khả thi cũng do hoàn cảnh quyết định; ví dụ nước nợ cao đặt trọng số lớn cho yếu tố kinh tế. Bài khuyên chấm điểm khả thi với tầm nhìn dài hạn, tính cả hàm ý bảo trì, để tránh vội vàng áp dụng vì nhiệt tình đầu cơ hoặc vì tư duy "giải pháp đi tìm vấn đề" (có công nghệ trước rồi mới đi tìm chỗ dùng).

**Ngưỡng đánh giá:**

- G hoặc F từ 4 trở xuống là thấp; từ 7 trở lên là cao.
- VM dưới 30 là thấp; trên 50 là cao.

**Ma trận lợi ích – khả thi.** Kết hợp hai điểm cho bốn góc phần tư:

| | Khả thi thấp | Khả thi cao |
|---|---|---|
| **Lợi ích cao** | Góc II: cân nhắc, thận trọng; làm thí điểm theo giai đoạn; VM khoảng 5–50 | Góc I: nên áp dụng; VM khoảng 30–100 |
| **Lợi ích thấp** | Góc III: chờ công nghệ trưởng thành, hoặc cải cách thể chế trước; VM khoảng 1–25 | Góc IV: áp dụng nhưng đừng kỳ vọng quá nhiều; VM khoảng 5–50 |

**Ví dụ tính toán: hợp đồng thông minh cho thanh toán xây dựng.** Bối cảnh giả định là một nước có nợ công cao, vừa công bố chiến lược chuyển đổi số năm 2024; bộ tài chính có Kế hoạch Năm năm hiện đại hoá PFM nhưng không sẵn sàng chấp nhận rủi ro lớn. Vấn đề: thanh toán theo tiến độ công trình đang làm thủ công, cán bộ mua sắm phải xác nhận từng mốc, gây chậm trễ và sai sót. Bài so sánh ba phương án.

*Phương án A: hợp đồng thông minh trên blockchain.* Hợp đồng tự động chi tiền khi điều kiện được ghi nhận trên chuỗi khối.

- Lợi ích: giảm 50% thời gian xử lý, tiết kiệm 15% chi phí hành chính. Điểm thành phần: quy trình 9, đầu ra 8, kết quả 7, trách nhiệm giải trình 7. Kết quả G = 7,75.
- Khả thi: không hệ thống nào hiện có dùng blockchain và công nghệ chưa trưởng thành (kỹ thuật 3); chi phí ban đầu 100.000 đô la, tiết kiệm 50.000 đô la mỗi năm, nhưng chi phí tích hợp chưa rõ (kinh tế 6); chưa có khung pháp lý cho hợp đồng thông minh (vận hành 3); cần hơn 18 tháng (tiến độ 4). Vì nợ cao, trọng số kinh tế là 0,4. Kết quả F = 4,4.
- VM: bài ghi VM = 7,75 × 4,4 = 33 (phép nhân chính xác cho khoảng 34,1; cả hai con số đều cho cùng kết luận). Phương án nằm ở góc phần tư II.
- Quyết định: chưa áp dụng; hợp tác với nhà cung cấp và viện nghiên cứu để lấp khoảng trống khả thi trước.

*Phương án B: chương trình tự thực thi trên nền tảng sẵn có, không dùng blockchain.* Quy trình: nhà thầu báo hoàn thành mốc, hệ thống báo cho cán bộ, cán bộ duyệt, rồi hệ thống kích hoạt thanh toán từ kho bạc.

- G = 7,5: lợi ích quy trình thấp hơn một chút vì vẫn còn bước duyệt thủ công, nhưng có nhật ký kiểm toán, phân quyền và chữ ký số.
- F = 7,6: dễ tích hợp, công nghệ trưởng thành, không vướng pháp lý, triển khai nhanh.
- VM = 57, góc phần tư I: áp dụng.

*Phương án B kết hợp AI phát hiện bất thường.* AI so sánh tiến độ báo cáo với lịch trình và lịch sử của nhà thầu, cảnh báo sai lệch, và làm bước kiểm tra lần cuối trước khi tiền được chuyển đi.

- G = 8,75: điểm trách nhiệm giải trình tăng 2 nhờ chống gian lận chủ động.
- F = 7,2: điểm kỹ thuật và điểm tiến độ mỗi thứ giảm 1.
- VM = 63, cao nhất trong ba phương án.
- Quyết định: áp dụng cả hai nhưng theo giai đoạn, làm chương trình tự thực thi trước, tích hợp AI sau.

Bài học của ví dụ: công nghệ "mới nhất" (blockchain) không thắng. Cùng một mục tiêu đạt được tốt hơn bằng công nghệ đã trưởng thành, và AI chỉ thêm giá trị khi đặt lên một nền tảng đã chạy ổn.

**Bài học từ thất bại: hệ thống trả lương Phoenix của Canada.** Hệ thống này được xây để tiết kiệm chi phí và nâng hiệu quả, nhưng cuối cùng bị Tổng Kiểm toán kết luận là "kém hiệu quả hơn và tốn kém hơn hệ thống 40 năm tuổi mà nó thay thế". Nguyên nhân: quản lý dự án yếu kém, thiếu chức năng quan trọng, kiểm thử không đầy đủ, ít tham vấn người dùng và thiếu giám sát.

**Công nghệ phải đi cùng thiết kế lại quy trình và cải cách pháp lý.** Để tối đa hoá giá trị, việc áp dụng công nghệ phải đi kèm đánh giá lại, thiết kế lại quy trình nghiệp vụ và cải cách pháp lý. Cạm bẫy phổ biến là tự động hoá nhiệm vụ thủ công mà không xem xét lại chính quy trình dưới ánh sáng năng lực công nghệ mới. Ví dụ cụ thể về rào cản pháp lý: nếu luật chưa chấp nhận hồ sơ số là chứng từ hợp pháp cho mục đích kiểm toán, cơ quan buộc phải giữ song song quy trình thủ công, kể cả việc trao đổi giấy tờ vật lý, và mất phần lớn lợi ích của hệ thống số.

### 6. Rủi ro và cây quyết định

**Các nhóm rủi ro.** Bài liệt kê các nhóm rủi ro kèm biện pháp giảm thiểu:

- an ninh mạng;
- quyền riêng tư và chủ quyền dữ liệu;
- pháp lý và quy định;
- thiếu hụt kỹ năng và tri thức;
- đạo đức;
- quản lý thay đổi;
- phụ thuộc nhà cung cấp;
- khả năng liên thông.

**Phụ thuộc nhà cung cấp** được nhấn mạnh riêng. Rủi ro gồm việc phụ thuộc vào hệ thống độc quyền, khó chuyển sang nhà cung cấp khác, cộng thêm khả năng nhà cung cấp mất ổn định hoặc bị mua lại, nhất là khi làm việc với công ty khởi nghiệp. Biện pháp: chiến lược đa nhà cung cấp; bảo đảm có thể chuyển dữ liệu đi nơi khác nhờ chuẩn mở; đàm phán điều khoản cấp phép linh hoạt và điều khoản thoát hợp đồng.

**Rủi ro đạo đức** gồm thiên lệch thuật toán và nguy cơ kết quả phân biệt đối xử khi máy ra quyết định tự động. Biện pháp: bộ quy tắc đạo đức, uỷ ban đạo đức, kiểm toán đạo đức định kỳ có công bố kết quả, và đào tạo.

**Cây quyết định.** Bài đề xuất một cây quyết định bắt đầu từ một trong hai tác nhân kích hoạt: một mục tiêu PFM cụ thể cần đạt, hoặc một rủi ro số cần xử lý. Từ đó, người ra quyết định đi qua lần lượt các câu hỏi:

1. Lợi ích kỳ vọng đã được xác định và đo lường được chưa?
2. Lý thuyết thay đổi có trung lập về công nghệ không? Nếu có, tức là vấn đề có thể giải quyết bằng cải cách quy trình hoặc pháp lý mà không cần công nghệ mới.
3. Có bằng chứng loại công nghệ này giúp đạt được mục tiêu không?
4. Công nghệ đã trưởng thành chưa?
5. Tổ chức có hạ tầng và kỹ năng cần thiết không?

Mỗi nhánh dẫn tới một khuyến nghị khác nhau: áp dụng ngay, nâng cấp kỹ năng trước, xây phòng thí nghiệm thử nghiệm, hoặc tìm giải pháp khác không dựa vào công nghệ đó.

### 7. Áp dụng bền vững

**Mười thực hành được đề xuất:**

1. thiết lập tầm nhìn và chiến lược rõ ràng;
2. chú trọng trải nghiệm người dùng thông qua sự tham gia của họ;
3. bảo đảm nguồn tài trợ bền vững;
4. dự đoán và quản lý sự phản kháng;
5. xây dựng và giữ chân năng lực, kỹ năng;
6. tuân thủ khả năng liên thông và các chuẩn;
7. áp dụng phương pháp linh hoạt và phát triển lặp;
8. hợp tác và tìm đối tác;
9. giảm thiểu rủi ro an ninh và bảo đảm quyền riêng tư dữ liệu;
10. theo dõi các công nghệ mới nổi tiếp theo.

**Con người.** Hiểu biết về quy trình nghiệp vụ từ góc nhìn của bộ tài chính không thể thay thế việc tiếp xúc trực tiếp với người dùng thực tế, tức những người vận hành hệ thống hằng ngày để thực hiện giao dịch hoặc lập báo cáo.

**Vấn đề sau khi dự án kết thúc.** Bài nêu thẳng một tình trạng phổ biến ở nước đang phát triển: nhà cung cấp cài đặt và triển khai hệ thống mới, rồi khi dự án kết thúc, chính nhân viên công nghệ thông tin của cơ quan phải hỗ trợ tuyến đầu, dù không được đào tạo riêng về hệ thống và hiểu biết hạn chế về chức năng của nó. Hậu quả có thể là mất dữ liệu, nhập dữ liệu sai vào hệ thống, hoặc an ninh bị tổn hại dẫn tới gian lận và trộm cắp.

**An ninh và bề mặt tấn công.** Hệ thống càng nhiều năng lực và càng phức tạp thì bề mặt tấn công càng lớn. Mỗi năng lực và cơ chế mới, từ hệ thống dữ liệu lớn tới blockchain tới tài nguyên đám mây, đều làm tăng khả năng bị tấn công. Nguyên nhân có thể là sự bất cẩn hay thiếu hiểu biết của người triển khai, lỗi ẩn trong phần mềm thương mại, cấu hình sai, hoặc tấn công phi kỹ thuật (lừa người dùng tiết lộ mật khẩu chẳng hạn). Đây là lý do mỗi công nghệ mới phải được tính cả chi phí an ninh đi kèm.

**Môi trường thử nghiệm an toàn.** Bài nêu ba hình thức để thử công nghệ mới mà không đặt cả hệ thống vào rủi ro:

| Hình thức | Ví dụ |
|---|---|
| Phòng thí nghiệm đổi mới của chính phủ | 18F Lab của Hoa Kỳ, đã hỗ trợ 34 cơ quan hoàn thành 455 dự án trong mười năm |
| Hộp cát quản lý (thử nghiệm với yêu cầu pháp lý được nới lỏng) | chương trình Giấy phép Thử nghiệm Đổi mới của Cơ quan Dịch vụ Tài chính Dubai; hộp cát fintech của Cơ quan Tiền tệ Singapore |
| Bãi thử công nghệ (dành cho một công nghệ cụ thể) | Trung tâm Dự án Trí tuệ Tiên tiến RIKEN của Nhật Bản |

**Kết luận: một quá trình liên tục, không phải cải cách một lần.** Chuyển đổi số PFM đòi hỏi giám sát và cải tiến liên tục cả công nghệ lẫn quy trình. Trước đây, hệ thống được xây để dùng nhiều năm chỉ với bảo trì; nay công nghệ thay đổi ngày càng nhanh. Bài đề xuất thiết lập cơ chế thẩm định và hiệu chỉnh sau triển khai: một vòng phản hồi so sánh kết quả thực tế với điểm G và F đã dự đoán, rồi điều chỉnh trọng số và cách chấm điểm dựa trên bài học đó cho các dự án sau.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| PFM | Quản lý tài chính công, bao trùm mọi khâu quản lý nguồn lực công |
| FMIS | Hệ thống thông tin quản lý tài chính, xương sống số hoá của PFM |
| GTMI | Chỉ số Trưởng thành Công nghệ Chính phủ của Ngân hàng Thế giới |
| TSA | Tài khoản kho bạc duy nhất |
| Digital by design | Số hoá theo thiết kế, thiết kế lại quy trình thay vì số hoá quy trình cũ |
| Value maximization (VM) | Tối đa hoá giá trị, khung quyết định VM = lợi ích × khả thi |
| Futures cone | Hình nón tương lai, phân loại kịch bản theo mức khả dĩ |
| Probable future | Tương lai khả dĩ nhất, giữ nguyên như cũ |
| Plausible future | Tương lai hợp lý, hiện đại hoá tiệm tiến |
| Possible future | Tương lai có thể, đại tu chuyển đổi |
| Technology S curve | Đường cong chữ S, hiệu năng công nghệ theo thời gian và nỗ lực |
| Hype cycle | Chu kỳ kỳ vọng thổi phồng, từ đỉnh kỳ vọng tới cao nguyên năng suất |
| Speculative enthusiasm | Nhiệt tình đầu cơ quanh công nghệ mới, nguồn gây quyết định sai |
| Fit for purpose | Phù hợp mục đích, tiêu chí đánh giá khả thi kỹ thuật |
| RPA | Tự động hoá quy trình bằng robot |
| Microservices | Vi dịch vụ, chia hệ thống thành các dịch vụ nhỏ độc lập |
| Loosely coupled | Liên kết lỏng, các thành phần tương tác qua giao diện chuẩn nhưng độc lập |
| Multicloud optimization | Tối ưu hoá đa đám mây, dùng nhiều nhà cung cấp để giảm phụ thuộc |
| DevSecOps | Tích hợp kiểm tra an ninh vào mọi khâu phát triển phần mềm |
| Zero-knowledge proof | Bằng chứng không tiết lộ, xác thực mà không lộ dữ liệu nền |
| Attack surface | Bề mặt tấn công, số cơ hội để kẻ tấn công xâm nhập hệ thống |
| Vendor lock-in | Phụ thuộc nhà cung cấp, khó chuyển đổi vì hệ thống độc quyền |
| Regulatory sandbox | Hộp cát quản lý, môi trường thử nghiệm với yêu cầu được nới lỏng |
| Innovation lab | Phòng thí nghiệm đổi mới trong chính phủ |
| Technology testbed | Bãi thử công nghệ dành cho một công nghệ cụ thể |
| SMART indicators | Chỉ tiêu cụ thể, đo được, khả thi, phù hợp, có thời hạn |

## Câu nói đáng nhớ

> "A common pitfall is automating manual tasks without evaluating existing processes in light of new technological capabilities."

> "The digital journey in PFM is an ongoing evolution, not a one-time reform."

> "Greater complexity and functionality of systems create a correspondingly larger attack surface."

## Đánh giá và phát hiện đáng chú ý

### Sáu tỷ đô la và bốn mươi năm: con số này lẽ ra phải định hình cả tài liệu

Một trăm năm mươi sáu dự án hệ thống thông tin quản lý tài chính do Ngân hàng Thế giới tài trợ từ năm 1984, tổng chi phí vượt sáu tỷ đô la, và kết luận vẫn là phần lớn hệ thống không đáp ứng được nhu cầu đang thay đổi. Con số này được đặt trong một khung cảnh báo nhỏ, nhưng nó là dữ kiện quan trọng nhất trong toàn bộ tài liệu.

Bốn thập niên là đủ dài để loại trừ giả thuyết "công nghệ chưa đủ tốt". Trong khoảng thời gian đó, công nghệ đã đi từ máy tính lớn tới đám mây. Nếu kết quả vẫn không đạt, thì nguyên nhân nằm ở chỗ khác.

Và chính tài liệu đã cung cấp bằng chứng về chỗ khác đó, qua trường hợp hệ thống trả lương Phoenix của Canada: quản lý dự án yếu, thiếu chức năng quan trọng, kiểm thử không đầy đủ, ít tham vấn người dùng, thiếu giám sát. Kết quả là một hệ thống mới **kém hiệu quả hơn và tốn kém hơn hệ thống bốn mươi năm tuổi mà nó thay thế**.

Hãy để ý: không một nguyên nhân nào trong danh sách đó là nguyên nhân chọn sai công nghệ. Phoenix không thất bại vì Canada chọn nhầm nền tảng. Nó thất bại ở khâu thực thi và ở khâu thể chế.

Đây là chỗ hở lớn nhất của tài liệu. Công cụ mà bài đưa ra — công thức tối đa hoá giá trị — là một công cụ **chọn lựa**: nó giúp trả lời nên áp dụng công nghệ nào. Nhưng bằng chứng lịch sử mà chính bài trình bày nói rằng thất bại không nằm ở việc chọn. Một điểm khả thi cao hơn sẽ không cứu được Phoenix, vì mọi nguyên nhân thất bại của Phoenix đều phát sinh **sau khi** quyết định đã được đưa ra.

### Giá trị thật của công thức không phải chỗ nó giúp chọn đúng, mà chỗ nó buộc phải ghi lại

Công thức nhân hai điểm số với nhau là một lựa chọn có nội dung: dạng nhân nghĩa là một yếu tố gần bằng không sẽ triệt tiêu cả dự án, dù yếu tố kia cao đến đâu. Đó là mô hình hoá đúng, vì một công nghệ tuyệt vời nhưng không triển khai được thì giá trị bằng không, chứ không phải bằng trung bình.

Nhưng cả mười thành phần đều được chấm bằng phán đoán chủ quan, và chấm bởi chính cơ quan đang muốn làm dự án. Trọng số cũng do chính cơ quan đó đặt. Trong điều kiện đó, một người đã quyết định muốn làm có thể tạo ra bất kỳ điểm số nào mình cần, và làm điều đó mà không hề gian dối — chỉ cần đặt trọng số hơi khác đi.

Vậy công thức này có vô dụng không? Không, nhưng giá trị của nó nằm ở chỗ khác với chỗ bài nói. Nó buộc người ra quyết định phải **viết xuống các giả định của mình bằng con số, kèm trọng số, tại thời điểm quyết định**. Điều đó tạo ra một hồ sơ có thể đối chiếu về sau.

Và đây chính là điều kiện cần cho khuyến nghị cuối cùng của bài, khuyến nghị bị đặt ở vị trí khiêm tốn nhất: cơ chế thẩm định sau triển khai, so sánh kết quả thực tế với điểm số đã dự đoán, rồi hiệu chỉnh cách chấm cho các dự án sau. Không có hồ sơ ex ante thì không có cách nào làm việc so sánh ex post, và không có việc so sánh ex post thì không có học hỏi.

Nói cách khác, công thức là **công cụ trách nhiệm giải trình được nguỵ trang thành công cụ phân tích**. Nên đọc nó theo đúng chức năng đó, và nên chống lại cám dỗ coi con số 57 hay 63 như một kết quả tính toán khách quan.

### Ví dụ tính toán mới là lập luận mạnh nhất, mạnh hơn cả công thức sinh ra nó

Trong toàn bộ tài liệu, phần có sức thuyết phục cao nhất là ví dụ về thanh toán theo tiến độ công trình, và lý do không phải vì nó minh hoạ công thức mà vì **kết quả của nó phản trực giác đúng theo chiều mà ngành cần nghe**.

Hợp đồng thông minh trên blockchain — phương án hào nhoáng, phương án mà mọi hội thảo về công nghệ trong khu vực công đều nói tới — cho điểm lợi ích cao nhưng thất bại ở khả thi, và ra kết quả khoảng 34 (bài ghi 33), tức là chưa nên làm. Một quy trình tự thực thi trên chính nền tảng đã có, không dùng blockchain, với nhật ký kiểm toán, phân quyền và chữ ký số, cho 57. Thêm một lớp AI phát hiện bất thường trước khi tiền chuyển đi, cho 63.

Điều đáng học ở đây là **phương án tốt nhất là phương án nhàm chán nhất**, và nó tốt nhất không phải vì lợi ích lớn hơn mà vì nó dùng công nghệ đã trưởng thành, trên hạ tầng đã có, không vướng khoảng trống pháp lý, và triển khai được trong thời hạn hợp lý. Chênh lệch điểm lợi ích giữa hai phương án chỉ là 7,75 so với 7,5 — gần như bằng nhau. Toàn bộ khác biệt nằm ở khả thi.

Kết quả này khái quát hoá được rất xa: trong khu vực công, **phần lớn giá trị nằm ở việc làm cho quy trình có nhật ký, có phân quyền và có tự động hoá, chứ không nằm ở tầng công nghệ bên dưới**. Ai đã từng nghe một bài trình bày về việc đưa blockchain vào quản lý ngân sách nên đọc kỹ ví dụ này trước khi đọc bất cứ thứ gì khác trong tài liệu.

### Câu hỏi sắc nhất nằm ở nhánh thứ hai của cây quyết định và hầu như không ai hỏi nó

Cây quyết định có một câu hỏi mà nếu được hỏi một cách trung thực sẽ loại bỏ một phần rất lớn các dự án công nghệ trong khu vực công: **lý thuyết thay đổi có trung lập về công nghệ không, và nếu có, thì cải cách quy trình hoặc cải cách pháp lý có giải quyết được vấn đề mà không cần công nghệ mới hay không?**

Đây là câu hỏi "liệu có cần phần mềm không". Nó hiếm khi được đặt ra, và lý do không phải là kỹ thuật. Một dự án công nghệ có ngân sách, có nhà cung cấp, có lễ khởi động, có báo cáo tiến độ và có ảnh chụp khi bàn giao. Một cải cách quy trình thì không có gì trong số đó, dù nó có thể giải quyết đúng vấn đề với chi phí bằng một phần trăm.

Chính tài liệu đưa ra ví dụ minh hoạ hoàn hảo cho điểm này, ở một chỗ khác và không nối lại: rào cản khiến nhiều quy trình vẫn phải làm thủ công không phải là thiếu phần mềm, mà là **hồ sơ số chưa được chấp nhận làm chứng từ hợp pháp cho mục đích kiểm toán**. Chừng nào quy định đó chưa đổi, cơ quan vẫn buộc phải in ra, ký tay và luân chuyển giấy, bất kể hệ thống điện tử tốt đến đâu.

Tức là trong trường hợp này, một sửa đổi văn bản pháp quy không tốn tiền sẽ mở khoá nhiều giá trị hơn bất kỳ khoản đầu tư công nghệ nào. Đây là cùng một mô thức xuất hiện ở các tài liệu khác trong thư mục, nơi luật về tính chung thẩm của quyết toán là điều kiện tiên quyết rẻ nhất cho toàn bộ hạ tầng token hoá: **bước rẻ nhất và ít hào nhoáng nhất thường là bước chặn đường tất cả các bước còn lại**.

### Khoảng trống ở quản lý đầu tư công không phải khoảng trống công nghệ

Con số 86 trên 193 cho quản lý đầu tư công, đặt cạnh 193 cho hệ thống quản lý tài chính, 191 cho hải quan, 187 cho thuế và 172 cho tài khoản kho bạc duy nhất, là dữ kiện gây chú ý nhất trong bảng độ phủ. Mọi chức năng khác gần như đã phủ kín; riêng chức năng này ở dưới một nửa.

Câu hỏi đúng là vì sao. Không phải vì công nghệ khó hơn — theo dõi tiến độ dự án và chi phí không phức tạp hơn quản lý nợ hay tính lương. Không phải vì ít quan trọng hơn — đầu tư công thường là khoản chi lớn nhất có thể kiểm soát được trong ngân sách.

Lời giải thích hợp lý hơn mang tính **kinh tế chính trị**. Trong các chức năng quản lý tài chính công, quản lý đầu tư công là chức năng có nhiều quyền tuỳ nghi nhất: chọn dự án nào, thẩm định ra sao, nghiệm thu khối lượng thế nào, điều chỉnh tổng mức đầu tư khi nào. Số hoá một quy trình có nghĩa là ghi lại mọi bước, gắn thời điểm và gắn người thực hiện — tức là **thu hẹp đúng phần quyền tuỳ nghi ấy**. Ở những chức năng mà quyền tuỳ nghi ít giá trị, số hoá diễn ra nhanh. Ở chức năng mà nó có giá trị, số hoá bị chậm lại, và sự chậm ấy hiện ra dưới dạng "chưa đủ nguồn lực" hoặc "hệ thống chưa phù hợp".

Cách đọc này cũng giải thích vì sao ví dụ tính toán của bài lại chọn đúng chủ đề thanh toán theo tiến độ xây dựng: đó là điểm đau lớn nhất, và cũng là điểm khó nhất, và hai điều đó là cùng một lý do.

Điều này nối trực tiếp với các phân tích về đầu tư công và nợ công trong thư mục khác của kho tài liệu này, nơi khoảng cách hiệu quả đầu tư công — phần giá trị bị hao hụt giữa số tiền chi ra và tài sản hạ tầng thực sự nhận được — là một trong những nguồn lãng phí lớn nhất ở các nền kinh tế đang phát triển. Tài liệu này không nhắc tới khoảng cách đó, nhưng bảng số liệu của nó vừa giải thích vì sao khoảng cách ấy dai dẳng: công cụ để đóng nó thì tồn tại và không đắt, nhưng nó chưa được triển khai ở hơn một nửa số nước.

### Một mâu thuẫn nội tại mà công thức không xử lý được

Trong sáu nhóm lợi ích, an ninh được tính là một **lợi ích** của việc áp dụng công nghệ mới, với lý lẽ đúng: hệ thống cũ hết hỗ trợ là một lỗ hổng, phải vá phần mềm lỗi thời là một rủi ro thường trực.

Nhưng ở phần cuối, bài phát biểu một nguyên lý ngược chiều: hệ thống càng nhiều năng lực và càng phức tạp thì bề mặt tấn công càng lớn. Mỗi năng lực mới — dữ liệu lớn, sổ cái phân tán, tài nguyên đám mây — đều thêm một cánh cửa.

Cả hai mệnh đề đều đúng, và chúng kéo ngược chiều nhau. Không nâng cấp thì chịu rủi ro của phần mềm hết hỗ trợ; nâng cấp thì chịu rủi ro của bề mặt tấn công lớn hơn. Nghĩa là tồn tại một điểm tối ưu ở giữa, và công thức như đang được trình bày **không tìm được điểm đó**, vì an ninh chỉ xuất hiện ở vế lợi ích chứ không xuất hiện ở vế khả thi hay ở một vế chi phí nào.

Cách sửa khá đơn giản và đáng được nêu: chấm điểm an ninh theo **mức thay đổi ròng** của rủi ro, tức là rủi ro giảm được nhờ loại bỏ hệ thống cũ, trừ đi rủi ro tăng thêm do bề mặt mới. Với một số công nghệ, hiệu số này là âm, và đó là thông tin mà một bộ tài chính rất cần biết trước khi ký hợp đồng.

### Với Việt Nam: bài này chỉ đúng vào điểm nghẽn quen thuộc nhất, và đưa ra một lời giải khiêm tốn

Việt Nam được nêu tên trong nhóm 112 nước đã có chiến lược quốc gia về công nghệ mới nổi. Nhưng phần đáng đọc với Việt Nam không phải phần chiến lược mà là ví dụ tính toán, vì nó mô tả gần như chính xác một vấn đề được nói tới liên tục trong nhiều năm: **giải ngân vốn đầu tư công chậm**, với nút thắt nằm ở khâu nghiệm thu khối lượng, xác nhận tiến độ và hoàn thiện hồ sơ thanh toán.

Lời giải mà bài đưa ra cho đúng vấn đề đó có ba đặc điểm đáng chú ý, và cả ba đều đi ngược lại kiểu đề xuất thường thấy.

**Thứ nhất, nó không cần công nghệ mới.** Phương án thắng là một quy trình tự thực thi trên nền tảng đã có: nhà thầu báo mốc, hệ thống tự thông báo cho cán bộ, cán bộ duyệt, thanh toán được kích hoạt từ kho bạc. Toàn bộ giá trị đến từ việc quy trình có nhật ký kiểm toán, có phân quyền rõ và có chữ ký số — không có phần nào đòi hỏi sổ cái phân tán hay bất cứ thứ gì chưa trưởng thành.

**Thứ hai, lớp có giá trị gia tăng cao nhất là lớp phát hiện bất thường.** Việc thêm một bước so sánh tiến độ báo cáo với lịch trình và với lịch sử nhà thầu, rồi cảnh báo sai lệch **trước khi tiền chuyển đi**, làm điểm trách nhiệm giải trình tăng mạnh nhất trong cả ví dụ. Đây là kiểm soát chủ động thay cho hậu kiểm bằng lấy mẫu, và nó đúng là điểm yếu cố hữu của mô hình kiểm soát dựa trên thanh tra sau.

**Thứ ba, và đây là điều kiện tiên quyết dễ bị bỏ qua:** việc công nhận hồ sơ số là chứng từ hợp pháp cho mục đích kiểm toán. Chừng nào quy định kiểm toán còn đòi chứng từ giấy có chữ ký tươi, mọi quy trình điện tử phía trên đều chỉ là một lớp song song, và cơ quan phải vận hành đồng thời hai hệ thống — chi phí kép mà không có lợi ích kép.

Một cảnh báo cuối, lấy thẳng từ bài và rất đúng với thực tế của nhiều cơ quan: mô hình nhà cung cấp cài đặt hệ thống rồi rời đi khi dự án kết thúc, để lại việc hỗ trợ vận hành cho nhân viên công nghệ thông tin của cơ quan vốn không được đào tạo riêng về hệ thống đó. Hậu quả mà bài liệt kê — mất dữ liệu, nhập sai dữ liệu, an ninh bị tổn hại dẫn tới gian lận — không phải lý thuyết. Điều đó có nghĩa là **chi phí thật của một hệ thống phải bao gồm nhiều năm vận hành và một đội ngũ trong biên chế**, và bất kỳ phép tính khả thi kinh tế nào bỏ qua khoản đó đều là phép tính sai.
