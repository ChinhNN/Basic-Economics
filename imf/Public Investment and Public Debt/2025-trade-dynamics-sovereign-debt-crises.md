# Trade Dynamics in Sovereign Debt Crises — Diễn biến thương mại trong khủng hoảng nợ chính phủ

**Nguồn:** IMF Working Paper WP/25/240, tháng 11/2025, Vụ Chiến lược, Chính sách và Đánh giá. Đây là bản sửa đổi lớn của WP/16/222 "Trade Costs of Sovereign Debt Restructurings: Does a Market-Friendly Approach Improve the Outcome?".
**Tác giả:** Tamon Asonuma, Marcos Chamon, Yasumasa Morito, Akira Sasahara.
**Ý chính:** Tái cơ cấu nợ chính phủ với chủ nợ tư nhân nước ngoài tác động lớn lên thương mại. Bài dùng mẫu **194 đợt tái cơ cấu ở 76 nước, 1975–2019**, chia theo cách của Asonuma và Trebesch (2016): **tái cơ cấu sau vỡ nợ** (đã ngừng trả mà không có sự đồng ý của chủ nợ) và **tái cơ cấu chủ động** (không ngừng trả, hoặc chỉ tạm ngừng sau khi đã đàm phán). Loại hình tái cơ cấu được biết ngay từ đầu, nên dùng được làm chỉ báo trước cho mức độ sâu và dài của khủng hoảng. Với phép chiếu địa phương kết hợp trọng số xác suất nghịch đảo tăng cường (AIPW), kết quả chính là: **nhập khẩu co mạnh sau vỡ nợ**, giảm khoảng **15% tỷ lệ nhập khẩu/GDP**, tương đương **khoảng 2 điểm phần trăm GDP**, vào năm thứ hai; còn sau tái cơ cấu chủ động, nhập khẩu **gần như không đổi**. **Xuất khẩu** mơ hồ hơn: sau vỡ nợ còn **tăng nhẹ** nhờ tỷ giá mất giá mạnh và doanh nghiệp chuyển sang bán ra nước ngoài, còn sau tái cơ cấu chủ động lại **giảm**. Co nhập khẩu **mạnh hơn nhiều khi tổng cầu trong nước ban đầu cao**. Thông điệp chính sách: cán cân thương mại cải thiện sau vỡ nợ **không phải tin tốt**, mà là dấu hiệu của một cuộc điều chỉnh đối ngoại bị ép buộc và tốn kém về phúc lợi.

> **Lưu ý:** bản PDF chỉ có phần chính. Các Phụ lục A tới I (danh sách nước, bảng OLS, các kiểm tra độ vững, kết quả tính theo điểm phần trăm GDP) được dẫn chiếu nhưng không có trong bản này. Một số lỗi trong bài:
> - Văn bản dẫn Behrens và cộng sự (2013), danh mục ghi 2023; Serfaty 2021 so với 2024; Kuvshinov và Zimmermann 2018 so với 2019.
> - Chú thích Bảng 2 nhắc tới "GDP và đầu tư", có vẻ sót lại từ một bài khác.
> - Tiêu đề các ô trong Hình 7 ghi "(% of GDP)", nhưng biến là tốc độ thay đổi của tỷ lệ.
> - Phần mở đầu nói xuất khẩu sau tái cơ cấu chủ động giảm khoảng 1,5 điểm phần trăm GDP, còn Mục 4.2 ghi khoảng 1,7.
> - Mục 4.2 nói nhập khẩu sau tái cơ cấu chủ động tăng 7%, trong khi Bảng 2 ghi 6,64.
> Các số trên hình là giá trị ước đọc.

## Sơ đồ

### Các kênh tác động

```text
       TÁI CƠ CẤU / VỠ NỢ
          │
          ├─▶ sản lượng và tổng cầu GIẢM ─────────▶ nhập khẩu ↓
          ├─▶ tỷ giá MẤT GIÁ mạnh ────────────────▶ nhập khẩu ↓
          │                                         xuất khẩu ↑
          ├─▶ tài trợ thương mại bị gián đoạn ────▶ nhập khẩu ↓
          │   (Mendoza–Yue 2012)                    xuất khẩu ↓
          └─▶ cầu nội địa yếu → nhà sản xuất
              chuyển sang THỊ TRƯỜNG NƯỚC NGOÀI ──▶ xuất khẩu ↑
       ═══════════════════════════════════════════════════════════
       ★ NHẬP KHẨU: mọi kênh cùng chiều GIẢM → kết quả RÕ
       ⚠ XUẤT KHẨU: các kênh NGƯỢC chiều → kết quả MƠ HỒ
```

### Hai loại tái cơ cấu

```text
       ┌──────────────────────────┬──────────────────────────────┐
       │ SAU VỠ NỢ (post-default) │ CHỦ ĐỘNG (preemptive)        │
       ├──────────────────────────┼──────────────────────────────┤
       │ đã ngừng trả KHÔNG có    │ không ngừng trả, hoặc chỉ tạm│
       │ đồng ý của chủ nợ        │ ngừng SAU khi đàm phán       │
       │ 115 đợt (≈60%)           │ 79 đợt                       │
       │ kéo dài ~5 năm           │ ngắn hơn                     │
       │ GDP giảm ~6% so với xu   │ thiệt hại rất hạn chế        │
       │ hướng (Asonuma 2024)     │                              │
       └──────────────────────────┴──────────────────────────────┘
       ★ mốc bắt đầu = sớm hơn trong hai sự kiện: tháng vỡ nợ, hoặc
         tháng công bố tái cơ cấu
       ★ mẫu cơ sở BỎ các trường hợp "lai" (công bố tái cơ cấu trước,
         vỡ nợ ở các năm sau) → giữ 106 đợt vỡ nợ ngay trong năm bắt
         đầu (92% số đợt sau vỡ nợ)
       ═══════════════════════════════════════════════════════════
       DỮ LIỆU THƯƠNG MẠI (UNCTAD, theo năm)
       hàng CHẾ TẠO · hoá chất, hàng chế tạo, máy móc và phương tiện
                      vận tải, hàng chế tạo khác
       hàng SƠ CẤP · lương thực, đồ uống, nguyên liệu thô, nhiên
                      liệu, dầu mỡ, kim loại màu
       hàng KHÁC ··· chỉ ~2% → bỏ qua
       chia tiếp: TƯ LIỆU SẢN XUẤT · TRUNG GIAN · TIÊU DÙNG
         (hàng sơ cấp chỉ có trung gian và tiêu dùng)
```

### Sự thật cách điệu

```text
       HÌNH 1 — BÌNH QUÂN THAY ĐỔI TÍCH LUỸ (%, ước đọc)
       ┌─────────────────┬──────────────────┬──────────────────┐
       │                 │ SAU VỠ NỢ        │ CHỦ ĐỘNG         │
       ├─────────────────┼──────────────────┼──────────────────┤
       │ nhập khẩu/GDP   │ ~−14 năm 2, hồi  │ ~−11 năm 3, còn  │
       │                 │ về ~0 năm 5      │ ~−8,5 năm 5      │
       │ xuất khẩu/GDP   │ ~−5 rồi ổn định, │ giảm liên tục,   │
       │                 │ ~−2 năm 5        │ ~−11,5 năm 5     │
       │ GDP             │ ★ ~−5,5 năm 3    │ ~−1,8 năm 1, gần │
       │                 │                  │ hồi phục         │
       │ tỷ giá thực     │ ~−8 năm 5        │ ~−10 năm 2,      │
       │                 │                  │ ~−14 năm 5       │
       └─────────────────┴──────────────────┴──────────────────┘
       ⚠ số liệu thô chưa tính việc tái cơ cấu xảy ra khi kinh tế
         vốn đã xấu → cần PHƯƠNG PHÁP điều chỉnh chọn mẫu
```

### Phương pháp

```text
       ❶ PHÉP CHIẾU ĐỊA PHƯƠNG (Jordà 2005), h = 1…5 năm
       log(y_{t+h}) − log(y_t) = αᵢ + β·D_{t+1} + X_t·γ + u
       y = nhập khẩu (xuất khẩu) / GDP
       hai thước đo: TỐC ĐỘ thay đổi (%) và MỨC thay đổi (điểm %
         GDP) · vd xuất khẩu 10% → 8% GDP = −20% hoặc −2 điểm %
       biến kiểm soát: tăng trưởng GDP, chi tiêu chính phủ/GDP, độ
         mở thương mại, khủng hoảng ngân hàng, tín dụng ngân hàng/
         GDP, lạm phát trên 50%, tổng cầu nội địa/GDP, tỷ giá mậu
         dịch, tỷ giá thực
       ═══════════════════════════════════════════════════════════
       ❷ PROBIT BƯỚC MỘT — xác suất tái cơ cấu
       ★ BẢNG 1 — biến dự báo (thoả mãn điều kiện loại trừ)
       ┌──────────────────────┬──────────────┬──────────────┐
       │                      │ SAU VỠ NỢ    │ CHỦ ĐỘNG     │
       ├──────────────────────┼──────────────┼──────────────┤
       │ lãi suất Fed         │ ★ +5,442*    │ −3,351       │
       │ lây lan (tái cơ cấu  │ ★ +4,224***  │ ★ +5,417***  │
       │ ở nước khác, theo    │              │              │
       │ khoảng cách)         │              │              │
       │ số lần chủ động trước│ −0,157       │ ★ −0,838***  │
       │ AUC                  │ 0,871        │ 0,935        │
       └──────────────────────┴──────────────┴──────────────┘
       → Fed thắt chặt: dễ VỠ NỢ hơn, ít CHỦ ĐỘNG hơn
       → biến dự báo nâng AUC: 0,79 → 0,87 (vỡ nợ), 0,85 → 0,94
       ═══════════════════════════════════════════════════════════
       ❸ AIPW (Jordà–Taylor 2016)
       trọng số THẤP cho quan sát dễ bị tái cơ cấu, CAO cho quan sát
       ít khả năng → giảm thiên lệch chọn mẫu theo biến quan sát được
       kết hợp: phần trọng số nghịch đảo + phần dự báo hồi quy
       ★ so sánh hai loại: bootstrap 1000 lần và thống kê z của
         Clogg và cộng sự (1995)
```

### Kết quả chính: nhập khẩu

```text
       ★★ BẢNG 2 — AIPW, TỐC ĐỘ thay đổi tích luỹ (%)
       ┌────────────────────┬───────┬───────┬───────┬───────┬───────┐
       │ năm                │   1   │   2   │   3   │   4   │   5   │
       ├────────────────────┼───────┼───────┼───────┼───────┼───────┤
       │ TỔNG sau vỡ nợ     │−6,07***│★−15,01***│−10,22***│−0,65│ 3,78 │
       │ TỔNG chủ động      │ 0,1   │−2,59* │ 0,4   │ 2,99  │6,64** │
       │ CHẾ TẠO sau vỡ nợ  │−7,21***│★−17,04***│−13,73***│1,39│ 1,33 │
       │ CHẾ TẠO chủ động   │−0,61  │−2,01  │−3,17  │5,51** │10,77***│
       │ SƠ CẤP sau vỡ nợ   │−7,05***│−12,51***│−9,68***│★−13,58***│−3,31│
       │ SƠ CẤP chủ động    │−0,87  │−2,55  │ 2,81  │ 0,5   │−1,36  │
       └────────────────────┴───────┴───────┴───────┴───────┴───────┘
       ★★★ ĐỌC BẢNG NÀY
       ① sau vỡ nợ: nhập khẩu SỤP 10–15% tới năm 3, tương đương
          ~2 điểm % GDP năm 2
          lý do: GDP giảm mạnh → cầu nhập khẩu co; tỷ giá mất giá →
          giá nhập khẩu tính bằng nội tệ tăng vọt
       ② hàng chế tạo và hàng sơ cấp giảm tương đương, nhưng hàng
          CHẾ TẠO hồi phục từ năm 4, hàng SƠ CẤP giảm lâu hơn
       ③ chủ động: ổn định, thậm chí TĂNG ~7% tới năm 5
       ⚠ khác biệt giữa hai loại có ý nghĩa theo z của Clogg, KHÔNG
         có ý nghĩa theo bootstrap
```

### Kết quả chính: xuất khẩu

```text
       ★★ BẢNG 2 (tiếp) — XUẤT KHẨU, tốc độ thay đổi tích luỹ (%)
       ┌────────────────────┬───────┬───────┬───────┬───────┬───────┐
       │ năm                │   1   │   2   │   3   │   4   │   5   │
       ├────────────────────┼───────┼───────┼───────┼───────┼───────┤
       │ TỔNG sau vỡ nợ     │−0,12  │−0,05  │5,5*** │★11,04***│5,86**│
       │ TỔNG chủ động      │−7,57***│−6,62***│−4,86**│−5,59***│−6,38***│
       │ CHẾ TẠO sau vỡ nợ  │ 3,39  │9,44***│17,26***│ 2,9  │★19,84***│
       │ CHẾ TẠO chủ động   │−9,51***│ 3,91 │−19,77***│−13,9***│−10,76***│
       │ SƠ CẤP sau vỡ nợ   │ 1,79  │−0,3   │4,71***│7,09***│ 3,66  │
       │ SƠ CẤP chủ động    │−7,11***│−7,27***│−5,99***│−10,17***│−14,6***│
       └────────────────────┴───────┴───────┴───────┴───────┴───────┘
       ★★★ ĐỌC BẢNG NÀY
       ① sau vỡ nợ: xuất khẩu TĂNG ~11% năm 4, do hàng CHẾ TẠO, nhất
          là TƯ LIỆU SẢN XUẤT
          → tỷ giá mất giá sâu và kéo dài + chuyển sản xuất sang thị
            trường ngoài BÙ ĐƯỢC cú sốc cung tiêu cực
       ② chủ động: xuất khẩu GIẢM ~5%
       ⚠⚠ tính theo ĐIỂM % GDP: hiệu ứng sau vỡ nợ gần như BIẾN MẤT
          (~+0,4 điểm), chủ động vẫn giảm ~1,7 điểm, chủ yếu hàng sơ
          cấp
       → mức tăng % lớn đến từ nền RẤT NHỎ ở các nền kinh tế đóng
       → kết quả về NHẬP KHẨU vững hơn XUẤT KHẨU
       ─────────────────────────────────────────────────────────
       ĐỘ VỮNG: gồm cả trường hợp "lai"; lấy năm vỡ nợ làm mốc; hai
       cách xử lý các đợt chồng lấn ("chiến lược ban đầu", "chiến
       lược tệ nhất"); hồi quy trung vị → kết quả tương tự
```

### Theo nhóm hàng chi tiết

```text
       NHẬP KHẨU
       chế tạo, sau vỡ nợ ··· giảm chủ yếu ở TƯ LIỆU SẢN XUẤT (~−23%)
                             và TRUNG GIAN (~−19%); tiêu dùng ổn định
       chế tạo, chủ động ···· ổn định trừ một đợt giảm hàng trung
                             gian; mức tăng cuối kỳ do tư liệu sản
                             xuất
       sơ cấp, sau vỡ nợ ···· giảm ở cả TRUNG GIAN và TIÊU DÙNG
                             (~−19% năm 3)
       ═══════════════════════════════════════════════════════════
       XUẤT KHẨU
       chế tạo, sau vỡ nợ ··· tăng do TƯ LIỆU SẢN XUẤT (~+45% năm 5)
       chế tạo, chủ động ···· cả ba nhóm cùng giảm
       sơ cấp, sau vỡ nợ ···· ổn định, có đợt tăng tạm hàng tiêu dùng
       sơ cấp, chủ động ····· giảm, do hàng TRUNG GIAN
       ⚠ tính theo điểm % GDP: chỉ còn rõ mức giảm ~1 điểm % của
         hàng sơ cấp trung gian sau tái cơ cấu chủ động
```

### Vai trò của tổng cầu trong nước

```text
       tổng cầu nội địa = tiêu dùng + đầu tư + chi tiêu chính phủ
                        = GDP − xuất khẩu ròng
       ★ ngưỡng = TRUNG VỊ các đợt tái cơ cấu = 101,8% GDP năm trước
         → CAO: một nửa số đợt sau vỡ nợ, một phần ba số đợt chủ động
       ═══════════════════════════════════════════════════════════
       ★★ BẢNG 3 — NHẬP KHẨU, tốc độ thay đổi tích luỹ (%)
       ┌───────────────────────┬───────┬───────┬───────┬───────┬───────┐
       │ năm                   │   1   │   2   │   3   │   4   │   5   │
       ├───────────────────────┼───────┼───────┼───────┼───────┼───────┤
       │ sau vỡ nợ, cầu CAO    │−14,74 │−23,1  │★−25,21│−19,15 │−11,07 │
       │ sau vỡ nợ, cầu THẤP   │ 3,65  │−5,85  │ 2,64  │ 10,8  │ 13,96 │
       │ chủ động, cầu CAO     │−12,09 │−13,32 │−6,78  │−6,4   │−0,05  │
       │ chủ động, cầu THẤP    │ 1,34  │ 0,38  │−1,45  │ 3,07  │−1,14  │
       └───────────────────────┴───────┴───────┴───────┴───────┴───────┘
       XUẤT KHẨU
       ┌───────────────────────┬───────┬───────┬───────┬───────┬───────┐
       │ sau vỡ nợ, cầu CAO    │ 0,05  │−2,46  │−4,51  │−7,13  │−4,88  │
       │ sau vỡ nợ, cầu THẤP   │ 3,09  │ 4,56  │15,62  │ ★33   │24,46  │
       │ chủ động, cầu CAO     │−4,35  │−2,03  │ 4,68  │ 2,53  │−2,64  │
       │ chủ động, cầu THẤP    │ 2,72  │ 2,58  │−2,41  │−1,26  │−3,56  │
       └───────────────────────┴───────┴───────┴───────┴───────┴───────┘
       ★★★ ĐỌC HAI BẢNG NÀY
       ① nước có tổng cầu CAO (hấp thụ nhiều nhập khẩu) co nhập khẩu
          MẠNH NHẤT, tới −25% sau vỡ nợ
       ② mức TĂNG xuất khẩu sau vỡ nợ hoàn toàn đến từ nước có tổng
          cầu THẤP; nước có tổng cầu cao còn GIẢM xuất khẩu
       ③ khác biệt cao–thấp chủ yếu ở hàng CHẾ TẠO
```

## Ba câu hỏi bài viết trả lời

1. Tái cơ cấu nợ chính phủ ảnh hưởng thế nào tới nhập khẩu và xuất khẩu, và ảnh hưởng đó có khác nhau giữa tái cơ cấu sau vỡ nợ và tái cơ cấu chủ động không?
2. Nhóm hàng nào, theo loại hàng và theo mục đích sử dụng, chịu tác động mạnh nhất?
3. Mức tổng cầu trong nước trước khủng hoảng khuếch đại hay làm dịu các tác động này?

## Dàn ý chi tiết

### 1. Mở đầu

- Khi vỡ nợ hoặc tái cơ cấu nợ nước ngoài, nước đi vay chịu sản lượng và tổng cầu giảm mạnh cùng tỷ giá mất giá lớn so với xu hướng trước khủng hoảng. Mọi kênh này đều ép nhập khẩu, còn tác động lên xuất khẩu thì mơ hồ.
- Một số cuộc khủng hoảng sâu và dai dẳng hơn những cuộc khác. Bài dùng tính chất sau vỡ nợ hay chủ động làm chỉ báo trước cho độ sâu và độ dài của thiệt hại. Chỉ báo này hợp với phép chiếu địa phương vì đã biết ngay từ đầu khủng hoảng.
- Bài mở rộng bằng cách chia mẫu theo tổng cầu nội địa so với GDP năm trước tái cơ cấu, theo cách của Auerbach và Gorodnichenko cùng Jordà và Taylor.

### 2. Vị trí trong tài liệu

- Nhánh xuyên quốc gia về chi phí thương mại của vỡ nợ: Rose (2005) thấy tái đàm phán với chủ nợ chính thức đi kèm thương mại giảm; Kuvshinov và Zimmermann thấy xuất khẩu ròng giảm; Serfaty thấy vỡ nợ từ 1815 tới 2019 đi kèm thương mại giảm, nhất là nhập khẩu. Bài làm sắc nét sự khác biệt giữa nhập và xuất, giữa các nhóm hàng và giữa hai loại tái cơ cấu.
- Nhánh cấp ngành và doanh nghiệp: Zymek thấy xuất khẩu ngành phụ thuộc tài chính giảm mạnh hơn; Gopinath và Neiman thấy nhập khẩu của Argentina sau vỡ nợ 2001 giảm chủ yếu do thay đổi cơ cấu sản phẩm và nhà cung cấp; Hébert và Schreger thấy doanh nghiệp xuất khẩu Argentina chịu thiệt nặng hơn dự kiến khi xác suất vỡ nợ tăng.
- Nhánh về động lực thương mại trong khủng hoảng tài chính toàn cầu: tổng cầu giảm là yếu tố chính làm nhập khẩu giảm. Bài bổ sung trường hợp cú sốc bắt nguồn trong nước.
- Nhánh về tính không đồng nhất của vỡ nợ: vỡ nợ "cứng" với mức cắt giảm nợ cao đi kèm GDP giảm kéo dài; nước phụ thuộc nhiều vào trung gian ngân hàng chịu thiệt nặng hơn.

### 3. Dữ liệu và sự thật cách điệu

- Mẫu gồm 194 đợt tái cơ cấu nợ nước ngoài với chủ nợ tư nhân. Mỗi đợt được tính riêng kể cả khi chồng lấn, vì có thể liên quan các công cụ nợ khác nhau.
- Số liệu thô cho thấy nhập khẩu và GDP giảm mạnh sau vỡ nợ, nhẹ hơn nhiều sau tái cơ cấu chủ động. Xuất khẩu giảm hai năm đầu sau vỡ nợ rồi ổn định, trong khi vẫn tiếp tục giảm sau tái cơ cấu chủ động.
- Ước lượng OLS cho kết quả tương tự nhưng khoảng tin cậy rộng, phần lớn khác biệt về xuất khẩu không có ý nghĩa thống kê.

### 4. Phương pháp AIPW

- Quyết định tái cơ cấu chịu ảnh hưởng của điều kiện kinh tế, và điều kiện xấu ban đầu có thể bị chính việc tái cơ cấu làm tệ thêm. AIPW gán trọng số khác nhau để phân bố quan sát ít thiên lệch chọn mẫu hơn.
- Probit dùng cả biến kiểm soát lẫn ba biến dự báo: lãi suất Fed, tái cơ cấu ở các nước khác có trọng số theo khoảng cách địa lý, và số lần tái cơ cấu chủ động trước đó. Hai biến đầu trực giao với quyết định của từng nước; biến thứ ba đã xác định trước.
- Đường ROC và mật độ xác suất dự báo cho thấy mô hình phân loại tốt, và trọng số được phân bố đều hơn trong nhóm được xử lý.

### 5. Kết quả AIPW

- Theo AIPW, tỷ giá thực sau vỡ nợ mất giá sâu và kéo dài, còn sau tái cơ cấu chủ động có cú sốc ban đầu lớn rồi gần như hồi phục hết vào năm thứ năm. Khác biệt này rõ hơn so với số liệu thô.
- Nhập khẩu co mạnh sau vỡ nợ, do cầu nhập khẩu giảm và giá nhập khẩu tính bằng nội tệ tăng. Sau tái cơ cấu chủ động, nhập khẩu ổn định.
- Xuất khẩu tăng nhẹ sau vỡ nợ nhờ hàng chế tạo, giảm nhẹ sau tái cơ cấu chủ động. Khi đo theo điểm phần trăm GDP, tác động sau vỡ nợ gần như biến mất, cho thấy kết quả đến từ các nền kinh tế tương đối đóng với nền xuất khẩu nhỏ.

### 6. Theo nhóm hàng

- Co nhập khẩu hàng chế tạo sau vỡ nợ chủ yếu do tư liệu sản xuất, phần nhỏ hơn do hàng trung gian. Co nhập khẩu hàng sơ cấp do cả hàng trung gian lẫn hàng tiêu dùng.
- Tăng xuất khẩu hàng chế tạo sau vỡ nợ do tư liệu sản xuất. Sau tái cơ cấu chủ động, mọi nhóm hàng chế tạo cùng giảm, còn hàng sơ cấp giảm chủ yếu ở hàng trung gian.

### 7. Vai trò của tổng cầu

- Mức độ phụ thuộc vào thương mại ảnh hưởng cả mức thiệt hại lẫn khả năng điều chỉnh. Nước mở hơn có thể dễ chuyển sang xuất khẩu hơn; nước đóng hơn thì co nhập khẩu từ nền thấp sẽ rất đau đớn.
- Nước có tổng cầu cao, vốn hấp thụ nhiều nhập khẩu, co nhập khẩu mạnh hơn, nhất là sau vỡ nợ. Với tái cơ cấu chủ động, khác biệt chủ yếu nằm ở hàng sơ cấp.
- Mức tăng xuất khẩu sau vỡ nợ đến từ nhóm có tổng cầu thấp, còn nhóm tổng cầu cao lại giảm xuất khẩu.

### 8. Kết luận

- Cách một nước xử lý khủng hoảng nợ ảnh hưởng lớn tới thương mại. Biến động lớn của xuất khẩu ròng có thể là thước đo gần đúng cho thiệt hại phúc lợi, khớp với các ước lượng chi phí sản lượng trong tài liệu.
- Khủng hoảng sâu và kéo dài có thể cải thiện cán cân thương mại, nhưng cái giá là co nhập khẩu và xuất khẩu dựa vào mất giá thực lớn.
- Quan điểm trọng thương đơn giản coi xuất khẩu ròng cao là tốt, nhưng ở đây nó có thể là kết quả của khủng hoảng sâu. Tái cơ cấu chủ động giúp tránh cuộc điều chỉnh đối ngoại bị ép buộc và tốn kém về phúc lợi.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Sovereign debt restructuring | Tái cơ cấu nợ chính phủ |
| Post-default restructuring | Tái cơ cấu sau khi đã ngừng trả nợ không có sự đồng ý của chủ nợ |
| Preemptive restructuring | Tái cơ cấu chủ động, trước khi vỡ nợ |
| Hybrid episodes | Trường hợp lai, công bố tái cơ cấu trước rồi mới vỡ nợ |
| Import compression | Co nhập khẩu |
| External adjustment | Điều chỉnh đối ngoại |
| Trade finance | Tài trợ thương mại |
| Real effective exchange rate (REER) | Tỷ giá thực hiệu dụng |
| Domestic aggregate demand | Tổng cầu nội địa, GDP trừ xuất khẩu ròng |
| Capital, intermediate, consumption goods | Tư liệu sản xuất, hàng trung gian, hàng tiêu dùng |
| Primary commodity | Hàng sơ cấp |
| Local projections | Phép chiếu địa phương của Jordà |
| Augmented inverse probability weighting (AIPW) | Trọng số xác suất nghịch đảo tăng cường |
| Selection on observables | Thiên lệch chọn mẫu theo biến quan sát được |
| Exclusion restriction | Điều kiện loại trừ của biến dự báo |
| Receiver operating characteristic (ROC) | Đường đặc tính hoạt động của bộ phân loại |
| Contagion | Lây lan |
| Clogg et al. z-statistic | Thống kê so sánh hệ số giữa hai hồi quy |
| Mercantilist view | Quan điểm trọng thương |

## Câu nói đáng nhớ

> "Import compression is significantly higher following post-default restructurings, which also tend to be associated with higher exports relative to preemptive restructurings."

> "While a simplistic mercantilist view would suggest higher net exports to be a desirable outcome, our results suggest they can be the result of deeper and more protracted crises."

> "By restructuring preemptively, countries may attenuate an impact that may otherwise require a welfare costly forced external adjustment."
