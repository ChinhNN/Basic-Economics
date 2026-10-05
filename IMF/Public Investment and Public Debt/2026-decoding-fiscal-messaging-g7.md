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

## Khái niệm cần biết

**Truyền thông tài khoá (fiscal communication).** Mọi cách bộ tài chính nói với bên ngoài về thuế, chi tiêu và nợ công: tài liệu ngân sách, bài phát biểu, thông cáo báo chí, họp báo. Khác với chính sách tài khoá (quyết định thu bao nhiêu, chi bao nhiêu), truyền thông tài khoá là cách giải thích các quyết định đó. Ví dụ trong bài: năm 2022, Anh công bố một gói cắt thuế lớn mà không nói rõ lấy tiền ở đâu bù vào, và thị trường trái phiếu phản ứng dữ dội. Bài này là nỗ lực đầu tiên đo một cách hệ thống xem bộ tài chính G7 nói những gì và nói thế nào.

**Kiến trúc nhiều tầng (layered architecture).** Bộ tài chính phải nói với nhiều nhóm người nghe cùng lúc, nên dùng mỗi kênh cho một nhóm: tài liệu ngân sách cho chuyên gia và thị trường, bài phát biểu cho công chúng, thông cáo cho nhà báo. Ví dụ trong bài: tài liệu ngân sách dài 60–80 nghìn từ, bài phát biểu 3–5 nghìn từ, thông cáo chỉ 0,5–1,5 nghìn từ. Hệ quả là ai chỉ đọc một kênh sẽ thấy một bức tranh khác với người đọc kênh khác; bài gọi đây là "khoảng cách rõ ràng".

**Tín hiệu (signaling).** Khi người ngoài không biết hết thông tin bên trong chính phủ, lời nói và hành động của chính phủ được dùng làm dấu hiệu để đoán ý định. Ví dụ minh hoạ: một chính phủ công bố trước lộ trình giảm thâm hụt 0,5% GDP mỗi năm và làm đúng hai năm liền; thị trường bắt đầu tin vào các lời hứa sau và đòi lãi suất thấp hơn. Đây là lớp lý thuyết đầu tiên mà bài dùng để giải thích vì sao truyền thông tài khoá quan trọng.

**Mơ hồ có chủ đích và đóng khung (strategic ambiguity, framing).** Đóng khung là chọn từ ngữ để cùng một sự việc gây ấn tượng khác nhau. Mơ hồ có chủ đích là cố ý nói không rõ để tránh phản ứng. Ví dụ trong bài: cắt chi được gọi là "tăng hiệu quả" hay "tinh gọn", tăng thuế được gọi là "bịt kẽ hở", thắt lưng buộc bụng được gọi là "tái cân bằng". Khái niệm này giải thích vì sao các câu nói thẳng về cắt chi hiếm tới vậy trong dữ liệu.

**Kinh tế học tự sự (narrative economics).** Ý tưởng của Robert Shiller rằng những câu chuyện lan truyền trong xã hội ảnh hưởng tới hành vi kinh tế, không kém gì con số. Ví dụ trong bài: cùng một khoản tăng thuế, nếu kể như "công bằng giữa các thế hệ" thì được đón nhận khác với khi kể như "thắt lưng buộc bụng". Bài coi một tự sự tài khoá mạch lạc là một dạng "vốn vĩ mô" giúp neo kỳ vọng.

**Chỉ số Flesch–Kincaid.** Một công thức đo độ khó đọc của văn bản dựa trên độ dài câu và số âm tiết mỗi từ, cho ra kết quả là số năm đi học cần có để hiểu. Ví dụ: điểm 10–12 nghĩa là học sinh cuối cấp ba đọc được; điểm 13–15 nghĩa là cần trình độ đại học. Trong bài, bài phát biểu ngân sách ở mức 10–12, dễ hơn hẳn tài liệu ngân sách (13–15) và tuyên bố chính sách tiền tệ (khoảng 16).

**Thiên lệch lạc quan (optimism bias).** Xu hướng có hệ thống nói nhiều về tin tốt và ít về tin xấu. Ví dụ trong bài: trong thông cáo báo chí, khoảng 52% số câu nói về tăng chi, chỉ khoảng 4% nói về giảm chi, tức tỷ lệ khoảng 13:1. Đây là phát hiện quan trọng nhất của bài, vì nó cho thấy công chúng nhận được một bức tranh tài khoá dễ chịu hơn thực tế.

**Kiểm định t và dấu sao.** Kiểm định t xem một chênh lệch quan sát được (ví dụ giữa hai kênh) có đủ lớn để không phải do ngẫu nhiên hay không. Giá trị t càng lớn thì bằng chứng càng mạnh; thường t trên khoảng 2 đã được coi là có ý nghĩa. Ký hiệu \*\*\* (p < 0,01) nghĩa là xác suất thấy chênh lệch như vậy khi thật ra không có khác biệt là dưới 1%; \*\* là dưới 5%; \* là dưới 10%. Ví dụ trong bài: giá trị t 43,6 cho giả thuyết "thông cáo nói về tăng chi nhiều hơn giảm chi" là bằng chứng cực kỳ mạnh.

**Hội đồng tài khoá độc lập (independent fiscal council).** Một cơ quan công không thuộc chính phủ đương nhiệm, có nhiệm vụ kiểm tra dự báo và kế hoạch ngân sách, và công bố đánh giá. Ví dụ trong bài: Văn phòng Trách nhiệm Ngân sách (OBR) của Anh. Bài đề xuất các hội đồng này đánh giá thêm cả việc lời kể của chính phủ có khớp với con số hay không.

## Nội dung chi tiết

### 1. Bối cảnh

**Hai cơ quan, hai cách nói.** Sau Thế chiến thứ hai, ngân sách nhà nước là công cụ chính để ổn định nền kinh tế một cách chủ động: suy thoái thì chi thêm, quá nóng thì thu bớt. Từ thập niên 1980 và 1990, ba trào lưu là chủ nghĩa tiền tệ, độc lập ngân hàng trung ương và lạm phát mục tiêu đã chuyển trách nhiệm ổn định ngắn hạn sang ngân hàng trung ương. Tài khoá từ đó gắn với củng cố ngân sách, quy tắc và kiểm soát nợ.

Hai loại cơ quan phát triển hai cách truyền thông rất khác nhau:

| | Ngân hàng trung ương ("nói") | Bộ tài chính ("làm") |
|---|---|---|
| Mục tiêu | một mục tiêu duy nhất là lạm phát | nhiều mục tiêu, không có điểm neo chung |
| Vị trí chính trị | độc lập với chính trị | nằm giữa đấu trường chính trị, liên minh, bầu cử |
| Công cụ truyền thông | hướng dẫn tương lai, họp báo, báo cáo lạm phát | văn bản pháp lý, phát biểu theo chu kỳ ngân sách |
| Vai trò của truyền thông | là một công cụ chính sách | chủ yếu để công bố quyết định |

Ngân hàng trung ương xây dựng các chiến lược quản lý kỳ vọng tinh vi. Bộ tài chính thì giữ mô hình truyền thông dựa trên hình thức pháp lý, thương lượng chính trị và phản ứng theo chu kỳ ngân sách. Nói gọn, chính sách tiền tệ thì "nói", còn chính sách tài khoá chủ yếu "làm", dựa vào việc thực hiện hơn là giải thích để truyền đạt ý định.

**Vì sao bất cân xứng này không còn ổn.** Mười lăm năm qua, qua khủng hoảng tài chính 2008, khủng hoảng nợ công châu Âu, COVID-19 và đợt lạm phát 2021–23, tài khoá đã quay lại trung tâm của ổn định vĩ mô. Nhưng thể chế truyền thông tài khoá thì tụt lại phía sau. Tài khoá tác động tới nền kinh tế không chỉ qua thuế, chi và vay nợ, mà còn qua kỳ vọng của hộ gia đình, doanh nghiệp và thị trường về ý định của chính phủ. Bài nêu ba ví dụ khi truyền thông thất bại:

- Ngân sách mini của Anh năm 2022: chính phủ không nói rõ các khoản cắt thuế được tài trợ ra sao, và thị trường phản ứng dữ dội.
- Các đợt bế tắc trần nợ ở Mỹ.
- Ý năm 2018, trong căng thẳng với quy tắc tài khoá của EU.

**Khoảng trống nghiên cứu.** Các nghiên cứu về minh bạch tài khoá tập trung vào chuẩn công bố số liệu và quy tắc tài khoá. Các nghiên cứu về truyền thông lại tập trung vào ngân hàng trung ương. Chưa có một khung thực nghiệm nào để phân tích cách bộ tài chính nói. Bài này lấp khoảng trống đó.

### 2. Khung khái niệm

Bài dựa trên ba lớp lý thuyết.

**Lớp thứ nhất: tín hiệu.** Trong điều kiện thông tin không đầy đủ, các thông báo tài khoá báo hiệu ý định tương lai, sức mạnh thể chế và mức đáng tin của chính phủ. Khi nợ tăng hoặc liên minh chính trị lung lay, một thông điệp rõ ràng và nhất quán giúp neo kỳ vọng.

**Lớp thứ hai: ràng buộc truyền thông.** Bộ tài chính nói trong một môi trường phân mảnh và chính trị hoá, chịu ảnh hưởng của chu kỳ bầu cử, liên minh cầm quyền, thay đổi nhân sự và quy tắc tài khoá. Vì vậy họ phải cân giữa minh bạch và mơ hồ có chủ đích. Sự mơ hồ có thể là một tài sản chiến lược để che các đánh đổi không được lòng dân. Ví dụ quen thuộc: thắt lưng buộc bụng được gọi là "tái cân bằng", tăng thuế được gọi là "bịt kẽ hở", cắt chi được gọi là "tăng hiệu quả".

**Lớp thứ ba: tự sự.** Theo kinh tế học tự sự của Shiller, cách kể quan trọng không kém nội dung. Cùng một khoản tăng thuế, nếu gọi là "công bằng giữa các thế hệ" thì tác động lên dư luận khác với khi gọi là "thắt lưng buộc bụng".

**Thiếu điểm neo.** Ngân hàng trung ương có mục tiêu lạm phát làm điểm neo vận hành duy nhất. Bộ tài chính không có điểm neo tương tự, nên truyền thông tài khoá thiếu tiêu điểm và thường rơi vào các tự sự phân tán hoặc cạnh tranh nhau.

**Nhiều khán giả, nhiều tầng.** Vì phải nói với nhiều nhóm người nghe cùng lúc, bộ tài chính hình thành một kiến trúc truyền thông nhiều tầng. Trong môi trường truyền thông trực tiếp và mạng xã hội, một câu lỡ lời có thể lan thẳng ra thị trường trái phiếu. Vì vậy một tự sự tài khoá mạch lạc trở thành một dạng vốn vĩ mô.

### 3. Dữ liệu và phương pháp

**Kho văn bản.** Bài xây dựng một kho hơn 500 văn bản tài khoá của bảy nước G7 trong giai đoạn 2000–2024, tổng cộng vài triệu từ, chia làm ba kênh:

| Kênh | Người đọc chính | Vai trò |
|---|---|---|
| Tài liệu ngân sách (chỉ dùng dự thảo ban đầu) | nghị sĩ, nhà kinh tế, tổ chức xếp hạng tín nhiệm, IMF, Ngân hàng Thế giới | bản thiết kế kỹ thuật: số liệu, giả định |
| Bài phát biểu của bộ trưởng | công chúng, giới chính trị | cầu nối sang tự sự, thuyết phục |
| Thông cáo báo chí | nhà báo, mạng xã hội | "cổng" định hình ấn tượng đầu tiên |

Ba kênh này được chọn vì đó là phần nhất quán và so sánh được nhất của lịch ngân sách ở các nền kinh tế phát triển. Các kênh khác như bản cập nhật giữa năm, kế hoạch dài hạn hay tranh luận ở quốc hội khác nhau quá nhiều giữa các nước. Bài chỉ dùng dự thảo ngân sách ban đầu, không dùng các bản sửa trong năm.

**Điều chỉnh theo từng nước.** Không phải nước nào cũng có đủ ba loại văn bản giống nhau:

- **Nhật Bản:** dùng Public Finance Factsheet thay cho tài liệu ngân sách, và Highlights of the Budget thay cho thông cáo; nhiều dữ liệu phải nhập tay.
- **Đức:** dùng kế hoạch ngân sách trung hạn, vì luật ngân sách hằng năm dài hơn 3.000 trang.
- **Mỹ:** dùng factsheet thay cho thông cáo, và phát biểu của Tổng thống (hoặc giám đốc Văn phòng Quản lý và Ngân sách, OMB) thay cho phát biểu của bộ trưởng.
- **Pháp, Đức, Ý:** thiếu thông cáo một cách có hệ thống, và văn bản của ba nước này được dịch sang tiếng Anh bằng GPT-4o-mini.

Bản dịch được kiểm tra bằng cách đối chiếu với văn bản song song, và mọi chỉ số được tính sau khi dịch. Bài thừa nhận khác biệt giữa văn bản gốc tiếng Anh và bản dịch máy vẫn có thể tồn tại.

**Công cụ đo:**

| Khía cạnh | Cách đo |
|---|---|
| Độ dễ đọc | chỉ số Flesch–Kincaid, tính bằng số năm đi học cần có |
| Văn phong | tỷ lệ số từ khác nhau trên tổng số từ (độ phong phú từ vựng); tỷ lệ câu ẩn dụ, theo quy trình nhận diện ẩn dụ của kho ngữ liệu VU Amsterdam |
| Chủ đề | GPT-4o-mini xếp từng câu vào 8 nhóm chủ đề |
| Tăng hay giảm chi, tăng hay giảm thu | phân loại hơn 190.000 câu, với các quy tắc chặt để mô hình ngôn ngữ không hiểu nhầm con số |
| Sắc thái về nợ công | mỗi câu được xếp là tích cực, tiêu cực hoặc trung lập |

**Thiết kế so sánh.** Bài so sánh giữa các kênh trong cùng một nước và cùng một năm, vì cả ba kênh nói về cùng một quyết định chính sách. Nhờ vậy, khác biệt giữa các kênh phản ánh lựa chọn truyền thông chứ không phải thực trạng tài khoá, dù cách này không xử lý trực tiếp vấn đề nội sinh. Cách tiếp cận là mô tả, tương tự học không giám sát: bài không tìm quan hệ nhân quả và không đo tác động của truyền thông lên lợi suất trái phiếu hay kỳ vọng.

**Khác biệt thể chế cần lưu ý.** Các nước liên bang như Mỹ, Canada, Đức có quy trình ngân sách phức tạp hơn. Mỹ không có một chu kỳ ngân sách thống nhất, nên bộ ba văn bản ở Mỹ kém ý nghĩa hơn. Ở Anh, Văn phòng Trách nhiệm Ngân sách (OBR) đảm nhận một phần nội dung phân tích, nên tài liệu ngân sách của Anh có thể ngắn hơn.

### 4. Hình thức truyền thông

**Ba kênh, ba "chất giọng".** Bảng sau tóm tắt khác biệt về hình thức (giá trị ước đọc từ biểu đồ):

| Chỉ tiêu | Tài liệu ngân sách | Bài phát biểu | Thông cáo |
|---|---|---|---|
| Số từ bình quân | 60–80 nghìn | 3–5 nghìn | 0,5–1,5 nghìn |
| Số từ mỗi câu | khoảng 25–30 | khoảng 20 | cũng dài |
| Flesch–Kincaid (năm đi học) | 13–15 | 10–12 | 13–15 |
| Tỷ lệ từ khác nhau | khoảng 0,1–0,15 | khoảng 0,35–0,4 | khoảng 0,5–0,6 |
| Tỷ lệ câu ẩn dụ (%) | khoảng 0–3 | khoảng 5–23 | khoảng 0–17 |

**Độ dài.** Thứ bậc độ dài rất ổn định: ngân sách dài nhất, phát biểu ở giữa, thông cáo ngắn nhất. Tài liệu ngân sách dài ra trong COVID để minh bạch và biện minh cho các biện pháp khẩn cấp; thông cáo dài ra trong khủng hoảng 2008. Anh và Mỹ đã rút gọn tài liệu ngân sách từ đầu thập niên 2010, còn Pháp thì mở rộng phần phụ lục. Canada, trong giai đoạn 2016–2018 và từ 2022, bỏ các phụ lục thuế đồ sộ để chuyển sang trình bày theo lối kể chuyện, xoay quanh "tầng lớp trung lưu". Từ khoảng 2016, phương sai của độ dài văn bản giữa các nước tăng vọt; thời điểm này không trùng với khủng hoảng 2008, cho thấy các chính phủ ngày càng khác nhau trong cách trình bày.

**Độ dễ đọc.** Bài phát biểu dễ đọc nhất, ở mức khoảng mười tới mười hai năm đi học, và sự hội tụ này giống nhau ở mọi nước. Để so sánh: tuyên bố chính sách tiền tệ ở các nước phát triển cần khoảng 16 năm đi học, phát biểu của lãnh đạo ECB khoảng 14,5. Như vậy phát biểu ngân sách dễ hiểu hơn hẳn. Ngược lại, tài liệu ngân sách và thông cáo đều cần trình độ đại học. Thông cáo ngắn nhưng không đơn giản: thực chất nó là một gói thông tin nén dành cho nhà báo và nhà phân tích.

**Phát hiện về thời gian.** Độ dễ đọc của tài liệu ngân sách và thông cáo gần như không đổi trong 20 năm, bất chấp khủng hoảng, đổi chính phủ hay các cải cách minh bạch. Điều này phản ánh một "văn phong nhà" của bộ máy hành chính. Chỉ có bài phát biểu đi theo xu hướng ngôn ngữ giản dị. Sau 2009, câu trong tài liệu ngân sách dài ra, còn câu trong bài phát biểu ngắn đi, nên hai kênh bù trừ cho nhau.

**Văn phong.** Tài liệu ngân sách ít màu sắc nhất, vì phải lặp đi lặp lại các thuật ngữ như thâm hụt, thuế, chương trình. Thông cáo có độ phong phú từ vựng cao nhất, nhất là đầu thập niên 2000, với các khẩu hiệu như "hỗ trợ gia đình lao động" hay "sống trong khả năng của mình". Thông cáo gần đây ở Anh và Canada tiết chế hơn, bớt khẩu hiệu. Ẩn dụ tăng lên trong các giai đoạn căng thẳng kinh tế, dù bài lưu ý cách định nghĩa ẩn dụ có thể thay đổi theo thời gian. Có khác biệt theo truyền thống pháp lý: các nước thông luật (Canada, Anh, Mỹ) dùng nhiều tự sự và ẩn dụ; các nước dân luật (Pháp, Ý) thiên về trình bày có cấu trúc; Nhật Bản ngắn gọn và định dạng chặt.

**Khoảng cách rõ ràng.** Hệ quả của kiến trúc này là ai chỉ nghe bài phát biểu sẽ bỏ lỡ các ràng buộc tài khoá, còn ai chỉ đọc tài liệu ngân sách sẽ bỏ lỡ cách chính phủ đóng khung vấn đề.

**Kiểm định thống kê về hình thức.** Bài dùng kiểm định t cặp để xem khác biệt giữa từng cặp kênh có ý nghĩa thống kê không (NS là ngân sách, PB là phát biểu, TC là thông cáo):

| Chỉ tiêu | NS so với TC | NS so với PB | PB so với TC |
|---|---|---|---|
| Độ dễ đọc | 4,7\*\*\* | 16,4\*\*\* | 13,9\*\*\* |
| Độ dài câu | 2,2\* | 12,3\*\*\* | 6,3\*\*\* |
| Độ phong phú từ vựng | 20,2\*\*\* | 29,4\*\*\* | 6,2\*\*\* |
| Độ dài văn bản | 18,5\*\*\* | 17,8\*\*\* | 10,2\*\*\* |

Gần như mọi khác biệt đều rất có ý nghĩa. Ngoại lệ duy nhất là độ dài câu giữa ngân sách và thông cáo, chỉ có ý nghĩa ở mức yếu, đúng như quan sát rằng câu trong thông cáo cũng dài.

### 5. Chủ đề và mục tiêu

**Chủ đề khác nhau theo kênh**, điều chứng tỏ bộ tài chính chủ động nhắm tới từng nhóm người nghe:

- **Tài liệu ngân sách** tập trung vào thuế và cơ chế chi tiêu.
- **Bài phát biểu** tập trung vào tăng trưởng, việc làm và chi xã hội.
- **Thông cáo** tập trung vào các sáng kiến mới (tăng chi, giảm thuế, dự án chủ lực) và bỏ qua các đánh đổi.

Trong các đợt khủng hoảng 2009 và 2020, mọi kênh đều chuyển sang chủ đề ổn định vĩ mô. Chủ đề khí hậu xuất hiện rải rác trước 2015 và nổi hơn sau Hiệp định Paris; Anh là nước chú ý tới khí hậu bền bỉ nhất. Mỗi nước cũng có điểm nhấn riêng: Mỹ và Anh nhấn giảm thuế; Pháp và Đức nhấn quy tắc (phanh nợ của Đức, tiêu chí Maastricht của EU); Nhật Bản nhấn dân số già và củng cố nợ. Khoảng 10–20% nội dung thuộc nhóm "khác": thủ tục, dẫn chiếu luật, lời đệm. Muốn thấy toàn bộ ưu tiên tài khoá của một chính phủ, người đọc phải đọc cả ba kênh.

**Cái giá của sự phân đoạn.** Chia thông điệp theo kênh có thể tăng ủng hộ chính trị ngắn hạn, nhưng làm yếu trách nhiệm giải trình. Công dân có thể ủng hộ một chương trình đầu tư "lịch sử" mà không hiểu hệ quả tài khoá của nó. Thị trường có thể định giá sai rủi ro nếu giả định tăng trưởng được nhấn mạnh còn dự báo nợ bị che đi.

**Mục tiêu theo kênh** (tỷ trọng ước đọc từ biểu đồ; bài lưu ý số liệu phần bài phát biểu trùng khớp với số liệu riêng của Canada, nên có thể đã đặt nhầm hình):

| Mục tiêu | Tài liệu ngân sách | Bài phát biểu |
|---|---|---|
| Phúc lợi xã hội | khoảng 24% | khoảng 33% |
| Trách nhiệm tài khoá | khoảng 19% | khoảng 15% |
| Bền vững môi trường | khoảng 13% | không đáng kể |
| Tạo việc làm | khoảng 12% | khoảng 19% |
| Năng lực cạnh tranh | khoảng 7% | khoảng 19% |

Mục tiêu trong bài phát biểu thiên về phúc lợi, việc làm và năng suất, với các câu như "xây nền kinh tế cho mọi người", "củng cố tầng lớp trung lưu". Mục tiêu trong tài liệu ngân sách thiên về bền vững tài khoá, quản lý nợ và tuân thủ quy tắc, với các câu như "đưa nợ trên GDP về 50% vào 2030", "đạt mục tiêu cân bằng trung hạn". Khí hậu nằm chủ yếu trong tài liệu ngân sách; bài phát biểu nhắc tới thưa thớt hoặc theo lối đạo đức.

Mục tiêu trách nhiệm tài khoá nổi bật ở một số nơi: chiếm khoảng 65% trong tài liệu ngân sách của Nhật, khoảng 58% trong bài phát biểu của Mỹ, khoảng 47% trong bài phát biểu của Nhật và khoảng 36% trong bài phát biểu của Đức. Đức gắn mục tiêu chặt với phanh nợ và nhấn mạnh việc tuân thủ hơn là tầm nhìn.

**Vai trò của thể chế.** Bài chưa phân tích chính thức vai trò của quy tắc tài khoá và hội đồng tài khoá, nhưng gợi ý rằng chúng có thể thu hẹp dư địa tu từ và làm nổi các tự sự dựa trên độ tin cậy.

### 6. Chi tiêu, thu và nợ công

**Động cơ "nhận công".** Chính phủ có động cơ nhận công cho các chính sách có lợi và giảm nhẹ chi phí của các chính sách gây thiệt. Dữ liệu G7 xác nhận điều này: chi tiêu được nói nhiều hơn thu ngân sách ở mọi kênh, và tăng chi áp đảo cắt chi.

Tỷ lệ câu theo loại (ước đọc; phần còn lại là câu trung lập):

| Kênh | Chi: tăng | Chi: giảm | Thu: tăng | Thu: giảm |
|---|---|---|---|---|
| Tài liệu ngân sách | khoảng 28% | khoảng 4% | khoảng 19% | khoảng 14% |
| Bài phát biểu | khoảng 31% | khoảng 3% | khoảng 17% | khoảng 22% |
| Thông cáo | khoảng 52% | khoảng 4% | khoảng 32% | khoảng 28% |

Câu về tăng chi nhiều gấp khoảng 7 lần câu về giảm chi trong tài liệu ngân sách, gấp khoảng 10 lần trong bài phát biểu và khoảng 13 lần trong thông cáo. Riêng bài phát biểu nói về giảm thu (giảm thuế) nhiều hơn tăng thu.

**Các kỹ thuật diễn đạt:**

- **Cắt chi** hiếm khi được nói thẳng. Thay vào đó là "tinh gọn", "tìm dư địa hiệu quả", "làm chậm tốc độ tăng chi". Nếu có nói thì dùng thì quá khứ, kiểu "năm ngoái chúng tôi đã có những quyết định khó khăn". Ví dụ Anh năm 2010–11: các chữ "trách nhiệm", "tiết kiệm nhờ hiệu quả", "kiềm chế lương khu vực công" được dùng thay cho chữ "cắt".
- **Tăng thu** được gắn với "thu thuế tốt hơn" hoặc "bịt kẽ hở"; gần như không bao giờ nói thẳng là tăng thuế diện rộng.
- **Ghép đôi:** khi buộc phải tăng thuế, chính phủ ghép ngay với một khoản chi được lòng dân. Ví dụ Nhật tăng thuế giá trị gia tăng năm 2014 và năm 2019 với lý do "bảo đảm an sinh xã hội".
- **Cải cách trung tính về thu** và cả việc "không tăng thuế" cũng được kể như một thành tích.
- Ví dụ Canada sau 2015: 60–70% số câu về thu ngân sách trong bài phát biểu là về giảm thuế, còn lo ngại về thâm hụt gần như biến mất.

**Hệ quả.** Có một sự bất cân xứng giữa thực tế tài khoá và tự sự tài khoá, và gánh nặng tìm ra mặt kém thuận lợi dồn lên nhà phân tích và nhà báo. Nhật Bản minh hoạ điều này: ràng buộc dài hạn rất lớn, nhưng truyền thông với công chúng vẫn chủ yếu là các cam kết chi.

**Sắc thái về nợ công.** Giọng lạc quan chiếm ưu thế ngay cả khi nợ đang tăng. Tỷ lệ câu tích cực về nợ (ước đọc):

| Kênh | Tỷ lệ câu tích cực |
|---|---|
| Bài phát biểu | Canada khoảng 72%, Anh khoảng 65%, Pháp khoảng 57%, Mỹ khoảng 56%, Đức khoảng 46%, Nhật khoảng 41% |
| Tài liệu ngân sách | Mỹ khoảng 51%, Canada khoảng 45%, các nước còn lại khoảng 25–35%; riêng Nhật có khoảng 55% số câu mang giọng tiêu cực |

Các công thức quen thuộc: nợ "sắp ổn định", "trong tầm kiểm soát", "đạt đỉnh năm sau rồi giảm" (Anh lặp lại câu này qua nhiều chu kỳ); Canada nói nước mình có "nợ thấp nhất G7". Giọng u ám chỉ xuất hiện trong các giai đoạn cấp tính (2009, 2020–21), và ngay lập tức được ghép với lạc quan về phục hồi. Bài gọi đây là "tính thuận chu kỳ nhẹ": lời nói luôn mạnh hơn nền tảng. Bài nói rõ rằng lạc quan không nhất thiết là trình bày sai, nhưng lạc quan lặp lại mà kết quả không khớp có thể dần làm mòn độ tin cậy. Bài phát biểu lạc quan hơn tài liệu viết.

**Kiểm định thống kê về nội dung.** Bài dùng kiểm định t một phía cho từng giả thuyết lạc quan:

| Giả thuyết | Tài liệu ngân sách | Thông cáo | Bài phát biểu |
|---|---|---|---|
| Nói về chi nhiều hơn thu | 12,9\*\*\* | 22,2\*\*\* | 10,8\*\*\* |
| Nói về tăng chi nhiều hơn giảm chi | 24,6\*\*\* | 43,6\*\*\* | 27,4\*\*\* |
| Nói về giảm thu nhiều hơn tăng thu | −3,1 | −11,3 | 6,9\*\* |
| Câu tích cực về nợ nhiều hơn câu tiêu cực | 9,5\*\*\* | 44,8\*\*\* | 30\*\*\* |

Giả thuyết lạc quan đúng ở hầu hết các ô. Riêng giảm thuế chỉ được nhấn mạnh trong bài phát biểu; ở tài liệu ngân sách và thông cáo, giá trị t âm nghĩa là tăng thu được bàn nhiều hơn giảm thu.

### 7. Thảo luận và hàm ý

**Vì sao chính phủ nói như vậy.** Xu hướng nhấn lợi ích và giảm nhẹ chi phí phản ánh ba điều: tâm lý ngại mất mát (người ta phản ứng mạnh với thiệt hại hơn với lợi ích cùng cỡ), hiệu ứng nổi bật (điều được nhắc nhiều thì được nhớ) và động cơ nhận công. Nhưng nó có thể gây ra "ảo giác tài khoá", khiến công chúng hiểu sai các đánh đổi.

**Giới hạn của truyền thông.** Truyền thông chiến lược chỉ ổn định kỳ vọng tạm thời; nó không bù được rủi ro nền tảng khi quỹ đạo nợ xấu đi. Nó cũng phụ thuộc vào việc có dữ liệu tài khoá kịp thời và đáng tin.

**Khuyến nghị:**

- Bộ tài chính nên truyền thông có điều kiện và theo giai đoạn: thừa nhận tình hình xấu đi trong ngắn hạn, nhưng nêu rõ lộ trình củng cố trung hạn.
- Cần chú ý hệ quả phân phối: khi truyền thông nhấn lợi ích và giảm nhẹ chi phí đến sau, hộ thu nhập thấp có thể chịu gánh nặng không tương xứng, làm xói mòn niềm tin.
- Các nước mới nổi đang cải cách khung minh bạch có cơ hội áp dụng cách truyền thông tích hợp và cân đối ngay từ đầu. IMF và OECD có thể xây dựng hướng dẫn không chỉ về quy tắc tài khoá mà cả về thực hành tự sự.
- Trong khủng hoảng, chính phủ thường vội chuyển sang trấn an. Cách tốt hơn là lập kịch bản, công bố các rủi ro dự phòng và nói thẳng về rủi ro mà không gây hoảng loạn.

**Học từ các lĩnh vực khác.** Từ truyền thông y tế, khí hậu và quản lý khủng hoảng, bài rút ra sáu bài học: bắt đầu từ niềm tin chứ không phải kỹ thuật; kể bằng câu chuyện; khán giả khác nhau cần thông điệp khác nhau; nhất quán quan trọng ngang nội dung; cho thấy giá trị đằng sau con số; đối thoại chứ không độc thoại.

**Mười nguyên tắc cho truyền thông tài khoá:**

1. Rõ ràng về thông điệp và về kênh (truyền thông nhiều tầng có chủ đích).
2. Nhất quán trong nội bộ và giữa các cơ quan.
3. Minh bạch về bất định: nêu khoảng dự báo, giả định, kịch bản.
4. Giải thích đánh đổi, và ai được, ai mất.
5. Truyền thông là một quá trình, không phải một khoảnh khắc.
6. Tự sự là một chiến lược.
7. Nhạy cảm về văn hoá và ngôn ngữ.
8. Thừa nhận các ràng buộc kinh tế chính trị.
9. Giữ ký ức thể chế và tính liên tục qua các nhiệm kỳ.
10. Tương tác chứ không chỉ phát đi.

**Đề xuất thể chế.** Bài đề xuất một chế độ truyền thông tài khoá có cấu trúc, giống khung lạm phát mục tiêu của ngân hàng trung ương: có điểm neo tự sự (ví dụ một lộ trình nợ được nhắc lại nhất quán), có bản tóm tắt bằng ngôn ngữ giản dị, và có "kiểm toán tự sự" do bên thứ ba thực hiện. Hội đồng tài khoá độc lập như OBR của Anh có thể đánh giá cả mức mạch lạc giữa lời nói và con số. Một ví dụ đã có: tháng 3/2025, Pháp cam kết thêm một mục về bất định và rủi ro vào tài liệu ngân sách, áp dụng lần đầu cho dự thảo ngân sách 2026.

### 8. Kết luận

Truyền thông tài khoá ở G7 có một kiến trúc nhất quán và gần như không đổi suốt hai thập kỷ: tài liệu ngân sách nhấn quy tắc và kiềm chế; bài phát biểu nhấn công bằng và tiến bộ; thông cáo chưng cất các thông điệp lạc quan. Như bài tóm lại, truyền thông tài khoá mang tính nhị nguyên: đơn giản khi nói, phức tạp khi viết.

Thiên lệch lạc quan kéo dài có thể làm giảm độ tin cậy khi các kỳ vọng không thành hiện thực. Sự khác biệt giữa các kênh có thể làm hiểu biết của công chúng và thị trường bị phân mảnh, mỗi bên nắm một nửa bức tranh. Thiết kế thể chế, như hội đồng tài khoá độc lập, có thể giúp lời kể và phép tính khớp nhau. Câu kết của bài: qua mọi kênh và mọi chu kỳ, sự mạch lạc không phải là thứ xa xỉ mà là điều kiện tiên quyết của niềm tin tài khoá.

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

## Đánh giá và phát hiện đáng chú ý

### Bằng chứng rõ nhất cho luận điểm trung tâm nằm trong một ô của bảng mà bài không đánh dấu

Trong Bảng 2, hầu hết các kiểm định đều đi cùng một hướng ở cả ba kênh: chi được nói nhiều hơn thu, tăng chi áp đảo giảm chi, giọng về nợ tích cực hơn tiêu cực. Chỉ có **một dòng duy nhất đổi dấu giữa các kênh**, và đó chính là dòng có nội dung nhất.

Giả thuyết "giảm thu được nhấn nhiều hơn tăng thu" cho kết quả **+6,9 có ý nghĩa ở bài phát biểu**, nhưng **−3,1 ở tài liệu ngân sách** và **−11,3 ở thông cáo**. Nghĩa là trong văn bản kỹ thuật, tăng thuế được bàn **nhiều hơn** giảm thuế; trong bài phát biểu trước công chúng thì ngược lại.

Đây là bằng chứng sạch nhất trong toàn bài cho luận điểm về kiến trúc hai khán giả, và nó không được đánh dấu sao, không được đưa vào tóm tắt. Phát biểu lại cho thẳng: **nhà nước nói với thị trường trái phiếu rằng mình sẽ tăng thu, và nói với cử tri rằng mình sẽ giảm thuế**, trong cùng một chu kỳ ngân sách, về cùng một bộ quyết định.

Điều này cũng làm rõ vì sao bài lại chọn phương pháp so sánh giữa các kênh trong cùng một nước và cùng một năm. Vì cả ba văn bản nói về **cùng một thực tế tài khoá**, mọi khác biệt giữa chúng đều là lựa chọn truyền thông thuần tuý. Đó là một thiết kế nhận dạng rất khéo, và ô vừa nêu là chỗ nó cho kết quả sắc nhất.

### Cái mà bài gọi là khiếm khuyết có thể chính là chức năng

Bài mô tả "khoảng cách rõ ràng" giữa các kênh như một vấn đề cần khắc phục: ai chỉ nghe phát biểu thì bỏ lỡ ràng buộc, ai chỉ đọc ngân sách thì bỏ lỡ cách đóng khung. Phần khuyến nghị đề xuất một chế độ truyền thông tài khoá có cấu trúc để hàn gắn khoảng cách đó.

Nhưng có một dữ kiện trong chính bài làm cách đọc này khó đứng vững: độ dễ đọc của tài liệu ngân sách và thông cáo **gần như không đổi suốt hai mươi năm**, bất chấp khủng hoảng 2008, đại dịch, hàng chục lần đổi chính phủ, và nhiều đợt cải cách minh bạch được thiết kế riêng để thay đổi điều này. Chỉ bài phát biểu đi theo xu hướng ngôn ngữ giản dị.

Một đặc tính sống sót qua hai thập kỷ áp lực cải cách ở bảy nước khác nhau thì khó gọi là một thói quen hành chính. Nó nhiều khả năng là một **cân bằng ổn định vì nó phục vụ ai đó**.

Và cơ chế thì khá rõ. Kiến trúc phân tầng cho phép một chính phủ **cam kết kỷ luật tài khoá ở nơi người cho vay đọc** — tài liệu ngân sách, nơi mục tiêu trách nhiệm tài khoá chiếm khoảng 19% và có các công thức như "đưa nợ trên GDP về 50% vào 2030" — trong khi **hứa hẹn mở rộng ở nơi cử tri nghe**, bài phát biểu, nơi phúc lợi xã hội chiếm khoảng 33% và trách nhiệm tài khoá chỉ khoảng 15%.

Bài chạm vào điều này một lần, khi ghi nhận rằng sự phân đoạn có thể tăng ủng hộ chính trị ngắn hạn nhưng làm yếu trách nhiệm giải trình. Nhưng nó vẫn xử lý hiện tượng như một sai sót về phối hợp. Cách đọc thuyết phục hơn là: **đây là một thiết kế, và nó tồn tại vì nó cho phép một chính phủ giữ hai lời hứa không tương thích với hai nhóm không đọc cùng một tài liệu**.

### "Thiên lệch lạc quan" đo bằng giọng điệu, và phản ví dụ Nhật Bản

Đây là chỗ cần dè dặt nhất về mặt khái niệm. Bài gán nhãn tích cực, tiêu cực hoặc trung lập cho từng câu nói về nợ công, và kết luận rằng giọng điệu tích cực chiếm ưu thế **ngay cả khi nợ đang tăng** — con số tiêu biểu là khoảng 72% câu tích cực trong bài phát biểu của Canada, 65% của Anh.

Nhưng nhiều câu được xếp là "tích cực" thực chất là **dự báo**, không phải cảm xúc. "Nợ sẽ đạt đỉnh năm sau rồi giảm" là một mệnh đề có thể đúng hoặc sai. Nếu nó đúng, đó không phải thiên lệch; đó là thông tin.

Để chứng minh có thiên lệch, phải **đối chiếu phát ngôn với kết quả thực tế**: bao nhiêu lần lời hứa "nợ đạt đỉnh năm sau" được thực hiện, và bao nhiêu lần nó bị dời sang chu kỳ tiếp theo. Bài ghi nhận rằng Anh lặp lại công thức này qua nhiều chu kỳ — một quan sát rất gợi — nhưng không bao giờ biến nó thành một phép đo.

Nếu làm phép đo đó, ta sẽ có một thứ có giá trị thực: **tỷ lệ thực hiện lời hứa tài khoá theo nước và theo thời gian**. Đó mới là thước đo độ tin cậy mà bài nói là mình quan tâm. Cái đang được đo hiện nay là **tông giọng**, và hai thứ này chỉ trùng nhau khi dự báo sai.

Trong toàn bộ mẫu, Nhật Bản là nước có truyền thông tài khoá **bi quan nhất**: tài liệu ngân sách có khoảng 55% số câu về nợ mang giọng **tiêu cực**, mục tiêu trách nhiệm tài khoá chiếm khoảng **65%** nội dung ngân sách và khoảng 47% bài phát biểu — cao nhất mẫu ở cả hai chỉ tiêu. Bài cũng ghi nhận Nhật nhấn mạnh dân số già và củng cố nợ hơn bất kỳ nước nào.

Nhật Bản cũng là nước có tỷ lệ nợ công cao nhất trong mẫu, khoảng 235% GDP.

Quan sát này đủ để bác bỏ bất kỳ liên hệ đơn giản nào giữa giọng điệu truyền thông và kết quả tài khoá. Nếu nói thẳng về khó khăn tạo ra kỷ luật, Nhật phải là nước có kết quả tốt nhất. Bài ghi nhận sự bất thường của Nhật trong một câu khác — rằng ràng buộc dài hạn rất lớn nhưng truyền thông công chúng vẫn chủ yếu là cam kết chi — nhưng không đặt nó cạnh các chỉ số bi quan của chính nước này, và không rút ra kết luận.

Kết luận đáng rút là: **truyền thông tài khoá phản ánh ràng buộc chứ không tạo ra nó**. Nhật nói bi quan vì tình hình bi quan, và nói bi quan không giúp cải thiện tình hình.

### Hai giới hạn: không đo hệ quả, và ranh giới của khâu dịch máy

Bài rất trung thực về điều này: cách tiếp cận là mô tả, không nhân quả, và **không đo tác động lên lợi suất hay kỳ vọng**. Đây là một lựa chọn hợp lệ cho một công trình xây dựng bộ dữ liệu đầu tiên trong lĩnh vực.

Nhưng toàn bộ phần khuyến nghị — mười nguyên tắc, kiểm toán tự sự, chế độ truyền thông có cấu trúc giống khung lạm phát mục tiêu — giả định rằng truyền thông tốt hơn tạo ra kết quả tốt hơn. Không có gì trong bài ủng hộ giả định đó.

Và có một điều trong chính bài đi ngược lại. Thiên lệch lạc quan được ghi nhận là **gần như không đổi suốt hai thập kỷ** ở cả bảy nước. Nếu nó đã ổn định như vậy trong suốt hai mươi năm mà không gây ra hậu quả có thể nhận diện được, thì có hai cách hiểu, và cả hai đều thú vị hơn kết luận mà bài đưa ra.

**Cách hiểu thứ nhất:** thị trường và nhà phân tích đã chiết khấu hoàn toàn giọng điệu chính trị và chỉ đọc con số. Khi đó thiên lệch lạc quan là vô hại đối với định giá — nhưng nó cũng có nghĩa là **truyền thông tài khoá có giá trị tín hiệu gần bằng không**, và toàn bộ chương trình cải cách truyền thông mà bài đề xuất sẽ không thay đổi gì.

**Cách hiểu thứ hai:** nó có hại, nhưng qua một kênh chậm — sự mòn dần của lòng tin công chúng — mà bài không có công cụ để đo.

Ví dụ thất bại duy nhất được bài nêu, ngân sách mini của Anh năm 2022, lại ủng hộ cách hiểu thứ nhất một cách khó chịu: thị trường phản ứng dữ dội vì tài liệu **không nói rõ khoản cắt thuế được tài trợ ra sao**, tức là vì một khoảng trống **nội dung**, không phải vì giọng điệu hay cách đóng khung.

Có một vấn đề kỹ thuật cụ thể đáng lưu ý. Văn bản của Pháp, Đức và Ý được dịch sang tiếng Anh bằng chính mô hình ngôn ngữ sau đó dùng để phân loại chủ đề và sắc thái, và mọi chỉ số đều được tính **sau khi dịch**.

Bài thừa nhận rủi ro chung. Nhưng có một phát hiện cụ thể nằm đúng trên đường ranh giới này: **nước thông luật (Canada, Anh, Mỹ) dùng nhiều tự sự và ẩn dụ hơn; nước dân luật (Pháp, Ý) thiên về trình bày có cấu trúc**.

Canada, Anh và Mỹ là ba nước **không bị dịch**. Pháp và Ý là hai nước **bị dịch**. Và dịch máy có xu hướng đã biết là **san phẳng thành ngữ và ẩn dụ**, chuyển chúng về diễn đạt chuẩn mực. Tỷ lệ câu ẩn dụ là một chỉ số đặc biệt nhạy với điều này.

Kết quả về truyền thống pháp lý vì thế không tách được khỏi hiệu ứng của khâu dịch. Nó có thể vẫn đúng — có lý do độc lập để tin rằng văn hoá hành chính Pháp và Ý ít dùng tu từ hơn — nhưng thiết kế hiện tại không kiểm chứng được.

Đây cũng là một trường hợp nữa của vấn đề tái lập mới mà mô hình ngôn ngữ tạo ra cho kinh tế học, vấn đề đã được nêu độc lập trong tài liệu về kinh tế vĩ mô của chiến tranh và phục hồi ở thư mục ASEAN: phiên bản mô hình sẽ bị ngừng phục vụ, kết quả phân loại không tất định, và một bước xử lý dữ liệu trung tâm sẽ không tái lập được sau vài năm.

### Mô hình ngân hàng trung ương không nhập khẩu được, vì lý do hiến định chứ không phải kỹ thuật

Khung của bài dựng trên tương phản "ngân hàng trung ương nói, bộ tài chính làm", và đề xuất một chế độ truyền thông tài khoá có cấu trúc tương tự khung lạm phát mục tiêu.

Nhưng sự khác biệt giữa hai loại cơ quan này không chủ yếu nằm ở kỹ năng truyền thông. Một tuyên bố của ngân hàng trung ương là **một cam kết có thể thực hiện đơn phương**: cơ quan đó có công cụ trong tay, một mục tiêu duy nhất, và không cần sự chấp thuận của ai. Một tuyên bố của bộ trưởng tài chính về thuế và chi tiêu là **một đề nghị cần quốc hội thông qua**, và bộ trưởng có thể mất ghế trước khi nó được thông qua.

Nghĩa là hướng dẫn tương lai của một bộ trưởng tài chính **kém đáng tin về mặt cấu trúc**, không phải vì cách diễn đạt mà vì bản chất quyền lực. Không một cải tiến tu từ nào sửa được điều đó, và chính bài cũng ghi nhận rằng cửa sổ chính sách hiệu quả rất hẹp.

Đó là lý do đề xuất cụ thể nhất của bài — **hội đồng tài khoá độc lập thực hiện kiểm toán tự sự**, kiểm tra xem lời kể có khớp với số học không — lại là đề xuất đúng hình dạng nhất. Nó không cố làm cho lời hứa của chính trị gia đáng tin hơn; nó đặt độ tin cậy vào một cơ quan **không phải tái tranh cử**. Đó chính là cấu trúc tạo ra độ tin cậy của ngân hàng trung ương, và là phần duy nhất của mô hình đó thực sự chuyển giao được.

### Một chuỗi nhân quả ghép từ hai tài liệu, và hàm ý cho Việt Nam

Tài liệu này và nghiên cứu khảo sát về nhận thức của người dân về nợ công trong cùng thư mục được viết bởi các nhóm khác nhau, và chúng khớp với nhau thành một lập luận mà không bài nào tự hoàn thành.

Nghiên cứu khảo sát ghi nhận **kết quả**: hơn 60% người trả lời đánh giá thấp tỷ lệ nợ trên GDP của nước mình, và mức đánh giá thấp càng lớn ở các nước nợ càng cao; chỉ khoảng 42% hiểu rằng tăng thuế hoặc cắt chi làm giảm thâm hụt.

Bài này ghi nhận **cơ chế**: trong mọi kênh truyền thông chính thức, chi tiêu được nói nhiều hơn thu; tăng chi áp đảo cắt chi với tỷ lệ khoảng 7:1 trong tài liệu ngân sách và 13:1 trong thông cáo; cắt chi gần như không bao giờ được gọi bằng tên thật mà là "tinh gọn", "tìm dư địa hiệu quả", "làm chậm tốc độ tăng chi", và nếu có nói thẳng thì dùng thì quá khứ; và giọng điệu về nợ vẫn tích cực ngay cả khi nợ tăng.

Ghép lại: công chúng không hiểu ràng buộc ngân sách một phần vì **hệ thống truyền thông chính thức được cấu trúc để họ không hiểu**. Sự thiếu hiểu biết mà bài khảo sát đo được không phải một thất bại giáo dục ngẫu nhiên; nó là sản phẩm có thể dự đoán được của một cách nói đã ổn định suốt hai thập kỷ.

Và điều đó làm cho khuyến nghị "giáo dục công chúng" trong tài liệu khảo sát trở nên yếu ớt: không thể giáo dục công chúng bằng cách bổ sung thông tin vào một hệ thống đang liên tục phát đi thông tin lệch.

Bài nói thẳng rằng các nước mới nổi đang cải cách khung minh bạch có cơ hội áp dụng cách truyền thông tích hợp và cân đối **ngay từ đầu**, thay vì phải gỡ một thói quen đã thành hình như ở G7. Đó là lời khuyên gửi đúng địa chỉ.

**Một phép chẩn đoán có thể làm ngay và gần như không tốn gì.** Lấy ba văn bản của cùng một kỳ ngân sách — báo cáo trình Quốc hội, phát biểu của lãnh đạo ngành tài chính, và thông cáo báo chí — rồi đếm ba thứ: tỷ lệ câu về chi so với câu về thu; tỷ lệ câu về tăng chi so với câu về tiết giảm chi; và số lần mỗi văn bản nêu con số nợ công và nghĩa vụ trả nợ. Nếu ba văn bản cho ba bức tranh khác nhau về cùng một bộ số, thì kiến trúc phân tầng đã hình thành. Đây là phép đo mà bài đã chứng minh là làm được với công cụ phổ thông.

**Điểm neo tự sự cần được theo dõi qua nhiều chu kỳ.** Công thức "nợ sẽ đạt đỉnh rồi giảm" là mẫu hình mà bài ghi nhận ở Anh qua nhiều chu kỳ liên tiếp. Chỉ tiêu cần lập là: mỗi cam kết tài khoá trung hạn được công bố, sau ba năm đối chiếu với kết quả thực tế, và công bố tỷ lệ thực hiện. Đó là thước đo độ tin cậy duy nhất có ý nghĩa, và nó không đòi hỏi bất kỳ công nghệ nào.

**Hội đồng tài khoá độc lập là thể chế có chức năng rõ nhất và chi phí thấp nhất trong toàn bộ danh sách khuyến nghị.** Không phải để dự báo tốt hơn bộ tài chính, mà để làm đúng một việc: xác nhận công khai rằng các con số trong kế hoạch có cộng lại đúng hay không, và các giả định tăng trưởng có nằm trong khoảng hợp lý hay không. Bài ghi nhận rằng Anh có Văn phòng Trách nhiệm Ngân sách đảm nhận một phần nội dung phân tích, và rằng chính sự tồn tại của cơ quan này làm thay đổi nội dung tài liệu ngân sách. Đó là bằng chứng cho thấy thể chế thay đổi được lời nói, trong khi lời khuyên về cách nói thì không.

**Và một lưu ý về hệ quả phân phối** mà bài nêu ở phần thảo luận và đáng được nhấn mạnh: khi truyền thông nhấn lợi ích trước mắt và giảm nhẹ chi phí trễ, **hộ thu nhập thấp thường chịu gánh nặng không tương xứng**, vì họ là nhóm ít có khả năng tự tìm ra phần thông tin bị bỏ sót và ít có khả năng phòng ngừa trước các điều chỉnh về sau. Cái giá của mơ hồ có chủ đích không được phân bổ đều.
