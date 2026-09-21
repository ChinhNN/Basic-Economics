# Decoding Fiscal Messaging: How G7 Finance Ministries Communicate — Giải mã thông điệp tài khoá: bộ tài chính các nước G7 truyền thông ra sao

**Nguồn:** IMF Working Paper WP/2026/117.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 5, không có trang bìa, tóm tắt và trang tác giả).
**Ý chính:** Ngân hàng trung ương đã biến truyền thông thành một công cụ chính sách, nhưng bộ tài chính thì vẫn "làm" nhiều hơn "nói". Bài dựng một kho dữ liệu **hơn 500 văn bản tài khoá của G7, 2000–2024**, gồm ba kênh: **tài liệu ngân sách, bài phát biểu của bộ trưởng và thông cáo báo chí**, rồi dùng xử lý ngôn ngữ tự nhiên và GPT-4o-mini để đo độ dài, độ dễ đọc, sự phong phú ngôn từ, chủ đề và sắc thái. Kết quả là một **kiến trúc phân tầng ổn định**: tài liệu ngân sách dài, kỹ thuật, khó đọc; bài phát biểu ngắn hơn, dễ hiểu, nhấn vào tăng trưởng và công bằng; thông cáo ngắn nhất nhưng không dễ đọc hơn. Điểm đáng chú ý nhất là **thiên lệch lạc quan có hệ thống**: chi tiêu được nói nhiều hơn thu ngân sách, **tăng chi áp đảo cắt chi**, và giọng điệu về nợ công **tích cực ngay cả khi nợ đang tăng**, nhất là trong bài phát biểu. Các đặc điểm này **gần như không đổi suốt hai thập kỷ**.

> **Lưu ý:** bản PDF bắt đầu từ trang 5, thiếu trang bìa, tóm tắt và trang tác giả. Số hiệu lấy từ trang bìa sau. Tiêu đề Hình 2, 3 và 6 ghi "2020-23" nhưng đồ thị phủ 2000–2024. Phần bài phát biểu của Hình 7 trùng khớp từng con số với biểu đồ của riêng Canada ở Hình A7, nên có thể bài đã đặt nhầm hình. Các số lấy từ hình là giá trị ước đọc.

## Sơ đồ

### Vì sao truyền thông tài khoá là vấn đề

```text
       ┌──────────────────────────┐      ┌──────────────────────────┐
       │ NGÂN HÀNG TRUNG ƯƠNG     │      │ BỘ TÀI CHÍNH             │
       │ "NÓI"                    │      │ "LÀM"                    │
       │ một mục tiêu duy nhất    │      │ nhiều mục tiêu, không có │
       │ (lạm phát)               │      │ điểm neo chung           │
       │ độc lập với chính trị    │      │ nằm giữa đấu trường chính│
       │ hướng dẫn tương lai, họp │      │ trị, liên minh, bầu cử   │
       │ báo, báo cáo lạm phát    │      │ văn bản pháp lý, phát    │
       │ → truyền thông là CÔNG CỤ│      │ biểu theo chu kỳ ngân    │
       │   CHÍNH SÁCH             │      │ sách                     │
       └──────────────────────────┘      └──────────────────────────┘
       ═══════════════════════════════════════════════════════════
       ⚠ BẤT CÂN XỨNG NÀY KHÔNG CÒN ỔN
       khủng hoảng 2008 · nợ công châu Âu · COVID-19 · lạm phát
       2021–23 → tài khoá quay lại TRUNG TÂM ổn định vĩ mô
       ví dụ thất bại: ngân sách mini của Anh 2022 (không nói rõ
         cắt thuế được tài trợ ra sao → thị trường phản ứng dữ dội);
         bế tắc trần nợ ở Mỹ; Ý 2018 với quy tắc tài khoá EU
       ═══════════════════════════════════════════════════════════
       BA LỚP LÝ THUYẾT
       ① TÍN HIỆU · thông báo tài khoá báo hiệu ý định, sức mạnh thể
         chế và mức đáng tin
       ② RÀNG BUỘC TRUYỀN THÔNG · cân giữa minh bạch và mơ hồ có chủ
         đích: thắt lưng buộc bụng thành "tái cân bằng", tăng thuế
         thành "bịt kẽ hở", cắt chi thành "tăng hiệu quả"
       ③ TỰ SỰ (Shiller) · cùng một khoản tăng thuế, gọi là "công
         bằng giữa các thế hệ" khác với gọi là "thắt lưng buộc bụng"
```

### Dữ liệu và phương pháp

```text
       G7 · 2000–2024 · hơn 500 văn bản · vài triệu từ
       ┌──────────────────┬─────────────────────┬──────────────────┐
       │ KÊNH             │ ĐỐI TƯỢNG           │ VAI TRÒ          │
       ├──────────────────┼─────────────────────┼──────────────────┤
       │ tài liệu ngân    │ nghị sĩ, kinh tế    │ bản thiết kế kỹ  │
       │ sách (dự thảo    │ gia, tổ chức xếp    │ thuật: số liệu,  │
       │ ban đầu)         │ hạng, IMF, WB       │ giả định         │
       │ bài phát biểu    │ công chúng, chính   │ cầu nối sang tự  │
       │ bộ trưởng        │ giới                │ sự, thuyết phục  │
       │ thông cáo báo chí│ nhà báo, mạng xã hội│ "cổng" định hình │
       │                  │                     │ ấn tượng đầu tiên│
       └──────────────────┴─────────────────────┴──────────────────┘
       ĐIỀU CHỈNH THEO NƯỚC
       Nhật · dùng Public Finance Factsheet thay tài liệu ngân sách,
         Highlights of the Budget thay thông cáo; nhập tay nhiều
       Đức · dùng kế hoạch ngân sách trung hạn (luật ngân sách năm
         dài hơn 3.000 trang)
       Mỹ · factsheet thay thông cáo, phát biểu của Tổng thống (hoặc
         giám đốc OMB) thay phát biểu bộ trưởng
       ⚠ Pháp, Đức, Ý thiếu thông cáo có hệ thống; Pháp, Đức, Ý dịch
         sang tiếng Anh bằng GPT-4o-mini
       ═══════════════════════════════════════════════════════════
       CÔNG CỤ
       độ dễ đọc ········· chỉ số Flesch–Kincaid (số năm đi học cần có)
       văn phong ········· tỷ lệ từ khác nhau trên tổng số từ; tỷ lệ
                           câu ẩn dụ (theo quy trình của kho VU
                           Amsterdam)
       chủ đề ············ GPT-4o-mini xếp từng câu vào 8 nhóm
       tăng/giảm chi, thu · hơn 190.000 câu, có quy tắc chặt để LLM
                           không hiểu nhầm con số
       sắc thái về nợ ···· tích cực · tiêu cực · trung lập
       ★ tiếp cận kiểu HỌC KHÔNG GIÁM SÁT: mô tả, KHÔNG nhân quả,
         KHÔNG đo tác động lên lợi suất hay kỳ vọng
```

### Hình thức: độ dài, độ dễ đọc, văn phong

```text
       ★★ BA KÊNH, BA "CHẤT GIỌNG"
       ┌───────────────────┬──────────┬──────────┬──────────────┐
       │                   │ NGÂN SÁCH│ PHÁT BIỂU│ THÔNG CÁO    │
       ├───────────────────┼──────────┼──────────┼──────────────┤
       │ số từ bình quân   │ 60–80    │ 3–5      │ 0,5–1,5      │
       │                   │ nghìn    │ nghìn    │ nghìn        │
       │ từ mỗi câu        │ ~25–30   │ ~20      │ ⚠ cũng dài   │
       │ Flesch–Kincaid    │ 13–15    │ ★ 10–12  │ 13–15        │
       │ tỷ lệ từ khác nhau│ ~0,1–0,15│ ~0,35–0,4│ ★ ~0,5–0,6   │
       │ câu ẩn dụ (%)     │ ~0–3     │ ★ ~5–23  │ ~0–17        │
       └───────────────────┴──────────┴──────────┴──────────────┘
       ★ SO SÁNH: tuyên bố chính sách tiền tệ ở nước phát triển cần
         ~16 năm đi học; phát biểu của lãnh đạo ECB ~14,5
         → phát biểu ngân sách DỄ HIỂU HƠN hẳn
       ═══════════════════════════════════════════════════════════
       ★★ PHÁT HIỆN VỀ THỜI GIAN
       độ dễ đọc của ngân sách và thông cáo GẦN NHƯ KHÔNG ĐỔI 20 năm
         → "văn phong nhà" của bộ máy hành chính, bất chấp khủng
           hoảng, đổi chính phủ hay cải cách minh bạch
       CHỈ bài phát biểu đi theo xu hướng ngôn ngữ giản dị
       sau 2009: câu trong ngân sách DÀI ra, câu trong phát biểu NGẮN
         đi → hai kênh bù trừ nhau
       từ khoảng 2016: phương sai độ dài TĂNG vọt (không trùng khủng
         hoảng 2008) → chính phủ ngày càng khác nhau
       ngân sách DÀI ra trong COVID; Anh, Mỹ rút gọn từ đầu thập niên
         2010; Pháp mở rộng phụ lục
       ═══════════════════════════════════════════════════════════
       ⚠ "KHOẢNG CÁCH RÕ RÀNG": ai chỉ nghe phát biểu bỏ lỡ ràng
         buộc; ai chỉ đọc ngân sách bỏ lỡ cách đóng khung
       ★ thông cáo gần đây ở Anh, Canada TIẾT CHẾ hơn, bớt khẩu hiệu
       ★ nước thông luật (Canada, Anh, Mỹ) dùng nhiều tự sự và ẩn dụ;
         nước dân luật (Pháp, Ý) thiên về trình bày có cấu trúc; Nhật
         ngắn gọn, định dạng chặt
```

### Nội dung: chủ đề và mục tiêu

```text
       ❶ CHỦ ĐỀ THEO KÊNH
       ngân sách ··· thuế và cơ chế chi tiêu
       phát biểu ··· tăng trưởng, việc làm, chi xã hội
       thông cáo ··· sáng kiến MỚI (tăng chi, giảm thuế, dự án chủ
                     lực), BỎ QUA đánh đổi
       khủng hoảng 2009, 2020 · mọi kênh chuyển sang ổn định vĩ mô
       khí hậu ··· rải rác trước 2015, nổi hơn sau Hiệp định Paris;
                   Anh chú ý bền bỉ nhất
       Mỹ, Anh nhấn giảm thuế; Pháp, Đức nhấn quy tắc (phanh nợ,
         Maastricht); Nhật nhấn dân số già và củng cố nợ
       10–20% nội dung là "khác": thủ tục, dẫn chiếu luật, lời đệm
       ═══════════════════════════════════════════════════════════
       ❷ MỤC TIÊU (Hình 7, ước đọc)
       ┌──────────────────────┬────────────┬────────────┐
       │ mục tiêu             │ NGÂN SÁCH  │ PHÁT BIỂU* │
       ├──────────────────────┼────────────┼────────────┤
       │ phúc lợi xã hội      │ ~24%       │ ★ ~33%     │
       │ trách nhiệm tài khoá │ ★ ~19%     │ ~15%       │
       │ bền vững môi trường  │ ★ ~13%     │ —          │
       │ tạo việc làm         │ ~12%       │ ~19%       │
       │ năng lực cạnh tranh  │ ~7%        │ ~19%       │
       └──────────────────────┴────────────┴────────────┘
       (* trùng số liệu Canada ở Hình A7)
       ★ phát biểu: "xây nền kinh tế cho mọi người", "củng cố tầng
         lớp trung lưu"
       ★ ngân sách: "đưa nợ/GDP về 50% vào 2030", "đạt mục tiêu cân
         bằng trung hạn"
       khí hậu nằm chủ yếu trong NGÂN SÁCH; phát biểu nhắc thưa hoặc
         theo lối đạo đức
       ★ trách nhiệm tài khoá nổi bật: ngân sách Nhật ~65%, phát biểu
         Mỹ ~58%, phát biểu Nhật ~47%, phát biểu Đức ~36%
```

### Thiên lệch lạc quan

```text
       ★★ CHI TIÊU VÀ THU NGÂN SÁCH (Hình 9, ước đọc)
       ┌──────────────┬───────────────────┬───────────────────┐
       │              │ CHI: tăng · giảm  │ THU: tăng · giảm  │
       ├──────────────┼───────────────────┼───────────────────┤
       │ ngân sách    │ ~28% · ~4%        │ ~19% · ~14%       │
       │ phát biểu    │ ~31% · ~3%        │ ~17% · ★ ~22%     │
       │ thông cáo    │ ★ ~52% · ~4%      │ ~32% · ~28%       │
       └──────────────┴───────────────────┴───────────────────┘
       (phần còn lại là câu trung lập)
       ★ cắt chi hiếm khi được nói thẳng: "tinh gọn", "tìm dư địa
         hiệu quả", "làm chậm tốc độ tăng chi"; nếu có thì dùng THÌ
         QUÁ KHỨ ("năm ngoái chúng tôi đã có quyết định khó khăn")
       ★ tăng thu được gắn với "thu thuế tốt hơn", "bịt kẽ hở"; gần
         như không bao giờ nói thẳng tăng thuế diện rộng
       ★ GHÉP ĐÔI: tăng thuế đi kèm ngay một khoản chi được lòng dân
         (Nhật tăng VAT 2014, 2019 để "đảm bảo an sinh")
       ★ "không tăng thuế" cũng được kể như một thành tích
       Canada sau 2015: 60–70% câu về thu trong phát biểu là về giảm
         thuế; lo ngại thâm hụt gần như biến mất
       Anh 2010–11: "trách nhiệm", "tiết kiệm nhờ hiệu quả", "kiềm
         chế lương khu vực công" thay cho chữ "cắt"
       ═══════════════════════════════════════════════════════════
       ★★ SẮC THÁI VỀ NỢ CÔNG (Hình 10, tỷ lệ câu tích cực, ước đọc)
       phát biểu · Canada ~72% · Anh ~65% · Pháp ~57% · Mỹ ~56% ·
                   Đức ~46% · Nhật ~41%
       ngân sách · Mỹ ~51% · Canada ~45% · còn lại ~25–35%;
                   ⚠ Nhật có ~55% câu TIÊU CỰC
       ★ công thức quen: nợ "sắp ổn định", "trong tầm kiểm soát",
         "đạt đỉnh năm sau rồi giảm" (Anh lặp nhiều chu kỳ); Canada
         "nợ thấp nhất G7"
       giọng u ám chỉ xuất hiện lúc cấp tính (2009, 2020–21), và ngay
         lập tức ghép với lạc quan về phục hồi
       → "tính THUẬN chu kỳ nhẹ": lời nói luôn mạnh hơn nền tảng
```

### Kiểm định thống kê

```text
       ★ BẢNG 1 — KIỂM ĐỊNH t CẶP, KHÁC BIỆT HÌNH THỨC
       ┌──────────────────┬───────────┬───────────┬───────────┐
       │                  │ NS–TC     │ NS–PB     │ PB–TC     │
       ├──────────────────┼───────────┼───────────┼───────────┤
       │ độ dễ đọc        │ 4,7***    │ 16,4***   │ 13,9***   │
       │ độ dài câu       │ 2,2*      │ 12,3***   │ 6,3***    │
       │ độ phong phú     │ 20,2***   │ 29,4***   │ 6,2***    │
       │ độ dài văn bản   │ 18,5***   │ 17,8***   │ 10,2***   │
       └──────────────────┴───────────┴───────────┴───────────┘
       ★★ BẢNG 2 — KIỂM ĐỊNH t MỘT PHÍA, NỘI DUNG
       ┌──────────────────────┬──────────┬──────────┬──────────┐
       │                      │ NGÂN SÁCH│ THÔNG CÁO│ PHÁT BIỂU│
       ├──────────────────────┼──────────┼──────────┼──────────┤
       │ chi > thu            │ 12,9***  │ 22,2***  │ 10,8***  │
       │ tăng chi > giảm chi  │ 24,6***  │ 43,6***  │ 27,4***  │
       │ giảm thu > tăng thu  │ −3,1     │ −11,3    │ ★ 6,9**  │
       │ nợ tích cực > tiêu   │ 9,5***   │ 44,8***  │ 30***    │
       │ cực                  │          │          │          │
       └──────────────────────┴──────────┴──────────┴──────────┘
       → giả thuyết lạc quan đúng ở hầu hết các ô; RIÊNG giảm thuế
         chỉ được nhấn mạnh trong PHÁT BIỂU
```

### Bài học cho người truyền thông tài khoá

```text
       HỘP 1 — HỌC TỪ Y TẾ, KHÍ HẬU, QUẢN LÝ KHỦNG HOẢNG
       bắt đầu từ niềm tin, không phải kỹ thuật · kể bằng câu chuyện
       · khán giả khác nhau cần thông điệp khác nhau · nhất quán
       quan trọng ngang nội dung · cho thấy giá trị sau con số ·
       đối thoại chứ không độc thoại
       ═══════════════════════════════════════════════════════════
       HỘP 2 — MƯỜI NGUYÊN TẮC
       ① rõ ràng về thông điệp và kênh (nhiều tầng)
       ② nhất quán nội bộ và giữa các cơ quan
       ③ minh bạch về bất định: khoảng, giả định, kịch bản
       ④ giải thích đánh đổi và ai được, ai mất
       ⑤ truyền thông là quá trình, không phải một khoảnh khắc
       ⑥ tự sự là chiến lược
       ⑦ nhạy cảm văn hoá và ngôn ngữ
       ⑧ thừa nhận ràng buộc kinh tế chính trị
       ⑨ ký ức thể chế và tính liên tục qua các nhiệm kỳ
       ⑩ tương tác chứ không chỉ phát đi
       ═══════════════════════════════════════════════════════════
       ★ ĐỀ XUẤT THỂ CHẾ: chế độ truyền thông tài khoá có cấu trúc,
         giống khung lạm phát mục tiêu: điểm neo tự sự, bản tóm tắt
         ngôn ngữ giản dị, KIỂM TOÁN TỰ SỰ bởi bên thứ ba; hội đồng
         tài khoá độc lập (như OBR của Anh) có thể đánh giá cả mức
         mạch lạc của thông điệp
       ★ ví dụ: Pháp 3/2025 cam kết thêm mục bất định và rủi ro vào
         ngân sách, lần đầu áp dụng cho dự thảo 2026
```

## Ba câu hỏi bài viết trả lời

1. Bộ tài chính các nước G7 nói về chính sách tài khoá qua những kênh nào, và các kênh đó khác nhau thế nào về độ dài, độ dễ đọc và văn phong?
2. Chủ đề, mục tiêu và cách đóng khung chi tiêu, thu ngân sách, nợ công thay đổi ra sao giữa các kênh, các nước và theo thời gian?
3. Truyền thông tài khoá có thiên lệch về phía tin tốt không, và nên thiết kế thể chế thế nào để lời nói khớp với con số?

## Dàn ý chi tiết

### 1. Bối cảnh

- Sau Thế chiến thứ hai, ngân sách là công cụ ổn định chủ động. Từ thập niên 1980 và 1990, chủ nghĩa tiền tệ, độc lập ngân hàng trung ương và lạm phát mục tiêu chuyển trách nhiệm ổn định ngắn hạn sang ngân hàng trung ương; tài khoá gắn với củng cố, quy tắc và kiểm soát nợ.
- Ngân hàng trung ương xây dựng chiến lược quản lý kỳ vọng tinh vi. Bộ tài chính giữ mô hình truyền thông dựa trên hình thức pháp lý, thương lượng chính trị và phản ứng theo chu kỳ ngân sách.
- Mười lăm năm qua, tài khoá quay lại trung tâm, nhưng thể chế truyền thông tụt lại. Tài khoá tác động không chỉ qua thuế, chi và vay nợ mà qua kỳ vọng hộ gia đình, doanh nghiệp và thị trường về ý định của chính phủ.
- Nghiên cứu về minh bạch tài khoá tập trung vào chuẩn công bố và quy tắc; nghiên cứu về truyền thông tập trung vào ngân hàng trung ương. Chưa có khung thực nghiệm để phân tích cách bộ tài chính nói.

### 2. Khung khái niệm

- Truyền thông tài khoá là cơ chế tín hiệu: trong điều kiện thông tin không đầy đủ, thông báo báo hiệu ý định tương lai, sức mạnh thể chế và độ tin cậy. Khi nợ tăng hoặc liên minh chính trị lung lay, thông điệp rõ ràng và nhất quán giúp neo kỳ vọng.
- Bộ tài chính nói trong môi trường phân mảnh và chính trị hoá, chịu chu kỳ bầu cử, liên minh, thay đổi nhân sự và quy tắc tài khoá. Sự mơ hồ có thể là tài sản chiến lược để che các đánh đổi không được lòng dân.
- Không có điểm neo vận hành duy nhất như mục tiêu lạm phát, nên truyền thông tài khoá thiếu tiêu điểm và thường rơi vào các tự sự phân tán hoặc cạnh tranh.
- Phải nói với nhiều khán giả cùng lúc, nên hình thành kiến trúc nhiều tầng. Trong môi trường truyền thông trực tiếp và mạng xã hội, một câu lỡ lời có thể lan ra thị trường trái phiếu. Một tự sự tài khoá mạch lạc trở thành một dạng vốn vĩ mô.

### 3. Dữ liệu và phương pháp

- Ba kênh được chọn vì là phần nhất quán và so sánh được nhất của lịch ngân sách ở các nền kinh tế phát triển. Các kênh khác như cập nhật giữa năm, kế hoạch dài hạn hay tranh luận quốc hội khác nhau nhiều giữa các nước.
- Bài chỉ dùng dự thảo ngân sách ban đầu, không dùng các bản sửa trong năm.
- Văn bản không có tiếng Anh được dịch bằng GPT-4o-mini, kiểm tra bằng văn bản song song; mọi chỉ số tính sau khi dịch. Bài thừa nhận khác biệt giữa văn bản gốc tiếng Anh và bản dịch máy vẫn có thể tồn tại.
- Bài so sánh giữa các kênh trong cùng một nước và cùng một năm, vì cả ba kênh nói về cùng một quyết định chính sách. Cách này giúp tách lựa chọn truyền thông khỏi thực trạng tài khoá, dù không xử lý trực tiếp tính nội sinh.
- Bài lưu ý khác biệt thể chế: nước liên bang như Mỹ, Canada, Đức có quy trình ngân sách phức tạp hơn; Mỹ không có chu kỳ ngân sách thống nhất nên bộ ba văn bản kém ý nghĩa hơn; Anh có Văn phòng Trách nhiệm Ngân sách đảm nhận một phần nội dung phân tích.

### 4. Hình thức truyền thông

- Thứ bậc độ dài ổn định: ngân sách dài nhất, phát biểu ở giữa, thông cáo ngắn nhất. Ngân sách dài ra trong COVID để minh bạch và biện minh cho các biện pháp khẩn cấp; thông cáo dài ra trong khủng hoảng 2008.
- Canada giai đoạn 2016–2018 và từ 2022 bỏ các phụ lục thuế đồ sộ để chuyển sang trình bày theo tự sự, xoay quanh "tầng lớp trung lưu".
- Phát biểu dễ đọc nhất, quanh mức mười tới mười hai năm đi học, và sự hội tụ này giống nhau ở mọi nước. Ngân sách và thông cáo cần trình độ đại học. Thông cáo ngắn nhưng không đơn giản, thực chất là gói thông tin nén cho nhà báo và nhà phân tích.
- Độ dễ đọc của ngân sách và thông cáo gần như không đổi hai thập kỷ, phản ánh "văn phong nhà" của bộ máy hành chính. Chỉ bài phát biểu theo xu hướng ngôn ngữ giản dị.
- Về văn phong, ngân sách ít màu sắc nhất vì phải lặp các thuật ngữ như thâm hụt, thuế, chương trình. Thông cáo có độ phong phú từ vựng cao nhất, nhất là đầu thập niên 2000 với các khẩu hiệu như "hỗ trợ gia đình lao động", "sống trong khả năng của mình". Ẩn dụ tăng trong giai đoạn căng thẳng kinh tế, nhưng bài lưu ý định nghĩa ẩn dụ có thể trôi theo thời gian.

### 5. Chủ đề và mục tiêu

- Chủ đề khác nhau theo kênh, điều chứng tỏ bộ tài chính chủ động nhắm khán giả. Muốn thấy toàn bộ ưu tiên tài khoá phải đọc cả ba kênh.
- Phân đoạn này có thể tăng ủng hộ chính trị ngắn hạn nhưng làm yếu trách nhiệm giải trình: công dân có thể ủng hộ chương trình đầu tư "lịch sử" mà không hiểu hệ quả tài khoá, thị trường có thể định giá sai rủi ro nếu giả định tăng trưởng được nhấn còn dự báo nợ bị che.
- Mục tiêu trong phát biểu thiên về phúc lợi, việc làm, năng suất; mục tiêu trong ngân sách thiên về bền vững tài khoá, quản lý nợ, tuân thủ quy tắc. Đức gắn mục tiêu chặt với phanh nợ và nhấn tuân thủ hơn tầm nhìn.
- Bài chưa phân tích chính thức vai trò của quy tắc tài khoá và hội đồng tài khoá, nhưng gợi ý chúng có thể thu hẹp dư địa tu từ và làm nổi các tự sự dựa trên độ tin cậy.

### 6. Chi tiêu, thu và nợ công

- Chính phủ có động cơ "nhận công": nhấn các chính sách có lợi, giảm nhẹ chi phí. Bằng chứng G7 xác nhận chi tiêu được nói nhiều hơn thu ở mọi kênh, và tăng chi áp đảo cắt chi.
- Cắt chi được diễn đạt mơ hồ hoặc ở thì quá khứ. Tăng thu được gán cho thu thuế tốt hơn hoặc bịt kẽ hở. Cải cách trung tính về thu được kể như thắng lợi. Tăng thuế bắt buộc thì ghép với một khoản chi được lòng dân.
- Hệ quả là bất cân xứng giữa thực tế và tự sự tài khoá; gánh nặng tìm ra mặt kém thuận lợi dồn lên nhà phân tích và nhà báo. Nhật minh hoạ điều này: ràng buộc dài hạn rất lớn nhưng truyền thông công chúng vẫn chủ yếu là cam kết chi.
- Về nợ, giọng lạc quan chiếm ưu thế kể cả khi nợ tăng. Bài nói rõ lạc quan không nhất thiết là trình bày sai, nhưng lạc quan lặp lại mà kết quả không khớp có thể dần làm mòn độ tin cậy. Phát biểu lạc quan hơn tài liệu viết.

### 7. Thảo luận và hàm ý

- Nhấn lợi ích và giảm chi phí phản ánh ngại mất mát, hiệu ứng nổi bật và động cơ nhận công, nhưng có thể gây ảo giác tài khoá, làm sai lệch hiểu biết về đánh đổi.
- Truyền thông chiến lược chỉ ổn định kỳ vọng tạm thời, không bù được rủi ro nền tảng khi quỹ đạo nợ xấu đi. Nó cũng phụ thuộc vào dữ liệu tài khoá kịp thời và đáng tin.
- Bộ tài chính nên truyền thông có điều kiện, theo giai đoạn: thừa nhận xấu đi ngắn hạn nhưng nêu rõ lộ trình củng cố trung hạn.
- Khi truyền thông nhấn lợi ích và giảm nhẹ chi phí trễ, hộ thu nhập thấp có thể chịu gánh nặng không tương xứng, làm xói mòn niềm tin.
- Các nước mới nổi đang cải cách khung minh bạch có cơ hội áp dụng cách truyền thông tích hợp và cân đối ngay từ đầu. IMF và OECD có thể xây dựng hướng dẫn không chỉ về quy tắc tài khoá mà về thực hành tự sự.
- Trong khủng hoảng, chính phủ thường vội chuyển sang trấn an; cách tốt hơn là lập kịch bản, công bố rủi ro dự phòng và nói thẳng về rủi ro mà không gây hoảng loạn.

### 8. Kết luận

- Truyền thông tài khoá có kiến trúc nhất quán: ngân sách nhấn quy tắc và kiềm chế, phát biểu nhấn công bằng và tiến bộ, thông cáo chưng cất thông điệp lạc quan.
- Thiên lệch lạc quan kéo dài có thể ảnh hưởng độ tin cậy khi kỳ vọng không thành hiện thực. Sự khác biệt giữa các kênh có thể làm hiểu biết của công chúng và thị trường phân mảnh.
- Thiết kế thể chế, như hội đồng tài khoá độc lập, có thể giúp tự sự và số học khớp nhau.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Fiscal communication | Truyền thông tài khoá |
| Budget document | Tài liệu ngân sách, bản kỹ thuật dài |
| Budget speech | Bài phát biểu ngân sách của bộ trưởng |
| Press communiqué | Thông cáo báo chí |
| Layered architecture | Kiến trúc nhiều tầng theo khán giả |
| Signaling | Tín hiệu về ý định và độ tin cậy |
| Strategic ambiguity | Mơ hồ có chủ đích |
| Narrative economics | Kinh tế học tự sự của Shiller |
| Framing | Đóng khung vấn đề |
| Credit claiming | Nhận công cho chính sách có lợi |
| Blame avoidance | Né trách nhiệm cho chính sách gây thiệt |
| Fiscal illusion | Ảo giác tài khoá, hiểu sai đánh đổi |
| Flesch-Kincaid index | Chỉ số độ dễ đọc, tính bằng số năm đi học |
| Eloquence ratio | Tỷ lệ từ khác nhau trên tổng số từ |
| Metaphor identification procedure | Quy trình nhận diện ẩn dụ |
| Clarity gap | Khoảng cách rõ ràng giữa phát biểu và tài liệu |
| House style | Văn phong nhà của bộ máy hành chính |
| Optimism bias | Thiên lệch lạc quan |
| Narrative anchor | Điểm neo tự sự, như "nợ đạt đỉnh năm sau" |
| Debt brake (Schuldenbremse) | Phanh nợ của Đức |
| Independent fiscal council | Hội đồng tài khoá độc lập |
| Office for Budget Responsibility (OBR) | Văn phòng Trách nhiệm Ngân sách của Anh |
| Narrative audit | Kiểm toán tự sự bởi bên thứ ba |

## Câu nói đáng nhớ

> "In essence, monetary policy 'talked,' while fiscal policy largely 'acted,' relying on implementation rather than explanation to convey intent."

> "Fiscal communication remains marked by dualism; simple when spoken, complex when written."

> "Across channels and cycles, across speeches and spreadsheets, coherence is not a luxury, it is the precondition of fiscal trust."
