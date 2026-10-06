# Public Debt and Growth — Nợ công và tăng trưởng

**Nguồn:** IMF Working Paper WP/10/174, tháng 7/2010, Vụ Tài khoá.
**Tác giả:** Manmohan S. Kumar, Jaejoon Woo.
**Ý chính:** Sau khủng hoảng tài chính toàn cầu, nợ chính phủ các nước phát triển tăng vọt, làm dấy lên lo ngại nợ lớn sẽ **cản trở tích luỹ vốn và kéo tăng trưởng xuống**. Bài dùng bảng **38 nước phát triển và mới nổi có dân số trên 5 triệu, 1970–2007**, chia thành **tám giai đoạn năm năm không chồng lấn**, và đặc biệt chú ý tới các vấn đề ước lượng: **nhân quả ngược, nội sinh, giá trị ngoại lai**. Cách xử lý nhân quả ngược là dùng **nợ ĐẦU KỲ** để giải thích tăng trưởng **TIẾP THEO**. Kết quả từ nhiều phương pháp (OLS gộp, hồi quy bền vững, ước lượng giữa nhóm BE, hiệu ứng cố định FE, GMM hệ thống SGMM) đều cho quan hệ nghịch: **tăng 10 điểm phần trăm tỷ lệ nợ/GDP đầu kỳ đi kèm tăng trưởng GDP thực bình quân đầu người chậm lại khoảng 0,2 điểm phần trăm mỗi năm**, ở nước phát triển nhỏ hơn (khoảng 0,15). Có bằng chứng **phi tuyến**: chỉ mức nợ **trên 90% GDP** mới có tác động âm rõ rệt, và cùng một mức tăng tỷ lệ nợ thì càng ở mức nợ cao càng gây thiệt hại lớn. Phân rã tăng trưởng cho thấy tác động xấu **chủ yếu qua năng suất lao động**, mà nguyên nhân là **đầu tư giảm và vốn trên mỗi lao động tăng chậm lại**: tăng 10 điểm nợ đầu kỳ đi kèm đầu tư trong nước giảm khoảng **0,4 điểm phần trăm GDP**, tác động ở nước mới nổi gần gấp đôi nước phát triển.

> **Lưu ý:** bản PDF đầy đủ. Một số điểm không khớp trong bài:
> - Mục 5 lời văn viết hệ số nợ đầu kỳ theo BE "ổn định quanh **0,23 tới 0,26**"; theo các bảng phải là **0,023 tới 0,026** (sai dấu thập phân).
> - Mục 6 viết hệ số nợ đầu kỳ trong hồi quy sản lượng trên lao động "từ −0,013 tới **0,022**"; Bảng 7 cho **−0,022**, thiếu dấu trừ. Phụ lục 4 viết "từ −0,019 tới **−0,24**", phải là **−0,024**.
> - Sơ đồ bố cục ở Mục 1 nhảy từ Mục 5 sang **Mục 7**, bỏ qua Mục 6 về hạch toán tăng trưởng.
> - **Bảng 3, cột 4 (SGMM tiết giản) có giá trị p của kiểm định Arellano-Bond AR(2) là 0,01**, tức bác bỏ giả thuyết không có tự tương quan bậc hai, làm ước lượng đó mất hiệu lực. Bài không bình luận điểm này.
> - Bảng 6 lấy bình quân hệ số của **bốn nhóm nợ**, trong khi Bảng 5 chỉ có **ba nhóm**, nên không đối chiếu trực tiếp được. Hệ số nhóm dưới 30% là **dương** (0,022) dù Bảng 5 cho các giá trị gần 0 và không có ý nghĩa.
> - Bảng phụ lục 1 có **hai cột cùng ghi "Initial Debt between 30 and 60 percent of GDP"**; cột thứ hai theo mạch phải là "between 60 and 90".
> - Tiêu đề Bảng 6 ghi "Real per **Capital** GDP Growth" (lỗi chính tả). Mục lục ghi Bảng 5 là "Levels of Initial Debt", bảng thực tên "**Different** Levels of Initial Debt".
> - **Easterly (2001)** được dẫn ở chú thích 5 nhưng **không có trong danh mục tài liệu** (chỉ có Easterly 2005). Grilliches và Hausman ghi **1986** trong chú thích 12 nhưng **1987** trong danh mục. Fatas và Mihov (2003) bị liệt **hai lần**. Clements, Bhattacharya và Nguyen (2003) có trong danh mục nhưng không được dẫn.
> - Trang bản quyền bị lỗi khi số hoá: mã giấy hiện thành "WP/32I396", và tên **Carlo Cottarelli** trong lời cảm ơn bị mã hoá sai.
> Các số lấy từ hình là giá trị đọc trên hình.

## Sơ đồ

### Vấn đề đặt ra

```text
       BỐI CẢNH 2010
       nợ chính phủ nước phát triển tăng vọt sau khủng hoảng
       → lo ngại về tính bền vững tài khoá và tác động lên thị trường
       ❓ nợ lớn có làm chậm TĂNG TRƯỞNG TIỀM NĂNG không?
       ⚠ "có rất ít bằng chứng có hệ thống" về mức độ tác động
       ═══════════════════════════════════════════════════════════
       VÒNG XOÁY NGUY HIỂM
       nợ cao → tăng trưởng chậm → bền vững tài khoá xấu đi
              → càng cần điều chỉnh sớm và quyết liệt
       ═══════════════════════════════════════════════════════════
       BÀI NÀY ĐỨNG TRÊN HAI NHÁNH TÀI LIỆU
       ① nhánh LỚN về các yếu tố quyết định tăng trưởng trung và dài
          hạn (Barro–Sala-i-Martin 2003, Aghion–Durlauf 2005)
       ② nhánh HẸP về tác động của nợ NGOẠI lên tăng trưởng ở nước
          thu nhập thấp, qua chèn lấn và "debt overhang"
       ★ khoảng trống: nợ CÔNG ở nước PHÁT TRIỂN và MỚI NỔI
```

### Năm kênh truyền dẫn

```text
       NỢ CÔNG CAO → TĂNG TRƯỞNG DÀI HẠN THẤP QUA:
       ① lãi suất dài hạn cao hơn ······ Gale–Orszag 2003;
                                          Baldacci–Kumar 2010
       ② thuế gây méo mó trong tương lai  Barro 1979; Dotsey 1994
       ③ lạm phát ····················· Sargent–Wallace 1981;
                                          Barro 1995; Cochrane 2010
       ④ bất định về triển vọng, chính sách
       ⑤ mất dư địa chính sách tài khoá NGƯỢC chu kỳ → biến động cao
          hơn → tăng trưởng thấp hơn (Aghion–Kharroubi 2007; Woo 2009)
       ⚠ trường hợp cực đoan: khủng hoảng nợ kích hoạt khủng hoảng
         ngân hàng hoặc tiền tệ → khuếch đại (Burnside 2001;
         Hemming 2003)
       ═══════════════════════════════════════════════════════════
       QUAN ĐIỂM TRUYỀN THỐNG (Elmendorf–Mankiw 1999)
       ngắn hạn ··· nợ do thâm hụt KÍCH cầu và sản lượng
       ★ dài hạn ·· nợ CHÈN LẤN vốn và làm giảm sản lượng
       lý thuyết tăng trưởng: mô hình tân cổ điển → giảm TẠM THỜI
       trên đường chuyển tiếp; mô hình nội sinh → giảm VĨNH VIỄN
       (Saint-Paul 1992)
```

### Đối chiếu với Reinhart–Rogoff (2010)

```text
       ★ NGHIÊN CỨU MỞ ĐƯỜNG: tăng trưởng và lạm phát theo mức nợ,
         dữ liệu lịch sử dài (Mỹ từ 1790, 44 nước, ~200 năm)
       ┌────────────────────┬──────────────────────────────────────┐
       │ chênh tăng trưởng  │ nợ THẤP (<30% GDP) so nợ CAO (>90%)  │
       ├────────────────────┼──────────────────────────────────────┤
       │ nước phát triển    │ trung vị 2,6 điểm · bình quân 4,2    │
       │ nước mới nổi       │ trung vị 2,1 điểm                    │
       └────────────────────┴──────────────────────────────────────┘
       lạm phát: KHÔNG có quan hệ dương hệ thống với nợ ở nước phát
         triển; nhưng RÕ ở nước mới nổi
       ═══════════════════════════════════════════════════════════
       ⚠ HẠN CHẾ mà bài này khắc phục
       chỉ xét TƯƠNG QUAN · không kiểm soát các yếu tố khác của
         tăng trưởng · không xử lý NHÂN QUẢ NGƯỢC
       ═══════════════════════════════════════════════════════════
       NHÁNH "DEBT OVERHANG" (nợ ngoại, nước đang phát triển)
       Krugman 1988, Sachs 1989: nghĩa vụ trả nợ nặng → phần lớn
         sản lượng về tay chủ nợ ngoại → mất động lực đầu tư
       Imbs–Ranciere 2009; Pattillo–Poirson–Ricci 2002, 2004:
         phi tuyến, âm khi nợ > ~60% GDP, không ý nghĩa khi nợ thấp
       ⚠ Cordella–Ricci–Arranz 2005: chỉ thấy ở mức nợ TRUNG BÌNH,
         không ý nghĩa ở cả rất thấp lẫn rất cao
```

### Chiến lược ước lượng: mỗi công cụ một thiên lệch

```text
       PHƯƠNG TRÌNH CƠ SỞ (1), τ = 4 (kỳ năm năm)
       y(i,t) − y(i,t−τ) = α·y(i,t−τ) + X'(i,t−τ)β + γ·Z(i,t−τ)
                            + η(t) + ν(i) + ε(i,t)
       y = log GDP thực bình quân đầu người · Z = ★ NỢ CHÍNH PHỦ
         GỘP ĐẦU KỲ (% GDP) · ν = hiệu ứng cố định nước
       ═══════════════════════════════════════════════════════════
       BA NGUỒN THIÊN LỆCH
       ① BIẾN BỊ BỎ SÓT (thiên lệch dị biệt): ν tương quan với biến
          giải thích → hại OLS gộp và BE
       ② NỘI SINH: biến giải thích tương quan với sai số → hại OLS
          gộp, BE, FE. Riêng bảng động còn có ★ THIÊN LỆCH BẢNG ĐỘNG
          làm FE không vững và lệch XUỐNG
       ③ SAI SỐ ĐO LƯỜNG: hại cả ba, nhưng NẶNG ở FE và NHẸ ở BE
       ═══════════════════════════════════════════════════════════
       ┌──────────┬───────────────────────────────────────────────┐
       │ BE       │ lấy bình quân theo thời gian → GIẢM sai số đo  │
       │          │ nhưng KHÔNG xử lý biến bị bỏ sót              │
       │ FE       │ khử ν → xử lý biến bị bỏ sót, nhưng phép TRỪ   │
       │          │ BÌNH QUÂN làm tỷ lệ tín hiệu/nhiễu xấu đi      │
       │          │ (Grilliches–Hausman; Hauk–Wacziarg)           │
       │ SGMM     │ về lý thuyết xử lý cả ba, nhưng dễ dính vấn đề │
       │          │ CÔNG CỤ YẾU (Roodman 2009; Bazzi–Clemens 2009) │
       │ hồi quy  │ chống GIÁ TRỊ NGOẠI LAI: bỏ quan sát có khoảng │
       │ bền vững │ cách Cook > 1, giảm trọng số phần dư lớn       │
       └──────────┴───────────────────────────────────────────────┘
       ★★ CHỌN BE VÀ SGMM LÀM ƯU TIÊN
       theo mô phỏng Monte Carlo của Hauk–Wacziarg (2009), BE cho
         TỔNG thiên lệch nhỏ nhất trong bốn ước lượng
       ═══════════════════════════════════════════════════════════
       ⚠ THÚ NHẬN QUAN TRỌNG: dùng nợ ĐẦU kỳ tránh được nhân quả
         ngược nhưng KHÔNG giải quyết nội sinh — nợ và tăng trưởng
         vẫn có thể cùng do một biến thứ ba quyết định
```

### Bộ biến kiểm soát "lõi"

```text
       THEO Sala-i-Martin, Doppelhofer, Miller (2004)
       xét 67 biến giải thích → 18 biến có xác suất đưa vào hậu
         nghiệm cao; trong đó chỉ vài biến KINH TẾ:
         GDP đầu người đầu kỳ · tỷ lệ nhập học tiểu học · tỷ trọng
         tiêu dùng chính phủ đầu kỳ · độ mở thương mại · giá tương
         đối của đầu tư
       phần còn lại là biến VÙNG và các yếu tố XÃ HỘI–CHÍNH TRỊ
       ═══════════════════════════════════════════════════════════
       X TRONG MÔ HÌNH CƠ SỞ (đều đo ĐẦU kỳ, trừ ba biến cuối)
       GDP đầu người ····· bắt "hội tụ", đuổi kịp
       vốn con người ····· log số năm học trung học bình quân dân số
                            trên 15 tuổi (Barro–Lee 2000)
       quy mô chính phủ ·· tiêu dùng chính phủ/GDP
       độ mở thương mại ·· (xuất + nhập)/GDP
       độ sâu tài chính ·· nợ thanh khoản/GDP (Woo 2003)
       lạm phát ·········· log(1 + tỷ lệ lạm phát)
       ─── đo TRONG kỳ ───
       tăng trưởng điều kiện thương mại
       ★ khủng hoảng ngân hàng (Reinhart–Reinhart 2008): khủng hoảng
         ngân hàng làm nợ tăng bình quân 86% trong các đợt lớn
         (Reinhart–Rogoff 2009) VÀ làm tăng trưởng chậm
       thâm hụt tài khoá (Fischer 1993; Baldacci 2004)
       ═══════════════════════════════════════════════════════════
       ⚠ KHÔNG đưa đầu tư và vốn/lao động vào bộ lõi: đó là nguyên
         nhân GẦN của tăng trưởng, sẽ xét riêng ở phần hạch toán
```

### Sự thật thống kê: hai bức tranh

```text
       ★ HÌNH 1 — TƯƠNG QUAN THÔ
       đường khớp: Tăng trưởng = 4,31 − 0,025 × Nợ đầu kỳ
       hệ số có ý nghĩa ở mức 1%
       → hiểu thô: tăng 10 điểm nợ ↔ tăng trưởng chậm 0,25 điểm
       ★ con số này RẤT GẦN với kết quả kinh tế lượng phía sau
       ═══════════════════════════════════════════════════════════
       ★★ HÌNH 2 — TĂNG TRƯỞNG THEO GIAI ĐOẠN NỢ (%/năm, ước đọc)
       nợ THẤP = dưới 30% GDP · nợ CAO = trên 90% GDP
       ┌────────────────┬──────────┬──────────┬──────────────────┐
       │ nhóm nước      │ nợ THẤP  │ nợ CAO   │ ★ CHÊNH LỆCH     │
       ├────────────────┼──────────┼──────────┼──────────────────┤
       │ G7             │ ~2,7     │ ~1,25    │ 1,5 điểm         │
       │ phát triển     │ ~3,2     │ ~1,93    │ 1,3 điểm         │
       │ mới nổi        │ ~6,6     │ ~3,9     │ ★ 2,7 điểm       │
       │ toàn mẫu       │ ~5,13    │ ~2,26    │ 2,8 điểm         │
       └────────────────┴──────────┴──────────┴──────────────────┘
       → chênh lệch ở nước mới nổi lớn GẤP HƠN HAI LẦN nước phát triển
```

### Kết quả cơ sở (Bảng 1)

```text
       ★★ HỆ SỐ NỢ CHÍNH PHỦ ĐẦU KỲ
       ┌────────────────┬──────────┬──────────┬──────────┬────────┐
       │                │ BE       │ OLS gộp  │ FE       │ SGMM   │
       ├────────────────┼──────────┼──────────┼──────────┼────────┤
       │ KHÔNG hiệu ứng │ −0,026***│ −0,020***│ −0,019***│−0,029**│
       │ thời gian      │          │          │          │      * │
       │ CÓ hiệu ứng    │ —        │ −0,018***│ ⚠ −0,004 │−0,020**│
       │ thời gian      │          │          │ (mất ý   │        │
       │                │          │          │  nghĩa)  │        │
       └────────────────┴──────────┴──────────┴──────────┴────────┘
       BE: tăng 10 điểm nợ đầu kỳ ↔ tăng trưởng chậm ~0,26 điểm/năm
       ★ có hiệu ứng thời gian → ước lượng còn ~0,2 điểm/năm
       N = 166 ở mọi cột
       ═══════════════════════════════════════════════════════════
       ★ KIỂM TRA TÍNH VỮNG CỦA SGMM BẰNG QUY TẮC BOND (2002)
       OLS lệch LÊN, FE lệch XUỐNG → GMM vững phải nằm GIỮA
       hệ số GDP đầu người: OLS −2,26 < SGMM −2,56 < FE −3,60 ✔
       ═══════════════════════════════════════════════════════════
       KIỂM ĐỊNH CÔNG CỤ
       ✔ Hansen J (công cụ hợp lệ) ········· p = 0,28
       ✔ difference-in-Hansen (bộ công cụ mức) p = 0,34
       ✔ Arellano-Bond AR(2) ··············· p = 0,64
       ★ kỹ thuật: "gộp" ma trận công cụ + giới hạn số độ trễ để
         tránh QUÁ NHIỀU CÔNG CỤ
       ═══════════════════════════════════════════════════════════
       ⚠ VÌ SAO FE SỤP KHI THÊM HIỆU ỨNG THỜI GIAN
       FE nhận diện tham số từ biến thiên TRONG nước; thêm biến giả
         năm thì biến thiên còn lại của các biến DAI DẲNG gần như
         không còn (Islam 1995) → hệ số bị kéo về 0
       cộng thêm sai số đo bị khuếch đại → bài vẫn giữ hiệu ứng thời
         gian cho các hồi quy sau, kèm cảnh báo này
```

### Độ vững (Bảng 2–4)

```text
       ✔ GIAI ĐOẠN 1990–2007 (N = 124)
         BE −0,024*** · OLS −0,021*** · SGMM −0,028* · ⚠ FE −0,011 ns
         → 10 điểm nợ ↔ chậm 0,2–0,3 điểm/năm
       ✔ BỎ GIỚI HẠN DÂN SỐ 5 TRIỆU → 46 nước (N = 208)
         BE −0,023*** · OLS −0,020*** · FE −0,013* · SGMM −0,025*
       ═══════════════════════════════════════════════════════════
       ✔ ĐẶC TẢ TIẾT GIẢN (bỏ thâm hụt tài khoá)
         nợ đầu kỳ: −0,026*** · −0,014** · ⚠ FE +0,010 · −0,024***
         ★ dùng NỢ BÌNH QUÂN thay nợ đầu kỳ: −0,027*** · −0,019** ·
           −0,006 ns · −0,020**
       ═══════════════════════════════════════════════════════════
       ✔ THÊM BIẾN (Bảng 4)
       ① quy mô dân số ··· nợ: −0,025***/−0,018***/0,001/−0,023***
                            dân số KHÔNG ý nghĩa (trừ FE)
       ② đầu tư đầu kỳ ··· nợ: −0,019**/−0,015**/−0,007/−0,018**
                            đầu tư +0,065**/+0,052*/⚠ −0,045/+0,063
       ③ ★ BIẾN ĐỘNG CHI TIÊU tài khoá (Fatas–Mihov 2003)
          GIẢ THUYẾT ĐỐI THỦ: tuỳ tiện tài khoá quá mức vừa làm nợ
            phình vừa làm tăng trưởng chậm → nợ chỉ là biến "ăn theo"
          ✘ BÁC BỎ: hệ số biến động KHÔNG ý nghĩa và đổi dấu, trong
            khi hệ số nợ GIỮ NGUYÊN độ lớn và ý nghĩa
       ═══════════════════════════════════════════════════════════
       ✔ HỒI QUY CHÉO NƯỚC (Phụ lục 4)
       lo ngại: kỳ năm năm chưa đủ dài để san bằng chu kỳ kinh doanh
       kết quả 1975–2007, 1990–2007, 1995–2007, 2000–2007: −0,017 tới
         −0,026, có ý nghĩa; ⚠ riêng 1985–2007 chỉ −0,004 và mất ý
         nghĩa (chỉ 20 quan sát)
       nợ BÌNH QUÂN: −0,018 tới −0,022, đều có ý nghĩa 5%
       mở rộng sang cả nước đang phát triển: −0,013 tới −0,020, nhỏ hơn
```

### Phi tuyến và khác biệt nhóm nước (Bảng 5–6)

```text
       ★★ BA NGƯỠNG NỢ — hệ số của nợ đầu kỳ × biến giả
       ┌──────────────┬────────┬─────────┬────────┬────────────────┐
       │              │ BE     │ OLS     │ FE     │ SGMM           │
       ├──────────────┼────────┼─────────┼────────┼────────────────┤
       │ Dum_30       │ −0,003 │ −0,001  │ +0,001 │ ⚠ +0,031       │
       │ (<30% GDP)   │ ns     │ ns      │ ns     │ ns, ĐỔI DẤU    │
       │ Dum_30-90    │ −0,015 │ −0,025**│ +0,005 │ −0,018         │
       │ (trung bình) │ ns     │         │ ns     │ ns             │
       │ ★ Dum_90     │−0,017**│−0,016***│ −0,002 │ −0,018*        │
       │ (>90% GDP)   │        │         │ ns     │                │
       └──────────────┴────────┴─────────┴────────┴────────────────┘
       ★★ CHỈ NỢ CAO mới có tác động âm có ý nghĩa (trừ FE)
       ═══════════════════════════════════════════════════════════
       ★★ PHÁT TRIỂN so với MỚI NỔI
       phát triển ··· −0,021** / −0,014*** / −0,005 ns / −0,017*
       mới nổi ······ −0,036*** / −0,034** / +0,007 ns / −0,041*
       → 10 điểm nợ ↔ chậm 0,15–0,2 điểm ở nước phát triển,
                       0,3–0,4 điểm ở nước mới nổi
       ★ GIẢI THÍCH: nước mới nổi có NĂNG LỰC VAY hạn chế do thị
         trường tài chính trong nước kém phát triển và khả năng tiếp
         cận vốn quốc tế mong manh
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 6 — TĂNG 10% (TỶ LỆ) TỶ LỆ NỢ, KHÔNG PHẢI 10 ĐIỂM
       lý do: từ 10 lên 20 là GẤP ĐÔI, từ 100 lên 110 chỉ thêm 1/10
       ┌──────────────────┬───────┬───────┬───────┬────────────────┐
       │ nhóm nợ (% GDP)  │  <30  │ 30–60 │ 60–90 │ ★ >90          │
       ├──────────────────┼───────┼───────┼───────┼────────────────┤
       │ nợ bình quân mẫu │ 15,8  │ 45,1  │ 70,3  │ 111,9          │
       │ hệ số bình quân  │ +0,022│ −0,025│ −0,023│ −0,017         │
       │ ★ tác động (điểm)│ +0,04 │ −0,11 │ −0,16 │ ★ −0,19        │
       └──────────────────┴───────┴───────┴───────┴────────────────┘
       ★★ NỢ BAN ĐẦU CÀNG CAO, CÙNG MỘT MỨC TĂNG TỶ LỆ CÀNG HẠI
       ⚠ bài tự cảnh báo: hệ số nhóm nợ thấp KHÔNG khác 0 về thống kê,
         và ý nghĩa của các hệ số khác thay đổi theo phương pháp
```

### Hạch toán tăng trưởng: nợ hại qua kênh nào (Bảng 7–8)

```text
       HÀM SẢN XUẤT COBB-DOUGLAS: Y = A·K^α·(HL)^(1−α)
       theo lao động: y = A·k^α·H^(1−α)
       ★ PHÂN RÃ (2): ẏ/y = Ȧ/A + α·(k̇/k) + (1−α)·(Ḣ/H)
       α = 0,35 (tỷ trọng thu nhập của vốn), lao động 0,65
       ═══════════════════════════════════════════════════════════
       ★★ HỆ SỐ NỢ ĐẦU KỲ THEO BIẾN PHỤ THUỘC (N = 159)
       ┌──────────────────────┬────────┬────────┬────────┬────────┐
       │ biến phụ thuộc       │ BE     │ OLS    │ FE     │ SGMM   │
       ├──────────────────────┼────────┼────────┼────────┼────────┤
       │ sản lượng/lao động   │−0,019**│−0,013**│ −0,002 │−0,022**│
       │ ★ TFP                │ −0,008 │ −0,005 │ +0,003 │ −0,011 │
       │                      │ ns     │ ns     │ ns     │ ns     │
       │ ★★ vốn/lao động      │−0,029* │−0,022**│−0,021**│−0,053**│
       │                      │        │        │        │      * │
       └──────────────────────┴────────┴────────┴────────┴────────┘
       ★★ KẾT LUẬN CHÍNH: tác động qua TFP KHÔNG có ý nghĩa ở mọi
          phương pháp; tác động qua VỐN TRÊN LAO ĐỘNG mạnh và vững
       nhân với α = 0,35: kênh vốn đóng góp 0,1–0,2 điểm/năm; cộng
         với TFP thì tổng 0,2–0,3 điểm, khớp với hồi quy trực tiếp
       ⚠ vốn con người: KHÔNG có tác động có ý nghĩa, không báo cáo
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 8 — HỒI QUY TRỰC TIẾP LÊN ĐẦU TƯ (% GDP)
       BE −0,099** · OLS −0,051* · FE −0,062*** · SGMM động −0,038*
       ★ tăng 10 điểm nợ ↔ đầu tư trong nước giảm ~0,4 điểm % GDP
       theo nhóm: phát triển −0,041* · ★ mới nổi −0,085*
         → tác động ở nước mới nổi GẦN GẤP ĐÔI
       ═══════════════════════════════════════════════════════════
       ⚠ BIẾN ĐỘNG VĨ MÔ: giả thuyết nợ cao → bất định và dễ khủng
         hoảng hơn → biến động lớn hơn. Đồ thị phân tán cho tương
         quan dương NHẸ, nhưng hồi quy chỉ có ý nghĩa ở FE KHÔNG có
         hiệu ứng thời gian; mọi đặc tả khác đều không ý nghĩa
```

### Kiểm chứng riêng cho nước Mỹ (Phụ lục 2)

```text
       TIỀN ĐỀ: ở Mỹ, mỗi đô la nợ chèn lấn đúng MỘT đô la vốn trong
         dài hạn (Elmendorf–Mankiw 1999)
       ═══════════════════════════════════════════════════════════
       tỷ trọng thu nhập của vốn ~1/3 · tỷ lệ vốn/sản lượng ~3,7 (2008)
       ★ SẢN PHẨM BIÊN CỦA VỐN (MPK) = (1/3) / 3,7 ≈ 9%
         (Elmendorf–Mankiw ước 9,5%; Caselli–Feyrer 2007: 11,4%)
       ═══════════════════════════════════════════════════════════
       GIẢ ĐỊNH: nợ ròng/GDP tăng 40 điểm trong năm năm ≈ 6.450 tỷ USD
         (GDP thực 13,3 nghìn tỷ, nợ công do dân nắm 40,8% GDP năm 2008,
          tăng trưởng thực bình quân 2%)
       → chèn lấn HOÀN TOÀN: sản lượng giảm ~4,4% tổng cộng
       → ≈ tăng trưởng chậm 0,8%; hay ★ 0,2%/năm cho mỗi 10 điểm nợ
       ★★ TRÙNG KHỚP với ước lượng kinh tế lượng
       ═══════════════════════════════════════════════════════════
       ⚠ ĐÂY LÀ CẬN TRÊN — hai giả định ngầm
       ① nền kinh tế ĐÓNG: thực tế dòng vốn vào bù một phần chèn lấn
       ② tiết kiệm tư nhân KHÔNG phản ứng: thực tế có thể tăng
          (lập luận Ricardo)
       nới lỏng theo Gale–Orszag 2003 (tiết kiệm tư nhân bù 20%, vốn
         ngoại bù 25%) → sản lượng chỉ giảm 2,6% thay vì 4,4%
       ═══════════════════════════════════════════════════════════
       ✔ NHƯNG CÓ NGOẠI TÁC ĐI NGƯỢC LẠI
       mô hình tăng trưởng nội sinh (Romer 1987): tích luỹ vốn kích
         thích tiến bộ công nghệ → chèn lấn thì ngược lại
       bất định và nguy cơ khủng hoảng cao cũng làm nản đầu tư
       → "xấp xỉ bậc nhất, dù vẫn thiên về cận trên"
```

### Dữ liệu và mẫu

```text
       NGUỒN
       GDP, dân số, đầu tư, quy mô chính phủ ··· Penn World Table 6.3
                                                  (Heston 2009)
       nợ chính phủ, thâm hụt, điều kiện thương mại ··· IMF WEO 2009
       lạm phát, độ sâu tài chính, đô thị hoá ··· WDI 2009
       số năm học ······························ Barro–Lee 2000
       khủng hoảng ngân hàng ··················· Reinhart–Reinhart 2008
       kiểm soát và cân bằng ··················· DPI 2009, Polity IV
       ═══════════════════════════════════════════════════════════
       TÁI TẠO TFP (Phụ lục 3)
       vốn con người H = e^φ(E), φ tuyến tính từng khúc theo suất sinh
         lợi giáo dục (Psacharopoulos 1994): 13,4% nếu E ≤ 4 năm;
         10,1% nếu 4 < E ≤ 8; 6,8% nếu E > 8
       vốn K theo phương pháp KIỂM KÊ VĨNH VIỄN, δ = 0,06; vốn 1950
         khởi tạo bằng I(1950)/(g + δ)
       ★ trừ phần vốn NHÀ Ở không trực tiếp phục vụ sản xuất; nơi
         thiếu số liệu giả định vốn phi nhà ở = 2/3 tổng vốn
       ✔ thử cả tỷ trọng lao động cố định 0,65 lẫn tỷ trọng thực tế
         (Gollin 2002; Bernanke–Gürkaynak 2001) → kết quả rất giống
       ═══════════════════════════════════════════════════════════
       MẪU 38 NƯỚC (dân số > 5 triệu), Phụ lục 6
       ⚠ danh sách "nước phát triển" của bài gồm cả MEXICO và THỔ NHĨ
         KỲ, được mô tả là "phần lớn là thành viên OECD"
       ⚠ Séc, Nga, Slovakia bị loại khỏi phần hạch toán tăng trưởng
         do thiếu dữ liệu tính TFP
       thêm 8 nước khi bỏ giới hạn dân số: Phần Lan, Iceland, Ireland,
         Israel, Jordan, Na Uy, New Zealand, Singapore
```

### Bảng phụ lục 1: bức tranh mô tả

```text
       TĂNG TRƯỞNG GDP THỰC BÌNH QUÂN ĐẦU NGƯỜI (%/năm, 5 năm sau)
       ┌────────────┬──────┬───────┬───────┬──────┬────────┬───────┐
       │            │ <30% │ 30-60%│ 60-90%│ >90% │ >60 và │ >60 và│
       │            │      │       │       │      │ ĐANG   │ ĐANG  │
       │            │      │       │       │      │ TĂNG   │ GIẢM  │
       ├────────────┼──────┼───────┼───────┼──────┼────────┼───────┤
       │ toàn mẫu   │ 5,1  │ 2,8   │ 2,7   │ 2,3  │ ★ 1,4  │ 3,1   │
       │ phát triển │ 3,2  │ 2,3   │ 2,2   │ 1,9  │ 1,6    │ 2,4   │
       │ mới nổi    │ 6,6  │ 2,6   │ 3,7   │ 3,9  │ 2,1    │ 4,7   │
       │ đang p.t.  │ 7,2  │ 4,5   │ 2,6   │ 2,3  │ ★ 0,7  │ 3,0   │
       └────────────┴──────┴───────┴───────┴──────┴────────┴───────┘
       ★★ CỘT ĐÁNG CHÚ Ý NHẤT: nợ trên 60% và ĐANG TĂNG cho tăng
          trưởng THẤP NHẤT ở mọi nhóm nước — hướng đi của nợ quan
          trọng không kém mức nợ
       ═══════════════════════════════════════════════════════════
       ĐẦU TƯ TRONG NƯỚC (% GDP, 5 năm sau)
       toàn mẫu ··· 26,7 → 22,7 → 20,0 → ★ 16,4
       phát triển · 32,0 → 26,7 → 27,5 → 29,4 (gần như không giảm)
       ★ mới nổi ·· 27,4 → 15,7 → 15,4 → ★ 11,4 (giảm hơn một nửa)
       đang p.t. ·· 18,6 → 15,6 → 11,1 → 9,4
```

## Ba câu hỏi bài viết trả lời

1. Mức nợ công cao hôm nay làm tăng trưởng GDP thực bình quân đầu người những năm sau chậm đi bao nhiêu, sau khi đã kiểm soát các yếu tố quyết định tăng trưởng khác và xử lý nhân quả ngược?
2. Quan hệ đó có tuyến tính không, hay chỉ vượt một ngưỡng nợ nhất định mới đáng lo, và có khác nhau giữa nước phát triển và nước mới nổi?
3. Nợ làm chậm tăng trưởng qua kênh nào: tích luỹ yếu tố sản xuất hay năng suất nhân tố tổng hợp?

## Khái niệm cần biết

**Tỷ lệ nợ công trên GDP và "điểm phần trăm".** Tổng nợ của chính phủ chia cho tổng sản lượng một năm của nền kinh tế. Bài dùng nợ chính phủ gộp (chưa trừ tài sản tài chính của chính phủ). "Tăng 10 điểm phần trăm" nghĩa là tỷ lệ đi từ, ví dụ, 50% lên 60%; khác với "tăng 10%" theo tỷ lệ, tức từ 50% lên 55%. Ví dụ trong bài: tăng 10 điểm phần trăm nợ đầu kỳ đi kèm tăng trưởng chậm lại khoảng 0,2 điểm phần trăm mỗi năm. Phân biệt hai cách nói này là điều kiện để hiểu phần phi tuyến của bài.

**Nợ đầu kỳ và nhân quả ngược (initial debt / reverse causality).** Nhân quả ngược là khả năng tăng trưởng thấp gây ra nợ cao (thu ngân sách hụt, GDP ở mẫu số co lại), chứ không phải nợ cao gây tăng trưởng thấp. Bài xử lý bằng cách dùng mức nợ **đầu** mỗi kỳ năm năm để giải thích tăng trưởng **trong** năm năm tiếp theo. Ví dụ minh hoạ: nợ năm 1990 được dùng để giải thích tăng trưởng bình quân 1990–1995; tăng trưởng 1990–1995 không thể quay ngược lại tác động lên nợ năm 1990. Đây là trục của toàn bộ chiến lược ước lượng.

**Nội sinh (endogeneity).** Khi nợ và tăng trưởng cùng do một biến thứ ba quyết định, ví dụ thể chế yếu vừa làm chính phủ vay nhiều vừa làm kinh tế tăng chậm, thì quan hệ quan sát được không phải là tác động của nợ. Ví dụ minh hoạ: hai nước có cùng nợ 80% GDP nhưng một nước có thể chế yếu tăng trưởng 1%, nước kia 3%; nếu không tính tới thể chế, ta sẽ quy nhầm phần chênh lệch cho nợ. Bài thừa nhận dùng nợ đầu kỳ không giải quyết được vấn đề này.

**Chèn lấn (crowding out).** Khi chính phủ vay nhiều, nó dùng một phần tiết kiệm của nền kinh tế, đẩy lãi suất lên và làm doanh nghiệp đầu tư ít hơn. Ví dụ trong bài: với nước Mỹ, giả định mỗi đô la nợ chèn lấn đúng một đô la vốn tư nhân trong dài hạn, nợ tăng 40 điểm GDP làm sản lượng giảm khoảng 4,4%. Đây là cơ chế mà phần hạch toán tăng trưởng của bài xác nhận.

**Các phương pháp ước lượng bảng (OLS gộp, BE, FE, SGMM).** Dữ liệu bảng là số liệu của nhiều nước qua nhiều kỳ. OLS gộp coi mọi quan sát như nhau. Ước lượng giữa nhóm (BE) lấy bình quân của mỗi nước qua thời gian rồi so các nước với nhau. Hiệu ứng cố định (FE) so mỗi nước với chính nó qua thời gian, nên loại được đặc điểm cố định của từng nước. GMM hệ thống (SGMM) dùng các giá trị trễ của chính các biến làm biến công cụ để xử lý nội sinh. Ví dụ trong bài: hệ số nợ đầu kỳ là −0,026 theo BE nhưng chỉ −0,004 và không có ý nghĩa theo FE khi có hiệu ứng thời gian. Mỗi phương pháp chịu một loại thiên lệch khác nhau, nên bài chạy cả bốn.

**Phi tuyến và hiệu ứng ngưỡng (nonlinearity / threshold effect).** Quan hệ phi tuyến là khi tác động của nợ không giống nhau ở mọi mức nợ; hiệu ứng ngưỡng là khi tác động chỉ xuất hiện sau một mức nhất định. Ví dụ trong bài: chỉ nhóm nợ trên 90% GDP có hệ số âm có ý nghĩa; và cùng một mức tăng 10% theo tỷ lệ, tác động là −0,11 điểm ở nhóm 30–60% nhưng −0,19 điểm ở nhóm trên 90%. Đây là phần được trích dẫn nhiều nhất của bài.

**Hạch toán tăng trưởng và TFP (growth accounting / total factor productivity).** Tách tăng trưởng sản lượng trên mỗi lao động thành ba phần: phần do mỗi lao động có thêm máy móc (vốn trên lao động), phần do lao động có trình độ cao hơn (vốn con người), và phần còn lại do dùng các yếu tố hiệu quả hơn, gọi là năng suất nhân tố tổng hợp (TFP). Ví dụ minh hoạ: nếu sản lượng trên lao động tăng 3%, vốn trên lao động tăng 4% và tỷ trọng thu nhập của vốn là 0,35, thì vốn đóng góp 1,4 điểm; nếu vốn con người đóng góp 0,6 điểm thì TFP là 1 điểm. Bài dùng cách này để chỉ ra nợ hại tăng trưởng qua kênh vốn chứ không qua TFP.

**Sản phẩm biên của vốn (MPK).** Lượng sản lượng tăng thêm khi nền kinh tế có thêm một đồng vốn. Ví dụ trong bài: với tỷ trọng thu nhập của vốn khoảng 1/3 và tỷ lệ vốn trên sản lượng khoảng 3,7, MPK của Mỹ là (1/3)/3,7 ≈ 9%, tức mỗi đô la vốn bị chèn lấn làm mất khoảng 9 cent sản lượng mỗi năm. Con số này cho phép bài kiểm chứng kết quả hồi quy bằng một phép tính độc lập.

## Nội dung chi tiết

### 1. Mở đầu

**Bối cảnh năm 2010.** Sau khủng hoảng tài chính toàn cầu, nợ chính phủ các nước phát triển tăng vọt, làm dấy lên lo ngại về tính bền vững tài khoá và tác động lên thị trường tài chính. Câu hỏi trọng tâm là nợ lớn có làm giảm tích luỹ vốn, năng suất và **tăng trưởng tiềm năng** hay không. Theo tác giả, "có rất ít bằng chứng có hệ thống" về mức độ tác động này.

Câu hỏi quan trọng vì có thể xảy ra một vòng xoáy nguy hiểm: nợ cao làm tăng trưởng chậm; tăng trưởng chậm làm tính bền vững tài khoá xấu đi (GDP ở mẫu số tăng chậm, thu ngân sách hụt); và vì thế càng cần điều chỉnh tài khoá sớm và quyết liệt. Nếu tăng trưởng thật sự bị ảnh hưởng thì lợi ích của việc điều chỉnh sớm càng lớn.

**Vị trí của bài trong tài liệu.** Bài đứng trên hai nhánh nghiên cứu:

1. Nhánh lớn về các yếu tố quyết định tăng trưởng trung và dài hạn (Barro và Sala-i-Martin 2003; Aghion và Durlauf 2005).
2. Nhánh hẹp về tác động của **nợ nước ngoài** lên tăng trưởng ở nước thu nhập thấp, qua chèn lấn và "debt overhang" (gánh nợ quá nặng).

Khoảng trống mà bài lấp là tác động của **nợ công** ở các nước **phát triển và mới nổi**.

**Cách tiếp cận.** Bài dùng hai phương pháp bổ trợ nhau: hồi quy tăng trưởng (nợ tác động bao nhiêu) và hạch toán tăng trưởng (nợ tác động qua kênh nào). Bài đặc biệt chú ý tới nhân quả ngược, nội sinh, phi tuyến và hiệu ứng ngưỡng.

### 2. Kênh truyền dẫn và tài liệu hiện có

**Năm kênh qua đó nợ công cao làm giảm tăng trưởng dài hạn.**

| Kênh | Cơ chế | Tài liệu dẫn |
|---|---|---|
| 1. Lãi suất dài hạn cao hơn | Chính phủ vay nhiều đẩy lãi suất lên, doanh nghiệp đầu tư ít đi | Gale và Orszag 2003; Baldacci và Kumar 2010 |
| 2. Thuế gây méo mó trong tương lai | Nợ hôm nay phải trả bằng thuế ngày mai, và thuế làm sai lệch quyết định làm việc, đầu tư | Barro 1979; Dotsey 1994 |
| 3. Lạm phát | Chính phủ có động cơ in tiền để giảm gánh nợ thực | Sargent và Wallace 1981; Barro 1995; Cochrane 2010 |
| 4. Bất định | Nhà đầu tư không chắc về triển vọng và chính sách tương lai nên trì hoãn đầu tư | |
| 5. Mất dư địa chính sách tài khoá ngược chu kỳ | Nợ cao thì không còn chỗ để tăng chi khi suy thoái, nên kinh tế biến động mạnh hơn, mà biến động cao đi kèm tăng trưởng thấp | Aghion và Kharroubi 2007; Woo 2009 |

Trường hợp cực đoan là khủng hoảng nợ kích hoạt khủng hoảng ngân hàng hoặc khủng hoảng tiền tệ, khuếch đại thiệt hại (Burnside 2001; Hemming 2003).

**Quan điểm truyền thống** (Elmendorf và Mankiw 1999): trong ngắn hạn, nợ sinh ra từ thâm hụt ngân sách kích cầu và làm tăng sản lượng; trong dài hạn, nợ chèn lấn vốn và làm giảm sản lượng. Lý thuyết tăng trưởng cho hai dự báo khác nhau về độ dài tác động: trong mô hình tân cổ điển, tăng trưởng chỉ giảm **tạm thời** trên đường chuyển tiếp tới trạng thái dừng mới; trong mô hình tăng trưởng nội sinh, tăng trưởng giảm **vĩnh viễn** (Saint-Paul 1992).

**Nghiên cứu mở đường của Reinhart và Rogoff (2010).** Hai tác giả so sánh tăng trưởng và lạm phát theo mức nợ trên dữ liệu lịch sử rất dài: 44 nước, khoảng 200 năm, với nước Mỹ từ năm 1790. Chênh lệch tăng trưởng giữa thời kỳ nợ thấp (dưới 30% GDP) và nợ cao (trên 90% GDP):

| Nhóm nước | Chênh lệch tăng trưởng |
|---|---|
| Nước phát triển | trung vị 2,6 điểm phần trăm; bình quân 4,2 điểm |
| Nước mới nổi | trung vị 2,1 điểm phần trăm |

Về lạm phát, họ không thấy quan hệ dương có hệ thống với nợ ở nước phát triển, nhưng thấy rõ ở nước mới nổi. Hạn chế của nghiên cứu này, mà bài muốn khắc phục: nó chỉ xét tương quan, không kiểm soát các yếu tố quyết định tăng trưởng khác, và không xử lý nhân quả ngược.

**Nhánh "debt overhang"** về nợ nước ngoài ở nước đang phát triển. Theo Krugman (1988) và Sachs (1989), khi nghĩa vụ trả nợ quá nặng, phần lớn sản lượng tăng thêm sẽ thuộc về chủ nợ nước ngoài, nên trong nước mất động lực đầu tư. Imbs và Ranciere (2009), Pattillo, Poirson và Ricci (2002, 2004) tìm thấy quan hệ phi tuyến: tác động âm khi nợ vượt khoảng 60% GDP, không có ý nghĩa khi nợ thấp. Riêng Cordella, Ricci và Arranz (2005) chỉ thấy tác động ở mức nợ trung bình, không có ý nghĩa ở cả mức rất thấp lẫn rất cao.

### 3. Chiến lược ước lượng

**Vấn đề độ vững và bộ biến lõi.** Vấn đề lớn nhất của tài liệu hồi quy tăng trưởng là hệ số ước lượng rất nhạy với việc đưa biến nào khác vào. Bài theo cách của Bosworth và Collins: chọn một bộ biến lõi đã được chứng minh ổn định, rồi đánh giá biến quan tâm (nợ) có điều kiện trên bộ lõi đó.

Bộ lõi lấy theo Sala-i-Martin, Doppelhofer và Miller (2004). Họ xét 67 biến giải thích và thấy 18 biến có xác suất hậu nghiệm cao được đưa vào mô hình (tức là đáng tin nhất). Trong 18 biến đó chỉ có vài biến kinh tế thuần tuý: GDP đầu người đầu kỳ, tỷ lệ nhập học tiểu học, tỷ trọng tiêu dùng chính phủ đầu kỳ, độ mở thương mại, và giá tương đối của hàng đầu tư. Phần còn lại là biến vùng địa lý và các yếu tố xã hội, chính trị.

**Phương trình cơ sở (1).** Mỗi kỳ dài năm năm, với τ = 4 là khoảng cách giữa năm đầu và năm cuối trong cách ký hiệu của bài:

> y(i,t) − y(i,t−τ) = α·y(i,t−τ) + X'(i,t−τ)β + γ·Z(i,t−τ) + η(t) + ν(i) + ε(i,t)

Trong đó y là log GDP thực bình quân đầu người của nước i; vế trái là tăng trưởng trong kỳ; Z là **nợ chính phủ gộp đầu kỳ** (% GDP), biến quan tâm chính, với hệ số γ; X là các biến kiểm soát; η(t) là hiệu ứng thời gian chung cho mọi nước; ν(i) là hiệu ứng cố định của từng nước; ε là sai số.

**Các biến kiểm soát X** (đều đo ở đầu kỳ, trừ ba biến cuối đo trong kỳ):

| Biến | Cách đo | Vai trò |
|---|---|---|
| GDP đầu người | log, đầu kỳ | bắt hiện tượng hội tụ: nước nghèo có xu hướng đuổi kịp |
| Vốn con người | log số năm học trung học bình quân của dân số trên 15 tuổi (Barro và Lee 2000) | |
| Quy mô chính phủ | tiêu dùng chính phủ/GDP | |
| Độ mở thương mại | (xuất khẩu + nhập khẩu)/GDP | |
| Độ sâu tài chính | nợ thanh khoản/GDP (Woo 2003) | |
| Lạm phát | log(1 + tỷ lệ lạm phát) | |
| Tăng trưởng điều kiện thương mại | trong kỳ | |
| Khủng hoảng ngân hàng | trong kỳ (Reinhart và Reinhart 2008) | khủng hoảng ngân hàng làm nợ tăng bình quân 86% trong các đợt lớn (Reinhart và Rogoff 2009) và đồng thời làm tăng trưởng chậm, nên nếu bỏ sót sẽ quy nhầm tác động cho nợ |
| Thâm hụt tài khoá | trong kỳ (Fischer 1993; Baldacci 2004) | |

Bài cố ý **không** đưa đầu tư và vốn trên lao động vào bộ lõi, vì đó là nguyên nhân gần của tăng trưởng (nợ có thể tác động qua chính các biến này); chúng được xét riêng ở phần hạch toán tăng trưởng.

**Xử lý nhân quả ngược và nội sinh.** Dùng nợ đầu kỳ để giải thích tăng trưởng tiếp theo tránh được nhân quả ngược. Nhưng bài nói rõ cách này không giải quyết được nội sinh: nợ và tăng trưởng vẫn có thể cùng do một biến thứ ba quyết định. Vì khó tìm biến công cụ bên ngoài, bài dùng SGMM với các độ trễ của biến ở dạng mức và dạng sai phân làm công cụ.

**Ba nguồn thiên lệch.**

1. *Biến bị bỏ sót* (còn gọi là thiên lệch dị biệt): hiệu ứng cố định ν của từng nước tương quan với các biến giải thích. Vấn đề này làm hỏng OLS gộp và BE.
2. *Nội sinh*: biến giải thích tương quan với sai số. Vấn đề này làm hỏng OLS gộp, BE và FE. Riêng với bảng động (có biến phụ thuộc trễ ở vế phải) còn có thiên lệch bảng động, làm FE không vững và lệch xuống.
3. *Sai số đo lường*: làm hỏng cả ba, nhưng nặng ở FE và nhẹ ở BE.

**Ưu nhược điểm của từng phương pháp.**

| Phương pháp | Ưu điểm | Nhược điểm |
|---|---|---|
| BE | lấy bình quân theo thời gian nên giảm sai số đo | không xử lý biến bị bỏ sót |
| FE | khử ν nên xử lý được biến bị bỏ sót | phép trừ bình quân làm tỷ lệ tín hiệu trên nhiễu xấu đi (Grilliches và Hausman; Hauk và Wacziarg) |
| SGMM | về lý thuyết xử lý được cả ba nguồn thiên lệch | dễ gặp vấn đề công cụ yếu (Roodman 2009; Bazzi và Clemens 2009) |
| Hồi quy bền vững | chống giá trị ngoại lai: bỏ quan sát có khoảng cách Cook lớn hơn 1, giảm trọng số các phần dư lớn | |

Không thể biết trước phương pháp nào cho tổng thiên lệch nhỏ nhất. Theo mô phỏng Monte Carlo của Hauk và Wacziarg (2009), BE cho tổng thiên lệch nhỏ nhất trong bốn ước lượng, nên bài chọn **BE và SGMM làm ưu tiên**. Do mỗi ước lượng có đánh đổi riêng, bài chạy đồng thời nhiều phương pháp, thêm hồi quy bền vững để chống giá trị ngoại lai, và một hồi quy chéo nước để xử lý lo ngại kỳ năm năm quá ngắn.

### 4. Dữ liệu và sự thật thống kê

**Nguồn dữ liệu.**

| Biến | Nguồn |
|---|---|
| GDP, dân số, đầu tư, quy mô chính phủ | Penn World Table 6.3 (Heston 2009) |
| Nợ chính phủ, thâm hụt, điều kiện thương mại | IMF WEO 2009 |
| Lạm phát, độ sâu tài chính, đô thị hoá | WDI 2009 |
| Số năm học | Barro và Lee 2000 |
| Khủng hoảng ngân hàng | Reinhart và Reinhart 2008 |
| Kiểm soát và cân bằng quyền lực | DPI 2009, Polity IV |

**Mẫu.** Việc có hay không số liệu nợ công quyết định quy mô mẫu. Kết quả là bảng 38 nước phát triển và mới nổi có dân số trên 5 triệu, giai đoạn 1970–2007, chia thành tám kỳ năm năm không chồng lấn. Vài lưu ý về mẫu:

- Danh sách "nước phát triển" của bài gồm cả Mexico và Thổ Nhĩ Kỳ, được mô tả là "phần lớn là thành viên OECD".
- Séc, Nga và Slovakia bị loại khỏi phần hạch toán tăng trưởng vì thiếu dữ liệu để tính TFP.
- Khi bỏ giới hạn dân số, mẫu có thêm 8 nước: Phần Lan, Iceland, Ireland, Israel, Jordan, Na Uy, New Zealand, Singapore.

**Tương quan thô.** Đồ thị phân tán giữa nợ đầu kỳ và tăng trưởng tiếp theo cho đường khớp:

> Tăng trưởng = 4,31 − 0,025 × Nợ đầu kỳ

Hệ số có ý nghĩa ở mức 1%. Đọc thô: tăng 10 điểm phần trăm nợ đi kèm tăng trưởng chậm 0,25 điểm mỗi năm. Con số này rất gần với kết quả kinh tế lượng ở phần sau.

**Tăng trưởng theo giai đoạn nợ** (% mỗi năm, giá trị đọc trên đồ thị; nợ thấp là dưới 30% GDP, nợ cao là trên 90% GDP):

| Nhóm nước | Nợ thấp | Nợ cao | Chênh lệch |
|---|---|---|---|
| G7 | khoảng 2,7 | khoảng 1,25 | 1,5 điểm |
| Phát triển | khoảng 3,2 | khoảng 1,93 | 1,3 điểm |
| Mới nổi | khoảng 6,6 | khoảng 3,9 | 2,7 điểm |
| Toàn mẫu | khoảng 5,13 | khoảng 2,26 | 2,8 điểm |

Ở mọi nhóm nước, tăng trưởng trong các giai đoạn nợ cao thấp hơn giai đoạn nợ thấp, và chênh lệch ở nước mới nổi lớn gấp hơn hai lần nước phát triển.

**Bức tranh mô tả chi tiết hơn.** Tăng trưởng GDP thực bình quân đầu người trong năm năm sau (% mỗi năm), theo mức nợ đầu kỳ:

| Nhóm nước | Nợ <30% | 30-60% | 60-90% | >90% | >60 và đang tăng | >60 và đang giảm |
|---|---|---|---|---|---|---|
| Toàn mẫu | 5,1 | 2,8 | 2,7 | 2,3 | 1,4 | 3,1 |
| Phát triển | 3,2 | 2,3 | 2,2 | 1,9 | 1,6 | 2,4 |
| Mới nổi | 6,6 | 2,6 | 3,7 | 3,9 | 2,1 | 4,7 |
| Đang phát triển | 7,2 | 4,5 | 2,6 | 2,3 | 0,7 | 3,0 |

Cột đáng chú ý nhất là nợ trên 60% và **đang tăng**: nó cho tăng trưởng thấp nhất ở mọi nhóm nước (1,4% toàn mẫu, chỉ 0,7% ở nước đang phát triển), thấp hơn hẳn nhóm cùng mức nợ nhưng đang giảm. Bài đọc điều này là hướng đi của nợ quan trọng không kém mức nợ.

Đầu tư trong nước (% GDP, năm năm sau), theo bốn mức nợ từ dưới 30% đến trên 90%:

| Nhóm nước | <30% | 30-60% | 60-90% | >90% |
|---|---|---|---|---|
| Toàn mẫu | 26,7 | 22,7 | 20,0 | 16,4 |
| Phát triển | 32,0 | 26,7 | 27,5 | 29,4 |
| Mới nổi | 27,4 | 15,7 | 15,4 | 11,4 |
| Đang phát triển | 18,6 | 15,6 | 11,1 | 9,4 |

Ở nước phát triển, đầu tư gần như không giảm theo mức nợ; ở nước mới nổi, đầu tư giảm hơn một nửa từ nhóm nợ thấp nhất tới nhóm nợ cao nhất.

### 5. Phân tích kinh tế lượng

**Kết quả cơ sở.** Hệ số của nợ chính phủ đầu kỳ (mỗi cột có 166 quan sát):

| | BE | OLS gộp | FE | SGMM |
|---|---|---|---|---|
| Không có hiệu ứng thời gian | −0,026\*\*\* | −0,020\*\*\* | −0,019\*\*\* | −0,029\*\*\* |
| Có hiệu ứng thời gian | — | −0,018\*\*\* | −0,004 (không có ý nghĩa) | −0,020\*\* |

(\*\*\* có ý nghĩa ở mức 1%, \*\* ở mức 5%, \* ở mức 10%.)

Không có hiệu ứng thời gian, hệ số nợ đầu kỳ âm và có ý nghĩa ở mức 1% trong khoảng −0,019 tới −0,029. Theo BE, tăng 10 điểm nợ đầu kỳ đi kèm tăng trưởng chậm khoảng 0,26 điểm mỗi năm. Các biến kiểm soát khác đều có dấu như kỳ vọng.

**Kiểm tra SGMM bằng quy tắc của Bond (2002).** Với bảng động, OLS gộp lệch lên còn FE lệch xuống, nên một ước lượng GMM đáng tin phải nằm giữa hai ước lượng đó. Hệ số của GDP đầu người thoả điều kiện: OLS −2,26, SGMM −2,56, FE −3,60, tức SGMM nằm giữa.

**Kiểm định công cụ của SGMM.**

| Kiểm định | Giá trị p | Ý nghĩa |
|---|---|---|
| Hansen J | 0,28 | không bác bỏ tính hợp lệ của công cụ |
| Difference-in-Hansen (bộ công cụ ở dạng mức) | 0,34 | không bác bỏ |
| Arellano-Bond AR(2) | 0,64 | không có tự tương quan bậc hai, điều kiện cần cho SGMM |

Về kỹ thuật, bài "gộp" ma trận công cụ và giới hạn số độ trễ dùng làm công cụ để tránh tình trạng quá nhiều công cụ, vốn làm các kiểm định trên mất tác dụng.

**Thêm hiệu ứng thời gian.** Hệ số giảm nhẹ nhưng vẫn có ý nghĩa với OLS và SGMM, tương ứng khoảng 0,2 điểm tăng trưởng mỗi năm cho mỗi 10 điểm nợ. Riêng FE trở nên không có ý nghĩa. Bài giải thích: FE nhận diện tham số chỉ từ biến thiên **trong** từng nước; khi thêm biến giả cho từng kỳ, phần biến thiên còn lại của các biến dai dẳng như nợ gần như không còn (Islam 1995), nên hệ số bị kéo về 0; thêm vào đó, sai số đo bị khuếch đại. Bài vẫn giữ hiệu ứng thời gian trong các hồi quy sau, kèm cảnh báo này.

**Bốn nhóm kiểm tra độ vững.**

*Giai đoạn ngắn hơn, 1990–2007* (124 quan sát): BE −0,024\*\*\*, OLS −0,021\*\*\*, SGMM −0,028\*, FE −0,011 không có ý nghĩa. Tức 10 điểm nợ đi kèm tăng trưởng chậm 0,2–0,3 điểm mỗi năm.

*Mẫu rộng hơn*, bỏ giới hạn dân số 5 triệu, được 46 nước (208 quan sát): BE −0,023\*\*\*, OLS −0,020\*\*\*, FE −0,013\*, SGMM −0,025\*.

*Đặc tả tiết giản* (bỏ biến thâm hụt tài khoá) và *nợ bình quân* thay cho nợ đầu kỳ:

| Đặc tả | BE | OLS | FE | SGMM |
|---|---|---|---|---|
| Tiết giản, nợ đầu kỳ | −0,026\*\*\* | −0,014\*\* | +0,010 | −0,024\*\*\* |
| Tiết giản, nợ bình quân kỳ | −0,027\*\*\* | −0,019\*\* | −0,006 (không có ý nghĩa) | −0,020\*\* |

*Thêm biến*:

| Biến thêm | Hệ số nợ (BE / OLS / FE / SGMM) | Hệ số biến thêm |
|---|---|---|
| Quy mô dân số | −0,025\*\*\* / −0,018\*\*\* / 0,001 / −0,023\*\*\* | không có ý nghĩa, trừ ở FE |
| Đầu tư đầu kỳ | −0,019\*\* / −0,015\*\* / −0,007 / −0,018\*\* | +0,065\*\* / +0,052\* / −0,045 / +0,063 |
| Biến động chi tiêu tài khoá (Fatas và Mihov 2003) | giữ nguyên độ lớn và ý nghĩa | không có ý nghĩa và đổi dấu |

Kết quả với biến động chi tiêu đáng chú ý vì nó kiểm định một giả thuyết đối thủ: tuỳ tiện tài khoá quá mức có thể vừa làm nợ phình to vừa làm tăng trưởng chậm, khi đó nợ chỉ là biến "ăn theo". Giả thuyết này bị bác bỏ: biến động chi tiêu không có ý nghĩa, còn hệ số nợ không đổi.

*Hồi quy chéo nước.* Lo ngại là một kỳ năm năm chưa đủ dài để san bằng chu kỳ kinh doanh. Bài chạy hồi quy chéo trên bình quân của các giai đoạn dài hơn. Với các giai đoạn 1975–2007, 1990–2007, 1995–2007 và 2000–2007, hệ số nợ đầu kỳ từ −0,017 tới −0,026 và có ý nghĩa; riêng giai đoạn 1985–2007 chỉ −0,004 và không có ý nghĩa, với chỉ 20 quan sát. Dùng nợ bình quân, hệ số từ −0,018 tới −0,022, đều có ý nghĩa ở mức 5%. Mở rộng mẫu sang cả nước đang phát triển, hệ số nhỏ hơn: −0,013 tới −0,020.

**Phi tuyến: ba ngưỡng nợ.** Bài nhân nợ đầu kỳ với biến giả cho ba nhóm: Dum_30 (nợ dưới 30% GDP), Dum_30-90 (nợ trung bình, từ 30 tới 90%), Dum_90 (nợ trên 90% GDP).

| Nhóm nợ | BE | OLS | FE | SGMM |
|---|---|---|---|---|
| Dưới 30% | −0,003 (ns) | −0,001 (ns) | +0,001 (ns) | +0,031 (ns, đổi dấu) |
| 30 tới 90% | −0,015 (ns) | −0,025\*\* | +0,005 (ns) | −0,018 (ns) |
| Trên 90% | −0,017\*\* | −0,016\*\*\* | −0,002 (ns) | −0,018\* |

(ns: không có ý nghĩa thống kê.) Chỉ nhóm nợ trên 90% GDP có hệ số âm và có ý nghĩa ở hầu hết phương pháp (trừ FE).

**Nước phát triển và nước mới nổi.**

| Nhóm | BE | OLS | FE | SGMM |
|---|---|---|---|---|
| Phát triển | −0,021\*\* | −0,014\*\*\* | −0,005 (ns) | −0,017\* |
| Mới nổi | −0,036\*\*\* | −0,034\*\* | +0,007 (ns) | −0,041\* |

Tức là 10 điểm nợ đi kèm tăng trưởng chậm 0,15–0,2 điểm ở nước phát triển và 0,3–0,4 điểm ở nước mới nổi, gấp khoảng đôi. Bài giải thích bằng năng lực vay hạn chế của nước mới nổi: thị trường tài chính trong nước kém phát triển và khả năng tiếp cận vốn quốc tế mong manh.

**Cùng một mức tăng theo tỷ lệ.** Phần trên đo tác động của 10 **điểm** phần trăm nợ. Nhưng đi từ 10% lên 20% GDP là gấp đôi nợ, còn đi từ 100% lên 110% chỉ là thêm 1/10. Vì vậy bài tính thêm tác động của một mức tăng 10% **theo tỷ lệ** của tỷ lệ nợ, ở bốn nhóm nợ:

| Nhóm nợ (% GDP) | <30 | 30–60 | 60–90 | >90 |
|---|---|---|---|---|
| Nợ bình quân của nhóm | 15,8 | 45,1 | 70,3 | 111,9 |
| Hệ số bình quân | +0,022 | −0,025 | −0,023 | −0,017 |
| Tác động lên tăng trưởng (điểm) | +0,04 | −0,11 | −0,16 | −0,19 |

Ví dụ cách tính ở nhóm trên 90%: tăng 10% của 111,9 là khoảng 11,2 điểm nợ, nhân với hệ số −0,017 ra khoảng −0,19 điểm tăng trưởng. Kết luận: nợ ban đầu càng cao, cùng một mức tăng theo tỷ lệ càng gây hại nhiều. Bài tự cảnh báo rằng hệ số của nhóm nợ thấp không khác 0 về mặt thống kê, và ý nghĩa của các hệ số khác thay đổi theo phương pháp.

### 6. Hạch toán tăng trưởng

**Khung phân rã.** Bài dùng hàm sản xuất Cobb-Douglas Y = A·K^α·(HL)^(1−α), trong đó A là TFP, K là vốn, H là vốn con người trên mỗi lao động, L là số lao động. Chia cho số lao động được y = A·k^α·H^(1−α). Lấy tốc độ tăng hai vế cho phân rã (2):

> ẏ/y = Ȧ/A + α·(k̇/k) + (1−α)·(Ḣ/H)

tức tăng trưởng sản lượng trên lao động bằng tăng trưởng TFP cộng phần đóng góp của vốn trên lao động cộng phần đóng góp của vốn con người. Tỷ trọng thu nhập của vốn α = 0,35, của lao động 0,65.

**Cách dựng số liệu.**

- *Vốn con người*: H = e^φ(E), với E là số năm đi học và φ tuyến tính từng khúc theo suất sinh lợi của giáo dục (Psacharopoulos 1994): mỗi năm học thêm làm tăng H 13,4% nếu E ≤ 4 năm; 10,1% nếu 4 < E ≤ 8; và 6,8% nếu E > 8.
- *Vốn vật chất*: theo phương pháp kiểm kê vĩnh viễn (cộng dồn đầu tư hằng năm và trừ khấu hao), với tỷ lệ khấu hao δ = 0,06. Vốn năm 1950 được khởi tạo bằng I(1950)/(g + δ), với I là đầu tư năm đó và g là tốc độ tăng trưởng dùng để khởi tạo.
- Bài trừ phần vốn nhà ở, vì nhà ở không trực tiếp phục vụ sản xuất; nơi thiếu số liệu thì giả định vốn phi nhà ở bằng 2/3 tổng vốn.
- Bài thử cả tỷ trọng lao động cố định 0,65 lẫn tỷ trọng thực tế của từng nước (Gollin 2002; Bernanke và Gürkaynak 2001), và kết quả rất giống nhau.

**Kết quả.** Hệ số của nợ đầu kỳ khi lần lượt dùng từng thành phần làm biến phụ thuộc (159 quan sát):

| Biến phụ thuộc | BE | OLS | FE | SGMM |
|---|---|---|---|---|
| Sản lượng trên lao động | −0,019\*\* | −0,013\*\* | −0,002 | −0,022\*\* |
| TFP | −0,008 (ns) | −0,005 (ns) | +0,003 (ns) | −0,011 (ns) |
| Vốn trên lao động | −0,029\* | −0,022\*\* | −0,021\*\* | −0,053\*\*\* |

Kết luận chính: tác động qua TFP **không có ý nghĩa** ở bất kỳ phương pháp nào, còn tác động qua **vốn trên lao động** mạnh và vững, có ý nghĩa ở mọi phương pháp, kể cả FE. Nhân hệ số vốn trên lao động với α = 0,35, kênh vốn đóng góp khoảng 0,1–0,2 điểm tăng trưởng mỗi năm cho mỗi 10 điểm nợ; cộng với phần (không có ý nghĩa) qua TFP thì tổng khoảng 0,2–0,3 điểm, khớp với kết quả hồi quy tăng trưởng trực tiếp. Vốn con người không có tác động có ý nghĩa nên không được báo cáo.

**Hồi quy trực tiếp lên đầu tư** (% GDP):

| Phương pháp | Hệ số nợ đầu kỳ |
|---|---|
| BE | −0,099\*\* |
| OLS | −0,051\* |
| FE | −0,062\*\*\* |
| SGMM động | −0,038\* |
| Riêng nước phát triển | −0,041\* |
| Riêng nước mới nổi | −0,085\* |

Hệ số âm và có ý nghĩa ở mọi phương pháp: tăng 10 điểm nợ đi kèm đầu tư trong nước giảm khoảng 0,4 điểm phần trăm GDP. Tác động ở nước mới nổi gần gấp đôi nước phát triển.

**Biến động vĩ mô.** Một giả thuyết là nợ cao làm bất định và nguy cơ khủng hoảng tăng, nên kinh tế biến động mạnh hơn. Đồ thị phân tán cho tương quan dương nhẹ, nhưng hồi quy chỉ có ý nghĩa ở FE không có hiệu ứng thời gian; mọi đặc tả khác đều không có ý nghĩa. Bài kết luận không có quan hệ vững giữa nợ và biến động vĩ mô.

**Kiểm chứng riêng cho nước Mỹ.** Để kiểm tra độ lớn ước lượng bằng một con đường độc lập, bài làm phép tính cho Mỹ:

- *Tiền đề*: ở Mỹ, trong dài hạn mỗi đô la nợ chèn lấn đúng một đô la vốn (Elmendorf và Mankiw 1999).
- *Sản phẩm biên của vốn*: tỷ trọng thu nhập của vốn khoảng 1/3, tỷ lệ vốn trên sản lượng khoảng 3,7 (năm 2008), nên MPK = (1/3)/3,7 ≈ 9%. Elmendorf và Mankiw ước 9,5%; Caselli và Feyrer (2007) ước 11,4%.
- *Giả định*: nợ ròng trên GDP tăng 40 điểm trong năm năm, tương đương khoảng 6.450 tỷ USD (GDP thực 13,3 nghìn tỷ USD, nợ công do công chúng nắm giữ 40,8% GDP năm 2008, tăng trưởng thực bình quân 2%).
- *Kết quả*: với chèn lấn hoàn toàn, sản lượng giảm khoảng 4,4% tổng cộng, tương đương tăng trưởng chậm 0,8%, hay 0,2% mỗi năm cho mỗi 10 điểm nợ. Con số này trùng khớp với ước lượng kinh tế lượng.

Bài nói rõ đây là **cận trên**, vì phép tính có hai giả định ngầm: (1) nền kinh tế đóng, trong khi thực tế dòng vốn nước ngoài bù một phần chèn lấn; (2) tiết kiệm tư nhân không phản ứng, trong khi theo lập luận Ricardo, người dân có thể tiết kiệm thêm khi thấy chính phủ vay nhiều. Nới lỏng theo Gale và Orszag (2003), với tiết kiệm tư nhân bù 20% và vốn ngoại bù 25%, sản lượng chỉ giảm 2,6% thay vì 4,4%.

Tuy vậy, cũng có những tác động đi theo hướng ngược lại, làm thiệt hại lớn hơn: trong mô hình tăng trưởng nội sinh (Romer 1987), tích luỹ vốn kích thích tiến bộ công nghệ, nên chèn lấn vốn còn làm chậm công nghệ; và bất định cùng nguy cơ khủng hoảng cao cũng làm nản đầu tư. Bài kết luận phép tính là "xấp xỉ bậc nhất, dù vẫn thiên về cận trên".

### 7. Kết luận

Quan hệ nghịch giữa nợ đầu kỳ và tăng trưởng tiếp theo là vững qua nhiều phương pháp và nhiều kiểm tra: tăng 10 điểm phần trăm tỷ lệ nợ trên GDP đầu kỳ đi kèm tăng trưởng GDP thực bình quân đầu người chậm lại khoảng 0,2 điểm phần trăm mỗi năm; ở nước phát triển khoảng 0,15, ở nước mới nổi lớn hơn.

Có bằng chứng phi tuyến: chỉ mức nợ trên 90% GDP mới có tác động âm có ý nghĩa, và cùng một mức tăng tỷ lệ nợ thì nợ ban đầu càng cao càng gây hại.

Về kênh truyền dẫn, tác động xấu chủ yếu phản ánh năng suất lao động tăng chậm, do đầu tư giảm và vốn trên mỗi lao động tăng chậm lại, chứ không qua TFP. Tăng 10 điểm nợ đi kèm đầu tư giảm khoảng 0,4 điểm phần trăm GDP.

Hàm ý chính sách: không chỉ cần ổn định nợ công mà phải đưa nó vào quỹ đạo **giảm** trong trung và dài hạn.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Initial debt | Nợ đầu kỳ, dùng để tránh nhân quả ngược |
| Subsequent growth | Tăng trưởng tiếp theo, bình quân của kỳ năm năm sau |
| Reverse causality | Nhân quả ngược: tăng trưởng thấp gây nợ cao chứ không phải ngược lại |
| Simultaneity bias | Thiên lệch đồng thời |
| Endogeneity | Nội sinh: nợ và tăng trưởng cùng do biến thứ ba quyết định |
| Omitted-variables bias / heterogeneity bias | Thiên lệch do biến bị bỏ sót, còn gọi là thiên lệch dị biệt |
| Dynamic panel bias | Thiên lệch bảng động, làm FE lệch xuống |
| Errors in variables | Sai số đo lường trong biến giải thích |
| Between estimator (BE) | Ước lượng giữa nhóm: OLS trên số liệu đã lấy bình quân theo thời gian |
| Fixed effects (FE) | Hiệu ứng cố định, khử bằng phép trừ bình quân |
| System GMM (SGMM) | GMM hệ thống của Arellano-Bover và Blundell-Bond |
| Difference GMM (DGMM) | GMM sai phân, chỉ khai thác phương trình sai phân |
| Robust regression | Hồi quy bền vững, bỏ ngoại lai theo khoảng cách Cook và giảm trọng số phần dư lớn |
| Weak instruments | Công cụ yếu |
| Collapsed instrument matrix | Ma trận công cụ được "gộp" để giảm số công cụ |
| Hansen J-test | Kiểm định ràng buộc quá nhận dạng, xem công cụ có hợp lệ không |
| Arellano-Bond AR(2) test | Kiểm định tự tương quan bậc hai của sai số sai phân |
| Crowding out | Chèn lấn: nợ chính phủ đẩy vốn tư nhân ra |
| Debt overhang | Gánh nợ quá nặng làm mất động lực đầu tư |
| Threshold effect | Hiệu ứng ngưỡng |
| Growth accounting | Hạch toán tăng trưởng |
| Total factor productivity (TFP) | Năng suất nhân tố tổng hợp |
| Capital per worker | Vốn trên mỗi lao động |
| Capital income share | Tỷ trọng thu nhập của vốn, giả định 0,35 |
| Marginal product of capital (MPK) | Sản phẩm biên của vốn |
| Perpetual inventory method | Phương pháp kiểm kê vĩnh viễn để ước lượng vốn |
| Conditional convergence | Hội tụ có điều kiện |
| Fiscal volatility | Biến động tài khoá, đo bằng log độ lệch chuẩn tăng trưởng chi tiêu thực |
| Fiscal foresight | Tầm nhìn tài khoá |
| Ricardian argument | Lập luận Ricardo: tiết kiệm tư nhân tăng bù cho tiết kiệm công giảm |

## Câu nói đáng nhớ

> "On average, a 10 percentage point increase in the initial debt-to-GDP ratio is associated with a slowdown in annual real per capita GDP growth of around 0.2 percentage points per year, with the impact being smaller (around 0.15) in advanced economies."

> "There is some evidence of nonlinearity, with only high (above 90 percent of GDP) levels of debt having a significant negative effect on growth."

> "This adverse effect largely reflects a slowdown in labor productivity growth, mainly due to reduced investment and slower growth of the capital stock per worker."

> "They underline the need to take measures to not just stabilize public debts but to place them on a downward trajectory in the medium and long term."

## Đánh giá và phát hiện đáng chú ý

### Dùng nợ đầu kỳ chỉ chặn được một nửa vấn đề nhân quả ngược

Đây là điểm phải nói trước tiên, vì nó quyết định cách đọc toàn bộ phần còn lại. Tranh luận kinh điển về nợ và tăng trưởng có hai chiều: nợ cao làm tăng trưởng chậm, hay tăng trưởng chậm làm nợ cao? Bài chọn cách xử lý là dùng nợ **đầu kỳ** để giải thích tăng trưởng của **năm năm tiếp theo**, và tự nhận rằng cách này tránh được nhân quả ngược nhưng không giải quyết được nội sinh.

Lời thú nhận đó vẫn chưa đủ mạnh. Nợ đầu kỳ chỉ là biến ngoại sinh với tăng trưởng tương lai nếu tăng trưởng **không dai dẳng**. Nhưng tăng trưởng thì dai dẳng, và cơ chế là hiển nhiên: một nước tăng trưởng kém trong kỳ 1985–1990 sẽ vừa tích nợ tới 1990, vừa nhiều khả năng tiếp tục kém trong 1990–1995 vì những lý do chẳng liên quan gì tới nợ. Khi đó nợ đầu kỳ đơn giản là một chỉ báo cho tăng trưởng quá khứ, và hệ số âm chỉ đo tính dai dẳng của tăng trưởng. Mô hình có kiểm soát GDP bình quân đầu người đầu kỳ, nhưng đó là **mức**, không phải **tốc độ** — hai thứ hoàn toàn khác nhau.

Bảng mô tả ở phụ lục cung cấp bằng chứng mạnh nhất cho cách đọc này, và bài nêu nó rồi đi tiếp. Với nợ trên 60% GDP, nhóm nợ **đang tăng** cho tăng trưởng 1,4%/năm trên toàn mẫu và 0,7% ở nước đang phát triển, trong khi nhóm nợ **đang giảm** cho 3,1% và 3,0%. Cùng một mức nợ, chênh lệch hơn hai điểm phần trăm chỉ do hướng đi. Bài đọc đây là "hướng của nợ quan trọng không kém mức nợ". Nhưng có một cách đọc khác ít thuận lợi hơn nhiều: **nợ đang tăng chính là thứ xảy ra khi tăng trưởng đang sụp**, mẫu số co lại và thu ngân sách hụt. Nhóm "nợ cao và đang tăng" gần như là định nghĩa của nhóm "đang trong khủng hoảng". Cùng một dữ kiện, tuỳ chiều nhân quả mà đổi ý nghĩa hoàn toàn.

### Ước lượng được ưu tiên lại là ước lượng không đụng tới vấn đề nhận dạng

Bài chọn BE và SGMM làm ưu tiên, căn cứ mô phỏng Monte Carlo của Hauk–Wacziarg cho thấy BE có tổng thiên lệch nhỏ nhất. Lập luận này hợp lệ về mặt thống kê nhưng đáng bàn về mặt nội dung.

BE lấy bình quân theo thời gian rồi hồi quy chéo nước. Nghĩa là nó khai thác **hoàn toàn biến thiên giữa các nước**: nước nợ cao tăng trưởng chậm hơn nước nợ thấp. Nó không hề khử hiệu ứng cố định nước, tức là không hề xử lý khả năng có một đặc tính quốc gia bền vững — chất lượng thể chế, cơ cấu dân số, lịch sử lạm phát — vừa làm nợ cao vừa làm tăng trưởng chậm.

Ngược lại, FE là ước lượng duy nhất hỏi đúng câu hỏi chính sách: **khi nợ của chính nước này tăng lên, tăng trưởng của chính nước này có chậm lại không?** Và FE sụp đổ. Có hiệu ứng thời gian, hệ số còn −0,004 và mất ý nghĩa; trong đặc tả tiết giản nó thành **+0,010**, tức đổi dấu; trong hầu hết bảng phi tuyến nó không có ý nghĩa ở bất kỳ nhóm nợ nào. Bài giải thích bằng suy giảm do sai số đo và biến thiên trong nước bị co lại — lời giải thích này có cơ sở lý thuyết và không sai. Nhưng nó cũng là lời giải thích thuận tiện, và hệ quả vẫn còn nguyên: **kết quả của bài về cơ bản là một mệnh đề về loại nước, không phải một mệnh đề về hành vi của nợ**.

### Không có "vách đá 90%" — chính số liệu của bài bác bỏ điều mà bài được trích để ủng hộ

Kết luận "chỉ nợ trên 90% GDP mới có tác động âm có ý nghĩa" là câu được trích nhiều nhất, và nó đã đi vào diễn ngôn chính sách như một ngưỡng: dưới 90% thì an toàn, trên 90% thì nguy hiểm.

Chính bài này bác bỏ cách đọc đó. Khi tính tác động của một mức tăng 10% theo tỷ lệ, kết quả là một **dốc liên tục**: nhóm 30–60% cho −0,11 điểm, nhóm 60–90% cho −0,16 điểm, nhóm trên 90% cho −0,19 điểm. Giữa nhóm 60–90 và nhóm trên 90 chỉ chênh 0,03 điểm — không có bước nhảy nào cả. Cái gọi là ngưỡng 90% không xuất phát từ một đứt gãy kinh tế mà từ việc chỉ có hệ số của nhóm nợ cao mới vượt được ngưỡng ý nghĩa thống kê, trong khi hệ số nhóm 30–90 có độ lớn tương đương nhưng sai số chuẩn lớn hơn.

Phân biệt này rất quan trọng về mặt chính sách. "Có một vách đá ở 90%" hàm ý một nước ở mức 70% có thể yên tâm vay thêm. "Càng nợ càng hại, không có mốc nào" hàm ý chi phí biên của mỗi đồng vay là dương ở mọi mức, chỉ khác độ lớn. Bài ủng hộ mệnh đề thứ hai; thế giới chính sách đã trích nó cho mệnh đề thứ nhất. Ba năm sau, khi con số 90% của Reinhart–Rogoff bị phát hiện là sản phẩm của một lỗi bảng tính và lựa chọn trọng số, phần lớn cơn bão dư luận đổ vào bài đó — nhưng bài học phương pháp thì áp dụng cho cả hai: **một ngưỡng sinh ra từ việc chia nhóm tuỳ ý rồi kiểm định ý nghĩa không phải là một ngưỡng kinh tế**.

### Sự "trùng khớp" giữa mô phỏng cho nước Mỹ và kết quả kinh tế lượng có thể là dấu hiệu xấu

Phụ lục tính riêng cho Mỹ là phần đẹp nhất của bài về mặt trình bày, và đáng ngờ nhất về mặt suy luận. Với sản phẩm biên của vốn khoảng 9%, giả định chèn lấn hoàn toàn một đổi một, nợ ròng tăng 40 điểm GDP trong năm năm làm sản lượng giảm 4,4%, tương đương tăng trưởng chậm 0,2%/năm cho mỗi 10 điểm nợ. Con số này **trùng khớp** với ước lượng hồi quy, và bài trình bày sự trùng khớp như một xác nhận chéo.

Nhưng bài cũng nói rõ đây là **cận trên**, vì nó giả định nền kinh tế đóng và tiết kiệm tư nhân không phản ứng. Khi nới lỏng theo Gale–Orszag — tiết kiệm tư nhân bù 20%, vốn ngoại bù 25% — sản lượng chỉ giảm 2,6% thay vì 4,4%, tức khoảng 0,12%/năm cho mỗi 10 điểm nợ.

Vậy sự trùng khớp là giữa ước lượng kinh tế lượng và **kịch bản cực đoan nhất** của mô hình, chứ không phải kịch bản hợp lý nhất. Có hai cách hiểu. Hoặc còn những kênh ngoài chèn lấn cộng thêm vào — bất định, rủi ro khủng hoảng, ngoại tác của tích luỹ vốn theo mô hình nội sinh — đúng như bài gợi ý. Hoặc **bản thân ước lượng kinh tế lượng cũng là một cận trên**, vì nó chứa phần đóng góp của nhân quả ngược và biến bị bỏ sót. Bài chỉ trình bày cách hiểu thứ nhất.

### Kênh truyền dẫn được tìm thấy mâu thuẫn với chính lời giải thích về nước mới nổi

Phần hạch toán tăng trưởng cho một kết quả rất sạch: tác động của nợ đi qua **vốn trên lao động** (hệ số −0,021 tới −0,053, có ý nghĩa ở mọi phương pháp kể cả FE) chứ **không qua TFP** (không có ý nghĩa ở bất kỳ phương pháp nào). Hồi quy trực tiếp lên đầu tư xác nhận: tăng 10 điểm nợ đi kèm đầu tư giảm khoảng 0,4 điểm phần trăm GDP.

Đây là một kết quả có nội dung, vì nó loại bỏ nhánh giải thích kiểu "debt overhang" theo nghĩa méo mó động cơ và trì hoãn cải cách — những thứ sẽ hiện lên ở TFP. Cái còn lại là chèn lấn cổ điển: nhà nước vay nhiều, lãi suất lên, vốn tư nhân bị đẩy ra.

Nhưng chèn lấn đòi hỏi thị trường vốn **đóng**. Nếu vốn di chuyển tự do, tiết kiệm nước ngoài sẽ bù vào và cơ chế yếu đi. Vậy mà bài tìm thấy tác động ở nước mới nổi **gần gấp đôi** nước phát triển: −0,085 so với −0,041 với đầu tư, −0,036 so với −0,021 với tăng trưởng. Và bài giải thích bằng "năng lực vay hạn chế do thị trường tài chính trong nước kém phát triển và khả năng tiếp cận vốn quốc tế mong manh".

Lời giải thích đó mô tả một cơ chế khác hẳn. Tiếp cận vốn quốc tế mong manh không phải là chèn lấn — đó là **phần bù rủi ro và nguy cơ dừng đột ngột**, tức là một câu chuyện về khủng hoảng, không phải về lãi suất cân bằng dài hạn. Bài dùng kết quả TFP để loại bỏ kênh khủng hoảng, rồi lại dùng kênh khủng hoảng để giải thích kết quả khác biệt nhóm nước. Hai mảnh này không được nối lại với nhau.

### Biến số quyết định nhất với Việt Nam lại là biến mà bài cố tình không đưa vào

Bài dùng **nợ chính phủ gộp**, không phân biệt nợ đó đã mua gì. Điều này hoàn toàn chính đáng cho câu hỏi mà bài đặt ra, nhưng nó tạo ra một điểm mù lớn đúng ngay chỗ quan trọng nhất với một nước như Việt Nam.

Cơ chế mà bài tự tìm ra là qua vốn trên lao động. Nếu một đồng nợ tài trợ cho tiêu dùng công hoặc trợ cấp, nó giảm vốn trên lao động và cơ chế của bài hoạt động đúng như mô tả. Nhưng nếu một đồng nợ tài trợ cho một tuyến đường cao tốc hay một nhà máy điện được thực hiện với hiệu quả hợp lý, nó **làm tăng** vốn trên lao động, và dấu của tác động có thể đảo ngược. Chính cơ chế mà bài xác định là cơ chế hàm ý rằng thành phần của chi tiêu phải quan trọng — nhưng thiết kế của bài lại không cho phép kiểm tra điều đó.

Đây là chỗ mà tài liệu này cần được đọc cùng với nhánh về chất lượng và hiệu quả đầu tư công, và với tài liệu về tham nhũng và cơ cấu chi tiêu trong cùng thư mục: nếu hiệu quả đầu tư công thấp, một đồng vay chỉ tạo ra một phần tài sản thật, và phần còn lại hành xử đúng như nợ tài trợ tiêu dùng. Khi đó hệ số âm của bài áp dụng được. Nếu hiệu quả cao, nó không áp dụng được.

Với Việt Nam, nơi nợ công nằm khá xa mọi ngưỡng trong bài mà nhu cầu hạ tầng thì lớn, con số đáng theo dõi không phải là tỷ lệ nợ trên GDP mà là **tỷ lệ chuyển hoá từ đồng vay sang tài sản hạ tầng vận hành được**. Và cảnh báo có sức nặng nhất của bài với nhóm nước mới nổi không nằm ở hệ số tăng trưởng mà ở bảng mô tả đầu tư: ở nước mới nổi, đầu tư trong nước giảm từ 27,4% GDP ở nhóm nợ dưới 30% xuống 11,4% ở nhóm nợ trên 90% — **mất hơn một nửa**, trong khi ở nước phát triển con số gần như không đổi (32,0% xuống 29,4%). Chi phí thật của nợ cao ở một nước mới nổi không phải là vài phần mười điểm tăng trưởng; đó là việc mất khả năng đầu tư.
