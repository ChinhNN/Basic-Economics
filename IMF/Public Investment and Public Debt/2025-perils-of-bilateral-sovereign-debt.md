# The Perils of Bilateral Sovereign Debt — Hiểm hoạ của nợ chính phủ song phương

**Nguồn:** IMF Working Paper WP/25/235, tháng 11/2025, Vụ Nghiên cứu. Bản trước đó được lưu hành với tên "Central Bank Swap Lines as Bilateral Sovereign Debt".
**Tác giả:** Francisco Roldán, César Sosa-Padilla.
**Ý chính:** Hai thập kỷ qua xuất hiện nhiều chủ nợ chính thức mới nằm **ngoài Câu lạc bộ Paris**, trong đó Trung Quốc lớn nhất. Họ thường đòi **vị thế ưu tiên trên thực tế** so với chủ nợ tư nhân. Bài dựng một mô hình vỡ nợ chủ quyền trong đó chính phủ vay từ hai nguồn: **thị trường cạnh tranh** (trái phiếu dài hạn, có thể vỡ nợ) và **một chủ nợ lớn**. Khoản vay của chủ nợ lớn **không thể vỡ nợ**, **ngắn hạn**, và lãi suất do **thương lượng song phương** quyết định. Hình mẫu thực tế gần nhất là **hạn mức hoán đổi giữa các ngân hàng trung ương**. Kết quả chính: dù khoản vay song phương chỉ khoảng **3% GDP**, sự có mặt của chủ nợ lớn làm **tần suất vỡ nợ tăng từ 5,7% lên 13%**, chênh lệch lợi suất bình quân tăng **từ 714 lên 2.105 điểm cơ bản**, và phúc lợi **giảm 0,43% tiêu dùng**. Có hai kênh gây thiệt hại. Kênh thứ nhất: vay được trong lúc vỡ nợ làm vỡ nợ bớt đau. Kênh thứ hai, mới, là **"vay quá mức do quan hệ"**: chính phủ phát hành càng nhiều trái phiếu thị trường thì càng ở thế mạnh khi thương lượng và được chủ nợ lớn cho vay rẻ hơn, nên kỷ luật của chênh lệch lợi suất bị bào mòn. Nếu thay thương lượng bằng **quy tắc minh bạch**, trong đó lãi suất tăng theo quy mô khoản vay song phương, thì phúc lợi lại **tăng 0,21%**.

> **Lưu ý:** bản PDF đầy đủ. Một số điểm không khớp nội bộ:
> - Mục 5.2 nói khoản vay song phương bình quân là **3,3% thu nhập năm**, trong khi Bảng 2 và 3 ghi 3,02% GDP; hai con số có thể dùng cách lọc mẫu khác nhau.
> - Mục 5.3 gọi phương án hạn chế là "Unavailable", ở chỗ khác gọi là "Limited".
> - Bảng 1 ghi δ = 0,05 là "thời hạn của nợ", nhưng thực chất đó là tốc độ giảm dần của coupon.
> - Phụ lục nói mô hình với θ = 0 và β < β_L tái tạo Hatchondo, Martinez và Önder (2017), nhưng bài không báo cáo giá trị β_L trong hiệu chỉnh.
> - Chú thích Bảng 4 viết sai chính tả "biltaral".
> Các số trên hình là giá trị ước đọc.

## Sơ đồ

### Bằng chứng mở đầu

```text
       HÌNH 1 — NỢ CHÍNH THỨC NƯỚC NGOÀI CỦA CÁC THỊ TRƯỜNG MỚI NỔI
       (nghìn tỷ USD giá 2023, ước đọc)
       ┌──────────────────┬──────────┬──────────┐
       │                  │ 2000     │ 2023     │
       ├──────────────────┼──────────┼──────────┤
       │ tổng             │ ~1,2     │ ~1,6     │
       │ IMF + World Bank │ ~0,4     │ ~0,6     │
       │ đa phương khác   │ ~0,2     │ ~0,5     │
       │ Câu lạc bộ Paris │ ~0,5     │ ~0,25    │
       │ ★ Trung Quốc     │ ~0       │ ~0,15    │
       │ song phương khác │ ~0,1     │ ~0,1     │
       └──────────────────┴──────────┴──────────┘
       ★ chủ nợ song phương: dưới 1/6 → khoảng 1/3 tổng nợ chính thức
       ★ Trung Quốc là chủ nợ song phương lớn nhất
       ⚠ HẠN MỨC HOÁN ĐỔI của ngân hàng trung ương thường KHÔNG nằm
         trong số liệu nợ công và nợ được bảo lãnh → hình còn đánh
         giá thấp; lãi suất, kỳ hạn thường được giữ BÍ MẬT
```

### Ba giả định then chốt về chủ nợ lớn

```text
       ┌───────────────────────────┬──────────────────────────────┐
       │ THỊ TRƯỜNG CẠNH TRANH     │ ★ CHỦ NỢ LỚN (song phương)   │
       ├───────────────────────────┼──────────────────────────────┤
       │ có thể vỡ nợ              │ ① KHÔNG thể vỡ nợ (ưu tiên)  │
       │ trái phiếu dài hạn        │ ② NGẮN HẠN, tái tục mỗi kỳ   │
       │ giá do cạnh tranh, lợi    │ ③ lãi suất do THƯƠNG LƯỢNG   │
       │ nhuận bằng 0              │   Nash, θ = sức mạnh của chủ │
       │                           │   nợ                         │
       └───────────────────────────┴──────────────────────────────┘
       ★ hình mẫu: hạn mức HOÁN ĐỔI giữa các ngân hàng trung ương —
         ngắn hạn, chưa từng bị vỡ nợ (kể cả khi tái cơ cấu nợ thị
         trường), điều khoản do đàm phán
       so sánh: IMF (phụ phí theo ngưỡng), hoán đổi của Fed (+25 bp,
         công bố công khai) → điều khoản CỐ ĐỊNH TRƯỚC
       ⚠ chủ nợ lớn được giả định chỉ vì LỢI NHUẬN, cùng sở thích với
         nhà đầu tư thị trường → để tách riêng tác động của CẤU TRÚC
         THỊ TRƯỜNG; kết quả vẫn giữ trừ khi chủ nợ rất muốn tránh
         vỡ nợ trên nợ thị trường
```

### Bước một: chỉ có khoản vay song phương

```text
       mỗi kỳ hai bên thương lượng: khoản chuyển x và khoản vay mới m'
       điểm đe doạ = trả hết m ngay
       lãi suất ngầm r: x = m'/(1 + r) − m
       θ = 0,5 · β = β_L (tách khỏi động cơ vay trước)
       ═══════════════════════════════════════════════════════════
       ★★ CHIẾN LƯỢC CỦA CHỦ NỢ (Hình 2, 4)
       nợ THẤP, thu nhập THẤP → lãi suất TRỢ GIÁ, thậm chí ÂM (~−7%)
          │ để kéo con nợ vào mức nợ cao
          ▼
       nợ CAO → trả hết khó → điểm đe doạ yếu → lãi TĂNG (~5–15%)
       ═══════════════════════════════════════════════════════════
       ★ hàm giá trị của chủ nợ LỒI theo m → chủ nợ trung tính rủi ro
         lại hành xử như ƯA RỦI RO: "đánh cược vào tình trạng nợ
         đè nặng"; lỗ nếu thu nhập con nợ hồi phục nhanh và trả hết
         trước khi kịp tăng lãi
       ★ θ = 0 (con nợ nắm hết sức mạnh): lãi luôn bằng lãi phi rủi
         ro, không trợ giá, không tăng lãi
       ─────────────────────────────────────────────────────────
       HAI BÀI HỌC
       ① lãi thương lượng tăng mạnh khi điểm đe doạ của con nợ đắt;
          không cần giả định "không thể vỡ nợ" cho kết quả này
       ② kỳ vọng lợi nhuận sau này → lãi thấp hôm nay → nợ tích tụ
```

### Mô hình đầy đủ

```text
       TRÌNH TỰ TRONG MỘT KỲ (khi không vỡ nợ)
       (b, m, z) ─▶ BUỔI SÁNG: quyết định vỡ nợ → phát hành b'
                 ─▶ BUỔI CHIỀU: thương lượng với chủ nợ lớn → (x, m')
                 ─▶ tiêu dùng ─▶ (b', m', z')
       ═══════════════════════════════════════════════════════════
       nợ thị trường: vĩnh viễn, coupon giảm dần theo (1 − δ)
       vỡ nợ: xoá toàn bộ trái phiếu, bị loại khỏi thị trường, quay lại
         với xác suất ψ, sản lượng mất ξ(z); cú sốc sở thích kiểu
         Extreme Value cho xác suất vỡ nợ trơn
       vay song phương khi đang vỡ nợ: m' ≤ Γ(m, z)
         KHÔNG HẠN CHẾ: Γ = +∞
         HẠN CHẾ: Γ = 0 → vỡ nợ thị trường thì phải trả hết cho chủ
           nợ lớn
       ═══════════════════════════════════════════════════════════
       ★ ĐIỂM MẤU CHỐT: dòng tiền ròng từ thị trường B(b', b, m, z) =
         q·(b' − (1 − δ)b) − κb đi thẳng vào điểm đe doạ
       vừa phát hành NHIỀU → tiền mặt nhiều → trả m dễ → thế MẠNH
       đang GIẢM nợ → tiền mặt ít → thế YẾU → lãi song phương cao
```

### Hiệu chỉnh

```text
       theo quý · phần lớn tham số lấy từ Roch và Roldán (2023), hiệu
       chỉnh cho vỡ nợ Argentina 2001
       ┌──────────────────────────────┬──────────┐
       │ β (chiết khấu chính phủ)     │ 0,9504   │
       │ γ (ngại rủi ro)              │ 2        │
       │ χ (cú sốc sở thích)          │ 0,025    │
       │ ★ θ (sức mạnh chủ nợ lớn)    │ 0,5      │
       │ r* (lãi phi rủi ro)          │ 0,01     │
       │ δ (tốc độ giảm coupon)       │ 0,05     │
       │ ρz · σz                      │ 0,9484 · 0,02 │
       │ ψ (xác suất quay lại)        │ 0,0385   │
       │ chi phí vỡ nợ d₀ · d₁        │ −0,24 · 0,3 │
       └──────────────────────────────┴──────────┘
```

### Kết quả định lượng

```text
       ★★ BẢNG 2, 3 và 4
       ┌───────────────────┬──────┬───────┬───────┬───────┬───────┬───────┐
       │                   │ CHỈ  │ KHÔNG │ KHÔNG │ HẠN   │ QUY   │ QUY   │
       │                   │ THỊ  │ HẠN   │ HẠN   │ CHẾ   │ TẮC   │ TẮC   │
       │                   │TRƯỜNG│ CHẾ   │ CHẾ   │ θ=0,5 │ THEO  │ KÍCH  │
       │                   │      │θ=0,25 │ θ=0,5 │       │ QUY MÔ│ RỦI RO│
       ├───────────────────┼──────┼───────┼───────┼───────┼───────┼───────┤
       │ chênh lệch bq (bp)│ 714  │ 1.613 │★2.105 │ 1.038 │ ★ 623 │ 921   │
       │ độ lệch chuẩn (bp)│ 399  │ 927   │ 1.331 │ 612   │ 315   │ 552   │
       │ nợ/GDP (%)        │ 22,5 │ 21,7  │ 21,2  │ 22,5  │ 23,5  │ 22,8  │
       │ vay song phương/  │ 0    │ 3,4   │ 3,02  │ 1,06  │ 0,71  │ 0,97  │
       │ GDP (%)           │      │       │       │       │       │       │
       │ chênh lệch vay    │ —    │ −52,5 │ −429  │ 536   │ 682   │ 1.264 │
       │ song phương (bp)  │      │       │       │       │       │       │
       │ tương quan vay và │ —    │ 61,7  │ 67,5  │ 71,1  │ 62,5  │ 48,1  │
       │ chênh lệch (%)    │      │       │       │       │       │       │
       │ tần suất vỡ nợ (%)│ 5,72 │ 11    │ ★ 13  │ 7,72  │ ★5,13 │ 6,92  │
       │ PHÚC LỢI          │ —    │−0,15% │★−0,43%│−0,2%  │★+0,21%│−0,079%│
       └───────────────────┴──────┴───────┴───────┴───────┴───────┴───────┘
       ★★★ ĐỌC BẢNG NÀY
       ① khoản vay song phương NHỎ (~3% GDP, một bậc độ lớn dưới nợ
          thị trường) nhưng làm tần suất vỡ nợ GẤP ĐÔI và chênh lệch
          GẤP BA
       ② kể cả khi chính phủ có sức mạnh thương lượng khá (θ = 0,25)
          vẫn THIỆT → chính phủ thà KHÔNG có chủ nợ lớn
       ③ cấm vay khi vỡ nợ: dùng giảm hơn 2/3, thiệt hại giảm một nửa
          nhưng VẪN ÂM
       ④ thay thương lượng bằng quy tắc lãi TĂNG THEO QUY MÔ khoản vay
          → vỡ nợ và chênh lệch THẤP hơn cả khi chỉ có thị trường,
          chính phủ LỢI, chủ nợ vẫn có lãi (lãi ≥ r*)
       ⑤ quy tắc lãi GIẢM khi nợ thị trường tăng ("kích rủi ro") → tái
          tạo gần đúng kết quả thương lượng → THIỆT
       ─────────────────────────────────────────────────────────
       ★ vì sao khoản vay nhỏ lại có tác động lớn: nợ thị trường DÀI
         HẠN nên mỗi kỳ chỉ trả một phần nhỏ, còn khoản vay song phương
         NGẮN HẠN phải trả hay tái tục toàn bộ mỗi kỳ → biến động lãi
         song phương tác động lên ngân sách kỳ này ngang biến động lãi
         trên một khối nợ thị trường lớn hơn nhiều
```

### Quanh các lần vỡ nợ

```text
       HÌNH 6 — KHÔNG HẠN CHẾ (ước đọc)
       ┌─────────────────┬──────────────────┬───────────────────┐
       │                 │ 2 năm TRƯỚC      │ lúc VỠ NỢ và sau  │
       ├─────────────────┼──────────────────┼───────────────────┤
       │ vay song phương │ ~3,4% thu nhập   │ ★ ~5,5%           │
       │ (% thu nhập năm)│                  │                   │
       │ lãi song phương │ ~−1% đến 0       │ ★ ~19–20%         │
       └─────────────────┴──────────────────┴───────────────────┘
       → trước vỡ nợ: vay song phương để TRÁNH hoặc HOÃN vỡ nợ, được
         trợ giá; hình KHÔNG thể hiện những lần vỡ nợ đã tránh được
       → khi vỡ nợ: lãi vọt lên, chủ nợ thu lời trong suốt thời gian
         bị loại khỏi thị trường
       ★ HÌNH 14: quay lại thị trường là phát hành trái phiếu NGAY để
         trả hết khoản vay song phương → chủ nợ cược rằng thu nhập
         KHÔNG hồi phục và thời gian bị loại DÀI
```

### Giá nợ và vùng vỡ nợ

```text
       HÌNH 7 — NỢ/GDP TẠI ĐÓ XÁC SUẤT VỠ NỢ VƯỢT 50% (ước đọc)
       chỉ thị trường, hạn chế: ~17% (z thấp) → ~39% (z cao)
       ★ không hạn chế: thấp hơn ~1–2 điểm → gánh được ÍT nợ hơn
       ═══════════════════════════════════════════════════════════
       HÌNH 8 — GIÁ TRÁI PHIẾU q khi b' thấp (ước đọc)
       chỉ thị trường ~0,88 · hạn chế ~0,81 · ★ không hạn chế ~0,69
       ★★ phương án HẠN CHẾ không đổi quyết định vỡ nợ kỳ tới, NHƯNG
          giá vẫn THẤP hơn → vì chính sách VAY TƯƠNG LAI thay đổi →
          tăng PHA LOÃNG NỢ
       ═══════════════════════════════════════════════════════════
       HÌNH 9 — PHÂN BỐ NỢ/GDP: có vay song phương (cả hai phương án)
         → nền kinh tế ở LÂU HƠN trong vùng nợ cao, rủi ro vỡ nợ lớn
         (đỉnh dời từ ~24% sang ~27–28%)
       HÌNH 12 — hàm giá trị: chính phủ muốn vay song phương BỊ CẤM
         lúc vỡ nợ, trừ khi sắp vỡ nợ ngay kỳ này
```

### Vay quá mức do quan hệ

```text
       HÌNH 10 — LỢI NHUẬN CHỦ NỢ LỚN theo nợ thị trường b
       ★ TĂNG theo b khi rủi ro còn vừa phải: chênh lệch mở rộng →
         chủ nợ có giá trị hơn với chính phủ → thặng dư lớn hơn
       nợ quá cao: hạn chế → lợi nhuận GIẢM (vỡ nợ thì phải trả hết m);
         không hạn chế → lợi nhuận TĂNG vọt (thu được nhiều lúc vỡ nợ)
       nợ an toàn: chủ nợ chẳng có gì hơn thị trường để bán
       ═══════════════════════════════════════════════════════════
       ★★ HÌNH 11 — lãi song phương theo b' (phương án hạn chế)
       b' ≈ 0 → ~8–15% · b' ≈ 0,7 trở lên → ~0%
       → lãi song phương GIẢM MẠNH khi nợ thị trường TĂNG
       ═══════════════════════════════════════════════════════════
       PHƯƠNG TRÌNH EULER CHO NỢ THỊ TRƯỜNG
       lợi ích biên của thêm một trái phiếu:
         chỉ thị trường ··· u'(c)·(q + ∂q/∂b'·i)
                            (∂q/∂b' < 0 → KỶ LUẬT của chênh lệch)
         ★ có chủ nợ lớn ·· u'(c)·(q + ∂q/∂b'·i + ∂x/∂b')
                            ∂x/∂b' > 0 = vay nhiều ngoài thị trường
                            → được chủ nợ lớn chuyển nhiều hơn, rẻ hơn
       → ★★ ĐỘ CO GIÃN CHÉO NỘI SINH của điều khoản song phương theo
          nợ thị trường ĐỐI TRỌNG với kỷ luật thị trường → vay nhiều
          hơn, giảm đòn bẩy chậm hơn → vỡ nợ nhiều hơn, chênh lệch cao
          hơn, phúc lợi thấp hơn
       ★ ngoài ra m' đổi theo b' → ảnh hưởng q' và x' kỳ sau qua
         quy tắc dây chuyền
```

### Phép thử cho nhà hoạch định chính sách

```text
       quy tắc: r(b', m') = max{r*, α₀ + α_b·b' + α_m·m'}
       ┌──────────────────────────┬───────────────────────────────┐
       │ α_b < 0 (lãi GIẢM khi nợ │ ⚠ kích vay quá mức → THIỆT    │
       │ thị trường tăng)         │                               │
       │ α_m > 0, α_b = 0 (lãi    │ ✔ vỡ nợ ít hơn, chênh lệch    │
       │ TĂNG theo quy mô khoản   │   thấp hơn → LỢI cho cả hai   │
       │ vay song phương)         │   bên                         │
       └──────────────────────────┴───────────────────────────────┘
       ★★ PHÉP THỬ ĐƠN GIẢN: điều khoản song phương có TỐT LÊN khi nợ
          (hay chênh lệch) thị trường tăng không?
          CÓ → vay quá mức do quan hệ → nhiều khả năng hại phúc lợi
          tốt lên khi nợ THẤP → hỗ trợ bền vững nợ
       ═══════════════════════════════════════════════════════════
       HÀM Ý
       ① hạn chế vay song phương trong lúc vỡ nợ → tăng phúc lợi (khớp
          chính sách Bảo đảm Tài trợ và Nợ quá hạn của IMF)
       ② quy tắc tài khoá hạn chế vay thị trường càng có lợi với nước
          tiếp cận được loại nợ song phương này
       ③ điều khoản MINH BẠCH, theo QUY TẮC tốt hơn đàm phán bí mật
       ⚠ tranh luận thường chỉ nhìn GIÁ khoản vay và VỊ THẾ ƯU TIÊN;
         thiệt hại chính lại đến từ ĐỘNG CƠ lệch lạc, kể cả khi chính
         phủ có quyền không vay nếu điều khoản không hấp dẫn
```

## Ba câu hỏi bài viết trả lời

1. Khi chính phủ có thêm một chủ nợ song phương lớn, ưu tiên và thương lượng điều khoản riêng, bên cạnh thị trường trái phiếu, thì rủi ro vỡ nợ và phúc lợi thay đổi thế nào?
2. Vì sao một khoản vay song phương nhỏ lại có thể làm chính phủ vay quá mức trên thị trường?
3. Thiết kế nào của khoản vay song phương có thể có lợi cho nước đi vay, và làm sao nhận biết một chủ nợ hay công cụ mới có khả năng gây hại?

## Khái niệm cần biết

**Nợ chính thức và nợ song phương (official debt, bilateral debt).** Nợ chính thức là khoản một chính phủ vay từ các chủ nợ không phải tư nhân: chính phủ nước khác, ngân hàng trung ương nước khác, ngân hàng phát triển, hay tổ chức đa phương như IMF và Ngân hàng Thế giới. Nợ song phương là phần nợ chính thức vay trực tiếp từ **một** chính phủ hay ngân hàng trung ương khác, theo thoả thuận hai bên. Ví dụ trong bài: tỷ trọng của chủ nợ song phương trong nợ chính thức của các nước mới nổi đã tăng từ dưới một phần sáu lên khoảng một phần ba trong giai đoạn 2000–2023, với Trung Quốc là chủ nợ song phương lớn nhất. Khái niệm này quan trọng vì toàn bộ bài hỏi việc có thêm một chủ nợ song phương lớn làm nước đi vay lợi hay thiệt.

**Câu lạc bộ Paris (Paris Club).** Nhóm các nước chủ nợ chính thức truyền thống, chủ yếu là các nước phát triển, phối hợp với nhau khi một nước đi vay cần tái cơ cấu nợ. Ví dụ trong bài: nợ của các nước mới nổi với Câu lạc bộ Paris giảm từ khoảng 0,5 nghìn tỷ đô la năm 2000 xuống khoảng 0,25 nghìn tỷ năm 2023, trong khi nợ với Trung Quốc tăng từ gần 0 lên khoảng 0,15 nghìn tỷ. Khái niệm này quan trọng vì các chủ nợ mới nằm ngoài nhóm này không phải tuân theo cách phối hợp chung của nó.

**Hạn mức hoán đổi giữa các ngân hàng trung ương (central bank swap line).** Thoả thuận trong đó một ngân hàng trung ương cho ngân hàng trung ương khác vay ngoại tệ trong thời gian ngắn, đổi lại bằng nội tệ của bên vay. Ví dụ trong bài: hạn mức hoán đổi của Cục Dự trữ Liên bang Mỹ (Fed) có lãi suất cố định trước và công bố công khai, cộng thêm 25 điểm cơ bản; trong khi nhiều hạn mức khác có lãi suất và kỳ hạn được giữ bí mật. Khái niệm này quan trọng vì đây là hình mẫu thực tế gần nhất với "chủ nợ lớn" trong mô hình: ngắn hạn, chưa từng bị vỡ nợ, điều khoản do đàm phán.

**Chênh lệch lợi suất và điểm cơ bản (spread, basis point).** Chênh lệch lợi suất là phần lãi mà chính phủ phải trả cao hơn lãi suất phi rủi ro, để bù cho nhà đầu tư rủi ro bị vỡ nợ. Một điểm cơ bản bằng 0,01 điểm phần trăm, nên 100 điểm cơ bản bằng 1 điểm phần trăm. Ví dụ trong bài: khi chỉ vay trên thị trường, chênh lệch bình quân là 714 điểm cơ bản (tức khoảng 7,1 điểm phần trăm); khi có chủ nợ lớn, nó lên 2.105 điểm cơ bản (khoảng 21 điểm phần trăm). Khái niệm này quan trọng vì chênh lệch là thước đo rủi ro và cũng là cái "phạt" mà thị trường áp lên chính phủ vay nhiều.

**Thương lượng Nash và điểm đe doạ (Nash bargaining, threat point).** Khi hai bên thương lượng, họ chia phần lợi ích chung (thặng dư) theo sức mạnh thương lượng của mỗi bên. Điểm đe doạ là điều xảy ra nếu đàm phán đổ vỡ; bên nào có điểm đe doạ tốt hơn thì đàm phán ở thế mạnh hơn. Trong bài, sức mạnh của chủ nợ lớn ký hiệu là θ: θ = 0,5 nghĩa là hai bên chia đôi thặng dư, θ = 0 nghĩa là chính phủ đi vay nắm toàn bộ sức mạnh. Điểm đe doạ của chính phủ là trả hết khoản vay song phương ngay lập tức. Ví dụ minh hoạ: nếu chính phủ đang có sẵn nhiều tiền mặt thì việc trả hết khoản vay là dễ, nên lời đe doạ "tôi sẽ trả hết và không vay anh nữa" là đáng tin, và chủ nợ phải giảm lãi. Khái niệm này quan trọng vì toàn bộ cơ chế gây hại trong bài đi qua điểm đe doạ.

**Vị thế ưu tiên (seniority).** Một chủ nợ được ưu tiên nghĩa là được trả trước các chủ nợ khác, kể cả khi chính phủ vỡ nợ với các chủ nợ còn lại. Bài giả định khoản vay của chủ nợ lớn **không thể vỡ nợ**: chính phủ có thể vỡ nợ với trái phiếu thị trường, nhưng không với chủ nợ lớn. Ví dụ trong bài: hạn mức hoán đổi chưa từng bị vỡ nợ, kể cả khi các nước tái cơ cấu nợ thị trường. Khái niệm này quan trọng vì vị thế ưu tiên là lý do chủ nợ lớn không cần đòi phần bù rủi ro vỡ nợ, nên mọi phần lãi cao hơn lãi phi rủi ro đều đến từ thương lượng.

**Pha loãng nợ (debt dilution).** Khi chính phủ phát hành thêm trái phiếu, khả năng trả các trái phiếu cũ giảm đi, nên giá trị của trái phiếu cũ giảm. Ví dụ minh hoạ: một nhà đầu tư mua trái phiếu khi nợ là 20% GDP; nếu năm sau chính phủ vay thêm tới 30% GDP, rủi ro vỡ nợ tăng và trái phiếu của người đó mất giá. Nhà đầu tư lường trước điều này nên trả giá thấp ngay từ đầu. Khái niệm này quan trọng vì bài cho thấy chủ nợ lớn làm giá trái phiếu giảm qua chính kênh này.

**Phúc lợi quy ra tiêu dùng tương đương (consumption-equivalent welfare).** Cách đo một thay đổi chính sách tốt hay xấu bằng câu hỏi: người dân sẵn sàng mất bao nhiêu phần trăm tiêu dùng mỗi năm, vĩnh viễn, để tránh (hay để có) thay đổi đó. Ví dụ trong bài: có chủ nợ lớn với θ = 0,5 làm phúc lợi giảm 0,43%, tức tương đương mất 0,43% tiêu dùng mỗi năm mãi mãi. Khái niệm này quan trọng vì đây là con số tổng kết cho câu hỏi "có chủ nợ lớn thì lợi hay thiệt".

## Nội dung chi tiết

### 1. Mở đầu

Một phần lớn khoản vay của các chính phủ ở thị trường mới nổi là nợ chính thức, tức vay từ chính phủ khác, từ ngân hàng phát triển khu vực hay từ tổ chức đa phương. Cơ cấu chủ nợ chính thức đã thay đổi đáng kể trong hai thập kỷ. Số liệu nợ chính thức nước ngoài của các nước mới nổi (nghìn tỷ đô la theo giá năm 2023, giá trị ước đọc từ hình):

| Chủ nợ | Năm 2000 | Năm 2023 |
|---|---|---|
| Tổng | khoảng 1,2 | khoảng 1,6 |
| IMF và Ngân hàng Thế giới | khoảng 0,4 | khoảng 0,6 |
| Đa phương khác | khoảng 0,2 | khoảng 0,5 |
| Câu lạc bộ Paris | khoảng 0,5 | khoảng 0,25 |
| Trung Quốc | gần 0 | khoảng 0,15 |
| Song phương khác | khoảng 0,1 | khoảng 0,1 |

Tỷ trọng của chủ nợ song phương đi từ dưới một phần sáu lên khoảng một phần ba tổng nợ chính thức, và Trung Quốc đã trở thành chủ nợ song phương lớn nhất. Các chủ nợ mới nằm ngoài Câu lạc bộ Paris thường đòi vị thế ưu tiên trên thực tế so với chủ nợ tư nhân, và điều này làm dấy lên lo ngại về phúc lợi của nước đi vay.

Bài cũng lưu ý rằng con số trên còn đánh giá thấp nợ song phương, vì hạn mức hoán đổi của ngân hàng trung ương thường không nằm trong số liệu nợ công và nợ được chính phủ bảo lãnh, và lãi suất cũng như kỳ hạn của chúng thường được giữ bí mật.

**Lập luận cốt lõi.** Lãi suất mà chủ nợ lớn đòi bị giới hạn bởi sự cạnh tranh ngầm từ thị trường: nếu đòi quá cao, chính phủ sẽ vay trên thị trường thay vì vay chủ nợ lớn. Nhưng khi rủi ro vỡ nợ đẩy lợi suất thị trường lên, phương án thay thế của chính phủ trở nên đắt, và chủ nợ lớn có thể đòi một phần bù. Vì khoản vay của chủ nợ lớn không có rủi ro vỡ nợ, phần bù này không phản ánh rủi ro mà chỉ phản ánh việc phương án thay thế của con nợ tệ đến đâu.

Bài chỉ ra hai lý do nước đi vay bị thiệt:

1. **Lý do quen thuộc:** nếu chính phủ vẫn vay được từ chủ nợ lớn trong lúc bị thị trường loại ra sau vỡ nợ, thì vỡ nợ bớt đau, tức giá trị của việc vỡ nợ tăng lên, và chính phủ dễ vỡ nợ hơn.
2. **Lý do căn bản hơn, và mới:** ngay cả khi cấm vay song phương lúc vỡ nợ, hiệu ứng **vay quá mức do quan hệ** vẫn làm phúc lợi giảm.

Thặng dư của quan hệ song phương lớn nhất khi chính phủ đang phải trả chênh lệch lợi suất cao trên thị trường, tức đúng lúc chính phủ cần chủ nợ lớn nhất. Vì vậy, khi chủ nợ dự kiến chính phủ sẽ gặp chênh lệch cao trong tương lai, họ đánh giá quan hệ cao hơn và sẵn sàng "đầu tư" vào quan hệ bằng cách cho vay rẻ hơn hôm nay.

Tham số then chốt là sức mạnh thương lượng. Khi chính phủ nắm hết sức mạnh (θ = 0), chủ nợ lớn chỉ cho vay ở lãi phi rủi ro; mô hình khi đó trở về kết quả của Hatchondo, Martinez và Önder (2017), và chính phủ được lợi. Nhưng lợi ích này biến mất nhanh khi sức mạnh của chính phủ giảm.

**Ba giả định then chốt về chủ nợ lớn.** Mô hình đặt hai loại chủ nợ cạnh nhau:

| Thị trường cạnh tranh | Chủ nợ lớn (song phương) |
|---|---|
| Chính phủ có thể vỡ nợ | Thứ nhất: không thể vỡ nợ, tức có vị thế ưu tiên |
| Trái phiếu dài hạn | Thứ hai: ngắn hạn, phải tái tục mỗi kỳ |
| Giá do cạnh tranh quyết định, nhà đầu tư có lợi nhuận kỳ vọng bằng 0 | Thứ ba: lãi suất do thương lượng Nash quyết định, θ là sức mạnh của chủ nợ |

Hình mẫu thực tế là hạn mức hoán đổi giữa các ngân hàng trung ương: ngắn hạn, chưa từng bị vỡ nợ kể cả khi nước đi vay tái cơ cấu nợ thị trường, và điều khoản do đàm phán. Để so sánh, IMF áp phụ phí theo ngưỡng định sẵn, còn hạn mức hoán đổi của Fed có lãi cộng 25 điểm cơ bản được công bố công khai; đó là những khoản vay có điều khoản cố định trước, không thương lượng.

Bài giả định chủ nợ lớn chỉ quan tâm đến lợi nhuận và có cùng sở thích với nhà đầu tư thị trường. Mục đích là tách riêng tác động của **cấu trúc thị trường** (một chủ nợ thương lượng, ưu tiên, ngắn hạn), không gán thêm động cơ chính trị nào. Kết quả vẫn giữ được, trừ khi chủ nợ lớn rất muốn tránh việc chính phủ vỡ nợ với nợ thị trường.

### 2. Vị trí trong tài liệu

Bài đóng góp vào nhánh nghiên cứu mới về tương tác giữa các loại nợ chủ quyền khác nhau:

- Hatchondo, Martinez và Önder cho thấy thêm một lượng giới hạn nợ không thể vỡ giúp tăng phúc lợi, nhưng chỉ tạm thời.
- Cordella và Powell cho thấy vị thế ưu tiên của các tổ chức tài chính quốc tế có thể hình thành một cách nội sinh.
- Nhiều nghiên cứu khác xét nợ ưu tiên đi kèm điều kiện chính sách, hoặc vai trò của cho vay chính thức trong việc loại bỏ đa cân bằng (tình huống nền kinh tế có thể rơi vào một cuộc tháo chạy tự thực hiện chỉ vì nhà đầu tư lo sợ).

Mô hình của bài cố ý không có đa cân bằng. Đây là điểm cần nhớ, vì đa cân bằng chính là thứ có thể mở đường cho lợi ích của khoản vay song phương: nếu khoản vay loại bỏ được cân bằng xấu, nó có thể có lợi. Bài cũng bỏ qua yếu tố điều kiện chính sách để tập trung vào thiết kế thị trường.

Arellano và Barreto cho thấy định giá cạnh tranh và kỳ hạn dài, như các khoản vay của Câu lạc bộ Paris, làm nợ chính thức ít rủi ro hơn. Liu, Liu và Yue cho thấy cân bằng tốt nhất khi có cả chủ nợ thị trường, song phương và đa phương có thể đạt được phân bổ hiệu quả trong giới hạn ràng buộc. Các bài này nhấn mạnh thể chế có thể cải thiện phúc lợi; bài này thì minh hoạ mặt hiểm hoạ.

Bài thừa nhận mô hình không mô tả mọi khía cạnh của hạn mức hoán đổi: không có khác biệt giữa các đồng tiền, không có điều kiện về dự trữ hay tài sản bảo đảm. Nó cũng coi nợ là công cụ làm mượt tiêu dùng qua các thời kỳ, không xét tài trợ dự án hay cho vay phát triển.

### 3. Mô hình chỉ có vay song phương

Để hiểu cơ chế, bài bắt đầu từ một mô hình đơn giản hơn: một nền kinh tế mở nhỏ nhận thu nhập ngẫu nhiên và chỉ vay từ một chủ nợ độc quyền. Vì khoản vay là ngắn hạn, thực chất nó được thương lượng lại liên tục mỗi kỳ.

Mỗi kỳ, hai bên thương lượng về hai thứ: khoản chuyển giao x trong kỳ và khoản vay mới m'. Điểm đe doạ của chính phủ là trả hết khoản nợ cũ m ngay lập tức. Lãi suất ngầm r được suy ra từ hệ thức x = m'/(1 + r) − m: chủ nợ đưa cho chính phủ giá trị hiện tại của khoản vay mới, trừ đi khoản nợ cũ. Trong phần này bài đặt θ = 0,5 và cho hệ số chiết khấu của chính phủ β = β_L, để tách riêng cơ chế thương lượng khỏi động cơ muốn vay trước của chính phủ nóng vội.

Về hành vi, nền kinh tế giảm nợ khi thu nhập cao và nhận tiền từ chủ nợ khi thu nhập thấp. Chủ nợ dùng lãi suất để chiếm thặng dư, theo một chiến lược hai giai đoạn:

| Tình trạng của con nợ | Lãi suất chủ nợ đặt ra | Lý do |
|---|---|---|
| Nợ thấp, thu nhập thấp | Trợ giá, thậm chí âm, khoảng −7% | Để kéo con nợ vào mức nợ cao |
| Nợ cao | Tăng lên khoảng 5–15% | Trả hết trở nên khó, điểm đe doạ của con nợ yếu |

Khi nợ tăng, lời đe doạ "trả hết" của con nợ kém đáng tin. Thặng dư của quan hệ tăng, nhưng đồng thời chủ nợ cũng mạnh hơn trong thương lượng. Hai điều này cộng lại làm hàm giá trị (lợi nhuận) của chủ nợ **lồi** theo quy mô khoản vay m: lợi nhuận tăng nhanh dần khi nợ tăng. Hệ quả là một chủ nợ trung tính với rủi ro lại hành xử như một người ưa rủi ro, mà bài gọi là "đánh cược vào tình trạng nợ đè nặng". Chủ nợ lỗ nếu thu nhập của con nợ hồi phục nhanh và con nợ trả hết trước khi chủ nợ kịp tăng lãi.

Để đối chiếu: khi θ = 0, tức con nợ nắm hết sức mạnh thương lượng, lãi suất luôn bằng lãi phi rủi ro, không có trợ giá và cũng không có tăng lãi.

Phần này cho hai bài học:

1. Lãi suất do thương lượng tăng mạnh khi điểm đe doạ của con nợ trở nên đắt. Kết quả này không cần đến giả định "không thể vỡ nợ".
2. Kỳ vọng thu được lợi nhuận sau này khiến chủ nợ đặt lãi thấp hôm nay, và vì vậy nợ tích tụ.

### 4. Mô hình đầy đủ

Trong mô hình đầy đủ, chính phủ vay từ hai nguồn: chủ nợ lớn và nhóm chủ nợ cạnh tranh trên thị trường. Chính phủ có thể vỡ nợ với nợ thị trường và khi đó chịu chi phí sản lượng theo cách chuẩn trong tài liệu; khoản vay song phương thì không thể vỡ nợ.

**Trình tự trong một kỳ** (khi không vỡ nợ). Trạng thái đầu kỳ gồm nợ thị trường b, nợ song phương m và thu nhập z.

1. **Buổi sáng:** chính phủ quyết định có vỡ nợ không, và nếu không thì phát hành trái phiếu, đưa nợ thị trường lên b'.
2. **Buổi chiều:** chính phủ thương lượng với chủ nợ lớn, quyết định khoản chuyển giao x và khoản vay mới m'.
3. Chính phủ tiêu dùng, và nền kinh tế bước sang kỳ sau với trạng thái (b', m', z').

Giá trái phiếu phản ánh kỳ vọng của nhà đầu tư về cả quyết định vỡ nợ lẫn kết quả thương lượng trong tương lai.

**Đặc điểm của nợ thị trường và vỡ nợ.**

- Nợ thị trường là trái phiếu vĩnh viễn với coupon giảm dần theo tỷ lệ (1 − δ) mỗi kỳ; nhờ vậy mỗi kỳ chỉ một phần nhỏ đến hạn, giống nợ dài hạn.
- Khi vỡ nợ, toàn bộ trái phiếu được xoá, chính phủ bị loại khỏi thị trường, quay lại thị trường với xác suất ψ mỗi kỳ, và trong thời gian bị loại chịu mất sản lượng ξ(z).
- Bài thêm một cú sốc sở thích theo phân phối giá trị cực trị (Extreme Value) để xác suất vỡ nợ thay đổi trơn tru thay vì nhảy bậc, giúp giải mô hình.

**Vay song phương khi đang vỡ nợ.** Bài xét hai phương án qua giới hạn m' ≤ Γ(m, z):

- **Không hạn chế:** Γ = +∞, tức chính phủ vẫn vay được từ chủ nợ lớn trong lúc vỡ nợ với thị trường.
- **Hạn chế:** Γ = 0, tức nếu vỡ nợ với thị trường thì phải trả hết cho chủ nợ lớn.

**Điểm mấu chốt.** Dòng tiền ròng mà chính phủ thu từ thị trường trong kỳ là B(b', b, m, z) = q·(b' − (1 − δ)b) − κb, tức tiền bán trái phiếu mới trừ đi phần coupon phải trả. Dòng tiền này đi thẳng vào điểm đe doạ trong cuộc thương lượng buổi chiều. Nếu chính phủ vừa phát hành nhiều, họ có nhiều tiền mặt, trả hết m dễ dàng, nên ở thế mạnh và được lãi song phương thấp. Nếu chính phủ đang giảm nợ thị trường, tiền mặt ít, trả hết m khó, nên ở thế yếu và phải chịu lãi song phương cao.

### 5. Kết quả định lượng

**Hiệu chỉnh.** Mô hình theo quý. Phần lớn tham số lấy từ Roch và Roldán (2023), vốn được hiệu chỉnh để tái tạo vụ vỡ nợ của Argentina năm 2001.

| Tham số | Giá trị |
|---|---|
| β, hệ số chiết khấu của chính phủ | 0,9504 |
| γ, mức ngại rủi ro | 2 |
| χ, độ lớn cú sốc sở thích | 0,025 |
| θ, sức mạnh thương lượng của chủ nợ lớn | 0,5 |
| r*, lãi suất phi rủi ro | 0,01 |
| δ, tốc độ giảm coupon | 0,05 |
| ρz và σz, độ bền và độ biến động của thu nhập | 0,9484 và 0,02 |
| ψ, xác suất quay lại thị trường mỗi quý | 0,0385 |
| d₀ và d₁, tham số chi phí vỡ nợ | −0,24 và 0,3 |

**Kết quả chính.** Bảng dưới so sánh sáu kịch bản: chỉ có thị trường; có chủ nợ lớn không hạn chế với θ = 0,25 và θ = 0,5; có chủ nợ lớn bị hạn chế (cấm vay lúc vỡ nợ) với θ = 0,5; và hai quy tắc lãi suất cố định thay cho thương lượng (sẽ giải thích ở mục 6).

| Chỉ tiêu | Chỉ thị trường | Không hạn chế, θ = 0,25 | Không hạn chế, θ = 0,5 | Hạn chế, θ = 0,5 | Quy tắc theo quy mô | Quy tắc kích rủi ro |
|---|---|---|---|---|---|---|
| Chênh lệch bình quân (điểm cơ bản) | 714 | 1.613 | 2.105 | 1.038 | 623 | 921 |
| Độ lệch chuẩn chênh lệch (điểm cơ bản) | 399 | 927 | 1.331 | 612 | 315 | 552 |
| Nợ thị trường/GDP (%) | 22,5 | 21,7 | 21,2 | 22,5 | 23,5 | 22,8 |
| Vay song phương/GDP (%) | 0 | 3,4 | 3,02 | 1,06 | 0,71 | 0,97 |
| Chênh lệch lãi vay song phương (điểm cơ bản) | không có | −52,5 | −429 | 536 | 682 | 1.264 |
| Tương quan giữa vay song phương và chênh lệch (%) | không có | 61,7 | 67,5 | 71,1 | 62,5 | 48,1 |
| Tần suất vỡ nợ (%) | 5,72 | 11 | 13 | 7,72 | 5,13 | 6,92 |
| Phúc lợi so với chỉ thị trường | không có | −0,15% | −0,43% | −0,2% | +0,21% | −0,079% |

Đọc bảng theo năm ý:

1. Khoản vay song phương nhỏ, khoảng 3% GDP, thấp hơn nợ thị trường một bậc độ lớn, nhưng làm tần suất vỡ nợ **gấp đôi** (từ 5,72% lên 13%) và chênh lệch lợi suất **gấp ba** (từ 714 lên 2.105 điểm cơ bản). Chênh lệch cũng biến động hơn nhiều, dù nợ thị trường thấp hơn đôi chút (21,2% so với 22,5%).
2. Kể cả khi chính phủ có sức mạnh thương lượng khá (θ = 0,25), họ vẫn thiệt (−0,15%). Tức là chính phủ thà **không có** chủ nợ lớn.
3. Cấm vay song phương trong lúc vỡ nợ làm lượng vay giảm hơn hai phần ba (từ 3,02% xuống 1,06% GDP) và thiệt hại phúc lợi giảm khoảng một nửa (từ −0,43% còn −0,2%), nhưng phúc lợi **vẫn âm**.
4. Thay thương lượng bằng quy tắc lãi suất tăng theo quy mô khoản vay song phương làm vỡ nợ và chênh lệch **thấp hơn cả khi chỉ có thị trường** (5,13% so với 5,72%; 623 so với 714 điểm cơ bản). Chính phủ được lợi (+0,21%) và chủ nợ vẫn có lãi vì lãi suất không bao giờ thấp hơn r*.
5. Quy tắc lãi suất giảm khi nợ thị trường tăng ("kích rủi ro") tái tạo gần đúng kết quả của thương lượng và gây thiệt (−0,079%).

**Vì sao khoản vay nhỏ lại có tác động lớn.** Nợ thị trường là dài hạn, nên mỗi kỳ chính phủ chỉ phải trả một phần nhỏ. Khoản vay song phương là ngắn hạn, nên mỗi kỳ phải trả hay tái tục **toàn bộ**. Vì vậy, một thay đổi lãi suất trên khoản vay song phương tác động lên ngân sách kỳ này ngang với một thay đổi lãi suất trên một khối nợ thị trường lớn hơn nhiều lần. Ví dụ minh hoạ: nếu nợ thị trường là 21% GDP và mỗi quý chỉ khoảng 5% số đó đến hạn (khoảng 1% GDP), thì khoản vay song phương 3% GDP phải tái tục toàn bộ lại lớn gấp ba phần nợ thị trường phải tái cấp vốn trong quý.

**Quanh các lần vỡ nợ.** Khoản vay song phương được dùng nhiều nhất quanh thời điểm vỡ nợ. Trong kịch bản không hạn chế (giá trị ước đọc từ hình):

| | Khoảng 2 năm trước vỡ nợ | Lúc vỡ nợ và sau đó |
|---|---|---|
| Vay song phương (% thu nhập năm) | khoảng 3,4% | khoảng 5,5% |
| Lãi suất song phương | khoảng −1% đến 0 | khoảng 19–20% |

Trước vỡ nợ, chính phủ dùng khoản vay song phương để tránh hoặc hoãn vỡ nợ, và khoản vay được trợ giá. Cần lưu ý rằng bức tranh này chỉ gồm những lần vỡ nợ thực sự xảy ra, không cho thấy những lần vỡ nợ đã được tránh nhờ khoản vay. Khi vỡ nợ, lãi suất song phương vọt lên, và chủ nợ thu lời trong suốt thời gian chính phủ bị loại khỏi thị trường. Khi chính phủ quay lại thị trường, việc đầu tiên là phát hành trái phiếu ngay để trả hết khoản vay song phương đắt đỏ. Như vậy, khi cho vay lúc vỡ nợ, chủ nợ đang cược rằng thu nhập của con nợ **không** hồi phục nhanh và thời gian bị loại khỏi thị trường kéo dài.

**Khi cấm vay song phương lúc vỡ nợ.** Lượng vay giảm hơn hai phần ba, vì việc phải trả hết khi vỡ nợ trở thành một chi phí vỡ nợ bổ sung, khiến chính phủ dè dặt hơn. Khoản vay vẫn được dùng chủ yếu khi chênh lệch cao, và phúc lợi vẫn giảm, dù ít hơn nhiều.

**Giá nợ và vùng vỡ nợ** (giá trị ước đọc từ hình):

- **Mức nợ tại đó xác suất vỡ nợ vượt 50%:** khi chỉ có thị trường hoặc khi bị hạn chế, ngưỡng này đi từ khoảng 17% GDP (thu nhập thấp) tới khoảng 39% GDP (thu nhập cao). Khi không hạn chế, ngưỡng thấp hơn khoảng 1–2 điểm phần trăm, tức nền kinh tế gánh được ít nợ hơn.
- **Giá trái phiếu q khi mức nợ mới b' thấp:** khoảng 0,88 khi chỉ có thị trường, khoảng 0,81 khi bị hạn chế, và chỉ khoảng 0,69 khi không hạn chế.

Điểm tinh tế là phương án hạn chế gần như không thay đổi quyết định vỡ nợ trong kỳ tới, **nhưng giá trái phiếu vẫn thấp hơn**. Lý do là chính sách vay mượn trong tương lai thay đổi: nhà đầu tư dự kiến chính phủ sẽ vay nhiều hơn về sau, làm pha loãng giá trị của trái phiếu họ đang mua.

- **Phân bố dài hạn của nợ trên GDP:** khi có vay song phương (cả hai phương án), nền kinh tế ở lâu hơn trong vùng nợ cao, nơi rủi ro vỡ nợ lớn; đỉnh của phân bố dời từ khoảng 24% sang khoảng 27–28% GDP.
- **Chính phủ muốn tự trói tay:** so sánh hàm giá trị cho thấy chính phủ muốn việc vay song phương lúc vỡ nợ bị cấm, trừ khi họ sắp vỡ nợ ngay trong kỳ này.

### 6. Lập trình cho chủ nợ lớn

**Vay quá mức do quan hệ: cơ chế.** Trước khi đến các quy tắc, cần hiểu vì sao thương lượng gây hại ngay cả khi đã cấm vay lúc vỡ nợ.

Lợi nhuận của chủ nợ lớn thay đổi theo mức nợ thị trường b. Khi rủi ro còn vừa phải, lợi nhuận **tăng** theo b: nợ thị trường cao hơn thì chênh lệch rộng hơn, chủ nợ lớn có giá trị hơn với chính phủ, và thặng dư để chia lớn hơn. Khi nợ quá cao, hai phương án tách ra: nếu bị hạn chế, lợi nhuận **giảm**, vì vỡ nợ thì chính phủ phải trả hết m và chủ nợ mất quan hệ; nếu không hạn chế, lợi nhuận **tăng vọt**, vì chủ nợ thu được nhiều trong lúc vỡ nợ. Khi nợ ở mức an toàn, chủ nợ chẳng có gì hơn thị trường để "bán".

Trong phương án hạn chế, lãi suất song phương phụ thuộc mạnh vào mức nợ thị trường mới b' (giá trị ước đọc): khi b' gần 0, lãi khoảng 8–15%; khi b' từ khoảng 0,7 trở lên, lãi gần 0%. Tức là lãi song phương **giảm mạnh khi nợ thị trường tăng**.

Phương trình Euler (điều kiện tối ưu khi phát hành thêm một trái phiếu) cho thấy hệ quả:

- **Chỉ có thị trường:** lợi ích biên của thêm một trái phiếu là u'(c)·(q + ∂q/∂b'·i). Vì ∂q/∂b' < 0 (vay thêm thì giá trái phiếu giảm), số hạng này là **kỷ luật của chênh lệch**: chính phủ phải chịu ngay cái giá của việc vay nhiều.
- **Có chủ nợ lớn:** lợi ích biên trở thành u'(c)·(q + ∂q/∂b'·i + ∂x/∂b'). Số hạng mới ∂x/∂b' > 0 nghĩa là vay nhiều hơn trên thị trường thì được chủ nợ lớn chuyển cho nhiều hơn, rẻ hơn.

Độ co giãn chéo nội sinh này, tức điều khoản song phương tốt lên khi nợ thị trường tăng, **đối trọng với kỷ luật thị trường**. Chính phủ vay nhiều hơn, giảm đòn bẩy chậm hơn, dẫn tới vỡ nợ nhiều hơn, chênh lệch cao hơn và phúc lợi thấp hơn. Ngoài ra, khoản vay song phương m' cũng thay đổi theo b', và điều này ảnh hưởng tới giá trái phiếu q' và khoản chuyển giao x' của kỳ sau theo quy tắc dây chuyền.

**Quy tắc thay cho thương lượng.** Bài thay thương lượng bằng một quy tắc lãi suất cố định, tuyến tính theo nợ thị trường và khoản vay song phương, có sàn ở lãi phi rủi ro để chủ nợ không bao giờ lỗ:

r(b', m') = max{r*, α₀ + α_b·b' + α_m·m'}

| Dạng quy tắc | Kết quả |
|---|---|
| **Kích rủi ro:** α_b < 0, lãi giảm khi nợ thị trường tăng | Tái tạo động thái của thương lượng, kích thích vay quá mức, gây thiệt |
| **Phụ thuộc quy mô:** α_m > 0 và α_b = 0, lãi tăng theo quy mô khoản vay song phương, không gắn với nợ thị trường | Vỡ nợ ít hơn, chênh lệch thấp hơn, có lợi cho cả hai bên |

Quy tắc phụ thuộc quy mô cải thiện phúc lợi của chính phủ trong khi chủ nợ vẫn có lợi nhuận. Đây là một **cải thiện Pareto**: có người lợi mà không ai thiệt.

**Phép thử đơn giản cho nhà hoạch định chính sách.** Hãy hỏi: điều khoản song phương có **tốt lên** khi nợ hoặc chênh lệch lợi suất thị trường tăng không? Nếu có, đó là dấu hiệu của vay quá mức do quan hệ và khoản vay nhiều khả năng gây hại phúc lợi. Nếu điều khoản tốt lên khi nợ **thấp**, chủ nợ đang hỗ trợ bền vững nợ.

### 7. Kết luận

Hai nguồn vốn, thị trường và chủ nợ lớn, liên kết chặt với nhau, dù khoản vay từ chủ nợ lớn nhỏ hơn nợ thị trường một bậc độ lớn.

Riêng độ co giãn chéo của điều khoản song phương theo nợ thị trường đã đủ để khuyến khích vay quá mức, tăng rủi ro và giảm phúc lợi. Thiệt hại có thể xảy ra ngay cả khi chính phủ được tự do không vay nếu điều khoản không đủ hấp dẫn. Có thêm một nguồn vay vì thế không nhất thiết có lợi: khoản vay song phương có thể giúp tránh vỡ nợ, nhưng cũng có thể khiến vỡ nợ dễ xảy ra hơn.

Ba hàm ý chính sách:

1. Hạn chế vay song phương trong lúc vỡ nợ sẽ tăng phúc lợi. Điều này khớp với chính sách Bảo đảm Tài trợ và Nợ quá hạn của IMF.
2. Quy tắc tài khoá hạn chế vay trên thị trường càng có lợi với những nước tiếp cận được loại nợ song phương này, vì nó thay thế phần kỷ luật thị trường đã bị bào mòn.
3. Điều khoản song phương minh bạch, theo quy tắc định sẵn, tốt hơn đàm phán bí mật.

Bài nhấn mạnh rằng tranh luận chính sách thường chỉ nhìn vào **giá** của khoản vay song phương và **vị thế ưu tiên** của chủ nợ. Theo mô hình, thiệt hại chính lại đến từ **động cơ lệch lạc** mà quan hệ thương lượng tạo ra cho chính phủ đi vay, và thiệt hại này xảy ra kể cả khi chính phủ có quyền từ chối vay nếu điều khoản không hấp dẫn.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Bilateral sovereign debt | Nợ chủ quyền song phương, vay từ một chính phủ hay ngân hàng trung ương khác |
| Official debt | Nợ chính thức, từ chính phủ và tổ chức đa phương |
| Paris Club | Câu lạc bộ Paris, nhóm chủ nợ chính thức phối hợp tái cơ cấu |
| De facto seniority | Vị thế ưu tiên trên thực tế |
| Central bank swap line | Hạn mức hoán đổi giữa các ngân hàng trung ương |
| Large lender | Chủ nợ lớn, độc quyền, thương lượng điều khoản |
| Competitive fringe | Nhóm chủ nợ cạnh tranh trên thị trường |
| Nash bargaining | Thương lượng Nash, chia thặng dư theo sức mạnh θ |
| Threat point | Điểm đe doạ, kết quả khi thương lượng đổ vỡ |
| Implicit interest rate | Lãi suất ngầm của khoản vay thương lượng |
| Gamble for debt overhang | Đánh cược vào tình trạng nợ đè nặng |
| Relational overborrowing | Vay quá mức do quan hệ song phương |
| Cross-elasticity | Độ co giãn chéo của điều khoản song phương theo nợ thị trường |
| Market discipline of spreads | Kỷ luật thị trường qua chênh lệch lợi suất |
| Debt dilution | Pha loãng nợ, phát hành thêm làm giảm giá trị nợ cũ |
| Geometrically decaying perpetuity | Trái phiếu vĩnh viễn có coupon giảm dần |
| Exclusion, reentry probability | Bị loại khỏi thị trường, xác suất quay lại |
| Ergodic distribution | Phân bố dừng dài hạn |
| Consumption-equivalent welfare | Phúc lợi quy ra tiêu dùng tương đương |
| Risk-inducing rule, size-dependent rule | Quy tắc kích rủi ro, quy tắc phụ thuộc quy mô |
| Financing Assurances and Sovereign Arrears | Chính sách Bảo đảm Tài trợ và Nợ quá hạn của IMF |
| Pareto improvement | Cải thiện Pareto, có người lợi mà không ai thiệt |

## Câu nói đáng nhớ

> "Increasing the amount of sources of indebtedness is not necessarily beneficial for the borrowing government."

> "When the large lender expects the government to face high spreads in the future, it values the relationship more and is willing to invest in it by lending more cheaply."

> "Bilateral loans whose interest rate is expected to be strongly decreasing in the amount (or spreads) of marketable debt will induce relational overborrowing and are thus likely to hurt welfare."

## Đánh giá và phát hiện đáng chú ý

### Tên bài chỉ sai người: thủ phạm không phải "song phương" mà là "thương lượng"

Bài mở đầu bằng sự trỗi dậy của các chủ nợ chính thức ngoài Câu lạc bộ Paris, với Trung Quốc là lớn nhất, và kết thúc bằng một kết luận về hiểm hoạ của nợ song phương. Nhưng nếu đọc kỹ cơ chế, đối tượng thực sự bị buộc tội lại khác.

Chính bài chỉ ra rằng hạn mức hoán đổi của Cục Dự trữ Liên bang Mỹ có **điều khoản cố định trước và công bố công khai** — cộng 25 điểm cơ bản — và rằng IMF áp phụ phí theo ngưỡng định sẵn. Đó cũng là các khoản vay song phương và đa phương ngắn hạn, ưu tiên, không thể vỡ nợ. Chúng thoả mọi đặc điểm cấu trúc của mô hình trừ một: **lãi suất không do thương lượng quyết định**.

Và đúng đặc điểm đó là nguồn gốc của toàn bộ thiệt hại. Khi bài thay thương lượng bằng một quy tắc minh bạch trong đó lãi suất tăng theo quy mô khoản vay song phương, phúc lợi chuyển từ **−0,43% lên +0,21%**, tần suất vỡ nợ từ 13% xuống **5,13% — thấp hơn cả kịch bản chỉ có thị trường (5,72%)** — và chủ nợ vẫn có lãi.

Vậy mệnh đề đúng không phải "nợ song phương nguy hiểm" mà là "**điều khoản được thương lượng lại mỗi kỳ trong bí mật thì nguy hiểm, bất kể ai là chủ nợ**". Đây là một cách phát biểu vừa chính xác hơn vừa hữu ích hơn về mặt chính sách, vì nó chỉ ra một biến số có thể thay đổi được — thiết kế hợp đồng — thay vì một đặc điểm không thể thay đổi là danh tính của chủ nợ.

### Kết quả sâu nhất: kết cục thương lượng không nằm trên biên Pareto

Đây là phát hiện mà bài nêu rồi đi tiếp, dù nó đảo ngược toàn bộ khung diễn giải thông thường về quan hệ chủ nợ–con nợ.

Trong cách hiểu quen thuộc, một chủ nợ song phương có sức mạnh thương lượng sẽ chiếm phần lớn thặng dư: con nợ thiệt, chủ nợ lợi, tổng thể là chuyển giao. Nhưng con số của bài không nói vậy. Dưới quy tắc phụ thuộc quy mô, **cả hai bên đều tốt hơn** so với kết cục thương lượng — bài gọi thẳng đó là một cải thiện Pareto.

Nghĩa là quan hệ song phương đang vận hành ở một điểm mà không ai muốn. Lý do là kinh điển: **bất nhất thời gian**. Chủ nợ không thể cam kết trước rằng mình sẽ không tăng lãi khi con nợ rơi vào thế yếu. Biết vậy, con nợ điều chỉnh hành vi vay mượn theo hướng làm cả hai cùng thiệt. Mỗi kỳ, mỗi bên hành động tối ưu, và kết quả tổng hợp là tệ hơn cho tất cả.

Hàm ý chính sách từ đây xây dựng hơn nhiều so với cảnh báo ở phần kết. Nếu cả chủ nợ lẫn con nợ đều muốn một quy tắc mà không bên nào tự cam kết được, thì có chỗ cho một **bên thứ ba**: một chuẩn công bố thông tin, một bộ quy tắc ứng xử đa phương, hoặc đơn giản là yêu cầu ghi nhận mọi hạn mức hoán đổi và thoả thuận song phương ngắn hạn vào thống kê nợ công. Vai trò của bên thứ ba không phải trừng phạt ai mà là **làm cho cam kết trở nên khả thi**. Đây là lập luận mạnh nhất có thể rút ra từ bài, và nó không được phát biểu.

### Cơ chế vay quá mức do quan hệ là một đóng góp thật, và nó tổng quát hơn phạm vi bài

Phương trình Euler là chỗ để nhìn thấy điều mới. Khi chỉ có thị trường, lợi ích biên của việc phát hành thêm một trái phiếu là u'(c)·(q + ∂q/∂b'·i), trong đó ∂q/∂b' < 0 chính là **kỷ luật của chênh lệch lợi suất**: vay thêm thì giá trái phiếu giảm, và chính phủ phải chịu cái giá đó ngay.

Khi có chủ nợ lớn, xuất hiện thêm số hạng ∂x/∂b' > 0. Phát hành nhiều trái phiếu thị trường làm chính phủ **có nhiều tiền mặt hơn trong tay khi bước vào bàn đàm phán**, do đó điểm đe doạ mạnh hơn, do đó được chủ nợ lớn cho vay rẻ hơn. Đối trọng này bào mòn kỷ luật thị trường.

Điều đáng nói là cơ chế này không đòi hỏi bất kỳ giả định nào về động cơ chính trị, về tài sản bảo đảm, hay về ý đồ chiến lược của chủ nợ. Bài giả định chủ nợ lớn **chỉ quan tâm lợi nhuận và có cùng sở thích với nhà đầu tư thị trường**, đúng để tách riêng tác động của cấu trúc thị trường. Thiệt hại vẫn xuất hiện. Đây là điểm mạnh về mặt lập luận: nó cho thấy vấn đề nằm ở kiến trúc của quan hệ, không ở phẩm chất của các bên.

Cũng vì thế, cơ chế này áp dụng rộng hơn phạm vi mà bài nhắm tới. Bất kỳ chủ nợ nào có **giá trị tăng lên khi con nợ gặp khó khăn** đều tạo ra cùng độ co giãn chéo đó — kể cả một ngân hàng trong nước độc quyền cấp tín dụng cho một chính quyền địa phương, hay một định chế chính sách là người mua cuối cùng cho trái phiếu doanh nghiệp nhà nước.

### Chủ nợ trở thành kẻ cho vay nặng lãi, và vì sao 3% GDP đủ gây hại

Mô tả hành vi của chủ nợ trong mô hình đáng được đọc chậm. Khi nợ và thu nhập của con nợ còn thấp, chủ nợ cho vay ở lãi suất **trợ giá, có khi âm tới khoảng −7%**, để kéo con nợ vào vùng nợ cao. Khi nợ đã cao và việc trả hết trở nên khó, điểm đe doạ của con nợ yếu đi và lãi suất được đẩy lên **5–15%**. Quanh thời điểm vỡ nợ, lãi suất song phương vọt lên **khoảng 19–20%** và chủ nợ thu lời suốt thời gian con nợ bị loại khỏi thị trường.

Hàm giá trị của chủ nợ lồi theo quy mô khoản vay, nên một chủ nợ **trung tính với rủi ro lại hành xử như một người ưa rủi ro** — bài gọi đó là "đánh cược vào tình trạng nợ đè nặng". Chủ nợ lỗ nếu con nợ phục hồi nhanh và trả hết trước khi kịp nâng lãi.

Đây là một mô tả gọn ghẽ của cấu trúc cho vay săn mồi, và điều khiến nó đáng chú ý là nó **xuất hiện nội sinh** từ một bài toán tối đa hoá lợi nhuận thuần tuý. Không cần giả định bất kỳ ý đồ nào. Hệ quả phân phối thì rõ: lợi nhuận của chủ nợ được tối đa hoá đúng ở những trạng thái mà phúc lợi của con nợ ở mức thấp nhất. Quan hệ này mang tính đối kháng đúng vào lúc con nợ cần nó nhất.

Con số gây ấn tượng nhất của bài là sự mất cân xứng: một khoản vay song phương trung bình chỉ khoảng **3% GDP**, tức nhỏ hơn nợ thị trường một bậc độ lớn, nhưng làm tần suất vỡ nợ tăng **từ 5,7% lên 13%** và chênh lệch lợi suất từ **714 lên 2.105 điểm cơ bản**.

Lời giải thích của bài rất đáng nhớ và có giá trị thực tiễn trực tiếp. Nợ thị trường trong mô hình là dài hạn với coupon giảm dần, nên mỗi kỳ chỉ một phần nhỏ đến hạn. Khoản vay song phương thì **ngắn hạn và phải tái tục toàn bộ mỗi kỳ**. Vì thế biến động lãi suất trên 3% GDP nợ ngắn hạn tác động lên ngân sách kỳ này ngang với biến động lãi suất trên một khối nợ thị trường lớn hơn nhiều lần.

Từ đó rút ra một chỉ báo rủi ro rất cụ thể: **mức nguy hiểm của một khoản vay tỷ lệ với tần suất phải quay vòng nó, không tỷ lệ với dư nợ**. Một hạn mức hoán đổi 90 ngày trị giá 2% GDP có thể nguy hiểm hơn một khoản vay ưu đãi 30 năm trị giá 10% GDP. Không một thước đo nợ trên GDP thông dụng nào nắm được sự phân biệt này.

### Phép thử khó dùng ở nơi cần nó nhất, và trọng lượng đúng của các con số

Bài kết thúc bằng một chỉ báo chẩn đoán đơn giản và thông minh: **điều khoản song phương có tốt lên khi nợ hoặc chênh lệch lợi suất thị trường tăng không?** Nếu có, đó là dấu hiệu của vay quá mức do quan hệ và nhiều khả năng gây hại phúc lợi. Nếu điều khoản tốt lên khi nợ thấp, đó là chủ nợ đang hỗ trợ bền vững nợ.

Phép thử này chỉ cần dữ liệu chuỗi thời gian về lãi suất song phương và chênh lệch thị trường, nên về nguyên tắc là rẻ.

Vấn đề nằm ở chính điều bài ghi nhận ngay từ hình đầu tiên: hạn mức hoán đổi của ngân hàng trung ương **thường không nằm trong số liệu nợ công và nợ được bảo lãnh**, và lãi suất cùng kỳ hạn thường được **giữ bí mật**. Nghĩa là dữ liệu cần thiết để chạy phép thử bị giấu chính xác ở những quan hệ có nhiều khả năng thất bại phép thử nhất.

Đây không phải một sơ suất của bài mà là một vòng lặp kín trong thực tế: các thoả thuận có động cơ lệch lạc nhất là các thoả thuận có điều khoản bảo mật chặt nhất, vì chính sự bảo mật là điều kiện để thương lượng lại từng kỳ diễn ra. Nó củng cố lập luận rằng yêu cầu công bố là biện pháp chính sách có tỷ suất cao nhất — cao hơn bất kỳ hạn mức hay quy tắc định lượng nào.

Đây là một mô hình định lượng được hiệu chỉnh, không phải bằng chứng thực nghiệm, và ba hạn chế cần nhớ khi trích dẫn.

**Tham số quyết định nhất được giả định chứ không ước lượng.** Sức mạnh thương lượng θ được đặt bằng 0,5. Kết quả cực kỳ nhạy với nó: ở θ = 0 con nợ được lợi và mô hình quay về kết quả trước đó trong tài liệu; ở θ = 0,25 phúc lợi giảm 0,15%; ở θ = 0,5 giảm 0,43%. Con số "0,43% tiêu dùng" được trích trong phần tóm tắt vì thế là hàm của một tham số không có neo thực nghiệm nào. Bài trung thực khi trình bày cả dải, nhưng dải đó cần đi kèm mỗi lần con số được nhắc.

**Lợi ích lớn nhất của cho vay chính thức bị giả định đi.** Mô hình không có đa cân bằng. Nhưng lập luận cổ điển bênh vực hạn mức hoán đổi và cho vay của IMF chính là loại bỏ các cuộc tháo chạy tự thực hiện — tức loại bỏ cân bằng xấu. Một mô hình gạt kênh đó ra rồi kết luận rằng cho vay chính thức gây hại đang trả lời một câu hỏi hẹp hơn nhiều so với tiêu đề gợi ý. Bài thừa nhận điều này ở phần điểm tài liệu.

**Nợ được mô hình hoá như công cụ làm mượt tiêu dùng, không phải tài trợ dự án.** Bài nói rõ điều này. Nó có nghĩa là toàn bộ kênh thứ hai của nợ song phương trong thực tế — tài trợ hạ tầng có ràng buộc mua sắm từ nhà thầu của nước cho vay, với các vấn đề về giá thành và chuyển giao công nghệ — nằm ngoài phạm vi hoàn toàn.

### Với Việt Nam: đúng cơ chế, nhưng có thể sai loại nợ

Hàm ý cho Việt Nam cần được tách làm hai phần, vì phần lớn nợ song phương của Việt Nam **không** thuộc loại mà mô hình mô tả.

**Phần không áp dụng.** Các khoản vay ODA và vay ưu đãi từ các đối tác song phương truyền thống có đặc điểm ngược hẳn với chủ nợ lớn trong mô hình: kỳ hạn rất dài, lãi suất cố định và công bố, điều khoản không thương lượng lại từng kỳ. Theo chính logic của bài, đó là cấu hình lành tính — thậm chí là cấu hình mà bài khuyến nghị. Rủi ro thật của nhóm này nằm ở chỗ khác, ở ràng buộc mua sắm và ở chất lượng dự án, và mô hình không nói gì về điều đó.

**Phần áp dụng.** Cảnh báo của bài nhắm vào các công cụ ngắn hạn, thương lượng và bảo mật: hạn mức hoán đổi song phương, các thoả thuận thanh khoản khu vực, và các khoản vay thương mại có bảo lãnh nhà nước với điều khoản không công bố. Ba hàm ý cụ thể:

**Ghi nhận và công bố theo kỳ hạn, không theo dư nợ.** Vì nguy cơ tỷ lệ với tần suất quay vòng, một bản thống kê nợ công đầy đủ cần tách riêng mọi nghĩa vụ phải tái tục trong vòng một năm với một đối tác duy nhất, kể cả khi quy mô nhỏ và kể cả khi chúng nằm ở bảng cân đối ngân hàng trung ương chứ không phải ngân sách.

**Quy tắc tài khoá có giá trị cao hơn khi tồn tại nguồn vay song phương.** Đây là hàm ý trực tiếp của mô hình: vì kỷ luật thị trường bị bào mòn bởi độ co giãn chéo, một ràng buộc hành chính lên tổng mức vay trở nên quan trọng hơn chứ không phải ít quan trọng hơn. Đây là một lập luận ủng hộ trần nợ và trần bội chi hoàn toàn khác với các lập luận thông thường.

**Ưu tiên điều khoản định trước trong mọi thoả thuận mới.** Kết quả cải thiện Pareto của bài nói rằng một quy tắc minh bạch tốt hơn cho cả hai bên so với thương lượng. Điều đó có nghĩa là việc yêu cầu công bố công thức lãi suất không phải một nhượng bộ mà phía đối tác phải chấp nhận miễn cưỡng — theo mô hình, đó là điều họ cũng có lợi nếu cam kết được.

Cuối cùng, tài liệu này nên được đọc cùng nhánh về dễ tổn thương nợ của các nền kinh tế mới nổi trong cùng thư mục, nơi ghi nhận rằng tỷ trọng chủ nợ tư nhân cộng song phương ngoài Câu lạc bộ Paris ở nhóm thu nhập thấp đã đi từ 22% lên 38% tổng nợ ngoài. Tài liệu kia đo sự dịch chuyển; tài liệu này giải thích vì sao sự dịch chuyển đó làm việc tái cơ cấu trở nên khó hơn và làm hành vi vay mượn trở nên tệ hơn ngay cả khi chưa có ai vỡ nợ.
