# The Effects of Fiscal Consolidations on the Debt Distribution — Tác động của củng cố tài khoá lên toàn bộ phân phối nợ công

**Nguồn:** IMF Working Paper WP/25/201, tháng 10/2025, Vụ Tài khoá.
**Tác giả:** Francesco Frangiamore, Davide Furceri, Domenico Giannone, Faizaan Kisat, Pietro Pizzuto.
**Ý chính:** Nợ công toàn cầu đang tiến tới 100% GDP, và rủi ro nghiêng về phía tăng: trong kịch bản xấu nghiêm trọng, nợ có thể lên **khoảng 117% GDP vào 2027**. Các nghiên cứu trước chủ yếu hỏi củng cố tài khoá tác động thế nào lên **tăng trưởng**. Bài này hỏi củng cố tác động thế nào lên **toàn bộ phân phối nợ trong tương lai**, trong đó quan trọng nhất là **đuôi phải**, tức "nợ có rủi ro" (debt-at-risk) đo bằng phân vị thứ 95. Mẫu gồm **192 nước, 1991–2021**. Cú sốc chi tiêu được nhận diện bằng **sai số dự báo chi tiêu** của IMF, và ước lượng bằng **mô hình vị trí–quy mô** kết hợp phép chiếu địa phương. Cắt chi 1% GDP làm nợ/GDP bình quân giảm khoảng **0,7 điểm ngay, đỉnh 0,9 điểm sau hai năm**. Điểm mới là củng cố còn **thu hẹp độ bất định** của nợ: nợ có rủi ro giảm khoảng **1 điểm trong ngắn hạn và 1,5 điểm trong trung hạn**, trong khi đuôi trái gần như không đổi. Tác động mạnh hơn khi nước đó **có quy tắc tài khoá** (nợ có rủi ro giảm khoảng 2 điểm, so với 0,5 điểm không có ý nghĩa thống kê) và khi **nợ ban đầu cao** (gấp khoảng bốn lần).

> **Lưu ý:** bản PDF đầy đủ. Một số điểm không khớp nội bộ:
> - Bài nói nợ có rủi ro giảm 1,5 điểm "sau năm năm", nhưng các ước lượng chỉ tới chân trời h = 4 (từ năm 0 tới năm 4).
> - Chú thích 18 dẫn chiếu "các cơ chế ở Mục III", trong khi phần cơ chế là Mục IV.
> - Văn bản dẫn Koenker và Basset (1987) và Loria, Matthes và Zhang (2015), còn danh mục ghi 1978 và 2025. Phụ lục ghi Furceri và cộng sự (2024), còn danh mục ghi 2025.
> - Bảng C.2 ghi dự báo chi tiêu chính phủ (theo % GDP) có bình quân 1,32 × 10⁹, rõ ràng sai đơn vị.
> - Hình A.8 bị in lộn ngược.
> Các số lấy từ hình là giá trị ước đọc.

## Sơ đồ

### Vì sao cần nhìn vào đuôi phân phối

```text
       HÌNH 1 — NỢ CÔNG TOÀN CẦU
       bình quân thế giới ~93% GDP cuối 2024 → gần 100% cuối thập kỷ
       ★ phân phối dự báo cho 2027 (Furceri và cộng sự 2025):
         trung vị ~97,5% · ★ phân vị 95 ~116,6% → cao hơn trung vị
         ~20 điểm, mức chưa thấy từ Thế chiến II
       ═══════════════════════════════════════════════════════════
       ★ NỢ CÓ RỦI RO (debt-at-risk) = phân vị thứ 95 của phân phối
         nợ/GDP dự báo
       nợ cao và nợ có rủi ro cao → thu hẹp dư địa tài khoá, báo trước
         căng thẳng chủ quyền
       ═══════════════════════════════════════════════════════════
       ❓ các nghiên cứu trước (Guajardo–Leigh–Pescatori, Alesina–
         Favero–Giavazzi…) hỏi củng cố tác động lên TĂNG TRƯỞNG
       ★ bài này hỏi: củng cố tác động lên TOÀN BỘ phân phối nợ tương
         lai ra sao, nhất là ĐUÔI PHẢI?
       vì sao chọn CẮT CHI: nhận diện được cho nhiều nước; chi tiêu
         không bị chu kỳ chi phối như thu; và củng cố dựa vào chi giảm
         nợ hiệu quả hơn dựa vào thuế (Alesina và cộng sự 2019)
```

### Mô hình vị trí–quy mô

```text
       PHƯƠNG TRÌNH (1), h = 0…4 năm
       d(t+h) = α(i) + β₁·g(t) + X'β₂ + [δ(i) + γ₁·g(t) + X'γ₂]·ε
                └──── VỊ TRÍ ────┘     └──── QUY MÔ ────┘
       d = nợ/GDP · g = chi tiêu chính phủ/GDP · X = biến kiểm soát
       ═══════════════════════════════════════════════════════════
       ★ TÁC ĐỘNG LÊN PHÂN VỊ τ: β₁ + γ₁·q(τ)
       q(τ) = nghịch đảo hàm phân phối của sai số tại τ
       ┌─────────────────┬──────────────────────────────────────────┐
       │ γ₁ = 0          │ chỉ DỊCH phân phối, mọi phân vị như nhau  │
       │                 │ (= phép chiếu địa phương tuyến tính)      │
       │ β, γ CÙNG DẤU   │ dịch VÀ giãn → đuôi phải chịu tác động    │
       │                 │ MẠNH NHẤT                                 │
       │ β, γ NGƯỢC DẤU  │ dịch nhưng đuôi TRÁI chịu nhiều hơn       │
       └─────────────────┴──────────────────────────────────────────┘
       (tác động của CẮT chi = nhân cả hai hệ số với −1)
       ═══════════════════════════════════════════════════════════
       vì sao KHÔNG dùng hồi quy phân vị thông thường: thêm biến giả
         nước vào dữ liệu bảng gây vấn đề THAM SỐ NGẪU NHIÊN
       ★ mô hình Machado–Santos Silva (2019) cho phép đặc điểm nước
         tác động lên CẢ phân phối, không chỉ dịch vị trí
       ước lượng GMM một bước (MM-QR trong Stata), sai số theo cụm nước
```

### Nhận diện cú sốc chi tiêu

```text
       ★ CÚ SỐC = phần chi tiêu KHÔNG DỰ BÁO ĐƯỢC
       theo định lý Frisch–Waugh–Lovell: g̃ = g − E(g | X)
       ═══════════════════════════════════════════════════════════
       BIẾN KIỂM SOÁT X
       ① dự báo chi tiêu của IMF công bố THÁNG 10 cùng năm
          → cú sốc chỉ gồm phần chi không lường trước; để phản ứng
            theo chu kỳ lọt vào thì phải xảy ra trong tháng 10–12,
            điều khó xảy ra do độ trễ lập pháp (theo Blanchard–Perotti)
       ② dự báo tháng 10 về tăng trưởng và lạm phát + trễ của nợ, chi
          tiêu, tăng trưởng, lạm phát (theo Colombo và cộng sự 2024)
       ═══════════════════════════════════════════════════════════
       VÌ SAO KHÔNG DÙNG CÁCH KHÁC
       SVAR Blanchard–Perotti ··· cần dữ liệu QUÝ
       phương pháp tường thuật ··· thiếu tài liệu ở nước mới nổi
       chi quân sự ··············· dính vấn đề "tầm nhìn tài khoá": người
                                   dân phản ứng từ khi biết TRƯỚC
       ═══════════════════════════════════════════════════════════
       ✔ BA TIÊU CHÍ NGOẠI SINH CỦA RAMEY (2016) — Bảng C.3
       không tương quan với biến vĩ mô hiện tại và quá khứ, cũng như
         sai số dự báo của chúng (thành phần chính thứ nhất)
       không dự báo được (xây từ sai số dự báo)
       không tương quan với chỉ số Bất định Thế giới hay cú sốc tiền tệ
       ★ Bảng C.4: bình quân ≈ 0, độ lệch chuẩn 3,3, khoảng tứ phân vị
         từ −1,4% đến +1,1%
```

### Kết quả cơ sở

```text
       ★★ HÌNH 3 — CẮT CHI 1% GDP (điểm %, ước đọc)
       ┌──────────────┬───────┬───────┬───────┬───────┬───────┐
       │ năm          │   0   │   1   │   2   │   3   │   4   │
       ├──────────────┼───────┼───────┼───────┼───────┼───────┤
       │ VỊ TRÍ       │ ~−0,65│ ~−0,8 │★~−0,9 │ ~−0,78│ ~−0,55│
       │ (bình quân)  │       │       │       │       │       │
       │ QUY MÔ       │ ~−0,11│ ~−0,1 │ ~−0,2 │★~−0,3 │ ~−0,2 │
       │ (độ bất định)│       │       │       │       │       │
       └──────────────┴───────┴───────┴───────┴───────┴───────┘
       → cả hai đều ÂM và có ý nghĩa ở mọi chân trời
       ★ một độ lệch chuẩn cú sốc ≈ giảm 17% độ lệch chuẩn của nợ/GDP
         ngay lập tức, 23% sau hai năm
       ═══════════════════════════════════════════════════════════
       ★★ HÌNH 4 — THEO PHÂN VỊ (ước đọc)
       ┌──────────────┬──────────────────┬───────────────────────┐
       │              │ PHÂN VỊ 5        │ ★ PHÂN VỊ 95          │
       │              │ (nợ thấp)        │ (nợ có rủi ro)        │
       ├──────────────┼──────────────────┼───────────────────────┤
       │ năm 0        │ ~−0,45           │ ~−0,95                │
       │ năm 2        │ ~−0,5            │ ~−1,35                │
       │ năm 3        │ ~−0,2            │ ★ ~−1,5               │
       │ năm 4        │ ~−0,2, mất ý     │ ~−1,0                 │
       │              │ nghĩa từ năm 2   │                       │
       └──────────────┴──────────────────┴───────────────────────┘
       → đường tác động DỐC XUỐNG theo phân vị ở MỌI chân trời
       ★★ ĐỌC KẾT QUẢ: cắt chi không chỉ đẩy phân phối sang trái mà còn
          làm nó HẸP lại → các kết cục nợ rất cao ÍT xảy ra hơn
       ═══════════════════════════════════════════════════════════
       ★ ĐỐI CHIẾU: Fiscal Monitor 2024 khuyến nghị điều chỉnh tích luỹ
         3–4,5% GDP → theo bài, nợ có rủi ro giảm khoảng 4,5–7 điểm
```

### Độ vững

```text
       ✔ số độ trễ 1, 3, 4 thay vì 2 → gần như không đổi
       ✔ bỏ giá trị cực đoan (dưới phân vị 1, trên phân vị 99) của nợ,
         của chi tiêu, hoặc cả hai → tương tự
       ⚠ thay chi tiêu bằng CÁN CÂN tài khoá: vị trí tương tự, nhưng
         quy mô YẾU hơn → ít bất đối xứng, vẫn còn ở năm 3–4
       ✔ Canay (2011): bỏ hiệu ứng cố định trước rồi hồi quy phân vị →
         ít bất đối xứng hơn nhưng vẫn dốc xuống
       ✔ hồi quy phân vị biến công cụ của Chernozhukov–Hansen (2006),
         công cụ là sai số dự báo tăng chi thực đã làm sạch → tương tự
         về định tính
```

### Cơ chế: vì sao nợ giảm

```text
       ★ PHƯƠNG TRÌNH ĐỘNG THÁI NỢ: nợ phụ thuộc cán cân sơ cấp, lãi
         suất, tăng trưởng, lạm phát
       ═══════════════════════════════════════════════════════════
       HÌNH 5 — NGÂN SÁCH (ước đọc)
       cán cân · vị trí +0,7 điểm ngay rồi giảm dần; quy mô ÂM → giảm
                 rủi ro thâm hụt lớn trong tương lai
       chi ····· vị trí −1 ngay, hồi dần
       ⚠ thu ··· GIẢM (~−0,27 ngay) vì sản lượng và lạm phát thấp hơn
       ═══════════════════════════════════════════════════════════
       HÌNH 6 — VĨ MÔ
       lạm phát ······· giảm nhẹ, đỉnh sau hai năm; quy mô không đổi
       ★ số nhân GDP ·· ÂM và NHỎ HƠN 1 (~0,2–0,4) → củng cố KHÔNG tự
                         thất bại; quy mô cũng GIẢM → bất định vĩ mô thấp
       ★ lãi dài hạn ·· giảm, rõ từ năm 2 (~−0,35); quy mô giảm tới năm 3
                         → có thể qua kênh PHẦN BÙ RỦI RO
       ═══════════════════════════════════════════════════════════
       ★★ PHÂN RÃ SAU MỘT NĂM
       nợ bình quân giảm 0,8 điểm, trong đó 0,55 điểm (~70%) nhờ cán
         cân cải thiện; phần còn lại qua tăng trưởng và lãi suất
```

### Quy tắc tài khoá

```text
       dữ liệu: Acalin và cộng sự (2025), 106 nước từng có quy tắc
         tài khoá 1985–2024; biến giả R = 1 nếu có quy tắc trong năm
       PHƯƠNG TRÌNH (4): mọi hệ số tách riêng cho hai trạng thái
       ═══════════════════════════════════════════════════════════
       ★★ HÌNH 7 — QUY TẮC CHUNG (ước đọc)
       ┌──────────────────┬──────────────────┬───────────────────┐
       │                  │ CÓ QUY TẮC       │ KHÔNG QUY TẮC     │
       ├──────────────────┼──────────────────┼───────────────────┤
       │ vị trí, trung hạn│ ★ −1,2           │ dưới −0,5         │
       │ quy mô, năm 0    │ ~−0,27           │ ~0                │
       │ nợ có rủi ro,    │ ★ ~−1,9          │ ~−0,5, KHÔNG ý    │
       │ năm 4            │                  │ nghĩa             │
       └──────────────────┴──────────────────┴───────────────────┘
       BẢNG 1 — giá trị p của khác biệt nợ có rủi ro:
         năm 0: 0,029 · năm 4: 0,002 (quy tắc chung)
         năm 0: 0,036 · năm 4: 0,003 (quy tắc nợ)
       ⚠ ở năm 1–3 khác biệt KHÔNG có ý nghĩa
       ═══════════════════════════════════════════════════════════
       ✔ quy tắc NỢ, CÁN CÂN, CHI TIÊU: kết quả tương tự
       ⚠ quy tắc THU: khác biệt yếu, khoảng tin cậy rộng
       ★ ĐỘ CHẶT của quy tắc (chỉ số Acalin, chỉ nước có quy tắc): chặt
         → nợ có rủi ro giảm ~2 điểm ngay, ~2,5 trung hạn; lỏng → gần 0
       ★ cơ chế: có quy tắc thì MẤT SẢN LƯỢNG ÍT HƠN (Phụ lục B)
```

### Nợ ban đầu cao hay thấp

```text
       PHƯƠNG TRÌNH (5): hàm chuyển trơn F(z) = e^(−γz)/(1 + e^(−γz))
       z = nợ/GDP bình quân của nước, chuẩn hoá giữa các nước; γ = 5
       ═══════════════════════════════════════════════════════════
       ★★ HÌNH 8 (ước đọc)
       ┌──────────────────┬──────────────────┬───────────────────┐
       │                  │ NỢ CAO           │ NỢ THẤP           │
       ├──────────────────┼──────────────────┼───────────────────┤
       │ vị trí, năm 2    │ ★ ~−1,3          │ ~−0,5             │
       │ quy mô, năm 3    │ ★ ~−0,38         │ ~−0,07            │
       │ nợ có rủi ro,    │ ★ ~−2,0          │ ~−0,6             │
       │ năm 3            │                  │                   │
       └──────────────────┴──────────────────┴───────────────────┘
       → tác động lên nợ có rủi ro lớn khoảng BỐN LẦN (bài nêu), khác
         biệt có ý nghĩa 5% ở năm 3 (p = 0,014)
       ✔ γ = 2,5 hoặc 7; hoặc chia theo tứ phân vị nợ → tương tự
       ★ cơ chế: nợ cao → củng cố làm GIẢM MẠNH hơn độ bất định của
         sản lượng
       ═══════════════════════════════════════════════════════════
       CÁC NGUỒN KHÁC BIỆT KHÁC (không trình bày chi tiết)
       ★ nước PHÁT TRIỂN: nợ có rủi ro giảm ~3 điểm trung hạn, so với
         dưới 1 điểm ở nước mới nổi và đang phát triển
       mức phi chính thức thấp hơn, thể chế tốt hơn → mạnh hơn chút ít
       độ mở thương mại, chế độ tỷ giá, chu kỳ kinh tế, giai đoạn lãi
         suất bằng không, căng thẳng tài chính → KHÔNG khác biệt
```

## Ba câu hỏi bài viết trả lời

1. Cắt chi tiêu chính phủ tác động thế nào lên toàn bộ phân phối nợ công tương lai, không chỉ mức bình quân mà cả độ bất định và đuôi rủi ro?
2. Củng cố làm nợ giảm qua những kênh nào: cán cân ngân sách, tăng trưởng, lạm phát hay lãi suất?
3. Khi nào củng cố hiệu quả nhất trong việc giảm rủi ro nợ: khi có quy tắc tài khoá, khi nợ ban đầu cao, hay ở nhóm nước nào?

## Khái niệm cần biết

**Củng cố tài khoá (fiscal consolidation).** Các biện pháp làm giảm thâm hụt ngân sách, bằng cắt chi, tăng thu, hoặc cả hai, thường nhằm kéo nợ công xuống. Bài chỉ xét củng cố bằng **cắt chi**. Ví dụ minh hoạ: một nước có GDP 500 tỷ USD cắt chi 5 tỷ USD trong năm là cắt chi 1% GDP, đúng quy mô cú sốc mà bài dùng để báo cáo kết quả.

**Phân phối nợ và nợ có rủi ro (debt-at-risk).** Vì tương lai bất định, nợ/GDP của một nước sau vài năm không phải một con số chắc chắn mà là một dải các khả năng, có khả năng cao, khả năng thấp; dải này gọi là phân phối dự báo. Nợ có rủi ro là **phân vị thứ 95** của phân phối đó: chỉ có 5% khả năng nợ cao hơn mức này. Ví dụ: với nợ công toàn cầu năm 2027, trung vị dự báo khoảng 97,5% GDP nhưng phân vị 95 khoảng 116,6% GDP. Nợ có rủi ro cho biết kịch bản xấu nghiêm trọng trông như thế nào, và đó là điều quyết định nguy cơ khủng hoảng.

**Phân vị và đuôi phân phối.** Phân vị τ là mức mà τ% các kết cục nằm dưới nó. Phân vị 5 là "đuôi trái" (kết cục nợ rất thấp, tức tình huống thuận lợi), phân vị 95 là "đuôi phải" (kết cục nợ rất cao). Bài quan tâm đuôi phải vì khủng hoảng nợ xảy ra ở đó, không phải ở mức bình quân.

**Vị trí và quy mô (location and scale).** Hai cách một chính sách có thể tác động lên phân phối. Tác động vị trí là **dịch** cả phân phối sang trái hay phải (thay đổi mức bình quân). Tác động quy mô là **co hoặc giãn** độ rộng phân phối (thay đổi độ bất định). Ví dụ minh hoạ: nếu trước cắt chi, nợ năm sau có thể từ 80% đến 120% GDP, thì một tác động vị trí −1 điểm đưa dải thành 79–119%, còn thêm tác động quy mô âm có thể đưa nó thành 80–117%: đầu cao bị kéo xuống mạnh hơn đầu thấp. Bài thấy cắt chi làm cả hai việc.

**Cú sốc chi tiêu và sai số dự báo.** Để đo tác động nhân quả, cần một thay đổi chi tiêu không phải do chính tình hình kinh tế gây ra. Bài lấy phần chi tiêu thực tế khác với dự báo mà IMF công bố tháng 10 cùng năm: phần chênh lệch này là thứ không ai lường trước. Ví dụ minh hoạ: IMF dự báo chi 30% GDP, thực tế 29% GDP, thì cú sốc là −1% GDP. Cách làm này tránh lẫn lộn kiểu "kinh tế suy thoái nên chi tăng".

**Phép chiếu địa phương (local projections).** Kỹ thuật ước lượng tác động của một cú sốc ở từng chân trời riêng: hồi quy nợ năm nay lên cú sốc, rồi nợ năm sau lên cú sốc, và cứ thế đến năm thứ 4. Kết quả là một chuỗi tác động theo thời gian (h = 0…4), ví dụ nợ bình quân giảm khoảng 0,65 điểm ngay năm 0 và khoảng 0,9 điểm ở năm 2.

**Số nhân tài khoá (fiscal multiplier).** Mỗi đồng chi tiêu chính phủ thay đổi làm GDP thay đổi bao nhiêu đồng. Ví dụ: số nhân 0,3 nghĩa là cắt chi 1 tỷ làm GDP giảm 0,3 tỷ. Nếu số nhân lớn hơn 1, cắt chi có thể làm GDP giảm mạnh đến mức nợ/GDP lại tăng; bài thấy số nhân khoảng 0,2–0,4, tức củng cố không tự thất bại.

**Quy tắc tài khoá (fiscal rule).** Giới hạn bằng con số, áp dụng lâu dài, lên các tổng số ngân sách, ví dụ "nợ không vượt 60% GDP" hay "thâm hụt không quá 3% GDP". Quy tắc giúp hạn chế động cơ chính trị muốn chi nhiều và xu hướng thâm hụt kéo dài, qua đó làm lời hứa củng cố đáng tin hơn. Bài thấy cắt chi ở nước có quy tắc giảm nợ có rủi ro khoảng 2 điểm, so với khoảng 0,5 điểm không có ý nghĩa ở nước không có quy tắc.

## Nội dung chi tiết

### 1. Mở đầu

Nợ công đã ở mức cao: bình quân thế giới khoảng 93% GDP cuối 2024 và dự kiến tiến tới gần 100% GDP vào cuối thập kỷ. Rủi ro lại nghiêng về phía tăng. Theo phân phối dự báo cho năm 2027 của Furceri và cộng sự (2025), trung vị khoảng 97,5% GDP, nhưng phân vị 95 khoảng 116,6% GDP (tức khoảng 117% GDP), cao hơn trung vị khoảng 20 điểm phần trăm, một mức chênh chưa thấy kể từ Thế chiến II. Nợ cao và nợ có rủi ro cao làm thu hẹp dư địa tài khoá và thường báo trước căng thẳng nợ chủ quyền.

Nhiều nước cần củng cố tài khoá để giảm nợ, đồng thời phải đáp ứng áp lực chi mới cho khí hậu, quốc phòng và phát triển. Củng cố bao nhiêu là đủ phụ thuộc vào việc củng cố tác động lên nợ thế nào theo thời gian. Thế nhưng quan hệ giữa củng cố và nợ, nhất là **rủi ro** nợ, chưa được nghiên cứu nhiều. Các nghiên cứu trước (Guajardo, Leigh và Pescatori; Alesina, Favero và Giavazzi…) chủ yếu hỏi củng cố tác động thế nào lên **tăng trưởng**. Bài này hỏi củng cố tác động thế nào lên **toàn bộ phân phối nợ tương lai**, nhất là đuôi phải.

Bài chọn xét **cắt chi** vì ba lý do: cú sốc chi tiêu nhận diện được cho nhiều nước; chi tiêu không bị chu kỳ kinh tế chi phối tự động như thu (thu thuế tự giảm khi suy thoái); và các nghiên cứu (Alesina và cộng sự 2019) cho thấy củng cố dựa vào cắt chi giảm nợ hiệu quả hơn củng cố dựa vào tăng thuế.

Về phương pháp, bài đưa mô hình vị trí–quy mô vào khung phép chiếu địa phương để ước lượng phản ứng ở các phân vị khác nhau của phân phối nợ. Mẫu gồm 192 nước, 1991–2021.

### 2. Vị trí trong tài liệu

Bài nối hai nhánh nghiên cứu.

**Nhánh thứ nhất: quan hệ giữa hành động tài khoá và nợ.** Reinhart, Reinhart và Rogoff bàn các lựa chọn giảm nợ (tăng trưởng, củng cố, lạm phát, vỡ nợ, kìm hãm tài chính). Kose và cộng sự tập trung vào nước đang phát triển. Ando và cộng sự dùng mô hình SVAR với ràng buộc dấu cho 58 nước và thấy bằng chứng lẫn lộn về việc củng cố có giảm được nợ hay không. Đóng góp của bài: mẫu lớn hơn nhiều, và cách nhận diện cú sốc vừa không dự báo được vừa ngoại sinh.

**Nhánh thứ hai: tác động của cú sốc chính sách lên rủi ro tăng trưởng và nợ.** Các bài trước xét cú sốc tiền tệ, hoặc cú sốc tin tức về chi tiêu ở Mỹ. Bài này tập trung vào chính sách tài khoá, với mẫu lớn và đa dạng. Bài xây trên khái niệm nợ có rủi ro của Furceri và cộng sự (2025), nhưng chuyển từ mô tả rủi ro sang đo **tác động nhân quả** của chính sách lên rủi ro.

### 3. Dữ liệu và phương pháp

**Dữ liệu.** Số liệu năm lấy từ bản tháng 10 của Triển vọng Kinh tế Thế giới (WEO), gồm nợ, chi, thu, cán cân ngân sách, lãi suất dài hạn thực, lạm phát, GDP, và các dự báo trong năm. Số nước và giai đoạn bị giới hạn bởi dữ liệu dự báo chi tiêu.

**Mô hình vị trí–quy mô.** Với mỗi chân trời h = 0…4 năm, phương trình (1) có dạng:

d(t+h) = α(i) + β₁·g(t) + X'β₂ + [δ(i) + γ₁·g(t) + X'γ₂]·ε

trong đó d là nợ/GDP, g là chi tiêu chính phủ/GDP, X là các biến kiểm soát, ε là sai số. Phần đầu (α, β) là phần **vị trí**: nó quyết định mức bình quân. Phần trong ngoặc vuông (δ, γ) là phần **quy mô**: nó nhân với sai số, nên quyết định độ rộng của phân phối.

Tác động của chi tiêu lên phân vị τ bằng β₁ + γ₁·q(τ), với q(τ) là nghịch đảo hàm phân phối của sai số tại τ (âm ở các phân vị thấp, dương ở các phân vị cao). Ba trường hợp:

| Trường hợp | Ý nghĩa |
|---|---|
| γ₁ = 0 | Chỉ dịch phân phối, mọi phân vị bị tác động như nhau (giống phép chiếu địa phương tuyến tính thông thường) |
| β và γ cùng dấu | Vừa dịch vừa giãn hoặc co, nên đuôi phải chịu tác động mạnh nhất |
| β và γ ngược dấu | Dịch, nhưng đuôi trái chịu tác động nhiều hơn |

Tác động của **cắt** chi bằng cách nhân cả hai hệ số với −1. Bài ước lượng cho các phân vị từ 5 tới 95 và tập trung vào phân vị 95.

**Vì sao không dùng hồi quy phân vị thông thường.** Với dữ liệu bảng, thêm biến giả cho từng nước vào hồi quy phân vị gây ra "vấn đề tham số ngẫu nhiên" (số tham số tăng theo số nước, làm ước lượng sai lệch). Mô hình của Machado và Santos Silva (2019) tránh được điều này và cho phép đặc điểm riêng của từng nước tác động lên **cả** phân phối, không chỉ dịch vị trí. Ước lượng bằng GMM một bước (lệnh MM-QR trong Stata), sai số chuẩn theo cụm nước.

**Nhận diện cú sốc chi tiêu.** Cú sốc là phần chi tiêu **không dự báo được**. Theo định lý Frisch–Waugh–Lovell, đưa các biến dự báo vào X tương đương với dùng g̃ = g − E(g | X), tức chi tiêu trừ đi phần kỳ vọng. Hai nhóm biến kiểm soát:
- Dự báo chi tiêu của IMF công bố tháng 10 cùng năm. Nhờ đó cú sốc chỉ gồm phần chi không lường trước. Để một phản ứng theo chu kỳ lọt vào cú sốc, nó phải xảy ra trong tháng 10–12, điều khó xảy ra do độ trễ lập pháp (theo lập luận của Blanchard và Perotti).
- Dự báo tháng 10 về tăng trưởng và lạm phát, cùng các giá trị trễ của nợ, chi tiêu, tăng trưởng và lạm phát (theo Colombo và cộng sự 2024).

**Vì sao không dùng cách nhận diện khác:**

| Cách khác | Vấn đề |
|---|---|
| SVAR kiểu Blanchard–Perotti | Cần dữ liệu quý, nhiều nước không có |
| Phương pháp tường thuật (đọc tài liệu ngân sách để xác định thay đổi có chủ đích) | Thiếu tài liệu ở nước mới nổi |
| Dùng chi quân sự | Dính vấn đề "tầm nhìn tài khoá": người dân phản ứng ngay từ khi biết trước, trước khi tiền được chi |

**Cú sốc có ngoại sinh không.** Cú sốc đạt cả ba tiêu chí của Ramey (2016): không tương quan với các biến vĩ mô hiện tại và quá khứ, cũng như với sai số dự báo của chúng (tóm bằng thành phần chính thứ nhất); không dự báo được, vì được xây từ chính sai số dự báo; và không tương quan với chỉ số Bất định Thế giới hay với cú sốc tiền tệ. Thống kê mô tả của cú sốc: bình quân xấp xỉ 0, độ lệch chuẩn 3,3, khoảng tứ phân vị từ −1,4% đến +1,1% GDP.

**Vì sao không dùng cú sốc làm biến công cụ trong hồi quy phân vị.** Ước lượng biến công cụ theo phân vị trên dữ liệu bảng đòi hỏi hiệu ứng cố định giống nhau giữa các phân vị, và chỉ xử lý được phương sai thay đổi, không xử lý được tương quan chuỗi mà phép chiếu địa phương tạo ra. Vì vậy bài đưa dự báo vào làm biến kiểm soát thay vì dùng công cụ trong mô hình chính.

### 4. Kết quả cơ sở

**Cắt chi giảm cả mức nợ lẫn độ bất định.** Tác động của việc cắt chi 1% GDP lên nợ/GDP (điểm phần trăm, giá trị ước đọc):

| Năm | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| Vị trí (bình quân) | khoảng −0,65 | khoảng −0,8 | khoảng −0,9 | khoảng −0,78 | khoảng −0,55 |
| Quy mô (độ bất định) | khoảng −0,11 | khoảng −0,1 | khoảng −0,2 | khoảng −0,3 | khoảng −0,2 |

Cả hai tham số đều âm và có ý nghĩa ở mọi chân trời. Nợ bình quân giảm khoảng 0,7 điểm ngay và đạt đỉnh 0,9 điểm sau hai năm. Tính theo độ lớn tương đối, một cú sốc bằng một độ lệch chuẩn làm độ lệch chuẩn của nợ/GDP giảm khoảng 17% ngay lập tức và 23% sau hai năm.

**Tác động tăng dần theo phân vị** (giá trị ước đọc):

| Năm | Phân vị 5 (nợ thấp) | Phân vị 95 (nợ có rủi ro) |
|---|---|---|
| 0 | khoảng −0,45 | khoảng −0,95 |
| 2 | khoảng −0,5 | khoảng −1,35 |
| 3 | khoảng −0,2 | khoảng −1,5 |
| 4 | khoảng −0,2 (mất ý nghĩa thống kê từ năm 2) | khoảng −1,0 |

Ở mọi chân trời, đường tác động dốc xuống theo phân vị: càng về đuôi phải, tác động càng lớn. Ở đuôi trái tác động nhỏ và mất ý nghĩa sau hai năm; ở đuôi phải tác động lớn và bền. Tóm lại, cắt chi 1% GDP làm nợ có rủi ro giảm khoảng 1 điểm trong ngắn hạn và 1,5 điểm trong trung hạn. Cách đọc: cắt chi không chỉ đẩy phân phối sang trái mà còn làm nó **hẹp** lại, nên các kết cục nợ rất cao ít xảy ra hơn.

**Đối chiếu với khuyến nghị chính sách.** Báo cáo Fiscal Monitor 2024 của IMF khuyến nghị điều chỉnh tích luỹ 3–4,5% GDP. Theo ước lượng của bài, mức điều chỉnh đó sẽ làm nợ có rủi ro giảm khoảng 4,5–7 điểm.

**Độ vững.** Các kiểm tra đều cho kết quả tương tự:
- Dùng 1, 3 hoặc 4 độ trễ thay vì 2: gần như không đổi.
- Bỏ giá trị cực đoan (dưới phân vị 1 và trên phân vị 99) của nợ, của chi tiêu, hoặc cả hai: tương tự.
- Thay chi tiêu bằng **cán cân** tài khoá làm biến xung động: tác động vị trí tương tự, nhưng tác động quy mô yếu hơn, nên ít bất đối xứng hơn; bất đối xứng vẫn còn ở năm 3–4.
- Phương pháp Canay (2011), loại hiệu ứng cố định trước rồi chạy hồi quy phân vị: ít bất đối xứng hơn nhưng đường tác động vẫn dốc xuống theo phân vị.
- Hồi quy phân vị biến công cụ của Chernozhukov và Hansen (2006), với công cụ là sai số dự báo tăng chi thực đã làm sạch: tương tự về định tính.

### 5. Cơ chế

Theo phương trình động thái nợ, tỷ lệ nợ/GDP thay đổi theo cán cân sơ cấp, lãi suất, tăng trưởng và lạm phát. Bài xét từng kênh.

**Ngân sách** (giá trị ước đọc):
- **Cán cân**: tác động vị trí +0,7 điểm ngay rồi giảm dần; tác động quy mô âm. Nghĩa là củng cố cải thiện cán cân tương lai và giảm độ bất định của nó, tức giảm rủi ro xảy ra thâm hụt lớn.
- **Chi**: tác động vị trí −1 điểm ngay (đúng quy mô cú sốc), rồi hồi dần.
- **Thu**: cũng giảm (khoảng −0,27 điểm ngay) vì sản lượng và lạm phát thấp hơn làm cơ sở thuế co lại. Đây là lý do cán cân chỉ cải thiện khoảng 0,7 chứ không phải trọn 1 điểm.

**Vĩ mô:**
- **Lạm phát** giảm nhẹ, đỉnh sau hai năm; tác động quy mô không đổi.
- **GDP**: số nhân chi tiêu âm và nhỏ hơn 1 (khoảng 0,2–0,4), phù hợp với tài liệu. Nghĩa là củng cố không gây mất sản lượng đủ lớn để tự triệt tiêu nỗ lực giảm nợ. Tác động quy mô cũng âm, tức củng cố làm giảm độ bất định của sản lượng.
- **Lãi suất dài hạn** giảm, rõ từ năm 2 (khoảng −0,35 điểm), phù hợp với lý thuyết tân cổ điển: điều kiện tín dụng tốt hơn kéo đầu tư tư nhân vào. Độ bất định của lãi suất cũng giảm tới năm 3, có thể qua kênh phần bù rủi ro (nhà đầu tư đòi lãi thấp hơn khi thấy nợ an toàn hơn).

**Phân rã sau một năm.** Nợ bình quân giảm 0,8 điểm, trong đó khoảng 0,55 điểm (khoảng 70%) nhờ cán cân cải thiện; phần còn lại đến qua tăng trưởng và lãi suất.

### 6. Khác biệt theo điều kiện

**Quy tắc tài khoá.** Quy tắc tài khoá là giới hạn bằng số, lâu dài, lên các tổng số ngân sách, giúp giảm méo mó chính trị và xu hướng thâm hụt kéo dài. Chúng có thể làm củng cố đáng tin hơn và giảm nguy cơ trượt tài khoá. Dữ liệu lấy từ Acalin và cộng sự (2025): 106 nước từng có quy tắc tài khoá trong 1985–2024; biến giả R = 1 nếu nước đó có quy tắc trong năm. Phương trình (4) cho mọi hệ số tách riêng theo hai trạng thái có và không có quy tắc.

Kết quả với quy tắc nói chung (giá trị ước đọc):

| Chỉ tiêu | Có quy tắc | Không quy tắc |
|---|---|---|
| Vị trí, trung hạn | −1,2 | dưới −0,5 |
| Quy mô, năm 0 | khoảng −0,27 | khoảng 0 |
| Nợ có rủi ro, năm 4 | khoảng −1,9 (khoảng 2 điểm) | khoảng −0,5, không có ý nghĩa |

Giá trị p của khác biệt về nợ có rủi ro giữa hai trạng thái: với quy tắc chung, 0,029 ở năm 0 và 0,002 ở năm 4; với quy tắc nợ, 0,036 ở năm 0 và 0,003 ở năm 4. Ở năm 1–3, khác biệt không có ý nghĩa thống kê.

Theo loại quy tắc: quy tắc nợ, quy tắc cán cân và quy tắc chi tiêu cho kết quả tương tự; quy tắc thu cho khác biệt yếu với khoảng tin cậy rộng. Theo độ chặt của quy tắc (chỉ số của Acalin, chỉ xét các nước có quy tắc): quy tắc chặt làm nợ có rủi ro giảm khoảng 2 điểm ngay và khoảng 2,5 điểm trong trung hạn; quy tắc lỏng cho tác động gần 0. Cơ chế được đề xuất: ở nước có quy tắc, củng cố làm **mất sản lượng ít hơn**.

**Nợ ban đầu cao hay thấp.** Nợ ban đầu là yếu tố quan trọng quyết định mức phơi nhiễm với rủi ro nợ. Phương trình (5) dùng hàm chuyển trơn F(z) = e^(−γz)/(1 + e^(−γz)), với z là nợ/GDP bình quân của nước đó, chuẩn hoá giữa các nước, và γ = 5. Hàm này cho mỗi quan sát một trọng số từ 0 đến 1 giữa trạng thái "nợ cao" và "nợ thấp" thay vì chia cứng.

| Chỉ tiêu (giá trị ước đọc) | Nợ cao | Nợ thấp |
|---|---|---|
| Vị trí, năm 2 | khoảng −1,3 | khoảng −0,5 |
| Quy mô, năm 3 | khoảng −0,38 | khoảng −0,07 |
| Nợ có rủi ro, năm 3 | khoảng −2,0 | khoảng −0,6 |

Ở nước nợ cao, củng cố giảm cả vị trí lẫn quy mô mạnh hơn, và theo bài, tác động lên nợ có rủi ro lớn khoảng bốn lần. Khác biệt có ý nghĩa ở mức 5% ở năm 3 (p = 0,014). Kết quả vững khi dùng γ = 2,5 hoặc 7, hoặc khi chia mẫu theo tứ phân vị nợ. Cơ chế: ở nước nợ cao, củng cố làm giảm mạnh hơn độ bất định của sản lượng.

**Các nguồn khác biệt khác** (bài không trình bày chi tiết):
- **Nước phát triển** hưởng lợi nhiều hơn: nợ có rủi ro giảm khoảng 3 điểm trong trung hạn, so với dưới 1 điểm ở nước mới nổi và đang phát triển. Khác biệt chủ yếu đến từ tác động vị trí lớn hơn, nhất quán với việc nước phát triển thường có quy tắc mạnh hơn và nợ cao hơn, và với bằng chứng rằng thâm hụt sơ cấp là động lực rủi ro nợ quan trọng hơn ở nhóm này.
- Mức phi chính thức thấp hơn và thể chế tốt hơn: tác động mạnh hơn chút ít.
- Độ mở thương mại, chế độ tỷ giá, giai đoạn của chu kỳ kinh tế, giai đoạn lãi suất bằng không, căng thẳng tài chính: không tạo khác biệt.

### 7. Kết luận và hàm ý

Cắt chi tiêu dịch phân phối nợ tương lai sang trái và thu hẹp nó. Tác động bất đối xứng: gần như không đáng kể ở đuôi trái (các kịch bản thuận lợi) nhưng lớn, bền và có ý nghĩa ở đuôi phải (các kịch bản nợ tăng vọt). Nói cách khác, giá trị lớn nhất của củng cố là bảo hiểm trước kịch bản xấu, chứ không chỉ kéo mức bình quân xuống.

Hàm ý chính sách:
- Nước có nợ rất cao nên cân nhắc củng cố dựa vào chi tiêu để giảm rủi ro nợ tăng vọt, vì chính trong bối cảnh này củng cố hiệu quả nhất (tác động lên nợ có rủi ro lớn khoảng bốn lần so với nước nợ thấp).
- Củng cố nên được đặt trong một khuôn khổ trung hạn đáng tin cậy, dẫn dắt bởi quy tắc tài khoá. Quy tắc làm tăng uy tín và hiệu quả của củng cố trong việc giảm rủi ro nợ (khoảng 2 điểm so với khoảng 0,5 điểm không có ý nghĩa).

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Fiscal consolidation | Củng cố tài khoá |
| Expenditure-based consolidation | Củng cố dựa vào cắt chi |
| Debt-at-risk | Nợ có rủi ro, phân vị thứ 95 của phân phối nợ/GDP dự báo |
| Location-scale model | Mô hình vị trí–quy mô của Machado và Santos Silva |
| Location effect | Tác động vị trí, lên mức bình quân |
| Scale effect | Tác động quy mô, lên độ phân tán hay độ bất định |
| Conditional quantile | Phân vị có điều kiện |
| Right tail, left tail | Đuôi phải (nợ cao), đuôi trái (nợ thấp) |
| Incidental parameters problem | Vấn đề tham số ngẫu nhiên khi thêm hiệu ứng cố định vào hồi quy phân vị |
| Local projections | Phép chiếu địa phương của Jordà |
| Forecast error | Sai số dự báo, dùng để nhận diện cú sốc chi tiêu |
| Fiscal foresight | Tầm nhìn tài khoá, người dân phản ứng trước khi chính sách thực hiện |
| Narrative approach | Phương pháp tường thuật, nhận diện cú sốc từ tài liệu chính sách |
| Frisch-Waugh-Lovell theorem | Định lý cho phép hiểu cú sốc là phần dư sau khi chiếu lên biến kiểm soát |
| Fiscal multiplier | Số nhân tài khoá |
| Crowding-in | Kéo đầu tư tư nhân vào |
| Risk-premium channel | Kênh phần bù rủi ro |
| Fiscal rule | Quy tắc tài khoá: nợ, cán cân, chi tiêu, thu |
| Fiscal rule stringency index | Chỉ số độ chặt của quy tắc tài khoá |
| Smooth transition function | Hàm chuyển trơn giữa hai trạng thái |
| Instrumental variable quantile regression | Hồi quy phân vị biến công cụ |
| Fiscal slippage | Trượt tài khoá, không đạt mục tiêu đã đề ra |

## Câu nói đáng nhớ

> "Fiscal expenditure consolidations not only shift the distribution of public debt-to-GDP to the left but also diminish its scale, thereby making instances of very high public debt realizations less likely."

> "Fiscal consolidations, on average, do not generate output losses of sufficient size to render efforts to lower public debt ratios self-defeating."

> "High public debt ratios require stabilization and consolidation of public spending is even more effective in reducing debt in this context."

## Đánh giá và phát hiện đáng chú ý

### Sản phẩm thật của củng cố tài khoá là bảo hiểm, không phải giảm nợ

Đây là cách đọc lại toàn bộ bài mà chính bài không đưa ra, dù mọi con số đều chỉ về đó.

Nếu chỉ nhìn tác động bình quân, kết quả khá đáng thất vọng: cắt chi 1% GDP chỉ làm nợ/GDP giảm khoảng 0,7 điểm ngay và 0,9 điểm ở đỉnh sau hai năm. Tức là **bỏ ra một đồng để giảm được chưa tới một đồng nợ**, sau khi đã tính cả các hiệu ứng vòng hai. Trên bàn nghị trường, đó là một lập luận yếu: người ta cắt một điểm phần trăm GDP chi tiêu công, chịu toàn bộ cái giá chính trị, để đổi lấy chưa đầy một điểm nợ.

Nhưng ở phân vị 95, cùng một hành động làm nợ có rủi ro giảm khoảng 1,5 điểm ở trung hạn, trong khi ở phân vị 5 tác động chỉ khoảng 0,2 điểm và **mất ý nghĩa thống kê từ năm thứ hai**. Đường tác động dốc xuống đều theo phân vị.

Đó là chân dung của một hợp đồng bảo hiểm, không phải của một khoản thanh toán nợ. Cái mà củng cố mua được không phải là một mức nợ thấp hơn — nó mua sự biến mất của các kịch bản xấu. Với một nước đã ở vùng an toàn, phí bảo hiểm này gần như không mang lại gì, đúng như đuôi trái của bài cho thấy. Với một nước ở vùng nguy hiểm, nó mới đáng tiền.

Phát biểu lại như vậy thay đổi cả cách tranh luận. Câu hỏi không còn là "cắt chi có giảm nợ không" (có, nhưng ít), mà là "**phí bảo hiểm này có rẻ hơn thiệt hại của kịch bản xấu nhân với xác suất của nó hay không**" — và câu trả lời phụ thuộc hoàn toàn vào việc nước đó đang đứng ở đâu trên phân phối.

### Bài áp lăng kính phân phối lên chính phủ và chỉ dùng lăng kính bình quân cho mọi người khác

Đây là điểm mù nghiêm trọng nhất, và nó mang tính cấu trúc chứ không phải sơ suất.

Toàn bộ cải tiến phương pháp của bài nằm ở chỗ: đừng chỉ nhìn giá trị bình quân, hãy nhìn cả đuôi phân phối, vì các kết cục cực đoan mới là thứ quan trọng. Lập luận này hoàn toàn đúng. Nhưng nó chỉ được áp cho **một biến duy nhất: tỷ lệ nợ công trên GDP**.

Cái giá của củng cố thì được đo bằng đúng một con số bình quân: số nhân tài khoá âm và nhỏ hơn 1, khoảng 0,2–0,4. Không có phân vị 95 của mất việc làm. Không có đuôi phải của tỷ lệ nghèo. Không có phân phối tác động theo nhóm thu nhập hộ gia đình. Chính lập luận mà bài dùng để biện minh cho sự tồn tại của mình — rằng bình quân che mất rủi ro ở đuôi — lại không được áp dụng cho bên chịu chi phí.

Và sự bất đối xứng này không trung lập. Một đợt cắt chi 1% GDP không phải là cắt đều 1% mọi khoản. Nó rơi vào những dòng ngân sách dễ cắt nhất về mặt chính trị: trợ cấp, tuyển dụng công, đầu tư mới, và các chương trình có người thụ hưởng phân tán, không có tổ chức. Nói cách khác, **chính phủ mua bảo hiểm cho đuôi rủi ro của bảng cân đối của mình, và trả phí bằng cách đẩy rủi ro vào đuôi trái của phân phối thu nhập hộ gia đình**.

Bài không phải sai khi không nghiên cứu điều đó — nó không đặt câu hỏi ấy. Nhưng kết luận chính sách ở phần cuối thì được viết như thể phép tính lợi ích–chi phí đã hoàn tất, trong khi một nửa của phép tính chưa được làm.

### Bài không phân biệt cắt chi thường xuyên với cắt đầu tư — và đó là phân biệt quan trọng nhất trong thư mục này

Cú sốc được nhận diện là sai số dự báo của **tổng chi tiêu chính phủ**. Không có phân tách giữa chi thường xuyên và chi đầu tư.

Với một tài liệu nằm trong thư mục Đầu tư công và Nợ công, đây là một khoảng trống lớn, vì nó đụng thẳng vào kết quả của một tài liệu khác cùng thư mục. Nhánh nghiên cứu về nợ và tăng trưởng kết luận rằng nợ cao làm tăng trưởng chậm **chủ yếu qua kênh vốn trên mỗi lao động**, không qua năng suất nhân tố tổng hợp. Nếu đúng vậy, thì một đợt củng cố thực hiện bằng cách cắt đầu tư công sẽ đồng thời làm hai việc trái ngược: giảm nợ có rủi ro hôm nay, và làm suy yếu chính cỗ máy sẽ phải trả khoản nợ còn lại.

Điều này không phải khả năng lý thuyết. Kinh nghiệm thực tế rất thống nhất: khi cần cắt gấp, dòng đầu tư công gần như luôn bị cắt trước, vì nó không tạo ra người mất việc ngay, không phải sửa luật, và hệ quả chỉ hiện ra sau nhiều năm. Một nghiên cứu gộp mọi loại chi vào một biến sẽ ghi nhận cả hai kiểu củng cố là như nhau.

Có một dấu hiệu trong chính dữ liệu của bài đáng chú ý ở đây: số nhân chỉ 0,2–0,4, tức nhỏ một cách đáng ngạc nhiên so với nhiều ước lượng khác. Một trong những lời giải thích khả dĩ là phần lớn biến động chi tiêu không dự báo được thực ra nằm ở **chi đầu tư**, nơi độ trễ giữa quyết định chi và tác động lên cầu là dài nhất, nên tác động ngắn hạn lên sản lượng nhỏ. Nếu vậy thì con số 0,2–0,4 không phải bằng chứng rằng củng cố ít tốn kém; nó là bằng chứng rằng chi phí đã được **dời sang tương lai** và nằm ngoài chân trời bốn năm của mô hình.

### Sai số dự báo chi tiêu có thể đang đo việc không giải ngân được, chứ không phải quyết định củng cố

Cú sốc được xây bằng cách lấy chi tiêu thực tế trừ đi dự báo tháng 10 của IMF cho chính năm đó. Bài kiểm tra ba tiêu chí ngoại sinh của Ramey và vượt qua, nên vấn đề không phải là nội sinh theo nghĩa thông thường.

Vấn đề là **ý nghĩa kinh tế của sai số âm**. Chi tiêu thấp hơn dự báo có thể đến từ ít nhất bốn nguồn rất khác nhau: một quyết định chính sách thắt chặt ngoài dự kiến; một sai sót dự báo của chính IMF; một cú sốc làm nhu cầu chi giảm; hoặc — phổ biến nhất ở các nước đang phát triển — **không giải ngân hết được kế hoạch**. Dự toán được duyệt, tiền được bố trí, nhưng thủ tục đấu thầu chậm, giải phóng mặt bằng vướng, năng lực chủ đầu tư yếu, và cuối năm tiền không tiêu hết.

Bốn sự kiện này giống hệt nhau trong dữ liệu và hoàn toàn khác nhau về bản chất. Ba cái đầu là chính sách; cái thứ tư là năng lực hành chính. Và nếu một phần đáng kể "củng cố tài khoá" trong mẫu 192 nước thực ra là chậm giải ngân đầu tư công, thì kết luận của bài phải được đọc lại: nó nói rằng chi tiêu không thực hiện được làm giảm nợ có rủi ro — điều đúng về mặt hạch toán, nhưng không phải là một khuyến nghị chính sách, và chắc chắn không phải là một thành tựu.

Điều này cũng cho một cách giải thích khác cho kết quả khác biệt nhóm nước: nợ có rủi ro giảm khoảng 3 điểm ở nước phát triển so với dưới 1 điểm ở nước mới nổi và đang phát triển. Bài quy cho việc nước phát triển có quy tắc tài khoá mạnh hơn và nợ cao hơn. Nhưng cũng nhất quán với khả năng rằng ở nước phát triển, sai số dự báo chi tiêu phản ánh quyết định chính sách thật, còn ở nước đang phát triển nó pha lẫn nhiều nhiễu hành chính hơn.

### Hai điểm yếu thống kê: ngoại suy tuyến tính và mẫu hình ý nghĩa của quy tắc tài khoá

Bài đối chiếu kết quả của mình với khuyến nghị của Fiscal Monitor về điều chỉnh tích luỹ 3–4,5% GDP, và kết luận nợ có rủi ro sẽ giảm khoảng 4,5–7 điểm. Đây là phép nhân tuyến tính hệ số của một cú sốc 1% GDP với 4,5.

Chính bài cung cấp con số cho thấy phép nhân này không an toàn. Phân bố cú sốc có khoảng tứ phân vị chỉ từ **−1,4% đến +1,1% GDP**. Nghĩa là biến thiên nhận dạng điển hình — nguồn gốc thực sự của các hệ số — là những cú sốc quanh một điểm phần trăm, xảy ra trong **một năm**. Một chương trình điều chỉnh 4,5% GDP tích luỹ qua nhiều năm là một sự kiện khác về chất: nó đòi hỏi duy trì ý chí chính trị nhiều năm liên tiếp, nó gây phản ứng kỳ vọng, và nó dễ bị đảo ngược giữa chừng.

Ngoài ra, chính bài đã chứng minh rằng tác động **không tuyến tính** theo bối cảnh — gấp bốn lần khi nợ ban đầu cao, gần bằng không khi không có quy tắc tài khoá. Một mô hình đã tìm thấy phi tuyến mạnh theo hai chiều thì khó biện minh cho việc ngoại suy tuyến tính theo chiều thứ ba, tức theo quy mô của chính cú sốc.

Khác biệt giữa nhóm có quy tắc và nhóm không có quy tắc được báo cáo là có ý nghĩa ở **năm 0** (p = 0,029) và **năm 4** (p = 0,002), nhưng **không có ý nghĩa ở năm 1, 2 và 3**.

Một hiệu ứng cấu trúc thật thường không có hình dạng như vậy. Nếu quy tắc tài khoá làm củng cố đáng tin hơn và do đó hiệu quả hơn, ta kỳ vọng khác biệt xuất hiện và lớn dần, chứ không phải xuất hiện, biến mất trong ba năm, rồi trở lại mạnh hơn bao giờ hết. Mẫu hình này cũng nhất quán với việc có hai hệ số ngẫu nhiên vượt ngưỡng trong một loạt năm phép kiểm định. Bài trình bày bảng giá trị p đầy đủ — điều rất đáng khen — rồi kết luận như thể khác biệt là liên tục.

Bên cạnh đó là vấn đề chọn lọc mà bài không xử lý. Nước có quy tắc tài khoá, và đặc biệt là nước duy trì được quy tắc **chặt**, không phải một mẫu ngẫu nhiên. Đó là những nước đã có sẵn đồng thuận chính trị về kỷ luật ngân sách, bộ máy tài chính đủ năng lực, và thường là thị trường trái phiếu đủ sâu để kỷ luật đó được thưởng. Biến giả "có quy tắc" gần như chắc chắn đang mang theo toàn bộ gói đặc tính đó. Cơ chế mà bài đề xuất — có quy tắc thì mất sản lượng ít hơn — chính nó cũng có thể là một biểu hiện khác của cùng gói đặc tính, chứ không phải một hệ quả của quy tắc.

Hàm ý thực tiễn vì thế phải khiêm tốn hơn nhiều so với câu kết của bài: **ban hành một quy tắc tài khoá không tự động mang lại hiệu ứng đo được ở đây**, vì cái tạo ra hiệu ứng có thể là điều kiện cho phép quy tắc tồn tại, chứ không phải bản thân văn bản quy tắc.

### Hệ số "gấp bốn lần", và vì sao củng cố không phải câu hỏi đúng với Việt Nam

Kết quả rằng củng cố hiệu quả hơn khoảng bốn lần ở nước nợ cao được bài dùng làm cơ sở cho khuyến nghị trung tâm: nước nợ rất cao nên củng cố, vì ở đó củng cố càng hiệu quả.

Cần tách hai thành phần. Một phần là hành vi: ở nước nợ cao, phần bù rủi ro lớn hơn nên việc củng cố hạ lãi suất dài hạn mạnh hơn, và bài đưa cơ chế này qua kết quả về giảm bất định sản lượng. Nhưng một phần khác thuần tuý là đòn bẩy số học. Với cùng một thay đổi về tốc độ tăng trưởng danh nghĩa hay lãi suất bình quân, một nước có nợ 120% GDP sẽ thấy tỷ lệ nợ trên GDP thay đổi gấp đôi so với một nước có nợ 60%. Thêm vào đó, nước nợ cao có phương sai nợ lớn hơn ngay từ đầu, nên phân vị 95 của họ nằm xa hơn và có nhiều dư địa để dịch chuyển hơn.

Điều này không bác bỏ kết luận, nhưng nó có nghĩa là con số "gấp bốn lần" không nên được hiểu là "hiệu lực chính sách cao gấp bốn lần". Và nó có một hệ quả ngược mà bài không nêu: với nước nợ thấp, tác động lên nợ có rủi ro chỉ khoảng 0,6 điểm — tức **gần như không có lý do nợ nào để củng cố**. Với những nước đó, nếu có lý do để cắt chi thì đó phải là lý do về hiệu quả phân bổ nguồn lực, không phải lý do về rủi ro nợ.

Nếu áp thẳng khung của bài, kết luận cho Việt Nam khá rõ và hơi ngược với trực giác thông thường. Với mức nợ công nằm ở nửa dưới của phân phối quốc tế và không có dấu hiệu nằm ở đuôi phải, **tác động của củng cố lên nợ có rủi ro sẽ thuộc nhóm nhỏ nhất** mà bài đo được. Khoản bảo hiểm ấy rẻ vì nó không bảo hiểm cho nhiều thứ.

Giá trị thực của tài liệu này với Việt Nam nằm ở ba chỗ khác.

**Thứ nhất là lời cảnh báo ngầm về thành phần của việc cắt.** Vì bài không phân biệt chi thường xuyên với chi đầu tư, nó không thể nói điều quan trọng nhất — nhưng chính sự im lặng đó là lời nhắc. Một chỉ tiêu bội chi được đáp ứng bằng cách chậm giải ngân đầu tư công sẽ hiện lên như một thành tựu củng cố trong mọi bảng thống kê, và như một tổn thất trong trữ lượng vốn mà không bảng nào ghi.

**Thứ hai là chỉ báo lãi suất dài hạn.** Bài tìm thấy củng cố làm lãi suất dài hạn thực giảm khoảng 0,35 điểm từ năm thứ hai, và diễn giải qua kênh phần bù rủi ro. Kênh này chỉ hoạt động khi thị trường thực sự đang định giá rủi ro chủ quyền. Ở một thị trường trái phiếu chính phủ do các định chế trong nước bị ràng buộc về quy định chi phối, lợi suất không phải một mức giá thị trường, nên kênh này hầu như không tồn tại — và do đó một trong hai nguồn tạo ra lợi ích của củng cố trong mô hình cũng không tồn tại. Đây là mối liên hệ trực tiếp với nhánh tài liệu về cơ cấu nợ và cơ sở nhà đầu tư trong cùng thư mục.

**Thứ ba là khái niệm nợ có rủi ro như một công cụ trình bày.** Việc báo cáo một phân phối dự báo nợ với phân vị 95 thay vì một con số trung tâm là một cải tiến rất đáng áp dụng trong các báo cáo bền vững nợ quốc gia. Nó buộc người đọc đối mặt với câu hỏi đúng — điều gì xảy ra nếu mọi thứ đi lệch cùng lúc — thay vì câu hỏi dễ chịu là kịch bản cơ sở trông thế nào.
