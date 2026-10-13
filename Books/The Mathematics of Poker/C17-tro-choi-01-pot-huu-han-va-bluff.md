# Chương 17 — Trộn bluff vào: các trò chơi [0,1] với pot hữu hạn (Mixing in Bluffs: Finite Pot [0,1] Games)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 17 "Mixing in Bluffs: Finite Pot [0,1] Games", trang 204–223.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương này thuộc Phần III "Chơi tối ưu" (Optimal Play). Chương 11 ([C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md)) đã giải trò chơi [0,1] half-street có pot hữu hạn (trò chơi số 2), đưa ra tỷ lệ α = 1/(P + 1) giữa vùng bluff và vùng value bet và quy tắc người bị bet phải call với 1 − α số tay. Chương 16 ([C16-tro-choi-01-khong-bo-bai.md](C16-tro-choi-01-khong-bo-bai.md)) giải các trò chơi [0,1] full-street không bỏ bài (số 4 tới số 8), nơi không có bluff và tỷ lệ raise là 1/2 hoặc r = √2 − 1. Chương 17 ghép hai mạch đó: giữ cấu trúc full-street của Chương 16 nhưng cho pot hữu hạn và cho phép bỏ bài, nên mỗi vùng value bet hay value raise đều có một vùng bluff tương ứng. Chương giải trò chơi số 9 (một bet), số 10 (hai bet, không check-raise), phác thảo số 11 (hai bet, có check-raise) và số 12 (raise không giới hạn, không check-raise). Chương 18 ([C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md)) nhìn lại toàn bộ họ trò chơi [0,1] và tính giá trị trò chơi; các chương 19–20 ([C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md), [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md)) đưa phân tích sang nhiều vòng cược.
**Ý chính:** **Khi pot hữu hạn và người chơi được bỏ bài, mọi vùng value (bet, raise, check-raise) phải đi kèm một vùng bluff có độ rộng bằng αₙ lần vùng value, với αₙ = 1/(P + 2n − 1); các vùng call và fold khi đó được suy ra từ các vùng value, nên toàn bộ trò chơi xoay quanh việc xác định các ngưỡng value.** Trò chơi số 9 (một bet): X value bet với [0, x₁], bluff với một vùng có độ rộng αx₁ ở cuối; Y bet sau khi X check với mọi tay X lẽ ra đã bet cộng một nửa số tay X sẽ check-call, bluff với vùng αy₁; mỗi người call với 1 − α tay có thể thắng bluff. Lời giải: y₁ = (1 − α)/(1 + α), x₁ = (1 − α)²/(1 + α), x₁* = y₁* = 1 − α, y₀ = 1 − αy₁, x₀ = 1 − αx₁; với pot 4 bet (α = 1/5): y₁ = 2/3, x₁ = 8/15, x₁* = y₁* = 4/5. Nguyên lý rút ra: nếu đối thủ có thể bet nhưng check, bạn không thể bị raise và đối thủ có thể call hoặc fold, hãy value bet mọi tay đối thủ lẽ ra đã value bet và một nửa số tay đối thủ sẽ call. Trò chơi số 10 (hai bet, không check-raise) đưa vào raise-bluff và ký hiệu mới yₙ*, yₙ#, α₂ = 1/(P + 3); Y raise với nửa số tay X sẽ call raise, X bet rồi fold trước raise với tỷ lệ α₂ số tay bet, Y raise-bluff với vùng α₂y₂ ngay dưới vùng call; chín phương trình bàng quan cho lời giải đóng (ví dụ x₁ = 2(1 − α)²(1 + 2α)²/[(1 + α)(7α² + 9α + 4)]) và công thức then chốt x₁ = (1 − α)²/[1 + α + (2 − α)(1 − α₂)R] với R = (1 − α₂)/2. Trò chơi số 11 cho thấy check-raise biến tỷ lệ y₂/x₁ thành tỷ lệ y₂/y₁, và y₁ = (1 − α)/[1 + α + (1 − α₂)R]. Trò chơi số 12 thay R bằng một hệ số R_P phụ thuộc kích thước pot, thoả hệ thức truy hồi R_P = [(P + 2)/(P + 3)] / [2 + R_{P+2}(P + 4)/(P + 5)] và tiến tới r = √2 − 1 khi pot tiến tới vô hạn.

> **Lưu ý:**
> - **Tham chiếu sai số ví dụ của Chương 11 (trang 204):** sách hai lần ghi "Example 11.2" cho trò chơi [0,1] pot hữu hạn đầu tiên và cho "[0,1] Game #2"; trò chơi số 2 thực ra là Ví dụ 11.3 (Ví dụ 11.2 là trò chơi số 1, không bỏ bài). Chính sách ở trang 206 và 213 ghi đúng "Game #2 (Example 11.3)".
> - **Ký hiệu in sai trong Ví dụ 17.1:** trang 204 viết ngưỡng call/fold mới của Y là "y₀*", nhưng mọi chỗ sau gọi là y₁*. Trang 205 ghi thứ tự "0 < x₁ < y₁ < x₁*, y₁* < y₀ < x₁ < 1"; ngưỡng cuối đúng là x₀. Trang 205 ghi tiêu đề bảng tại y₁* là "indifference between checking and betting"; đúng là giữa call và fold.
> - **Lỗi trong bảng tại x₀ của Ví dụ 17.1 (trang 207):** cột đầu ghi "X check-calls", đúng là "X check-folds"; dòng cuối ghi khoảng "[y₀, 1]", đúng là [x₀, 1]. Tổng (P + 1)y₁* − P đúng.
> - **Lỗi trong bảng tại x₁ của Ví dụ 17.1 (trang 207):** dòng [0, x₁] có hiệu 0 nhưng ghi tích "x₁", đúng là 0; dòng [y₀, 1] có hiệu −1 nhưng ghi tích "(1 − y₀)", đúng là −(1 − y₀). Tổng y₁* − y₁ − (1 − y₀) của sách đúng.
> - **Lỗi trong lời giải của Ví dụ 17.1 (trang 208):** sách ghi y₀ = (1 + α)²/(1 + α) (tức 1 + α, lớn hơn 1, vô lý). Đúng là y₀ = 1 − αy₁ = **(1 + α²)/(1 + α)**. Kiểm với P = 4: (1 + 1/25)/(6/5) = 13/15, khớp 1 − (1/5)(2/3) = 13/15.
> - **Lỗi chỉ số trong phần giải thích trực giác của Ví dụ 17.1 (trang 208):** sách viết X bet "thắng một bet khi bài Y nằm giữa y₂ và y₁*"; trò chơi một bet không có y₂, đúng là giữa y₁ và y₁* (chính câu sau của sách viết đúng "[y₁, y₁*]").
> - **Lỗi trong phần tính tay với pot 4 (trang 209):** (1) sách nói x₁* nằm ở 4/5 quãng đường "từ x₁ tới x₀" và x₀ là "1 − (1/5)x₁"; theo chính phương trình x₁* = (1 − α)(y₀ − x₁) + x₁, đúng là 4/5 quãng đường **từ x₁ tới y₀** (chỉ các tay tốt hơn y₀ mới thắng được bluff của Y), với y₀ = 1 − (1/5)y₁. Kiểm: 8/15 + (4/5)(13/15 − 8/15) = 8/15 + 4/15 = 4/5; còn 4/5 quãng từ x₁ = 8/15 tới x₀ = 67/75 cho 0,8213, không phải 0,8. (2) Sách định nghĩa c là khoảng cách từ x₁ tới x₀ rồi kết luận c = 1/3; thực tế x₀ − x₁ = 67/75 − 40/75 = 9/25 = 0,36, còn 1/3 là khoảng cách y₀ − x₁. (3) Sách dùng ký hiệu α cho khoảng cách a (từ x₁ tới y₁), trùng ký hiệu với α = 1/(P + 1); kết quả "α = 2/15" của phép tính này là a = y₁ − x₁ = 2/15, không phải α. (4) Dòng "1 = (4/5)b + (5/2)α" sai hệ số; đúng là 1 = (5/4)b + (5/2)a (tương đương b + 2a = 4/5, tức x₁* = 4/5), dòng sau "b = (4/5)(1 − (5/2)a) = 4/5 − 2a" của sách khớp với dạng đúng này. (5) Sách viết "With pot size 4, y₂ = 2/3"; đúng là y₁ = 2/3.
> - **Tham chiếu sai trò chơi tương ứng (trang 209, 211, 216, 221):** sách gọi trò chơi số 10 là "bản tương ứng của trò chơi số 6 (Ví dụ 16.3)"; trò chơi số 10 (hai bet, không check-raise) thực ra tương ứng với trò chơi số 5 (Ví dụ 16.2). Trang 211 viết "we parameterize [0,1] Game #6 this way", đúng là Game #10. Trang 216 viết R = (1 − α₂)/2 tiến tới 1/2 "là giá trị trong trò chơi số 6"; R = 1/2 là của trò chơi số 5 (trò chơi số 6 có R = r). Trang 221 viết "ngưỡng thấp nhất mà trò chơi này khác [0,1] Game #6", đúng là khác Game #10.
> - **Lỗi trong bảng tại x₂* của Ví dụ 17.2 (trang 215):** dòng [0, y₂] ghi "X bet-calls −1, X bet-folds −2"; hai giá trị bị đảo: bet rồi call trước value raise của Y mất 2 bet, bet rồi fold mất 1 bet. Phương trình y₂ = (P + 3)(y₂# − y₁*) của sách đúng với giá trị đã sửa. Câu ngay sau gọi vùng raise-bluff là "y₂* − y₁#"; đúng là y₂# − y₁*.
> - **Ký hiệu trong phép biến đổi tại y₂# (trang 214):** các dòng "2x₂* = (P + 1)(x₁ − x₂) + …" và "αx₂ = α₂(x₁ + 1 − x₀)" thiếu dấu sao, đúng là x₂*.
> - **Tham chiếu "y₁#" ở trang 216:** sách viết kết quả y₂# = 1 − α "tương tự phương trình cho y₁# trong trò chơi số 9"; trò chơi số 9 không có y₁#, đúng là y₁*.
> - **Lỗi trong bảng các ngưỡng của Ví dụ 17.2 (trang 217–218):** cột P = ε (pot gần 0) ghi y₀ = 0 và x₀ = 0. Theo chính công thức của sách, khi α → 1 thì y₀ → 1 và x₀ → 1 (không còn vùng bluff nào, vì không có pot để giành). Người tổng hợp kiểm bằng số: với P = 0,001, y₀ ≈ 0,9995 và x₀ ≈ 1,0000. Các cột P = 1, P = 2, P = 9, P = ∞ được người tổng hợp tính lại bằng phân số đúng và khớp toàn bộ (ví dụ P = 1: y₁ = 76/246 = 38/123; P = 2: y₁ = 279/630 = 31/70).
> - **Lỗi trong Ví dụ 17.3 (trang 218–219):** (1) sách nói Y "folds 1 − α₂ of his value bets to a raise"; đúng là Y fold với tỷ lệ **α₂** số tay value bet (và call với 1 − α₂), như chính kết quả y₂* = (1 − α₂)y₁ ngay sau đó. (2) Bảng "tại x₂#" có dòng [y₂*, y₁] ghi "X check-raise-bluffs −(P + 1)"; đúng là +(P + 1) (Y bet rồi fold trước check-raise, X giành pot P cộng bet của Y). Phương trình y₂* = (P + 2)(y₁ − y₂*) của sách chỉ đúng với dấu cộng. Người tổng hợp nhận xét thêm: bảng này so sánh check-call với check-raise-bluff, tức là phương trình bàng quan tại ranh giới giữa vùng check-call và vùng check-raise-bluff (x₁*), không phải tại x₂# (ranh giới giữa check-raise-bluff và check-fold). (3) Dòng "y₁* − y₁ = (P + 1) + (y₂# − y₁*) + (1 − y₀)" in nhầm dấu cộng; đúng là (P + 1)(y₂# − y₁*).
> - **Lỗi trong Ví dụ 17.4 (trang 221–222):** (1) sách viết "trò chơi không bỏ bài (Example 16.4) … y₂ was 1/2 and x₁ was 1/2. Hence, R was 1/2"; trò chơi không bỏ bài với hai bet và không check-raise là Ví dụ 16.2 (trò chơi số 5), trong đó **y₂ = 1/4** và x₁ = 1/2, nên R = 1/2. (2) Sách nói R_P tiến tới r khi P → ∞ "vì đây là xấp xỉ của trò chơi không bỏ bài ở Ví dụ 16.4"; trò chơi tương ứng là Ví dụ 16.3 (trò chơi số 6, raise không giới hạn, không check-raise). (3) Ký hiệu "x₃ = R_p+2y₂" trong lớp chữ nghĩa là x₃ = R_{P+2}·y₂.
> - **Kiểm chứng độc lập (người tổng hợp):** người tổng hợp viết chương trình tính kỳ vọng thật của từng hành động trên cây trò chơi hai bet (có và không có check-raise), rồi kiểm rằng lời giải của sách cho trò chơi số 10 thoả mọi phương trình bàng quan (sai số dưới 10⁻¹⁵), và giải số trò chơi số 11 để kiểm các khẳng định y₂ = y₁(1 − α₂)/2, y₂* = (1 − α₂)y₁, vùng check-raise-bluff rộng α₂x₂ và công thức 17.13; tất cả đều đúng. Các bảng số của trò chơi số 11 và số 12 trong bản tổng hợp là kết quả tính của người tổng hợp, sách không in.
> - **Hình 17.1 và 17.2 là sơ đồ minh hoạ:** sách không ghi P cho hai hình; vị trí các ngưỡng đọc từ trục chỉ là ước lượng và không khớp đúng với một giá trị P nào (Hình 17.1 gần với P = 2).
> - **Lớp chữ OCR:** "l" thay số 1, "a" thay α trong khung lời giải của trò chơi số 10, "15" là 1/5, "45" là 4/5, "23" là 2/3, "m" thay "in", "hi" thay "In", "+i" là +1. Mọi công thức đã được đọc lại từ ảnh trang.
> - **Quy ước:** P là kích thước pot tính bằng số bet; bet bằng 1 đơn vị; bài 0 là nuts. Các bảng kỳ vọng tính ex-showdown như Chương 16: chỉ ghi phần thay đổi so với kết quả showdown nếu không ai bet (ví dụ người đang thua showdown mà bluff thành công được +P; người đang thắng showdown mà bỏ bài mất −P). Số thập phân dùng dấu phẩy.

## Sơ đồ

### Phần mở đầu Chương 17 — từ không bỏ bài sang pot hữu hạn (trang 204)

```text
       Chương 16: luật không bỏ bài (xấp xỉ pot rất lớn) — không có
       bluff, các vùng bet chỉ gồm bài mạnh nhất để rút giá trị
                                │
                                ▼
       Bluff là thành phần then chốt của poker; đưa nó vào làm trò chơi
       phức tạp hơn nhưng gần poker thật hơn
                                │
                                ▼
       Chương 17: các trò chơi full-street với POT HỮU HẠN (P bet, bet
       bằng 1 đơn vị); thay đổi chính: mỗi vùng value bet và value raise
       có một VÙNG BLUFF tương ứng
```

### Ví dụ 17.1 — Trò chơi [0,1] số 9: một bet, pot P (Example 17.1 [0,1] Game #9, trang 204–209)

```text
       Luật: một vòng full-street; còn một bet; pot P, bet 1 đơn vị
                                │
                                ▼
       Sáu ngưỡng:
       · X: x₁ (value bet / check-call), x₁* (check-call / check-fold),
            x₀ (check-fold / bluff)
       · Y: y₁ (value bet / check khi X check), y₁* (call / fold khi X
            bet), y₀ (check / bluff khi X check)
       · thứ tự: 0 < x₁ < y₁ < x₁*, y₁* < y₀ < x₀ < 1 (vị trí tương đối
         của x₁* và y₁* không quan trọng vì không bao giờ cùng xuất hiện)
                                │
                                ▼
       Sáu phương trình bàng quan:
       · tại y₁:  y₁ = (x₁ + x₁*)/2      · tại y₁*: 1 − x₀ = αx₁
       · tại x₁*: 1 − y₀ = αy₁           · tại y₀:  x₁* = (1 − α)(y₀ − x₁) + x₁
       · tại x₀:  y₁* = 1 − α            · tại x₁:  y₁* − y₁ = 1 − y₀
       với α = 1/(P + 1)
                                │
                                ▼
       LỜI GIẢI: y₁ = (1 − α)/(1 + α)     x₁ = (1 − α)²/(1 + α)
                 x₁* = y₁* = 1 − α        y₀ = 1 − αy₁ = (1 + α²)/(1 + α)
                 x₀ = 1 − αx₁
       · pot 4 (α = 1/5): y₁ = 2/3, x₁ = 8/15, x₁* = y₁* = 4/5,
         y₀ = 13/15, x₀ = 67/75
                                │
                                ▼
       Giải thích trực giác (pot 4):
       · Y call 4/5 số tay để X bàng quan khi bluff (bluff mất 1 khi bị
         call, được 4 khi Y fold)
       · X bluff với 1/5 so với số tay value bet để Y bàng quan khi call
       · tại x₁: bet thắng thêm một bet khi Y call nhưng không tự bet
         ([y₁, y₁*]), check thắng thêm một bet nhờ dụ Y bluff ([y₀, 1]);
         hai vùng bằng nhau: 4/5 − y₁ = y₁/5, nên y₁ = 2/3
       · y₁ là trung điểm của x₁ và x₁*; x₁* nằm ở 1 − α quãng từ x₁ tới
         y₀ (X chỉ còn [x₁, x₀] để phòng thủ)
                                │
                                ▼
       NGUYÊN LÝ: đối thủ có thể bet nhưng check, bạn không thể bị
       raise, đối thủ có thể call hoặc fold → value bet mọi tay đối thủ
       lẽ ra đã value bet và MỘT NỬA số tay đối thủ sẽ call
```

### Ví dụ 17.2 — Trò chơi [0,1] số 10: hai bet, không check-raise, pot P (Example 17.2 [0,1] Game #10, trang 209–218)

```text
       Luật: một vòng; còn hai bet; không check-raise; pot P
                                │
                                ▼
       Nếu Y chỉ value raise mà không bao giờ raise bluff, X fold mọi
       tay kém hơn ngưỡng raise của Y → Y phải bảo vệ value raise bằng
       RAISE-BLUFF
       · raise-bluff lấy từ đâu? Không phải từ tay tệ nhất: lấy từ các
         tay MẠNH NHẤT trong nhóm không đủ để call (ngay dưới vùng call),
         vì các tay đó cũng không thắng được showdown
                                │
                                ▼
       Ký hiệu mới:
       · yₙ*: ngưỡng giữa call bet thứ n và (nếu được) raise-bluff bet
         thứ n + 1, hoặc fold
       · yₙ#: ngưỡng giữa vùng bỏ bet thứ n như bluff và vùng fold trước
         bet thứ n − 1
       · αₙ = 1/(P + 2n − 1)  (17.1);  α₁ = α = 1/(P + 1), α₂ = 1/(P + 3)
                                │
                                ▼
       Chiến lược (thứ tự 0, y₂, x₂*, x₁, y₁, x₁*, y₁*, y₂#, y₀, x₀, 1):
       · X: bet-call [0, x₂*]; bet-fold [x₂*, x₁]; check-call [x₁, x₁*];
            check-fold [x₁*, x₀]; bluff [x₀, 1]
       · Y khi X bet: raise [0, y₂]; call [y₂, y₁*]; raise-bluff
            [y₁*, y₂#]; fold [y₂#, 1]
       · Y khi X check: bet [0, y₁]; check [y₁, y₀]; bluff [y₀, 1]
                                │
                                ▼
       Chín phương trình (17.2)–(17.10), trong đó mới là:
       · y₂ = x₂*/2: Y raise với nửa số tay X sẽ call raise
       · x₂* = (1 − α₂)x₁: X bet rồi fold với tỷ lệ α₂ số tay bet
       · y₂# − y₁* = α₂y₂: vùng raise-bluff bằng α₂ lần vùng value raise
       · y₂# = 1 − α: tổng số tay Y fold trước bet của X là α
       · y₁* − y₁ = (P + 1)(y₂# − y₁*) + (1 − y₀)
                                │
                                ▼
       Gộp: y₂ = R·x₁ với R = (1 − α₂)/2  (17.11)
       Công thức then chốt cho mọi trò chơi không check-raise:
       x₁ = (1 − α)² / [1 + α + (2 − α)(1 − α₂)R]   (17.12)
                                │
                                ▼
       Lời giải đóng và bảng số cho P = ∞, 1, 2, 9, ε
       · P = ∞: trở về trò chơi số 5 (x₁ = 1/2, y₁ = 3/4, y₂ = 1/4)
       · P → 0: không ai bet, không ai bluff
```

### Ví dụ 17.3 — Trò chơi [0,1] số 11: hai bet, có check-raise, pot P (Example 17.3 [0,1] Game #11, trang 218–220)

```text
       Luật: như trò chơi số 10 nhưng X được check-raise
       · thêm vùng check-raise bluff của X (giữa x₁* và x₂#), rộng
         α₂ lần vùng value check-raise [0, x₂]
       · vùng value bet của Y khi X check tách thành bet-call [0, y₂*] và
         bet-fold [y₂*, y₁]; Y fold với tỷ lệ α₂ số tay value bet
                                │
                                ▼
       Thay đổi định tính (như trò chơi số 7 so với số 5):
       · Y bet chặt hơn sau khi X check (sợ bị check-raise)
       · X bet rộng hơn (bù giá trị mất do không dụ được tay yếu bet)
       · Y raise rộng hơn (vì X bet rộng hơn)
                                │
                                ▼
       Bàng quan tại x₂ (check-raise hay bet rồi call) kết hợp
       y₂* = (1 − α₂)y₁, y₂# − y₁* = α₂y₂ và phương trình tại x₁:
       → y₂ = y₁(1 − α₂)/2
       · không check-raise: (1 − α₂)/2 là tỷ lệ y₂/x₁
       · có check-raise: (1 − α₂)/2 là tỷ lệ y₂/y₁
       · cùng mẫu với Chương 16: không check-raise thì r nối các ngưỡng
         X–Y xen kẽ; có check-raise thì r nối các ngưỡng Y liên tiếp
                                │
                                ▼
       y₁ = (1 − α) / [1 + α + (1 − α₂)R]   (17.13)
```

### Ví dụ 17.4 — Trò chơi [0,1] số 12: raise không giới hạn, không check-raise, pot P (Example 17.4 [0,1] Game #12, trang 220–222)

```text
       Luật: một vòng; không check-raise; bet và raise không giới hạn;
       được bỏ bài
       · hầu hết phương trình giống trò chơi số 10; chỉ phương trình tại
         y₂ thay đổi vì X có thể reraise
       · mọi vùng bluff thứ n có độ rộng αₙ lần vùng value tương ứng:
         αₙyₙ = yₙ# − yₙ₋₁*
                                │
                                ▼
       Công thức 17.12 vẫn đúng, chỉ cần R mới:
       · kiểm: P → ∞, R = 1/2 cho x₁ = 1/2 (trò chơi số 5)
       · kiểm: một bet, R = 0 cho x₁ = (1 − α)²/(1 + α) (trò chơi số 9)
                                │
                                ▼
       Phương trình mới:
       · x₃# − x₂* = α₃x₃ (vùng reraise-bluff);  x₃# = (1 − α₂)x₁
       · tại y₂: x₂* − y₂ = y₂ + (P + 3)α₃x₃
       → x₁(P + 2)/(P + 3) = 2y₂ + x₃(P + 4)/(P + 5)   (17.14)
                                │
                                ▼
       Hệ số phụ thuộc pot: y₂ = R_P·x₁, x₃ = R_{P+2}·y₂, y₄ = R_{P+4}·x₃
       R_P = [(P + 2)/(P + 3)] / [2 + R_{P+2}(P + 4)/(P + 5)]
       · R_P → r = √2 − 1 khi P → ∞; truy hồi ngược hội tụ rất nhanh
       · có R_P thì tính x₁ bằng 17.12, nhân dần để được các ngưỡng
         value, rồi suy ra các vùng bluff, call
```

### Khái niệm then chốt cuối chương (Key Concepts, trang 222–223)

```text
       1. Trò chơi [0,1] mở rộng được cho check-raise, số bet tuỳ ý, …
       2. Chìa khoá luôn là các ngưỡng VALUE; mỗi vùng value có vùng
          bluff, call, fold, raise-bluff tương ứng, tính được từ tỷ lệ
          giữa kích thước pot và vùng value
       3. Không check-raise: hệ thức truy hồi nối các ngưỡng X và Y xen
          kẽ x₁ → y₂ → x₃ → …
       4. Có check-raise: hệ thức truy hồi tương tự nối các ngưỡng Y
          liên tiếp
       5. Đối thủ có thể bet nhưng check, bạn không thể bị raise, đối thủ
          có thể call hoặc fold: value bet mọi tay đối thủ lẽ ra đã value
          bet và một nửa số tay đối thủ sẽ call
```

## Ba câu hỏi chương này trả lời

1. **Khi đối thủ có thể bỏ bài, nên bluff bao nhiêu và call bao nhiêu?** Mỗi vùng value phải có một vùng bluff rộng bằng αₙ lần vùng value, với αₙ = 1/(P + 2n − 1): với bet đầu tiên α = 1/(P + 1), với raise α₂ = 1/(P + 3) (raise-bluff tốn hai bet nhưng pot đã lớn hơn). Người bị bet phải tiếp tục (call hoặc raise) với 1 − α số tay có thể thắng bluff; ví dụ với pot 4 bet, Y call 4/5 số tay và X bluff với 1/5 so với số tay value bet (x₁ = 8/15, vùng bluff rộng 8/75). Trong trò chơi hai bet, X bet rồi fold trước raise với tỷ lệ α₂ số tay đã bet, và Y raise-bluff với vùng α₂y₂.
2. **Nên value bet với bao nhiêu tay khi đối thủ đã check?** Với mọi tay đối thủ lẽ ra đã value bet, cộng một nửa số tay đối thủ sẽ call (nguyên lý của trò chơi số 9). Trong trò chơi không bỏ bài, đối thủ luôn call nên đây trở thành "một nửa số tay đối thủ còn có thể cầm". Với pot 4, y₁ = 2/3 là trung điểm của x₁ = 8/15 và x₁* = 4/5. Khi có thêm bet thứ hai, X bet chặt hơn: x₁ = (1 − α)²/[1 + α + (2 − α)(1 − α₂)R] với R = (1 − α₂)/2.
3. **Raise và check-raise thay đổi cấu trúc thế nào, và tỷ lệ raise phụ thuộc pot ra sao?** Không có check-raise, Y raise với y₂ = R·x₁, R = (1 − α₂)/2 (tiến tới 1/2 khi pot vô hạn, như trò chơi số 5). Có check-raise, tỷ lệ đó nối y₂ với y₁ thay vì với x₁, và y₁ = (1 − α)/[1 + α + (1 − α₂)R]. Khi raise không giới hạn, tỷ lệ raise thành R_P phụ thuộc pot theo truy hồi R_P = [(P + 2)/(P + 3)] / [2 + R_{P+2}(P + 4)/(P + 5)], tăng từ khoảng 0,326 (P = 1) tới r ≈ 0,414 (pot vô hạn) theo tính toán của người tổng hợp.

## Khái niệm cần biết

- **Pot hữu hạn và α (alpha):** pot có P bet, bet bằng 1 đơn vị; α = 1/(P + 1) (Phương trình 11.1 của Chương 11) là tỷ lệ giữa vùng bluff và vùng value bet, đồng thời là tỷ lệ số tay người bị bet được phép fold. Ví dụ: P = 4 cho α = 1/5. Quan trọng vì mọi kích thước vùng bluff, vùng call trong chương đều tính từ α.
- **αₙ = 1/(P + 2n − 1) (Phương trình 17.1):** bản tổng quát của α cho bet thứ n. Ví dụ: P = 4 cho α₁ = 1/5, α₂ = 1/7, α₃ = 1/9. Quan trọng vì bluff bet thứ n tốn n bet nhưng pot đã chứa thêm các bet trước, nên tỷ lệ khác nhau.
- **Bluff và vùng bluff:** bet với bài yếu để đối thủ bỏ bài tốt hơn. Ví dụ: trong trò chơi số 9 với pot 4, X bluff với [67/75; 1], rộng 8/75 bằng 1/5 vùng value bet 8/15. Quan trọng vì bluff khiến đối thủ phải call với một số tay trung bình, nhờ đó value bet có giá trị.
- **Ngưỡng có dấu sao xₙ*, yₙ*:** ngưỡng giữa call và fold (trò chơi một bet); từ trò chơi số 10, yₙ* là ngưỡng giữa call bet thứ n và raise-bluff bet thứ n + 1 (nếu được) hoặc fold. Ví dụ: y₁* = 1 − α = 4/5 với pot 4. Quan trọng vì đây là ngưỡng phòng thủ trước bluff.
- **Ngưỡng có dấu thăng yₙ#:** ngưỡng giữa vùng bỏ bet thứ n như một bluff và vùng fold trước bet thứ n − 1. Ví dụ: trong trò chơi số 10, Y raise-bluff trên [y₁*, y₂#] và fold trên [y₂#, 1], với y₂# = 1 − α. Quan trọng vì nó cho biết vùng raise-bluff kết thúc ở đâu.
- **Ngưỡng y₀, x₀:** ngưỡng giữa check (hoặc check-fold) và bluff. Ví dụ: y₀ = 1 − αy₁ = 13/15 với pot 4. Quan trọng vì 1 − y₀ là độ rộng vùng bluff của Y.
- **Raise-bluff (raise như một bluff):** raise với bài không đủ mạnh để call, mong đối thủ bỏ bài. Ví dụ: Y raise-bluff trên vùng α₂y₂ ngay dưới vùng call. Quan trọng vì không có nó, X sẽ fold mọi tay kém hơn ngưỡng raise của Y và vô hiệu hoá value raise.
- **Check-raise bluff:** check rồi raise như một bluff khi đối thủ bet. Ví dụ: trong trò chơi số 11, X có vùng check-raise bluff rộng α₂x₂ ngay dưới vùng check-call. Quan trọng vì nó bảo vệ vùng value check-raise.
- **Bet-call, bet-fold, check-call, check-fold:** chiến lược đầy đủ của X khi có hai bet phải ghi cả phản ứng với raise. Ví dụ: X bet-call trên [0, x₂*], bet-fold trên [x₂*, x₁]. Quan trọng vì phương trình bàng quan so sánh các chiến lược đầy đủ, không chỉ "bet" hay "check".
- **Phương trình bàng quan với pot hữu hạn:** như Chương 16 nhưng kết quả mỗi dòng có thể là ±P hoặc ±(P + 1) khi có người bỏ bài. Ví dụ: tại y₁*, Y call so với fold: −1 khi X value bet (độ dài x₁), +(P + 1) khi X bluff (độ dài 1 − x₀), cho (P + 1)(1 − x₀) = x₁. Quan trọng vì mỗi ngưỡng cho một phương trình tuyến tính.
- **Tỷ lệ raise R và R_P:** tỷ lệ y₂/x₁ giữa vùng raise của Y và vùng bet của X. Ví dụ: trong trò chơi số 10, R = (1 − α₂)/2 = 3/7 với P = 4; trong trò chơi số 12, R_P ≈ 0,367 với P = 4 (người tổng hợp tính). Quan trọng vì một khi biết R, công thức 17.12 cho ngay x₁.
- **Lời giải đóng (closed-form solution):** công thức biểu diễn mọi ngưỡng theo α. Ví dụ: y₂ = (1 − α)²(1 + 2α)/(7α² + 9α + 4) trong trò chơi số 10. Quan trọng vì tác giả nhấn mạnh phương pháp quan trọng hơn bản thân công thức.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 204)

Với các trò chơi của Chương 16, tác giả đặt một luật đặc biệt không thường áp dụng trong poker: không ai được bỏ bài. Trong thực tế, đôi khi gặp tình huống tương tự khi pot rất lớn. Một đặc điểm quan trọng của các trò chơi đó là không có bluff: vùng bet của cả hai người chỉ gồm các tay mạnh nhất và chỉ nhằm rút giá trị từ các tay đó.

Tuy nhiên, bluff là thành phần then chốt của poker; đưa nó vào làm trò chơi phức tạp hơn nhiều, nhưng cho xấp xỉ tốt hơn và hiểu biết sâu hơn về poker thật. Chương này xét các trò chơi full-street với pot hữu hạn; thay đổi chính so với các trò chơi không bỏ bài là đưa vào các **vùng bluff tương ứng với các vùng value bet và value raise**.

Quy ước: pot có P bet; mỗi bet bằng 1 đơn vị; α = 1/(P + 1).

### 2. Ví dụ 17.1 — Trò chơi [0,1] số 9: một bet (Example 17.1 [0,1] Game #9, trang 204–209)

**Luật.** Một vòng full-street; còn một bet; pot P, bet 1 đơn vị.

**Ký hiệu.** Khi giải trò chơi [0,1] pot hữu hạn đầu tiên ở Chương 11 (trò chơi số 2), ngoài ký hiệu yₙ, tác giả đã dùng y₀ cho ngưỡng giữa check và bluff, và x₁* cho ngưỡng giữa check-call và check-fold của X. Giống như Y bluff với các tay tệ nhất và value bet với các tay tốt nhất, X cũng sẽ bluff với tay tệ nhất và value bet với tay tốt nhất. Trong trò chơi full-street, X có thêm hành động bet (ngưỡng x₁) và bluff (ngưỡng x₀); Y có thêm ngưỡng giữa call và fold khi X bet (y₁*). Y call với tay yếu hơn tay mình fold là bị trội; Y chỉ cần call với tay mạnh hơn và fold tay yếu hơn.

Chiến lược của X gồm ba ngưỡng: x₀ giữa check-fold và bluff; x₁* giữa check-fold và check-call; x₁ giữa value bet và check-call. Chiến lược của Y cũng gồm ba ngưỡng: y₀ giữa check và bluff khi X check; y₁* giữa call và fold khi X bet; y₁ giữa value bet và check khi X check.

**Thứ tự ngưỡng.** Từ các trò chơi trước, có thể dự đoán Y bet sau khi X check với nhiều tay hơn số tay X đã bet: y₁ > x₁. Tỷ lệ α giữa bluff và value bet của trò chơi này sẽ giống trò chơi số 2 cho cả hai người; vì vùng bluff của X rộng αx₁ và của Y rộng αy₁, có thể đặt y₀ bên trái x₀. Ngưỡng call của mỗi người nằm đâu đó giữa vùng value bet và vùng bluff của đối thủ (để đối thủ bàng quan khi bluff): x₁ < y₁* < x₀ và y₁ < x₁* < y₀. Quan hệ giữa y₁* và x₁* không quan trọng, vì khi viết phương trình bàng quan ta chỉ dùng một trong hai. Tổng thể:

```text
0 < x₁ < y₁ < x₁*, y₁* < y₀ < x₀ < 1
```

**Hình 17.1 (cấu trúc chiến lược trò chơi số 9)**: cột X, từ dưới lên: BET [0, x₁] (khoảng 0,4), CHECK-CALL [x₁, x₁*] (tới khoảng 0,65), CHECK-FOLD [x₁*, x₀] (tới khoảng 0,91), BLUFF [x₀, 1]. Cột Y: BET [0, y₁] (khoảng 0,5), CALL [y₁, y₁*] (tới khoảng 0,65), FOLD [y₁*, y₀] (tới khoảng 0,88), BLUFF [y₀, 1]. Nhãn của cột Y gộp hai tình huống: "BET" và "BLUFF" là hành động khi X check, "CALL" và "FOLD" là phản ứng khi X bet (trên [0, y₁] Y cũng call). Các vị trí là ước lượng đọc từ trục.

Trong các bảng dưới đây, sách cố ý bỏ những khoảng mà hành động đang xét không thể xảy ra: ví dụ tại y₁, Y chọn giữa check và bet sau khi X check, nên bài X trong [0, x₁] và [x₀, 1] (X đã bet) bị bỏ qua.

*Y tại y₁ (check hay bet khi X check).* X check với [x₁, x₀].

| Bài của X | Y bet | Y check | Hiệu | Tích |
|---|---|---|---|---|
| [x₁, y₁] | −1 (X check-call, X thắng) | 0 | −1 | −(y₁ − x₁) |
| [y₁, x₁*] | +1 (X check-call, Y thắng) | 0 | +1 | x₁* − y₁ |
| [x₁*, x₀] | 0 (X fold, Y vốn thắng showdown) | 0 | 0 | 0 |
| **Tổng** | | | | **−2y₁ + x₁ + x₁*** |

Nên **y₁ = (x₁ + x₁*)/2**. Ý nghĩa trực giác: Y hiển nhiên bet mọi tay X lẽ ra đã value bet, và thêm một nửa số tay X sẽ check-call; y₁ là trung điểm của [x₁, x₁*].

*Y tại y₁* (call hay fold khi X bet).* X bet với [0, x₁] (value) và [x₀, 1] (bluff).

| Bài của X | Y call | Y fold | Hiệu | Tích |
|---|---|---|---|---|
| [0, x₁] | −1 | 0 | −1 | −x₁ |
| [x₀, 1] | +(P + 1) | 0 | +(P + 1) | (P + 1)(1 − x₀) |
| **Tổng** | | | | **(P + 1)(1 − x₀) − x₁** |

Nên (P + 1)(1 − x₀) = x₁, tức **1 − x₀ = αx₁**. Phương trình này nói vùng bluff (độ rộng 1 − x₀) bằng α lần vùng value bet (độ rộng x₁), với α = 1/(P + 1).

*X tại x₁* (check-call hay check-fold khi Y bet).* Y bet với [0, y₁] (value) và [y₀, 1] (bluff).

| Bài của Y | X check-call | X check-fold | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₁] | −1 | 0 | −1 | −y₁ |
| [y₀, 1] | P + 1 | 0 | +(P + 1) | (P + 1)(1 − y₀) |
| **Tổng** | | | | **(P + 1)(1 − y₀) − y₁** |

Nên **1 − y₀ = αy₁** (đây là Phương trình 11.4 của Chương 11).

*Y tại y₀ (check hay bluff khi X check).*

| Bài của X | Y bet (bluff) | Y check | Hiệu | Tích |
|---|---|---|---|---|
| [x₁, x₁*] | −1 (X call) | 0 | −1 | −(x₁* − x₁) |
| [x₁*, y₀] | +P (X fold, Y vốn thua showdown) | 0 | +P | P(y₀ − x₁*) |
| [y₀, x₀] | 0 (X fold, Y vốn thắng) | 0 | 0 | 0 |
| **Tổng** | | | | **−(x₁* − x₁) + P(y₀ − x₁*)** |

Biến đổi:

```text
x₁* − x₁ = P(y₀ − x₁*)
x₁* = α(P·y₀ + x₁)
x₁* = (1 − α)y₀ + αx₁ + (x₁ − x₁)        (vì αP = 1 − α)
x₁* = (1 − α)y₀ − (1 − α)x₁ + x₁
x₁* = (1 − α)(y₀ − x₁) + x₁
```

Ở trò chơi số 2 (Ví dụ 11.3), ta đã thấy rằng cũng như tỷ lệ bluff trên value bet là α, người bị bet call với 1 − α số tay có thể thắng bluff. Ở đây X đã bet với một số tay, nên các tay X check là [x₁, x₀], và trong số đó chỉ các tay tốt hơn y₀ mới thắng được bluff. Vậy x₁* bằng x₁ cộng (1 − α) lần độ rộng vùng tay của X có thể thắng bluff.

*X tại x₀ (check-fold hay bluff).* (Bảng đã sửa nhãn, xem khối Lưu ý.)

| Bài của Y | X check-fold | X bluff | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₁*] | 0 | −1 (Y call) | +1 | y₁* |
| [y₁*, x₀] | 0 | +P (Y fold, X vốn thua) | −P | −P(x₀ − y₁*) |
| [x₀, 1] | −P (Y bluff, X fold, X vốn thắng) | 0 (Y fold) | −P | −P(1 − x₀) |
| **Tổng** | | | | **(P + 1)y₁* − P** |

Nên y₁* = P/(P + 1), tức **y₁* = 1 − α**. Tình huống giống trước, chỉ khác là khi X bet, Y chưa thu hẹp phân phối bài của mình (khác với X, người đã check ở ngưỡng trước). Vì vậy Y call với 1 − α số tay của mình. Ở đây bỏ cụm "có thể thắng bluff" vì với X, lựa chọn là giữa check-fold và bluff; nếu check-fold, X vẫn thua các tay yếu nhất của Y vì Y sẽ bluff.

*X tại x₁ (check-call hay bet).*

| Bài của Y | X bet | X check-call | Hiệu | Tích |
|---|---|---|---|---|
| [0, x₁] | −1 | −1 | 0 | 0 |
| [x₁, y₁] | +1 | +1 | 0 | 0 |
| [y₁, y₁*] | +1 (Y call) | 0 (Y check) | +1 | y₁* − y₁ |
| [y₁*, y₀] | 0 (Y fold) | 0 (Y check) | 0 | 0 |
| [y₀, 1] | 0 (Y fold) | +1 (Y bluff, X call) | −1 | −(1 − y₀) |
| **Tổng** | | | | **y₁* − y₁ − (1 − y₀)** |

Nên **y₁* − y₁ = 1 − y₀**. Với một tay nằm ở ranh giới giữa bet và check, X có hai lựa chọn hợp lý: check thì dụ Y bluff và thắng một bet; bet thì thắng một bet từ các tay Y quá yếu để bet nhưng vẫn call. Vì vậy hai vùng này bằng nhau.

**Hệ sáu phương trình, sáu ẩn:**

```text
y₁ = (x₁* + x₁)/2
1 − x₀ = αx₁
1 − y₀ = αy₁
x₁* = (1 − α)(y₀ − x₁) + x₁
y₁* = 1 − α
y₁* − y₁ = 1 − y₀
```

**Lời giải** (đã sửa y₀, xem khối Lưu ý):

| Ngưỡng | Công thức | P = 1 (α = 1/2) | P = 2 (α = 1/3) | P = 4 (α = 1/5) | P = 9 (α = 1/10) |
|---|---|---|---|---|---|
| x₁ | (1 − α)²/(1 + α) | 1/6 ≈ 0,167 | 1/3 ≈ 0,333 | 8/15 ≈ 0,533 | 81/110 ≈ 0,736 |
| y₁ | (1 − α)/(1 + α) | 1/3 ≈ 0,333 | 1/2 | 2/3 ≈ 0,667 | 9/11 ≈ 0,818 |
| x₁* | 1 − α | 1/2 | 2/3 | 4/5 | 9/10 |
| y₁* | 1 − α | 1/2 | 2/3 | 4/5 | 9/10 |
| y₀ | 1 − αy₁ = (1 + α²)/(1 + α) | 5/6 ≈ 0,833 | 5/6 ≈ 0,833 | 13/15 ≈ 0,867 | 101/110 ≈ 0,918 |
| x₀ | 1 − αx₁ = 1 − α(1 − α)²/(1 + α) | 11/12 ≈ 0,917 | 8/9 ≈ 0,889 | 67/75 ≈ 0,893 | 1019/1100 ≈ 0,926 |

(Sách chỉ in công thức; các cột số do người tổng hợp tính. Kiểm sáu phương trình với P = 4: (8/15 + 4/5)/2 = 2/3; 1 − 67/75 = 8/75 = (1/5)(8/15); 1 − 13/15 = 2/15 = (1/5)(2/3); (4/5)(13/15 − 8/15) + 8/15 = 4/5; 4/5 − 2/3 = 2/15 = 1 − 13/15.) Nhận xét của người tổng hợp: x₁* = y₁* = 1 − α, tức hai người có cùng ngưỡng call, dù X chỉ phòng thủ trên khoảng [x₁, x₀].

**Giải thích trực giác với pot 4 bet** (α = 1/5, theo Phương trình 11.1). X value bet một phần số tay. Y call với số tay bằng vùng X bluff (hoà vốn trên phần đó), nhưng còn phải call thêm để X bàng quan khi bluff: khi X bluff và Y call, X mất một bet; khi Y fold, X được 4 bet. Để X bàng quan, Y phải call nhiều gấp bốn lần fold. Vì Y có cả đoạn [0, 1] để chọn, Y call với 4/5 tổng số tay, tức 1 − α.

Ngược lại, X cũng phải cân bằng value bet và bluff để Y không khai thác được bằng cách call nhiều hơn hay ít hơn. Ví dụ, nếu X không bao giờ bluff, Y chỉ cần call với ít tay hơn vùng X value bet và thắng giá trị từ mỗi tay đó. X muốn rút giá trị từ value bet, nên phải bluff để buộc Y call với một số tay nằm giữa vùng value bet và vùng bluff của X. X phải bluff đủ để Y bàng quan khi call với các tay giữa x₁ và x₀: với pot 4, X được 4 bet khi Y fold và mất một bet khi Y call; để Y bàng quan, X phải value bet nhiều gấp bốn lần bluff, tức bluff với 1/5 so với số tay value bet, hay αx₁. Cũng theo lập luận đó, các tay Y value bet sau khi X check phải được "đỡ" bởi một tỷ lệ bluff tương ứng trong vùng [y₀, 1].

Tiếp theo, X nên value bet bao nhiêu? Tại ngưỡng giữa bet và check-call, X có hai lựa chọn: bet thì thắng thêm một bet khi bài Y nằm giữa y₁ và y₁* (Y call với bài kém hơn nhưng sẽ không bet nếu được check); check thì thắng thêm một bet khi dụ được Y bluff, tức bài Y nằm giữa y₀ và 1. X bàng quan nên hai vùng [y₁, y₁*] và [y₀, 1] bằng nhau. Vùng thứ hai rộng αy₁, vùng thứ nhất rộng 1 − α − y₁, nên y₁ = (1 − α)/(1 + α). Với pot 4: y₁* = 4/5 và 1 − y₀ = (1/5)y₁, nên 4/5 − y₁ = (1/5)y₁, tức **y₁ = 2/3**.

Như vậy đã giải thích trực giác y₁, y₁*, y₀ và quan hệ giữa x₁ và 1 − x₀; x₁* và x₁ tốt nhất nên tìm đồng thời. Trong các trò chơi không bỏ bài, nguyên lý là khi X check, Y bet với một nửa số tay X check (nếu X không raise được). Trong trò chơi pot hữu hạn, khi Y cân nhắc check hay bet tại y₁, Y thắng một bet khi X nằm giữa y₁ và x₁* và thua một bet khi X nằm giữa x₁ và y₁; hai vùng phải bằng nhau nên y₁ là trung điểm của x₁ và x₁*. Phát biểu lại thành nguyên lý:

> **Nếu đối thủ có thể bet nhưng đã check, bạn không thể bị raise, và đối thủ có thể call hoặc fold, chiến lược đúng là value bet mọi tay đối thủ lẽ ra đã value bet và một nửa số tay đối thủ sẽ call.**

Nguyên lý này khớp với nguyên lý cũ: trong trường hợp không bỏ bài, đối thủ luôn phải call, nên value bet một nửa số tay là đúng; khi đối thủ có thể fold, ý tưởng là bet với một nửa số tay đối thủ sẽ call.

Ngoài ra, X phải chọn x₁* để phòng thủ trước bluff của Y như cách Y phòng thủ trước bluff của X. Nhưng X không có cả phân phối [0, 1] để phòng thủ, mà chỉ có tập con [x₁, x₀], vì X đã bet các tay ngoài khoảng này (bluff hoặc value bet). Sách viết rằng X phải call với 1 − α của khoảng [x₁, x₀], nên x₁* nằm ở 1 − α quãng đường từ x₁ tới x₀; theo phương trình bàng quan đã lập, đúng ra là 1 − α quãng đường **từ x₁ tới y₀**, vì chỉ các tay tốt hơn y₀ mới thắng được bluff (xem khối Lưu ý).

**Tính tay với pot 4 (sách, đã sửa).** Gọi b là khoảng từ 0 tới x₁ (tức x₁), a là khoảng từ x₁ tới y₁, c là khoảng từ x₁ tới y₀. Vì y₁ = 2/3 là trung điểm của x₁ và x₁* = 4/5:

```text
b = 2/3 − a                    (vì y₁ = b + a = 2/3)
b + 2a = 4/5                   (vì x₁* = b + 2a = 4/5; tương đương 1 = (5/4)b + (5/2)a)
b = 4/5 − 2a
4/5 − 2a = 2/3 − a   →   a = 2/15
b = 8/15
c = y₀ − x₁ = 13/15 − 8/15 = 1/3
```

Kết quả khớp với công thức (b = x₁ = 8/15). Tác giả nhấn mạnh hiểu trò chơi này là điều kiện để đi tiếp sang các trò chơi pot hữu hạn phức tạp hơn; nhiều điều được giải thích kỹ ở đây sẽ được coi là hiển nhiên về sau, nên người đọc nên tự đối chiếu cách các giải thích trực giác phản ánh đại số.

### 3. Ví dụ 17.2 — Trò chơi [0,1] số 10: hai bet, không check-raise (Example 17.2 [0,1] Game #10, trang 209–218)

**Luật.** Một vòng full-street; còn hai bet; không được check-raise; pot P, bet 1 đơn vị. Đây là bản pot hữu hạn của trò chơi số 5 ở Chương 16 (sách ghi nhầm là trò chơi số 6).

**Vì sao cần raise-bluff.** Xét Y sau khi X bet. Rõ ràng Y sẽ raise for value với vùng tay tốt nhất; call với một vùng yếu hơn để buộc X bluff đúng tỷ lệ; và fold với một vùng nữa vì không đủ giá trị để tiếp tục. Giả sử Y dùng chiến lược ba vùng như vậy. Sau khi Y value raise, X biết Y có tay mạnh nên có thể fold mọi tay kém hơn ngưỡng raise của Y để san bằng — giống như X sẽ bỏ các tay trung bình nếu chỉ còn một bet và Y không bao giờ bluff. Vậy Y không thể chỉ value raise với tay tốt nhất mà không bảo vệ các value raise đó bằng một kiểu **raise-bluff**.

**Raise-bluff lấy từ đâu?** Khi chỉ còn một bet, ta bluff với tay tệ nhất vì chúng có ít giá trị showdown nhất nếu ván được check tới cuối; chúng được lợi nhiều nhất khi chơi như bluff; khi đối thủ call bluff, ta không bao giờ nên thắng pot nếu đối thủ chơi tối ưu (hay chỉ cần hợp lý). Nhưng khi đối thủ đã bet, ta vẫn muốn raise với tay tốt nhất và call với nhóm tay tiếp theo để dùng giá trị showdown hiệu quả nhất. Theo nguyên tắc raise-bluff không bao giờ thắng pot khi bị call, raise-bluff phải lấy từ phần tay còn lại — không raise, không call. Trong phần đó, một số tay sẽ raise-bluff, theo tỷ lệ bảo vệ đúng các value raise so với kích thước pot và vùng value raise; phần còn lại fold.

Trực giác có thể gợi ý raise-bluff giống bluff một bet, tức dùng tay tệ nhất trong vùng. Điều này không đúng. Về kỹ thuật, với Y, raise-bluff có thể lấy từ bất cứ đâu trong nhóm tay kém hơn y₁* và vẫn ít nhất đồng tối ưu. Nhưng vì các tay không raise-bluff sẽ bị fold, và tay tốt hơn một bluff cũng không có hy vọng thắng showdown, dùng các **tay mạnh nhất** trong vùng (fold, raise-bluff) là chiến lược trội hơn mọi chiến lược khác.

**Ký hiệu mới.**

- yₙ* được định nghĩa lại là ngưỡng giữa call bet thứ n và, nếu bet thứ n + 1 và việc fold được phép, bỏ bet đó như một bluff; nếu không thì fold.
- yₙ# là ngưỡng giữa vùng bỏ bet thứ n như một bluff và vùng fold trước bet thứ n − 1.

Theo định nghĩa này, yₙ* đi cặp và liên hệ chặt với yₙ₊₁#. Khi tham số hoá, có thể có nhiều cây trò chơi tuỳ hành động trước, nên đôi khi một ngưỡng được vẽ trên hay dưới một ngưỡng khác dù không cần, vì hai ngưỡng không bao giờ cùng có ý nghĩa. Ví dụ x₁* chỉ có ý nghĩa nếu X check; nếu X check thì y₁* và y₂# không liên quan; nên x₁* nằm trên hay dưới y₁* là tuỳ ý khi tham số hoá (dù lời giải vẫn cho biết vị trí thật).

**Tham số hoá trò chơi số 10:** 0, y₂, x₂*, x₁, y₁, x₁*, y₁*, y₂#, y₀, x₀, 1.

**Hình 17.2 (cấu trúc chiến lược trò chơi số 10)** và chiến lược tương ứng:

- X: bet for value và call raise trên [0, x₂*]; bet for value và fold trước raise trên [x₂*, x₁]; check và call trên [x₁, x₁*]; check và fold trên [x₁*, x₀]; bluff (rồi fold nếu bị raise) trên [x₀, 1].
- Y nếu X bet: raise for value trên [0, y₂]; call trên [y₂, y₁*]; raise-bluff trên [y₁*, y₂#]; fold trên [y₂#, 1].
- Y nếu X check: bet for value trên [0, y₁]; check trên [y₁, y₀]; bluff trên [y₀, 1].

Hình ghi cho Y các nhãn kép (phản ứng khi X bet / hành động khi X check): RAISE dưới y₂ (khoảng 0,16), CALL/BET tới y₁ (khoảng 0,51), CALL/CHECK tới y₁* (khoảng 0,66), RAISE-BLUFF/CHECK tới y₂# (khoảng 0,79), FOLD/CHECK tới y₀ (khoảng 0,89), FOLD/BLUFF trên y₀; cho X: BET-CALL dưới x₂* (khoảng 0,31), BET-FOLD tới x₁ (khoảng 0,40), CHECK-CALL tới x₁* (khoảng 0,66), CHECK-FOLD tới x₀ (khoảng 0,92), BLUFF-FOLD trên x₀ (ước lượng đọc từ trục). Tác giả khuyên ôn kỹ ký hiệu này; về sau sẽ gặp những ngưỡng như x₄# — ngưỡng giữa "X check-raise rồi bỏ bet thứ tư như bluff" và "X fold trước bet thứ ba sau khi check-raise" — rất dễ lạc nếu không nắm vững.

**Tỷ lệ αₙ.** Với một bet, α = 1/(P + 1) chi phối quan hệ giữa bet, bluff và call. Với hai bet, pot đã lớn hơn và bluff tốn hai bet, nên tỷ lệ khác:

```text
α₂ = 1/(P + 3)
αₙ = 1/(P + (2n − 1))                    (17.1)
```

α của trò chơi số 2 (Ví dụ 11.3) nói chính xác là α₁; quy ước α không ghi chỉ số là α₁. Trò chơi có chín ẩn; mỗi ẩn cho một phương trình bàng quan.

*Y tại y₂ (call hay raise khi X bet).* X bet-call trên [0, x₂*], bet-fold trên [x₂*, x₁], bluff trên [x₀, 1].

| Bài của X | Y call | Y raise |
|---|---|---|
| [0, y₂] | −1 | −2 |
| [y₂, x₂*] | +1 | +2 |
| [x₂*, x₁] | +1 | +1 (X fold) |
| [x₀, 1] | +1 | +1 (X fold) |

Y mất thêm một bet khi raise các tay tốt nhất của X, và thắng thêm một bet khi raise các tay kém hơn y₂ mà X sẽ call. Vì X không raise lại được, ta lại thấy ý quen thuộc: Y raise với một nửa số tay X sẽ call: y₂ = x₂* − y₂, tức **y₂ = x₂*/2**.

*Y tại y₁ (bet hay check khi X check):* giống hệt trò chơi số 9, vì X không raise được: **y₁ = (x₁* + x₁)/2**. y₁ vẫn là trung điểm của ngưỡng bet và ngưỡng call của X.

*Y tại y₁* (call hay raise-bluff khi X bet).*

| Bài của X | Y call | Y raise-bluff |
|---|---|---|
| [0, x₂*] | −1 | −2 (X call raise) |
| [x₂*, x₁] | −1 | +(P + 1) (X fold) |
| [x₀, 1] | +1 | +1 (X fold) |

```text
x₂* = (P + 2)(x₁ − x₂*)
x₂* = x₁(P + 2)/(P + 3)
x₂* = (1 − α₂)x₁
```

Đây là lần đầu α₂ xuất hiện: X bet rồi fold trước raise với tỷ lệ α₂ số tay đã bet, để Y bàng quan khi raise-bluff. Dùng α₂ thay cho α vì pot đã lớn hơn — bet của X và raise của Y đều đã vào pot.

*Y tại y₂# (raise-bluff hay fold khi X bet).*

| Bài của X | Y raise-bluff | Y fold |
|---|---|---|
| [0, x₂*] | −2 | 0 |
| [x₂*, x₁] | +(P + 1) | 0 |
| [x₀, 1] | +1 (X fold) | −P (Y vốn thắng showdown) |

Biến đổi đại số:

```text
2x₂* = (P + 1)(x₁ − x₂*) + (P + 1)(1 − x₀)
2x₂* = (P + 1)(x₁ − x₂* + 1 − x₀)
(P + 3)x₂* = (P + 1)(x₁ + 1 − x₀)
α·x₂* = α₂(x₁ + 1 − x₀)                    (chia hai vế cho (P + 1)(P + 3))
α(1 − α₂)x₁ = α₂(x₁ + 1 − x₀)
(α/α₂ − α)x₁ = x₁ + 1 − x₀
```

Đồng nhất thức: α/α₂ = (1/(P + 1))/(1/(P + 3)) = (P + 3)/(P + 1) = 1 + 2α. Thế vào: (1 + α)x₁ = x₁ + 1 − x₀, tức **αx₁ = 1 − x₀**. Trước đó tác giả đã nói vùng raise-bluff của Y có thể nằm bất cứ đâu trong vùng fold; vì chỉ chơi chiến lược không bị trội nên ta có phương trình bàng quan giữa raise-bluff và fold; nếu giải theo một ngưỡng khác giữa call và fold thì phương trình trên xuất hiện trực tiếp, không cần biến đổi. Đây là phương trình quen thuộc (Phương trình 11.4: 1 − y₀ = αy₁ và các dạng tương tự) liên hệ vùng bet và vùng bluff của X qua hệ số α.

*Y tại y₀:* giống trò chơi số 9 vì X vẫn không check-raise được: **x₁* = (1 − α)(y₀ − x₁) + x₁**.

*X tại x₂* (bet rồi call hay bet rồi fold khi Y raise).* (Đã sửa dòng đầu, xem khối Lưu ý.)

| Bài của Y | X bet-call | X bet-fold |
|---|---|---|
| [0, y₂] | −2 | −1 |
| [y₁*, y₂#] | +2 | −(P + 1) |

Khi xét bàng quan giữa hai hành động, không đủ nói "X bet" hay "X check"; phải ghi cả chiến lược "X bet-call" hay "X bet-fold". x₂* là ngưỡng mới, giữa call raise và fold trước raise: X mất một bet khi call value raise của Y, nhưng bắt được raise-bluff của Y. Vì raise-bluff tốn của Y hai bet thay vì một, tỷ lệ call của X có dạng khác:

```text
y₂ = (P + 3)(y₂# − y₁*)
α₂y₂ = y₂# − y₁*
```

Đây là phương trình raise-bluff tương tự Phương trình 11.4 nhưng cho hai bet: độ rộng vùng raise-bluff y₂# − y₁* bằng vùng value raise y₂ nhân với tỷ lệ α₂. Đây là quy tắc chung xuyên suốt mọi trò chơi [0,1] pot hữu hạn: **mỗi vùng value có một vùng bluff tương ứng, với độ rộng bằng vùng value nhân một giá trị αₙ.**

*X tại x₁ (bet-fold hay check-call).*

| Bài của Y | X bet-fold | X check-call |
|---|---|---|
| [0, x₁] | −1 | −1 |
| [x₁, y₁] | +1 | +1 |
| [y₁, y₁*] | +1 (Y call) | 0 (Y check) |
| [y₁*, y₂#] | −(P + 1) (Y raise-bluff, X fold) | 0 |
| [y₂#, y₀] | 0 | 0 |
| [y₀, 1] | 0 | +1 (Y bluff, X call) |

```text
y₁* − y₁ = (P + 1)(y₂# − y₁*) + (1 − y₀)
```

Phương trình này liên hệ vùng Y call một bet nhưng sẽ không tự bet (y₁* − y₁) với vùng raise-bluff và vùng bluff của Y. Đây là lựa chọn của X giữa dụ bluff với một tay value bet ở ranh giới và cố rút giá trị: bet thì thắng một bet khi Y call mà lẽ ra không bet, nhưng mất P + 1 bet khi Y raise-bluff đẩy X ra khỏi pot; check thì đôi khi dụ được Y bluff.

*X tại x₁*:* như cũ, **1 − y₀ = αy₁**.

*X tại x₀ (check-fold hay bluff).*

| Bài của Y | X check-fold | X bluff |
|---|---|---|
| [0, y₂#] | 0 | −1 |
| [y₂#, x₀] | 0 | +P |
| [x₀, 1] | −P | 0 |

```text
y₂# = (x₀ − y₂#)P + (1 − x₀)P
(P + 1)y₂# = P
y₂# = 1 − α
```

Kết quả tương tự phương trình cho y₁* ở trò chơi số 9: tổng số tay Y fold trước bet của X là α. Ở trò chơi số 9 ta nói "Y call với 1 − α số tay"; cách nói chính xác hơn, theo kết quả này, là "Y fold α số tay trước một bet" (vì nay một phần không fold là raise-bluff, không phải call).

**Chín phương trình:**

```text
y₁ = (x₁* + x₁)/2                         (17.2)
y₂ = x₂*/2                                (17.3)
x₂* = (1 − α₂)x₁                          (17.4)
αx₁ = 1 − x₀                              (17.5)
x₁* = (1 − α)(y₀ − x₁) + x₁               (17.6)
α₂y₂ = y₂# − y₁*                          (17.7)
y₁* − y₁ = (P + 1)(y₂# − y₁*) + (1 − y₀)  (17.8)
1 − y₀ = αy₁                              (17.9)
y₂# = 1 − α                               (17.10)
```

Gộp (17.3) và (17.4) được quan hệ quan trọng:

```text
y₂ = x₁(1 − α₂)/2                          (17.11)
```

Như ở Chương 16, viết lại thành y₂ = R·x₁ với **R = (1 − α₂)/2**. Khi P tiến tới vô cùng, R tiến tới 1/2 — giá trị của trò chơi số 5 (sách ghi nhầm số 6).

**Rút gọn về hai ẩn.** Giải (17.2) và (17.6) theo x₁*, cho bằng nhau, được một phương trình chỉ chứa x₁ và y₁. Phương trình thứ hai lấy từ (17.8), chứa y₁*, y₁, y₂#, y₀: y₀ viết theo y₁ nhờ (17.9); y₂# là hằng số theo (17.10); y₁* viết theo y₂ nhờ (17.7), và y₂ = Rx₁, nên y₁* viết theo x₁. Người tổng hợp viết rõ hai phương trình:

```text
(A)  (1 + α)(2 − α)·y₁ = (1 − α) + (1 + α)x₁
(B)  1 − α = (1 + α)y₁ + (1 − α₂)R·x₁       (dùng (P + 2)α₂ = 1 − α₂)
```

Khử y₁:

```text
x₁ = (1 − α)² / [1 + α + (2 − α)(1 − α₂)R]        (17.12)
```

Phương trình này rất quan trọng cho các trò chơi không check-raise, vì nó đúng không chỉ cho trò chơi hai bet mà cho mọi trò chơi có thêm bet, được bỏ bài nhưng không check-raise: thêm bet chỉ đổi giá trị R, không đổi quan hệ cơ bản giữa các ngưỡng thấp. Có x₁ thì thế ngược để được y₁ và các ẩn còn lại từ (17.2)–(17.10).

**Lời giải** (α = 1/(P + 1); sách viết "a" trong khung lời giải):

```text
y₂  = (1 − α)²(1 + 2α) / (7α² + 9α + 4)
y₁  = (1 − α)(8α² + 9α + 3) / [(1 + α)(7α² + 9α + 4)]
y₁* = 1 − α − α₂(1 − α)²(1 + 2α) / (7α² + 9α + 4)
y₂# = 1 − α
y₀  = 1 − α(1 − α)(8α² + 9α + 3) / [(1 + α)(7α² + 9α + 4)]
x₂* = 2(1 − α)²(1 + 2α) / (7α² + 9α + 4)
x₁  = 2(1 − α)²(1 + 2α)² / [(1 + α)(7α² + 9α + 4)]
x₁* = 4(1 − α)(2α² + 2α + 1) / (7α² + 9α + 4)
x₀  = 1 − 2α(1 − α)²(1 + 2α)² / [(1 + α)(7α² + 9α + 4)]
```

Người tổng hợp đã giải lại hệ chín phương trình bằng phân số chính xác cho P = 1, 2, 4, 9 và xác nhận cả chín công thức; đồng thời kiểm trên mô hình cây trò chơi độc lập rằng lời giải thoả mọi điều kiện bàng quan. Tác giả thừa nhận lời giải cuối cùng này không hữu ích lắm; điều hữu ích là phương pháp và các nguyên lý dùng để tìm ra nó.

**Bảng ngưỡng theo kích thước pot** (cột P = ε là pot rất nhỏ, gần 0; sách in giá trị P = 9 dạng thập phân; các giá trị thập phân trong ngoặc do người tổng hợp thêm):

| Ngưỡng | P = ∞ | P = 1 | P = 2 | P = 9 | P = ε (≈ 0) |
|---|---|---|---|---|---|
| y₂ | 1/4 | 2/41 (0,049) | 2/21 (0,095) | 0,195573 | 0 |
| x₂* | 1/2 | 4/41 (0,098) | 4/21 (0,190) | 0,391147 | 0 |
| x₁ | 1/2 | 16/123 (0,130) | 5/21 (0,238) | 0,426706 | 0 |
| y₁ | 3/4 | 76/246 (0,309) | 279/630 (0,443) | 0,655204 | 0 |
| x₁* | 1 | 20/41 (0,488) | 68/105 (0,648) | 0,883702 | 0 |
| y₁* | 1 | 20/41 (0,488) | 68/105 (0,648) | 0,883702 | 0 |
| y₂# | 1 | 1/2 | 2/3 | 0,9 | 0 |
| y₀ | 1 | 208/246 (0,846) | 537/630 (0,852) | 0,934480 | **1** (sách in 0) |
| x₀ | 1 | 230/246 (0,935) | 58/63 (0,921) | 0,957329 | **1** (sách in 0) |

Khi pot tiến về 0, các ngưỡng tiến tới trạng thái "không ai bet" như dự đoán: không value bet (x₁, y₁ → 0) và không bluff (x₀, y₀ → 1). Khi pot vô hạn, các ngưỡng trở về trò chơi số 5 của Chương 16 (x₁ = 1/2, y₁ = 3/4, y₂ = 1/4) và mọi ngưỡng call/bluff bằng 1 (call mọi tay, không bluff). Nhận xét của người tổng hợp: x₁* = y₁* ở mọi cột, giống trò chơi số 9.

### 4. Ví dụ 17.3 — Trò chơi [0,1] số 11: hai bet, có check-raise (Example 17.3 [0,1] Game #11, trang 218–220)

**Luật.** Một vòng full-street; còn hai bet; được check-raise; pot P, bet 1 đơn vị.

Từ đây tác giả thường bỏ việc liệt kê toàn bộ lời giải và tính từng ngưỡng, vì như trò chơi số 10 cho thấy, lời giải các trò chơi pot hữu hạn phức tạp rất rối và khó nhìn ra ý nghĩa. Thay vào đó, tác giả dựa trên kết quả các trò chơi trước và chỉ ra chỗ khác biệt.

**Các ngưỡng bổ sung, phần lớn suy ra dễ dàng.** X có một vùng **check-raise bluff** giữa x₂# và x₁*; độ rộng vùng này bằng vùng value check-raise (x₂) nhân α₂. Tương tự, thay vì chỉ có một vùng value bet bên trái y₁, Y có vùng "bet-call" bên trái y₂* và vùng "bet-fold" giữa y₂* và y₁, với tỷ lệ sao cho Y fold α₂ số tay value bet trước check-raise (sách in nhầm "1 − α₂"), để X bàng quan khi check-raise bluff; và cứ thế.

**Điều quan trọng là sự thay đổi của các vùng value.** Thay đổi ở vùng value lan sang mọi ngưỡng khác và ảnh hưởng chiến lược cả hai người, nhưng quan hệ giữa các ngưỡng khác với vùng value khá đơn giản. Thay vì viết phương trình cho mọi ngưỡng, tác giả chỉ ra các ngưỡng quan trọng. Ta biết chiến lược value bet của Y sau khi X check bị ảnh hưởng bởi khả năng check-raise của X; chiến lược value raise của Y bị ảnh hưởng vì X check một số tay mạnh và có lẽ bet rộng hơn một chút so với khi không có check-raise. Đây đúng là các dịch chuyển chính trong trò chơi không bỏ bài (Chương 16, trò chơi số 7 so với số 5): Y bet chặt hơn sau khi X check (sợ check-raise), X bet rộng hơn (để lấy lại phần giá trị mất do không dụ được tay yếu bet), Y raise rộng hơn (vì X bet rộng hơn).

**Bàng quan tại x₂ (check-raise hay bet rồi call).**

| Bài của Y | X check-raise | X bet-call |
|---|---|---|
| [0, x₂] | −2 | −2 |
| [x₂, y₂] | +2 | +2 |
| [y₂, y₂*] | +2 (Y bet-call) | +1 (Y call) |
| [y₂*, y₁] | +1 (Y bet-fold) | +1 |
| [y₁, y₁*] | 0 (Y check) | +1 (Y call) |
| [y₁*, y₂#] | 0 (Y check) | +2 (Y raise-bluff, X call) |
| [y₀, 1] | +1 (Y bluff rồi fold) | 0 (Y fold) |

```text
y₂* − y₂ + (1 − y₀) = 2(y₂# − y₁*) + y₁* − y₁
```

**Tìm y₂*.** Sách xét bàng quan giữa check-call và check-raise-bluff của X (sách gọi là "tại x₂#"; xem khối Lưu ý):

| Bài của Y | X check-call | X check-raise-bluff |
|---|---|---|
| [0, y₂*] | −1 | −2 (Y call raise) |
| [y₂*, y₁] | −1 | +(P + 1) (Y fold) |
| [y₀, 1] | +1 | +1 |

```text
y₂* = (P + 2)(y₁ − y₂*)
y₂* = (1 − α₂)y₁
```

Ngoài ra y₂# − y₁* = α₂y₂ (như trò chơi số 10). Vậy:

```text
(1 − α₂)y₁ − y₂ + (1 − y₀) = 2α₂y₂ + y₁* − y₁
```

Trong trò chơi không check-raise, từ bàng quan tại x₁ ta có y₁* − y₁ = (P + 1)(y₂# − y₁*) + (1 − y₀). Phương trình này đến từ việc X phải bàng quan giữa bet-fold và check-call tại x₁: bet thì thắng một bet khi Y có tay sẽ call nhưng không tự bet; đổi lại mất P + 1 bet khi Y raise-bluff, và mất thêm các bluff không dụ được do đã bet. Thế vào, các số hạng bluff (1 − y₀) triệt tiêu:

```text
(1 − α₂)y₁ − y₂ = (P + 3)α₂y₂ = y₂
(1 − α₂)y₁ = 2y₂
y₂ = y₁(1 − α₂)/2
```

Trong trò chơi không check-raise, tỷ lệ (1 − α₂)/2 nối y₂ với x₁; ở đây nó nối y₂ với y₁. Tương tự, ở Chương 16, trò chơi raise không giới hạn không check-raise (Ví dụ 16.3) có r là tỷ lệ giữa các ngưỡng liên tiếp y₂, x₃, y₄, …; còn khi có check-raise, r là tỷ lệ giữa các ngưỡng yₙ liên tiếp. **Kết quả chung (cho các trường hợp đối xứng đơn giản): tỷ lệ giữa ngưỡng Y và ngưỡng X trong trò chơi không check-raise trở thành tỷ lệ giữa các ngưỡng Y liên tiếp trong trò chơi có check-raise.** Theo chuỗi lập luận này, phương trình tổng quát cho y₁ là:

```text
y₁ = (1 − α) / [1 + α + (1 − α₂)R]                 (17.13)
```

tương tự trực tiếp Phương trình 17.12 nhưng có yếu tố check-raise. Tính các ngưỡng còn lại là việc lập phương trình bàng quan và giải; vùng bluff liên hệ với vùng value qua một giá trị α.

**Bảng số của người tổng hợp.** Sách không in lời giải trò chơi số 11. Người tổng hợp giải số hệ mười hai phương trình bàng quan trên cây trò chơi đầy đủ (X: check-raise [0, x₂], bet-call [x₂, x₂*], bet-fold [x₂*, x₁], check-call [x₁, x₁*], check-raise bluff [x₁*, x₂#], check-fold [x₂#, x₀], bluff [x₀, 1]; Y khi X check: bet-call [0, y₂*], bet-fold [y₂*, y₁], check [y₁, y₀], bluff [y₀, 1]), xác nhận 17.13 với R = (1 − α₂)/2, và so với trò chơi số 10 cùng pot 4:

| Ngưỡng (P = 4) | Trò chơi số 10 (không check-raise) | Trò chơi số 11 (có check-raise) |
|---|---|---|
| x₂ (value check-raise) | — | 0,0848 |
| y₂ (Y raise) | 0,1474 | 0,2188 |
| x₁ (X bet) | 0,3439 | 0,3974 |
| y₁ (Y bet khi X check) | 0,5614 | 0,5104 |
| y₂* (Y bet-call) | — | 0,4375 |
| y₀ (Y bluff từ) | 0,8877 | 0,8979 |
| x₀ (X bluff từ) | 0,9312 | 0,9375 |

Cả ba dịch chuyển định tính đều xuất hiện: Y bet chặt hơn khi X check (0,561 xuống 0,510), X bet rộng hơn (0,344 lên 0,397), Y raise rộng hơn (0,147 lên 0,219). Kiểm 17.13: (1 − 1/5)/[1 + 1/5 + (6/7)(3/7)] = 0,8/1,5673 = 0,5104.

### 5. Ví dụ 17.4 — Trò chơi [0,1] số 12: raise không giới hạn, không check-raise (Example 17.4 [0,1] Game #12, trang 220–222)

**Luật.** Một vòng full-street; không check-raise; số bet và raise tuỳ ý; được bỏ bài.

Tác giả giải bằng cách liên hệ với các trò chơi đã giải. Hầu hết phương trình bàng quan giống hệt trò chơi số 10; thực ra phương trình duy nhất không còn đúng là tại y₂. Ở trò chơi số 10, bet thứ hai là bet cuối nên Y không thể bị raise lại, và Y raise với một nửa số tay X sẽ call; ở đây X có thể raise lại nên phải xét lại phương trình đó. Ngoài ra trò chơi có vô số ngưỡng, mỗi ngưỡng một phương trình bàng quan; nhiều phương trình có dạng rõ ràng, ví dụ với mọi n thích hợp:

```text
αₙ·yₙ = yₙ# − yₙ₋₁*
```

— tỷ lệ bluff trên value quen thuộc (dựa trên Phương trình 11.4 của Chương 11: 1 − y₀ = αy₁), với giá trị α tuỳ số bet bỏ vào pot.

**Công thức 17.12 vẫn đúng.** Ở trò chơi số 10 ta đã có dạng tổng quát của x₁ cho trò chơi không check-raise:

```text
(1 − α)² = x₁[1 + α + R(2 − α)(1 − α₂)]
```

Phương trình cần sửa là y₂ = R·x₁, nhưng nó không cần đổi dạng — chỉ R có giá trị mới. Kiểm bằng các trò chơi đã giải:

- Trò chơi không bỏ bài hai bet không check-raise (trò chơi số 5, Ví dụ 16.2; sách ghi nhầm Ví dụ 16.4): cho pot tiến tới vô cùng thì mọi α tiến về 0; ở đó y₂ = 1/4, x₁ = 1/2 (sách in nhầm y₂ = 1/2), nên R = 1/2. Thế vào công thức với α, α₂ → 0: x₁ = 1/(1 + 2·1/2) = 1/2, đúng.
- Trò chơi một bet: R = 0 vì y₂ ở 0; x₁ = (1 − α)²/(1 + α), đúng là lời giải trò chơi số 9.

**Các phương trình mới** (theo tác giả, trực giác với người đã theo tới đây):

```text
x₃# − x₂* = α₃x₃
```

Vùng bluff thứ n (ở đây là vùng X reraise-bluff, ngay dưới vùng X call raise) rộng αₙ lần vùng value tương ứng (vùng X value reraise [0, x₃]).

```text
x₃# = (1 − α₂)x₁
```

Khi bỏ bet thứ n for value, phải ít nhất call (hoặc raise) với 1 − αₙ₊₁ số tay đã bỏ bet đó, để không bị khai thác bằng raise-bluff.

**Bàng quan tại y₂** (ngưỡng thấp nhất mà trò chơi này khác trò chơi số 10; sách ghi nhầm số 6):

```text
x₂* − y₂ = y₂ + (P + 3)α₃x₃
```

Y thắng thêm một bet tại y₂ nhờ value raise khi X nằm giữa y₂ và x₂*. Y mất thêm một bet mỗi khi X tốt hơn y₂ (Y fold trước các raise tiếp theo), và mất P + 3 bet khi X nằm trong vùng reraise-bluff x₃# − x₂* (Y đã bỏ hai bet, fold và mất pot P mà lẽ ra thắng). Giải:

```text
(1 − α₂)x₁ − α₃x₃ = 2y₂ + (P + 3)α₃x₃        (vì x₂* = x₃# − α₃x₃)
x₁(P + 2)/(P + 3) = 2y₂ + x₃(P + 4)/(P + 5)   (17.14)
```

(vì 1 − α₂ = (P + 2)/(P + 3) và (P + 4)α₃ = (P + 4)/(P + 5).)

**Hệ số raise phụ thuộc pot.** Các phương trình bàng quan lặp lại y hệt khi tăng ngưỡng thêm hai bet, nên (17.14) là một trường hợp riêng của truy hồi tổng quát cho xₙ, yₙ₊₁, xₙ₊₂. Có thể dùng nguyên lý: từ raise thứ hai trở đi, trò chơi hoàn toàn đối xứng về tỷ lệ giữa các ngưỡng, chỉ khác kích thước pot. Giá trị các ngưỡng khác nhau vì đã nhân với một giá trị tương tự r = √2 − 1 (Phương trình 14.1); đến giờ ta gọi nó là R vì chỉ xét trò chơi có một raise; nhưng khi pot lớn dần, hệ số này cũng đổi. Gọi hệ số thay đổi theo pot là R_P:

```text
y₂ = R_P·x₁
x₃ = R_{P+2}·y₂
y₄ = R_{P+4}·x₃
…
```

Thế vào 17.14:

```text
x₁(P + 2)/(P + 3) = 2R_P·x₁ + R_P·R_{P+2}·x₁(P + 4)/(P + 5)
```

x₁ triệt tiêu:

```text
R_P = [(P + 2)/(P + 3)] / [2 + R_{P+2}(P + 4)/(P + 5)]
```

Đây là truy hồi tổng quát giữa các giá trị R_P liên tiếp. Để có giá trị cụ thể, dùng điều đã biết: R_P tiến tới r khi P tiến tới vô cùng (vì khi đó trò chơi xấp xỉ trò chơi không bỏ bài số 6, Ví dụ 16.3; sách ghi nhầm 16.4). Do đó có thể chọn n lớn tuỳ ý, đặt R tại pot P + 2n bằng √2 − 1, rồi tính ngược về P cần tìm; truy hồi này hội tụ rất nhanh. (Kiểm của người tổng hợp: khi P → ∞, truy hồi thành R = 1/(2 + R), tức R² + 2R − 1 = 0, R = √2 − 1, khớp trò chơi số 6.) Với trường hợp không bỏ bài, R_P đơn giản bằng r ở mọi ngưỡng, và trò chơi rút về bản không bỏ bài.

Có R_P thì tính x₁ bằng 17.12, nhân dần với các R_P thích hợp để được các ngưỡng value; như thường lệ, các vùng bluff và vùng call theo sau các vùng value, và ta có lời giải.

**Bảng số của người tổng hợp** (sách không in): tính R_P bằng truy hồi ngược bắt đầu từ r ở 200 bước (kết quả không đổi nếu bắt đầu từ 0 hay 1 ở 30 bước), rồi x₁ bằng 17.12:

| P | R_P (trò chơi số 12) | R = (1 − α₂)/2 (trò chơi số 10) | x₁ trò chơi số 12 | y₂ = R_P·x₁ |
|---|---|---|---|---|
| 1 | 0,3263 | 0,375 | 0,1339 | 0,0437 |
| 2 | 0,3457 | 0,400 | 0,2477 | 0,0856 |
| 4 | 0,3669 | 0,429 | 0,3624 | 0,1330 |
| 9 | 0,3878 | 0,458 | 0,4562 | 0,1769 |
| 100 | 0,4113 | 0,495 | 0,5385 | 0,2215 |
| ∞ | 0,4142 (r) | 0,5 | 0,5469 | 0,2265 |

Khi X có thể reraise, Y raise ít hơn (R_P nhỏ hơn R của trò chơi số 10), và X bet rộng hơn một chút (ví dụ P = 4: 0,362 so với 0,344). Cột P = ∞ trùng trò chơi số 6 của Chương 16 (x₁ ≈ 0,5469, y₂ ≈ 0,2265).

### 6. Khái niệm then chốt (Key Concepts, trang 222–223)

- Các trò chơi [0,1] mở rộng được cho những tình huống phức tạp hơn, gồm check-raise, số bet tuỳ ý, và các luật khác.
- Trong mọi tình huống đó, chìa khoá của trò chơi là các ngưỡng value. Với mỗi vùng value có các vùng bluff, call, fold và raise-bluff tương ứng, tính được bằng cách liên hệ kích thước pot với kích thước vùng value.
- Trong trò chơi không check-raise, có một hệ thức truy hồi giữa các ngưỡng X và Y xen kẽ: x₁ → y₂ → x₃ và cứ thế.
- Trong trò chơi có check-raise, có một hệ thức truy hồi tương tự giữa các ngưỡng Y liên tiếp.
- Nếu đối thủ có thể bet nhưng check, bạn không thể bị raise, và đối thủ có thể call hoặc fold, chiến lược đúng là value bet mọi tay đối thủ lẽ ra đã value bet và một nửa số tay đối thủ sẽ call.

## Luận điểm cốt lõi

### Mệnh đề

Trong trò chơi [0,1] pot hữu hạn, chiến lược tối ưu của mỗi người được quyết định bởi các ngưỡng value; mọi vùng khác (bluff, raise-bluff, check-raise bluff, call, fold) có độ rộng tỷ lệ với vùng value tương ứng qua αₙ = 1/(P + 2n − 1). Value bet sau khi đối thủ check gồm mọi tay đối thủ lẽ ra đã bet và một nửa số tay đối thủ sẽ call; tỷ lệ raise tiến từ 1/2 (bet cuối) xuống r = √2 − 1 (raise không giới hạn) và phụ thuộc kích thước pot.

### Giả định

- Bài phân phối đều, độc lập trên [0, 1]; một vòng cược; X hành động trước.
- Limit: bet cố định 1 đơn vị; pot P bet (hữu hạn); được bỏ bài.
- Các vùng chiến lược liền nhau theo thứ tự tác giả chọn; trong các lựa chọn đồng tối ưu (ví dụ vị trí vùng raise-bluff), chọn chiến lược không bị trội (raise-bluff bằng các tay mạnh nhất trong vùng không call).
- Kỳ vọng tính ex-showdown.

### Cơ chế

1. Tham số hoá chiến lược: thêm cho mỗi vùng value một vùng bluff và các ngưỡng call/fold (*), bluff/fold (#).
2. Viết phương trình bàng quan tại mỗi ngưỡng; với pot hữu hạn, các dòng có thể có ±P hoặc ±(P + 1).
3. Các phương trình chia thành hai loại: loại "bluff/value" (vùng bluff bằng αₙ lần vùng value; người bị bet tiếp tục với 1 − αₙ số tay) và loại "value" (các ngưỡng value, quyết định toàn bộ cấu trúc).
4. Rút gọn về một công thức cho x₁ (17.12) hoặc y₁ (17.13) theo tỷ lệ raise R; với nhiều bet, R thay bằng R_P tính bằng truy hồi.

### Bằng chứng và ví dụ tác giả đưa ra

- Trò chơi số 9: sáu bảng bàng quan, lời giải đóng; ví dụ pot 4: y₁ = 2/3, x₁ = 8/15, x₁* = y₁* = 4/5.
- Trò chơi số 10: chín phương trình (17.2)–(17.10), lời giải đóng, bảng số cho P = ∞, 1, 2, 9, ε.
- Trò chơi số 11: phương trình bàng quan tại x₂ dẫn tới y₂ = y₁(1 − α₂)/2 và 17.13.
- Trò chơi số 12: phương trình 17.14 và truy hồi R_P.

### Kết luận và hàm ý cho người chơi

- Mỗi khi bet hay raise for value, cần có bluff tương ứng; tỷ lệ bluff giảm khi pot nhỏ đi so với bet (pot 4: 1 bluff cho 5 value bet; pot 1: 1 cho 2).
- Raise-bluff nên dùng các tay "gần đủ để call" chứ không phải tay tệ nhất.
- Khi bị raise, phải tiếp tục với 1 − α₂ số tay đã bet (fold α₂), nếu không đối thủ raise-bluff có lời.
- Sau khi đối thủ check, value bet với mọi tay đối thủ lẽ ra đã bet và một nửa số tay đối thủ sẽ call.
- Khi đối thủ có thể check-raise, bet chặt hơn sau khi đối thủ check; khi đối thủ có thể reraise, raise ít hơn.

### Trong ngôn ngữ lý thuyết trò chơi

Mỗi trò chơi là trò chơi tổng bằng hằng số hai người, thông tin không đầy đủ, với cân bằng Nash dạng chiến lược ngưỡng; các bluff là phần "hỗn hợp" của chiến lược (dù về hình thức là chiến lược thuần trên từng tay, tỷ lệ bluff trên toàn phân phối đóng vai trò tần suất hỗn hợp). Điều kiện bàng quan cho một hệ phương trình tuyến tính theo các ngưỡng; nghiệm phụ thuộc hữu tỷ vào α. Khi số bet không giới hạn, cấu trúc tự đồng dạng (ngoài kích thước pot) cho một truy hồi phân thức liên tục cho R_P, có điểm bất động r = √2 − 1 khi pot vô hạn.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| finite pot | pot hữu hạn | pot có P bet, người chơi có thể bỏ bài |
| pot | pot | tổng tiền cược trên bàn |
| bet / call / check / fold | bet / call / check / fold | đặt cược / theo / không cược / bỏ bài |
| raise / reraise | raise / reraise | tăng cược / tăng tiếp |
| check-raise | check-raise | check rồi raise khi đối thủ bet |
| bluff | bluff | bet với bài yếu để đối thủ bỏ bài tốt hơn |
| bluffing region | vùng bluff | khoảng tay bài dùng để bluff |
| raise-bluff | raise-bluff | raise như một bluff |
| check-raise bluff | check-raise bluff | check-raise như một bluff |
| reraise-bluff | reraise-bluff | reraise như một bluff |
| value bet / value raise | value bet / value raise | bet hay raise mong bị call bởi bài yếu hơn |
| bet-call / bet-fold | bet rồi call / bet rồi fold | phản ứng của người đã bet khi bị raise |
| check-call / check-fold | check rồi call / check rồi fold | phản ứng của người đã check khi bị bet |
| showdown / showdown value | showdown / giá trị showdown | lật bài so sánh / khả năng thắng khi lật bài |
| nuts | nuts | bài mạnh nhất có thể; ở đây là 0 |
| α (alpha), αₙ | α, αₙ | 1/(P + 2n − 1): tỷ lệ vùng bluff trên vùng value |
| threshold xₙ*, yₙ* | ngưỡng có dấu sao | ranh giới call / fold (hoặc call / raise-bluff) |
| threshold yₙ# | ngưỡng có dấu thăng | ranh giới bluff bet thứ n / fold |
| indifference equation | phương trình bàng quan | hai hành động cùng kỳ vọng tại ngưỡng |
| parameterization | tham số hoá | mô tả chiến lược bằng thứ tự các ngưỡng |
| dominated / co-optimal | bị trội / đồng tối ưu | kém hơn một chiến lược khác / cùng tối ưu |
| exploit | khai thác | tăng kỳ vọng nhờ lỗi của đối thủ |
| optimal strategy | chiến lược tối ưu | chiến lược cân bằng, không bị khai thác |
| closed-form solution | lời giải đóng | công thức tường minh cho các ngưỡng |
| raising ratio R, R_P | tỷ lệ raise R, R_P | tỷ lệ giữa vùng raise và vùng bet trước đó |
| recursion / recurrence relation | truy hồi / hệ thức truy hồi | quan hệ giữa các số hạng liên tiếp |
| golden mean of poker | tỷ lệ vàng của poker | r = √2 − 1 ≈ 0,414 |
| ex-showdown | ex-showdown | chỉ tính phần thay đổi so với kết quả showdown |
| full-street / half-street | full-street / half-street | cả hai người được bet / chỉ một người |
| limit | limit | kích thước bet cố định |

## Câu nói đáng nhớ

> "However, bluffing is a key element of poker, and with its introduction to the game we obtain much more complexity, and additionally better approximations and insight into real poker." — phần mở đầu
>
> *Dịch: Tuy nhiên, bluff là thành phần then chốt của poker; đưa nó vào trò chơi làm trò chơi phức tạp hơn nhiều, nhưng cho xấp xỉ tốt hơn và hiểu biết sâu hơn về poker thật.*
>
> Ý nghĩa: lý do chuyển từ mô hình không bỏ bài sang pot hữu hạn.

> "If your opponent could have bet but checks, you cannot be raised, and your opponent may call or fold, the proper strategy is to value bet all hands that your opponent would have value bet and half the hands with which he will call." — Ví dụ 17.1 và Key Concepts
>
> *Dịch: Nếu đối thủ có thể bet nhưng check, bạn không thể bị raise, và đối thủ có thể call hoặc fold, chiến lược đúng là value bet mọi tay đối thủ lẽ ra đã value bet và một nửa số tay đối thủ sẽ call.*
>
> Ý nghĩa: quy tắc thực hành quan trọng nhất của chương cho value bet ở vị trí sau.

> "So Y cannot just value raise with his best hands without protecting those value raises with some type of raise-bluffs." — Ví dụ 17.2
>
> *Dịch: Vậy Y không thể chỉ value raise với tay tốt nhất mà không bảo vệ các value raise đó bằng một kiểu raise-bluff.*
>
> Ý nghĩa: không có bluff, đối thủ fold mọi tay trung bình và value raise mất giá trị.

> "Using the principle that raise-bluffs should never win the pot if called, we can see that the raise-bluffs will come from the remaining fraction of hands that are neither raising hands nor calling hands." — Ví dụ 17.2
>
> *Dịch: Theo nguyên tắc raise-bluff không bao giờ nên thắng pot khi bị call, ta thấy raise-bluff phải lấy từ phần tay còn lại, không phải tay raise cũng không phải tay call.*
>
> Ý nghĩa: vị trí của raise-bluff trong phân phối bài.

> "For every value region, there is a corresponding bluffing region." — Ví dụ 17.2
>
> *Dịch: Với mỗi vùng value, có một vùng bluff tương ứng.*
>
> Ý nghĩa: quy tắc cấu trúc chung của mọi trò chơi [0,1] pot hữu hạn.

> "Admittedly, this final solution isn't particularly useful - what is useful is the method and the principles that were used in deriving it." — Ví dụ 17.2
>
> *Dịch: Phải thừa nhận lời giải cuối cùng này không hữu ích lắm; điều hữu ích là phương pháp và các nguyên lý dùng để tìm ra nó.*
>
> Ý nghĩa: giá trị của chương nằm ở cách lập luận, không ở công thức.

> "The ratio of Y thresholds to X thresholds in the no-check-raise game is the ratio of successive Y thresholds in the game with check-raise." — Ví dụ 17.3
>
> *Dịch: Tỷ lệ giữa ngưỡng Y và ngưỡng X trong trò chơi không check-raise là tỷ lệ giữa các ngưỡng Y liên tiếp trong trò chơi có check-raise.*
>
> Ý nghĩa: một quy luật chuyển đổi gọn giữa hai họ trò chơi.

> "In all of these situations, however, the keys to the game are the value thresholds." — Key Concepts
>
> *Dịch: Trong mọi tình huống đó, chìa khoá của trò chơi là các ngưỡng value.*
>
> Ý nghĩa: xác định đúng vùng value là đủ để suy ra phần còn lại của chiến lược.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương cho thấy một cấu trúc rất gọn ẩn sau các lời giải đại số rối rắm: mọi vùng phi value đều tỷ lệ với một vùng value qua αₙ, nên chỉ cần tìm các ngưỡng value. Trò chơi số 9 được giải hai lần — bằng đại số và bằng lập luận trực giác với pot 4 — giúp người đọc thấy mỗi phương trình nói điều gì về poker. Nguyên lý "value bet mọi tay đối thủ lẽ ra đã bet và một nửa số tay đối thủ sẽ call" là một quy tắc thực hành rõ ràng. Phân tích raise-bluff (lấy từ tay mạnh nhất trong vùng không đủ call, không phải tay tệ nhất) là một điểm tinh tế mà nhiều người chơi không tự nghĩ ra. Kết quả công thức 17.12 dùng chung cho mọi trò chơi không check-raise, và truy hồi R_P nối liền với r = √2 − 1 của Chương 14 và Chương 16.

### Những chỗ đơn giản hoá

- **Một vòng cược và phân phối đều độc lập**: không có lá bài tiếp theo, không có draw, không có liên hệ giữa phân phối bài và hành động ở các vòng trước.
- **Limit với bet cố định**: kích thước bet không phải là biến quyết định (Chương 14 mới xét no-limit).
- **Phần trò chơi số 11 và số 12 chỉ được phác thảo**: sách không in lời giải đầy đủ, và một số bước ("We can follow this chain of logic to find…") bị bỏ qua; người tổng hợp phải tự giải số để kiểm.
- **Nhiều lỗi in và tham chiếu sai** (đã liệt kê ở khối Lưu ý), đặc biệt ở phần tính tay với pot 4 và trong việc gọi tên các trò chơi tương ứng của Chương 16; người đọc tự kiểm sẽ dễ bị lạc.
- **Thứ tự vùng được giả định**: vùng raise-bluff được đặt ngay dưới vùng call vì chiến lược khác bị trội; lời giải không chứng minh rằng mọi cân bằng đều có dạng này.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

Các solver GTO hiện đại giải trực tiếp những tình huống river nhiều kích thước bet với phân phối bài thật; kết quả của chúng thường xác nhận những nguyên tắc của chương: tỷ lệ bluff trên value bet tăng theo kích thước bet so với pot, raise-bluff và check-raise bluff thường dùng các tay có ít giá trị showdown nhưng không phải tệ nhất (trong poker thật còn tính tới "blocker" — lá bài làm giảm khả năng đối thủ có tay mạnh), và người bị bet phải tiếp tục với khoảng 1 − α phân phối để không bị bluff có lời (khái niệm "minimum defense frequency" trong cộng đồng poker). Ngôn ngữ "polarized range" (dải bài phân cực gồm value và bluff) trở nên phổ biến chính là mô tả cấu trúc vùng value cộng vùng bluff mà chương này trình bày.

### Liên hệ các chương khác

- [C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md): α = 1/(P + 1) (Phương trình 11.1), 1 − y₀ = αy₁ (Phương trình 11.4), trò chơi số 2 half-street có bluff.
- [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md): r = √2 − 1 (Phương trình 14.1), giới hạn của R_P.
- [C16-tro-choi-01-khong-bo-bai.md](C16-tro-choi-01-khong-bo-bai.md): các trò chơi số 5, 6, 7 là giới hạn pot vô hạn của trò chơi số 10, 12, 11; quy tắc "nửa số tay" và tỷ lệ r.
- [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md): giá trị trò chơi và bài học tổng kết của họ trò chơi [0,1].
- [C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md), [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md): mở rộng sang nhiều vòng cược.

### Vận dụng

- **Cho người chơi poker:** trước mỗi value bet hay value raise, hãy hỏi "vùng bluff tương ứng của mình là gì?". Với bet bằng pot (P = 1 nếu tính pot bằng một bet), tỷ lệ bluff trên value bet là 1:2; với pot 4 bet là 1:5; càng ít bluff khi pot càng lớn so với bet. Khi bị bet, fold không quá α số tay có thể thắng bluff (pot 4: fold không quá 1/5). Khi chọn tay để raise-bluff, ưu tiên tay vừa dưới ngưỡng call, không phải tay tệ nhất. Ở vị trí sau, khi đối thủ check, value bet với mọi tay đối thủ lẽ ra đã bet và nửa số tay đối thủ sẽ call — không phải nửa số tay đối thủ có thể có.
- **Cho người làm tài chính và ra quyết định:** cấu trúc "mỗi cam kết thật (value) phải đi kèm một tỷ lệ cam kết giả (bluff) để đối phương không thể suy ra thông tin từ hành động" xuất hiện trong đàm phán, đấu giá và chiến lược cạnh tranh: nếu chỉ hành động mạnh khi thực sự mạnh, đối phương sẽ luôn nhượng bộ đúng lúc và không bao giờ trả giá cho sự yếu thế của mình. Tỷ lệ cân bằng phụ thuộc vào "pot" (giá trị đang tranh chấp) so với chi phí mỗi hành động — cùng logic với α = 1/(P + 1). Phương pháp lập phương trình bàng quan tại các ngưỡng và khử dần ẩn là công cụ chung khi thiết kế quy tắc quyết định trước một đối thủ thông minh.
