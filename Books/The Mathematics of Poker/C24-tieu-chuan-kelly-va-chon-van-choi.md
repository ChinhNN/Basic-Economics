# Chương 24 — Làm bankroll tăng trưởng: tiêu chuẩn Kelly và chọn trò chơi hợp lý (Growing Bankrolls: The Kelly Criterion and Rational Game Selection)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 24 "Growing Bankrolls: The Kelly Criterion and Rational Game Selection", trang 318–323.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 22 ([C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md)) và Chương 23 ([C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md)) đo rủi ro phá sản (risk of ruin) với giả định chơi mãi một trò chơi ở một mức cược cố định; Chương 23 đã nhiều lần hứa bàn việc "xuống mức cược thấp hơn" khi bankroll giảm. Chương 24 bỏ giả định mức cược cố định: thay vì tối đa hoá kỳ vọng tính bằng đô la, người chơi tối đa hoá hàm hữu dụng logarit U(x) = ln x — tiêu chuẩn Kelly — để bankroll tăng nhanh nhất; khái niệm hữu dụng (utility) đã được nhắc ở Phần I ([C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md)). Chương dùng lại trò xúc xắc của Chương 22 và các khái niệm phương sai, độ lệch chuẩn của Chương 2 ([C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md)), rồi áp vào "quyết định ngoài ván bài" (metagame): chơi bàn nào, mức cược nào. Chương 25 ([C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md)) mở rộng sang chơi nhiều trò chơi cùng lúc như một danh mục và đánh giá thoả thuận tài trợ cũng bằng hữu dụng Kelly; Phần V ([C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md)) quay lại giải đấu, nơi công thức xấp xỉ của chương này không dùng được.
**Ý chính:** **Khi mục tiêu là làm bankroll tăng nhanh nhất, người chơi nên tối đa hoá kỳ vọng của ln(bankroll) thay vì kỳ vọng của bankroll; áp vào việc chọn giữa hai trò chơi có tỷ lệ thắng μ₁ > μ₂ và độ lệch chuẩn σ₁ > σ₂, điều này cho một ngưỡng bankroll c = [μ₁ + μ₂ + (σ₁² − σ₂²)/(μ₁ − μ₂)]/2 ≈ (σ₁² − σ₂²)/(2(μ₁ − μ₂)): trên ngưỡng chơi trò lớn, dưới ngưỡng chơi trò nhỏ.** Chương mở bằng khái niệm hữu dụng: hàm U(x) tăng, thường lõm (đồng tiền thêm vào có giá trị ít hơn khi đã giàu), coi như liên tục; giá trị chắc chắn tương đương (certainty equivalent) của một vụ cược là số tiền X có U(X) bằng hữu dụng kỳ vọng của vụ cược. Tối đa hoá kỳ vọng đô la đòi đặt cả bankroll vào mọi vụ cược có lợi, nhưng thua là hết vốn để tăng tiếp; hàm ln x tối đa hoá tốc độ tăng trưởng mỗi lần chơi. Đặt cược theo Kelly tối đa hoá trung vị bankroll sau một số lần chơi, tối thiểu hoá thời gian trung bình để đạt một mức bankroll, và cho phân phối bankroll log-chuẩn. Ví dụ 24.1: người cá cược thể thao thắng 51,5%, trả ngang (even money), bankroll $5.000, đặt cược tối ưu $150, tức 3% bankroll — bằng đúng lợi thế. Cược Kelly có rủi ro phá sản bằng 0 nếu chia nhỏ bankroll tuỳ ý, nhưng poker không có đủ mọi mức cược; tính logarit khiến gấp đôi bankroll và mất một nửa bankroll có giá trị tuyệt đối bằng nhau; người sẵn sàng lên xuống mức cược theo bankroll có thể chơi mức cao với bankroll nhỏ hơn nhiều. Tác giả nhận xét người chơi thường quá ngại rủi ro (muốn rủi ro phá sản chỉ 5%, trong khi doanh nhân sẽ mừng với 5% thất bại) và mất nhiều lợi nhuận vì chơi mức thấp quá lâu. Chương cũng đảo bài toán: với cược cố định, tìm bankroll tối ưu; với trò xúc xắc thắng/thua 1 đơn vị (2/3 và 1/3), bankroll tối ưu là 3. Khai triển Taylor ln(1 + x/B) ≈ x/B − x²/(2B²) cho hữu dụng Kelly của một giờ chơi U ≈ μ/B − (μ² + σ²)/(2B²), từ đó ra công thức ngưỡng (24.1). Ví dụ 24.2 so $20-40 hold'em ($35/giờ, độ lệch chuẩn $400/giờ) với $40-80 ($60/giờ, $800/giờ): sách cho ngưỡng $19.295, nhưng người tổng hợp tính lại thấy đó là giá trị của 2c; ngưỡng đúng là c ≈ $9.648. Công thức không dùng được khi có kết quả cỡ bankroll, như giải đấu đông người.

> **Lưu ý:**
> - **Ví dụ 24.2 tính sai ngưỡng bankroll gấp đôi (trang 323):** sách viết 2c = 60 + 35 + (800² − 400²)/(60 − 35) rồi kết luận "c = $19,295". Tính: (640.000 − 160.000)/25 = 19.200, cộng 95 được **2c = 19.295**, nên **c = $9.647,50**. Công thức xấp xỉ 24.1 cho c ≈ 480.000/(2 × 25) = $9.600, khớp với $9.647,50 chứ không khớp $19.295. Kiểm tra trực tiếp: tại B = $9.647,50, hữu dụng Kelly mỗi giờ của hai trò chơi bằng nhau (cùng 0,00276); tại B = $19.295, trò $40-80 cho 0,00225 còn $20-40 chỉ cho 0,00160, tức trò lớn đã tốt hơn rõ. Vậy theo đúng mô hình của sách, người có bankroll khoảng $9.650 trở lên nên chơi $40-80, không phải $19.295.
> - **Khai triển Taylor của ln(1 + t) in sai (trang 321–322):** sách viết ln(1 + t) = t − t²/2! + t³/3! − t⁴/4! + …, và do đó ln(1 + x/B) = x/B − x²/(2!B²) + x³/(3!B³) − …; rồi lập luận các số hạng bậc cao có "(n!)(Bⁿ) ở mẫu nên tiến về 0 cực nhanh". Khai triển đúng là ln(1 + t) = t − t²/2 + t³/3 − t⁴/4 + … (mẫu là n, không phải n!; các giai thừa thuộc khai triển của eᵗ). Vì 2! = 2, hai số hạng đầu trùng nhau nên kết quả U ≈ x/B − x²/(2B²) và công thức 24.1 không bị ảnh hưởng; nhưng lý do bỏ các số hạng bậc cao là xⁿ/(nBⁿ) nhỏ khi x nhỏ so với B, không phải vì giai thừa. Sách cũng nói "bỏ số hạng thứ ba trở đi" — đúng, giữ hai số hạng đầu.
> - **Thiếu dấu bằng (trang 322):** dòng "⟨(x² − 2xμ + μ²)⟩ σ²" thiếu "=": đúng là ⟨x² − 2xμ + μ²⟩ = σ². Dòng "⟨(x − μ)²⟩ = σ2" là σ².
> - **Các tính chất của cược Kelly là tính chất tiệm cận (nhận xét của người tổng hợp):** "tối đa hoá trung vị bankroll sau một số lần chơi cho trước" và "tối thiểu hoá thời gian trung bình để đạt một mức bankroll" đúng theo nghĩa tiệm cận (khi số lần chơi lớn, hoặc mục tiêu xa), theo hiểu biết của người tổng hợp; với số lần chơi hữu hạn nhỏ, chiến lược khác có thể có trung vị cao hơn đôi chút. "Phân phối bankroll log-chuẩn" cũng là xấp xỉ khi số lần chơi lớn.
> - **"Giá trị chắc chắn tương đương" và ký hiệu (trang 318):** sách dùng chữ B cho vụ cược và b cho các kết quả của nó, rồi ở phần sau dùng B cho bankroll. Bản tổng hợp gọi vụ cược là "vụ cược B" ở mục 1 và dùng B cho bankroll từ mục 4 trở đi.
> - **Ví dụ đồng xu triệu đô (trang 318):** sách nói "50% thời gian ta nhận hữu dụng của một triệu, 50% hữu dụng của 0". Với hàm ln x của Kelly, hữu dụng của bankroll 0 là −∞, nên người dùng Kelly thuần tuý không bao giờ chọn tung đồng xu nếu đó là toàn bộ tài sản; ví dụ này minh hoạ hàm hữu dụng lõm nói chung, chưa phải hàm Kelly (nhận xét của người tổng hợp).
> - **Lỗi chính tả và OCR:** "the lust bet" ("last"), "risk of rum" ("ruin"), "hi general" ("in general"), "increase out-Kelly utility" ("our Kelly utility"), "which game to play ill a quantitative manner" ("in"), "quantify'" ("quantify"), "< In (B + x) >" ("ln").
> - **Quy ước thuật ngữ:** "utility" dịch là "hữu dụng" (độ thoả dụng); "Kelly criterion" là "tiêu chuẩn Kelly"; "Kelly betting" là "cược theo Kelly"; "certainty equivalent" là "giá trị chắc chắn tương đương"; "metagame decisions" là "quyết định ngoài ván bài" (chọn trò chơi, chọn mức cược, có chơi hay không); "cutoff bankroll" là "ngưỡng bankroll"; "even money" là "trả ngang" (thắng bao nhiêu nhận bấy nhiêu); "juice" là phí của nhà cái. "$20-40" là mức cược limit: small bet $20, big bet $40.

## Sơ đồ

### Phần mở đầu Chương 24 — hữu dụng và giá trị chắc chắn tương đương (trang 318)

```text
       Tạm rời ví dụ poker để bàn tiêu chuẩn Kelly — quan trọng trong
       lý thuyết danh mục cổ phiếu, blackjack, cá cược thể thao: có
       bankroll và một vụ cược kỳ vọng dương, chọn mức cược để bankroll
       tăng nhanh nhất
                                │
                                ▼
       HỮU DỤNG (utility): mức ưa thích tiền đã điều chỉnh
       · $20 hơn $10: hữu dụng của $20 cao hơn
       · tung đồng xu công bằng lấy $1.000.000 hay nhận chắc $500.000?
         đa số chọn tiền chắc: hữu dụng của 1 triệu không gấp đôi hữu
         dụng của nửa triệu
                                │
                                ▼
       HÀM HỮU DỤNG U(x), riêng cho mỗi người:
       · tăng với mọi x > 0 (không ai thích ít tiền hơn — nếu thích thì
         cứ cho đi phần chênh)
       · thường lõm: càng giàu, thêm một đô la càng ít giá trị
       · coi như liên tục
                                │
                                ▼
       GIÁ TRỊ CHẮC CHẮN TƯƠNG ĐƯƠNG của vụ cược B: số tiền X sao cho
       U(X) = ⟨U(kết quả của B)⟩
       · với khoản tiền rất nhỏ, X gần ⟨B⟩ (hữu dụng gần tuyến tính)
       · với đồng xu triệu đô, X thấp hơn nhiều so với $500.000
```

### Tiêu chuẩn Kelly và các tính chất của cược theo Kelly (trang 318–319)

```text
       Tối đa hoá kỳ vọng đô la ⇒ đặt CẢ bankroll vào mọi vụ cược có lợi
       · nhưng thua thì bankroll nhỏ đi, lần sau tăng từ nền thấp hơn
                                │
                                ▼
       Kelly: tối đa hoá tốc độ tăng trưởng mỗi lần chơi bằng cách tối
       đa hoá kỳ vọng của hàm hữu dụng U(x) = ln x
                                │
                                ▼
       Ba tính chất (giữa mọi chiến lược đặt cược):
       · tối đa hoá TRUNG VỊ bankroll sau một số lần chơi cho trước
       · tối thiểu hoá THỜI GIAN TRUNG BÌNH để đạt một mức bankroll
       · bankroll có phân phối LOG-CHUẨN (logarit của bankroll có phân
         phối chuẩn) — phân phối quen thuộc trong tài chính, quyền chọn
```

### Ví dụ 24.1 — người cá cược thể thao có lợi thế 3% (Example 24.1, trang 319)

```text
       Thắng 51,5%, thua 48,5%, trả ngang (đã tính phí nhà cái); lợi thế
       3%; bankroll $5.000; được cược số tiền bất kỳ
                                │
                                ▼
       Cược x đô la: ⟨U⟩ = 0,515·ln(5.000 + x) + 0,485·ln(5.000 − x)
       Đạo hàm bằng 0: 0,515/(5.000 + x) − 0,485/(5.000 − x) = 0
       ⇒ x = $150 = 3% bankroll
                                │
                                ▼
       Với mọi vụ cược trả ngang: cược tỷ lệ bankroll BẰNG lợi thế
       · thắng ván đầu: cược 3% của $5.150 = $154,50
       · thua ván đầu: cược 3% của $4.850 = $145,50
                                │
                                ▼
       Ý then chốt dùng cho chương: thay kỳ vọng đô la bằng hữu dụng
       ln x khi ra QUYẾT ĐỊNH NGOÀI VÁN BÀI (metagame): chơi trò nào, mức
       cược nào, có chơi poker không
```

### Bốn nhận xét về cược Kelly và mức chấp nhận rủi ro (trang 319–320)

```text
       1. Rủi ro phá sản bằng 0 nếu chia nhỏ bankroll tuỳ ý: thua thì
          giảm cược ngay, thắng thì tăng cược ngay
       2. Không áp dụng trực tiếp cho poker: sòng bài không mở bàn mức
          $1,02-$2,04 hay $12,46-$24,92
       3. Tính logarit: gấp đôi bankroll được bao nhiêu hữu dụng thì mất
          một nửa bankroll mất bấy nhiêu; bankroll đã nhỏ thì mất thêm
          một phần là thảm hoạ, bankroll lớn thì thắng thêm một khoản
          lớn tuyệt đối cũng không đáng bao nhiêu
       4. Cho phép mạo hiểm hơn mô hình rủi ro phá sản, vì tự điều chỉnh
          mức cược; người sẵn sàng lên xuống mức cược theo bankroll chơi
          được mức cao với bankroll ngắn hơn nhiều
                                │
                                ▼
       Nhận xét của tác giả: người chơi thường QUÁ ngại rủi ro
       · muốn chỉ 5% khả năng mất vốn ban đầu; doanh nhân sẽ mừng rỡ với
         5% khả năng thất bại
       · nhưng doanh nghiệp poker khó bán lại được giá cao như công ty
       · người thận trọng ở mức thấp quá lâu, bỏ lỡ nhiều lợi nhuận
```

### Chọn giữa hai trò chơi và khái niệm bankroll tối ưu (trang 320–321)

```text
       Sòng bài chỉ có một số mức cược và số bàn hữu hạn ⇒ thường phải
       chọn giữa HAI trò chơi
       · nếu một trò vừa kỳ vọng cao hơn vừa phương sai thấp hơn: rõ ràng
       · thường gặp: trò lớn lợi nhuận cao, phương sai cao (tính bằng đô
         la) so với trò nhỏ lợi nhuận thấp, phương sai thấp
                                │
                                ▼
       Đảo bài toán Kelly: cược CỐ ĐỊNH, tìm BANKROLL làm hữu dụng Kelly
       tăng nhiều nhất khi chơi
       · hữu dụng Kelly của việc chơi: ⟨ln(B + x)⟩ − ln B
                                │
                                ▼
       Trò xúc xắc (thắng 1 với 2/3, thua 1 với 1/3):
       U(B) = (1/3)ln(B − 1) + (2/3)ln(B + 1) − ln B
       U′(B) = 1/(3(B − 1)) + 2/(3(B + 1)) − 1/B = 0
       ⇒ B(B + 1) + 2B(B − 1) − 3(B − 1)(B + 1) = 0 ⇒ −B + 3 = 0
       ⇒ bankroll tối ưu B = 3 (khớp Kelly: cược 1/3 bankroll)
```

### Dẫn công thức ngưỡng bankroll 24.1 (trang 321–322)

```text
       Giả định: trò 1 (lớn hơn) và trò 2; tỷ lệ thắng μ₁, μ₂ và độ lệch
       chuẩn σ₁, σ₂ đã biết, đều dương và hữu hạn; bankroll B
       Mô hình: có ngưỡng c — trên c chơi trò 1 tăng hữu dụng Kelly nhiều
       hơn, dưới c chơi trò 2
                                │
                                ▼
       U = ⟨ln(B + x)⟩ − ln B = ⟨ln(1 + x/B)⟩
       Taylor: ln(1 + t) = t − t²/2 + t³/3 − …; B lớn so với x
       ⇒ U ≈ ⟨x/B − x²/(2B²)⟩
       · ⟨x⟩ = μ; ⟨x²⟩ = μ² + σ² (vì σ² = ⟨x²⟩ − μ²)
       ⇒ U ≈ μ/B − (μ² + σ²)/(2B²)
                                │
                                ▼
       Đặt hữu dụng hai trò bằng nhau tại B = c, nhân 2c²:
       2cμ₁ − μ₁² − σ₁² = 2cμ₂ − μ₂² − σ₂²
       ⇒ 2c = μ₁ + μ₂ + (σ₁² − σ₂²)/(μ₁ − μ₂)
       Trong poker μ rất nhỏ so với phương sai:
       c ≈ (σ₁² − σ₂²) / (2(μ₁ − μ₂))                          (24.1)
```

### Ví dụ 24.2 — $20-40 hay $40-80 hold'em (Example 24.2, trang 322–323)

```text
       $20-40: μ₂ = $35/giờ, σ₂ = $400/giờ
       $40-80: μ₁ = $60/giờ, σ₁ = $800/giờ
                                │
                                ▼
       2c = 60 + 35 + (800² − 400²)/(60 − 35) = 95 + 19.200 = 19.295
       · sách: "c = $19.295" — SAI, đó là 2c
       · đúng: c = $9.647,50 (xấp xỉ 24.1: $9.600)
                                │
                                ▼
       Bankroll trên ngưỡng: chơi $40-80; dưới ngưỡng: chơi $20-40
                                │
                                ▼
       Giới hạn: công thức sai khi có kết quả cỡ bankroll (bỏ số hạng
       Taylor bậc cao không còn hợp lý) — thường gặp ở giải đấu đông
       người, giải nhất có thể hơn 500 buy-in; dùng được cho mọi loại
       cash game
```

### Phần "Key Concepts" — các khái niệm then chốt cuối chương (trang 323)

```text
       · Quyết định thực tế không thể chỉ dựa vào kỳ vọng; phải xét
         hữu dụng, gán hàm hữu dụng và đánh giá kết quả theo hữu dụng
       · Hàm hữu dụng được nghiên cứu nhiều trong thị trường tài chính
         vì tính chất đặc biệt trong lý thuyết danh mục: tiêu chuẩn
         Kelly, U(x) = ln x
       · Thay tiêu chuẩn Kelly vào hai bộ điều kiện trò chơi cho hữu dụng
         của mỗi trò; khi điều kiện phù hợp, có ngưỡng bankroll: trên
         ngưỡng chơi trò lớn, dưới ngưỡng chơi trò nhỏ
```

## Ba câu hỏi chương này trả lời

1. **Nếu muốn bankroll tăng nhanh nhất thì nên cược bao nhiêu?** Tối đa hoá kỳ vọng của ln(bankroll), không phải kỳ vọng của bankroll. Với vụ cược trả ngang có xác suất thắng p, cược tỷ lệ bankroll bằng lợi thế p − (1 − p): người cá cược thắng 51,5% với bankroll $5.000 cược $150 (3%), rồi điều chỉnh theo bankroll mới ($154,50 sau khi thắng, $145,50 sau khi thua). Cách này tối đa hoá trung vị bankroll và tốc độ tăng trưởng dài hạn, và (nếu chia nhỏ tuỳ ý) không bao giờ phá sản.
2. **Với một vụ cược cố định, bankroll bao nhiêu là tối ưu, và khi nào nên lên mức cược cao hơn?** Hữu dụng Kelly của một lần chơi là ⟨ln(B + x)⟩ − ln B ≈ μ/B − (μ² + σ²)/(2B²). Với trò xúc xắc ±1 (2/3, 1/3), bankroll tối ưu là 3 đơn vị. Giữa hai trò chơi, trò lớn tốt hơn khi bankroll vượt ngưỡng c = [μ₁ + μ₂ + (σ₁² − σ₂²)/(μ₁ − μ₂)]/2 ≈ (σ₁² − σ₂²)/(2(μ₁ − μ₂)). Với $20-40 ($35/giờ, σ $400) và $40-80 ($60/giờ, σ $800), ngưỡng đúng là khoảng $9.650 (sách in nhầm $19.295, là giá trị của 2c).
3. **Cách nhìn Kelly thay đổi thái độ với rủi ro ra sao?** Vì tự giảm cược khi thua, người sẵn sàng xuống mức thấp hơn có thể chơi mức cao với bankroll nhỏ hơn nhiều so với mô hình rủi ro phá sản (vốn giả định chơi mãi một mức). Tác giả cho rằng người chơi thường quá ngại rủi ro — đòi rủi ro phá sản 5% trong khi doanh nhân chấp nhận cao hơn nhiều — và mất lợi nhuận vì ở mức thấp quá lâu. Công thức không dùng cho giải đấu, nơi một kết quả có thể cỡ cả bankroll.

## Khái niệm cần biết

- **Hữu dụng (utility) và hàm hữu dụng U(x):** mức ưa thích một lượng tiền (hay bankroll) x, đã điều chỉnh theo hoàn cảnh người đó. Ví dụ: đa số chọn $500.000 chắc chắn thay vì 50% cơ hội lấy $1.000.000. Quan trọng vì chương thay kỳ vọng đô la bằng kỳ vọng hữu dụng khi chọn trò chơi.
- **Hàm lõm (concave downward):** đồ thị cong xuống, tức mỗi đô la thêm vào làm hữu dụng tăng ít hơn đô la trước. Ví dụ: một đô la nhặt được có giá trị với người nghèo lớn hơn với triệu phú. Quan trọng vì nó là lý do người ta ngại rủi ro.
- **Giá trị chắc chắn tương đương (certainty equivalent):** số tiền chắc chắn có cùng hữu dụng với một vụ cược. Ví dụ của người tổng hợp: với hữu dụng ln và tài sản nền $100.000, vụ tung đồng xu ±$50.000 có giá trị chắc chắn tương đương √(150.000 × 50.000) ≈ $86.600, tức thấp hơn $100.000 khoảng $13.400.
- **Tiêu chuẩn Kelly (Kelly criterion), cược theo Kelly (Kelly betting):** quyết định nhằm tối đa hoá ⟨ln(bankroll)⟩. Ví dụ: cược 3% bankroll khi có lợi thế 3% ở vụ cược trả ngang. Quan trọng vì nó tối đa hoá tốc độ tăng trưởng dài hạn của bankroll.
- **Tốc độ tăng trưởng mỗi lần chơi (growth rate per trial):** kỳ vọng của ln(bankroll sau/bankroll trước). Ví dụ: cược $150 trên $5.000 cho 0,000450 mỗi lần, tức bankroll tăng trung bình khoảng 0,045% mỗi vụ cược theo nghĩa nhân. Quan trọng vì đó là đại lượng Kelly tối đa hoá.
- **Phân phối log-chuẩn (log-normal):** phân phối của một biến mà logarit của nó có phân phối chuẩn. Ví dụ: bankroll sau nhiều lần cược theo Kelly. Quan trọng vì trung vị và trung bình của nó khác nhau: trung bình bị kéo lên bởi số ít trường hợp thắng rất lớn.
- **Quyết định ngoài ván bài (metagame decisions):** quyết định không gắn với một ván hay một trò cụ thể, như chơi trò nào, mức cược nào, có chơi poker không. Ví dụ: chọn $20-40 hay $40-80.
- **Hữu dụng Kelly của việc chơi một trò chơi:** ⟨ln(B + x)⟩ − ln B, mức tăng hữu dụng khi chơi thêm một đơn vị (giờ, ván). Ví dụ: trò xúc xắc với B = 3 cho 0,0566. Quan trọng vì so sánh nó giữa hai trò cho lựa chọn trò chơi.
- **Bankroll tối ưu (optimal bankroll):** với cược cố định, mức bankroll làm hữu dụng Kelly của việc chơi lớn nhất; theo xấp xỉ bậc hai, B* = (μ² + σ²)/μ (người tổng hợp suy ra). Ví dụ: trò xúc xắc có μ = 1/3, ⟨x²⟩ = 1, nên B* = 3, khớp sách.
- **Ngưỡng bankroll (cutoff bankroll) c:** mức bankroll mà hai trò chơi cho hữu dụng Kelly bằng nhau. Ví dụ: ≈ $9.650 giữa $20-40 và $40-80. Quan trọng vì nó là quy tắc lên/xuống mức cược.
- **Khai triển Taylor (Taylor series):** viết một hàm thành tổng các luỹ thừa. Ví dụ: ln(1 + t) = t − t²/2 + t³/3 − …; với t = 0,1, hai số hạng đầu cho 0,095, giá trị thật 0,0953. Quan trọng vì cho phép thay ⟨ln(1 + x/B)⟩ bằng biểu thức chỉ chứa μ và σ.
- **Trả ngang (even money) và phí nhà cái (juice):** thắng bao nhiêu nhận bấy nhiêu; phí nhà cái làm giảm lợi thế. Ví dụ: 51,5% thắng trả ngang cho lợi thế 0,515 − 0,485 = 3%.

## Nội dung chi tiết

### 1. Hữu dụng và giá trị chắc chắn tương đương (phần mở đầu chương, trang 318)

Dù đây là sách về toán của poker, tác giả tạm rời ví dụ poker trực tiếp để bàn một chủ đề cực kỳ quan trọng trong nhiều lĩnh vực: "tiêu chuẩn Kelly". Nó quan trọng trong lý thuyết danh mục cổ phiếu, blackjack, cá cược thể thao, và mọi lĩnh vực nơi có một bankroll ban đầu và một vụ cược kỳ vọng dương, người chơi chọn mức cược và mong bankroll tăng nhanh nhất có thể.

Ở Phần I, tác giả đã nhắc tới khái niệm **hữu dụng** (utility), một khái niệm khá rộng với nhiều khía cạnh vượt phạm vi cuốn sách. Ở đây, hữu dụng phản ánh mức ưa thích tiền của một người theo cách đã điều chỉnh. Sách bỏ qua các khía cạnh như "cảm giác muốn làm từ thiện", dù chúng quan trọng để hiểu đầy đủ về hữu dụng.

Ví dụ: được chọn giữa nhận $20 ngay hay nhận $10 ngay, rõ ràng ta chọn $20, vì gán hữu dụng cao hơn cho việc có $20. Giờ xét lựa chọn giữa tung một đồng xu công bằng để thắng $1.000.000 (hoặc không gì) và nhận chắc $500.000 ngay. Thường ta chọn tiền chắc, vì hữu dụng của một triệu đô la không gấp đôi hữu dụng của nửa triệu: 50% thời gian ta có hữu dụng của một triệu, 50% hữu dụng của 0.

Ta có thể dựng một **hàm hữu dụng**, ánh xạ mỗi mức bankroll x sang giá trị hữu dụng U(x). Hàm này riêng cho từng người và có các tính chất:

- **Tăng với mọi x > 0:** ta không bao giờ thích ít tiền hơn nhiều tiền. Nếu thích, khi có nhiều tiền ta chỉ cần cho đi phần chênh lệch để tăng hữu dụng.
- **Thường lõm (concave downward):** càng nhiều tiền, một đô la thêm vào càng ít hữu dụng. Chẳng hạn, hữu dụng một triệu phú nhận được khi nhặt được một đô la trên đường ít hơn nhiều so với người nghèo nhặt được cùng đô la đó.
- **Thường coi là liên tục** (dù tiền không thật sự liên tục).

Giả sử ta được đề nghị một vụ cược B. Có một số tiền X sao cho hữu dụng U(X) bằng hữu dụng của vụ cược, tức ⟨U(b)⟩ với b là các kết quả của B. Với khoản tiền rất nhỏ, X có thể rất gần ⟨B⟩ (kỳ vọng đô la của vụ cược), vì hữu dụng thường gần tuyến tính với khoản nhỏ. Nhưng với vụ tung đồng xu triệu đô, có một số tiền X là giá trị công bằng của vụ cược đối với ta tính theo hữu dụng. X gọi là **giá trị chắc chắn tương đương** (certainty equivalent) của B.

Minh hoạ của người tổng hợp với hàm ln và tài sản nền $100.000: vụ cược 50/50 thắng hay thua $50.000 có hữu dụng kỳ vọng 0,5 ln 150.000 + 0,5 ln 50.000 = ln √(150.000 × 50.000) = ln 86.603, nên giá trị chắc chắn tương đương là $86.603 — người này sẵn sàng trả tới khoảng $13.400 để tránh vụ cược có kỳ vọng 0.

### 2. Tiêu chuẩn Kelly và các tính chất của nó (trang 318–319)

Tiêu chuẩn Kelly tìm một hàm hữu dụng sao cho tốc độ tăng trưởng của bankroll hay danh mục là lớn nhất. Lý do: có thể tối đa hoá tổng kỳ vọng đô la chỉ bằng cách đặt toàn bộ bankroll vào mọi vụ cược kỳ vọng dương; nhưng khi thua, ta còn ít bankroll hơn để tăng ở lần sau. Để đạt mục tiêu tăng trưởng, ta tối đa hoá hàm hữu dụng Kelly U(x) cho mỗi vụ cược thay vì tối đa hoá kỳ vọng đô la. Vì lý do vượt phạm vi sách (người đọc quan tâm có thể xem trong giáo trình tài chính tốt), hàm hữu dụng tối đa hoá tốc độ tăng trưởng mỗi lần chơi là

$$U(x) = \ln x.$$

(Giải thích ngắn của người tổng hợp: sau n lần chơi, bankroll là B₀·r₁·r₂·…·rₙ với rᵢ là tỷ số bankroll sau/trước của lần i. Lấy logarit: ln Bₙ = ln B₀ + Σ ln rᵢ; theo luật số lớn, (1/n)Σ ln rᵢ → ⟨ln r⟩. Vậy tốc độ tăng trưởng dài hạn chính là ⟨ln r⟩, và tối đa hoá nó tương đương tối đa hoá ⟨ln(bankroll)⟩ mỗi lần.)

Các quyết định tối đa hoá hàm hữu dụng này được gọi là dùng **tiêu chuẩn Kelly**, hay gọn là **cược theo Kelly**. Cược theo Kelly có một số tính chất làm nó quan trọng trong lý thuyết danh mục và trong cá cược thể thao, blackjack. Trong mọi chiến lược đặt cược, nó:

- tối đa hoá **trung vị** bankroll sau một số lần chơi cho trước;
- tối thiểu hoá **thời gian trung bình** cần để đạt một mức bankroll định trước;
- cho phân phối bankroll **log-chuẩn**: vẽ logarit của các bankroll sẽ thấy phân phối chuẩn. Vì phân phối này quan trọng trong giao dịch quyền chọn và tài chính, nó được hiểu rất rõ.

### 3. Ví dụ 24.1 — người cá cược thể thao (Example 24.1, trang 319)

Một người cá cược thể thao có một mô hình cho phép chọn các trận với lợi thế 3%: các vụ cược của anh ta (đã tính phí nhà cái, "juice") thắng 51,5% và thua 48,5%, và được trả ngang (even money). Anh ta có bankroll ban đầu $5.000 và được cược số tiền bất kỳ. Cược bao nhiêu để bankroll tăng nhanh nhất?

Ta tối đa hoá kỳ vọng của hàm hữu dụng Kelly. Nếu cược x đô la, có hai kết quả: 51,5% thời gian bankroll thành 5.000 + x; 48,5% thời gian thành 5.000 − x.

$$\langle U(x)\rangle = 0{,}515\ln(5000 + x) + 0{,}485\ln(5000 - x).$$

Lấy đạo hàm bậc nhất và cho bằng 0:

$$\frac{0{,}515}{5000 + x} - \frac{0{,}485}{5000 - x} = 0.$$

Giải (người tổng hợp viết các bước): 0,515(5.000 − x) = 0,485(5.000 + x), tức 2.575 − 0,515x = 2.425 + 0,485x, nên 150 = x. Vậy **x = $150**.

Số tiền nên cược khi có lợi thế 3% đúng bằng 3% bankroll; điều này đúng với mọi vụ cược trả ngang (người tổng hợp chứng minh: với xác suất thắng p, ⟨U⟩ = p ln(B + x) + (1 − p) ln(B − x); đạo hàm bằng 0 cho x/B = p − (1 − p) = 2p − 1, chính là lợi thế). Nếu thắng vụ cược đầu, lần sau anh ta cược 3% của $5.150, tức $154,50; nếu thua, cược 3% của $4.850, tức $145,50, và cứ thế.

Bảng của người tổng hợp — tốc độ tăng trưởng ⟨ln(bankroll sau/bankroll trước)⟩ theo mức cược, bankroll $5.000:

| Mức cược | Tỷ lệ bankroll | Tốc độ tăng trưởng mỗi vụ cược |
|---:|---:|---:|
| $0 | 0% | 0 |
| $50 | 1% | 0,000250 |
| $150 (Kelly) | 3% | 0,000450 |
| $300 (gấp đôi Kelly) | 6% | ≈ 0 (−0,000001) |
| $450 (gấp ba Kelly) | 9% | −0,00136 |

Cược gấp đôi mức Kelly cho tăng trưởng dài hạn gần như bằng 0 dù mỗi vụ cược đều có kỳ vọng dương; cược nhiều hơn nữa làm bankroll co lại theo thời gian. Đây là lý do "cược quá tay" nguy hiểm dù có lợi thế.

Tác giả nói sách không phải giáo trình về cờ bạc nói chung nên giới thiệu nguồn khác cho chủ đề này. Ý then chốt muốn truyền đạt, sẽ dùng trong chương này, là **thay kỳ vọng đô la của bankroll bằng hàm hữu dụng ln x** khi ra cái có thể gọi là **quyết định ngoài ván bài** (metagame decisions): những quyết định không gắn với một ván hay một trò cụ thể, mà là chơi trò nào, mức cược nào, hay có chơi poker không.

### 4. Bốn nhận xét về cược Kelly; người chơi thường quá ngại rủi ro (trang 319–320)

Hàm hữu dụng logarit dẫn tới vài nhận xét chung về cược Kelly:

- **Rủi ro phá sản bằng 0**, nếu chia nhỏ bankroll vô hạn được. Lý do: thua thì lập tức giảm mức cược, thắng thì lập tức tăng mức cược; bankroll co lại theo tỷ lệ nhưng không bao giờ về 0.
- **Không áp dụng trực tiếp được cho poker**, vì không có vô số trò chơi ở mọi mức cược. Dù ta có thể muốn sòng bài (hay phòng online) mở các mức như $1,02-$2,04 hay $12,46-$24,92 để tối đa hoá tăng trưởng bankroll, điều đó khó xảy ra.
- **Tính logarit có vài hệ quả thú vị.** Chẳng hạn, gấp đôi bankroll có giá trị dương bằng đúng giá trị âm của việc mất một nửa bankroll (ln 2 và ln(1/2) = −ln 2). Khi bankroll nhỏ đi nhiều, mất thêm một phần của nó là thảm hoạ về hữu dụng, còn thắng những khoản lớn tuyệt đối từ một bankroll lớn lại tương đối ít giá trị.
- **Cược Kelly cho phép chịu rủi ro nhiều hơn đáng kể** so với mức người chơi quen theo mô hình rủi ro phá sản, vì chiến lược tự co giãn nhanh nên chống phá sản tốt hơn. Ngược lại, phần lớn người chơi không thích xuống lại mức thấp sau khi đã lên mức cao. Nếu người chơi sẵn sàng lên xuống mức cược mạnh tay theo dao động của bankroll, anh ta thực tế có thể chơi ở các mức khác nhau với bankroll ngắn hơn đáng kể so với bankroll cần để luôn chơi ở mức cao nhất.

Về điểm cuối, tác giả cho rằng người chơi điển hình thường ngại rủi ro hơn mức hợp lý khi "mở doanh nghiệp poker". Ví dụ, nhiều người chơi muốn chỉ có 5% khả năng mất vốn ban đầu, trong khi phần lớn doanh nhân sẽ vui mừng khôn xiết nếu biết mình chỉ có 5% khả năng thất bại. Mặt khác, khó mà gây dựng một doanh nghiệp poker rồi bán nó với giá lớn như nhiều doanh nhân làm. Nhưng ta nên đánh giá hợp lý khả năng phá sản so với phần thưởng có được khi không phá sản. Người chơi thận trọng thường dành quá nhiều thời gian ở mức thấp so với mức hoàn cảnh của họ cho phép, và bỏ lỡ nhiều lợi nhuận vì thế.

### 5. Chọn giữa hai trò chơi và bankroll tối ưu (trang 320–321)

Cược Kelly cho một khung đánh giá dựa trên rủi ro về hữu dụng của việc làm bankroll tăng; có thể áp khung này vào việc chọn giữa các trò chơi ở các mức cược khác nhau. Ta có số lựa chọn hữu hạn: sòng bài địa phương, dù là sòng thật hay phòng poker online, chỉ có một số mức cược và số bàn nhất định; hoặc không đủ người lấp các bàn trống ở mức ta muốn. Vì vậy ta thường phải chọn giữa hai trò chơi. Đôi khi quyết định hoàn toàn rõ: nếu một trò vừa có kỳ vọng cao hơn vừa có phương sai thấp hơn, chọn trò đó. Nhưng thường không như vậy, và ta phải chọn giữa một trò lợi nhuận cao, phương sai cao (tính bằng đô la tuyệt đối) và một trò lợi nhuận thấp, phương sai thấp.

Có thể dùng hữu dụng Kelly làm hướng dẫn, với giả định ta chưa chắc chơi trò nào và sẵn sàng lên xuống giữa hai trò. Khi đó ta xem mỗi trò tác động tới hàm hữu dụng ra sao và quyết định chơi trò nào ở mỗi mức bankroll.

**Bankroll tối ưu.** Trước đó, tác giả xét một góc khác của hữu dụng Kelly: **bankroll tối ưu**. Ở trên ta cố định bankroll và tìm mức cược tối ưu; giờ đảo lại: với một trò có mức cược cố định, tìm bankroll mà tại đó chơi trò này làm hữu dụng Kelly tăng nhiều nhất. Hữu dụng Kelly của việc chơi một trò có phân phối kết quả X là

$$\langle \ln(B + x)\rangle - \ln B,$$

với B là bankroll và x rút từ X. Nói cách khác, thay đổi hữu dụng Kelly do chơi trò này bằng kỳ vọng hữu dụng Kelly sau khi chơi trừ hữu dụng Kelly trước khi chơi.

**Ví dụ trò xúc xắc.** Quay lại trò đã xét ở Chương 22: tung xúc xắc, ra 3–6 thắng 1 đơn vị, ra 1–2 thua 1 đơn vị. Mức cược thực chất là 1 đơn vị. Với bankroll B, hữu dụng Kelly của việc chơi là

$$U(B) = \tfrac{1}{3}\ln(B - 1) + \tfrac{2}{3}\ln(B + 1) - \ln B.$$

Lấy đạo hàm theo B:

$$U'(B) = \frac{1}{3(B-1)} + \frac{2}{3(B+1)} - \frac{1}{B}.$$

Cho bằng 0 và nhân hai vế với 3B(B − 1)(B + 1):

$$0 = B(B+1) + 2(B-1)B - 3(B-1)(B+1) = B^2 + B + 2B^2 - 2B - 3B^2 + 3 = 3 - B,$$

nên **B = 3**. Với trò này, mức tăng hữu dụng Kelly từ việc chơi lớn nhất khi bankroll bằng 3 đơn vị.

Kiểm tra của người tổng hợp: U(2) ≈ 0,0393; U(2,5) ≈ 0,0540; U(3) ≈ 0,0566; U(3,5) ≈ 0,0554; U(4) ≈ 0,0529; U(10) ≈ 0,0284; còn U(1,5) ≈ −0,0257 (bankroll quá nhỏ thì chơi làm *giảm* hữu dụng Kelly). Kết quả B = 3 khớp với cược Kelly: lợi thế của trò là 2/3 − 1/3 = 1/3, nên cược 1 đơn vị là tối ưu khi bankroll là 3.

### 6. Dẫn công thức ngưỡng bankroll (24.1) (trang 321–322)

Với khái niệm bankroll tối ưu, mô hình giả định:

- Có hai trò cần so sánh, gọi là trò 1 và trò 2; trò 1 là trò lớn hơn.
- Biết tỷ lệ thắng μ₁, μ₂ và độ lệch chuẩn σ₁, σ₂ của hai trò; cả hai trò có tỷ lệ thắng dương và phương sai hữu hạn.
- Có bankroll B.

Rõ ràng, nếu buộc phải chơi một trong hai và có bankroll rất lớn, ta sẽ chơi trò lớn; nếu bankroll khá nhỏ, ta chơi trò nhỏ. Mô hình cho rằng có một ngưỡng bankroll c: trên c, chơi trò lớn làm hữu dụng Kelly tăng nhiều hơn; dưới c, trò nhỏ làm hữu dụng Kelly tăng nhiều hơn. Cần tìm c.

Với mỗi trò có một phân phối kết quả X. Thay đổi hữu dụng Kelly:

$$U = \langle\ln(B + x)\rangle - \ln B = \langle\ln B(1 + x/B)\rangle - \ln B = \langle\ln B\rangle + \langle\ln(1 + x/B)\rangle - \ln B.$$

⟨ln B⟩ là hằng số bằng ln B, nên U = ⟨ln(1 + x/B)⟩.

Dùng khai triển Taylor của ln(1 + t) (sách in nhầm mẫu là giai thừa, xem Lưu ý):

$$\ln(1 + t) = t - \frac{t^2}{2} + \frac{t^3}{3} - \frac{t^4}{4} + \dots$$

nên

$$\ln\!\left(1 + \frac{x}{B}\right) = \frac{x}{B} - \frac{x^2}{2B^2} + \frac{x^3}{3B^3} - \frac{x^4}{4B^4} + \dots$$

Nếu giả định B lớn hơn nhiều mọi kết quả x, có thể bỏ từ số hạng thứ ba trở đi, vì chúng có xⁿ ở tử nhưng nBⁿ ở mẫu nên tiến về 0 nhanh. Còn lại

$$U \approx \left\langle \frac{x}{B} - \frac{x^2}{2B^2}\right\rangle.$$

Với mọi phân phối, ⟨x⟩ = μ, và

$$\langle (x-\mu)^2\rangle = \sigma^2 \;\Rightarrow\; \langle x^2 - 2x\mu + \mu^2\rangle = \sigma^2 \;\Rightarrow\; \langle x^2\rangle - 2\langle x\rangle\mu + \mu^2 = \sigma^2 \;\Rightarrow\; \langle x^2\rangle - \mu^2 = \sigma^2 \;\Rightarrow\; \langle x^2\rangle = \mu^2 + \sigma^2.$$

Thay vào:

$$U \approx \frac{\mu}{B} - \frac{\mu^2 + \sigma^2}{2B^2}.$$

(Hệ quả người tổng hợp rút ra từ công thức này: U > 0 khi B > (μ² + σ²)/(2μ) — dưới mức đó, chơi trò này làm *giảm* hữu dụng Kelly; U lớn nhất khi B = (μ² + σ²)/μ, đúng bằng 3 cho trò xúc xắc với μ = 1/3 và ⟨x²⟩ = 1.)

Ngưỡng c là bankroll tại đó hữu dụng của trò 1 bằng của trò 2; trên giá trị này chơi trò 1, dưới thì chơi trò 2:

$$\frac{\mu_1}{c} - \frac{\mu_1^2 + \sigma_1^2}{2c^2} = \frac{\mu_2}{c} - \frac{\mu_2^2 + \sigma_2^2}{2c^2}.$$

Nhân hai vế với 2c²: 2cμ₁ − μ₁² − σ₁² = 2cμ₂ − μ₂² − σ₂². Chuyển vế: 2c(μ₁ − μ₂) = μ₁² − μ₂² + σ₁² − σ₂². Chia cho μ₁ − μ₂ và dùng μ₁² − μ₂² = (μ₁ − μ₂)(μ₁ + μ₂):

$$2c = \mu_1 + \mu_2 + \frac{\sigma_1^2 - \sigma_2^2}{\mu_1 - \mu_2}.$$

Vì trong poker μ₁ và μ₂ thường cực nhỏ so với phương sai, có thể rút gọn:

$$c \approx \frac{\sigma_1^2 - \sigma_2^2}{2(\mu_1 - \mu_2)} \qquad (24.1)$$

Đọc công thức (nhận xét của người tổng hợp): ngưỡng tỷ lệ thuận với phần phương sai *tăng thêm* khi lên trò lớn, và tỷ lệ nghịch với phần tỷ lệ thắng *tăng thêm*. Nếu trò lớn tăng tỷ lệ thắng ít mà tăng phương sai nhiều, cần bankroll rất lớn mới đáng lên.

### 7. Ví dụ 24.2 — $20-40 hay $40-80 hold'em (Example 24.2, trang 322–323)

Có hai trò đang cân nhắc ở một sòng bài: $20-40 hold'em, nơi ta có tỷ lệ thắng $35/giờ với độ lệch chuẩn $400/giờ; và $40-80 hold'em, tỷ lệ thắng $60/giờ, độ lệch chuẩn $800/giờ. Ngưỡng bankroll:

$$2c = 60 + 35 + \frac{800^2 - 400^2}{60 - 35} = 95 + \frac{640.000 - 160.000}{25} = 95 + 19.200 = 19.295.$$

Sách kết luận "c = $19.295"; đúng ra **c = 19.295/2 = $9.647,50** (xấp xỉ 24.1 cho 480.000/50 = $9.600). Nghĩa là với bankroll lớn hơn mức này nên chơi $40-80, nhỏ hơn thì nên chơi $20-40 xét về hữu dụng.

Bảng kiểm tra của người tổng hợp — hữu dụng Kelly mỗi giờ U ≈ μ/B − (μ² + σ²)/(2B²), nhân 100 để dễ đọc (tức tốc độ tăng trưởng logarit tính bằng phần trăm mỗi giờ):

| Bankroll B | $20-40 | $40-80 | Trò tốt hơn |
|---:|---:|---:|---|
| $5.000 | 0,378% | −0,087% | $20-40 |
| $9.647,50 | 0,276% | 0,276% | bằng nhau (ngưỡng) |
| $15.000 | 0,198% | 0,257% | $40-80 |
| $19.295 | 0,160% | 0,225% | $40-80 |
| $30.000 | 0,108% | 0,164% | $40-80 |

Ngoài ra (người tổng hợp tính): hữu dụng của $40-80 chỉ dương khi B > (60² + 800²)/120 ≈ $5.363, và lớn nhất ở B ≈ $10.727; của $20-40 dương khi B > ≈ $2.303, lớn nhất ở B ≈ $4.606. Với bankroll $5.000, chơi $40-80 thậm chí làm hữu dụng Kelly giảm.

Khung này cho phép so sánh hữu dụng đã điều chỉnh theo rủi ro của hai trò chơi khác nhau, để chọn trò chơi một cách định lượng. Giới hạn chính: công thức không đúng với phân phối có kết quả cỡ bankroll (khi đó bỏ các số hạng Taylor bậc cao không còn hợp lý). Điều này hay gặp nhất ở giải đấu, nhất là giải đông người, nơi giải thưởng cao nhất có thể vượt 500 buy-in. Tuy vậy, với mọi loại cash game, có thể định lượng giá trị đã điều chỉnh rủi ro của việc chơi hai trò bất kỳ bằng phương pháp này.

### 8. Các khái niệm then chốt (Key Concepts, trang 323)

- Khi ra quyết định thực tế, không thể chỉ dùng kỳ vọng làm hướng dẫn; phải xét hữu dụng. Có thể gán một hàm hữu dụng và đánh giá kết quả theo hữu dụng.
- Một hàm hữu dụng phổ biến, được nghiên cứu rất nhiều trong thị trường tài chính vì các tính chất đặc biệt trong lý thuyết danh mục, là tiêu chuẩn Kelly, U(x) = ln x.
- Thay tiêu chuẩn Kelly vào hai bộ điều kiện trò chơi khả dĩ, ta tìm được hữu dụng của việc chơi mỗi trò. Khi các trò có điều kiện phù hợp, có thể xác định một mức bankroll mà trên đó nên chơi trò lớn, dưới đó nên chơi trò nhỏ.

## Luận điểm cốt lõi

### Mệnh đề

Khi mục tiêu là tăng trưởng bankroll dài hạn, quyết định đúng là quyết định tối đa hoá kỳ vọng của logarit bankroll. Áp vào lựa chọn trò chơi, điều này cho một quy tắc lên/xuống mức cược theo ngưỡng bankroll c ≈ (σ₁² − σ₂²)/(2(μ₁ − μ₂)), và cho thấy người chơi sẵn sàng xuống mức thấp khi thua có thể chơi mức cao với bankroll nhỏ hơn mô hình rủi ro phá sản gợi ý.

### Giả định

- Mục tiêu duy nhất là tối đa hoá tốc độ tăng trưởng (hữu dụng ln); không xét tiêu dùng, mục tiêu ngắn hạn hay ngại sụt giảm.
- Tỷ lệ thắng và độ lệch chuẩn của mỗi trò đã biết chắc (bỏ qua bất định của Chương 23).
- Bankroll lớn so với kết quả mỗi đơn vị chơi (để khai triển Taylor bậc hai đúng).
- Người chơi sẵn sàng lên xuống mức cược theo bankroll và luôn có bàn để chơi.
- Ở Ví dụ 24.1, lợi thế 3% được biết chính xác.

### Cơ chế

1. Bankroll tăng theo tích các tỷ số; logarit biến tích thành tổng; tốc độ tăng trưởng dài hạn là ⟨ln r⟩.
2. Tối đa hoá ⟨ln(B + x)⟩ cân bằng giữa kỳ vọng (số hạng μ/B) và phương sai (số hạng −(μ² + σ²)/(2B²)): phương sai bị phạt nặng khi bankroll nhỏ, nhẹ khi bankroll lớn.
3. Vì phạt phương sai giảm theo 1/B² còn lợi ích kỳ vọng giảm theo 1/B, với bankroll đủ lớn trò có kỳ vọng cao hơn luôn thắng, với bankroll nhỏ trò có phương sai thấp hơn thắng; điểm chuyển là c.
4. Tự giảm cược khi thua làm rủi ro phá sản về 0 (nếu chia nhỏ được), nên chấp nhận được mức cược lớn hơn so với mô hình chơi một mức cố định.

### Bằng chứng và ví dụ tác giả đưa ra

- Hai ví dụ về hữu dụng: $20 hay $10; đồng xu $1.000.000 hay $500.000 chắc.
- Ví dụ 24.1: thắng 51,5% trả ngang, bankroll $5.000, cược tối ưu $150 (3%).
- Trò xúc xắc ±1 với 2/3 và 1/3: bankroll tối ưu 3.
- Ví dụ 24.2: $20-40 ($35/giờ, σ $400) và $40-80 ($60/giờ, σ $800): ngưỡng $19.295 theo sách ($9.647,50 khi tính đúng).
- So sánh với doanh nhân: 5% khả năng thất bại là rất tốt với một doanh nghiệp.

### Kết luận và hàm ý cho người chơi

- Không chọn mức cược theo kỳ vọng đô la cao nhất; chọn theo hữu dụng Kelly ứng với bankroll hiện tại.
- Lập quy tắc lên/xuống mức cược trước: lên trò lớn khi bankroll vượt c, xuống khi bankroll dưới c — và thực sự làm theo.
- Đừng quá thận trọng: ở mức thấp quá lâu cũng là một chi phí.
- Không dùng công thức này cho giải đấu đông người.

### Trong ngôn ngữ tài chính và lý thuyết quyết định

Hữu dụng ln là trường hợp riêng của hàm hữu dụng có hệ số ngại rủi ro tương đối không đổi bằng 1 (CRRA với γ = 1, theo hiểu biết của người tổng hợp). Xấp xỉ U ≈ μ/B − (μ² + σ²)/(2B²) là phiên bản "trung bình – phương sai" của Kelly: với tài sản tài chính có lợi nhuận kỳ vọng vượt trội μ và phương sai σ² (theo tỷ lệ), tỷ trọng Kelly là μ/σ², và tốc độ tăng trưởng xấp xỉ μ − σ²/2 — chính là "kéo lùi do biến động" (volatility drag) quen thuộc trong tài chính. Ngưỡng c là điểm mà hai "tài sản" (hai trò chơi) cho cùng tốc độ tăng trưởng logarit.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| Kelly criterion | tiêu chuẩn Kelly | tối đa hoá kỳ vọng ln(bankroll) |
| Kelly betting | cược theo Kelly | đặt cược theo tiêu chuẩn Kelly |
| utility | hữu dụng | mức ưa thích tiền đã điều chỉnh |
| utility function U(x) | hàm hữu dụng | ánh xạ bankroll sang hữu dụng |
| log utility | hữu dụng logarit | U(x) = ln x |
| concave downward | lõm | tăng chậm dần |
| certainty equivalent | giá trị chắc chắn tương đương | số tiền chắc chắn có cùng hữu dụng với vụ cược |
| growth rate | tốc độ tăng trưởng | ⟨ln(bankroll sau/trước)⟩ mỗi lần chơi |
| median | trung vị | giá trị giữa của phân phối |
| log-normal distribution | phân phối log-chuẩn | logarit của biến có phân phối chuẩn |
| portfolio theory | lý thuyết danh mục | lý thuyết phân bổ vốn giữa các tài sản |
| options trading | giao dịch quyền chọn | mua bán quyền chọn tài chính |
| sports betting | cá cược thể thao | đặt cược kết quả trận đấu |
| blackjack | blackjack | trò chơi bài sòng bạc có thể có lợi thế khi đếm bài |
| edge / advantage | lợi thế | kỳ vọng lãi trên mỗi đơn vị cược |
| even money | trả ngang | thắng bao nhiêu nhận bấy nhiêu |
| juice (vig) | phí nhà cái | phần nhà cái giữ lại |
| bookmaker | nhà cái | người nhận cược thể thao |
| metagame decisions | quyết định ngoài ván bài | chọn trò, chọn mức cược, có chơi hay không |
| game selection | chọn trò chơi | quyết định chơi bàn nào |
| optimal bankroll | bankroll tối ưu | bankroll làm hữu dụng Kelly của một trò lớn nhất |
| cutoff bankroll | ngưỡng bankroll | bankroll mà hai trò có hữu dụng Kelly bằng nhau |
| limit ($20-40, $40-80) | mức cược | small bet và big bet của limit |
| hold'em | hold'em | biến thể poker phổ biến nhất |
| cardroom | phòng bài | nơi tổ chức poker |
| move up / move down in limits | lên / xuống mức cược | đổi sang bàn lớn hơn / nhỏ hơn |
| risk-averse | ngại rủi ro | sẵn sàng đổi kỳ vọng lấy ít rủi ro hơn |
| Taylor series expansion | khai triển Taylor | viết hàm thành tổng luỹ thừa |
| derivative | đạo hàm | tốc độ thay đổi của hàm |
| buy-in | buy-in | phí tham gia giải |
| ring game | cash game | bàn chơi tiền mặt |

## Câu nói đáng nhớ

> "The utility of a million dollars is not twice that of a half-million." — mở đầu chương
>
> *Dịch: Hữu dụng của một triệu đô la không gấp đôi hữu dụng của nửa triệu.*
>
> Ý nghĩa: tiền có giá trị giảm dần, nên kỳ vọng đô la không đủ để ra quyết định.

> "We can maximize overall EV by simply betting the whole bankroll on any +EV bet. However, when we lose, we have less bankroll to grow from the next trial." — phần tiêu chuẩn Kelly
>
> *Dịch: Ta có thể tối đa hoá tổng kỳ vọng chỉ bằng cách đặt cả bankroll vào mọi vụ cược kỳ vọng dương. Nhưng khi thua, ta còn ít bankroll hơn để tăng ở lần sau.*
>
> Ý nghĩa: tối đa hoá kỳ vọng và tối đa hoá tăng trưởng là hai mục tiêu khác nhau.

> "So the amount that the bettor should bet on his 3% advantage is actually 3% of his bankroll; this is the case for all even-money bets." — Ví dụ 24.1
>
> *Dịch: Vậy số tiền người cá cược nên đặt với lợi thế 3% đúng bằng 3% bankroll; điều này đúng với mọi vụ cược trả ngang.*
>
> Ý nghĩa: quy tắc Kelly đơn giản nhất: tỷ lệ cược bằng lợi thế.

> "Doubling our bankroll is worth as much to the positive as losing half of our bankroll is worth to the negative." — nhận xét về cược Kelly
>
> *Dịch: Gấp đôi bankroll có giá trị dương bằng giá trị âm của việc mất một nửa bankroll.*
>
> Ý nghĩa: với hữu dụng logarit, thua 50% phải thắng 100% mới bù lại.

> "Most entrepreneurs, however, would be ecstatic to learn that they have just a 5% chance of failing." — nhận xét về mức ngại rủi ro
>
> *Dịch: Tuy nhiên, phần lớn doanh nhân sẽ vui mừng khôn xiết nếu biết mình chỉ có 5% khả năng thất bại.*
>
> Ý nghĩa: người chơi poker thường đặt chuẩn an toàn khắt khe hơn mức hợp lý.

> "Often cautious players spend far too much time playing at lower limits than is justified by their particular situation and forego large amounts of profit by doing so." — nhận xét về mức ngại rủi ro
>
> *Dịch: Người chơi thận trọng thường dành quá nhiều thời gian ở mức cược thấp so với mức hoàn cảnh của họ cho phép, và bỏ lỡ nhiều lợi nhuận vì thế.*
>
> Ý nghĩa: thận trọng quá mức cũng có chi phí.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương nối poker với một công cụ trung tâm của tài chính và cờ bạc chuyên nghiệp chỉ trong vài trang, và đưa ra một quy tắc thực hành rõ ràng (ngưỡng bankroll c) chỉ cần hai con số cho mỗi trò: tỷ lệ thắng và độ lệch chuẩn. Ý tưởng "bankroll tối ưu" — đảo bài toán Kelly từ chọn mức cược sang chọn mức bankroll phù hợp với một mức cược cố định — rất hợp với poker, nơi mức cược là rời rạc. Lời nhận xét rằng người chơi thường quá ngại rủi ro là một đối trọng tốt với hai chương rủi ro phá sản trước.

### Những chỗ đơn giản hoá

- **Lỗi số học ở Ví dụ 24.2 làm ngưỡng gấp đôi.** Với số đúng, người chơi nên lên $40-80 ở khoảng $9.650, tức khoảng 120 big bet của $40-80 — mạo hiểm hơn nhiều so với mức sách in, và cũng mạo hiểm hơn nhiều so với lời khuyên bankroll phổ biến thời đó (300 big bet). Người đọc nên biết rằng đây là ngưỡng *Kelly đầy đủ*.
- **Kelly đầy đủ rất biến động.** Theo hiểu biết của người tổng hợp, cược Kelly đầy đủ có khoảng 50% khả năng bankroll có lúc giảm còn một nửa, và người thực hành thường dùng "Kelly phân số" (nửa Kelly), đổi khoảng 25% tốc độ tăng trưởng lấy mức biến động giảm một nửa. Với ngưỡng c, nửa Kelly tương đương nhân ngưỡng lên khoảng 2 lần — trùng hợp gần với con số $19.295 mà sách in.
- **Tỷ lệ thắng biết chắc.** Như Chương 23 chỉ ra, tỷ lệ thắng ước lượng có sai số lớn và thường bị thổi phồng; cược theo Kelly với lợi thế bị thổi phồng là cược quá tay, và cược gấp đôi Kelly cho tăng trưởng gần bằng 0 (bảng ở mục 3). Đây là lý do mạnh để dùng Kelly phân số.
- **Tỷ lệ thắng ở mức cao hơn không độc lập với bankroll và tâm lý.** Khi lên mức cao, người chơi gặp đối thủ mạnh hơn và chịu áp lực tâm lý lớn hơn; mô hình coi μ₁ là cố định.
- **Xấp xỉ bậc hai.** Bỏ số hạng bậc ba bỏ qua độ lệch (skew) của phân phối kết quả; với no-limit có các ván cả stack, kết quả một giờ có thể chiếm phần đáng kể bankroll nhỏ.
- **Hữu dụng ln chỉ là một lựa chọn.** Người có thu nhập ngoài poker (bankroll ảo, Chương 23) hay cần tiêu dùng đều đặn có hữu dụng khác; tác giả thừa nhận khái niệm hữu dụng rộng hơn nhiều.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Poker online sau 2006 đưa vào rất nhiều mức cược, kể cả những mức rất nhỏ, và cho phép chơi nhiều bàn cùng lúc; điều này làm cho việc lên xuống mức cược theo bankroll (gần với Kelly) dễ thực hiện hơn nhiều so với ở sòng bài thật.
- Cộng đồng poker phổ biến các quy tắc "shot taking" (thử mức cao với một phần nhỏ bankroll rồi xuống ngay nếu thua) và "bankroll management" theo số buy-in; về bản chất đây là các phiên bản đơn giản hoá của tư duy Kelly trong chương.
- Trong tài chính, cược Kelly và Kelly phân số vẫn được bàn nhiều trong quản lý quỹ định lượng và cá cược thể thao chuyên nghiệp; phê phán quen thuộc là Kelly đầy đủ quá biến động với nhà đầu tư thông thường.

### Liên hệ các chương khác

- [C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md): khái niệm hữu dụng được nhắc lần đầu ở Phần I.
- [C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md): phương sai và đẳng thức ⟨x²⟩ = μ² + σ².
- [C22-rui-ro-pha-san.md](C22-rui-ro-pha-san.md): trò xúc xắc ±1 và mô hình rủi ro phá sản với mức cược cố định mà Kelly thay thế.
- [C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md): bất định của tỷ lệ thắng, chủ đề "xuống mức cược thấp hơn" được hứa ở đó.
- [C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md): dùng hữu dụng Kelly để kết hợp nhiều trò chơi thành danh mục và đánh giá thoả thuận tài trợ.
- [C26-giai-dau-phan-1-nhan-doi.md](C26-giai-dau-phan-1-nhan-doi.md): giải đấu — nơi công thức 24.1 không dùng được.

### Vận dụng

- **Người chơi poker:** ước lượng μ và σ mỗi giờ (hay mỗi 100 ván) ở hai mức cược đang cân nhắc, tính c = [μ₁ + μ₂ + (σ₁² − σ₂²)/(μ₁ − μ₂)]/2; dùng tỷ lệ thắng thận trọng (Chương 23) và cân nhắc nhân c lên 2 (nửa Kelly) cho an toàn. Đặt quy tắc xuống mức cược khi bankroll dưới c và tuân thủ.
- **Người làm tài chính và đầu tư:** Kelly cho tỷ trọng tối ưu của một tài sản rủi ro là khoảng μ/σ² (lợi nhuận vượt trội chia phương sai); ví dụ lợi nhuận vượt trội 5%/năm, độ biến động 20%/năm cho tỷ trọng 0,05/0,04 = 125%, nghĩa là Kelly đầy đủ đòi đòn bẩy — một lý do để dùng Kelly phân số. Bài học "cược gấp đôi Kelly cho tăng trưởng bằng 0" giải thích vì sao đòn bẩy quá mức phá huỷ lợi nhuận dài hạn dù mỗi khoản đầu tư đều có kỳ vọng dương. Cách so sánh hai trò chơi tương ứng với so sánh hai chiến lược theo tốc độ tăng trưởng logarit μ − σ²/2 thay vì theo lợi nhuận trung bình.
- **Người ra quyết định nói chung:** khi một quyết định lặp đi lặp lại và kết quả cộng dồn theo kiểu nhân (vốn kinh doanh, danh mục), hãy so các lựa chọn bằng tăng trưởng logarit; quy mô cam kết nên tăng giảm theo vốn hiện có.
