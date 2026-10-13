# Toán học của poker — Bill Chen và Jerrod Ankenman (2006)

*The Mathematics of Poker.* Mỗi chương được tổng hợp thành một file riêng; hai phụ lục chương (trò chơi AKQ no-limit, giải phương trình sai phân) nằm cuối file của Chương 15 và 16, còn trang đề từ mở mỗi Phần nằm đầu file của chương đầu tiên trong Phần đó. File nào cũng đi qua đủ từng mục và từng ví dụ của chương theo đúng thứ tự, chép lại mọi công thức kèm từng bước giải, mọi bảng (kể cả hai bảng jam-or-fold 13×13), mô tả và đọc số từ mọi hình, và **mọi phép tính của sách đã được người tổng hợp tính lại** bằng phân số chính xác, tích phân số, liệt kê đủ bộ bài hoặc mô phỏng Monte Carlo. Sau đó là các khái niệm cần biết, luận điểm cốt lõi, bảng thuật ngữ Anh–Việt, câu nói đáng nhớ và phần đánh giá: chỗ nào sách tính nhầm hoặc in sai, điều gì đã thay đổi từ 2006 (solver, poker trực tuyến, AI chơi poker), cách vận dụng cho người chơi poker và cho người làm tài chính, đầu tư.

**Tác giả:** Bill Chen, tiến sĩ toán Đại học California tại Berkeley (1999), làm ở công ty giao dịch Susquehanna International Group, vô địch hai giải World Series of Poker năm 2006. Jerrod Ankenman, cử nhân quản trị kinh doanh Đại học Pepperdine (2004), người chơi poker chuyên nghiệp, á quân một giải WSOP 2006. Hai người trao đổi từ năm 2000 và cùng nghiên cứu poker từ năm 2002. Lời tựa do Chris "Jesus" Ferguson, nhà vô địch WSOP 2000, viết.

**Nguồn:** bản PDF tiếng Anh 390 trang của ấn bản đầu tiên (ConJelCo, Pittsburgh, 2006; ISBN 978-1-886070-25-7), dựng lại bằng LibreOffice năm 2016.

> **Lưu ý về nguồn:**
> - **Số trang.** Các file ghi "trang n" theo số in ở chân trang của bản PDF này (bằng số thứ tự trang PDF). Mục lục của sách lệch một trang so với chân trang, và cả hai có thể khác bản in gốc.
> - **Bản PDF dựng lại có lỗi riêng.** Lớp chữ làm phẳng chỉ số dưới (y₂ thành "y2"), có lỗi nhận dạng chữ ("wc" thay "we", ký hiệu "|" của xác suất có điều kiện thành "∨" hoặc "¿"), nhiều công thức bị vỡ, và biểu tượng đánh dấu đoạn toán có thể bỏ qua đã mất. Mọi hình và nhiều bảng là ảnh; người tổng hợp đọc từ ảnh trang. **Trang 312 để trắng**, nên bảng so sánh rủi ro phá sản ở Chương 23 bị mất; file Chương 23 thay bằng bảng do người tổng hợp tự tính theo đúng thông số của sách, có ghi rõ.
> - **Sách có nhiều lỗi in và lỗi tính toán; bản tổng hợp ghi cả số của sách và số đúng** (nhận xét của người tổng hợp, chưa đối chiếu danh sách đính chính của nhà xuất bản). Phần lớn là lỗi dấu, nhãn bảng hoặc số hiệu ví dụ trong các bước trung gian mà lời giải cuối vẫn đúng. Những lỗi làm thay đổi con số kết luận:
>   - Chương 6: khoảng tin cậy 95% của tỷ lệ thắng sau 10.000 ván ghi ±0,02 BB/ván, đó chỉ là ±1 sai số chuẩn; đúng là khoảng ±0,04.
>   - Chương 7, Ví dụ 7.2: một tiểu trường hợp ghi $346,21, đúng là $186,36 (sách quên nhân xác suất 30/45).
>   - Chương 12: kỳ vọng của raise lên 2 với Q3o ghi −0,638, đúng là −0,362; lỗi này làm yếu lập luận về ngưỡng 8 big blind. Hai con số đếm của sách cũng không khớp với chính bảng jam-or-fold (ở 8 big blind: sách 61,7%, đếm từ bảng 63,2%).
>   - Chương 18: giá trị trò chơi [0,1] số 6 ghi ≈ 0,1143, đúng là ≈ 0,1133.
>   - Chương 20, Ví dụ 20.5: α ≈ 0,1965 là do thay nhầm biểu thức; đúng là 127/867 ≈ 0,1465, nên câu "X fold gần 1/5 số lần" sai (X fold ít hơn 1/6).
>   - Chương 22, Ví dụ 22.3: α ≈ 0,000632 không thoả chính phương trình của sách; đúng là ≈ 0,000606, nên cả bảng rủi ro phá sản thấp hơn thực tế (bankroll $1.000: 53,2% → 54,6%).
>   - Chương 23: với σ = 12 và 100 giờ, xác suất tỷ lệ thắng quan sát lệch quá 1 bet/giờ ghi 32%, đúng là khoảng 40,5%.
>   - Chương 24, Ví dụ 24.2: ngưỡng c ghi $19.295, đó là 2c; đúng là c = $9.647,50.
>   - Chương 25: công thức định giá thoả thuận chia lãi theo bậc tính kỳ vọng của toàn bộ kết quả thay vì phần vượt ngưỡng; phần của người chơi đúng là 43,1% ($978,15), không phải 60,4%.
>   - Chương 27: quỹ thưởng giải nhất trong ví dụ Landrum-Burns in 2.200, đúng là 2.000; equity người chơi thứ ba 1.066,67 → 1.166,67.
>   - Chương 28: phạm vi {66+, A9s+, AT+, KJs+} ghi "khoảng 7%" số tay bài, đúng là 9,8%.
>   - Chương 29: điểm cân bằng của ví dụ side pot thứ hai (x ≈ 0,2848) không thoả phương trình của sách; nghiệm đúng là x ≈ 0,5178, X call 51,8% thay vì 28,5%. Bài học định tính không đổi.
> - **Equity tay bài hold'em** mà sách lấy từ phần mềm PokerStove được kiểm bằng liệt kê đủ hoặc mô phỏng Monte Carlo khi có thể; phần lớn khớp trong phạm vi sai số mô phỏng. Chỗ không khớp hoặc không kiểm được đều ghi trong khối Lưu ý của từng file.
> - **Sách còn bản quyền.** Bản tổng hợp diễn đạt lại bằng lời mới; câu trích nguyên văn chủ yếu nằm ở mục "Câu nói đáng nhớ".
> - **Thuật ngữ.** Các từ poker phổ biến trong cộng đồng poker Việt Nam (pot, pot odds, bluff, call, raise, fold, flop, river, equity, bankroll…) được giữ tiếng Anh và giải thích ở lần đầu; khái niệm toán được dịch sang tiếng Việt. Cách gọi của sách cho người chơi (X, Y), các trò chơi ([0,1], AKQ, jam-or-fold) và các ngưỡng (x₁, y₁, y₀…) được giữ nguyên.

## Chuỗi lập luận của cả cuốn sách

```text
       GIỚI THIỆU — VÌ SAO CẦN TOÁN TRONG POKER
       · thị trường trái phiếu, quyền chọn và cờ backgammon đều đã chuyển
         từ trực giác sang phân tích định lượng; poker đang đi cùng hướng
       · mọi người chơi đều ngầm dùng một mô hình; hai cách tiếp cận:
         CHƠI KHAI THÁC (đánh vào điểm yếu đối thủ) và CHƠI TỐI ƯU (lý
         thuyết trò chơi, không thể bị khai thác)
                                │
                                ▼
       PHẦN I — CƠ BẢN (Chương 1–3)
       · C1: xác suất và giá trị kỳ vọng; quyết định đúng là quyết định
         có kỳ vọng cao nhất
       · C2: phương sai, độ lệch chuẩn, phân phối chuẩn; kết quả ngắn hạn
         dao động mạnh quanh kỳ vọng
       · C3: ước lượng tỷ lệ thắng, khoảng tin cậy, định lý Bayes để cập
         nhật niềm tin về đối thủ và về chính mình
                                │
                                ▼
       PHẦN II — CHƠI KHAI THÁC (Chương 4–9)
       · C4: pot odds và implied odds; khi nào call một draw có lãi
       · C5: đọc bài là ước lượng phân phối tay bài theo Bayes
       · C6: dữ liệu lịch sử ván chơi trực tuyến và giới hạn thống kê
       · C7–C9: tính kỳ vọng chính xác khi bài lật ngửa, khi một tay bài
         đấu một phân phối, và khi phân phối đấu phân phối
                                │
                                ▼
       PHẦN III — CHƠI TỐI ƯU (Chương 10–21)
       · C10: lý thuyết trò chơi: cân bằng, chiến lược hỗn hợp, nemesis
       · C11–C13: trò chơi đồ chơi: nửa vòng cược, jam-or-fold (kèm bảng
         13×13), trò chơi AKQ; tỷ lệ bluff và call tối ưu α = 1/(P+1)
       · C14: chọn mức cược no-limit tối ưu
       · C15–C18: trò chơi trọn vòng và trò chơi [0,1] (bài là một số
         ngẫu nhiên trong [0,1]); raise, check-raise, bluff với pot hữu hạn
       · C19–C20: trò chơi nhiều vòng cược, khi bài thay đổi và không đổi
       · C21: áp dụng lý thuyết trò chơi vào một tình huống hold'em thật
                                │
                                ▼
       PHẦN IV — RỦI RO (Chương 22–25)
       · C22: rủi ro phá sản (risk of ruin) và cỡ bankroll cần thiết
       · C23: rủi ro phá sản khi tỷ lệ thắng thật không chắc chắn
       · C24: tiêu chuẩn Kelly và chọn bàn, chọn mức cược để tăng bankroll
       · C25: lý thuyết danh mục và thoả thuận tài trợ (backing) người chơi
                                │
                                ▼
       PHẦN V — CHỦ ĐỀ KHÁC (Chương 26–30)
       · C26–C28: giải đấu: chip không phải tiền, mô hình equity (Landrum-
         Burns, Malmuth-Harville, Malmuth-Weitzman), rebuy, add-on, sit-and-go
       · C29: trò chơi nhiều người và các liên minh ngầm
       · C30: kết hợp tất cả: dùng toán để chơi tốt hơn
```

## Mục lục

- [Giới thiệu — Lời cảm ơn, Lời tựa và Giới thiệu](00-gioi-thieu.md) (Acknowledgments, Foreword, Introduction): lời tựa của Chris Ferguson; từ trực giác sang định lượng; chơi khai thác và chơi tối ưu; cấu trúc cuốn sách

**Phần I — Cơ bản (Basics)**
- [Chương 1 — Quyết định dưới rủi ro: xác suất và kỳ vọng](C01-quyet-dinh-duoi-rui-ro-xac-suat-va-ky-vong.md) (Decisions Under Risk: Probability and Expectation)
- [Chương 2 — Dự báo tương lai: phương sai và kết quả mẫu](C02-du-bao-tuong-lai-phuong-sai-va-ket-qua-mau.md) (Predicting the Future: Variance and Sample Outcomes)
- [Chương 3 — Dùng hết thông tin: ước lượng tham số và định lý Bayes](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md) (Using All the Information: Estimating Parameters and Bayes' Theorem)

**Phần II — Chơi khai thác (Exploitive Play)**
- [Chương 4 — Pot odds và implied odds](C04-pot-odds-va-implied-odds.md) (Playing the Odds: Pot Odds and Implied Odds)
- [Chương 5 — Đọc bài và chiến lược](C05-doc-bai-va-chien-luoc.md) (Scientific Tarot: Reading Hands and Strategies)
- [Chương 6 — Các chủ đề về poker trực tuyến](C06-poker-truc-tuyen.md) (The Tells are in the Data: Topics in Online Poker)
- [Chương 7 — Chơi chính xác, phần 1: bài lật ngửa](C07-choi-chinh-xac-bai-lat-ngua.md) (Playing Accurately, Part I: Cards Exposed Situations)
- [Chương 8 — Chơi chính xác, phần 2: tay bài đấu phân phối](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md) (Playing Accurately, Part II: Hand vs. Distribution)
- [Chương 9 — Chơi thích nghi: phân phối đấu phân phối](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md) (Adaptive Play: Distribution vs. Distribution)

**Phần III — Chơi tối ưu (Optimal Play)**
- [Chương 10 — Lý thuyết trò chơi](C10-ly-thuyet-tro-choi.md) (Facing The Nemesis: Game Theory)
- [Chương 11 — Trò chơi nửa vòng cược](C11-tro-choi-nua-vong.md) (One Side of the Street: Half-Street Games)
- [Chương 12 — Trò chơi jam-or-fold](C12-tro-choi-jam-or-fold.md) (Headsup With High Blinds: The Jam-or-Fold Game)
- [Chương 13 — Trò chơi AKQ](C13-tro-choi-akq.md) (Poker Made Simple: The AKQ Game)
- [Chương 14 — Chọn mức cược no-limit](C14-chon-muc-cuoc-no-limit.md) (You Don't Have To Guess: No-Limit Bet Sizing)
- [Chương 15 — Trò chơi trọn vòng cược](C15-tro-choi-tron-vong.md) (Player X Strikes Back: Full-Street Games), kèm phụ lục trò chơi AKQ no-limit
- [Chương 16 — Trò chơi [0,1] không được fold](C16-tro-choi-01-khong-bo-bai.md) (Small Bets, Big Pots: No-Fold [0,1] Games), kèm phụ lục giải phương trình sai phân
- [Chương 17 — Trò chơi [0,1] với pot hữu hạn và bluff](C17-tro-choi-01-pot-huu-han-va-bluff.md) (Mixing in Bluffs: Finite Pot [0,1] Games)
- [Chương 18 — Nhìn lại trò chơi [0,1]](C18-tro-choi-01-nhin-lai.md) (Lessons and Values: The [0,1] Game Redux)
- [Chương 19 — Trò chơi nhiều vòng cược với bài không đổi](C19-tro-choi-nhieu-vong-tinh.md) (The Road to Poker: Static Multi-Street Games)
- [Chương 20 — Trò chơi nhiều vòng cược với bài thay đổi](C20-tro-choi-nhieu-vong-dong.md) (Drawing Out: Non-Static Multi-Street Games)
- [Chương 21 — Nghiên cứu tình huống: áp dụng lý thuyết trò chơi](C21-nghien-cuu-tinh-huong-ly-thuyet-tro-choi.md) (A Case Study: Using Game Theory)

**Phần IV — Rủi ro (Risk)**
- [Chương 22 — Rủi ro phá sản](C22-rui-ro-pha-san.md) (Staying in Action: Risk of Ruin)
- [Chương 23 — Rủi ro phá sản khi tỷ lệ thắng bất định](C23-rui-ro-pha-san-khi-ty-le-thang-bat-dinh.md) (Adding Uncertainty: Risk of Ruin with Uncertain Win Rates)
- [Chương 24 — Tiêu chuẩn Kelly và chọn ván chơi](C24-tieu-chuan-kelly-va-chon-van-choi.md) (Growing Bankrolls: The Kelly Criterion and Rational Game Selection)
- [Chương 25 — Lý thuyết danh mục và thoả thuận tài trợ](C25-ly-thuyet-danh-muc-va-thoa-thuan-tai-tro.md) (Poker Finance: Portfolio Theory and Backing Agreements)

**Phần V — Chủ đề khác (Other Topics)**
- [Chương 26 — Giải đấu, phần 1: nhân đôi chip](C26-giai-dau-phan-1-nhan-doi.md) (Doubling Up: Tournaments, Part I)
- [Chương 27 — Giải đấu, phần 2: chip không phải tiền](C27-giai-dau-phan-2-chip-khong-phai-tien.md) (Chips Aren't Cash: Tournaments, Part II)
- [Chương 28 — Giải đấu, phần 3: poker vẫn là poker](C28-giai-dau-phan-3-poker-van-la-poker.md) (Poker's Still Poker: Tournaments, Part III)
- [Chương 29 — Trò chơi nhiều người](C29-tro-choi-nhieu-nguoi.md) (Three's a Crowd: Multiplayer Games)
- [Chương 30 — Kết hợp tất cả: dùng toán để chơi tốt hơn](C30-ket-hop-tat-ca.md) (Putting It All Together: Using Math to Improve Play)

## Sách đọc thêm do tác giả giới thiệu (Recommended Reading)

- **Lý thuyết trò chơi:** R. Duncan Luce và Howard Raiffa, *Games and Decisions* (Dover, 1957); John von Neumann và Oskar Morgenstern, *Theory of Games and Economic Behavior* (Princeton University Press, 1944); J. D. Williams, *The Compleat Strategist* (Dover, 1966).
- **Poker và cờ bạc nói chung:** Richard A. Epstein, *Theory of Gambling and Statistical Logic* (Academic Press, 1967); David Sklansky, *The Theory of Poker* (Two Plus Two Publishing, 1987).
- **Chủ đề liên quan:** Peter Bernstein, *Against the Gods: The Remarkable Story of Risk* (John Wiley & Sons, 1996); Nassim Nicholas Taleb, *Fooled by Randomness* (Thomson, 2004).

## Gợi ý đọc

- **Đọc trước tiên:** Giới thiệu, rồi Chương 1–4. Bốn chương này cho đủ công cụ (kỳ vọng, phương sai, Bayes, pot odds) để hiểu phần còn lại.
- **Muốn hiểu lý thuyết trò chơi trong poker:** đọc liền Chương 10 → 11 → 13 → 15; trò chơi AKQ là mô hình gọn nhất cho thấy vì sao phải bluff và bluff bao nhiêu. Chương 16–20 là phần toán nặng nhất, nên đọc sau.
- **Chơi giải đấu ngắn stack:** Chương 12 (bảng jam-or-fold) và Chương 26–28.
- **Người làm tài chính, đầu tư, quản lý rủi ro:** Phần IV (Chương 22–25) dùng được trực tiếp: rủi ro phá sản, tiêu chuẩn Kelly, lý thuyết danh mục; đọc kèm Chương 2–3 về phương sai và ước lượng.
- **Liên hệ trong repo:** đọc kèm [The Art of Statistics](../The%20Art%20of%20Statistics/README.md) cho khoảng tin cậy và Bayes, [The Art of Strategy](../The%20Art%20of%20Strategy/README.md) cho lý thuyết trò chơi không toán, và bài [Câu chuyện kỳ diệu về rủi ro — "Against the Gods"](../../VN/Personal%20Finance/Risk%20Management/2025-07-against-the-gods-cau-chuyen-ve-rui-ro.md).
