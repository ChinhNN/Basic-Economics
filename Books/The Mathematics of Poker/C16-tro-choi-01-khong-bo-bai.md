# Chương 16 — Cược nhỏ, pot lớn: các trò chơi [0,1] không bỏ bài (Small Bets, Big Pots: No-Fold [0,1] Games)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 16 "Small Bets, Big Pots: No-Fold [0,1] Games", trang 183–200, cùng Phụ lục Chương 16 "Solving the Difference Equations", trang 201–203.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương này thuộc Phần III "Chơi tối ưu" (Optimal Play). Chương 11 ([C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md)) đã giới thiệu trò chơi [0,1] ở dạng half-street (chỉ một người được bet), trong đó có trò chơi [0,1] số 1 không cho bỏ bài, và đặt quy ước đặt tên ngưỡng x₁, y₁, x₂…. Chương 14 ([C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md)) đặt tên hằng số r = √2 − 1 là "tỷ lệ vàng của poker" (golden mean of poker). Chương 15 ([C15-tro-choi-tron-vong.md](C15-tro-choi-tron-vong.md)) giải trò chơi full-street đầu tiên (cả hai người đều có quyền bet) trên trò chơi AKQ. Chương 16 đưa trò chơi [0,1] sang full-street nhưng giữ luật "không ai được bỏ bài", nên không có bluff; chương giải năm trò chơi [0,1] số 4 tới số 8, từ một bet duy nhất tới raise không giới hạn có check-raise, và cho thấy r = √2 − 1 là tỷ lệ raise đúng khi đối thủ có thể raise lại. Chương 17 ([C17-tro-choi-01-pot-huu-han-va-bluff.md](C17-tro-choi-01-pot-huu-han-va-bluff.md)) giải lại đúng các cấu trúc này nhưng với pot hữu hạn (có bỏ bài, có bluff), và nhiều lần so sánh với các trò chơi số 6 và số 7 của chương này; Chương 18 ([C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md)) tính giá trị trò chơi (game value) mà chương này mới chỉ nhắc tới.
**Ý chính:** **Khi không ai được bỏ bài, poker chỉ còn là bài toán rút đúng lượng giá trị từ bài mạnh: mỗi người bet hoặc raise với một tỷ lệ cố định của những tay bài mà đối thủ còn có thể đang cầm, và tỷ lệ đó là 1/2 khi không thể bị raise lại, là r = √2 − 1 ≈ 0,414 khi việc raise qua lại không giới hạn.** Luật "không bỏ bài" mô phỏng tình huống pot rất lớn so với một bet, nên mọi chiến lược tối ưu đều không có bluff. Mọi trò chơi được giải bằng cùng một phương pháp: tham số hoá chiến lược bằng các ngưỡng, rồi viết một phương trình bàng quan (indifference equation) tại mỗi ngưỡng. **Trò chơi số 4** (một bet, không raise): X bet mọi tay bài (x₁ = 1), Y luôn call, giá trị trò chơi bằng 0. **Trò chơi số 5** (hai bet, không check-raise): x₁ = 1/2, y₂ = 1/4, y₁ = 3/4; Y raise với một nửa số tay X bet, bet sau khi X check với một nửa số tay X check, và vùng raise của Y rộng bằng vùng check của Y; Y có lợi thế vị trí (người tổng hợp tính được 1/8 bet). **Trò chơi số 6** (raise không giới hạn, không check-raise): mỗi ngưỡng raise bằng R lần ngưỡng trước, và phương trình bàng quan tại y₂ cho R² + 2R − 1 = 0, tức R = √2 − 1; x₁ ≈ 0,5469, y₁ ≈ 0,7735, y₂ ≈ 0,2265, x₃ ≈ 0,0938. **Trò chơi số 7** (hai bet, có check-raise): x₂ = 1/9, y₂ = 1/3, x₁ = 5/9, y₁ = 2/3; so với trò chơi số 5, Y bet ít tay hơn sau khi X check (vì sợ bị check-raise), X bet thêm các tay trung bình, Y raise rộng hơn. **Trò chơi số 8** (raise không giới hạn, có check-raise): phương trình bàng quan dẫn tới phương trình sai phân y_{k+2} + 2y_{k+1} − y_k = 0 và x_k + 2x_{k+1} − x_{k+2} = 2r^k; nghiệm là yₙ = rⁿ/(1 − r) và xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2, tức xₙ = rⁿ khi n chẵn và rⁿ⁻¹(1 − r) khi n lẻ; X check đúng một nửa số tay, trong đó r ≈ 0,414 là check rồi call và khoảng 0,086 là check-raise. Phụ lục trình bày cách giải hai phương trình sai phân bằng phương trình đặc trưng và nghiệm riêng.

> **Lưu ý:**
> - **Lỗi trong bảng bàng quan tại x₁ của Ví dụ 16.1 (trang 184):** bảng ghi tiêu đề cột "X's hand", "<Y, bet>", "<Y, check>", nhưng nội dung là bài của **Y** và kỳ vọng của **X** khi X bet hoặc check (X đang ở ngưỡng x₁ và cân nhắc hành động của chính mình). Ô "Product" ở dòng [0, x₁] ghi "x₁" cho cả hai cột; đúng ra là −x₁ (xác suất x₁ nhân với −1). Các tổng 1 − 2x₁ và y₁ − 2x₁ của sách chỉ đúng khi dùng −x₁: (−x₁) + (y₁ − x₁) + (1 − y₁) = 1 − 2x₁ và (−x₁) + (y₁ − x₁) + 0 = y₁ − 2x₁.
> - **Lỗi chỉ số trong bảng tại y₁ của Ví dụ 16.2 (trang 187):** tổng ghi "2y₂ − x₁ − 1" và phương trình ghi "2y₂ − x₁ − 1 = 0"; đúng là 2y₁ − x₁ − 1, vì (y₁ − x₁) − (1 − y₁) = 2y₁ − x₁ − 1. Kết luận y₁ = (1 + x₁)/2 của sách đúng.
> - **Dấu sai trong bảng tại x₁ của Ví dụ 16.2 (trang 186):** dòng [x₁, y₁] (bài Y yếu hơn X) ghi −1 cho cả check-call và bet; đúng là +1 cho cả hai (X thắng một bet). Hiệu vẫn bằng 0 nên phương trình y₂ = 1 − y₁ không đổi. Bảng tương tự ở Ví dụ 16.4 (trang 193) gộp hai khoảng [y₂, x₁] và [x₁, y₁] thành một dòng ghi −1, cùng lỗi này.
> - **Nhãn không nhất quán ở phần kiểm tra lời giải của Ví dụ 16.2 (trang 188):** sách viết "<y, x bets>" và "<x, check>" cho hai đại lượng cùng là kỳ vọng của Y; các phép tính 4x − 5/4 và 2x − 3/4 đều đúng.
> - **Lỗi chỉ số trong bảng tại y₂ của Ví dụ 16.3 (trang 190):** dòng [y₂, x₁] ghi tích "−1(x₁ − y₁)"; đúng là −(x₁ − y₂). Tổng x₃ + 2y₂ − x₁ của sách đúng với y₂: 2x₃ + (y₂ − x₃) − (x₁ − y₂) = x₃ + 2y₂ − x₁.
> - **Ký hiệu R và r trong Ví dụ 16.3:** sách gọi tỷ lệ raise là R trong toàn bộ lời giải, rồi trong khung "Solution" chuyển sang r (hằng số √2 − 1 của Chương 14). Hai ký hiệu chỉ cùng một số sau khi giải ra R = √2 − 1.
> - **Lỗi trong bảng tại y₁ của Ví dụ 16.4 (trang 193):** tiêu đề cột ghi "Y raises / Y calls", đúng là "Y check / Y bets". Hai dòng [x₁, y₁] và [y₁, 1] bị đảo dấu ở cột chênh lệch: với hiệu (check − bet), dòng [x₁, y₁] là 0 − (−1) = +1, tích +(y₁ − x₁); dòng [y₁, 1] là 0 − (+1) = −1, tích −(1 − y₁). Tổng sách ghi "2x₂ + 2y₂ − x₁ + 1"; đúng là 2x₂ + 2y₁ − x₁ − 1. Phương trình cuối 2y₁ = 1 + x₁ − 2x₂ của sách đúng (kiểm bằng lời giải: 2/9 + 4/3 − 5/9 − 1 = 0), nên lỗi chỉ nằm trong bảng.
> - **Lỗi trong Ví dụ 16.5, bảng tại x₂ (trang 195):** tổng ghi "−y₃ + 1 − 2y₁ − y₂"; đúng là −y₃ − 1 + 2y₁ − y₂ (từ −y₃ + (y₁ − y₂) − (1 − y₁)). Dòng sau của sách, y₃ + y₂ + 1 = 2y₁, lại đúng. Bước thế y₂ = 1 − y₁ của sách cho "y₃ + 2 = 2y₁"; đúng là **y₃ + 2 = 3y₁** (vì y₃ + (1 − y₁) + 1 = 2y₁). Kiểm bằng lời giải cuối: y₃ + 2 = 0,12132 + 2 = 2,12132 và 3y₁ = 3 × 0,70711 = 2,12132. Bảng cũng bỏ qua các khoảng bài của Y có chênh lệch bằng 0 (ví dụ [y₃, y₂]); việc bỏ này không sai nhưng làm bảng khó theo dõi.
> - **Lỗi trong Ví dụ 16.5, bảng tại x₄ (trang 196):** tiêu đề cột ghi "X bet-reraises / X check-raises", nhưng cột thứ nhất thực ra là "check-raise rồi raise tiếp" và cột thứ hai là "bet rồi reraise" (đúng như câu dẫn của sách). Tổng ghi "… + 2y₁ + 1"; đúng là −y₅ + 2y₃ − y₄ − 2y₂ + 2y₁ − 1. Dạng sắp xếp lại ngay sau đó, (y₃ − y₄) + (y₁ − y₂) = y₅ + (y₂ − y₃) + (1 − y₁), đúng (kiểm số: hai vế cùng bằng 0,48528).
> - **Lỗi trong lời giải của Y ở Ví dụ 16.5 (trang 196):** sách viết "yₙ = rⁿ/(1 − r) (for y > 0)", đúng là "với n ≥ 1" (công thức cho n = 0 ra 1,707, không phải ngưỡng). Sách viết "y₁ is 1/(1 − r)"; đúng là y₁ = r/(1 − r) = 1/√2 ≈ 0,7071, như chính bảng ngưỡng của sách và câu "Y puts in the first bet if checked to with hands below r/(1 − r)" ở trang 199.
> - **Lỗi chỉ số khi cộng hai phương trình của X (trang 199):** dòng đầu ghi "x_{k+1} − y_k + x_k − y_{k+1} = …"; số hạng đầu đúng là x_{k−1} (lấy từ phương trình tại y_k: x_{k−1} − y_k = …). Dòng tiếp theo của sách, x_{k−1} + 2x_k − x_{k+1} = 2y_k + 2y_{k+1}, đúng.
> - **Bảng ở phương trình tại y₂ của Ví dụ 16.5 (trang 198):** các ô "0 / −2" là phần chênh lệch thêm, không phải kỳ vọng thật của mỗi hành động (ví dụ X cầm bài trong [x₄, x₃] thì Y raise mất 3 bet, Y call mất 1 bet; chênh lệch 2). Số hạng cuối của tổng ghi "2(x₂ₖ − x₂ₖ₊₁)", đúng ra phải là 2(x₂ₖ₊₁ − x₂ₖ₊₂) cho phương trình tại y₂. Không ảnh hưởng kết quả.
> - **Lỗi trong tổng các vùng check của X (trang 200):** sách viết tổng là r Σ_{n=1}^{∞} (r²)ⁿ; chỉ số đúng phải bắt đầu từ n = 0 (các vùng có độ rộng r, r³, r⁵, …). Với n = 1 tổng chỉ là r³/(1 − r²) ≈ 0,0858. Sách sau đó dùng đúng công thức r/(1 − r²). Dòng "r² = 2·2√2 + 1 = 3 − 2√2" in hỏng; đúng là r² = 2 − 2√2 + 1 = 3 − 2√2 ≈ 0,1716.
> - **Lỗi trong Phụ lục (trang 201–203):** (1) "yₙ = arⁿ + b(−1 − √2)qⁿ" đúng là yₙ = arⁿ + b(−1 − √2)ⁿ. (2) Dòng "a(1 − r) − 1" thiếu "= 0". (3) "This equation, like Equation 20.1" đúng là Phương trình 16.1. (4) **Hằng số của nghiệm riêng tính sai:** từ c(1 + 2r − r²) = 2 và r² = 1 − 2r được c · 4r = 2, nên c = 1/(2r) ≈ 1,2071, không phải c = r/2 ≈ 0,2071 như sách viết; nghiệm riêng đúng là Z = rⁿ/(2r) = rⁿ⁻¹/2. Các dòng tiếp theo của sách ("½r", "a = (2r − 1)/2r") và công thức cuối xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2 chỉ đúng khi hiểu hằng số là 1/(2r); nếu dùng r/2 thì sẽ ra a = 1 − r/2 và công thức sai. (5) Định nghĩa "nghiệm riêng là một nghiệm cho một giá trị k nào đó" không chính xác: nghiệm riêng là một dãy thoả phương trình không thuần nhất với **mọi** k (nhận xét của người tổng hợp).
> - **Các hình chiến lược (Hình 16.1–16.4) là sơ đồ minh hoạ, không vẽ đúng tỷ lệ:** ngưỡng của X luôn được ghi là "x₁*" trong khi theo quy ước của Chương 11, dấu sao dành cho ngưỡng giữa call và fold; ở đây đúng ra là x₁. Hình 16.3 (trò chơi số 7) vẽ y₁ khoảng 0,77 và y₂ khoảng 0,22 (đọc từ trục, ước lượng) trong khi lời giải là y₁ = 2/3, y₂ = 1/3; Hình 16.4 (trò chơi số 8) vẽ y₁ khoảng 0,77 và x₁ khoảng 0,55 trong khi lời giải là 0,7071 và 0,5858. Bản tổng hợp dùng giá trị của lời giải, không dùng vị trí trên hình.
> - **Lớp chữ OCR:** chữ "l" thay số 1 ("l/(l+2r)"), phân số 1/2, 1/4, 3/4 bị làm phẳng thành "12", "14", "34"; "m" thay "in" ("no x 2 m this game"); "rn-1" là rⁿ⁻¹. Mọi công thức đã được đọc lại từ ảnh trang.
> - **Quy ước:** "kỳ vọng" trong chương là kỳ vọng ex-showdown, chỉ tính số bet thắng hay thua trên vòng cược đang xét, không tính phần pot có sẵn. Bài 0 là bài mạnh nhất (nuts), bài 1 là bài yếu nhất. Số thập phân dùng dấu phẩy; phân số giữ dạng a/b.

## Sơ đồ

### Phần mở đầu Chương 16 — trò chơi [0,1] full-street với luật không bỏ bài (trang 183)

```text
       Chương 15 đã giải trò chơi full-street đầu tiên (trò chơi AKQ, cả
       hai người đều có quyền bet); chương này quay lại trò chơi [0,1]
       · trò chơi [0,1] gần poker nhất vì có vô số loại bài và người chơi
         phải chia bài thành các VÙNG hành động
                                │
                                ▼
       Luật xuyên suốt chương: KHÔNG AI ĐƯỢC BỎ BÀI (đã gặp ở Chương 11)
       · luật này xấp xỉ tình huống pot cực lớn so với một bet
       · hệ quả: không chiến lược nào có bluff, vì bluff chỉ có ích khi
         đối thủ có thể bỏ bài
                                │
                                ▼
       Luận điểm in nghiêng của chương: trò chơi không bỏ bài là bài tập
       rút ĐÚNG LƯỢNG giá trị từ bài mạnh
```

### Ví dụ 16.1 — Trò chơi [0,1] số 4: một bet, không raise (Example 16.1 [0,1] Game #4, trang 183–185)

```text
       Luật: một vòng full-street; không ai được bỏ bài; chỉ một bet
       · ba chuỗi hành động: X bet rồi Y call; X check, Y bet, X call;
         X check rồi Y check
                                │
                                ▼
       Lập luận trực giác:
       · X không bao giờ bet một tay yếu hơn tay X check (Y không bỏ bài)
       · nếu X check, Y bet mọi tay X lẽ ra đã bet (chắc thắng) cộng với
         nửa tốt hơn của các tay còn lại
       · Y chỉ kiếm được giá trị khi X check, nên X chặn được bằng cách
         bet MỌI tay bài
                                │
                                ▼
       Lập luận bằng ngưỡng: X bet dưới x₁, check trên x₁; Y bet dưới
       y₁ khi X check; mỗi người làm đối thủ bàng quan tại ngưỡng của
       đối thủ
       · bàng quan tại y₁:  2y₁ = x₁ + 1
       · bàng quan tại x₁:  1 − 2x₁ = y₁ − 2x₁, nên y₁ = 1
       · thế vào: x₁ = 1
                                │
                                ▼
       LỜI GIẢI: X bet mọi tay, Y call mọi tay; một bet luôn vào pot,
       giá trị trò chơi bằng 0 cho cả hai
```

### Ví dụ 16.2 — Trò chơi [0,1] số 5: hai bet, không check-raise (Example 16.2 [0,1] Game #5, trang 185–188)

```text
       Luật: một vòng; còn hai bet; X không được check-raise; không bỏ bài
       · không có x₂ vì X không bao giờ bỏ được bet thứ hai vào pot
       · bet mọi tay như trò chơi số 4 không còn tốt: Y có thể raise, và
         X có lợi hơn nếu check-call với các tay tệ nhất
                                │
                                ▼
       Thứ tự ngưỡng: 0 < y₂ < x₁ < y₁ < 1
       · X: bet trên [0, x₁], check-call trên [x₁, 1]
       · Y khi X bet: raise trên [0, y₂], call phần còn lại
       · Y khi X check: bet trên [0, y₁], check trên [y₁, 1]
                                │
                                ▼
       Ba phương trình bàng quan:
       · tại y₂ (Y raise hay call):  y₂ = x₁/2, viết chung là y₂ = R·x₁
         với R = 1/2 khi người kia không thể raise lại
       · tại x₁ (X bet hay check-call):  y₂ = 1 − y₁ — vùng raise của Y
         rộng bằng vùng Y check sau khi X check
       · tại y₁ (Y bet hay check):  y₁ = (1 + x₁)/2
       · giải: x₁ = 1/(1 + 2R)
                                │
                                ▼
       LỜI GIẢI: x₁ = 1/2, y₂ = 1/4, y₁ = 3/4
       · kiểm tra: với bài x trong [0, 1/4], kỳ vọng của Y khi X bet là
         4x − 5/4, khi X check là 2x − 3/4; X bet tốt hơn khi x < 1/4
       · Y có lợi thế nhờ vị trí (giá trị trò chơi, Chương 18); người
         tổng hợp tính được Y lời 1/8 bet mỗi ván
```

### Ví dụ 16.3 — Trò chơi [0,1] số 6: trò chơi raise (Example 16.3 [0,1] Game #6 – The Raising Game, trang 188–191)

```text
       Luật: một vòng; raise và reraise không giới hạn, stack vô hạn;
       không check-raise; không bỏ bài
                                │
                                ▼
       Thứ tự ngưỡng: 0 < … < y₂ₙ < x₂ₙ₋₁ < … < x₃ < y₂ < x₁ < y₁ < 1
       · khi X check: chỉ còn ngưỡng y₁ (bet cuối, X không raise được)
       · khi X bet: chuỗi vô hạn — Y raise dưới y₂, X reraise dưới x₃,
         Y bỏ bet thứ tư dưới y₄, …
                                │
                                ▼
       Tính "đối xứng": ở mỗi bước, người raise đứng trước một khoảng bài
       của đối thủ và raise với cùng một tỷ lệ R của khoảng đó
       · y₂ = R·x₁,  x₃ = R·y₂,  nói chung yₙ = R·xₙ₋₁ và xₙ = R·yₙ₋₁
       · như trò chơi số 5: y₁ = (1 + x₁)/2 và y₂ = 1 − y₁,
         nên x₁ = 1/(2R + 1)
                                │
                                ▼
       Phương trình bàng quan tại y₂ (Y raise hay call):
       x₃ + 2y₂ − x₁ = 0  →  R²x₁ + 2Rx₁ − x₁ = 0  →  R² + 2R − 1 = 0
       →  R = √2 − 1 = r, "tỷ lệ vàng của poker" (Chương 14)
                                │
                                ▼
       LỜI GIẢI (r ≈ 0,4142):
       x₁ = 1/(1 + 2r) ≈ 0,5469     y₁ = (1 + r)/(1 + 2r) ≈ 0,7735
       y₂ = r/(1 + 2r) ≈ 0,2265     x₃ = r²/(1 + 2r) ≈ 0,0938
       yₙ (n chẵn) và xₙ (n lẻ) = rⁿ⁻¹/(1 + 2r)
       · trả lời câu hỏi: nên raise đối thủ không bỏ bài nhưng có thể
         raise lại bao thường xuyên? Với tỷ lệ r của các tay đối thủ
         có thể đang cầm
```

### Ví dụ 16.4 — Trò chơi [0,1] số 7: hai bet, có check-raise (Example 16.4 [0,1] Game #7, trang 191–194)

```text
       Luật: như trò chơi số 5 nhưng X ĐƯỢC check-raise
       · thêm một ngưỡng x₂: X check-raise với tay tốt hơn x₂
       · X chỉ check-raise với tay tốt hơn y₁; sách chọn đặt vùng
         check-raise ở dưới cùng (các cách xếp khác cũng tối ưu nếu đúng
         độ rộng), thứ tự: 0 < x₂ < y₂ < x₁ < y₁ < 1
                                │
                                ▼
       Chiến lược:
       · X: check-raise trên [0, x₂]; bet trên [x₂, x₁]; check-call trên
         [x₁, 1]
       · Y khi X bet: raise trên [0, y₂], call trên [y₂, 1]
       · Y khi X check: bet trên [0, y₁], check trên [y₁, 1]
                                │
                                ▼
       Bốn phương trình bàng quan:
       · tại x₂: y₂ = 2y₁ − 1          · tại y₂: y₂ = (x₁ + x₂)/2
       · tại x₁: y₂ = 1 − y₁           · tại y₁: 2y₁ = 1 + x₁ − 2x₂
                                │
                                ▼
       LỜI GIẢI: x₂ = 1/9, y₂ = 1/3, x₁ = 5/9, y₁ = 2/3
                                │
                                ▼
       So với trò chơi số 5:
       · y₁ giảm từ 3/4 xuống 2/3: Y bet ít tay hơn sau khi X check vì
         mỗi bet giờ có thể mất thêm một bet nữa do bị check-raise
       · x₁ tăng từ 1/2 lên 5/9: các tay trung bình của X mất giá trị
         check-call, nên X bet thêm chúng
       · y₂ tăng từ 1/4 lên 1/3: X đã rút bớt tay mạnh nhất sang check
         và bet thêm tay trung bình, nên Y raise được rộng hơn
```

### Ví dụ 16.5 — Trò chơi [0,1] số 8: trò chơi raise có check-raise (Example 16.5 [0,1] Game #8: The Raising Game with Check-Raise, trang 194–200)

```text
       Luật: một vòng; raise không giới hạn; có check-raise; không bỏ bài
       (đây là trò chơi [0,1] một vòng không bỏ bài "đầy đủ")
       · thứ tự ngưỡng: 0 < xₙ₊₁ < yₙ₊₁ < xₙ < yₙ < 1 với mọi n
       · X xen kẽ: check-call [x₁, 1], bet [x₂, x₁], check-raise [x₃, x₂],
         bet rồi reraise [x₄, x₃], …
                                │
                                ▼
       CHIẾN LƯỢC CỦA Y — phương trình bàng quan tại các ngưỡng của X:
       · tại x₁: y₂ = 1 − y₁;  tại x₂: y₃ + y₂ + 1 = 2y₁;  tại x₃, x₄, …
       · trừ hai phương trình liên tiếp (ví dụ tại x₆ và x₇) được
         phương trình sai phân (16.1): y_{k+2} + 2y_{k+1} − y_k = 0
       · nghiệm (Phụ lục): yₙ = rⁿ/(1 − r) với n ≥ 1, tức yₙ = r·yₙ₋₁
       · y₁ = r/(1 − r) ≈ 0,7071; mỗi bet thêm Y chỉ bỏ với tỷ lệ r
         của các tay đã bỏ bet trước
                                │
                                ▼
       CHIẾN LƯỢC CỦA X — phương trình bàng quan tại các ngưỡng của Y:
       · tại yₙ: xₙ₋₁ − yₙ = (yₙ − xₙ) + 2(xₙ₊₁ − xₙ₊₂) + 2(xₙ₊₃ − xₙ₊₄)
         + …, với x₀ = 1
       · cộng hai phương trình liên tiếp, các số hạng xa triệt tiêu:
         (16.2) x_k + 2x_{k+1} − x_{k+2} = 2r^k
       · nghiệm (Phụ lục): xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2,
         tức xₙ = rⁿ khi n chẵn, xₙ = rⁿ⁻¹(1 − r) khi n lẻ
                                │
                                ▼
       Bảng ngưỡng: y₁ ≈ 0,7071  x₁ ≈ 0,5858  y₂ ≈ 0,2929  x₂ ≈ 0,1716
                    y₃ ≈ 0,1213  x₃ ≈ 0,1005  y₄ ≈ 0,0503  x₄ ≈ 0,0294
       · tỷ số yₙ/xₙ dao động: r/(1 − r) + 1/2 khi n lẻ, r/(1 − r) + 1
         khi n chẵn — ngưỡng của X không nằm đều giữa ngưỡng của Y
       · lý do: với bài rất mạnh X thường muốn bet, vì chuỗi "bet rồi
         call" mang lại nhiều giá trị
                                │
                                ▼
       Tổng các vùng X check: r + r³ + r⁵ + … = r/(1 − r²) = 1/2
       · X check đúng một nửa số tay; r ≈ 0,414 trong số đó là check
         rồi call, phần còn lại ≈ 0,086 là check-raise
```

### Khái niệm then chốt cuối chương (Key Concepts, trang 200)

```text
       1. Trong trò chơi full-street không bỏ bài, có một quan hệ quan
          trọng giữa các tay đối thủ có thể đã dùng để hành động và các
          tay bạn dùng để hành động tiếp
       2. Nếu bạn không thể bị raise và đối thủ không thể bỏ bài: bet hoặc
          raise với 1/2 số tay mà đối thủ đã bet hoặc check tới lúc đó
       3. Nếu đối thủ CÓ THỂ raise lại, tỷ lệ này nhỏ đi; khi raise không
          giới hạn, tỷ lệ là r = √2 − 1 ≈ 0,414
       4. Trò chơi không bỏ bài là bài tập rút đúng lượng giá trị từ bài
          mạnh
```

### Phụ lục Chương 16 — Giải các phương trình sai phân (Appendix to Chapter 16: Solving the Difference Equations, trang 201–203)

```text
       PHƯƠNG TRÌNH 16.1: y_{k+2} + 2y_{k+1} − y_k = 0
       (phương trình sai phân tuyến tính thuần nhất cấp hai)
       · dạng chung y_{n+2} + c·y_{n+1} + d·yₙ = 0 có nghiệm yₙ = a·pⁿ + b·qⁿ,
         p, q là hai nghiệm thực phân biệt của x² + cx + d = 0
       · ở đây x² + 2x − 1 = 0, nghiệm x = −1 ± √2, tức r và −1 − √2
       · yₙ phải tiến về 0 khi n lớn, mà |−1 − √2| > 1, nên b = 0
       · điều kiện y₂ = 1 − y₁ và r² = 1 − 2r cho a = 1/(1 − r)
       · KẾT QUẢ: yₙ = rⁿ/(1 − r)
                                │
                                ▼
       PHƯƠNG TRÌNH 16.2: x_k + 2x_{k+1} − x_{k+2} = 2r^k
       (không thuần nhất vì vế phải khác 0)
       · nghiệm tổng quát = nghiệm của phương trình thuần nhất + một
         nghiệm riêng Z
       · thuần nhất: 1 + 2x − x² = 0, nghiệm 1 ± √2, tức −r và 1 + √2;
         bỏ 1 + √2 vì không hội tụ
       · nghiệm riêng thử dạng Z = c·rⁿ: c(1 + 2r − r²) = 2, tức c·4r = 2,
         c = 1/(2r) (sách in nhầm r/2)
       · điều kiện x₀ = 1 cho a = (2r − 1)/(2r)
       · KẾT QUẢ: xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2
```

## Ba câu hỏi chương này trả lời

1. **Khi không ai được bỏ bài, nên bet và raise với bao nhiêu tay?** Không có bluff; mọi bet đều là value bet, và số tay bet được quyết định bởi tỷ lệ giữa các tay mình bet và các tay đối thủ còn có thể đang cầm. Nếu không thể bị raise lại, tỷ lệ là 1/2: trong trò chơi số 5, X bet với [0; 1/2], Y raise với [0; 1/4] (một nửa của 1/2), và khi X check thì Y bet với [0; 3/4] (mọi tay X lẽ ra đã bet cộng với nửa tốt hơn của phần X check). Nếu việc raise qua lại không giới hạn, tỷ lệ là R = √2 − 1 ≈ 0,414, nghiệm của R² + 2R − 1 = 0 (trò chơi số 6: x₁ ≈ 0,5469, y₂ ≈ 0,2265, x₃ ≈ 0,0938…).
2. **Quyền check-raise thay đổi chiến lược tối ưu thế nào?** Người ở vị trí sau (Y) phải bet ít tay hơn sau khi X check, vì mỗi bet có thể bị check-raise và mất thêm một bet; X bù lại bằng cách bet thêm các tay trung bình đã mất giá trị check-call; Y nhờ đó raise được rộng hơn. Với hai bet (trò chơi số 7), y₁ giảm từ 3/4 xuống 2/3, x₁ tăng từ 1/2 lên 5/9, y₂ tăng từ 1/4 lên 1/3, và X check-raise với 1/9 tay mạnh nhất. Với raise không giới hạn (trò chơi số 8), ngưỡng của Y thành dãy hình học yₙ = rⁿ/(1 − r) (y₁ ≈ 0,7071), còn X check đúng một nửa số tay: r ≈ 0,414 để check-call và khoảng 0,086 để check-raise.
3. **Làm sao giải được trò chơi có vô số ngưỡng?** Viết phương trình bàng quan tại một ngưỡng tổng quát, lấy hiệu hoặc tổng của hai phương trình liên tiếp để các số hạng xa triệt tiêu, được phương trình sai phân tuyến tính: y_{k+2} + 2y_{k+1} − y_k = 0 cho Y và x_k + 2x_{k+1} − x_{k+2} = 2r^k cho X. Giải bằng phương trình đặc trưng (nghiệm r và −1 − √2), loại nghiệm không hội tụ, rồi dùng điều kiện biên (y₂ = 1 − y₁; x₀ = 1). Kết quả: yₙ = rⁿ/(1 − r), xₙ = rⁿ khi n chẵn và rⁿ⁻¹(1 − r) khi n lẻ.

## Khái niệm cần biết

- **Trò chơi [0,1] ([0,1] game):** mỗi người chơi nhận một số ngẫu nhiên phân phối đều trên đoạn [0, 1]; số nhỏ hơn thắng ở showdown (0 là nuts, tức bài mạnh nhất có thể). Ví dụ: X cầm 0,30, Y cầm 0,55 thì X thắng. Quan trọng vì xác suất đối thủ cầm bài trong một khoảng bằng đúng độ dài khoảng đó, nên kỳ vọng tính được bằng cộng độ dài khoảng nhân với số bet thắng thua.
- **Full-street và half-street:** half-street là vòng cược chỉ một người được bet (người kia buộc phải check trước); full-street là vòng cược đầy đủ, X hành động trước (check hoặc bet), rồi Y hành động. Ví dụ: trò chơi số 1 của Chương 11 là half-street; trò chơi số 4 tới số 8 ở đây đều là full-street. Quan trọng vì full-street cho Y lợi thế vị trí và cho X các lựa chọn bet, check-call, check-raise.
- **Luật không bỏ bài (no-fold):** không người nào được fold trước một bet. Ví dụ: Y bet thì X buộc phải call dù cầm bài 0,99. Quan trọng vì nó mô phỏng pot cực lớn (bỏ bài gần như luôn sai) và loại bỏ bluff, để chương tập trung vào value bet.
- **Ngưỡng (threshold) và cách đặt tên:** điểm trên [0, 1] tách hai hành động. xₙ (hoặc yₙ) là ngưỡng giữa các tay bỏ bet thứ n và các tay chỉ bỏ tới bet thứ n − 1. Ví dụ: trong trò chơi số 5, y₂ = 1/4 nghĩa là Y raise (bỏ bet thứ hai) với bài tốt hơn 1/4 và chỉ call với bài tệ hơn. Quan trọng vì lời giải của mỗi trò chơi chỉ là danh sách các ngưỡng.
- **Phương trình bàng quan (indifference equation):** tại ngưỡng của một người, người đó phải được kỳ vọng như nhau cho hai hành động hai bên ngưỡng; nếu không, dịch ngưỡng sẽ có lợi. Ví dụ: tại y₂ của trò chơi số 5, Y raise hay call cùng kỳ vọng khi y₂ − (x₁ − y₂) = 0, tức y₂ = x₁/2. Quan trọng vì mỗi ngưỡng cho một phương trình, và hệ phương trình cho lời giải tối ưu.
- **Bảng chênh lệch kỳ vọng:** để viết phương trình bàng quan, sách liệt kê các khoảng bài của đối thủ, ghi số bet thắng thua cho mỗi hành động, lấy hiệu và nhân với độ dài khoảng. Ví dụ: tại x₁ của trò chơi số 5, chỉ hai khoảng có hiệu khác 0: [0, y₂] (hiệu +1) và [y₁, 1] (hiệu −1), nên y₂ − (1 − y₁) = 0. Quan trọng vì đây là công cụ tính toán chính của cả chương.
- **Kỳ vọng ex-showdown (ex-showdown expectation):** kỳ vọng chỉ tính số bet thắng thua trên vòng cược đang xét, không tính phần pot có sẵn. Ví dụ: X bet, Y call, X thắng thì X được +1, dù pot thực có thể lớn hơn nhiều. Quan trọng vì với luật không bỏ bài, phần pot chia theo bài và không phụ thuộc chiến lược, nên chỉ phần ex-showdown cần tối ưu.
- **Value bet và raise for value:** bet hoặc raise với hy vọng bị call bởi bài yếu hơn. Ví dụ: Y cầm 0,10 raise khi X bet trong trò chơi số 5, vì X bet với [0; 0,5] và Y thắng phần lớn các tay đó. Quan trọng vì trong trò chơi không bỏ bài mọi bet đều là value bet.
- **Check-raise:** check rồi raise khi đối thủ bet. Ví dụ: trong trò chơi số 7, X check-raise với [0; 1/9]. Quan trọng vì quyền check-raise buộc Y bet chặt hơn sau khi X check.
- **Tỷ lệ raise R:** tỷ lệ giữa độ rộng vùng bài người sau bỏ bet tiếp theo và độ rộng vùng bài người trước đã bỏ bet. Ví dụ: y₂ = R·x₁; R = 1/2 khi không thể bị raise lại; R = √2 − 1 khi raise không giới hạn. Quan trọng vì nó trả lời câu hỏi "nên raise bao thường xuyên".
- **Tỷ lệ vàng của poker (golden mean of poker) r = √2 − 1 ≈ 0,4142:** hằng số Chương 14 đặt tên, là nghiệm dương của r² + 2r − 1 = 0, thoả r² = 1 − 2r và 1 + r = √2. Ví dụ: r/(1 − r) = 1/√2 ≈ 0,7071 là ngưỡng y₁ của trò chơi số 8. Quan trọng vì nó xuất hiện ở mọi trò chơi có raise không giới hạn.
- **Giá trị trò chơi (game value):** kỳ vọng của một người khi cả hai chơi tối ưu. Ví dụ: trò chơi số 4 có giá trị 0; trò chơi số 5 có giá trị 1/8 bet cho Y (người tổng hợp tính). Quan trọng vì nó đo lợi thế vị trí; Chương 18 phân tích kỹ.
- **Phương trình sai phân (difference equation):** phương trình liên hệ các số hạng liên tiếp của một dãy. Ví dụ: y_{k+2} + 2y_{k+1} − y_k = 0 cho phép tính y₃ từ y₁, y₂: y₃ = y₁ − 2y₂ = 0,7071 − 0,5858 = 0,1213. Quan trọng vì đây là cách duy nhất xử lý vô số ngưỡng.
- **Phương trình đặc trưng, nghiệm thuần nhất và nghiệm riêng:** với y_{n+2} + c·y_{n+1} + d·yₙ = 0, thử yₙ = λⁿ được λ² + cλ + d = 0; nghiệm tổng quát là a·pⁿ + b·qⁿ. Nếu vế phải khác 0 (không thuần nhất), cộng thêm một nghiệm riêng. Ví dụ: x² + 2x − 1 = 0 cho r và −1 − √2. Quan trọng vì đây là kỹ thuật của Phụ lục.

## Nội dung chi tiết

### 1. Phần mở đầu chương (trang 183)

Ở Chương 15, tác giả đã giải trò chơi full-street đầu tiên, trong đó cả hai người chơi đều có quyền bet, trên trò chơi AKQ. Chương này quay lại trò chơi đã xét khi bắt đầu nghiên cứu các trò chơi half-street: trò chơi [0,1]. Đây là một trong những trò chơi quan trọng nhất của sách vì nó gần với poker nhất, chủ yếu do có rất nhiều loại bài và người chơi buộc phải dùng các vùng cược (betting regions) — mỗi hành động được thực hiện với cả một khoảng bài.

Trong toàn chương, mọi trò chơi đều có một luật đặc biệt đã gặp ở Chương 11: **không người nào được bỏ bài**. Luật này xấp xỉ việc chơi khi pot cực lớn. Hệ quả là không chiến lược nào sau đây có bluff; bluff không có ích vì đối thủ không có cơ hội bỏ bài. Tác giả in nghiêng câu tóm tắt: **trò chơi không bỏ bài là bài tập rút đúng lượng giá trị từ bài mạnh**.

Quy ước của trò chơi [0,1] (nhắc lại từ Chương 11): mỗi người nhận một số phân phối đều trên [0, 1]; số nhỏ hơn là bài tốt hơn; xác suất đối thủ cầm bài trong khoảng [a, b] bằng b − a. Mọi kỳ vọng tính theo đơn vị bet và là kỳ vọng ex-showdown.

### 2. Ví dụ 16.1 — Trò chơi [0,1] số 4: một bet, không raise (Example 16.1 [0,1] Game #4, trang 183–185)

**Luật.** Một vòng full-street. Không ai được bỏ bài. Chỉ được một bet (không raise). Mỗi người có đúng một quyết định: X quyết định bet với tay nào; Y quyết định bet với tay nào nếu X check. Ai bet thì người kia phải call. Có ba chuỗi hành động: X bet rồi Y call; X check, Y bet, X call; X check rồi Y check. Tác giả khuyên người đọc tự đoán chiến lược tối ưu trước khi đọc lời giải để rèn trực giác.

**Lời giải trực giác.** X sẽ bet ít nhất một phần thời gian. Khi bet, X không bao giờ bet một tay yếu hơn một tay mình check, vì Y không bao giờ bỏ bài (bet tay yếu chỉ thua thêm). Nếu X check, Y có thể bet mọi tay mà X lẽ ra đã bet (X đã check nên Y chắc chắn thắng với những tay đó), và thêm nửa mạnh hơn của các tay còn lại. Nếu bài của X nằm trong nửa mạnh đó, Y hoà vốn trung bình trên các lần X call; nếu bài của X nằm ở nửa dưới, Y thắng một bet. Tóm lại chiến lược của Y: nếu X bet, Y buộc phải call; nếu X check, Y bet mọi tay X lẽ ra đã bet và nửa tốt hơn của các tay X check.

Vì Y chỉ kiếm được giá trị khi bet sau khi X check (mọi hành động khác của Y đều bị ép), X chặn được việc bị khai thác bằng cách **bet mọi tay**. Khi đó trò chơi có kỳ vọng bằng nhau cho cả hai (luôn đúng một bet vào pot). Chiến lược tối ưu: X bet mọi tay, Y call mọi tay.

**Lời giải bằng ngưỡng.** Tác giả tham số hoá: có ngưỡng x₁ sao cho X bet với bài tốt hơn x₁ (nhỏ hơn x₁) và check với bài tệ hơn; có ngưỡng y₁ sao cho Y bet với bài tốt hơn y₁ nếu X check, check với bài tệ hơn. Để chiến lược của X tối ưu, X phải làm cho Y không thể đơn phương tăng kỳ vọng bằng cách dịch y₁, và ngược lại. Như vậy mỗi người muốn đối thủ **bàng quan** giữa hai hành động hai bên mỗi ngưỡng của đối thủ — tức hai hành động có cùng kỳ vọng. Ta viết một phương trình bàng quan cho mỗi ngưỡng.

*Bàng quan tại y₁* (Y cầm bài đúng bằng y₁, cân nhắc bet hay check sau khi X check). Kỳ vọng của Y theo bài của X:

| Bài của X | Xác suất | Y bet | Tích | Y check | Tích |
|---|---|---|---|---|---|
| [0, x₁] | x₁ | không xảy ra (X đã bet) | — | — | — |
| [x₁, y₁] | y₁ − x₁ | −1 | x₁ − y₁ | 0 | 0 |
| [y₁, 1] | 1 − y₁ | +1 | 1 − y₁ | 0 | 0 |
| **Tổng** | | | **x₁ − 2y₁ + 1** | | **0** |

Như ở Ví dụ 11.3 của Chương 11, ta cộng cột "Tích" và cho hai kỳ vọng bằng nhau: 0 = x₁ − 2y₁ + 1, tức **2y₁ = x₁ + 1**.

*Bàng quan tại x₁* (X cầm bài đúng bằng x₁, cân nhắc bet hay check). Bảng dưới đây ghi kỳ vọng của X theo bài của Y (sách ghi nhầm tiêu đề cột và dấu ô đầu, xem khối Lưu ý):

| Bài của Y | Xác suất | X bet | Tích | X check | Tích |
|---|---|---|---|---|---|
| [0, x₁] | x₁ | −1 | −x₁ | −1 (Y bet, X call, thua) | −x₁ |
| [x₁, y₁] | y₁ − x₁ | +1 | y₁ − x₁ | +1 (Y bet, X call, thắng) | y₁ − x₁ |
| [y₁, 1] | 1 − y₁ | +1 | 1 − y₁ | 0 (Y check) | 0 |
| **Tổng** | | | **1 − 2x₁** | | **y₁ − 2x₁** |

Cho hai tổng bằng nhau: 1 − 2x₁ = y₁ − 2x₁, nên **y₁ = 1**. Thế vào 2y₁ = x₁ + 1: 2 = x₁ + 1, nên **x₁ = 1**. Đây đúng là đáp án trực giác: cả x₁ và y₁ nằm ở 1, X bet mọi tay, Y không bao giờ có cơ hội bet mà chỉ call.

### 3. Ví dụ 16.2 — Trò chơi [0,1] số 5: hai bet, không check-raise (Example 16.2 [0,1] Game #5, trang 185–188)

**Luật.** Một vòng full-street; còn hai bet; X không được check-raise; không ai được bỏ bài. Trò chơi này giới thiệu khái niệm raise for value (raise để lấy giá trị).

Ký hiệu mới: y₂ là ngưỡng giữa bet (call) và raise của Y. Không có x₂, vì X không được check-raise nên không có chuỗi hành động nào để X bỏ bet thứ hai vào pot. Khi X bet, Y sẽ raise với một phần các tay X bet. Ở trò chơi số 4, X chặn được Y bằng cách bet mọi tay; ở đây cách đó không còn tốt, vì Y có quyền raise và với những tay tệ nhất, X có lợi hơn nếu check rồi call thay vì bet.

**Tham số hoá:** 0 < y₂ < x₁ < y₁ < 1. Nghĩa là X bet một số tay; Y raise với ít tay hơn số đó; nếu X check, Y bet với nhiều tay hơn số tay X đã bet.

**Hình 16.1 (cấu trúc chiến lược của trò chơi số 5)** vẽ hai cột trên trục giá trị bài từ 0 (nuts) tới 1. Cột X: BET từ 0 tới x₁ (khoảng 0,5), CHECK từ x₁ tới 1. Cột Y: RAISE từ 0 tới y₂ (khoảng 0,25), BET từ y₂ tới y₁ (khoảng 0,75), CALL từ y₁ tới 1. Cách đọc đầy đủ: nếu X bet, Y raise trên [0, y₂] và call phần còn lại; nếu X check, Y bet trên [0, y₁] và check trên [y₁, 1].

Từ ví dụ này, sách rút gọn bảng: mỗi dòng chỉ ghi **hiệu** kỳ vọng giữa hai hành động, rồi cho tổng các hiệu (nhân với độ dài khoảng) bằng 0.

*Tại y₂ (Y call hay raise khi X bet).* X bet với [0, x₁]:

| Bài của X | Y call | Y raise | Hiệu (call − raise) | Tích |
|---|---|---|---|---|
| [0, y₂] | −1 | −2 | +1 | y₂ |
| [y₂, x₁] | +1 | +2 | −1 | −(x₁ − y₂) |
| **Tổng** | | | | **2y₂ − x₁** |

Kỳ vọng của Y khi call và khi raise phải bằng nhau (nguyên lý bàng quan); độ dài các khoảng [0, y₂] và [y₂, x₁] là xác suất vì bài được rút từ phân phối đều. Vậy 2y₂ − x₁ = 0, tức **y₂ = x₁/2**: Y raise với một nửa số tay X bet. Lý do giống ở trò chơi half-street: trong trò chơi không bỏ bài, nếu X cầm một tập tay bài nào đó và Y được bỏ thêm đúng một bet mà X phải call, thì dù đó là bet thứ nhất hay thứ hai, Y bỏ bet đó với một nửa số tay X có thể cầm.

Ngay cả khi X có thể reraise, trong các trò chơi không bỏ bài vẫn có một tỷ lệ cố định giữa các tay X có thể cầm và các tay Y dùng để bỏ bet tiếp. Sách gọi tỷ lệ đó là R:

```text
y₂ = R·x₁
```

R là tỷ lệ các tay value bet của X mà Y nên raise. Ở đây R = 1/2 vì X không reraise được. Thực ra điều này luôn đúng với bet cuối cùng: khi một người không thể bị raise lại và người kia không thể bỏ bài, R = 1/2.

*Tại x₁ (X check-call hay bet).* Bet khiến X có thể bị raise, nên X buộc phải bet với một phân phối tay hẹp hơn:

| Bài của Y | X check-call | X bet | Hiệu (check-call − bet) | Tích |
|---|---|---|---|---|
| [0, y₂] | −1 | −2 (Y raise) | +1 | y₂ |
| [y₂, x₁] | −1 | −1 | 0 | 0 |
| [x₁, y₁] | +1 (Y bet, X call) | +1 | 0 | 0 |
| [y₁, 1] | 0 (Y check) | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **y₂ − 1 + y₁** |

(Sách ghi dòng [x₁, y₁] là −1 và −1; với X cầm đúng x₁, bài Y trong [x₁, y₁] yếu hơn nên đúng ra là +1 và +1; hiệu vẫn bằng 0 nên tổng không đổi.) Phương trình không chứa x nào: **y₂ = 1 − y₁**, nghĩa là vùng raise của Y phải rộng bằng vùng Y check sau khi X check.

*Tại y₁ (Y check hay bet sau khi X check).* Đây là mẫu quen thuộc: Y bet sau khi X check với một nửa số tay X check:

| Bài của X | Y check | Y bet | Hiệu (check − bet) | Tích |
|---|---|---|---|---|
| [0, x₁] | không xảy ra | — | — | — |
| [x₁, y₁] | 0 | −1 | +1 | y₁ − x₁ |
| [y₁, 1] | 0 | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **2y₁ − x₁ − 1** |

Nên 2y₁ − x₁ − 1 = 0, tức **y₁ = (1 + x₁)/2**.

**Giải hệ ba phương trình** y₂ = R·x₁, y₂ = 1 − y₁, y₁ = (1 + x₁)/2: cho hai biểu thức của y₂ bằng nhau và thế y₁:

```text
R·x₁ = 1 − (1 + x₁)/2
2R·x₁ = 1 − x₁
x₁ = 1/(1 + 2R)
```

Với R = 1/2: **x₁ = 1/2, y₂ = 1/4, y₁ = 3/4.**

**Kiểm tra lời giải.** Ta xem có người nào cải thiện được bằng cách chơi khác trước chiến lược tối ưu của đối thủ. Xét X cầm bài x trong [0, 1/4]; X chọn giữa check-call và bet. Tính kỳ vọng **của Y**:

- Nếu X bet: Y tốt hơn x (xác suất x) thì Y raise, X thua hai bet; Y tệ hơn x nhưng tốt hơn 1/4 (xác suất 1/4 − x) thì Y raise, X thắng hai bet; Y tệ hơn 1/4 (xác suất 3/4) thì Y call, X thắng một bet. Kỳ vọng của Y: (x)(2) + (1/4 − x)(−2) + (3/4)(−1) = 4x − 5/4.
- Nếu X check: Y tốt hơn x (xác suất x): Y bet, X call, X thua một bet; Y trong (x, 1/4) (xác suất 1/4 − x): X thắng một bet; Y trong (1/4, 3/4) (xác suất 1/2): Y vẫn bet, X thắng một bet; Y tệ hơn 3/4 (xác suất 1/4): Y check, 0. Kỳ vọng của Y: (x)(1) + (1/4 − x)(−1) + (1/2)(−1) = 2x − 3/4.

Kỳ vọng của Y khi X check lớn hơn khi X bet khi 2x − 3/4 > 4x − 5/4, tức x < 1/4. Vậy với mọi tay của X trong [0, 1/4], bet cho X kỳ vọng cao hơn check, nên X không cải thiện được bằng cách đổi chiến lược. Có thể kiểm tra tiếp mọi vùng khác, nhưng vì các chiến lược này tối ưu nên không có cơ hội cải thiện đơn phương nào.

**Giá trị trò chơi.** Phần trên chạm tới một khái niệm quan trọng: **giá trị trò chơi** (game value). Trò chơi này có giá trị dương cho Y nhờ lợi thế vị trí; Chương 18 sẽ bàn kỹ và so sánh giá trị của các loại trò chơi. Sách không ghi con số; người tổng hợp tính kỳ vọng của Y khi cả hai chơi tối ưu bằng cách tích phân theo bài x của X:

```text
X bet, x trong [0, 1/4]:      kỳ vọng của Y là 4x − 5/4;   tích phân = 1/8 − 5/16 = −3/16
X bet, x trong [1/4, 1/2]:    kỳ vọng của Y là (x + 1/4) − (1 − x) = 2x − 3/4;  tích phân = 0
X check, x trong [1/2, 3/4]:  kỳ vọng của Y là x − (3/4 − x) = 2x − 3/4;  tích phân = 1/8
X check, x trong [3/4, 1]:    kỳ vọng của Y là 3/4;  tích phân = 3/16
Tổng: −3/16 + 0 + 1/8 + 3/16 = 1/8
```

Vậy Y lời 1/8 bet mỗi ván (kiểm lại bằng lưới số 2.000 × 2.000 điểm cho 0,1245). So sánh: ở trò chơi số 4, giá trị bằng 0 vì X bet mọi tay; ở trò chơi số 1 của Chương 11 (half-street, chỉ Y được bet), Y lời 1/4 bet.

### 4. Ví dụ 16.3 — Trò chơi [0,1] số 6: trò chơi raise (Example 16.3 [0,1] Game #6 – The Raising Game, trang 188–191)

**Luật.** Một vòng full-street; được raise và reraise không giới hạn, stack lớn tuỳ ý; không check-raise; không ai được bỏ bài. Trò chơi giống trò chơi số 5 nhưng số bet có thể tăng mãi; tất nhiên trong chiến lược tối ưu, đến một lúc một người sẽ dừng raise và call.

**Các ngưỡng.** x₁ là ngưỡng X bàng quan giữa check và bet. Vì không có check-raise, khi X check chỉ còn một ngưỡng y₁, và từ trò chơi trước ta biết y₁ nằm giữa x₁ và 1 (đây là bet cuối, X không raise được). Ta cũng biết X không bao giờ "bluff" bằng cách bỏ bet thứ n với một tay yếu hơn một tay không bỏ bet đó. Khi X bet thì có một dãy vô hạn ngưỡng: y₂ (giữa Y raise và Y call), bên trái y₂ là x₃ (X reraise), bên trái x₃ là y₄ (Y bỏ bet thứ tư), và cứ thế:

```text
0 < y₂ₙ < x₂ₙ₋₁ < … < y₂ < x₁ < y₁ < 1
```

**Hình 16.2 (cấu trúc chiến lược trò chơi số 6)**: cột X gồm RERAISE từ 0 tới x₃ (khoảng 0,09), BET từ x₃ tới x₁ (khoảng 0,55), CHECK từ x₁ tới 1; cột Y gồm (từ dưới lên) một vùng nhỏ dưới y₄, RAISE từ y₄ tới y₂ (khoảng 0,23), BET từ y₂ tới y₁ (khoảng 0,77), CALL trên y₁. Các vị trí đọc từ trục là ước lượng và khớp với lời giải.

**Tính "đối xứng" của trò chơi.** Khi X bet, Y raise với một tỷ lệ R các tay của X: y₂ = R·x₁ như trước, nhưng R không còn là 1/2 vì X có thể reraise. Khi Y đã raise, Y cầm bài trong [0, R·x₁]. Lúc này X muốn reraise với một phần các tay Y đã raise — tình huống của X giống hệt tình huống của Y ở bet trước: đối thủ có một khoảng bài, mình muốn raise. Vậy X raise với cùng tỷ lệ R: x₃ = R·y₂. Rồi Y đứng trước bet của X và raise với R các tay của X, và cứ thế. Tổng quát, với n > 1:

```text
yₙ = R·xₙ₋₁   (y₃, y₅, … không tồn tại)
xₙ = R·yₙ₋₁   (x₂, x₄, … không tồn tại)
```

Sách gọi đây là "trò chơi raise" vì nó trả lời một câu hỏi thường gặp: **"nên raise đối thủ bao thường xuyên nếu đối thủ có thể reraise và không ai được bỏ bài?"** Giải ra R là có câu trả lời.

**Khi X check.** Y bet với mọi tay tốt hơn x₁ và một nửa số tay tệ hơn x₁: y₁ = (1 + x₁)/2. Phương trình bàng quan tại x₁ cũng giữ nguyên như trò chơi trước (vì không có check-raise), cho vùng raise của Y rộng bằng vùng check: y₂ = 1 − y₁. Thế vào:

```text
y₂ = 1 − (1 + x₁)/2
2R·x₁ = 2 − 1 − x₁
x₁ = 1/(2R + 1)
```

Từ đó mọi ngưỡng y₂, x₃, y₄, … tính được theo R bằng cách nhân thêm R đủ số lần; y₁ cũng tính được theo R.

**Tìm R: bàng quan của Y tại y₂ (raise hay call).**

| Bài của X | Y raise | Y call | Hiệu (call − raise) | Tích |
|---|---|---|---|---|
| [0, x₃] | −3 (X reraise, Y call) | −1 | +2 | 2x₃ |
| [x₃, y₂] | −2 | −1 | +1 | y₂ − x₃ |
| [y₂, x₁] | +2 | +1 | −1 | −(x₁ − y₂) |
| **Tổng** | | | | **x₃ + 2y₂ − x₁** |

Phương trình x₃ + 2y₂ − x₁ = 0 liên hệ ba ngưỡng. Viết mọi thứ theo R và x₁ (x₃ = R²x₁, y₂ = Rx₁):

```text
R²x₁ + 2Rx₁ − x₁ = 0
R² + 2R − 1 = 0
R = √2 − 1   (nghiệm dương; nghiệm kia −1 − √2 âm)
```

Đây lại là √2 − 1, hằng số mà Chương 14 đặt tên "tỷ lệ vàng của poker" (Phương trình 14.1: r = √2 − 1). Nó xuất hiện như câu trả lời cho câu hỏi "nên raise đối thủ không thể bỏ bài nhưng có thể raise lại bao thường xuyên?".

**Lời giải** (r = √2 − 1 ≈ 0,41421; người tổng hợp đã tính lại mọi giá trị):

| Ngưỡng | Công thức | Giá trị |
|---|---|---|
| x₁ | 1/(1 + 2r) | 0,5469 |
| y₁ | (1/(1 + 2r) + 1)/2 = (1 + r)/(1 + 2r) | 0,7735 |
| y₂ | r/(1 + 2r) | 0,2265 |
| x₃ | r²/(1 + 2r) | 0,0938 |
| y₄ | r³/(1 + 2r) | 0,0389 (người tổng hợp tính) |
| yₙ, n chẵn > 1 | rⁿ⁻¹/(1 + 2r) | |
| xₙ, n lẻ > 2 | rⁿ⁻¹/(1 + 2r) | |

Kiểm tra: y₂ + y₁ = 0,2265 + 0,7735 = 1, đúng điều kiện y₂ = 1 − y₁; x₃ + 2y₂ − x₁ = 0,0938 + 0,4531 − 0,5469 = 0. Trò chơi tiếp theo cho X thêm một lựa chọn: check-raise.

### 5. Ví dụ 16.4 — Trò chơi [0,1] số 7: hai bet, có check-raise (Example 16.4 [0,1] Game #7, trang 191–194)

**Luật.** Một vòng full-street; còn hai bet; được check-raise; không được bỏ bài.

Ở trò chơi số 5 không có ngưỡng x₂ vì không chuỗi hành động nào cho X bỏ bet thứ hai. Khi cho X quyền check-raise, ta có cùng trò chơi nhưng thêm một ngưỡng cần giải. Điểm then chốt là xác định X check-raise với tay nào. Hiển nhiên X chỉ muốn bỏ bet thứ hai với tay tốt hơn y₁ (tay tệ hơn sẽ mất giá trị khi check-raise), và X không bỏ bet thứ hai với tay yếu hơn tay bỏ bet thứ nhất (đã chứng minh là bị trội). Theo trực giác X muốn tự mình bỏ hai bet với các tay mạnh nhất; thực ra các chiến lược của X đều đồng tối ưu (co-optimal) miễn là X chọn đúng **độ rộng** vùng check-raise trong các tay tốt hơn y₂. Để đơn giản, và vì cách này tiện khi có nhiều bet hơn, sách tham số hoá:

```text
0 < x₂ < y₂ < x₁ < y₁ < 1
```

**Hình 16.3 (cấu trúc chiến lược trò chơi số 7)** và chiến lược tương ứng:

- X: check rồi raise nếu Y bet, trên [0, x₂]; bet for value trên [x₂, x₁]; check rồi call trên [x₁, 1].
- Y khi X bet: raise for value trên [0, y₂]; call trên [y₂, 1].
- Y khi X check: bet for value trên [0, y₁]; check trên [y₁, 1].

(Hình vẽ các ngưỡng của Y ở vị trí khoảng 0,77 và 0,22, không đúng với lời giải 2/3 và 1/3; xem khối Lưu ý.)

**Bốn phương trình bàng quan.**

*X tại x₂ (check-raise hay bet):*

| Bài của Y | X check-raise | X bet | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₂] | −2 | −2 (Y raise) | 0 | 0 |
| [y₂, y₁] | +2 (Y bet, X raise, Y call) | +1 | +1 | y₁ − y₂ |
| [y₁, 1] | 0 (Y check) | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **2y₁ − y₂ − 1** |

Nên **y₂ = 2y₁ − 1**.

*Y tại y₂ (raise hay call khi X bet):* X bet với [x₂, x₁].

| Bài của X | Y raise | Y call | Hiệu (call − raise) | Tích |
|---|---|---|---|---|
| [0, x₂] | không xảy ra (X check) | — | — | — |
| [x₂, y₂] | −2 | −1 | +1 | y₂ − x₂ |
| [y₂, x₁] | +2 | +1 | −1 | −(x₁ − y₂) |
| [x₁, 1] | không xảy ra | — | — | — |
| **Tổng** | | | | **2y₂ − x₁ − x₂** |

Nên **y₂ = (x₁ + x₂)/2**: Y raise với nửa tốt hơn của vùng bet [x₂, x₁] của X.

*X tại x₁ (check-call hay bet):*

| Bài của Y | X check-call | X bet | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₂] | −1 | −2 | +1 | y₂ |
| [y₂, y₁] | ±1 (như nhau) | ±1 | 0 | 0 |
| [y₁, 1] | 0 | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **y₂ − 1 + y₁** |

Nên **y₂ = 1 − y₁**.

*Y tại y₁ (check hay bet khi X check)* — bảng đã sửa dấu (sách in nhầm, xem khối Lưu ý). X check với [0, x₂] (để check-raise) và [x₁, 1] (để check-call):

| Bài của X | Y check | Y bet | Hiệu (check − bet) | Tích |
|---|---|---|---|---|
| [0, x₂] | 0 | −2 (X check-raise, Y call) | +2 | 2x₂ |
| [x₂, x₁] | không xảy ra (X bet) | — | — | — |
| [x₁, y₁] | 0 | −1 | +1 | y₁ − x₁ |
| [y₁, 1] | 0 | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **2x₂ + 2y₁ − x₁ − 1** |

Nên **2y₁ = 1 + x₁ − 2x₂**.

**Giải hệ.** Từ y₂ = 2y₁ − 1 và y₂ = 1 − y₁: 2y₁ − 1 = 1 − y₁, nên y₁ = 2/3 và y₂ = 1/3. Thế vào hai phương trình còn lại:

```text
4/3 = 1 + x₁ − 2x₂
1/3 = (x₁ + x₂)/2   →   x₁ = 2/3 − x₂
4/3 = 1 + 2/3 − 3x₂   →   3x₂ = 1/3   →   x₂ = 1/9
x₁ = 2/3 − 1/9 = 5/9
```

**Lời giải: x₁ = 5/9, y₁ = 2/3, x₂ = 1/9, y₂ = 1/3.** Người tổng hợp kiểm cả bốn phương trình: 2·(2/3) − 1/3 − 1 = 0; 2·(1/3) − 5/9 − 1/9 = 0; 1/3 − 1 + 2/3 = 0; 2/9 + 4/3 − 5/9 − 1 = 0.

**So sánh với trò chơi số 5.** Trước khi nhìn số, tác giả dự đoán: thứ nhất, Y sẽ bet ít tay hơn khi X check, vì ở trò chơi số 5 bet của Y chỉ đặt rủi ro một bet, còn ở trò chơi số 7 bet của Y đặt rủi ro thêm bet thứ hai do X đôi khi check-raise. Điều này lại gây khó cho X: ở trò chơi số 5, X check-call với các tay hơi tệ hơn 1/2 và kiếm giá trị check-call vì Y bet cả những tay yếu tới 3/4; nay Y không còn value bet những tay trung bình đó, nên các tay này của X mất một phần giá trị, và X có lẽ sẽ bet thêm các tay tệ hơn 1/2. Đến lượt mình, điều này cho Y nới ngưỡng raise vì hai lẽ: X đang check một số tay mạnh nhất nên Y không phải sợ X cầm chúng khi X bet; và X đang bet thêm các tay trung bình quanh 1/2. Vậy Y raise for value được với tay hơi yếu hơn so với trò chơi số 5. Lời giải xác nhận cả ba dự đoán:

| Ngưỡng | Trò chơi số 5 | Trò chơi số 7 |
|---|---|---|
| x₁ | 1/2 | 5/9 ≈ 0,556 |
| y₁ | 3/4 | 2/3 ≈ 0,667 |
| y₂ | 1/4 | 1/3 ≈ 0,333 |

Trò chơi cuối cùng là bản tương tự của trò chơi số 6 khi có check-raise; có thể coi đó là trò chơi [0,1] một vòng không bỏ bài đầy đủ.

### 6. Ví dụ 16.5 — Trò chơi [0,1] số 8: trò chơi raise có check-raise (Example 16.5 [0,1] Game #8: The Raising Game with Check-Raise, trang 194–200)

**Luật.** Một vòng full-street; raise và reraise không giới hạn, stack lớn tuỳ ý; được check-raise; không ai được bỏ bài. Cả hai người được bỏ bao nhiêu raise tuỳ theo bài, và X được check-raise. Như trò chơi số 6, có vô số ngưỡng nên không thể viết hết các phương trình bàng quan; thay vào đó ta lập một quan hệ truy hồi cho các phương trình bậc cao và giải nó.

**Tham số hoá:** với mọi số nguyên dương n, 0 < xₙ₊₁ < yₙ₊₁ < xₙ < yₙ < 1.

**Hình 16.4 (cấu trúc chiến lược trò chơi số 8)**: cột X, từ dưới lên, gồm một vùng dưới x₄, BET-RAISE (bet rồi reraise) [x₄, x₃], CHECK-RAISE [x₃, x₂], BET [x₂, x₁], CHECK [x₁, 1]; cột Y gồm (dưới y₄, ghi "etc."), RAISE [y₄, y₃], RAISE [y₃, y₂], BET [y₂, y₁], CALL trên y₁. Hình là sơ đồ, các vị trí không theo tỷ lệ của lời giải.

Cách đọc: X luân phiên giữa các vùng "mở bằng check" ([x₁, 1] để call, [x₃, x₂] để check-raise, [x₅, x₄] để check-raise rồi raise tiếp, …) và "mở bằng bet" ([x₂, x₁], [x₄, x₃], …). Ngưỡng xₙ ứng với tay bài bỏ bet thứ n trong chuỗi cược của X; yₙ ứng với tay bài bỏ bet thứ n của Y.

#### 6a. Chiến lược của Y: phương trình bàng quan tại các ngưỡng của X

*Tại x₁:* giống trò chơi số 6, **y₂ = 1 − y₁**.

*Tại x₂ (X check-raise hay bet).* Người tổng hợp viết bảng đầy đủ (sách bỏ các khoảng có hiệu bằng 0). Nhớ y₃ < x₂ < y₂. Khi X check-raise: Y bet (nếu bài tốt hơn y₁), X raise, Y bỏ bet thứ ba nếu bài tốt hơn y₃, X (ở x₂) call.

| Bài của Y | X check-raise | X bet | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₃] | −3 | −2 (Y raise, X call) | −1 | −y₃ |
| [y₃, x₂] | −2 | −2 | 0 | 0 |
| [x₂, y₂] | +2 | +2 | 0 | 0 |
| [y₂, y₁] | +2 | +1 | +1 | y₁ − y₂ |
| [y₁, 1] | 0 | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **−y₃ + 2y₁ − y₂ − 1** |

Nên **y₃ + y₂ + 1 = 2y₁**. Thế y₂ = 1 − y₁: y₃ + (1 − y₁) + 1 = 2y₁, tức **y₃ + 2 = 3y₁** (sách in nhầm "2y₁").

*Tại x₃ (X bet rồi reraise, hay check-raise).* Nhớ y₄ < x₃ < y₃. Bet-reraise: X bet, Y raise nếu tốt hơn y₂, X bỏ bet thứ ba, Y bỏ bet thứ tư nếu tốt hơn y₄, X call. Check-raise: Y bet nếu tốt hơn y₁, X raise, Y bỏ bet thứ ba nếu tốt hơn y₃, X call.

| Bài của Y | X bet-reraise | X check-raise | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₄] | −4 | −3 | −1 | −y₄ |
| [y₄, x₃] | −3 | −3 | 0 | 0 |
| [x₃, y₃] | +3 | +3 | 0 | 0 |
| [y₃, y₂] | +3 | +2 | +1 | y₂ − y₃ |
| [y₂, y₁] | +1 | +2 | −1 | −(y₁ − y₂) |
| [y₁, 1] | +1 | 0 | +1 | 1 − y₁ |
| **Tổng** | | | | **−y₄ − y₃ + 2y₂ − 2y₁ + 1** |

Nên −y₄ − y₃ + 2y₂ − 2y₁ + 1 = 0, viết lại: **y₄ + (y₁ − y₂) = (y₂ − y₃) + (1 − y₁)**.

*Tại x₄ (check-raise rồi raise tiếp, hay bet rồi reraise).* Nhớ y₅ < x₄ < y₄.

| Bài của Y | X check-raise-reraise | X bet-reraise | Hiệu | Tích |
|---|---|---|---|---|
| [0, y₅] | −5 | −4 | −1 | −y₅ |
| [y₅, x₄] | −4 | −4 | 0 | 0 |
| [x₄, y₄] | +4 | +4 | 0 | 0 |
| [y₄, y₃] | +4 | +3 | +1 | y₃ − y₄ |
| [y₃, y₂] | +2 | +3 | −1 | −(y₂ − y₃) |
| [y₂, y₁] | +2 | +1 | +1 | y₁ − y₂ |
| [y₁, 1] | 0 | +1 | −1 | −(1 − y₁) |
| **Tổng** | | | | **−y₅ + 2y₃ − y₄ − 2y₂ + 2y₁ − 1** |

Viết lại: **(y₃ − y₄) + (y₁ − y₂) = y₅ + (y₂ − y₃) + (1 − y₁)**.

*Dạng tổng quát tại xₙ.* Khi n lẻ:

```text
yₙ₊₁ + (yₙ₋₂ − yₙ₋₁) + (yₙ₋₄ − yₙ₋₃) + … + (y₁ − y₂)
     = (yₙ₋₁ − yₙ) + (yₙ₋₃ − yₙ₋₂) + … + (1 − y₁)
```

Khi n chẵn:

```text
(yₙ₋₁ − yₙ) + (yₙ₋₃ − yₙ₋₂) + … + (y₁ − y₂)
     = yₙ₊₁ + (yₙ₋₂ − yₙ₋₁) + (yₙ₋₄ − yₙ₋₃) + … + (1 − y₁)
```

(Kiểm: n = 2 cho (y₁ − y₂) = y₃ + (1 − y₁), đúng là y₃ + y₂ + 1 = 2y₁; n = 3 và n = 4 cho đúng hai phương trình ở trên.)

*Lấy hiệu hai phương trình liên tiếp.* Với x₆ và x₇:

```text
(y₅ − y₆) + (y₃ − y₄) + (y₁ − y₂) = y₇ + (y₄ − y₅) + (y₂ − y₃) + (1 − y₁)
y₈ + (y₅ − y₆) + (y₃ − y₄) + (y₁ − y₂) = (y₆ − y₇) + (y₄ − y₅) + (y₂ − y₃) + (1 − y₁)
```

Lấy phương trình thứ nhất trừ phương trình thứ hai: vế trái còn −y₈, vế phải còn y₇ − (y₆ − y₇) = 2y₇ − y₆, nên y₈ = −2y₇ + y₆. Làm tương tự cho hai ngưỡng bất kỳ x_{k+1} và x_k:

```text
y_{k+2} + (y_{k−1} − y_k) + (y_{k−3} − y_{k−2}) + … + (y₁ − y₂)
      = (y_k − y_{k+1}) + (y_{k−2} − y_{k−1}) + (y_{k−4} − y_{k−3}) + … + (1 − y₁)
(y_{k−1} − y_k) + (y_{k−3} − y_{k−2}) + … + (y₁ − y₂)
      = y_{k+1} + (y_{k−2} − y_{k−1}) + (y_{k−4} − y_{k−3}) + … + (1 − y₁)
```

Trừ hai phương trình: y_{k+2} = −2y_{k+1} + y_k, tức

```text
y_{k+2} + 2y_{k+1} − y_k = 0          (16.1)
```

Phương trình loại này gọi là **phương trình sai phân** (difference equation); giải nó cần một kỹ thuật toán cao hơn một chút, được trình bày ở Phụ lục (mục 8 dưới đây). Nghiệm là

```text
yₙ = rⁿ/(1 − r)      với n ≥ 1
```

Đây là toàn bộ chiến lược của Y trong một công thức: y₁ = r/(1 − r) ≈ 0,7071 (sách in nhầm 1/(1 − r)), và Y bỏ bet thứ n + 1 với tỷ lệ r của các tay đã bỏ bet thứ n. So với trò chơi không check-raise (số 6): ở đó các thừa số r tách các ngưỡng xen kẽ từ X sang Y (yₙ = r·xₙ₋₁); ở đây các thừa số r tách mỗi ngưỡng của Y với ngưỡng kế tiếp của chính Y: **yₙ = r·yₙ₋₁**.

Người tổng hợp kiểm ba phương trình đầu bằng số: y₂ = 0,29289 và 1 − y₁ = 0,29289; y₃ + 2 = 2,12132 = 3y₁; y₄ + (y₁ − y₂) = 0,05025 + 0,41421 = 0,46447 và (y₂ − y₃) + (1 − y₁) = 0,17157 + 0,29289 = 0,46447.

#### 6b. Chiến lược của X: phương trình bàng quan tại các ngưỡng của Y

Chiến lược của X giải tương tự nhưng phức tạp hơn một chút. Chiến lược của Y không bị ảnh hưởng bởi các vùng ứng với ngưỡng có chỉ số thấp hơn nhiều; còn X ngay từ đầu đã luân phiên giữa check-raise và bet, và điều này ảnh hưởng tới cả ngưỡng thấp nhất y₁.

*Y tại y₁ (check hay bet khi X check).* X check với [x₁, 1] (để call) và các vùng [x₃, x₂], [x₅, x₄], … (để check-raise). Kỳ vọng của Y:

| Bài của X | Y check | Y bet |
|---|---|---|
| [y₁, 1] | 0 | +1 |
| [x₁, y₁] | 0 | −1 |
| [x₃, x₂] | 0 | −2 (X check-raise, Y ở y₁ call) |
| [x₅, x₄] | 0 | −2 |
| [x₇, x₆] | 0 | −2 |
| … | | |
| [x₂ₖ₊₁, x₂ₖ] | 0 | −2 |

(Khi X check-raise rồi raise tiếp, Y ở y₁ không bỏ thêm bet, nên chỉ mất 2.) Phương trình (k → ∞):

```text
1 − y₁ = (y₁ − x₁) + 2(x₂ − x₃) + 2(x₄ − x₅) + 2(x₆ − x₇) + … + 2(x₂ₖ − x₂ₖ₊₁)
```

Ở ngưỡng này, khi chọn giữa bet và check, Y thắng một bet khi X check vì bài yếu, nhưng mất hai bet mỗi khi X định check-raise.

*Y tại y₂ (raise hay call khi X bet).* X bet với [x₂, x₁], [x₄, x₃], …. Bảng (vùng sâu hơn ghi phần chênh lệch: Y raise thì X reraise, Y ở y₂ mất thêm 2 so với call):

| Bài của X | Y raise | Y call |
|---|---|---|
| [y₂, x₁] | +2 | +1 |
| [x₂, y₂] | −2 | −1 |
| [x₄, x₃] | 0 | −2 (tương đối: raise mất 3, call mất 1) |
| [x₆, x₅] | 0 | −2 |
| [x₈, x₇] | 0 | −2 |
| … | | |

```text
x₁ − y₂ = (y₂ − x₂) + 2(x₃ − x₄) + 2(x₅ − x₆) + 2(x₇ − x₈) + …
```

*Tổng quát tại yₙ:*

| Bài của X | Y raise | Y call |
|---|---|---|
| [yₙ, xₙ₋₁] | +2 | +1 |
| [xₙ, yₙ] | −2 | −1 |
| [xₙ₊₂, xₙ₊₁] | 0 | −2 |
| [xₙ₊₄, xₙ₊₃] | 0 | −2 |
| … | | |

```text
xₙ₋₁ − yₙ = (yₙ − xₙ) + 2(xₙ₊₁ − xₙ₊₂) + 2(xₙ₊₃ − xₙ₊₄) + …
```

Quay lại y₁: phương trình tại y₁ chính là dạng tổng quát này nếu định nghĩa **x₀ = 1**, điều hợp lý vì X không bao giờ bluff trong trò chơi mà Y không thể bỏ bài.

*Cộng hai phương trình liên tiếp.* Viết phương trình cho k và k + 1:

```text
x_{k−1} − y_k   = (y_k − x_k)         + 2(x_{k+1} − x_{k+2}) + 2(x_{k+3} − x_{k+4}) + …
x_k − y_{k+1}   = (y_{k+1} − x_{k+1}) + 2(x_{k+2} − x_{k+3}) + 2(x_{k+4} − x_{k+5}) + …
```

Cộng lại, các số hạng có chỉ số cao triệt tiêu nhờ dấu xen kẽ: 2[(x_{k+1} − x_{k+2}) + (x_{k+2} − x_{k+3}) + …] = 2x_{k+1} (vì xₙ → 0). Do đó:

```text
x_{k−1} − y_k + x_k − y_{k+1} = y_k − x_k + y_{k+1} + x_{k+1}
x_{k−1} + 2x_k − x_{k+1} = 2y_k + 2y_{k+1}
x_k + 2x_{k+1} − x_{k+2} = 2y_{k+1} + 2y_{k+2}       (dời chỉ số lên 1)
```

Thế yₙ = rⁿ/(1 − r), dùng r/(1 − r) = (√2 − 1)/(2 − √2) = 1/√2 và 1 + r = √2:

```text
x_k + 2x_{k+1} − x_{k+2} = 2r^{k+1}/(1 − r) + 2r^{k+2}/(1 − r)
                         = √2·r^k + √2·r^{k+1}
                         = √2·r^k(1 + r)
x_k + 2x_{k+1} − x_{k+2} = 2r^k                        (16.2)
```

Phương trình này cũng giải bằng kỹ thuật ở Phụ lục. Nghiệm cho chiến lược của X:

```text
xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2
```

**Lời giải trò chơi số 8:** xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2 và yₙ = rⁿ/(1 − r).

#### 6c. Đọc lời giải

Hai chiến lược tương phản thú vị. Chiến lược của Y khá đơn giản: các ngưỡng liên tiếp có quan hệ hàm mũ. Y bỏ bet đầu tiên khi X check với tay tốt hơn r/(1 − r) ≈ 0,7071, và sẵn sàng bỏ thêm một bet với mỗi lần nhân thêm r nếu X tiếp tục raise.

Mỗi ngưỡng của X nằm giữa hai ngưỡng của Y, bắt đầu với x₁ = 1 − r ≈ 0,5858. Nhưng các ngưỡng này không cách đều giữa các ngưỡng của Y. Sách nói các vùng check-raise của X hẹp hơn nhiều so với các vùng bet; trong công thức, điều này đến từ số hạng (−1)ⁿ. Giải thích trực giác: khi X cầm bài rất mạnh, X thường muốn bet vì chuỗi "bet rồi call" mang lại rất nhiều giá trị. Vì vậy các ngưỡng của X dao động trong quan hệ với các ngưỡng của Y.

**Bảng ngưỡng của trò chơi số 8** (sách in tới n = 5; người tổng hợp đã tính lại mọi giá trị, khớp sách):

| n | yₙ | xₙ | yₙ/xₙ |
|---|---|---|---|
| 0 | 1 (quy ước) | 1 (quy ước x₀ = 1) | 1 |
| 1 | 0,707107 | 0,585786 | r/(1 − r) + 1/2 ≈ 1,2071 |
| 2 | 0,292893 | 0,171573 | r/(1 − r) + 1 ≈ 1,7071 |
| 3 | 0,121320 | 0,100505 | r/(1 − r) + 1/2 ≈ 1,2071 |
| 4 | 0,050253 | 0,029437 | r/(1 − r) + 1 ≈ 1,7071 |
| 5 | 0,020815 | 0,017244 | r/(1 − r) + 1/2 ≈ 1,2071 |

Phần trong ngoặc vuông của xₙ bằng 2r khi n chẵn và 2(1 − r) khi n lẻ. Vậy **xₙ = rⁿ khi n chẵn và xₙ = rⁿ⁻¹(1 − r) khi n lẻ** (kiểm: x₂ = r² = 0,171573; x₃ = r²(1 − r) = 0,100505).

**Độ rộng các vùng check của X.**

```text
x₀ → x₁:   1 − (1 − r) = r
x₂ → x₃:   r² − r²(1 − r) = r²(1 − (1 − r)) = r³
x₄ → x₅:   r⁴ − r⁴(1 − r) = r⁵
x₂ₙ → x₂ₙ₊₁:  r²ⁿ − r²ⁿ(1 − r) = r²ⁿ⁺¹
```

Tổng độ rộng là r Σ_{n=0}^{∞} (r²)ⁿ (sách ghi chỉ số bắt đầu từ 1, xem khối Lưu ý). Vì r² < 1, tổng của chuỗi hình học là r/(1 − r²). Với r² = 2 − 2√2 + 1 = 3 − 2√2:

```text
(√2 − 1)/(1 − (3 − 2√2)) = (√2 − 1)/(2√2 − 2) = 1/2
```

Kết quả thú vị: **X check đúng một nửa số tay**. Phần lớn các tay đó sẽ miễn cưỡng call — chính xác là r ≈ 0,414 của toàn bộ tay bài (vùng [x₁, 1]); phần còn lại, 1/2 − r ≈ 0,086, sẽ check-raise và sẵn sàng bỏ thêm bet khi thích hợp.

Người tổng hợp tính thêm độ rộng các vùng bet của X: [x₂, x₁] rộng (1 − r) − r² = r (dùng r² = 1 − 2r), [x₄, x₃] rộng r²(1 − r) − r⁴ = r³, nói chung r, r³, r⁵, …, tổng cũng bằng 1/2. Như vậy câu "vùng check-raise hẹp hơn nhiều vùng bet" đúng khi so vùng check-raise đầu tiên [x₃, x₂] (rộng r³ ≈ 0,071) với vùng bet đầu tiên [x₂, x₁] (rộng r ≈ 0,414); vùng bet-reraise kế tiếp [x₄, x₃] rộng đúng bằng vùng check-raise r³.

### 7. Khái niệm then chốt (Key Concepts, trang 200)

- Trong trò chơi full-street không bỏ bài, có một quan hệ quan trọng giữa các tay bài đối thủ có thể đã dùng để thực hiện một hành động và các tay bài bạn dùng để thực hiện hành động của mình.
- Nếu bạn không thể bị raise và đối thủ không thể bỏ bài, hãy bet hoặc raise với 1/2 số tay mà đối thủ đã bet hoặc check tới lúc đó.
- Nếu đối thủ **có thể** raise lại, tỷ lệ này nhỏ đi. Khi được raise không giới hạn, tỷ lệ trở thành r.
- Trò chơi không bỏ bài là bài tập rút đúng lượng giá trị từ bài mạnh.

### 8. Phụ lục Chương 16 — Giải các phương trình sai phân (Appendix to Chapter 16: Solving the Difference Equations, trang 201–203)

#### 8a. Phương trình 16.1 (trang 201–202)

```text
y_{k+2} + 2y_{k+1} − y_k = 0          (16.1)
```

Phương trình này gọi là **phương trình sai phân thuần nhất cấp hai** (second-order homogeneous difference equation); nó mô tả quan hệ giữa ba ngưỡng y liên tiếp.

Mọi phương trình dạng y_{n+2} + c·y_{n+1} + d·yₙ = 0, với c, d là hằng số, có nghiệm dạng

```text
yₙ = a·pⁿ + b·qⁿ                      (16.1a)
```

trong đó a, b là hằng số, p và q là hai nghiệm thực phân biệt của **phương trình đặc trưng** x² + cx + d = 0. (Nếu hai nghiệm trùng nhau thì nghiệm có dạng khác, nhưng không liên quan ở đây.) Giải thích của người tổng hợp: thử yₙ = λⁿ vào phương trình được λⁿ(λ² + cλ + d) = 0, nên λ phải là nghiệm của phương trình đặc trưng; vì phương trình tuyến tính, tổ hợp tuyến tính của hai nghiệm cũng là nghiệm.

Với Phương trình 16.1, phương trình đặc trưng là x² + 2x − 1 = 0, nghiệm x = −1 ± √2. Nghiệm √2 − 1 chính là "tỷ lệ vàng của poker" của Chương 14; ta gọi nó là r. Thế hai nghiệm vào 16.1a:

```text
yₙ = a·rⁿ + b·(−1 − √2)ⁿ
```

Dùng trực giác: khi n → ∞, yₙ hội tụ về 0, vì Y cần bài ngày càng gần 0 mới bỏ thêm bet khi n lớn. Số hạng thứ hai không hội tụ về 0 với bất kỳ b nào khác 0 (vì |−1 − √2| ≈ 2,414 > 1). Vậy b = 0 và yₙ = a·rⁿ.

Tìm a bằng phương trình tại ngưỡng x₁:

```text
y₂ = 1 − y₁
a·r² = 1 − a·r
a·r² + a·r − 1 = 0
```

Có thể giải như phương trình bậc hai theo r, nhưng tiện hơn là dùng đồng nhất thức:

```text
r² = (√2 − 1)² = 2 − 2√2 + 1 = −2(√2 − 1) + 1 = 1 − 2r
```

Thế vào:

```text
a(1 − 2r) + a·r − 1 = 0
a − a·r − 1 = 0
a(1 − r) − 1 = 0
a = 1/(1 − r)
```

Do đó **yₙ = rⁿ/(1 − r)**. (Kiểm: a ≈ 1,7071; y₁ = 1,7071 × 0,41421 = 0,70711.)

#### 8b. Phương trình 16.2 (trang 202–203)

```text
x_k + 2x_{k+1} − x_{k+2} = 2r^k        (16.2)
```

Đây cũng là phương trình sai phân cấp hai (sách in nhầm "như Phương trình 20.1"; đúng là như Phương trình 16.1). Nhưng vì vế trái của các số hạng x có tổng khác 0, phương trình gọi là **không thuần nhất** (non-homogeneous), và cần thêm một bước. Nếu Z là một **nghiệm riêng** (particular solution) — một dãy thoả phương trình 16.2 với mọi k — thì mọi nghiệm của phương trình là **nghiệm tổng quát** của phương trình thuần nhất tương ứng cộng với Z:

```text
xₙ = a·pⁿ + b·qⁿ + Z                   (16.2a)
```

*Phần thuần nhất.* Phương trình đặc trưng của x_k + 2x_{k+1} − x_{k+2} = 0 là 1 + 2x − x² = 0, nghiệm x = 1 ± √2. Vậy p = 1 − √2 = −r và q = 1 + √2:

```text
xₙ = a(−r)ⁿ + b(1 + √2)ⁿ + Z
```

*Nghiệm riêng.* Đoán Z có dạng Z = c·λⁿ với c, λ là hằng số (sách dùng chữ x cho λ). Thế vào 16.2:

```text
c·λⁿ + 2c·λⁿ⁺¹ − c·λⁿ⁺² = 2rⁿ
c·λⁿ(1 + 2λ − λ²) = 2rⁿ
```

Vì (1 + 2λ − λ²) là hằng số, chọn λ = r thì với một giá trị c thích hợp đây là nghiệm:

```text
c·rⁿ(1 + 2r − r²) = 2rⁿ
c(1 + 2r − (1 − 2r)) = 2
c(4r) = 2
c = 1/(2r)        (sách in "c = r/2", sai; xem khối Lưu ý)
```

Vậy nghiệm riêng là Z = rⁿ/(2r) = rⁿ⁻¹/2. Khi n → ∞, Z hội tụ về 0. Theo đúng lập luận khi giải 16.1, số hạng thứ hai của nghiệm tổng quát chỉ hội tụ về 0 khi b = 0 (vì 1 + √2 > 1). Do đó:

```text
xₙ = a(−r)ⁿ + rⁿ/(2r)
```

*Tìm a* bằng định nghĩa x₀ = 1:

```text
x₀ = a(−r)⁰ + r⁰/(2r)
1 = a + 1/(2r)
a = (2r − 1)/(2r)          (≈ −0,2071)
xₙ = ((2r − 1)/(2r))(−1)ⁿrⁿ + rⁿ/(2r)
xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2
```

Người tổng hợp kiểm 16.2 với k = 0: x₀ + 2x₁ − x₂ = 1 + 1,171573 − 0,171573 = 2 = 2r⁰; với k = 1: x₁ + 2x₂ − x₃ = 0,585786 + 0,343146 − 0,100505 = 0,828427 = 2r.

## Luận điểm cốt lõi

### Mệnh đề

Khi không ai được bỏ bài, chiến lược tối ưu chỉ gồm value bet, và mỗi người bỏ thêm một bet với một tỷ lệ cố định của các tay bài đối thủ còn có thể đang cầm: 1/2 khi bet đó không thể bị raise lại, và r = √2 − 1 khi raise qua lại không giới hạn. Quyền check-raise của người đi trước buộc người đi sau bet chặt hơn sau khi bị check, và người đi trước khi đó check đúng một nửa số tay.

### Giả định

- Trò chơi [0,1]: bài của mỗi người phân phối đều, độc lập trên [0, 1]; mỗi người biết bài mình, không biết bài đối thủ.
- Không ai được bỏ bài (xấp xỉ pot rất lớn); kỳ vọng tính ex-showdown.
- Một vòng cược duy nhất, X hành động trước, Y sau.
- Bet có kích thước cố định (limit); trong trò chơi số 6 và số 8, số raise không giới hạn và stack vô hạn.
- Cấu trúc chiến lược là các vùng liền nhau theo thứ tự ngưỡng do tác giả chọn (tham số hoá); lời giải được kiểm bằng phương trình bàng quan, và ở trò chơi số 7 tác giả nói rõ có nhiều cách xếp vùng check-raise đồng tối ưu.

### Cơ chế

1. Tham số hoá chiến lược bằng các ngưỡng, xếp theo thứ tự.
2. Tại mỗi ngưỡng, người chơi phải bàng quan giữa hai hành động hai bên; viết bảng hiệu kỳ vọng theo các khoảng bài của đối thủ, cộng tích, cho bằng 0.
3. Giải hệ phương trình (hữu hạn ngưỡng) hoặc biến các phương trình tổng quát thành phương trình sai phân (vô hạn ngưỡng), giải bằng phương trình đặc trưng, loại nghiệm không hội tụ, dùng điều kiện biên.
4. Kiểm tra lời giải bằng cách xem người chơi có cải thiện được bằng cách đổi hành động ở một vùng bài hay không.

### Bằng chứng và ví dụ tác giả đưa ra

- Trò chơi số 4: x₁ = y₁ = 1; X bet mọi tay.
- Trò chơi số 5: x₁ = 1/2, y₂ = 1/4, y₁ = 3/4; kiểm tra với x trong [0, 1/4]: 4x − 5/4 so với 2x − 3/4.
- Trò chơi số 6: R² + 2R − 1 = 0, R = √2 − 1; x₁ ≈ 0,5469, y₁ ≈ 0,7735, y₂ ≈ 0,2265, x₃ ≈ 0,0938.
- Trò chơi số 7: x₂ = 1/9, y₂ = 1/3, x₁ = 5/9, y₁ = 2/3; bảng so sánh với trò chơi số 5.
- Trò chơi số 8: yₙ = rⁿ/(1 − r), xₙ = rⁿ⁻¹[(2r − 1)(−1)ⁿ + 1]/2; bảng ngưỡng tới n = 5; X check một nửa số tay.

### Kết luận và hàm ý cho người chơi

- Khi đối thủ gần như không bao giờ bỏ bài (pot lớn, hoặc đối thủ có thói quen call mọi bet), đừng bluff; hãy value bet với khoảng một nửa số tay đối thủ có thể đang cầm nếu không sợ bị raise lại.
- Khi đối thủ có thể raise lại, raise ít hơn một nửa: khoảng 41% các tay đối thủ có thể đang cầm.
- Người đi sau phải tính tới check-raise: nếu người đi trước có khả năng check-raise, value bet sau khi bị check phải chặt hơn (3/4 xuống 2/3 trong ví dụ hai bet).
- Người đi trước nên check cả một số tay rất mạnh (để check-raise) và bet thêm các tay trung bình.
- Vị trí có giá trị: ngay cả khi không có bluff, Y (người hành động sau) lời 1/8 bet mỗi ván trong trò chơi hai bet không check-raise (người tổng hợp tính).

### Trong ngôn ngữ lý thuyết trò chơi

Mỗi trò chơi là một trò chơi tổng bằng không hai người với thông tin không đầy đủ (mỗi người chỉ biết bài mình); chiến lược thuần là hàm từ bài sang hành động, và cân bằng Nash có dạng chiến lược ngưỡng (threshold strategies). Điều kiện bàng quan tại ngưỡng là điều kiện bậc nhất của bài toán tối ưu: nếu kỳ vọng hai hành động khác nhau tại ngưỡng thì dời ngưỡng có lợi. Với vô số ngưỡng, điều kiện bàng quan tạo thành hệ phương trình tuyến tính vô hạn có cấu trúc dịch chuyển, nên rút gọn về phương trình sai phân tuyến tính hệ số hằng; điều kiện các ngưỡng tiến về 0 đóng vai trò điều kiện biên ở vô cực. Tính xen kẽ (−1)ⁿ trong chiến lược của X là dấu vết của nghiệm đặc trưng âm −r.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| [0,1] game | trò chơi [0,1] | mỗi người nhận một số đều trên [0, 1], số nhỏ thắng |
| full-street | vòng cược đầy đủ (full-street) | cả hai người đều có quyền bet trên vòng |
| half-street | nửa vòng (half-street) | chỉ một người được bet |
| no-fold game | trò chơi không bỏ bài | luật cấm fold; xấp xỉ pot rất lớn |
| pot | pot | tổng tiền cược đang có trên bàn |
| bet | bet | đặt cược đầu tiên trên vòng |
| call | call | theo cược của đối thủ |
| check | check | không đặt cược, chuyển lượt |
| raise / reraise | raise / reraise | tăng cược / tăng tiếp sau khi bị raise |
| check-raise | check-raise | check trước rồi raise khi đối thủ bet |
| check-call | check rồi call | check, rồi call khi đối thủ bet |
| fold | fold (bỏ bài) | bỏ ván, mất phần đã cược |
| bluff | bluff | bet với bài yếu để đối thủ bỏ bài tốt hơn |
| value bet / raise for value | value bet / raise lấy giá trị | bet hoặc raise mong bị call bởi bài yếu hơn |
| showdown | showdown | lật bài so sánh cuối ván |
| nuts | nuts | bài mạnh nhất có thể; ở đây là 0 |
| ex-showdown expectation | kỳ vọng ex-showdown | kỳ vọng chỉ tính phần cược trên vòng, không tính pot sẵn có |
| equity | equity | phần giá trị kỳ vọng của một người |
| threshold | ngưỡng | điểm tách hai hành động trên [0, 1] |
| betting region | vùng cược | khoảng bài cùng một hành động |
| parameterization | tham số hoá | mô tả chiến lược bằng các ngưỡng và thứ tự của chúng |
| indifference / indifference equation | bàng quan / phương trình bàng quan | hai hành động cùng kỳ vọng tại ngưỡng |
| optimal strategy | chiến lược tối ưu | chiến lược không bị đối thủ khai thác; cân bằng |
| co-optimal | đồng tối ưu | nhiều chiến lược cùng tối ưu |
| dominated | bị trội | luôn kém hơn một chiến lược khác |
| exploit | khai thác | tăng kỳ vọng nhờ lỗi chiến lược của đối thủ |
| game value | giá trị trò chơi | kỳ vọng khi cả hai chơi tối ưu |
| positional advantage | lợi thế vị trí | lợi thế của người hành động sau |
| raising ratio R | tỷ lệ raise R | tỷ lệ tay bỏ bet tiếp so với tay đối thủ đã bỏ bet |
| golden mean of poker | tỷ lệ vàng của poker | r = √2 − 1 ≈ 0,4142 |
| stack | stack | số chip người chơi có |
| limit | limit | kích thước bet cố định |
| difference equation | phương trình sai phân | quan hệ giữa các số hạng liên tiếp của dãy |
| second-order homogeneous | thuần nhất cấp hai | liên hệ ba số hạng liên tiếp, vế phải bằng 0 |
| non-homogeneous | không thuần nhất | vế phải khác 0 |
| characteristic equation | phương trình đặc trưng | phương trình bậc hai cho cơ số của nghiệm dạng λⁿ |
| particular solution | nghiệm riêng | một dãy thoả phương trình không thuần nhất |
| general solution | nghiệm tổng quát | mọi nghiệm: nghiệm thuần nhất cộng nghiệm riêng |
| converge | hội tụ | tiến về một giới hạn |
| uniform distribution | phân phối đều | mọi điểm trên [0, 1] như nhau |
| hold'em | hold'em | biến thể poker phổ biến nhất, hai lá riêng và năm lá chung |
| draw | draw | tay bài chưa thành, cần lá sau để mạnh lên |
| implied odds | implied odds | tỷ lệ tính cả tiền có thể thắng thêm ở các vòng sau |
| solver GTO | solver GTO | phần mềm tính chiến lược cân bằng cho tình huống poker |

## Câu nói đáng nhớ

> "No-fold games are exercises in extracting the proper amount of value from strong hands." — phần mở đầu và Key Concepts
>
> *Dịch: Trò chơi không bỏ bài là bài tập rút đúng lượng giá trị từ bài mạnh.*
>
> Ý nghĩa: khi đối thủ không bỏ bài, vấn đề không phải lừa mà là bet đúng mức với đúng số tay.

> "The 'neither player may fold' rule approximates play when the pot is extremely large." — phần mở đầu
>
> *Dịch: Luật "không người nào được bỏ bài" xấp xỉ cách chơi khi pot cực lớn.*
>
> Ý nghĩa: mô hình đơn giản hoá này có đối ứng thực tế: pot càng lớn so với bet, bỏ bài càng hiếm.

> "Each player, then, wants to play so that the other is indifferent between the two actions on either side of each of his threshold points." — Ví dụ 16.1
>
> *Dịch: Vậy mỗi người muốn chơi sao cho đối thủ bàng quan giữa hai hành động hai bên mỗi ngưỡng của đối thủ.*
>
> Ý nghĩa: đây là phương pháp giải của cả chương.

> "In fact, this is always the case on the last bet - when a player cannot be reraised and the other player cannot fold, R is 1/2." — Ví dụ 16.2
>
> *Dịch: Thực ra điều này luôn đúng với bet cuối cùng — khi một người không thể bị raise lại và người kia không thể bỏ bài, R bằng 1/2.*
>
> Ý nghĩa: quy tắc nửa số tay cho value bet cuối cùng.

> "How often should I raise an opponent who cannot fold and can raise me back?" — Ví dụ 16.3
>
> *Dịch: Nên raise một đối thủ không thể bỏ bài nhưng có thể raise lại mình bao thường xuyên?*
>
> Ý nghĩa: câu trả lời là với tỷ lệ r = √2 − 1 ≈ 41% các tay đối thủ có thể đang cầm.

> "The intuitive explanation for this is that when X has a very strong hand, he often wants to bet, because he gets a very large amount of value from the sequence 'bet-call.'" — Ví dụ 16.5
>
> *Dịch: Giải thích trực giác là khi X cầm bài rất mạnh, X thường muốn bet, vì X lấy được rất nhiều giá trị từ chuỗi "bet rồi call".*
>
> Ý nghĩa: check-raise không phải lúc nào cũng tốt hơn bet thẳng với bài mạnh.

> "This intriguing result indicates that X checks half his hands overall." — Ví dụ 16.5
>
> *Dịch: Kết quả lý thú này cho thấy X check tổng cộng một nửa số tay.*
>
> Ý nghĩa: quy tắc nửa số tay lại xuất hiện, lần này ở chiến lược mở đầu của người đi trước.

> "If your opponent can raise you back, this ratio shrinks. In the case where an infinite number of raises are allowed, it becomes r." — Key Concepts
>
> *Dịch: Nếu đối thủ có thể raise lại, tỷ lệ này nhỏ đi. Khi được raise không giới hạn, tỷ lệ trở thành r.*
>
> Ý nghĩa: rủi ro bị raise lại làm giảm số tay nên raise.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương xây một chuỗi năm trò chơi tăng dần độ phức tạp, mỗi trò chơi chỉ thêm một luật (thêm bet thứ hai, raise không giới hạn, check-raise, cả hai), nên người đọc thấy rõ mỗi luật thay đổi chiến lược thế nào. Bảng so sánh trò chơi số 5 và số 7 là một ví dụ tốt về "dự đoán trước, kiểm bằng toán sau": cả ba dự đoán định tính của tác giả đều được lời giải xác nhận. Kết quả R = √2 − 1 trả lời một câu hỏi thực hành cụ thể ("nên raise bao thường xuyên khi đối thủ có thể raise lại?") bằng một con số gọn. Việc giải trò chơi số 8 bằng phương trình sai phân cho thấy phương pháp bàng quan mở rộng được tới vô số ngưỡng, và kết quả "X check đúng một nửa số tay" là một phát hiện đẹp.

### Những chỗ đơn giản hoá

- **Luật không bỏ bài** loại bỏ thành phần quan trọng nhất của poker thật là bluff và fold; tác giả biết điều này và để Chương 17 xử lý pot hữu hạn.
- **Phân phối bài đều và độc lập** khác poker thật, nơi phân phối bài của hai người phụ thuộc vào hành động trước đó và vào bài chung; trong hold'em, equity của hai tay bài thay đổi theo các lá chưa lật, còn ở đây bài đã cố định (không có draw).
- **Một vòng cược duy nhất**: không có vòng sau, nên không có implied odds hay việc giữ bài để bluff vòng sau.
- **Raise không giới hạn và stack vô hạn** trong trò chơi số 6 và số 8; ở limit thật thường có giới hạn ba hoặc bốn bet mỗi vòng, nên tỷ lệ raise thực nằm giữa 1/2 (bet cuối) và r.
- **Bảng tính của sách có nhiều lỗi in** (đã liệt kê ở khối Lưu ý); kết quả cuối đúng, nhưng người đọc tự kiểm từng bảng sẽ bị bối rối. Phương pháp "chỉ ghi hiệu" khiến các bảng bỏ qua những khoảng có hiệu bằng 0, làm khó theo dõi ở trò chơi số 8.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

Các solver GTO hiện đại (ví dụ PioSOLVER, GTO Wizard và các công cụ tương tự) giải trực tiếp các tình huống river với phân phối bài thật, nhiều kích thước bet và cho phép fold; các kết quả "toy game" như trò chơi [0,1] vẫn được dùng trong giảng dạy để giải thích vì sao solver đưa ra tần suất bet và raise như vậy. Quy tắc "value bet với một nửa số tay đối thủ có thể call khi không bị raise lại" và việc người đi trước check cả một số tay mạnh (để bảo vệ dải check) đều là những ý tưởng trở thành phổ biến khi người chơi học từ solver, dưới tên gọi "bảo vệ dải check" (protecting the checking range).

### Liên hệ các chương khác

- [C11-tro-choi-nua-vong.md](C11-tro-choi-nua-vong.md): trò chơi [0,1] half-street số 1 (không bỏ bài, Y bet với nửa số tay, lời 1/4 bet), số 2 (có bỏ bài, có bluff), quy ước đặt tên ngưỡng, Ví dụ 11.3.
- [C14-chon-muc-cuoc-no-limit.md](C14-chon-muc-cuoc-no-limit.md): nơi r = √2 − 1 xuất hiện lần đầu (mức bet tối ưu trong một trò chơi no-limit) và được đặt tên "tỷ lệ vàng của poker".
- [C15-tro-choi-tron-vong.md](C15-tro-choi-tron-vong.md): trò chơi full-street đầu tiên (AKQ) và phụ lục AKQ no-limit.
- [C17-tro-choi-01-pot-huu-han-va-bluff.md](C17-tro-choi-01-pot-huu-han-va-bluff.md): các trò chơi [0,1] số 9 tới số 12 với pot hữu hạn, có bluff; trò chơi số 10, 11, 12 là bản pot hữu hạn của trò chơi số 5, 7, 6, và khi pot tiến tới vô hạn, lời giải của chúng tiến về lời giải không bỏ bài của chương này (ví dụ tỷ lệ raise R_P của trò chơi số 12 tiến tới r).
- [C18-tro-choi-01-nhin-lai.md](C18-tro-choi-01-nhin-lai.md): giá trị trò chơi của các trò chơi [0,1], mà chương này mới chỉ nhắc tới.
- [C19-tro-choi-nhieu-vong-tinh.md](C19-tro-choi-nhieu-vong-tinh.md) và [C20-tro-choi-nhieu-vong-dong.md](C20-tro-choi-nhieu-vong-dong.md): mở rộng sang nhiều vòng cược.

### Vận dụng

- **Cho người chơi poker:** khi pot đã lớn và đối thủ gần như chắc chắn call (river trong pot nhiều người, hoặc đối thủ không bao giờ bỏ bài), hãy bỏ hẳn bluff và value bet rộng: khoảng một nửa số tay đối thủ có thể đang cầm. Khi cân nhắc raise một đối thủ có thể reraise, chỉ raise với khoảng 40% đầu của dải bài đối thủ đang bet. Ở vị trí đầu, đừng bet mọi tay mạnh: giữ một phần nhỏ (khoảng một phần năm số tay mạnh, như trò chơi số 7: 1/9 trong 5/9 tay tốt nhất được check-raise, phần còn lại được bet) để check-raise, buộc đối thủ không dám value bet mỏng sau khi bạn check.
- **Cho người làm tài chính và ra quyết định:** cấu trúc "mỗi bước tăng cam kết chỉ với một tỷ lệ cố định của phần đối thủ còn lại" giống các tình huống đấu giá hay đàm phán leo thang, nơi mỗi lần nâng giá đều có thể bị nâng lại; mô hình cho thấy khả năng bị phản ứng lại làm giảm tần suất nên leo thang (từ 1/2 xuống khoảng 0,41). Phương pháp "đặt ngưỡng, rồi buộc bên kia bàng quan tại ngưỡng" là công cụ chung khi thiết kế chiến lược trước một đối thủ thông minh. Kỹ thuật phương trình sai phân của Phụ lục cũng là kỹ thuật cơ bản trong tài chính (dòng tiền truy hồi, mô hình lãi kép, mô hình cây nhị phân).
