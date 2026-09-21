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

## Dàn ý chi tiết

### 1. Mở đầu

- Một phần lớn khoản vay của các chính phủ thị trường mới nổi là nợ chính thức, từ chính phủ khác, ngân hàng phát triển khu vực hay tổ chức đa phương. Sự trỗi dậy của các chủ nợ mới ngoài Câu lạc bộ Paris, cùng với việc họ đòi vị thế ưu tiên, làm dấy lên lo ngại về phúc lợi của nước đi vay.
- Lãi suất của chủ nợ lớn bị giới hạn bởi cạnh tranh ngầm từ thị trường, nhưng khi rủi ro vỡ nợ đẩy lợi suất thị trường lên, chủ nợ lớn có thể đòi phần bù. Vì khoản vay không có rủi ro vỡ nợ, phần bù này chỉ phản ánh phương án thay thế của con nợ.
- Có hai lý do nước đi vay thiệt. Lý do quen thuộc: vay được trong lúc bị loại khỏi thị trường làm tăng giá trị của vỡ nợ. Lý do căn bản hơn: ngay cả khi cấm vay lúc vỡ nợ, hiệu ứng vay quá mức do quan hệ vẫn làm phúc lợi giảm.
- Thặng dư của quan hệ song phương lớn nhất khi chính phủ đang trả chênh lệch cao, đúng lúc chính phủ cần chủ nợ lớn nhất. Vì vậy, khi chủ nợ dự kiến chính phủ sẽ gặp chênh lệch cao, họ đánh giá quan hệ cao hơn và sẵn sàng đầu tư vào nó bằng cách cho vay rẻ hơn.
- Tham số then chốt là sức mạnh thương lượng. Khi chính phủ nắm hết sức mạnh, chủ nợ lớn chỉ cho vay ở lãi phi rủi ro, mô hình trở về Hatchondo, Martinez và Önder (2017), và chính phủ được lợi. Nhưng lợi ích biến mất nhanh khi sức mạnh của chính phủ giảm.

### 2. Vị trí trong tài liệu

- Bài đóng góp vào nhánh nghiên cứu mới về tương tác giữa các loại nợ chủ quyền. Hatchondo, Martinez và Önder cho thấy thêm một lượng nợ không thể vỡ có giới hạn giúp phúc lợi nhưng chỉ tạm thời; Cordella và Powell cho thấy vị thế ưu tiên của tổ chức tài chính quốc tế có thể hình thành nội sinh; nhiều nghiên cứu khác xét nợ ưu tiên đi kèm điều kiện, hay vai trò của cho vay chính thức trong loại bỏ đa cân bằng.
- Mô hình của bài không có đa cân bằng, vốn là thứ có thể mở đường cho lợi ích của khoản vay song phương nếu nó loại bỏ được cân bằng xấu, và bỏ qua yếu tố điều kiện để tập trung vào thiết kế thị trường.
- Arellano và Barreto cho thấy định giá cạnh tranh và kỳ hạn dài, như khoản vay của Câu lạc bộ Paris, làm nợ chính thức ít rủi ro hơn. Liu, Liu và Yue cho thấy cân bằng tốt nhất với chủ nợ thị trường, song phương và đa phương có thể đạt phân bổ hiệu quả có ràng buộc. Các bài này nhấn mạnh thể chế có thể cải thiện phúc lợi, còn bài này minh hoạ hiểm hoạ.
- Mô hình không mô tả mọi khía cạnh của hạn mức hoán đổi: không có khác biệt đồng tiền, điều kiện về dự trữ hay tài sản bảo đảm. Nó cũng xem nợ là công cụ làm mượt tiêu dùng, không xét tài trợ dự án hay cho vay phát triển.

### 3. Mô hình chỉ có vay song phương

- Nền kinh tế mở nhỏ nhận thu nhập ngẫu nhiên và vay từ một chủ nợ độc quyền. Khoản vay ngắn hạn nên thực chất được thương lượng lại liên tục, với điểm đe doạ là trả hết nợ.
- Nền kinh tế giảm nợ khi thu nhập cao và nhận chuyển giao khi thu nhập thấp. Chủ nợ dùng lãi suất để chiếm thặng dư: trợ giá khi nợ và thu nhập thấp, rồi tăng lãi khi nợ lớn và việc trả hết trở nên khó.
- Khi nợ tăng, điểm đe doạ của con nợ kém đáng tin, thặng dư tăng nhưng chủ nợ cũng mạnh hơn trong thương lượng. Điều này làm hàm lợi nhuận của chủ nợ lồi, khiến chủ nợ trung tính rủi ro hành xử như người ưa rủi ro.

### 4. Mô hình đầy đủ

- Chính phủ vay từ chủ nợ lớn và từ nhóm chủ nợ cạnh tranh. Vỡ nợ với nợ thị trường có thể xảy ra, chịu chi phí sản lượng chuẩn, còn khoản vay song phương thì không.
- Buổi sáng, chính phủ quyết định vỡ nợ và phát hành; buổi chiều, thương lượng với chủ nợ lớn; sau đó tiêu dùng. Giá trái phiếu phản ánh kỳ vọng về cả quyết định vỡ nợ lẫn kết quả thương lượng.
- Kênh quan trọng nhất là dòng tiền ròng từ thị trường, vốn điều chỉnh điểm đe doạ: sau một đợt phát hành lớn, chính phủ ở thế mạnh vì trả nợ song phương ít tốn kém.

### 5. Kết quả định lượng

- Sự có mặt của chủ nợ lớn làm tăng mạnh tần suất vỡ nợ, chênh lệch cao hơn và biến động hơn, dù nợ thị trường thấp hơn đôi chút và khoản vay song phương khiêm tốn.
- Khoản vay song phương dùng nhiều nhất quanh vỡ nợ. Trước vỡ nợ, nó được trợ giá để tránh hoặc hoãn vỡ nợ; khi vỡ nợ, lãi tăng vọt.
- Khi cấm vay song phương trong lúc vỡ nợ, việc dùng khoản vay giảm hơn hai phần ba, vì phải trả hết khi vỡ nợ trở thành một chi phí vỡ nợ bổ sung. Khoản vay vẫn được dùng chủ yếu khi chênh lệch cao, và phúc lợi vẫn giảm dù ít hơn nhiều.
- Ngay cả khi quyết định vỡ nợ kỳ tới gần như không đổi, giá nợ vẫn thấp hơn vì chính sách vay tương lai thay đổi, tăng pha loãng nợ. Nền kinh tế dành nhiều thời gian hơn ở vùng nợ rủi ro.

### 6. Lập trình cho chủ nợ lớn

- Bài thay thương lượng bằng quy tắc lãi cố định dạng tuyến tính theo nợ thị trường và khoản vay song phương, có sàn ở lãi phi rủi ro nên chủ nợ không lỗ.
- Quy tắc kích rủi ro, trong đó lãi giảm khi nợ thị trường tăng, tái tạo động thái của thương lượng và gây thiệt.
- Quy tắc phụ thuộc quy mô, trong đó lãi tăng theo khoản vay song phương và không gắn với nợ thị trường, làm vỡ nợ và chênh lệch thấp hơn, cải thiện phúc lợi chính phủ trong khi chủ nợ vẫn có lợi nhuận, tức là một cải thiện Pareto.

### 7. Kết luận

- Hai nguồn vốn liên kết chặt dù khoản vay từ chủ nợ lớn nhỏ hơn nợ thị trường một bậc độ lớn.
- Độ co giãn chéo tự nó đủ để khuyến khích vay quá mức, tăng rủi ro và giảm phúc lợi. Thiệt hại có thể xảy ra ngay cả khi chính phủ được tự do không vay nếu điều khoản không đủ hấp dẫn.
- Có thêm nguồn vay không nhất thiết có lợi: khoản vay song phương có thể giúp tránh vỡ nợ, nhưng cũng có thể làm vỡ nợ dễ xảy ra hơn.
- Chính sách gợi ý: hạn chế vay song phương khi vỡ nợ, dùng quy tắc tài khoá hạn chế vay thị trường, và quy định điều khoản song phương minh bạch theo quy tắc.

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
