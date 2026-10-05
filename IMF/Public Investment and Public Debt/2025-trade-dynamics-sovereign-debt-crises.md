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

## Khái niệm cần biết

**Tái cơ cấu nợ chính phủ: sau vỡ nợ và chủ động (post-default, preemptive restructuring).** Tái cơ cấu nợ là khi chính phủ và chủ nợ thoả thuận đổi điều khoản của khoản nợ: giảm gốc, giảm lãi hoặc kéo dài kỳ hạn. Bài chia làm hai loại, theo cách của Asonuma và Trebesch (2016). **Sau vỡ nợ**: chính phủ đã ngừng trả nợ mà không có sự đồng ý của chủ nợ, rồi mới đàm phán. **Chủ động**: chính phủ không ngừng trả, hoặc chỉ tạm ngừng sau khi đã đàm phán với chủ nợ. Ví dụ trong bài: trong 194 đợt tái cơ cấu, 115 đợt (khoảng 60%) là sau vỡ nợ và kéo dài khoảng 5 năm, 79 đợt là chủ động và ngắn hơn. Khái niệm này quan trọng vì toàn bộ bài so sánh tác động thương mại của hai loại.

**Co nhập khẩu (import compression).** Nhập khẩu bị ép giảm mạnh, không phải vì nước đó muốn mà vì không còn đủ ngoại tệ, thu nhập giảm và hàng nhập trở nên quá đắt. Ví dụ trong bài: sau vỡ nợ, tỷ lệ nhập khẩu trên GDP giảm khoảng 15% vào năm thứ hai, tương đương khoảng 2 điểm phần trăm GDP. Khái niệm này quan trọng vì đây là kết quả rõ và vững nhất của bài.

**Tỷ giá thực và mất giá (real exchange rate, depreciation).** Tỷ giá thực đo giá hàng hoá trong nước so với giá hàng hoá nước ngoài khi quy về cùng một đồng tiền. Khi đồng nội tệ mất giá thực, hàng nhập khẩu trở nên đắt hơn với người trong nước, còn hàng xuất khẩu trở nên rẻ hơn với người nước ngoài. Ví dụ minh hoạ: nếu nội tệ mất giá 20% và giá cả trong nước không đổi, một chiếc máy nhập khẩu giá 100.000 đô la sẽ tốn nhiều hơn 25% tính bằng nội tệ. Khái niệm này quan trọng vì mất giá là kênh vừa ép nhập khẩu vừa có thể đẩy xuất khẩu.

**Tổng cầu nội địa (domestic aggregate demand).** Tổng chi tiêu của mọi người trong nước: tiêu dùng cộng đầu tư cộng chi tiêu chính phủ, tức bằng GDP trừ đi xuất khẩu ròng. Khi tổng cầu nội địa lớn hơn 100% GDP, nghĩa là nước đó đang tiêu nhiều hơn mình sản xuất, phần chênh được bù bằng nhập khẩu và vay nước ngoài. Ví dụ trong bài: ngưỡng chia mẫu là 101,8% GDP của năm trước tái cơ cấu. Khái niệm này quan trọng vì nó quyết định nhập khẩu co mạnh tới đâu.

**Phép chiếu địa phương (local projections).** Phương pháp do Jordà (2005) đưa ra để đo tác động của một sự kiện theo thời gian: với mỗi khoảng h năm sau sự kiện (h từ 1 tới 5), chạy một hồi quy riêng xem biến kết quả thay đổi bao nhiêu so với trước sự kiện. Ví dụ minh hoạ: một hồi quy cho biết nhập khẩu thay đổi bao nhiêu sau 1 năm, hồi quy khác cho biết sau 2 năm, và ghép lại thành một "đường phản ứng". Khái niệm này quan trọng vì đó là cách bài vẽ ra diễn biến thương mại qua năm năm sau tái cơ cấu.

**Thiên lệch chọn mẫu và AIPW (selection bias, augmented inverse probability weighting).** Các nước tái cơ cấu thường là những nước vốn đã có kinh tế xấu, nên nếu chỉ so trước và sau, ta có thể nhầm cái xấu sẵn có thành tác động của tái cơ cấu. AIPW sửa điều này: trước hết ước lượng xác suất mỗi quan sát bị tái cơ cấu, rồi gán trọng số thấp cho quan sát rất dễ bị tái cơ cấu và trọng số cao cho quan sát ít khả năng, đồng thời kết hợp với một phần dự báo bằng hồi quy. Ví dụ minh hoạ: nếu một nước có xác suất tái cơ cấu 90% thì việc nó tái cơ cấu là điều gần như chắc chắn và ít cho ta thông tin, nên được gán trọng số thấp. Khái niệm này quan trọng vì đây là phương pháp chính của bài, theo Jordà và Taylor (2016).

**Tốc độ thay đổi và mức thay đổi theo điểm phần trăm GDP.** Cùng một thay đổi có thể đo hai cách. Ví dụ trong bài: nếu xuất khẩu đi từ 10% GDP xuống 8% GDP thì tốc độ thay đổi là −20%, còn mức thay đổi là −2 điểm phần trăm GDP. Với một nước có xuất khẩu rất nhỏ, một tốc độ tăng lớn có thể chỉ là mức tăng rất nhỏ tính theo GDP. Khái niệm này quan trọng vì kết quả về xuất khẩu của bài gần như biến mất khi đổi từ cách đo thứ nhất sang cách đo thứ hai.

**Tư liệu sản xuất, hàng trung gian, hàng tiêu dùng.** Ba nhóm hàng theo mục đích sử dụng. Tư liệu sản xuất là máy móc, thiết bị dùng lâu dài để sản xuất (ví dụ một dây chuyền đóng gói). Hàng trung gian là đầu vào bị dùng hết trong quá trình sản xuất (ví dụ vải để may áo, linh kiện để lắp điện thoại). Hàng tiêu dùng là hàng người dân mua để dùng. Khái niệm này quan trọng vì bài cho thấy sau vỡ nợ, phần bị cắt mạnh nhất là tư liệu sản xuất và hàng trung gian, không phải hàng tiêu dùng.

## Nội dung chi tiết

### 1. Mở đầu

Khi một chính phủ vỡ nợ hoặc tái cơ cấu nợ nước ngoài, nền kinh tế thường chịu sản lượng và tổng cầu giảm mạnh, cùng với tỷ giá mất giá lớn so với xu hướng trước khủng hoảng. Câu hỏi của bài là điều đó ảnh hưởng tới thương mại thế nào.

**Các kênh tác động.** Bài liệt kê bốn kênh:

| Kênh | Tác động lên nhập khẩu | Tác động lên xuất khẩu |
|---|---|---|
| Sản lượng và tổng cầu giảm | Giảm | |
| Tỷ giá mất giá mạnh | Giảm (hàng nhập đắt hơn) | Tăng (hàng xuất rẻ hơn với người nước ngoài) |
| Tài trợ thương mại bị gián đoạn (Mendoza và Yue 2012) | Giảm | Giảm |
| Cầu nội địa yếu, nhà sản xuất chuyển sang bán ra thị trường nước ngoài | | Tăng |

Với nhập khẩu, mọi kênh đều cùng chiều giảm, nên kết quả kỳ vọng là rõ ràng. Với xuất khẩu, các kênh ngược chiều nhau, nên kết quả là mơ hồ và phải xác định bằng số liệu.

**Ý tưởng chính.** Một số cuộc khủng hoảng nợ sâu và dai dẳng hơn những cuộc khác. Bài dùng tính chất "sau vỡ nợ" hay "chủ động" của đợt tái cơ cấu làm chỉ báo trước cho độ sâu và độ dài của thiệt hại. Chỉ báo này rất hợp với phép chiếu địa phương, vì loại tái cơ cấu đã được biết ngay từ đầu khủng hoảng, nên có thể dùng làm điểm xuất phát để theo dõi diễn biến các năm sau.

Hai loại tái cơ cấu khác nhau rõ rệt:

| | Sau vỡ nợ | Chủ động |
|---|---|---|
| Định nghĩa | Đã ngừng trả nợ mà không có sự đồng ý của chủ nợ | Không ngừng trả, hoặc chỉ tạm ngừng sau khi đã đàm phán |
| Số đợt trong mẫu | 115 (khoảng 60%) | 79 |
| Thời gian kéo dài | Khoảng 5 năm | Ngắn hơn |
| Thiệt hại sản lượng | GDP giảm khoảng 6% so với xu hướng (Asonuma 2024) | Rất hạn chế |

Bài mở rộng phân tích bằng cách chia mẫu theo tổng cầu nội địa so với GDP của năm trước tái cơ cấu, theo cách làm của Auerbach và Gorodnichenko cùng Jordà và Taylor khi họ chia mẫu theo trạng thái của nền kinh tế.

### 2. Vị trí trong tài liệu

Bài nằm giữa bốn nhánh nghiên cứu.

**Nghiên cứu xuyên quốc gia về chi phí thương mại của vỡ nợ.** Rose (2005) thấy rằng tái đàm phán nợ với chủ nợ chính thức đi kèm với thương mại giảm. Kuvshinov và Zimmermann thấy xuất khẩu ròng giảm. Serfaty, với dữ liệu các đợt vỡ nợ từ 1815 tới 2019, thấy vỡ nợ đi kèm thương mại giảm, nhất là nhập khẩu. Bài này làm sắc nét hơn ba sự phân biệt: giữa nhập khẩu và xuất khẩu, giữa các nhóm hàng, và giữa hai loại tái cơ cấu.

**Nghiên cứu cấp ngành và doanh nghiệp.** Zymek thấy xuất khẩu của các ngành phụ thuộc nhiều vào tài chính giảm mạnh hơn sau vỡ nợ. Gopinath và Neiman thấy nhập khẩu của Argentina sau vỡ nợ năm 2001 giảm chủ yếu do thay đổi trong cơ cấu sản phẩm và nhà cung cấp. Hébert và Schreger thấy các doanh nghiệp xuất khẩu Argentina chịu thiệt nặng hơn dự kiến khi xác suất vỡ nợ tăng.

**Động lực thương mại trong khủng hoảng tài chính toàn cầu.** Nhánh này thấy tổng cầu giảm là yếu tố chính làm nhập khẩu giảm. Bài bổ sung trường hợp cú sốc bắt nguồn từ trong nước (khủng hoảng nợ của chính nước đó) chứ không phải từ bên ngoài.

**Tính không đồng nhất của vỡ nợ.** Vỡ nợ "cứng", với mức cắt giảm nợ cao cho chủ nợ, đi kèm GDP giảm kéo dài; những nước phụ thuộc nhiều vào trung gian ngân hàng chịu thiệt nặng hơn.

### 3. Dữ liệu và sự thật cách điệu

**Mẫu tái cơ cấu.** Mẫu gồm 194 đợt tái cơ cấu nợ nước ngoài với chủ nợ tư nhân, ở 76 nước, trong giai đoạn 1975–2019. Mỗi đợt được tính riêng, kể cả khi chồng lấn thời gian với đợt khác, vì các đợt có thể liên quan tới những công cụ nợ khác nhau.

Mốc bắt đầu của một đợt là sự kiện nào xảy ra sớm hơn trong hai sự kiện: tháng vỡ nợ, hoặc tháng công bố tái cơ cấu. Mẫu cơ sở bỏ các trường hợp "lai", tức công bố tái cơ cấu trước rồi vỡ nợ ở các năm sau, vì không rõ chúng thuộc loại nào. Sau khi bỏ, còn lại 106 đợt vỡ nợ xảy ra ngay trong năm bắt đầu, chiếm 92% số đợt sau vỡ nợ.

**Dữ liệu thương mại.** Số liệu lấy từ UNCTAD, theo năm, chia thành:

- **Hàng chế tạo:** hoá chất, hàng chế tạo cơ bản, máy móc và phương tiện vận tải, hàng chế tạo khác.
- **Hàng sơ cấp:** lương thực, đồ uống, nguyên liệu thô, nhiên liệu, dầu mỡ, kim loại màu.
- **Hàng khác:** chỉ chiếm khoảng 2%, nên bỏ qua.

Mỗi nhóm lại được chia tiếp theo mục đích sử dụng thành tư liệu sản xuất, hàng trung gian và hàng tiêu dùng (hàng sơ cấp chỉ có hàng trung gian và hàng tiêu dùng).

**Sự thật cách điệu từ số liệu thô.** Bình quân thay đổi tích luỹ (%, giá trị ước đọc từ hình), tính từ năm bắt đầu tái cơ cấu:

| Biến | Sau vỡ nợ | Chủ động |
|---|---|---|
| Nhập khẩu/GDP | Khoảng −14% ở năm 2, hồi về khoảng 0 ở năm 5 | Khoảng −11% ở năm 3, vẫn còn khoảng −8,5% ở năm 5 |
| Xuất khẩu/GDP | Khoảng −5% rồi ổn định, còn khoảng −2% ở năm 5 | Giảm liên tục, khoảng −11,5% ở năm 5 |
| GDP | Khoảng −5,5% ở năm 3 | Khoảng −1,8% ở năm 1, rồi gần như hồi phục |
| Tỷ giá thực | Khoảng −8% ở năm 5 | Khoảng −10% ở năm 2, khoảng −14% ở năm 5 |

Như vậy số liệu thô cho thấy nhập khẩu và GDP giảm mạnh sau vỡ nợ, nhẹ hơn nhiều sau tái cơ cấu chủ động. Xuất khẩu giảm trong hai năm đầu sau vỡ nợ rồi ổn định, trong khi tiếp tục giảm sau tái cơ cấu chủ động.

Nhưng số liệu thô chưa tính tới việc tái cơ cấu thường xảy ra khi kinh tế vốn đã xấu, nên cần một phương pháp điều chỉnh cho thiên lệch chọn mẫu. Ước lượng bằng hồi quy bình phương nhỏ nhất thông thường (OLS) cho kết quả tương tự, nhưng khoảng tin cậy rộng, và phần lớn khác biệt về xuất khẩu không có ý nghĩa thống kê.

### 4. Phương pháp AIPW

**Vấn đề.** Quyết định tái cơ cấu chịu ảnh hưởng của điều kiện kinh tế, và điều kiện xấu ban đầu có thể bị chính việc tái cơ cấu làm tệ thêm. Nếu không xử lý, ta không tách được phần nào là do tái cơ cấu và phần nào là do hoàn cảnh sẵn có.

**Bước thứ nhất: phép chiếu địa phương.** Theo Jordà (2005), với mỗi khoảng h = 1 đến 5 năm, bài ước lượng:

log(y_{t+h}) − log(y_t) = αᵢ + β·D_{t+1} + X_t·γ + u

Trong đó y là tỷ lệ nhập khẩu (hoặc xuất khẩu) trên GDP, D là biến cho biết có tái cơ cấu hay không, αᵢ là hiệu ứng cố định của từng nước, và X là các biến kiểm soát. Bài dùng hai thước đo: tốc độ thay đổi (%) và mức thay đổi (điểm phần trăm GDP). Ví dụ: xuất khẩu đi từ 10% xuống 8% GDP là −20% theo thước đo thứ nhất và −2 điểm phần trăm theo thước đo thứ hai.

Các biến kiểm soát gồm: tăng trưởng GDP, chi tiêu chính phủ trên GDP, độ mở thương mại, khủng hoảng ngân hàng, tín dụng ngân hàng trên GDP, lạm phát trên 50%, tổng cầu nội địa trên GDP, tỷ giá mậu dịch và tỷ giá thực.

**Bước thứ hai: mô hình probit dự báo xác suất tái cơ cấu.** Mô hình dùng cả các biến kiểm soát lẫn ba biến dự báo bổ sung. Ba biến này cần thoả điều kiện loại trừ: chúng ảnh hưởng tới xác suất tái cơ cấu nhưng không trực tiếp ảnh hưởng tới thương mại. Hai biến đầu (lãi suất Fed và tái cơ cấu ở nước khác) đến từ bên ngoài, trực giao với quyết định của từng nước; biến thứ ba đã được xác định từ trước.

| Biến dự báo | Sau vỡ nợ | Chủ động |
|---|---|---|
| Lãi suất của Cục Dự trữ Liên bang Mỹ (Fed) | +5,442\* | −3,351 |
| Lây lan: tái cơ cấu ở các nước khác, có trọng số theo khoảng cách địa lý | +4,224\*\*\* | +5,417\*\*\* |
| Số lần tái cơ cấu chủ động trước đó | −0,157 | −0,838\*\*\* |
| Diện tích dưới đường ROC (AUC) | 0,871 | 0,935 |

Đọc bảng: khi Fed thắt chặt, một nước dễ rơi vào vỡ nợ hơn và ít khả năng tái cơ cấu chủ động hơn. Tái cơ cấu ở các nước lân cận làm tăng xác suất cả hai loại. Nước đã từng tái cơ cấu chủ động nhiều lần ít có khả năng tái cơ cấu chủ động thêm.

AUC đo khả năng phân loại của mô hình, từ 0,5 (đoán ngẫu nhiên) đến 1 (phân loại hoàn hảo). Thêm ba biến dự báo nâng AUC từ 0,79 lên 0,87 cho vỡ nợ, và từ 0,85 lên 0,94 cho tái cơ cấu chủ động. Đường ROC và mật độ xác suất dự báo cho thấy mô hình phân loại tốt, và sau khi gán trọng số, các quan sát trong nhóm có tái cơ cấu được phân bố đều hơn.

**Bước thứ ba: AIPW** (Jordà và Taylor 2016). Phương pháp gán trọng số thấp cho quan sát dễ bị tái cơ cấu và trọng số cao cho quan sát ít khả năng, để giảm thiên lệch chọn mẫu theo các biến quan sát được. Nó kết hợp hai phần: phần trọng số xác suất nghịch đảo và phần dự báo bằng hồi quy. Cách kết hợp này có ưu điểm là kết quả vẫn đúng nếu một trong hai phần được xác định đúng.

Để so sánh hệ số giữa hai loại tái cơ cấu, bài dùng hai phép kiểm định: bootstrap 1000 lần (lấy mẫu lại nhiều lần để ước lượng sai số) và thống kê z của Clogg và cộng sự (1995).

### 5. Kết quả AIPW

**Tỷ giá thực.** Theo AIPW, sau vỡ nợ tỷ giá thực mất giá sâu và kéo dài. Sau tái cơ cấu chủ động có cú sốc ban đầu lớn, rồi tỷ giá gần như hồi phục hết vào năm thứ năm. Khác biệt này rõ hơn so với số liệu thô.

**Nhập khẩu.** Tốc độ thay đổi tích luỹ (%) của tỷ lệ nhập khẩu trên GDP:

| Năm | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Tổng, sau vỡ nợ | −6,07\*\*\* | −15,01\*\*\* | −10,22\*\*\* | −0,65 | 3,78 |
| Tổng, chủ động | 0,1 | −2,59\* | 0,4 | 2,99 | 6,64\*\* |
| Hàng chế tạo, sau vỡ nợ | −7,21\*\*\* | −17,04\*\*\* | −13,73\*\*\* | 1,39 | 1,33 |
| Hàng chế tạo, chủ động | −0,61 | −2,01 | −3,17 | 5,51\*\* | 10,77\*\*\* |
| Hàng sơ cấp, sau vỡ nợ | −7,05\*\*\* | −12,51\*\*\* | −9,68\*\*\* | −13,58\*\*\* | −3,31 |
| Hàng sơ cấp, chủ động | −0,87 | −2,55 | 2,81 | 0,5 | −1,36 |

Đọc bảng theo ba ý:

1. Sau vỡ nợ, nhập khẩu sụp 10–15% cho tới năm 3, sâu nhất ở năm 2 với −15,01%, tương đương khoảng 2 điểm phần trăm GDP. Lý do là GDP giảm mạnh làm cầu nhập khẩu co lại, và tỷ giá mất giá làm giá nhập khẩu tính bằng nội tệ tăng vọt.
2. Hàng chế tạo và hàng sơ cấp giảm với mức tương đương nhau, nhưng hàng chế tạo hồi phục từ năm 4, còn hàng sơ cấp giảm lâu hơn (vẫn −13,58% ở năm 4).
3. Sau tái cơ cấu chủ động, nhập khẩu ổn định, thậm chí tăng khoảng 7% (6,64%) tới năm 5.

Lưu ý: khác biệt giữa hai loại tái cơ cấu có ý nghĩa thống kê theo thống kê z của Clogg, nhưng **không** có ý nghĩa theo bootstrap.

**Xuất khẩu.** Tốc độ thay đổi tích luỹ (%) của tỷ lệ xuất khẩu trên GDP:

| Năm | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Tổng, sau vỡ nợ | −0,12 | −0,05 | 5,5\*\*\* | 11,04\*\*\* | 5,86\*\* |
| Tổng, chủ động | −7,57\*\*\* | −6,62\*\*\* | −4,86\*\* | −5,59\*\*\* | −6,38\*\*\* |
| Hàng chế tạo, sau vỡ nợ | 3,39 | 9,44\*\*\* | 17,26\*\*\* | 2,9 | 19,84\*\*\* |
| Hàng chế tạo, chủ động | −9,51\*\*\* | 3,91 | −19,77\*\*\* | −13,9\*\*\* | −10,76\*\*\* |
| Hàng sơ cấp, sau vỡ nợ | 1,79 | −0,3 | 4,71\*\*\* | 7,09\*\*\* | 3,66 |
| Hàng sơ cấp, chủ động | −7,11\*\*\* | −7,27\*\*\* | −5,99\*\*\* | −10,17\*\*\* | −14,6\*\*\* |

Đọc bảng:

1. Sau vỡ nợ, xuất khẩu tăng, đỉnh khoảng 11% ở năm 4, chủ yếu nhờ hàng chế tạo, nhất là tư liệu sản xuất. Cách giải thích: tỷ giá mất giá sâu và kéo dài, cộng với việc doanh nghiệp chuyển sản xuất sang phục vụ thị trường nước ngoài, đã bù được cú sốc cung tiêu cực (thiếu tài trợ thương mại, thiếu đầu vào).
2. Sau tái cơ cấu chủ động, xuất khẩu giảm khoảng 5% và duy trì như vậy qua cả năm năm.

**Kết quả đổi khi đo theo điểm phần trăm GDP.** Khi đo theo mức thay đổi thay vì tốc độ thay đổi, tác động lên xuất khẩu sau vỡ nợ gần như biến mất, chỉ còn khoảng +0,4 điểm phần trăm GDP. Sau tái cơ cấu chủ động, xuất khẩu vẫn giảm khoảng 1,7 điểm phần trăm GDP, chủ yếu ở hàng sơ cấp. Lý do: mức tăng phần trăm lớn sau vỡ nợ đến từ một nền xuất khẩu rất nhỏ ở các nền kinh tế tương đối đóng. Ví dụ minh hoạ: xuất khẩu tăng 11% từ nền 4% GDP chỉ là thêm khoảng 0,4 điểm phần trăm GDP. Vì vậy kết quả về nhập khẩu vững hơn nhiều so với kết quả về xuất khẩu.

**Độ vững.** Kết quả tương tự khi: đưa cả các trường hợp "lai" vào mẫu; lấy năm vỡ nợ thay cho năm công bố làm mốc; xử lý các đợt chồng lấn theo hai cách khác nhau ("chiến lược ban đầu", tức xếp theo loại của đợt đầu, và "chiến lược tệ nhất", tức xếp theo loại tệ hơn); và dùng hồi quy trung vị thay cho hồi quy trung bình.

### 6. Theo nhóm hàng

Phân tách theo mục đích sử dụng cho thấy rõ phần nào của thương mại chịu tác động (giá trị ước đọc từ hình).

**Nhập khẩu.**

| Nhóm | Diễn biến |
|---|---|
| Hàng chế tạo, sau vỡ nợ | Giảm chủ yếu ở tư liệu sản xuất (khoảng −23%) và hàng trung gian (khoảng −19%); hàng tiêu dùng chế tạo ổn định |
| Hàng chế tạo, chủ động | Ổn định, trừ một đợt giảm ở hàng trung gian; mức tăng cuối kỳ là nhờ tư liệu sản xuất |
| Hàng sơ cấp, sau vỡ nợ | Giảm ở cả hàng trung gian lẫn hàng tiêu dùng (khoảng −19% ở năm 3) |

Như vậy co nhập khẩu hàng chế tạo sau vỡ nợ chủ yếu là do cắt nhập máy móc thiết bị, một phần nhỏ hơn do cắt đầu vào trung gian; còn co nhập khẩu hàng sơ cấp đến từ cả đầu vào lẫn hàng tiêu dùng như lương thực và nhiên liệu.

**Xuất khẩu.**

| Nhóm | Diễn biến |
|---|---|
| Hàng chế tạo, sau vỡ nợ | Tăng nhờ tư liệu sản xuất (khoảng +45% ở năm 5) |
| Hàng chế tạo, chủ động | Cả ba nhóm cùng giảm |
| Hàng sơ cấp, sau vỡ nợ | Ổn định, có một đợt tăng tạm thời ở hàng tiêu dùng |
| Hàng sơ cấp, chủ động | Giảm, do hàng trung gian |

Khi đo theo điểm phần trăm GDP, trong các kết quả xuất khẩu chỉ còn rõ mức giảm khoảng 1 điểm phần trăm GDP của hàng sơ cấp trung gian sau tái cơ cấu chủ động.

### 7. Vai trò của tổng cầu

**Vì sao xét tổng cầu.** Mức độ phụ thuộc vào thương mại ảnh hưởng cả tới mức thiệt hại lẫn khả năng điều chỉnh. Nước mở hơn có thể dễ chuyển sang xuất khẩu hơn khi cầu trong nước sụp; nước đóng hơn thì việc co nhập khẩu từ một nền vốn đã thấp sẽ rất đau đớn.

Tổng cầu nội địa bằng tiêu dùng cộng đầu tư cộng chi tiêu chính phủ, tức bằng GDP trừ xuất khẩu ròng. Ngưỡng chia mẫu là trung vị của các đợt tái cơ cấu, bằng 101,8% GDP của năm trước tái cơ cấu. Nhóm "cầu cao" gồm một nửa số đợt sau vỡ nợ và một phần ba số đợt chủ động.

**Nhập khẩu** (tốc độ thay đổi tích luỹ, %):

| Năm | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Sau vỡ nợ, cầu cao | −14,74 | −23,1 | −25,21 | −19,15 | −11,07 |
| Sau vỡ nợ, cầu thấp | 3,65 | −5,85 | 2,64 | 10,8 | 13,96 |
| Chủ động, cầu cao | −12,09 | −13,32 | −6,78 | −6,4 | −0,05 |
| Chủ động, cầu thấp | 1,34 | 0,38 | −1,45 | 3,07 | −1,14 |

**Xuất khẩu** (tốc độ thay đổi tích luỹ, %):

| Năm | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Sau vỡ nợ, cầu cao | 0,05 | −2,46 | −4,51 | −7,13 | −4,88 |
| Sau vỡ nợ, cầu thấp | 3,09 | 4,56 | 15,62 | 33 | 24,46 |
| Chủ động, cầu cao | −4,35 | −2,03 | 4,68 | 2,53 | −2,64 |
| Chủ động, cầu thấp | 2,72 | 2,58 | −2,41 | −1,26 | −3,56 |

Đọc hai bảng theo ba ý:

1. Nước có tổng cầu cao, vốn đang hấp thụ nhiều nhập khẩu, co nhập khẩu mạnh nhất: tới −25% ở năm 3 sau vỡ nợ. Nước có tổng cầu thấp gần như không co nhập khẩu. Với tái cơ cấu chủ động, nhóm cầu cao cũng co nhập khẩu (khoảng −12% đến −13% hai năm đầu) và khác biệt giữa hai nhóm chủ yếu nằm ở hàng sơ cấp.
2. Mức tăng xuất khẩu sau vỡ nợ hoàn toàn đến từ nhóm có tổng cầu thấp (tới 33% ở năm 4), còn nhóm có tổng cầu cao lại giảm xuất khẩu.
3. Khác biệt giữa nhóm cao và thấp nhìn chung tập trung ở hàng chế tạo.

### 8. Kết luận

Cách một nước xử lý khủng hoảng nợ ảnh hưởng lớn tới thương mại của nó. Sau vỡ nợ, nhập khẩu co khoảng 15%, tương đương khoảng 2 điểm phần trăm GDP; sau tái cơ cấu chủ động, nhập khẩu gần như không đổi. Biến động lớn của xuất khẩu ròng có thể dùng làm thước đo gần đúng cho thiệt hại phúc lợi, và điều này khớp với các ước lượng về chi phí sản lượng của vỡ nợ trong tài liệu.

Khủng hoảng sâu và kéo dài có thể làm cán cân thương mại cải thiện, nhưng cái giá là co nhập khẩu và một mức xuất khẩu dựa vào mất giá thực lớn. Quan điểm trọng thương đơn giản coi xuất khẩu ròng cao là điều tốt; ở đây xuất khẩu ròng cao lại có thể là kết quả của một cuộc khủng hoảng sâu. Ví dụ minh hoạ: một nước có xuất khẩu không đổi nhưng nhập khẩu giảm 2 điểm phần trăm GDP sẽ thấy cán cân thương mại "cải thiện" 2 điểm, trong khi thực chất người dân và doanh nghiệp đang phải nhịn hàng hoá và máy móc.

Thông điệp chính sách của bài: bằng cách tái cơ cấu chủ động, các nước có thể làm dịu tác động mà nếu không sẽ đòi hỏi một cuộc điều chỉnh đối ngoại bị ép buộc và tốn kém về phúc lợi.

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

## Đánh giá và phát hiện đáng chú ý

### Cơ cấu của co nhập khẩu, và mắt xích nó cung cấp cho một tài liệu khác trong thư mục

Kết quả có sức nặng nhất trong toàn bài nằm ở phần phân tách theo nhóm hàng, và nó được trình bày như một chi tiết bổ sung.

Sau vỡ nợ, co nhập khẩu **không rơi đều**. Nhập khẩu **tư liệu sản xuất** giảm khoảng **23%**, nhập khẩu **hàng trung gian** giảm khoảng **19%**, trong khi nhập khẩu **hàng tiêu dùng chế tạo giữ ổn định**.

Đây là một mẫu hình có ý nghĩa rất rõ. Cuộc điều chỉnh đối ngoại bị ép buộc không được phân bổ lên tiêu dùng hiện tại; nó được dồn lên **năng lực sản xuất tương lai**. Máy móc không được nhập là nhà máy không được xây, dây chuyền không được nâng cấp, thiết bị không được thay. Cái giá của việc đó không xuất hiện trong năm khủng hoảng mà xuất hiện năm năm, mười năm sau, dưới dạng một trữ lượng vốn nhỏ hơn và một cơ cấu xuất khẩu lạc hậu hơn.

Vì sao lại phân bổ theo hướng đó? Câu trả lời là kinh tế chính trị, và bài không đưa ra. Cắt nhập khẩu hàng tiêu dùng là việc thấy ngay: kệ hàng trống, giá tăng, phản ứng xã hội tức thì. Cắt nhập khẩu tư liệu sản xuất thì **không ai nhìn thấy**, vì nó chỉ là một dự án bị hoãn và một đơn hàng không được ký. Khi ngoại tệ khan hiếm và phải phân bổ — bằng thị trường hay bằng hành chính — hệ thống chính trị sẽ chọn đúng cách phân bổ làm hoãn cái đau sang nhiệm kỳ sau.

Nhánh nghiên cứu về nợ công và tăng trưởng trong cùng thư mục tìm thấy một kết quả mà nó không giải thích được đầy đủ: nợ cao làm tăng trưởng chậm **chủ yếu qua kênh vốn trên mỗi lao động**, trong khi tác động lên năng suất nhân tố tổng hợp không có ý nghĩa thống kê ở bất kỳ phương pháp nào. Lời giải thích được đưa ra là chèn lấn cổ điển: nhà nước vay nhiều, lãi suất lên, vốn tư nhân bị đẩy ra. Nhưng cơ chế chèn lấn đòi hỏi một thị trường vốn đóng, và nó không giải thích được vì sao tác động ở nước mới nổi lại lớn gần gấp đôi nước phát triển.

Bài này cung cấp một cơ chế khác, cụ thể hơn và phù hợp hơn với nhóm nước mới nổi: **sau một cuộc khủng hoảng nợ, nước đó ngừng nhập máy móc**. Không phải vì lãi suất trong nước cao, mà vì ngoại tệ không còn, tỷ giá mất giá làm giá nhập khẩu tính bằng nội tệ tăng vọt, và tài trợ thương mại bị gián đoạn.

Hai kết quả này chưa bao giờ được nối với nhau — hai bài không trích dẫn nhau và thuộc hai nhánh tài liệu khác nhau. Nhưng chúng khớp gần như hoàn hảo: một bài đo được rằng thiệt hại tăng trưởng của khủng hoảng nợ đi qua tích luỹ vốn; bài kia đo được rằng đúng dòng nhập khẩu tạo ra tích luỹ vốn là dòng bị cắt mạnh nhất. Đặt cạnh nhau, chúng tạo thành một chuỗi nhân quả hoàn chỉnh mà không bài nào tự mình dựng được.

### Nửa gây ngạc nhiên nhất của kết luận là nửa không sống sót qua phép đổi đơn vị

Phần tóm tắt và câu trích dẫn trung tâm đều nhấn mạnh rằng tái cơ cấu sau vỡ nợ **đi kèm xuất khẩu cao hơn**. Các con số trông rất ấn tượng: tổng xuất khẩu tăng 11,04% ở năm 4, hàng chế tạo tăng 19,84% ở năm 5, riêng tư liệu sản xuất tăng khoảng 45%.

Nhưng chính bài ghi nhận rằng khi đo theo **điểm phần trăm GDP** thay vì theo tốc độ thay đổi, hiệu ứng sau vỡ nợ **gần như biến mất, còn khoảng +0,4 điểm**. Lý do được nêu thẳng: mức tăng phần trăm lớn đến từ một **nền rất nhỏ** ở các nền kinh tế tương đối đóng.

Nói cách khác, "xuất khẩu tăng 45%" ở đây có thể có nghĩa là xuất khẩu tư liệu sản xuất đi từ 0,3% GDP lên 0,44% GDP. Về mặt phúc lợi và về mặt điều chỉnh đối ngoại, con số đó không có ý nghĩa gì.

Kết quả về **nhập khẩu** thì sống sót qua cả hai thước đo: giảm khoảng 15% tương đương khoảng 2 điểm phần trăm GDP. Bài tự nói rằng kết quả nhập khẩu vững hơn kết quả xuất khẩu.

Đây là một ví dụ sạch về việc một kết luận mạnh hơn bằng chứng cho phép. Cách trích dẫn đúng là: **tái cơ cấu sau vỡ nợ đi kèm co nhập khẩu lớn và có ý nghĩa; tác động lên xuất khẩu không được xác lập**. Vế thứ hai gần như chắc chắn sẽ là vế được lan truyền, vì nó bất ngờ hơn.

### So sánh trung tâm của bài chỉ vượt được phép kiểm định ít bảo thủ hơn trong hai phép

Toàn bộ giá trị của bài nằm ở việc **hai loại tái cơ cấu khác nhau**. Bài dùng hai phép kiểm định để so hệ số giữa hai nhóm: thống kê z của Clogg và bootstrap 1000 lần.

Khác biệt giữa hai loại có ý nghĩa theo z của Clogg, **không có ý nghĩa theo bootstrap**.

Đây là một chi tiết mà bài báo cáo trung thực và người đọc cần cân nhắc đúng mức. Bootstrap là phép kiểm định bảo thủ hơn và phù hợp hơn ở đây, vì nó tính được cả sai số phát sinh từ việc **trọng số AIPW cũng là đại lượng được ước lượng** ở bước một — một nguồn bất định mà công thức của Clogg bỏ qua. Khi hai phép kiểm định cho kết luận ngược nhau, kết luận nên theo phép bảo thủ hơn.

Điều đó không làm bài mất giá trị. Bằng chứng mô tả vẫn rõ ràng và hướng của kết quả nhất quán qua nhiều kiểm tra độ vững. Nhưng nó có nghĩa là mệnh đề "tái cơ cấu chủ động ít tốn kém hơn về thương mại" nên được phát biểu như một **kết quả gợi ý**, không phải một khác biệt đã được xác lập về mặt thống kê.

### Tổng cầu ban đầu quyết định tất cả, và loại tái cơ cấu không hoàn toàn là một lựa chọn

Phần được trình bày như một mở rộng lại là phần đảo ngược cách đọc cả bài.

Chia mẫu theo tổng cầu nội địa trước khủng hoảng, với ngưỡng là trung vị **101,8% GDP**, cho ra hai thế giới khác hẳn nhau:

| | nhập khẩu, năm 3 | xuất khẩu, năm 4 |
|---|---|---|
| sau vỡ nợ, tổng cầu **cao** | **−25,21%** | −7,13% |
| sau vỡ nợ, tổng cầu **thấp** | **+2,64%** | **+33%** |

Đây không phải sự khác biệt về mức độ mà là sự khác biệt về **dấu**. Một nước bước vào khủng hoảng với tổng cầu nội địa trên 101,8% GDP — tức đang hấp thụ nhiều hơn mình sản xuất, được tài trợ bằng vay nước ngoài — co nhập khẩu một phần tư và giảm xuất khẩu. Một nước không ở tình trạng đó **tăng cả nhập khẩu lẫn xuất khẩu** sau vỡ nợ.

Hệ quả là tác động bình quân của "tái cơ cấu sau vỡ nợ" gần như không mang thông tin, vì nó là trung bình của hai hiện tượng đối nghịch.

Và nó gợi một cách đọc nhân quả khác với cách bài đưa ra. Thứ gây ra cuộc điều chỉnh đối ngoại đau đớn có lẽ không phải là **vỡ nợ**, mà là **mất cân đối đối ngoại có sẵn từ trước**. Vỡ nợ chỉ là thời điểm nguồn tài trợ cho mất cân đối đó dừng lại. Một nước tiêu nhiều hơn sản xuất buộc phải điều chỉnh khi không vay được nữa, bất kể việc ngừng vay được đó mang hình thức pháp lý nào.

Nếu cách đọc này đúng thì thông điệp chính sách phải đổi. Không phải "tái cơ cấu chủ động để tránh điều chỉnh đau đớn", mà là "**đừng để tổng cầu nội địa vượt quá xa sản lượng trong thời gian dài, vì đó mới là khoản nợ thật sẽ phải trả**".

Khuyến nghị cuối bài — tái cơ cấu chủ động giúp tránh một cuộc điều chỉnh đối ngoại bị ép buộc và tốn kém — giả định rằng loại tái cơ cấu là một **biến chính sách** mà chính phủ chọn được.

Thực tế hạn chế hơn nhiều. Tái cơ cấu chủ động đòi hỏi chủ nợ chịu ngồi vào bàn **trước khi** có một khoản thanh toán bị lỡ, và điều đó đòi hỏi con nợ còn ít nhiều khả năng tiếp cận thị trường, một chính phủ đủ gắn kết để đàm phán, một bộ máy kỹ thuật đủ năng lực, và thời gian. Một nước đâm vào bức tường thanh khoản không có lựa chọn chủ động nào cả.

Phương pháp AIPW xử lý **thiên lệch chọn mẫu theo biến quan sát được**, và bài nói rõ như vậy. Nhưng các yếu tố vừa kể — năng lực nhà nước, sự gắn kết chính trị, chất lượng quan hệ với chủ nợ — chính là những biến **không quan sát được**, và chúng đồng thời quyết định cả loại tái cơ cấu lẫn kết cục thương mại.

Một dấu hiệu định lượng cho điều này nằm ngay trong bài: mô hình probit bước một đạt AUC **0,935** cho tái cơ cấu chủ động. Khả năng phân loại tốt là điều tốt cho việc gán trọng số, nhưng nó cũng có nghĩa là **loại tái cơ cấu gần như dự đoán được hoàn toàn từ hoàn cảnh** — tức là rất xa một phép gán ngẫu nhiên. Càng dự đoán được tốt, càng ít có thể coi sự khác biệt về kết cục là tác động nhân quả của lựa chọn.

### Một kết quả phụ có hàm ý lớn: khả năng tái cơ cấu êm thấm được quyết định một phần ở Washington

Trong bảng probit, **lãi suất Fed** có hệ số **+5,442** với tái cơ cấu sau vỡ nợ và **−3,351** với tái cơ cấu chủ động. Tức là khi Fed thắt chặt, xác suất một nước rơi vào vỡ nợ cứng tăng lên, còn xác suất nước đó xử lý được êm thấm giảm xuống.

Bài đưa biến này vào như một công cụ nhận dạng và không bình luận thêm. Nhưng về mặt nội dung, đây là một mệnh đề về chu kỳ tài chính toàn cầu với hệ quả rõ ràng: **cửa sổ để tái cơ cấu chủ động mở và đóng theo điều kiện tài chính quốc tế, không theo mức độ sẵn sàng của con nợ**. Một nước nhận ra mình cần tái cơ cấu vào đúng chu kỳ thắt chặt sẽ thấy chủ nợ không chịu đàm phán trước, vì họ có lựa chọn thay thế hấp dẫn hơn ở nơi khác.

Hàm ý thực tiễn là tính thời điểm quan trọng hơn người ta tưởng, và rằng việc trì hoãn một cuộc tái cơ cấu cần thiết không chỉ tốn thêm thời gian — nó có thể làm mất luôn hình thức ít tốn kém của cuộc tái cơ cấu đó. Đây là mối liên hệ trực tiếp với nhánh tài liệu về dòng vốn và chu kỳ tài chính toàn cầu trong repo.

### Với Việt Nam: giá trị nằm ở chỉ báo, và một lưu ý về phạm vi mẫu

Việt Nam không ở trong tình huống mà bài mô tả, và khả năng rơi vào đó trong tầm nhìn hiện tại là thấp. Giá trị của tài liệu nằm ở ba chỉ báo và một cách đọc số liệu.

**Nhập khẩu tư liệu sản xuất là chỉ báo sớm cho tích luỹ vốn.** Kết quả trung tâm của bài — khi ngoại tệ khan hiếm, tư liệu sản xuất là thứ bị cắt trước, không phải hàng tiêu dùng — có nghĩa là một đợt sụt giảm nhập khẩu máy móc và thiết bị là tín hiệu sớm về đầu tư của những năm sau, và nó xuất hiện trước khi bất kỳ số liệu về hình thành tài sản cố định nào được công bố.

**Co nhập khẩu hàng trung gian là một cú sốc cung, không phải một cơ chế ổn định.** Với một nền kinh tế mà xuất khẩu phụ thuộc nặng vào đầu vào nhập khẩu — đúng cấu trúc của ngành điện tử và dệt may Việt Nam — việc cắt nhập khẩu hàng trung gian **trực tiếp cắt năng lực xuất khẩu**. Điều này giúp giải thích vì sao kết quả xuất khẩu của bài lại mơ hồ đến vậy: ở các nước hội nhập sâu vào chuỗi giá trị, hai kênh triệt tiêu nhau. Và nó có nghĩa là với Việt Nam, một cú sốc ngoại tệ sẽ **không** tạo ra sự cải thiện cán cân thương mại nhờ mất giá như mô hình sách giáo khoa dự đoán, vì mất giá đồng thời làm đắt lên chính các đầu vào mà xuất khẩu cần.

**Tổng cầu nội địa so với GDP là biến phân nhóm đáng theo dõi.** Bài dùng ngưỡng 101,8% GDP để tách hai thế giới. Đại lượng này chính là mức độ hấp thụ vượt quá sản lượng, và nó là chỉ báo cho biết một nền kinh tế sẽ phải điều chỉnh bao nhiêu nếu nguồn tài trợ bên ngoài dừng lại.

**Và một cách đọc số liệu cần ghi nhớ:** cán cân thương mại cải thiện đột ngột không phải tin tốt. Bài phản bác thẳng quan điểm trọng thương đơn giản, và lập luận của nó áp dụng rộng hơn phạm vi khủng hoảng nợ. Xuất khẩu ròng tăng vì xuất khẩu tăng là một chuyện; xuất khẩu ròng tăng vì nhập khẩu tư liệu sản xuất sụp là chuyện hoàn toàn khác, và trong thống kê tổng hợp chúng trông giống hệt nhau.

Cuối cùng, cần đặt mẫu của bài vào bối cảnh mà các tài liệu khác trong thư mục cung cấp. Đây là 194 đợt tái cơ cấu **nợ nước ngoài với chủ nợ tư nhân**, giai đoạn **1975–2019**.

Nhưng nhánh tài liệu về dễ tổn thương nợ của các nền kinh tế mới nổi cho thấy cơ cấu chủ nợ đã dịch chuyển mạnh sang tư nhân và song phương ngoài Câu lạc bộ Paris trong đúng thập kỷ cuối của mẫu này, và một tài liệu khác trong thư mục cho thấy tái cơ cấu nợ **trong nước** đã trở thành một phần ngày càng lớn của bức tranh. Một cuộc tái cơ cấu điển hình ngày nay có tập chủ nợ phân mảnh hơn, có cấu phần nội địa lớn hơn, và có cơ chế phối hợp yếu hơn so với một cuộc tái cơ cấu điển hình trong mẫu.

Các hệ số ước lượng ở đây vì thế mô tả một chế độ đang lùi vào quá khứ. Cơ chế — co nhập khẩu dồn vào tư liệu sản xuất, vai trò quyết định của mất cân đối đối ngoại có sẵn — nhiều khả năng vẫn đúng. Độ lớn thì không nên ngoại suy.
