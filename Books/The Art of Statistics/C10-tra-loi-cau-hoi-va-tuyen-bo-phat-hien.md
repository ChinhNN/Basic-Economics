# Chương 10 — Trả lời câu hỏi và tuyên bố phát hiện (Answering Questions and Claiming Discoveries)

**Nguồn:** David Spiegelhalter, *The Art of Statistics: How to Learn from Data*, Basic Books (Hachette), bản Mỹ đầu tiên tháng 9/2019 (bản gốc Pelican/Penguin, Anh, tháng 3/2019), Chương 10 "Answering Questions and Claiming Discoveries", trang PDF 174–202 (ebook không có số trang in; vị trí ghi theo chỉ số trang PDF và tên tiểu mục).
**Tác giả:** Sir David Spiegelhalter, nhà thống kê, chủ tịch Trung tâm Winton về Truyền đạt Rủi ro và Bằng chứng (Winton Centre for Risk and Evidence Communication), Phòng Thí nghiệm Thống kê, Đại học Cambridge; nguyên chủ tịch Hội Thống kê Hoàng gia Anh (Royal Statistical Society); được phong tước hiệp sĩ vì đóng góp cho thống kê.
**Vị trí trong lập luận của cả cuốn sách:** Phần mở đầu ([00-gioi-thieu.md](00-gioi-thieu.md)) giới thiệu chu trình giải quyết vấn đề PPDAC (Vấn đề, Kế hoạch, Dữ liệu, Phân tích, Kết luận) và vụ bác sĩ Harold Shipman. Chương 7 ([C07-uoc-luong-va-khoang.md](C07-uoc-luong-va-khoang.md)) dạy cách ước lượng một con số và gắn cho nó khoảng tin cậy bằng phương pháp bootstrap; Chương 8 ([C08-xac-suat-ngon-ngu-cua-bat-dinh.md](C08-xac-suat-ngon-ngu-cua-bat-dinh.md)) đưa ra ngôn ngữ xác suất, phân phối Poisson, cách nghĩ theo "1.000 người được xét nghiệm" và ngộ nhận của bên công tố; Chương 9 ([C09-ket-hop-xac-suat-va-thong-ke.md](C09-ket-hop-xac-suat-va-thong-ke.md)) dùng lý thuyết xác suất để tính khoảng tin cậy mà không cần mô phỏng. Chương 10 chuyển từ câu hỏi "con số này là bao nhiêu và chắc đến đâu" sang câu hỏi "dữ liệu có đủ bằng chứng để bác bỏ một giả định mặc định hay không": kiểm định giả thuyết, giá trị P, ý nghĩa thống kê, lý thuyết Neyman–Pearson về sai lầm loại I và loại II, kiểm định tuần tự, và những cách giá trị P bị dùng sai. Đây là phần "Phân tích" mang tính khẳng định của chu trình PPDAC. Chương 11 ([C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md](C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md)) trình bày cách tiếp cận Bayes, vốn bác bỏ toàn bộ ý tưởng kiểm định giả thuyết không; Chương 12 ([C12-nhung-dieu-co-the-sai.md](C12-nhung-dieu-co-the-sai.md)) quay lại câu "phần lớn kết quả nghiên cứu được công bố là sai" và các hậu quả của việc săn ý nghĩa thống kê; Chương 13 ([C13-lam-thong-ke-tot-hon.md](C13-lam-thong-ke-tot-hon.md)) bàn cách làm và đọc thống kê tốt hơn.
**Ý chính:** Spiegelhalter muốn người đọc hiểu rằng **kiểm định giả thuyết là một cơ chế để tự bảo vệ trước những "phát hiện" giả: ta giữ một giả thuyết không (null hypothesis) — giả định mặc định rằng không có gì xảy ra — cho tới khi dữ liệu đủ bất ngờ dưới giả định đó; giá trị P đo mức bất ngờ ấy, tức xác suất có được kết quả cực đoan ít nhất như đã quan sát nếu giả thuyết không (và mọi giả định khác của mô hình) đúng. Giá trị P không phải xác suất giả thuyết không đúng, không đo độ lớn hay tầm quan trọng của hiệu ứng, và "không có ý nghĩa thống kê" không có nghĩa là "không có hiệu ứng"; khi làm nhiều kiểm định, cắt dữ liệu thành nhiều nhóm hay kiểm định lặp lại trên dữ liệu tích luỹ, ngưỡng phải được điều chỉnh, nếu không phát hiện giả là điều chắc chắn xảy ra.** Chương mở đầu bằng John Arbuthnot (1710): 82 năm liền ở London số bé trai được rửa tội đều nhiều hơn bé gái, xác suất điều đó xảy ra nếu bé trai và bé gái là "năm ăn năm thua" là 1/2^82 — kiểm định ý nghĩa thống kê đầu tiên trong lịch sử. Mục "What Is a 'Hypothesis'?" định nghĩa giả thuyết là một giả định tạm thời về một thành phần của mô hình thống kê. Mục "Why Do We Need Formal Testing of Null Hypotheses?" giải thích rằng con người có xu hướng thấy quy luật ở nơi không có, nên cần một thủ tục chính thức; giả thuyết không giống bị cáo được coi là vô tội cho tới khi bị chứng minh có tội; ví dụ khoanh tay của 54 nghiên cứu sinh (nữ 64% tay phải ở trên, nam 57%) cho thấy bằng phép kiểm định hoán vị rằng chênh lệch 7% nằm ngay giữa phân phối kỳ vọng, giá trị P một phía 0,45, hai phía 0,89. Mục "Statistical Significance" nêu định nghĩa ý nghĩa thống kê, chân dung Ronald Fisher, thí nghiệm nếm trà (xác suất đoán đúng cả 4 cốc là 1/70) và sáu bước của kiểm định ý nghĩa giả thuyết không (NHST). Mục "Using Probability Theory" dùng các phép kiểm định có sẵn công thức — khi bình phương, t — để trả lời lại năm câu hỏi của sách: số vụ giết người theo ngày khớp phân phối Poisson (P = 0,96); thay đổi thất nghiệp 3.000 người không có ý nghĩa vì khoảng tin cậy 95% chứa 0; statin giảm nhồi máu cơ tim 27% với P cực nhỏ; chiều cao mẹ vẫn liên quan tới chiều cao con trai khi đã tính chiều cao bố (t = 7,25); và cây phân loại "thắng" cuộc thi Titanic chỉ nhờ may mắn (P = 0,59). Mục "The Danger of Carrying Out Many Significance Tests" chỉ ra rằng làm 10 kiểm định với thuốc vô dụng thì 40% khả năng có ít nhất một kết quả "có ý nghĩa"; con cá hồi chết có 16 vùng não "phản ứng" với ảnh; cách chữa là hiệu chỉnh Bonferroni, kiểm soát tỷ lệ phát hiện sai và đòi hỏi lặp lại nghiên cứu; hạt Higgs được công bố ở mức "năm sigma". Mục "Neyman—Pearson Theory" thêm giả thuyết đối, sai lầm loại I (mức α) và loại II (β), lực kiểm định 1 − β, và giải thích vì sao Nghiên cứu Bảo vệ Tim (HPS) cần hơn 20.000 người. Khung câu hỏi về Harold Shipman cho thấy kiểm định lặp lại hằng năm chắc chắn sẽ báo động sai, và kiểm định tỷ số xác suất tuần tự (SPRT) sẽ phát hiện Shipman năm 1984, cứu khoảng 175 người. Phần "What could go wrong with P-values?" dùng cây tần số 1.000 nghiên cứu (36% "phát hiện" là sai) và sáu nguyên tắc của Hiệp hội Thống kê Mỹ (ASA) năm 2016 để chỉ ra các cách hiểu sai giá trị P, kèm ví dụ rượu và ví dụ học đại học với u não.

> **Lưu ý:**
> - **Mức ý nghĩa của hạt Higgs bị gọi nhầm là "hai phía" (mục "The Danger of Carrying Out Many Significance Tests", phần câu hỏi 5, trang PDF 188):** sách viết rằng một quan sát cho "giá trị P hai phía 1 trên 3,5 triệu" sẽ cách giả thuyết không năm sai số chuẩn. Theo tính toán của người tổng hợp với phân phối chuẩn, xác suất vượt quá 5 sai số chuẩn **về một phía** là khoảng 2,9 × 10⁻⁷, tức khoảng 1 trên 3,5 triệu; xác suất **hai phía** là khoảng 5,7 × 10⁻⁷, tức khoảng 1 trên 1,7 triệu. Vậy con số 1 trên 3,5 triệu là giá trị P một phía (theo hiểu biết của người tổng hợp, vật lý hạt quy ước dùng giá trị P một phía vì chỉ quan tâm tới tín hiệu vượt nền). Nhận xét của người tổng hợp.
> - **Ký hiệu β dùng sai trong mục "Neyman—Pearson Theory" (trang PDF 190):** sách định nghĩa β là xác suất sai lầm loại II và lực kiểm định là 1 − β, nhưng ngay sau đó viết "often setting α = 0.05 and β = 0.80" và "the study has around β = 90% power". Đúng ra là 1 − β = 0,80 (tức β = 0,20) và 1 − β = 90% (tức β = 0,10). Cùng đoạn, "Health Protection Study" là lỗi đánh máy của "Heart Protection Study". Chú thích Hình 10.4 viết "Type 1" thay vì "Type I". Bản tổng hợp dùng ký hiệu đúng.
> - **Chú thích dấu sao về Shipman năm 1979 mâu thuẫn với lời văn:** lời văn (trang PDF 193) so 40 ca tử vong quan sát với 25,3 ca kỳ vọng và cho giá trị P một phía 0,004; chú thích dấu sao lại nói "xác suất một biến Poisson có trung bình 22,5 đạt ít nhất 40". Người tổng hợp tính gần đúng (xấp xỉ Wilson–Hilferty cho đuôi Poisson): với trung bình 25,3, P(X ≥ 40) ≈ 0,004 — khớp lời văn; với trung bình 22,5, P(X ≥ 40) ≈ 0,0006. Vậy 22,5 trong chú thích nhiều khả năng là lỗi; bản tổng hợp dùng 25,3.
> - **Thống kê khi bình phương 0,02 trong ví dụ khoanh tay là bản có hiệu chỉnh liên tục (Yates), sách không nói ra:** người tổng hợp tính lại từ bảng 2 × 2 (nữ 5 trái/9 phải, nam 17 trái/23 phải; kỳ vọng 5,70/8,30/16,30/23,70): công thức đơn giản nhất trong bảng thuật ngữ của sách, tổng (quan sát − kỳ vọng)²/kỳ vọng, cho 0,70² × (1/5,70 + 1/16,30 + 1/8,30 + 1/23,70) ≈ 0,20, ứng với P ≈ 0,66. Con số 0,02 và P = 0,90 của sách khớp với bản có hiệu chỉnh Yates: (0,70 − 0,5)² × 0,399 ≈ 0,017, P ≈ 0,90. Kết luận "không có bằng chứng" không đổi.
> - **Giá trị P hai phía 0,89 trong ví dụ khoanh tay (chỗ chưa chắc):** người tổng hợp tính tay phân phối siêu bội (số nữ tay phải ở trên, từ 0 tới 14) và được: P(9 trở lên) ≈ 0,453 — khớp giá trị một phía 0,45 của sách; P(đúng 8) ≈ 0,242. Nếu hiểu đúng từng chữ "chênh lệch ít nhất 7% theo cả hai chiều" thì chỉ loại trường hợp 8 nữ (chênh lệch −2,9%), và P hai phía ≈ 1 − 0,242 = 0,76. Con số 0,89 gần với cách **nhân đôi giá trị một phía** (bảng thuật ngữ của sách nói đây là cách thường dùng): 2 × 0,447 (đọc từ 1.000 hoán vị) ≈ 0,89, hoặc 2 × 0,453 ≈ 0,91. Dù cách nào, kết luận không đổi.
> - **Bảng 10.3 (số vụ giết người theo ngày):** cột "số ngày quan sát" cộng lại được 259 + 387 + 261 + 131 + 40 + 13 + 3 = **1.094**, không phải 1.095 như dòng tổng. Chú thích bảng ghi giai đoạn "April 2014 to March 2016" (2 năm, khoảng 730 ngày), nhưng 1.095 ngày là 3 năm và Chương 8 nói "ba năm"; giai đoạn hợp lý là tháng 4/2013 tới tháng 3/2016. Cột kỳ vọng thì người tổng hợp tính lại khớp (trung bình 1.545/1.095 = 1,411 vụ/ngày).
> - **Dấu của thay đổi thất nghiệp:** sách viết "a quarterly change in unemployment of 3,000" rồi lại dùng "point estimate (−3,000)". Theo Chương 7, đó là mức **giảm** 3.000 người; khoảng tin cậy −80.000 tới +74.000 khớp với ước lượng −3.000 ± 77.000.
> - **Bảng 10.4 (HPS):** lớp chữ của ebook ghi "P > 0.0001", ảnh trang ghi đúng là "P < 0.0001". Khoảng tin cậy chỉ "xấp xỉ" ước lượng ± 2 sai số chuẩn: với nhồi máu cơ tim, 27% ± 2 × 4% là 19%–35%, còn bảng ghi 21%–33% (sách giải thích do HPS làm tròn). Câu "giá trị P cho mức giảm 27% nhồi máu cơ tim vào khoảng 1 trên 3 triệu" khó khớp với chính số liệu của bảng: 27/4 ≈ 6,75 sai số chuẩn ứng với P cỡ 10⁻¹¹; tính từ số ca (8,7% của 10.269 người và 11,8% của 10.267 người) người tổng hợp được khoảng 7,5 sai số chuẩn. Một trên 3 triệu tương ứng khoảng 5 sai số chuẩn. Người tổng hợp không đối chiếu được nguồn gốc con số này; kết luận "P rất nhỏ" không đổi.
> - **Chú thích Hình 10.1 viết sai loại đường:** chú thích nói "đường liền biểu diễn số bé trai và bé gái bằng nhau", nhưng trên hình, đường biểu diễn tỷ số 100 là **đường nét đứt** nằm ngang; đường liền trơn là đường cong làm khớp với dữ liệu, còn đường gấp khúc màu xám là số liệu từng năm.
> - **Làm tròn nhỏ:** hiệu chỉnh Bonferroni cho con cá hồi dùng 8.000 thay vì 8.064 điểm (0,05/8.064 ≈ 1 trên 161.000, so với 1 trên 160.000 của sách); 25.000 bác sĩ đa khoa × 5% = 1.250, sách làm tròn thành "khoảng 1.300"; 3.715 ca u não trên 2.000.000 nam giới là 1 trên 538, sách ghi "khoảng 1 trên 600" vì số nam giới là "hơn 2 triệu".
> - **Các phép tính đã tự kiểm tra và khớp:** 1/2⁸² ≈ 2,1 × 10⁻²⁵ (24 số 0 sau dấu phẩy); 1/2⁸¹ ≈ 4,1 × 10⁻²⁵; 21/20 = 105 bé trai trên 100 bé gái; 9/14 = 64%, 23/40 = 57%, 32/54 = 59%; kỳ vọng 14 × 22/54 = 5,70; 54! ≈ 2,3 × 10⁷¹ và thời gian duyệt hết với tốc độ một triệu hoán vị mỗi giây ≈ 7 × 10⁵⁷ năm; 52! ≈ 8 × 10⁶⁷ và với một nghìn tỷ ván mỗi giây ≈ 2,6 × 10⁴⁸ năm; nếm trà: C(8,4) = 70; t = 0,33355/0,04600 = 7,25; 0,41175/0,04668 = 8,82; 69,22882/0,10664 = 649,2; Titanic: 0,1028/√412 = 0,0050, t = −0,0027/0,0050 = −0,54, P hai phía ≈ 0,59; 1 − 0,95² = 0,0975; 1 − 0,95¹⁰ = 0,40; 8.064 × 0,001 ≈ 8; 0,05/1.000.000 = 1 trên 20 triệu; 0,05 × 0,05 = 1/400; 0,05/25.000 = 1 trên 500.000; 105 − 59,2 = 45,8 ≈ 46; ngưỡng SPRT ln(0,99/0,01) ≈ 4,6, ln(0,9999/0,0001) ≈ 9,2, ln(0,999999/0,000001) ≈ 13,8 (khớp các vạch trên Hình 10.4); 0,69 = ln 2; cây tần số: 45/125 = 36%, 4,5/84,5 = 5,3%; u não: 3.000/600 = 5, 5 × 1,19 = 5,95 ≈ 6; 10.267 + 10.269 = 20.536 người trong HPS.
> - **Hình là đồ thị không ghi số:** Hình 10.1 (tỷ số giới tính theo năm), Hình 10.2 (hai biểu đồ cột phân phối hoán vị), Hình 10.3 (số tử vong vượt kỳ vọng cộng dồn của Shipman) và Hình 10.4 (thống kê SPRT) không ghi số; mọi con số đọc từ trục trong bản tổng hợp là **ước lượng** của người tổng hợp. Riêng Hình 10.2(b), người tổng hợp kiểm tra số đọc được với phân phối siêu bội tính tay và thấy khớp (ví dụ cột tại −3% khoảng 243 trên 1.000, tính ra 242). Hình 10.5 (cây tần số) có ghi số.
> - **Lớp chữ và chú thích:** các công thức dạng ảnh bị mất trong lớp chữ (công thức sai số chuẩn trong chú thích về Titanic, công thức khi bình phương và công thức phân phối siêu bội trong bảng thuật ngữ); bản tổng hợp viết lại theo dạng chuẩn. Danh sách chú thích dấu sao đi kèm bundle của chương này bị lệch (là chú thích của các chương khác); người tổng hợp đã đối chiếu `footnotes-all.txt` và xác định 9 chú thích chữ (về thuận tay, tỷ số odds, chữ "chi", kiểm định t ghép cặp, 1 − 0,95², việc "chấp nhận" giả thuyết không, giá trị P của Shipman, Wald và Barnard, sáu nguyên tắc ASA) cùng 6 bảng (Bảng 10.1–10.6) là của chương này.

## Sơ đồ

### Phần mở đầu chương, khung câu hỏi "Are more boys born than girls?" — Có nhiều bé trai ra đời hơn bé gái không? (trang PDF 174–176)

```text
       John Arbuthnot (bác sĩ của Nữ hoàng Anne) xem số trẻ được rửa tội ở
       London trong 82 năm, 1629–1710
       · năm nào bé trai cũng nhiều hơn bé gái
       · tỷ số giới tính chung 107 bé trai/100 bé gái, dao động 101–116
                                │
                                ▼
       Lập luận: nếu thật ra không có khác biệt, mỗi năm giống tung một
       đồng xu cân đối (50:50 trai nhiều hơn hay gái nhiều hơn)
       · 82 năm liền "trai nhiều hơn" giống 82 lần ngửa liên tiếp
       · xác suất = 1/2^82 ≈ 2 × 10^-25 (24 số 0 sau dấu phẩy)
                                │
                                ▼
       Kết luận của Arbuthnot: có một "lực" làm sinh nhiều bé trai hơn,
       ông cho là để bù cho tỷ lệ tử vong cao hơn của nam giới (và dùng
       nó làm bằng chứng cho "Ý trời")
       · ngày nay tỷ số tự nhiên được coi là khoảng 105 (21 trai/20 gái)
       · đây là kiểm định ý nghĩa thống kê đầu tiên trong lịch sử
                                │
                                ▼
       Năm câu hỏi chương sẽ trả lời, từ nhất thời tới vĩnh cửu:
       1. số vụ giết người mỗi ngày ở Anh có theo phân phối Poisson không
       2. tỷ lệ thất nghiệp ở Anh quý vừa rồi có thay đổi không
       3. statin có giảm nhồi máu cơ tim, đột quỵ ở "người như tôi" không
       4. chiều cao mẹ có liên quan chiều cao con trai khi đã tính chiều
          cao bố không
       5. hạt Higgs có tồn tại không
       → đây là phần Phân tích chính thức của chu trình PPDAC: KIỂM ĐỊNH
         GIẢ THUYẾT
```

### Mục "What Is a 'Hypothesis'?" — Giả thuyết là gì? (trang PDF 176–177)

```text
       Giả thuyết: một lời giải thích được đề xuất cho một hiện tượng
       · không phải chân lý tuyệt đối, mà là giả định làm việc tạm thời
       · giống một "nghi phạm" trong vụ án hình sự
                                │
                                ▼
       Nhắc lại từ Chương 5:
       quan sát = mô hình tất định + sai số ngẫu nhiên (phần dư)
       · phần ngẫu nhiên được mô tả bằng một phân phối xác suất
                                │
                                ▼
       Trong khoa học thống kê, giả thuyết là một giả định cụ thể về MỘT
       thành phần của mô hình thống kê, mang tính tạm thời
```

### Mục "Why Do We Need Formal Testing of Null Hypotheses?" — Vì sao cần kiểm định chính thức giả thuyết không? (trang PDF 177–181)

```text
       Con người thích phát hiện tới mức hay "thấy" điều không có
       (apophenia — thấy quy luật ở nơi không có quy luật)
       · có thể có lợi cho người săn bắt hái lượm (chạy trước khi biết
         chắc bụi cây có hổ), nhưng phá hỏng khoa học
       · cần một cơ chế chống phát hiện giả: kiểm định giả thuyết
                                │
                                ▼
       GIẢ THUYẾT KHÔNG (H0): dạng đơn giản hoá của mô hình, giữ nguyên
       cho tới khi có đủ bằng chứng chống lại nó
       · luôn "phủ định": không thay đổi, không tác dụng, không tồn tại
       · không ai tin nó đúng tuyệt đối; nó KHÔNG BAO GIỜ được chứng minh
         (Fisher: thí nghiệm chỉ cho dữ kiện cơ hội bác bỏ nó)
       · giống toà án Anh: có thể bị kết "có tội", không ai được tuyên
         "vô tội", chỉ là "chưa chứng minh được có tội"
                                │
                                ▼
       VÍ DỤ KHOANH TAY: 54 nghiên cứu sinh ở Viện Khoa học Toán học châu
       Phi (2013)
       · nữ: 9/14 = 64% tay phải ở trên; nam: 23/40 = 57%
       · chênh lệch quan sát 7%; H0: khoanh tay không liên quan giới tính
       · câu hỏi: 7% có "tương thích" với H0 không?
                                │
                                ▼
       KIỂM ĐỊNH HOÁN VỊ: trộn 54 "vé khoanh tay" rồi chia ngẫu nhiên lại
       cho 14 nữ và 40 nam, tính chênh lệch; lặp 1.000 lần
       · phân phối chênh lệch đối xứng quanh 0; 7% nằm gần giữa
       · duyệt hết mọi hoán vị là không thể (54! ≈ 2 × 10^71 cách)
       · lý thuyết cho phân phối chính xác: PHÂN PHỐI SIÊU BỘI
                                │
                                ▼
       GIÁ TRỊ P = xác suất có kết quả cực đoan ít nhất như đã thấy, nếu
       H0 (và mọi giả định khác của mô hình) đúng
       · một phía (chỉ chiều "nữ nhiều hơn"): 0,45
       · hai phía (cả hai chiều): 0,89 → không có bằng chứng chống H0
       · Arbuthnot: 1/2^82 là một phía; nhân đôi thành 1/2^81 là giá trị P
         hai phía đầu tiên được ghi nhận
```

### Mục "Statistical Significance" — Ý nghĩa thống kê (trang PDF 181–182)

```text
       Giá trị P đủ nhỏ thì kết quả "có ý nghĩa thống kê"
       (thuật ngữ do Ronald Fisher phổ biến từ thập niên 1920)
       · Fisher: tiên phong cả di truyền học lẫn thống kê; tính khí khó
         chịu, ủng hộ thuyết ưu sinh, công khai nghi ngờ bằng chứng hút
         thuốc gây ung thư phổi, có quan hệ tài chính với ngành thuốc lá
                                │
                                ▼
       Thí nghiệm nếm trà: 8 cốc (4 rót sữa trước, 4 rót trà trước), bày
       ngẫu nhiên; bà Muriel Bristol (được cho là) đoán đúng cả 4
       · xác suất đoán bừa mà đúng hết = 1/70 (phân phối siêu bội)
       · P nhỏ → có ý nghĩa thống kê
                                │
                                ▼
       SÁU BƯỚC (Kiểm định ý nghĩa giả thuyết không, NHST):
       1. đặt câu hỏi dưới dạng giả thuyết không H0
       2. chọn thống kê kiểm định (giá trị đủ cực đoan làm ta nghi H0)
       3. tạo phân phối lấy mẫu của thống kê đó nếu H0 đúng
       4. xem giá trị quan sát có nằm ở đuôi không; tóm bằng giá trị P
       5. định nghĩa "cực đoan" cẩn thận (một phía hay hai phía)
       6. tuyên bố có ý nghĩa nếu P nhỏ hơn một ngưỡng
                                │
                                ▼
       Ngưỡng 0,05 và 0,01 của Fisher thành quy ước nhờ bảng tra của ông
       · nay nên báo cáo giá trị P chính xác
       · giá trị P phụ thuộc cả H0 lẫn MỌI giả định khác (không thiên
         lệch hệ thống, quan sát độc lập...)
```

### Mục "Using Probability Theory" — Dùng lý thuyết xác suất (trang PDF 182–187)

```text
       Bước khó nhất là bước 3; có thể mô phỏng, nhưng tiện hơn nếu lý
       thuyết xác suất cho sẵn diện tích đuôi
                                │
                                ▼
       KIỂM ĐỊNH KHI BÌNH PHƯƠNG (Karl Pearson, khoảng 1900)
       · tính số kỳ vọng mỗi ô nếu không có liên hệ, ví dụ nữ tay trái ở
         trên: 14 × 22/54 = 5,7
       · đo tổng chênh lệch quan sát–kỳ vọng: 0,02; P = 0,90
         (gần như trùng phép kiểm định chính xác)
                                │
                                ▼
       Trả lời lại các câu hỏi:
       1. Giết người và Poisson: 1.545 vụ/1.095 ngày = 1,41 vụ/ngày;
          kiểm định khớp phân phối khi bình phương, P = 0,96 → không bác
          bỏ (khớp "tốt đến mức đáng ngờ"); dùng làm giả định được
       2. Thất nghiệp: −3.000 ± 77.000, khoảng 95% từ −80.000 tới +74.000
          chứa 0 → không có ý nghĩa
          · khoảng tin cậy 95% không chứa 0 ⇔ P hai phía < 0,05
          · khoảng tin cậy 95% = tập các giả thuyết không KHÔNG bị bác bỏ
            ở mức 0,05
       3. Statin (HPS): giảm 27% nhồi máu cơ tim, 25% đột quỵ, 13% tử vong
          mọi nguyên nhân; khoảng tin cậy loại trừ 0; P rất nhỏ
       4. Chiều cao (dữ liệu Galton, kết quả của phần mềm R):
          t = ước lượng / sai số chuẩn; mẹ t = 7,25, bố t = 8,82
          · |t| > 2 ứng với P < 0,05 khi mẫu lớn; R đánh dấu sao
       ·  Titanic: cây phân loại thắng mạng nơ-ron với điểm Brier 0,139 so
          với 0,142; kiểm định t ghép cặp: t = −0,54, P = 0,59
          → chiến thắng có thể chỉ do may mắn
```

### Mục "The Danger of Carrying Out Many Significance Tests" — Nguy cơ khi làm nhiều kiểm định ý nghĩa (trang PDF 187–188)

```text
       Thuốc vô dụng, ngưỡng 0,05:
       · 1 thử nghiệm: 5% khả năng "có ý nghĩa" (dương tính giả)
       · 2 thử nghiệm: 1 − 0,95² ≈ 10%
       · 10 thử nghiệm: 1 − 0,95^10 ≈ 40%
       = vấn đề KIỂM ĐỊNH NHIỀU LẦN (báo cáo kết quả nổi bật nhất)
                                │
                                ▼
       Cá hồi chết (2009): chụp fMRI não một con cá hồi Đại Tây Dương nặng
       khoảng 1,8 kg đã chết khi cho "xem" ảnh người biểu lộ cảm xúc
       · 16 trên 8.064 điểm "phản ứng có ý nghĩa" ở ngưỡng 0,001
       · chỉ do ngẫu nhiên đã kỳ vọng khoảng 8
                                │
                                ▼
       Cách chữa:
       · HIỆU CHỈNH BONFERRONI: ngưỡng 0,05/n
         (cá hồi: 0,05/8.000 = 1 trên 160.000; hệ gen: 0,05/1.000.000 =
         1 trên 20 triệu)
       · kiểm soát TỶ LỆ PHÁT HIỆN SAI: nới dần ngưỡng cho kết quả cực
         đoan thứ hai, thứ ba...
       · đòi LẶP LẠI nghiên cứu: FDA cần 2 thử nghiệm độc lập đều P < 0,05
         → thuốc vô dụng được duyệt với xác suất 0,05 × 0,05 = 1/400
                                │
                                ▼
       5. Hạt Higgs (CERN, 2012): "cái bướu" trên đường cong tần suất sự
          kiện đúng chỗ dự đoán; P < 1 trên 3,5 triệu nếu Higgs không tồn
          tại
          · "năm sigma" = cách giả thuyết không 5 sai số chuẩn (giống giá
            trị t)
          · phải tính tới "hiệu ứng nhìn chỗ khác" (kiểm định ở mọi mức
            năng lượng) và muốn chắc chắn sẽ lặp lại được
          · Higgs tồn tại trở thành giả thuyết không MỚI
```

### Mục "Neyman—Pearson Theory" và khung câu hỏi "Why did the Heart Protection Study need over 20,000 participants?" — Lý thuyết Neyman–Pearson (trang PDF 188–190)

```text
       Fisher (thập niên 1920): giá trị P là công cụ không chính thức để
       kiểm tra một giả thuyết; P càng nhỏ, càng nhiều bằng chứng chống H0
                                │
                                ▼
       Neyman và Pearson (thập niên 1930): "hành vi quy nạp", chặt chẽ hơn
       · thêm GIẢ THUYẾT ĐỐI
       · hai quyết định: bác bỏ H0 để theo giả thuyết đối, hoặc không bác
         bỏ H0
                                │
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       SAI LẦM LOẠI I                    SAI LẦM LOẠI II
       bác bỏ H0 khi H0 đúng             không bác bỏ H0 khi giả thuyết
       (kết tội người vô tội)            đối đúng (tha người có tội)
       xác suất = MỨC α                  xác suất = β
       ("size", thường 0,05)             LỰC KIỂM ĐỊNH = 1 − β
                                         (khả năng phát hiện hiệu ứng thật)
               └────────────────┬────────────────┘
                                ▼
       α chính là ngưỡng của giá trị P: bác bỏ H0 khi P < α
       · cỡ mẫu cố định thì phải đánh đổi: nới ngưỡng để tăng lực thì
         tăng α
                                │
                                ▼
       Lập kế hoạch thử nghiệm lâm sàng: chọn α và lực → ra cỡ mẫu
       · thường α = 0,05, lực 80%
       · HPS: lực > 90% để đạt P < 0,01 nếu statin giảm 25% tử vong mạch
         vành và 15% tử vong mọi nguyên nhân → cần hơn 20.000 người
       · kết quả thật: giảm 13% tử vong mọi nguyên nhân, rất gần kế hoạch
       · tâm lý học, thần kinh học: có khi chỉ 20 người mỗi nhóm → bỏ sót
         hiệu ứng thật
                                │
                                ▼
       Thực tế là "hỗn hợp kỳ lạ nhưng hiệu quả": THIẾT KẾ theo Neyman–
       Pearson, PHÂN TÍCH bằng khoảng tin cậy và giá trị P kiểu Fisher
```

### Khung câu hỏi "Could Harold Shipman have been caught earlier?" — Có thể bắt Harold Shipman sớm hơn không? (trang PDF 191–196)

```text
       Số giấy chứng tử Shipman ký (bệnh nhân ≥ 65 tuổi, chết tại nhà hoặc
       phòng khám), 1977–1998, trừ số kỳ vọng theo cơ cấu tuổi và tỷ lệ tử
       vong của các bác sĩ đa khoa lân cận
       · tử vong vượt kỳ vọng đến 1998: 174 nữ, 49 nam — gần đúng số nạn
         nhân lớn tuổi mà cuộc điều tra công khai xác nhận
                                │
                                ▼
       Kiểm định ý nghĩa mỗi cuối năm (H0: số chết cộng dồn theo Poisson
       với kỳ vọng cộng dồn)
       · 1979: quan sát 40, kỳ vọng 25,3, P một phía 0,004 → "có ý nghĩa"
                                │
                                ▼
       Hai lý do cách làm này SAI khi áp cho mọi bác sĩ:
       1. khoảng 25.000 bác sĩ đa khoa × 5% ≈ 1.250 (sách: khoảng 1.300)
          bác sĩ vô tội bị báo động mỗi lần → Shipman lẫn trong đám đông
          · Bonferroni: ngưỡng 0,05/25.000 = 1 trên 500.000 → Shipman vượt
            năm 1984 (105 ca, kỳ vọng 59,2, vượt 46)
       2. KIỂM ĐỊNH LẶP LẠI trên dữ liệu tích luỹ: theo "luật lôgarit lặp",
          dù H0 đúng, sớm muộn gì cũng CHẮC CHẮN bác bỏ ở mọi ngưỡng
                                │
                                ▼
       Giải pháp: KIỂM ĐỊNH TUẦN TỰ — Kiểm định tỷ số xác suất tuần tự
       (SPRT), sinh ra trong Thế chiến II cho kiểm soát chất lượng vũ khí
       (Wald ở Mỹ, Barnard ở Anh)
       · thống kê = 0,69 × số chết quan sát cộng dồn − số chết kỳ vọng
         cộng dồn (giả thuyết đối: tỷ lệ tử vong gấp đôi)
       · ngưỡng = ln((1 − β)/α), với α = β = 1/100, 1/10.000, 1/1.000.000
       · nữ vượt ngưỡng 1 phần triệu năm 1985; cả nam và nữ: năm 1984
                                │
                                ▼
       Nếu điều tra năm 1984: khoảng 175 người có thể được cứu
       · hệ thống thí điểm sau đó báo động ngay một bác sĩ tử vong còn cao
         hơn — hoá ra ông làm việc ở thị trấn ven biển nhiều nhà dưỡng lão
         và tận tâm giúp bệnh nhân được mất tại nhà
       · bài học: thống kê phát hiện điểm bất thường, không giải thích
         nguyên nhân; phải triển khai cẩn thận để tránh buộc tội oan
```

### Khung câu hỏi "What could go wrong with P-values?" — Giá trị P có thể sai ở đâu? (trang PDF 196–201)

```text
       Fisher hình dung: một bộ dữ liệu, một thước đo, một kiểm định
       Thực tế: giá trị P thành "tiền tệ" của nghiên cứu (một nghiên cứu
       gom khoảng 30.000 thống kê t từ 3 năm của 18 tạp chí tâm lý, thần
       kinh học)
                                │
                                ▼
       CÂY TẦN SỐ 1.000 nghiên cứu (α = 5%, lực 80%, 10% giả thuyết không
       thật sự sai):
       · 100 H0 sai → 80 bác bỏ đúng, 20 bỏ sót
       · 900 H0 đúng → 45 bác bỏ sai, 855 không bác bỏ
       · 125 "phát hiện", trong đó 45 (36%) là sai
       · tạp chí ưu tiên kết quả dương tính → càng tệ hơn (Ioannidis 2005:
         "phần lớn kết quả nghiên cứu công bố là sai")
                                │
                                ▼
       2015: một tạp chí tâm lý học cấm dùng NHST
       2016: Hiệp hội Thống kê Mỹ (ASA) đưa ra SÁU NGUYÊN TẮC:
       1. P cho biết dữ liệu không tương thích với mô hình đến đâu
       2. P KHÔNG phải xác suất giả thuyết đúng, cũng không phải xác suất
          dữ liệu "chỉ do ngẫu nhiên" (ngộ nhận của bên công tố — Higgs:
          BBC nói đúng, Forbes và The Independent nói sai)
       3. kết luận và quyết định không được chỉ dựa vào việc P qua ngưỡng
          · "không có ý nghĩa" ≠ "không có hiệu ứng" (The Times: "Rượu rốt
            cuộc chẳng có lợi gì cho sức khoẻ")
       4. suy luận đúng cần báo cáo đầy đủ, minh bạch (đã làm bao nhiêu
          kiểm định)
       5. P không đo độ lớn hay tầm quan trọng của hiệu ứng
          · học đại học và u não: tăng 19% (khoảng 7%–33%), nhưng chỉ là 5
            so với 6 ca trên 3.000 nam giới → có ý nghĩa thống kê, không có
            ý nghĩa thực tế
       6. riêng một giá trị P không phải thước đo bằng chứng tốt; P gần
          0,05 chỉ là bằng chứng yếu
          · đề xuất đổi ngưỡng "phát hiện" thành P < 0,005: phát hiện sai
            giảm từ 45 còn 4,5 (36% còn 5%)
                                │
                                ▼
       Cảnh báo "giả kim thuật": biến bất định thành chắc chắn bằng cách
       chia máy móc mọi kết quả thành "có" và "không có ý nghĩa"
       → chương sau: cách tiếp cận Bayes, bác bỏ hẳn kiểm định giả thuyết
         không
```

### Phần "Summary" — Tóm tắt (trang PDF 202)

```text
       · Kiểm định giả thuyết không (giả định mặc định về mô hình) là phần
         lớn của thực hành thống kê
       · Giá trị P đo mức không tương thích giữa dữ liệu và H0: xác suất
         có kết quả cực đoan như vậy nếu H0 đúng
       · Ngưỡng truyền thống 0,05 và 0,01 để tuyên bố "có ý nghĩa"
       · Phải điều chỉnh ngưỡng khi làm nhiều kiểm định (nhiều nhóm con,
         nhiều thước đo kết cục)
       · Khoảng tin cậy và giá trị P tương ứng chính xác: khoảng 95% loại
         trừ 0 thì bác bỏ H0 "bằng 0" ở P < 0,05
       · Neyman–Pearson: thêm giả thuyết đối, cố định tỷ lệ sai lầm loại I
         và loại II
       · Có các dạng kiểm định riêng cho kiểm định tuần tự
       · Giá trị P hay bị hiểu sai: không phải xác suất H0 đúng; "không có
         ý nghĩa" không có nghĩa H0 đúng
```

## Ba câu hỏi chương này trả lời

1. **Làm sao biết một khác biệt quan sát được là "thật" hay chỉ do ngẫu nhiên?** Đặt một giả thuyết không — giả định rằng không có khác biệt, không có tác dụng — rồi hỏi: nếu giả thuyết đó đúng, khả năng thấy một kết quả cực đoan ít nhất như đã thấy là bao nhiêu? Con số đó là giá trị P. Phân phối của thống kê dưới giả thuyết không có thể tạo bằng mô phỏng (kiểm định hoán vị) hoặc bằng lý thuyết xác suất (phân phối siêu bội, kiểm định khi bình phương, thống kê t). Arbuthnot: 82 năm liền bé trai nhiều hơn, P = 1/2⁸² — bác bỏ giả thuyết "50:50". Khoanh tay: nữ 64% so với nam 57%, P hai phía 0,89 — không có bằng chứng. Statin: giảm 27% nhồi máu cơ tim, khoảng tin cậy 21%–33%, P < 0,0001 — bằng chứng rất mạnh. Khoảng tin cậy và giá trị P là hai mặt của cùng một phép tính: khoảng 95% không chứa 0 khi và chỉ khi P hai phía nhỏ hơn 0,05.
2. **Khi nào một "phát hiện có ý nghĩa thống kê" vẫn có thể là sai?** Khi làm nhiều kiểm định rồi chọn kết quả nổi bật nhất (10 kiểm định với thuốc vô dụng: 40% khả năng có ít nhất một kết quả "có ý nghĩa"; con cá hồi chết có 16 trên 8.064 vùng não "phản ứng"); khi kiểm định lặp lại trên dữ liệu tích luỹ (theo luật lôgarit lặp, sớm muộn gì cũng bác bỏ giả thuyết không đúng); và khi phần lớn giả thuyết được kiểm định vốn đúng (với α = 5%, lực 80% và chỉ 10% giả thuyết không sai, 45 trên 125 "phát hiện", tức 36%, là sai). Cách chữa: hiệu chỉnh Bonferroni (ngưỡng 0,05/n), kiểm soát tỷ lệ phát hiện sai, đòi hỏi lặp lại (FDA: hai thử nghiệm, xác suất duyệt nhầm thuốc vô dụng 1/400), kiểm định tuần tự (SPRT), ngưỡng chặt hơn (năm sigma của hạt Higgs; đề xuất P < 0,005).
3. **Giá trị P KHÔNG nói gì?** Nó không phải xác suất giả thuyết không đúng, cũng không phải xác suất kết quả "chỉ do may rủi" (báo chí viết sai về hạt Higgs); "không có ý nghĩa" không có nghĩa "không có hiệu ứng" (rượu: khoảng tin cậy rộng vẫn tương thích với mức giảm tử vong 10%–20%); "có ý nghĩa" không có nghĩa "quan trọng" (học đại học tăng nguy cơ u não 19%, tức 6 so với 5 ca trên 3.000 nam giới, chỉ phát hiện được vì có hơn 2 triệu người); và riêng một giá trị P gần 0,05 chỉ là bằng chứng yếu. Cũng vì vậy, thống kê phát hiện được điểm bất thường (Shipman) nhưng không giải thích được nguyên nhân (vị bác sĩ ở thị trấn nhiều nhà dưỡng lão).

## Khái niệm cần biết

- **Giả thuyết (hypothesis):** một lời giải thích được đề xuất cho một hiện tượng; trong thống kê là một giả định cụ thể, mang tính tạm thời, về một thành phần của mô hình (phần tất định hoặc phần ngẫu nhiên). Ví dụ: "số vụ giết người mỗi ngày theo phân phối Poisson với trung bình 1,41". Quan trọng vì mọi kiểm định đều kiểm tra một giả định cụ thể chứ không kiểm tra "sự thật".
- **Giả thuyết không (null hypothesis, H0):** dạng đơn giản nhất của mô hình, thường là "không có hiệu ứng, không có thay đổi, không tồn tại", được giữ cho tới khi có đủ bằng chứng chống lại. Ví dụ: "khoanh tay không liên quan tới giới tính", nên chênh lệch kỳ vọng là 0%. Quan trọng vì giả thuyết không chỉ có thể bị bác bỏ, không bao giờ được chứng minh — như bị cáo chỉ được tuyên "không có tội" chứ không được tuyên "vô tội".
- **Giả thuyết đối (alternative hypothesis):** lời giải thích thay thế, thường là một hiệu ứng vừa hợp lý vừa đáng kể. Ví dụ: trong HPS, "statin giảm 25% tử vong mạch vành và 15% tử vong mọi nguyên nhân"; với Shipman, "tỷ lệ tử vong gấp đôi đồng nghiệp". Quan trọng vì không có giả thuyết đối thì không tính được lực kiểm định và cỡ mẫu.
- **Thống kê kiểm định (test statistic):** một con số tóm tắt dữ liệu mà nếu nó đủ cực đoan sẽ khiến ta nghi ngờ giả thuyết không. Ví dụ: chênh lệch tỷ lệ 7% trong ví dụ khoanh tay; thống kê khi bình phương 0,02; thống kê t = 7,25. Quan trọng vì giá trị P được tính trên thống kê này.
- **Bảng chéo / bảng tiếp liên (cross-tabulation / contingency table):** bảng đếm số quan sát theo hai biến phân loại. Ví dụ: 54 sinh viên chia theo giới tính và tay nào ở trên (5, 17, 9, 23). Quan trọng vì đây là dạng dữ liệu của kiểm định khi bình phương về liên hệ.
- **Kiểm định hoán vị (permutation / randomization test):** tạo phân phối của thống kê dưới giả thuyết không bằng cách xáo trộn ngẫu nhiên nhãn (ở đây là "vé khoanh tay") rồi tính lại thống kê nhiều lần. Ví dụ: 1.000 lần xáo trộn cho phân phối chênh lệch đối xứng quanh 0, khoảng 45% số lần có chênh lệch từ 7% trở lên nghiêng về nữ. Quan trọng vì không cần toán phức tạp, chỉ cần máy tính.
- **Phân phối siêu bội (hypergeometric distribution):** xác suất có k "thành công" khi rút n lần không hoàn lại từ một tổng thể N phần tử có K thành công: C(K, k) × C(N − K, n − k) / C(N, n). Ví dụ: xác suất đoán đúng cả 4 cốc trà rót sữa trước trong 8 cốc là 1/C(8,4) = 1/70; trong ví dụ khoanh tay, xác suất đúng 9 trong 14 nữ là người "tay phải ở trên" khi 32 trong 54 người như vậy là khoảng 0,23. Quan trọng vì nó cho phân phối chính xác mà kiểm định hoán vị chỉ ước lượng.
- **Giá trị P (P-value):** xác suất có được kết quả cực đoan ít nhất như đã quan sát, nếu giả thuyết không (và mọi giả định khác của mô hình) đúng; về hình học là một diện tích đuôi. Ví dụ: khoanh tay, P một phía 0,45; Shipman năm 1979, P = 0,004. Quan trọng vì đây là khái niệm nổi bật nhất của thống kê hiện nay và cũng bị hiểu sai nhiều nhất.
- **Kiểm định một phía và hai phía (one-sided / two-sided test; one-tailed / two-tailed P-value):** một phía chỉ coi giá trị lớn theo một chiều là cực đoan; hai phía coi cả hai chiều. Ví dụ: Arbuthnot 1/2⁸² (một phía) và 1/2⁸¹ (hai phía); Shipman dùng một phía vì chỉ quan tâm tử vong tăng. Quan trọng vì giá trị P hai phía thường gấp đôi một phía.
- **Ý nghĩa thống kê (statistical significance):** kết quả được gọi là có ý nghĩa thống kê khi giá trị P nhỏ hơn một ngưỡng định trước, thường 0,05 hoặc 0,01. Ví dụ: nếm trà, P = 1/70 ≈ 0,014 < 0,05. Quan trọng vì ngưỡng này, vốn là lựa chọn khá tuỳ tiện của Fisher, nay chi phối việc công bố khoa học.
- **Kiểm định ý nghĩa giả thuyết không (Null Hypothesis Significance Testing, NHST):** toàn bộ quy trình sáu bước từ đặt H0 tới tuyên bố có ý nghĩa. Quan trọng vì đây là đối tượng tranh cãi chính của chương.
- **Kiểm định khi bình phương (chi-squared test) về liên hệ và về độ khớp (association / goodness-of-fit):** so số đếm quan sát o với số kỳ vọng e dưới giả thuyết không bằng thống kê X² = Σ (o − e)²/e, có phân phối xấp xỉ khi bình phương. Ví dụ: số ngày có 0, 1, 2… vụ giết người so với kỳ vọng Poisson, P = 0,96. Quan trọng vì cho giá trị P mà không cần mô phỏng.
- **Thống kê t (t-statistic, t-value), phân phối Student:** ước lượng chia cho sai số chuẩn, tức ước lượng cách 0 bao nhiêu sai số chuẩn. Ví dụ: hệ số chiều cao mẹ 0,33355 / 0,04600 = 7,25. Với mẫu lớn, |t| > 2 ứng với P < 0,05. "Student" là bút danh của William Gosset, người làm cho hãng bia Guinness.
- **Kiểm định t ghép cặp (paired t-test):** kiểm định t trên tập hiệu số giữa từng cặp quan sát. Ví dụ: 412 hiệu số sai số dự báo bình phương giữa hai thuật toán Titanic, trung bình −0,0027, độ lệch chuẩn 0,1028, sai số chuẩn 0,0050, t = −0,54. Quan trọng vì cho thấy "người thắng" một cuộc thi dự báo có thể chỉ thắng nhờ may.
- **Dương tính giả (false-positive):** tuyên bố có hiệu ứng khi thật ra không có. Ví dụ: kết luận thuốc vô dụng là có hiệu quả vì P < 0,05 (xác suất 5% mỗi lần). Quan trọng vì làm nhiều kiểm định thì dương tính giả gần như chắc chắn xảy ra.
- **Kiểm định nhiều lần (multiple testing):** làm nhiều kiểm định rồi báo cáo kết quả có ý nghĩa nhất, làm tăng xác suất có ít nhất một dương tính giả. Ví dụ: 10 kiểm định với thuốc vô dụng, xác suất ít nhất một P < 0,05 là 1 − 0,95¹⁰ = 40%.
- **Hiệu chỉnh Bonferroni (Bonferroni correction):** khi làm n kiểm định, dùng ngưỡng 0,05/n cho từng kiểm định. Ví dụ: 25.000 bác sĩ đa khoa, ngưỡng 0,05/25.000 = 1 trên 500.000. Quan trọng vì là cách đơn giản nhất để giữ xác suất có ít nhất một dương tính giả ở mức 5%.
- **Tỷ lệ phát hiện sai (false discovery rate):** tỷ lệ các "phát hiện" (giả thuyết không bị bác bỏ) hoá ra là sai. Ví dụ: trong cây 1.000 nghiên cứu, 45/125 = 36%. Các phương pháp kiểm soát tỷ lệ này nới nhẹ ngưỡng Bonferroni cho kết quả cực đoan thứ hai, thứ ba…
- **Lặp lại nghiên cứu (replication):** làm lại thí nghiệm trong hoàn cảnh khác với cùng quy trình. Ví dụ: FDA đòi hai thử nghiệm độc lập đều có P < 0,05, nên xác suất duyệt một thuốc vô dụng là 0,05 × 0,05 = 1/400.
- **"Năm sigma" (five-sigma) và hiệu ứng nhìn chỗ khác (look elsewhere effect):** trong vật lý, kết quả "k sigma" là quan sát cách giả thuyết không k sai số chuẩn, giống giá trị t; năm sigma ứng với giá trị P khoảng 1 trên 3,5 triệu (một phía). Hiệu ứng nhìn chỗ khác là tên trong vật lý của việc hiệu chỉnh kiểm định nhiều lần khi tìm tín hiệu ở mọi mức năng lượng.
- **Sai lầm loại I và mức của kiểm định (Type I error, size, α):** bác bỏ giả thuyết không khi nó đúng; xác suất của nó khi H0 đúng gọi là mức của kiểm định, ký hiệu α, cũng chính là ngưỡng của giá trị P. Ví dụ: α = 0,05 nghĩa là bác bỏ H0 với mọi P < 0,05. Tương tự kết tội người vô tội.
- **Sai lầm loại II và lực kiểm định (Type II error, β, power 1 − β):** không bác bỏ giả thuyết không khi giả thuyết đối đúng (tha kẻ có tội), xác suất là β; lực kiểm định 1 − β là khả năng phát hiện đúng một hiệu ứng thật. Ví dụ: HPS thiết kế với lực trên 90% ở mức α = 0,01. Quan trọng vì lực quyết định cỡ mẫu; nghiên cứu quá nhỏ bỏ sót hiệu ứng thật.
- **Kiểm định tuần tự (sequential testing):** kiểm định lặp lại trên dữ liệu tích luỹ dần. Nếu dùng ngưỡng thông thường, theo **luật lôgarit lặp (Law of the Iterated Logarithm)**, dù H0 đúng thì sớm muộn cũng chắc chắn bác bỏ nó. Cần phương pháp riêng.
- **Kiểm định tỷ số xác suất tuần tự (Sequential Probability Ratio Test, SPRT):** thống kê theo dõi bằng chứng tích luỹ, so liên tục với các ngưỡng cố định, vượt ngưỡng thì báo động; ngưỡng được chọn để giữ xác suất sai lầm loại I và loại II tổng thể ở mức định trước. Ví dụ: với Shipman, SPRT = 0,69 × số chết quan sát cộng dồn − số chết kỳ vọng cộng dồn, ngưỡng ln((1 − β)/α) ≈ 13,8 với α = β = 1 phần triệu; Shipman vượt năm 1984.
- **Ý nghĩa thực tế (practical significance):** hiệu ứng có tầm quan trọng thật. Ví dụ: tăng 19% nguy cơ u não có ý nghĩa thống kê nhưng chỉ là 1 ca thêm trên 3.000 nam giới. Quan trọng vì dữ liệu lớn dễ cho kết quả có ý nghĩa thống kê mà không có ý nghĩa thực tế.
- **Ngộ nhận của bên công tố (prosecutor's fallacy):** đảo chiều xác suất có điều kiện. Ví dụ: diễn giải "P = 1 trên 3,5 triệu" thành "xác suất không phải hạt Higgs là dưới 1 phần triệu" (Forbes). Quan trọng vì đây là lỗi phổ biến nhất khi đọc giá trị P.

## Nội dung chi tiết

### 1. Có nhiều bé trai ra đời hơn bé gái không? (phần mở đầu chương, khung câu hỏi "Are more boys born than girls?", trang PDF 174–176)

John Arbuthnot, một bác sĩ trở thành ngự y của Nữ hoàng Anne năm 1705, muốn trả lời câu hỏi này. Ông xem số liệu rửa tội ở London trong 82 năm, từ 1629 tới 1710 (1710 − 1629 + 1 = 82 năm), và trình bày kết quả dưới dạng mà ngày nay gọi là **tỷ số giới tính (sex ratio)**: số bé trai sinh ra trên 100 bé gái.

**Số liệu của Arbuthnot (Hình 10.1 trong sách, đồ thị không ghi số; các mức dưới đây là ước lượng của người tổng hợp đọc từ trục):** trục tung là tỷ số giới tính, từ 90 tới 120; trục hoành là năm, từ 1629 tới 1710. Đường gấp khúc màu xám là tỷ số từng năm; một đường nét đứt nằm ngang ở mức 100 biểu diễn số trai và gái bằng nhau; một đường cong liền trơn được làm khớp với dữ liệu.

| Đặc điểm | Giá trị (ước lượng đọc từ hình, trừ dòng có nguồn từ lời văn) |
|---|---|
| Tỷ số chung cả giai đoạn (lời văn) | 107 |
| Khoảng dao động từng năm (lời văn) | 101 tới 116 |
| Các đỉnh cao nhất | khoảng 114 (đầu thập niên 1650) và khoảng 115–116 (khoảng 1659–1661) |
| Mức thấp nhất | khoảng 101 (đầu thập niên 1700) |
| Đường cong làm khớp | khoảng 107 năm 1629, nhích lên khoảng 108 quanh 1655–1660, giảm về khoảng 106 trong giai đoạn 1680–1700, khoảng 106,5 năm 1710 |
| Số năm tỷ số dưới 100 | không năm nào |

Arbuthnot thấy năm nào số bé trai được rửa tội cũng nhiều hơn bé gái. Nhưng ông muốn khẳng định một quy luật tổng quát hơn, nên lập luận: nếu thật ra tỷ lệ sinh bé trai và bé gái như nhau, thì mỗi năm có 50% khả năng trai nhiều hơn gái và 50% khả năng gái nhiều hơn trai, giống tung một đồng xu. Khi đó, việc năm nào trai cũng nhiều hơn giống như tung đồng xu cân đối 82 lần và lần nào cũng ra mặt ngửa. Xác suất của điều này là 1/2⁸², khoảng 2,1 × 10⁻²⁵, tức có 24 chữ số 0 sau dấu phẩy trước chữ số khác 0 đầu tiên. Nếu thấy chuyện như vậy trong một thí nghiệm thật, ta sẽ tự tin nói đồng xu không cân đối. Tương tự, Arbuthnot kết luận có một lực nào đó làm sinh nhiều bé trai hơn, và ông cho rằng đó là để bù cho tỷ lệ tử vong cao hơn của nam giới: "Để bù đắp mất mát ấy, Tự nhiên chu đáo, theo sự sắp đặt của Đấng Sáng tạo khôn ngoan, sinh ra nhiều nam hơn nữ, và gần như theo một tỷ lệ cố định."

Số liệu của Arbuthnot đã được phân tích lại nhiều lần. Có thể có lỗi đếm, và chỉ các lễ rửa tội của Giáo hội Anh được tính, nhưng phát hiện cơ bản vẫn đúng: ngày nay tỷ số giới tính "tự nhiên" được coi là khoảng 105, nghĩa là cứ 20 bé gái thì có 21 bé trai. Tiêu đề bài báo của ông dùng dữ liệu làm bằng chứng thống kê trực tiếp cho sự can thiệp siêu nhiên: "Một luận cứ cho Ý trời, rút ra từ tính đều đặn bất biến quan sát được trong số sinh của hai giới". Dù kết luận đó có chính đáng hay không, và dù ông không biết, Arbuthnot đã đi vào lịch sử vì thực hiện **kiểm định ý nghĩa thống kê đầu tiên** trên thế giới.

Spiegelhalter nói chương này là phần có lẽ quan trọng nhất của chu trình giải quyết vấn đề: tìm câu trả lời cho các câu hỏi cụ thể về cách thế giới vận hành. Ông nêu năm câu hỏi, đa dạng từ nhất thời tới vĩnh cửu:

| Câu hỏi | Tính chất |
|---|---|
| 1. Số vụ giết người mỗi ngày ở Anh có theo phân phối Poisson không? | Một quy luật chung, công chúng không mấy quan tâm, nhưng giúp trả lời liệu tỷ lệ nền có thay đổi không |
| 2. Tỷ lệ thất nghiệp ở Anh có thay đổi trong quý vừa qua không? | Câu hỏi cụ thể về một thời điểm, một nơi |
| 3. Uống statin có giảm nguy cơ nhồi máu cơ tim và đột quỵ ở những người như tôi không? | Một khẳng định khoa học nhưng riêng cho một nhóm |
| 4. Chiều cao của mẹ có liên quan tới chiều cao con trai khi đã tính tới chiều cao của bố không? | Có thể có ý nghĩa khoa học chung |
| 5. Hạt Higgs có tồn tại không? | Có thể thay đổi những ý niệm cơ bản về các định luật vật lý của vũ trụ |

Với những câu hỏi này, các chương trước đã có dữ liệu, đã vẽ đồ thị khám phá và rút ra một số kết luận không chính thức về mô hình thống kê phù hợp. Chương này đi vào khía cạnh chính thức của bước Phân tích trong chu trình PPDAC, thường gọi là **kiểm định giả thuyết (hypothesis testing)**.

### 2. Giả thuyết là gì? (What Is a 'Hypothesis'?, trang PDF 176–177)

Có thể định nghĩa giả thuyết là một lời giải thích được đề xuất cho một hiện tượng. Nó không phải chân lý tuyệt đối mà là một giả định làm việc tạm thời; cách hình dung tốt nhất có lẽ là một "nghi phạm" trong một vụ án hình sự.

Khi bàn về hồi quy ở Chương 5, sách đã nêu: *quan sát = mô hình tất định + sai số phần dư*. Ý tưởng là mô hình thống kê là biểu diễn toán học của điều ta quan sát, gồm một thành phần tất định và một thành phần "ngẫu nhiên" (stochastic) thể hiện tính không dự đoán được hay "sai số" ngẫu nhiên, thường được mô tả bằng một phân phối xác suất. Trong khoa học thống kê, một giả thuyết là một giả định cụ thể về một trong các thành phần này của mô hình, với hàm ý là tạm thời chứ không phải "sự thật".

### 3. Vì sao cần kiểm định chính thức giả thuyết không? (Why Do We Need Formal Testing of Null Hypotheses?, trang PDF 177–181)

#### Xu hướng "thấy" phát hiện và vai trò của giả thuyết không

Không chỉ nhà khoa học mới trân trọng phát hiện; niềm vui tìm ra điều mới là phổ quát. Nó đáng mơ ước tới mức con người có xu hướng bẩm sinh cảm thấy mình đã tìm ra điều gì đó khi thật ra không có. Sách đã dùng thuật ngữ **apophenia** cho khả năng thấy quy luật ở nơi không có quy luật, và có ý kiến cho rằng xu hướng này còn mang lại lợi thế tiến hoá: những tổ tiên bỏ chạy khi nghe bụi cây xào xạc, không chờ biết chắc đó có phải hổ hay không, có lẽ dễ sống sót hơn. Thái độ đó ổn với người săn bắt hái lượm, nhưng không thể dùng trong khoa học — toàn bộ quá trình khoa học sụp đổ nếu các tuyên bố chỉ là sản phẩm tưởng tượng. Phải có cách bảo vệ ta trước phát hiện giả, và kiểm định giả thuyết cố gắng đảm nhận vai trò đó.

Ý tưởng **giả thuyết không** trở thành trung tâm: đó là dạng đơn giản hoá của mô hình thống kê mà ta sẽ dùng cho tới khi có đủ bằng chứng chống lại nó. Với năm câu hỏi trên, giả thuyết không có thể là:

1. Số vụ giết người mỗi ngày ở Anh **có** theo phân phối Poisson.
2. Tỷ lệ thất nghiệp ở Anh **không thay đổi** trong quý vừa qua.
3. Statin **không** giảm nguy cơ nhồi máu cơ tim và đột quỵ ở những người như tôi.
4. Chiều cao của mẹ **không có tác động** tới chiều cao con trai khi đã tính tới chiều cao của bố.
5. Hạt Higgs **không** tồn tại.

Giả thuyết không là điều ta sẵn lòng coi là đúng cho tới khi chứng minh được điều ngược lại. Nó phủ định một cách kiên định, chối bỏ mọi tiến bộ và thay đổi. Nhưng điều đó không có nghĩa ta thật sự tin nó đúng theo nghĩa đen: không giả thuyết nào ở trên có thể đúng chính xác tuyệt đối (có lẽ trừ việc hạt Higgs không tồn tại). Vì vậy ta không bao giờ có thể nói giả thuyết không đã được chứng minh. Như Ronald Fisher viết: "giả thuyết không không bao giờ được chứng minh hay xác lập, mà chỉ có thể bị bác bỏ, trong quá trình thực nghiệm. Có thể nói mỗi thí nghiệm tồn tại chỉ để cho các dữ kiện một cơ hội bác bỏ giả thuyết không."

Có một phép so sánh rất sát với phiên toà hình sự ở Anh: bị cáo có thể bị tuyên có tội, nhưng không ai được tuyên vô tội, chỉ là chưa chứng minh được có tội. Tương tự, ta có thể bác bỏ giả thuyết không, nhưng nếu không đủ bằng chứng để bác bỏ thì cũng không có nghĩa ta chấp nhận nó là sự thật. Nó chỉ là giả định làm việc cho tới khi có cái tốt hơn.

#### Ví dụ khoanh tay: bảng chéo và chênh lệch 7%

Hãy khoanh tay lại. Tay trái hay tay phải ở trên? Các nghiên cứu cho thấy khoảng một nửa dân số đặt tay phải ở trên, nửa kia tay trái. Nhưng điều này có liên quan tới giới tính không? Đây không phải câu hỏi khoa học cấp bách, nhưng Spiegelhalter đã tìm hiểu nó khi dạy ở Viện Khoa học Toán học châu Phi (African Institute of Mathematical Sciences) năm 2013 — một bài tập tốt trên lớp, và ông thật sự muốn biết đáp án. (Chú thích của tác giả: có lẽ câu hỏi tự nhiên hơn là liên hệ giữa khoanh tay và thuận tay, nhưng có quá ít người thuận tay trái để khảo sát.) Ông thu số liệu từ 54 nghiên cứu sinh đến từ khắp châu Phi.

**Bảng: Bảng chéo giới tính và kiểu khoanh tay của 54 nghiên cứu sinh (Table 10.1 trong sách)**

| | Nữ | Nam | Tổng |
|---|---:|---:|---:|
| Tay trái ở trên | 5 | 17 | 22 |
| Tay phải ở trên | 9 | 23 | 32 |
| Tổng | 14 | 40 | 54 |

Loại bảng này gọi là bảng chéo hay bảng tiếp liên. Nhìn chung, đa số đặt tay phải ở trên (32/54 = 59%). Tỷ lệ "tay phải" ở nữ (9/14 = 64%) cao hơn ở nam (23/40 = 57%): chênh lệch quan sát là 64% − 57% = 7% (chính xác hơn: 64,3% − 57,5% = 6,8%). Giả thuyết không ở đây là hoàn toàn không có liên hệ giữa kiểu khoanh tay và giới tính, khi đó chênh lệch kỳ vọng giữa hai giới là 0%. Nhưng tất nhiên, sự biến thiên ngẫu nhiên không tránh khỏi giữa người với người, kể cả khi giả thuyết không đúng, khiến chênh lệch quan sát không bao giờ đúng bằng 0%. Câu hỏi then chốt là: chênh lệch 7% có đủ lớn để làm bằng chứng chống lại giả thuyết không hay không? (Chú thích của tác giả: có thể chọn thống kê khác để tóm tắt liên hệ, như tỷ số odds, nhưng kết quả về cơ bản như nhau.)

Để trả lời, cần biết những chênh lệch nào sẽ xuất hiện chỉ do biến thiên ngẫu nhiên, nếu giả thuyết không thật sự đúng và khoanh tay hoàn toàn độc lập với giới tính. Nói chính thức hơn: chênh lệch 7% có **tương thích** với giả thuyết không không? Đây là ý tưởng khó nhưng then chốt. Với Arbuthnot, dễ thấy dữ liệu hoàn toàn không tương thích với giả thuyết không — khả năng trai nhiều hơn gái cả 82 năm, nếu chỉ có may rủi, là cực nhỏ. Trong tình huống phức tạp hơn, việc này không đơn giản, nhưng **kiểm định hoán vị** sau đây là một thủ tục mạnh mà không cần toán phức tạp.

#### Kiểm định hoán vị

Hãy tưởng tượng 54 sinh viên đứng thành hàng, 14 người đầu là nữ, 40 người sau là nam, mỗi người mang một số từ 1 tới 54. Mỗi người cũng cầm một tấm vé ghi mình là người "tay trái" hay "tay phải". Giờ lấy hết các vé khoanh tay, trộn trong một chiếc mũ, rồi chia ngẫu nhiên lại cho các sinh viên. Đây chính là cách tự nhiên sẽ vận hành nếu giả thuyết không đúng, vì khi đó kiểu khoanh tay hoàn toàn không liên quan tới giới tính.

Dù vé đã được chia ngẫu nhiên, tỷ lệ "tay phải" ở nữ và nam sẽ không đúng bằng nhau, chỉ do may rủi, và ta tính được chênh lệch tỷ lệ cho lần chia lại này. Lặp lại việc chia ngẫu nhiên, chẳng hạn 1.000 lần, sẽ cho một phân phối các chênh lệch. Cách khác, nếu có rất nhiều thời gian, là duyệt có hệ thống mọi hoán vị có thể của các vé, thay vì chỉ mô phỏng 1.000 lần; phân phối thu được sẽ trơn hơn. Tiếc là số hoán vị khổng lồ: kể cả tính một triệu hoán vị mỗi giây, số năm cần để duyệt hết có 57 chữ số 0 theo sau.

(Chú thích cuối chương của tác giả: có 54 × 53 × 52 × … × 2 × 1 hoán vị, gọi là "54 giai thừa", ký hiệu 54!, xấp xỉ 2 với 71 chữ số 0 theo sau. Người tổng hợp kiểm tra: 54! ≈ 2,3 × 10⁷¹; chia cho 10⁶ hoán vị/giây và khoảng 3,16 × 10⁷ giây/năm được khoảng 7 × 10⁵⁷ năm, khớp. Tác giả thêm: số cách chia một bộ bài 52 lá là 52! ≈ 8 × 10⁶⁷, nên kể cả chia một nghìn tỷ ván mỗi giây, số năm cần để duyệt hết có 48 chữ số 0 theo sau — người tổng hợp tính được khoảng 2,6 × 10⁴⁸ năm — trong khi tuổi vũ trụ chỉ khoảng 14 tỷ năm. Vì thế có thể khá chắc rằng trong toàn bộ lịch sử chơi bài, chưa từng có hai bộ bài đã xáo nào có thứ tự giống hệt nhau.)

May là không cần làm vậy, vì phân phối của chênh lệch tỷ lệ dưới giả thuyết không có thể tính bằng lý thuyết, dựa trên **phân phối siêu bội** — phân phối cho xác suất một ô cụ thể của bảng nhận từng giá trị có thể dưới các hoán vị ngẫu nhiên. (Theo bảng thuật ngữ của sách: xác suất có k phần tử mang đặc điểm khi rút n lần không hoàn lại từ tổng thể N phần tử có đúng K phần tử mang đặc điểm, bằng C(K, k) × C(N − K, n − k) / C(N, n). Ở đây N = 54, K = 32 người tay phải, n = 14 nữ.)

**Hình: Phân phối chênh lệch tỷ lệ "tay phải ở trên" giữa nữ và nam (Figure 10.2 trong sách; đồ thị cột không ghi số, tần số dưới đây là ước lượng của người tổng hợp đọc từ trục).** Hai biểu đồ: (a) từ 1.000 hoán vị ngẫu nhiên; (b) từ mọi hoán vị có thể, đồng khả năng (vẽ theo cùng thang 1.000). Đường nét đứt thẳng đứng đánh dấu chênh lệch quan sát 7%. Vì có 14 nữ, chênh lệch chỉ nhận các giá trị rời rạc, ứng với số nữ "tay phải" k = 4, 5, …, 14; mỗi khi k tăng 1, chênh lệch tăng 1/14 + 1/40 ≈ 9,6 điểm phần trăm. Cột ứng với dữ liệu thật (k = 9) nằm đúng tại đường nét đứt.

| Số nữ "tay phải" (k) | Chênh lệch nữ − nam | (a) 1.000 hoán vị ngẫu nhiên (ước lượng) | (b) mọi hoán vị, quy về 1.000 (ước lượng) | (b) người tổng hợp tính bằng phân phối siêu bội |
|---:|---:|---:|---:|---:|
| 4 | khoảng −41% | 4 | 7 | 7 |
| 5 | khoảng −32% | 34 | 31 | 31 |
| 6 | khoảng −22% | 87 | 89 | 89 |
| 7 | khoảng −12% | 171 | 177 | 177 |
| 8 | khoảng −3% | 257 | 243 | 242 |
| 9 (quan sát) | khoảng +7% | 235 | 228 | 228 |
| 10 | khoảng +16% | 136 | 145 | 145 |
| 11 | khoảng +26% | 56 | 61 | 61 |
| 12 | khoảng +36% | 17 | 16 | 16 |
| 13 | khoảng +45% | 3 | 2 | 2 |

(Các giá trị k từ 0 tới 3 và k = 14 có xác suất không đáng kể, dưới 0,5 phần nghìn.)

Phân phối trên cho thấy chênh lệch quan sát (7% nghiêng về nữ) nằm khá gần giữa phân phối các chênh lệch sẽ xuất hiện nếu thật ra không có liên hệ nào. Phân phối tản ra hai phía — có lần nghiêng về nam, có lần về nữ — và có tâm ở chênh lệch 0.

#### Giá trị P: định nghĩa, một phía và hai phía

Cần một con số tóm tắt giá trị quan sát gần tâm đến đâu. Một cách là lấy "diện tích đuôi" bên phải đường nét đứt, ở đây là 45%, tức 0,45 (theo bảng trên: 228 + 145 + 61 + 16 + 2 ≈ 452 trên 1.000). Diện tích đuôi này gọi là **giá trị P**, một trong những khái niệm nổi bật nhất của thống kê hiện nay, nên sách đưa định nghĩa chính thức:

> **Giá trị P là xác suất có được một kết quả cực đoan ít nhất như kết quả ta đã có, nếu giả thuyết không (và mọi giả định khác của mô hình) thật sự đúng.**

Vấn đề là "cực đoan" nghĩa là gì. Giá trị P 0,45 ở trên là **một đuôi (one-tailed)**, vì nó chỉ đo khả năng thấy một giá trị cực đoan như vậy theo chiều nghiêng về nữ nếu giả thuyết không đúng; nó tương ứng với **kiểm định một phía (one-sided test)**. Nhưng một chênh lệch nghiêng về nam cũng sẽ khiến ta nghi ngờ giả thuyết không. Vì vậy cũng nên tính khả năng có chênh lệch ít nhất 7% theo **bất kỳ** chiều nào — giá trị P **hai đuôi (two-tailed)**, tương ứng **kiểm định hai phía (two-sided test)**. Tổng diện tích hai đuôi theo sách là 0,89; vì gần 1, nó cho thấy giá trị quan sát ở gần tâm của phân phối dưới giả thuyết không. Tất nhiên điều này nhìn biểu đồ là thấy ngay, nhưng không phải lúc nào cũng có đồ thị, nên cần một con số để tóm tắt chính thức độ cực đoan của dữ liệu. (Người tổng hợp lưu ý: con số 0,89 gần với cách nhân đôi giá trị một phía; xem khối Lưu ý.)

Arbuthnot là ví dụ đầu tiên được ghi lại của quy trình này: dưới giả thuyết không rằng bé trai và bé gái có khả năng sinh ra như nhau, xác suất trai nhiều hơn gái cả 82 năm là 1/2⁸². Con số này chỉ định nghĩa "cực đoan" theo chiều trai nhiều hơn gái; nhưng nếu gái nhiều hơn trai cả 82 năm ta cũng nghi ngờ giả thuyết không, nên phải nhân đôi thành 1/2⁸¹ (khoảng 4,1 × 10⁻²⁵) để có xác suất của một kết quả cực đoan như vậy theo cả hai chiều. Vậy 1/2⁸¹ có thể coi là giá trị P hai phía đầu tiên được ghi nhận, dù thuật ngữ này chưa được dùng trong hai trăm năm mươi năm sau đó.

Nhân tiện, mẫu nhỏ của tác giả không cho thấy liên hệ giữa giới tính và kiểu khoanh tay, và các nghiên cứu khoa học hơn cũng không tìm thấy liên hệ giữa kiểu khoanh tay với giới tính, tay thuận hay bất kỳ đặc điểm nào khác.

### 4. Ý nghĩa thống kê (Statistical Significance, trang PDF 181–182)

Ý tưởng **ý nghĩa thống kê** đơn giản: nếu giá trị P đủ nhỏ, ta nói kết quả có ý nghĩa thống kê. Thuật ngữ này được Ronald Fisher phổ biến từ thập niên 1920 và, bất chấp những chỉ trích sẽ thấy ở phần sau, vẫn giữ vai trò lớn trong thống kê.

Ronald Fisher là người phi thường nhưng khó tính. Phi thường vì ông được coi là người tiên phong ở hai lĩnh vực riêng biệt — di truyền học và thống kê. Nhưng ông nổi tiếng nóng tính, có thể chỉ trích gay gắt bất kỳ ai ông cảm thấy chất vấn ý tưởng của mình; việc ông ủng hộ thuyết ưu sinh và công khai chỉ trích bằng chứng về liên hệ giữa hút thuốc và ung thư phổi làm tổn hại vị thế của ông. Danh tiếng cá nhân của ông bị ảnh hưởng khi các mối quan hệ tài chính của ông với ngành thuốc lá bị phơi bày, nhưng danh tiếng khoa học không suy giảm, vì ý tưởng của ông liên tục tìm được ứng dụng mới trong phân tích các bộ dữ liệu lớn.

Như đã nói ở Chương 4, Fisher phát triển ý tưởng ngẫu nhiên hoá trong thí nghiệm nông nghiệp khi làm việc ở Trạm Thí nghiệm Rothamsted. Ông minh hoạ thêm ý tưởng ngẫu nhiên hoá trong thiết kế thí nghiệm bằng **thí nghiệm nếm trà** nổi tiếng: một phụ nữ (được cho là Muriel Bristol) khẳng định có thể nếm một cốc trà mà biết sữa được cho vào trước hay sau khi rót trà. Người ta chuẩn bị bốn cốc cho sữa trước và bốn cốc rót trà trước, đưa tám cốc ra theo thứ tự ngẫu nhiên; bà được biết có bốn cốc mỗi loại và phải đoán bốn cốc nào cho sữa trước. Tương truyền bà đoán đúng cả bốn. Một ứng dụng khác của phân phối siêu bội cho thấy, dưới giả thuyết không rằng bà chỉ đoán bừa, xác suất này là 1 trên 70 (số cách chọn 4 cốc trong 8 là C(8,4) = 8 × 7 × 6 × 5 / (4 × 3 × 2 × 1) = 70, và chỉ một cách đúng hoàn toàn). Đây là một giá trị P, theo quy ước được coi là nhỏ (1/70 ≈ 0,014 < 0,05), nên kết quả có thể được tuyên bố là bằng chứng có ý nghĩa thống kê rằng bà thật sự phân biệt được.

Tóm lại, quy trình gồm các bước:

1. Đặt câu hỏi dưới dạng một giả thuyết không cần kiểm tra, thường ký hiệu H0.
2. Chọn một thống kê kiểm định ước lượng một đại lượng mà nếu nó đủ cực đoan sẽ khiến ta nghi ngờ giả thuyết không (thường giá trị lớn hơn của thống kê cho thấy không tương thích với giả thuyết không).
3. Tạo phân phối lấy mẫu của thống kê kiểm định này nếu giả thuyết không đúng.
4. Kiểm tra xem thống kê quan sát có nằm ở đuôi phân phối đó không và tóm tắt bằng giá trị P: xác suất, nếu giả thuyết không đúng, thấy một thống kê cực đoan như vậy. Giá trị P vì thế là một diện tích đuôi cụ thể.
5. "Cực đoan" phải được định nghĩa cẩn thận: nếu cả giá trị dương lớn lẫn âm lớn của thống kê đều bị coi là không tương thích với giả thuyết không, giá trị P phải tính tới điều đó.
6. Tuyên bố kết quả có ý nghĩa thống kê nếu giá trị P nhỏ hơn một ngưỡng tới hạn nào đó.

Fisher dùng P < 0,05 và P < 0,01 làm ngưỡng tiện lợi để chỉ ý nghĩa, và lập bảng các giá trị tới hạn của thống kê kiểm định cần để đạt các mức đó. Sự phổ biến của các bảng này khiến 0,05 và 0,01 thành quy ước, dù nay người ta khuyến nghị báo cáo giá trị P chính xác. Cần nhấn mạnh rằng giá trị P chính xác phụ thuộc không chỉ vào việc giả thuyết không đúng, mà còn vào **mọi giả định khác** của mô hình thống kê, như không có thiên lệch hệ thống, các quan sát độc lập, v.v.

Toàn bộ quy trình này được gọi là **Kiểm định ý nghĩa giả thuyết không (NHST)** và, như sẽ thấy, đã thành nguồn tranh cãi lớn. Nhưng trước hết cần xem ý tưởng của Fisher được dùng thế nào trong thực tế.

### 5. Dùng lý thuyết xác suất (Using Probability Theory, trang PDF 182–187)

Có lẽ phần khó nhất của kiểm định ý nghĩa giả thuyết không là bước 3 — xác lập phân phối của thống kê kiểm định đã chọn dưới giả thuyết không. Ta luôn có thể dựa vào các phương pháp mô phỏng tốn sức máy tính, như kiểm định hoán vị cho dữ liệu khoanh tay, nhưng tiện hơn nhiều nếu dùng được lý thuyết xác suất để tính trực tiếp diện tích đuôi, như Arbuthnot làm trong một trường hợp đơn giản và Fisher làm với phân phối siêu bội. Thường người ta dùng các phép xấp xỉ do những người tiên phong của suy luận thống kê phát triển.

#### Kiểm định khi bình phương về liên hệ

Khoảng năm 1900, Karl Pearson phát triển một loạt thống kê để kiểm định liên hệ trong các bảng chéo như bảng khoanh tay, từ đó ra đời **kiểm định khi bình phương về liên hệ (chi-squared test of association)** kinh điển. (Chú thích của tác giả: "chi", đọc là "kai", là một chữ cái Hy Lạp.) Các thống kê này tính số sự kiện kỳ vọng trong mỗi ô của bảng nếu giả thuyết không — không có liên hệ — đúng, rồi thống kê khi bình phương đo tổng chênh lệch giữa số quan sát và số kỳ vọng. Ví dụ, số nữ kỳ vọng có tay trái ở trên bằng tổng số nữ (14) nhân với tỷ lệ "tay trái" chung (22/54), được 5,7.

**Bảng: Số quan sát và số kỳ vọng (trong ngoặc) theo kiểu khoanh tay và giới tính, số kỳ vọng tính dưới giả thuyết không rằng khoanh tay không liên quan giới tính (Table 10.2 trong sách)**

| | Nữ | Nam | Tổng |
|---|---:|---:|---:|
| Tay trái ở trên | 5 (5,7) | 17 (16,3) | 22 |
| Tay phải ở trên | 9 (8,3) | 23 (23,7) | 32 |
| Tổng | 14 | 40 | 54 |

Kiểm tra: 14 × 22/54 = 5,70; 40 × 22/54 = 16,30; 14 × 32/54 = 8,30; 40 × 32/54 = 23,70 — khớp.

Rõ ràng số quan sát và số kỳ vọng khá giống nhau, phản ánh rằng dữ liệu gần đúng như điều ta kỳ vọng dưới giả thuyết không. Thống kê khi bình phương là thước đo tổng thể của sự khác biệt giữa số quan sát và số kỳ vọng; dạng đơn giản nhất theo bảng thuật ngữ của sách là X² = Σ (o − e)²/e, lấy tổng qua mọi ô, và dưới giả thuyết không X² có phân phối lấy mẫu xấp xỉ khi bình phương. Sách cho giá trị 0,02 và giá trị P tương ứng (lấy từ phần mềm thông dụng) là 0,90, tức không có bằng chứng chống lại giả thuyết không. Thật yên tâm khi giá trị P này về cơ bản bằng giá trị P của phép kiểm định "chính xác" dựa trên phân phối siêu bội. (Người tổng hợp lưu ý: 0,02 là giá trị có hiệu chỉnh liên tục Yates; công thức đơn giản nhất cho khoảng 0,20 và P ≈ 0,66 — xem khối Lưu ý.)

Việc xây dựng và dùng thống kê kiểm định và giá trị P xưa nay chiếm phần lớn một khoá thống kê chuẩn, và không may khiến ngành này mang tiếng chủ yếu là chọn đúng công thức và tra đúng bảng. Cuốn sách cố gắng có góc nhìn rộng hơn, nhưng vẫn đáng xem lại các ví dụ xuyên suốt sách xét về ý nghĩa thống kê.

#### Câu hỏi 1: Số vụ giết người mỗi ngày ở Anh có theo phân phối Poisson không?

Ở Chương 8, sách trình bày số ngày quan sát được với từng số vụ giết người ở Anh và xứ Wales, giai đoạn 2014–2016: tổng cộng 1.545 vụ trong 1.095 ngày, trung bình 1.545/1.095 = 1,41 vụ mỗi ngày. Dưới giả thuyết không rằng số vụ mỗi ngày theo phân phối Poisson với trung bình này, số ngày kỳ vọng như cột cuối của bảng dưới. Mở rộng cách làm với bảng khoanh tay, chênh lệch giữa số quan sát và số kỳ vọng có thể tóm tắt bằng thống kê **kiểm định khi bình phương về độ khớp (chi-squared goodness-of-fit test)**.

**Bảng: Số ngày quan sát và kỳ vọng với từng số vụ giết người mỗi ngày, Anh và xứ Wales (Table 10.3 trong sách; chú thích sách ghi giai đoạn tháng 4/2014 tới tháng 3/2016)**

| Số vụ giết người trong ngày | Số ngày quan sát | Số ngày kỳ vọng dưới giả thuyết không |
|---|---:|---:|
| 0 | 259 | 267,1 |
| 1 | 387 | 376,8 |
| 2 | 261 | 265,9 |
| 3 | 131 | 125,0 |
| 4 | 40 | 44,1 |
| 5 | 13 | 12,4 |
| 6 trở lên | 3 | 3,6 |
| Tổng | 1.095 | 1.095 |

Người tổng hợp kiểm tra cột kỳ vọng với Poisson trung bình 1,411: P(0) = e⁻¹·⁴¹¹ ≈ 0,2439, nhân 1.095 được 267,1; P(1) = 0,3442, được 376,9; P(2) = 0,2428, được 265,9; P(3) = 0,1142, được 125,0; P(4) = 0,0403, được 44,1; P(5) = 0,0114, được 12,4; phần còn lại khoảng 3,6–3,7 — khớp. Cột quan sát cộng lại chỉ được 1.094 (xem khối Lưu ý).

Kiểm định khi bình phương về độ khớp cho giá trị P = 0,96, không có ý nghĩa, nên không có bằng chứng để bác bỏ giả thuyết không (thực ra độ khớp tốt tới mức gần như đáng ngờ). Tất nhiên không vì thế mà cho rằng giả thuyết không đúng chính xác, nhưng hợp lý khi dùng nó làm giả định, chẳng hạn khi đánh giá các thay đổi về tỷ lệ giết người ở Chương 9.

#### Câu hỏi 2: Tỷ lệ thất nghiệp ở Anh có thay đổi gần đây không?

Ở Chương 7, sách cho thấy mức thay đổi thất nghiệp theo quý là giảm 3.000 người, với biên sai số ± 77.000 dựa trên ± 2 sai số chuẩn. Như vậy khoảng tin cậy 95% chạy từ −80.000 tới +74.000 và rõ ràng chứa giá trị 0, ứng với không thay đổi. Việc khoảng 95% chứa 0 tương đương về logic với việc ước lượng điểm (−3.000) cách 0 chưa tới 2 sai số chuẩn, nghĩa là thay đổi không khác 0 một cách có ý nghĩa. (Sai số chuẩn là 77.000/2 = 38.500, nên −3.000 chỉ cách 0 khoảng 0,08 sai số chuẩn.)

Điều này cho thấy sự đồng nhất cốt lõi giữa kiểm định giả thuyết và khoảng tin cậy:

- Giá trị P hai phía nhỏ hơn 0,05 nếu khoảng tin cậy 95% không chứa giá trị của giả thuyết không (thường là 0).
- Khoảng tin cậy 95% là tập hợp các giả thuyết không **không** bị bác bỏ ở mức P < 0,05.

Mối liên hệ mật thiết này lẽ ra phải ngăn người ta hiểu sai các kết quả "không khác 0 một cách có ý nghĩa thống kê" — điều đó không có nghĩa giả thuyết không thật sự đúng, mà chỉ có nghĩa khoảng tin cậy cho giá trị thật có chứa 0. Tiếc là, như sẽ thấy, bài học này thường bị phớt lờ.

#### Câu hỏi 3: Uống statin có giảm nguy cơ nhồi máu cơ tim và đột quỵ ở những người như tôi không?

Sách nhắc lại kết quả của Nghiên cứu Bảo vệ Tim (Heart Protection Study, HPS) đã trình bày ở Chương 4, thêm các cột cho thấy lợi ích đã được xác lập chắc chắn đến đâu.

**Bảng: Kết quả cuối cùng của Nghiên cứu Bảo vệ Tim, với hiệu ứng tương đối ước lượng, sai số chuẩn, khoảng tin cậy và giá trị P cho giả thuyết không "không có tác dụng" (Table 10.4 trong sách)**

| Biến cố | % trong 10.269 người dùng statin | % trong 10.267 người dùng giả dược | Mức giảm nguy cơ (tương đối) ở nhóm statin | Sai số chuẩn của mức giảm | Khoảng tin cậy cho % giảm | Giá trị P |
|---|---:|---:|---:|---:|---:|---|
| Nhồi máu cơ tim | 8,7 | 11,8 | 27% | 4% | 21% tới 33% | P < 0,0001 |
| Đột quỵ | 4,3 | 5,7 | 25% | 5% | 15% tới 34% | P < 0,0001 |
| Tử vong mọi nguyên nhân | 12,9 | 14,7 | 13% | 4% | 6% tới 19% | P = 0,0003 |

Có mối liên hệ chặt giữa sai số chuẩn, khoảng tin cậy và giá trị P. Khoảng tin cậy cho mức giảm nguy cơ xấp xỉ ước lượng ± 2 sai số chuẩn (HPS làm tròn mức giảm tương đối thành số nguyên). Các khoảng tin cậy loại trừ rất xa giả thuyết không 0%, tức statin không có tác dụng, nên giá trị P rất nhỏ — sách nói giá trị P cho mức giảm 27% nhồi máu cơ tim là khoảng 1 trên 3 triệu. Đó là hệ quả của một nghiên cứu quy mô lớn như vậy. (Người tổng hợp: kiểm tra mức giảm tương đối từ tỷ lệ — 1 − 8,7/11,8 = 26%, 1 − 4,3/5,7 = 25%, 1 − 12,9/14,7 = 12% — gần khớp với số làm tròn của HPS; về con số 1 trên 3 triệu, xem khối Lưu ý.)

Có thể dùng thống kê tóm tắt khác, như hiệu số nguy cơ tuyệt đối, nhưng chúng đều nên cho giá trị P tương tự. Nhóm HPS tập trung vào mức giảm tương đối vì nó khá ổn định giữa các nhóm con, nên là một thước đo tóm tắt đơn lẻ tốt. Có nhiều cách tính khoảng tin cậy, nhưng chúng chỉ nên khác nhau chút ít.

#### Câu hỏi 4: Chiều cao của mẹ có liên quan tới chiều cao con trai khi đã tính chiều cao của bố không?

Ở Chương 5, sách trình bày hồi quy tuyến tính bội với chiều cao con trai là biến đáp ứng (phụ thuộc), chiều cao mẹ và bố là biến giải thích (độc lập), nhưng chưa xét liệu các hệ số có khác 0 một cách có ý nghĩa không. Để minh hoạ cách kết quả hiện ra trong phần mềm thống kê, sách chép lại dạng kết quả của chương trình R (miễn phí, phổ biến).

**Bảng: Kết quả hồi quy bội trong R trên dữ liệu của Galton, chiều cao con trai là biến đáp ứng, chiều cao mẹ và bố là biến giải thích (Table 10.5 trong sách)**

| | Ước lượng (Estimate) | Sai số chuẩn (Std Error) | Giá trị t | Pr(>\|t\|) |
|---|---:|---:|---:|---|
| Hệ số chặn (Intercept) | 69,22882 | 0,10664 | 649,168 | < 2 e−16 *** |
| Chiều cao mẹ | 0,33355 | 0,04600 | 7,252 | 1,74 e−12 *** |
| Chiều cao bố | 0,41175 | 0,04668 | 8,820 | < 2 e−16 *** |

Mã ý nghĩa: *** = 0,001; ** = 0,01; * = 0,05. Cột Pr(>|t|) là giá trị P hai phía: xác suất có giá trị t lớn như vậy, dương hay âm, dưới giả thuyết không rằng quan hệ thật bằng 0. Ký hiệu "2 e−16" nghĩa là giá trị P nhỏ hơn 0,0000000000000002 (15 chữ số 0 sau dấu phẩy).

Như ở Chương 5, hệ số chặn là chiều cao trung bình của con trai (khoảng 69,2 inch), còn các hệ số ("Estimate") là mức thay đổi kỳ vọng của chiều cao con trai ứng với mỗi inch chênh lệch của chiều cao mẹ và bố so với chiều cao trung bình của các bà mẹ và các ông bố. Sai số chuẩn tính theo một công thức đã biết và rõ ràng nhỏ so với độ lớn của các hệ số.

**Giá trị t**, còn gọi là **thống kê t**, là trọng tâm chú ý vì nó cho biết liên hệ giữa một biến giải thích và biến đáp ứng có ý nghĩa thống kê hay không. Giá trị t là trường hợp riêng của thống kê t của Student. "Student" là bút danh của William Gosset, người phát triển phương pháp năm 1908 khi được hãng bia Guinness ở Dublin biệt phái sang University College London — hãng muốn giữ kín danh tính nhân viên của mình. Giá trị t đơn giản là ước lượng chia cho sai số chuẩn, nên có thể hiểu là ước lượng cách 0 bao nhiêu sai số chuẩn. Kiểm tra: 0,33355/0,04600 = 7,25; 0,41175/0,04668 = 8,82; 69,22882/0,10664 = 649,2 — khớp. Biết giá trị t và cỡ mẫu, phần mềm cho giá trị P chính xác; với mẫu lớn, giá trị t lớn hơn 2 hoặc nhỏ hơn −2 tương ứng P < 0,05, còn với mẫu nhỏ thì ngưỡng lớn hơn. R dùng hệ thống sao đơn giản cho giá trị P, từ một sao (P < 0,05) tới ba sao (P < 0,001). Ở đây giá trị t lớn tới mức giá trị P nhỏ không đáng kể: chiều cao mẹ vẫn liên quan rõ rệt tới chiều cao con trai khi đã tính chiều cao bố.

#### Ví dụ thêm: thuật toán "thắng" cuộc thi Titanic có thật sự tốt nhất không?

Ở Chương 6, một thuật toán có thể thắng cuộc thi dự báo với cách biệt rất nhỏ. Khi dự báo khả năng sống sót của tập kiểm tra *Titanic*, cây phân loại đơn giản đạt điểm Brier (sai số dự báo bình phương trung bình) tốt nhất là 0,139, chỉ thấp hơn chút ít so với 0,142 của mạng nơ-ron lấy trung bình. Hợp lý khi hỏi cách biệt −0,003 này có ý nghĩa thống kê không, tức có thể giải thích bằng biến thiên ngẫu nhiên không.

Việc kiểm tra khá đơn giản (chú thích của tác giả): với mỗi người trong 412 người của tập kiểm tra, tính hiệu số giữa sai số dự báo bình phương của hai thuật toán; 412 hiệu số này có trung bình −0,0027 và độ lệch chuẩn 0,1028. Sai số chuẩn của ước lượng hiệu số "thật" là 0,1028/√412 = 0,1028/20,3 ≈ 0,0050, nên thống kê t = ước lượng/sai số chuẩn = −0,0027/0,0050 = −0,54. Đây gọi là **kiểm định t ghép cặp** vì dựa trên tập hiệu số giữa các cặp số. Giá trị P hai phía là 0,59. Vậy không có bằng chứng tốt rằng cây phân loại thật sự là thuật toán tốt nhất. Loại phân tích này không phổ biến trong các cuộc thi kiểu Kaggle, nhưng có vẻ quan trọng phải biết rằng vị trí thắng cuộc phụ thuộc vào việc chọn ngẫu nhiên các trường hợp vào tập kiểm tra.

Các nhà nghiên cứu dành cả đời soi những kết quả máy tính như bảng hồi quy ở trên, mong thấy những ngôi sao lấp lánh báo hiệu một kết quả có ý nghĩa để đưa vào bài báo khoa học tiếp theo. Nhưng, như sẽ thấy, việc săn ý nghĩa thống kê một cách ám ảnh như vậy dễ dẫn tới ảo tưởng phát hiện.

### 6. Nguy cơ khi làm nhiều kiểm định ý nghĩa (The Danger of Carrying Out Many Significance Tests, trang PDF 187–188)

#### Kiểm định nhiều lần làm tăng dương tính giả

Các ngưỡng chuẩn để tuyên bố "có ý nghĩa", P < 0,05 và P < 0,01, là lựa chọn khá tuỳ tiện của Fisher cho các bảng tra của ông, vào thời chưa thể tính giá trị P chính xác bằng máy tính cơ và điện. Điều gì xảy ra khi làm nhiều kiểm định, mỗi lần xem giá trị P có nhỏ hơn 0,05 không?

Giả sử một loại thuốc thật sự không có tác dụng, tức giả thuyết không đúng. Nếu làm một thử nghiệm lâm sàng, ta sẽ tuyên bố kết quả có ý nghĩa nếu P < 0,05, và vì thuốc vô dụng, khả năng này là 0,05 hay 5% — đó chính là định nghĩa của giá trị P. Kết quả như vậy là **dương tính giả**, vì ta tin sai rằng thuốc có hiệu quả. Nếu làm hai thử nghiệm và nhìn vào kết quả cực đoan nhất, khả năng có ít nhất một kết quả có ý nghĩa — tức dương tính giả — gần 0,10 hay 10%. (Chú thích của tác giả: chính xác là 1 − xác suất cả hai đều không có ý nghĩa = 1 − 0,95 × 0,95 = 0,0975, làm tròn thành 0,10.) Khả năng có ít nhất một dương tính giả tăng nhanh khi làm thêm thử nghiệm; với mười thử nghiệm thuốc vô dụng, khả năng có ít nhất một kết quả có ý nghĩa ở P < 0,05 lên tới 40% (1 − 0,95¹⁰ = 1 − 0,599 = 0,401). Đây là vấn đề **kiểm định nhiều lần**, xảy ra mỗi khi làm nhiều kiểm định ý nghĩa rồi báo cáo kết quả có ý nghĩa nhất.

#### Con cá hồi chết

Một vấn đề đặc biệt xảy ra khi nhà nghiên cứu chia dữ liệu thành nhiều tập con, làm kiểm định trong từng tập, rồi chọn kết quả có ý nghĩa nhất. Một minh hoạ kinh điển là thí nghiệm năm 2009 của các nhà nghiên cứu có uy tín: cho một "đối tượng" xem loạt ảnh người biểu lộ các cảm xúc khác nhau, đồng thời chụp cộng hưởng từ chức năng (fMRI) não để xem vùng nào phản ứng có ý nghĩa, với ngưỡng P < 0,001. Điểm bất ngờ là "đối tượng" là một con cá hồi Đại Tây Dương nặng 4 pound (khoảng 1,8 kg), "không còn sống vào thời điểm chụp". Trong tổng số 8.064 điểm trên não con cá chết khá to này, 16 điểm cho phản ứng có ý nghĩa thống kê với các bức ảnh. Thay vì kết luận con cá hồi chết có năng lực kỳ diệu, nhóm nghiên cứu chỉ ra đúng vấn đề kiểm định nhiều lần — hơn 8.000 kiểm định ý nghĩa chắc chắn sẽ cho dương tính giả. Ngay cả với ngưỡng chặt P < 0,001, chỉ do ngẫu nhiên ta đã kỳ vọng 8.064 × 0,001 ≈ 8 kết quả có ý nghĩa.

#### Bonferroni, tỷ lệ phát hiện sai và lặp lại nghiên cứu

Một cách khắc phục là đòi giá trị P rất thấp mới tuyên bố có ý nghĩa. Cách đơn giản nhất, gọi là **hiệu chỉnh Bonferroni**, dùng ngưỡng 0,05/n, với n là số kiểm định đã làm. Ví dụ, kiểm định ở mỗi điểm trên não cá hồi có thể đòi P < 0,05/8.000 = 0,00000625, tức 1 trên 160.000. Kỹ thuật này đã thành thông lệ khi dò tìm trong bộ gen người các vị trí liên quan tới bệnh: vì có khoảng 1.000.000 vị trí gen, người ta thường đòi P nhỏ hơn 0,05/1.000.000 = 1 trên 20 triệu trước khi công bố phát hiện. (Bảng thuật ngữ của sách diễn đạt tổng quát: để có mức tổng thể α khi kiểm định n giả thuyết, kiểm định mỗi giả thuyết ở mức α/n, hoặc tương đương dùng khoảng tin cậy 100(1 − α/n)% cho từng đại lượng; ví dụ 10 giả thuyết với α = 5% thì so giá trị P với 0,005 và dùng khoảng tin cậy 99,5%.)

Như vậy, khi kiểm định đồng thời rất nhiều giả thuyết như trong chụp ảnh não hay hệ gen học, có thể dùng Bonferroni để quyết định kết quả cực đoan nhất có ý nghĩa hay không. Cũng có những kỹ thuật đơn giản nới nhẹ tiêu chí Bonferroni cho kết quả cực đoan thứ hai, thứ ba, v.v., nhằm kiểm soát tỷ lệ tổng thể của các "phát hiện" hoá ra là sai — gọi là **tỷ lệ phát hiện sai**.

Một cách khác để tránh dương tính giả là đòi **lặp lại** nghiên cứu ban đầu, làm lại thí nghiệm trong hoàn cảnh hoàn toàn khác nhưng về cơ bản cùng quy trình. Để một loại thuốc mới được Cục Quản lý Thực phẩm và Dược phẩm Mỹ (FDA) phê duyệt, thông lệ là phải có hai thử nghiệm lâm sàng độc lập, mỗi thử nghiệm cho lợi ích lâm sàng có ý nghĩa ở P < 0,05. Như vậy xác suất tổng thể phê duyệt một thuốc thật ra hoàn toàn vô ích là 0,05 × 0,05 = 0,0025, tức 1 trên 400.

#### Câu hỏi 5: Hạt Higgs có tồn tại không?

Suốt thế kỷ 20, các nhà vật lý xây dựng một "mô hình chuẩn" nhằm giải thích các lực tác động ở cấp hạ nguyên tử. Một mảnh của mô hình vẫn là lý thuyết chưa được chứng minh: "trường Higgs" — một trường năng lượng tràn ngập vũ trụ, mang lại khối lượng cho các hạt như electron thông qua hạt cơ bản của chính nó, gọi là hạt Higgs (Higgs boson). Khi các nhà nghiên cứu ở CERN cuối cùng công bố phát hiện hạt Higgs năm 2012, nó được tuyên bố là một kết quả "năm sigma". Nhưng ít ai nhận ra đây là cách diễn đạt mức ý nghĩa thống kê.

Khi vẽ tần suất xảy ra các sự kiện cụ thể theo các mức năng lượng khác nhau, đường cong có một "cái bướu" rõ rệt đúng tại chỗ sẽ xuất hiện nếu hạt Higgs tồn tại. Điều then chốt là một dạng kiểm định khi bình phương về độ khớp cho giá trị P nhỏ hơn 1 trên 3,5 triệu, dưới giả thuyết không rằng hạt Higgs **không** tồn tại và "cái bướu" chỉ là kết quả của biến thiên ngẫu nhiên.

Vì sao lại gọi là phát hiện "năm sigma"? Trong vật lý lý thuyết, thông lệ là báo cáo các tuyên bố phát hiện theo "sigma": một kết quả "hai sigma" là quan sát cách giả thuyết không hai sai số chuẩn (sigma, σ, là chữ cái Hy Lạp sách dùng cho độ lệch chuẩn của tổng thể). Các "sigma" trong vật lý tương ứng chính xác với giá trị t trong kết quả hồi quy ở trên. Vì một quan sát cho giá trị P cỡ 1 trên 3,5 triệu sẽ cách giả thuyết không năm sai số chuẩn, hạt Higgs được gọi là kết quả năm sigma. (Người tổng hợp lưu ý: 1 trên 3,5 triệu là giá trị P một phía của năm sigma, không phải hai phía như sách viết — xem khối Lưu ý.)

Nhóm CERN rõ ràng không muốn công bố "phát hiện" cho tới khi giá trị P cực kỳ nhỏ. Thứ nhất, họ phải tính tới việc các kiểm định ý nghĩa đã được làm ở mọi mức năng lượng, không chỉ ở mức trong phép kiểm định khi bình phương cuối cùng — việc hiệu chỉnh cho kiểm định nhiều lần này trong vật lý gọi là **"hiệu ứng nhìn chỗ khác" (look elsewhere effect)**. Nhưng chủ yếu họ muốn chắc chắn rằng mọi nỗ lực lặp lại sẽ đi tới cùng kết luận: đưa ra một tuyên bố sai về các định luật vật lý thì quá xấu hổ.

Trả lời câu hỏi: giờ đây có vẻ hợp lý khi coi hạt Higgs tồn tại. Điều này trở thành giả thuyết không mới, cho tới khi, có lẽ, một lý thuyết sâu hơn được đề xuất.

### 7. Lý thuyết Neyman–Pearson (Neyman—Pearson Theory, trang PDF 188–190)

#### Khung câu hỏi: Vì sao Nghiên cứu Bảo vệ Tim cần hơn 20.000 người tham gia?

HPS rất lớn (10.269 + 10.267 = 20.536 người), nhưng quy mô đó không phải lựa chọn tuỳ tiện. Khi lập kế hoạch thử nghiệm, các nhà nghiên cứu phải nói cần ngẫu nhiên hoá bao nhiêu người vào nhóm statin và nhóm không statin, và con số này phải có nền tảng thống kê vững để biện minh cho chi phí của một thí nghiệm như vậy. Kế hoạch của họ dựa trên các ý tưởng thống kê của Jerzy Neyman và Egon Pearson — những người đã gặp ở Chương 7 với tư cách người phát triển khoảng tin cậy.

#### Từ Fisher tới Neyman–Pearson

Ý tưởng giá trị P và kiểm định ý nghĩa được Fisher phát triển trong thập niên 1920 như một cách kiểm tra mức phù hợp của một giả thuyết cụ thể. Nếu thấy giá trị P nhỏ, thì hoặc điều gì đó rất bất ngờ đã xảy ra, hoặc giả thuyết không sai: giá trị P càng nhỏ, càng có nhiều bằng chứng rằng giả thuyết không có thể là giả định không phù hợp. Đây vốn là một thủ tục khá không chính thức, nhưng trong thập niên 1930, Neyman và Pearson phát triển một lý thuyết "hành vi quy nạp" (inductive behaviour) nhằm đặt kiểm định giả thuyết lên nền tảng toán học chặt chẽ hơn.

Khung của họ đòi hỏi nêu rõ không chỉ giả thuyết không mà cả một **giả thuyết đối**, biểu diễn một lời giải thích phức tạp hơn cho dữ liệu. Sau đó họ xét các quyết định có thể sau một kiểm định: bác bỏ giả thuyết không để theo giả thuyết đối, hoặc không bác bỏ giả thuyết không. (Chú thích của tác giả: lý thuyết gốc của Neyman và Pearson có ý "chấp nhận" giả thuyết không, nhưng phần này nay bị bỏ qua.) Vì vậy có hai loại sai lầm: **sai lầm loại I** là bác bỏ giả thuyết không khi nó đúng, và **sai lầm loại II** là không bác bỏ giả thuyết không khi thật ra giả thuyết đối đúng.

**Bảng: Các kết cục có thể của một kiểm định giả thuyết, so với phiên toà hình sự (Table 10.6 trong sách)**

| Sự thật | Không bác bỏ giả thuyết không (tuyên nghi phạm "không có tội") | Bác bỏ giả thuyết không để theo giả thuyết đối (tuyên nghi phạm có tội) |
|---|---|---|
| Giả thuyết không đúng (nghi phạm vô tội) | Đúng khi không bác bỏ. Tuyên đúng một người vô tội là "không có tội" | Sai lầm loại I: bác bỏ sai giả thuyết không. Kết tội nhầm một người vô tội |
| Giả thuyết đối đúng (nghi phạm có tội) | Sai lầm loại II: không bác bỏ khi lẽ ra phải bác bỏ. Không kết tội được một người có tội | Bác bỏ đúng. Kết tội đúng một người có tội |

#### Mức α, β và lực kiểm định

Khi lập kế hoạch thí nghiệm, Neyman và Pearson đề nghị chọn hai đại lượng cùng quyết định thí nghiệm cần lớn đến đâu. Thứ nhất, cố định xác suất sai lầm loại I khi giả thuyết không đúng ở một giá trị định trước, ví dụ 0,05; đây gọi là **mức (size) của kiểm định**, thường ký hiệu α (alpha). Thứ hai, định trước xác suất sai lầm loại II khi giả thuyết đối đúng, thường ký hiệu β (beta). Thực tế các nhà nghiên cứu thường làm việc với 1 − β, gọi là **lực kiểm định (power)**: khả năng bác bỏ giả thuyết không để theo giả thuyết đối khi giả thuyết đối đúng. Nói cách khác, lực của một thí nghiệm là khả năng nó phát hiện đúng một hiệu ứng có thật.

Mức α liên hệ chặt với giá trị P của Fisher. Nếu lấy α làm ngưỡng để coi kết quả là có ý nghĩa, thì các kết quả dẫn tới bác bỏ giả thuyết không chính là những kết quả có P nhỏ hơn α. Vậy α có thể coi là mức ý nghĩa ngưỡng — α = 0,05 nghĩa là bác bỏ giả thuyết không với mọi giá trị P nhỏ hơn 0,05.

Có các công thức tính mức và lực cho các dạng thí nghiệm khác nhau, và chúng đều phụ thuộc mạnh vào cỡ mẫu. Nhưng nếu cỡ mẫu cố định thì không tránh được đánh đổi: muốn tăng lực, luôn có thể nới ngưỡng "ý nghĩa" để dễ phát hiện đúng một hiệu ứng thật hơn, nhưng như vậy làm tăng xác suất sai lầm loại I (mức α). Theo phép so sánh với toà án, có thể nới tiêu chí kết tội, chẳng hạn nới yêu cầu chứng minh "vượt quá mọi nghi ngờ hợp lý"; điều đó giúp kết tội đúng nhiều tội phạm hơn, nhưng với cái giá không tránh được là nhiều người vô tội bị kết tội oan hơn.

#### Lực kiểm định trong thử nghiệm lâm sàng: HPS

Lý thuyết Neyman–Pearson bắt nguồn từ kiểm soát chất lượng công nghiệp, nhưng nay được dùng rộng rãi trong kiểm nghiệm các phương pháp điều trị mới. Trước khi bắt đầu một thử nghiệm lâm sàng ngẫu nhiên, đề cương sẽ nêu giả thuyết không rằng phương pháp điều trị không có tác dụng, và một giả thuyết đối, thường là một hiệu ứng được coi là vừa hợp lý vừa quan trọng. Các nhà nghiên cứu sau đó định mức và lực của nghiên cứu, thường α = 0,05 và lực 1 − β = 0,80 (sách ghi nhầm "β = 0,80"). Nghĩa là họ đòi P < 0,05 mới tuyên bố có ý nghĩa, và có 80% khả năng đạt được điều đó nếu phương pháp điều trị thật sự có tác dụng; hai con số này cùng cho ra ước tính số người tham gia cần thiết.

Muốn làm một thử nghiệm lâm sàng mang tính quyết định thì phải chặt hơn. Nhóm HPS kết luận rằng:

> nếu liệu pháp hạ cholesterol giảm khoảng 25% tử vong do bệnh mạch vành trong 5 năm và khoảng 15% tử vong do mọi nguyên nhân, thì một nghiên cứu cỡ này với mức tuân thủ tốt sẽ có cơ hội rất cao chứng minh các hiệu ứng đó ở mức ý nghĩa thống kê thuyết phục (tức lực trên 90% để đạt p < 0,01).

Nói cách khác, nếu hiệu ứng thật là giảm 25% tử vong do bệnh tim và 15% tử vong mọi nguyên nhân (các giả thuyết đối), nghiên cứu có lực khoảng 90% (1 − β = 0,90; sách ghi nhầm "β = 90%") và mức α = 1%. Các yêu cầu này đòi cỡ mẫu trên 20.000. Thực tế, như bảng HPS ở trên cho thấy, kết quả cuối cùng gồm mức giảm 13% tử vong mọi nguyên nhân, rất gần với mức đã lập kế hoạch (15%).

Ý tưởng có mẫu đủ lớn để có đủ lực phát hiện một giả thuyết đối hợp lý đã trở thành nền nếp trong lập kế hoạch nghiên cứu y khoa. Nhưng trong tâm lý học và thần kinh học, cỡ mẫu thường được chọn theo sự tiện lợi hay truyền thống, có thể chỉ 20 người cho mỗi điều kiện nghiên cứu. Những giả thuyết đối đúng và thú vị có thể bị bỏ lỡ chỉ vì nghiên cứu quá nhỏ, và nhu cầu các lĩnh vực thực nghiệm khác phải nghĩ về lực thí nghiệm của mình cuối cùng cũng đang được thừa nhận.

#### Hỗn hợp Fisher và Neyman–Pearson

Như chương sau sẽ kể, Neyman và Pearson đã tranh cãi kịch liệt, thậm chí công khai xúc phạm, với Fisher về dạng kiểm định giả thuyết phù hợp, và xung đột này chưa bao giờ được giải quyết thành một cách tiếp cận "đúng" duy nhất. HPS cho thấy các thử nghiệm lâm sàng có xu hướng được thiết kế theo quan điểm Neyman–Pearson, nhưng nói chặt chẽ thì mức và lực không còn liên quan khi thí nghiệm đã được thực hiện. Lúc đó thử nghiệm được phân tích bằng khoảng tin cậy để chỉ ra các giá trị hợp lý của hiệu ứng điều trị, và bằng giá trị P kiểu Fisher để tóm tắt sức mạnh của bằng chứng chống lại giả thuyết không. Một hỗn hợp kỳ lạ giữa ý tưởng của Fisher và của Neyman–Pearson hoá ra lại hiệu quả đáng kể.

### 8. Có thể bắt Harold Shipman sớm hơn không? (khung câu hỏi "Could Harold Shipman have been caught earlier?", trang PDF 191–196)

#### Số tử vong vượt kỳ vọng

Như phần mở đầu cuốn sách đã kể, bác sĩ Harold Shipman đã sát hại hơn 200 bệnh nhân trong hai mươi năm trước khi bị bắt. Gia đình các nạn nhân đương nhiên đau đớn vì ông ta có thể gây tội lâu như vậy mà không bị nghi ngờ, và một cuộc điều tra công khai sau đó được giao xem liệu có thể phát hiện ông ta sớm hơn không. Trước cuộc điều tra, người ta đã cộng dồn số giấy chứng tử Shipman ký cho những người chết tại nhà hoặc tại phòng khám của ông ta từ năm 1977, và so với số kỳ vọng dựa trên cơ cấu tuổi của mọi bệnh nhân dưới sự "chăm sóc" của Shipman và tỷ lệ tử vong của các bác sĩ đa khoa khác trong vùng. So sánh kiểu này giúp kiểm soát các điều kiện địa phương như thời tiết thay đổi hay dịch cúm. Lấy số quan sát trừ số kỳ vọng, cộng dồn từ 1977 tới khi Shipman bị bắt năm 1998, được số tử vong "vượt" của ông ta.

**Hình: Số giấy chứng tử Shipman ký cho bệnh nhân từ 65 tuổi chết tại nhà hoặc phòng khám, đã trừ số kỳ vọng theo danh sách bệnh nhân, cộng dồn (Figure 10.3 trong sách; đồ thị không ghi số, các giá trị là ước lượng của người tổng hợp đọc từ trục, trừ giá trị năm 1998 có trong lời văn)**

| Năm | Nữ (vượt kỳ vọng cộng dồn) | Nam (vượt kỳ vọng cộng dồn) |
|---|---:|---:|
| 1977 | khoảng 0 | khoảng −5 |
| 1979 | khoảng 15 | khoảng 0 |
| 1982 | khoảng 25 | khoảng 11 |
| 1984 | khoảng 32 | khoảng 16 |
| 1985 | khoảng 42 | khoảng 20 |
| 1988 | khoảng 61 | khoảng 22 |
| 1990 | khoảng 69 | khoảng 25 |
| 1992 | khoảng 71 | khoảng 24 |
| 1994 | khoảng 90 | khoảng 28 |
| 1996 | khoảng 130 | khoảng 46 |
| 1998 | 174 (lời văn) | 49 (lời văn) |

Đường của nữ tăng khá đều tới đầu thập niên 1990, đi ngang quanh 1990–1992, rồi tăng vọt từ 1993 (giai đoạn tăng nhanh nhất là 1994–1997). Đường của nam đi ngang quanh 20–28 trong giai đoạn 1985–1994, rồi tăng lên khoảng 46–49 trong 1995–1998.

Đến năm 1998, số tử vong vượt ước tính ở người từ 65 tuổi là 174 nữ và 49 nam. Con số này gần như đúng bằng số người cao tuổi sau đó được cuộc điều tra xác nhận là nạn nhân, cho thấy độ chính xác đáng kinh ngạc của một phân tích thuần tuý thống kê, không dùng chút hiểu biết nào về từng trường hợp.

#### Kiểm định ý nghĩa mỗi năm: báo động năm 1979

Giả sử, trong một lịch sử hư cấu, có người theo dõi số tử vong của Shipman từng năm và làm các phép tính như hình trên. Khi nào họ có thể "thổi còi"? Chẳng hạn, họ có thể làm một kiểm định ý nghĩa vào cuối mỗi năm. Số tử vong, giống số vụ giết người, là kết quả của nhiều cá nhân mỗi người có xác suất nhỏ gặp sự kiện, nên có thể giả định theo phân phối Poisson. Giả thuyết không là: số tử vong quan sát cộng dồn là một quan sát từ phân phối Poisson có kỳ vọng bằng số kỳ vọng cộng dồn.

Nếu làm như vậy với tổng số tử vong cả nam và nữ, thì năm 1979, chỉ sau ba năm theo dõi, giá trị P một phía là 0,004, khi so 40 ca tử vong quan sát với 25,3 ca kỳ vọng. (Chú thích của tác giả: giá trị P là một phía vì chỉ quan tâm phát hiện tử vong tăng, không phải giảm; nó là xác suất một biến Poisson với trung bình kỳ vọng đạt ít nhất 40. Người tổng hợp tính gần đúng với trung bình 25,3 được khoảng 0,004 — khớp; chú thích ghi trung bình "22,5", xem khối Lưu ý.) Kết quả có thể đã được tuyên bố là "có ý nghĩa thống kê", và Shipman bị điều tra và phát hiện.

#### Hai lý do cách làm này không phù hợp

Nhưng có hai lý do khiến một thủ tục như vậy hoàn toàn không phù hợp để giám sát tỷ lệ tử vong của các bác sĩ đa khoa.

**Thứ nhất, kiểm định nhiều lần.** Trừ khi có lý do khác để nghi ngờ Shipman và lập quy trình giám sát riêng ông ta, ta sẽ phải tính những giá trị P như vậy cho mọi bác sĩ đa khoa ở Anh — khoảng 25.000 người vào thời đó. Như với con cá hồi chết, làm đủ nhiều kiểm định thì sẽ có tín hiệu giả. Với 25.000 bác sĩ kiểm định ở ngưỡng 0,05, ta kỳ vọng 1 trên 20 bác sĩ hoàn toàn vô tội — khoảng 1.250 người (sách làm tròn "khoảng 1.300") — bị "cao một cách có ý nghĩa" mỗi lần kiểm định, và điều tra tất cả họ là hoàn toàn không phù hợp. Shipman cũng có thể bị lẫn trong đám dương tính giả đó.

Một cách khác là áp dụng Bonferroni và đòi giá trị P 0,05/25.000, tức 1 trên 500.000, cho bác sĩ cực đoan nhất. Với Shipman, điều này xảy ra năm 1984, khi ông ta có 105 ca tử vong so với 59,2 ca kỳ vọng, vượt 46.

**Thứ hai, kiểm định lặp lại.** Ngay cả vậy, đây vẫn không phải thủ tục đáng tin để áp dụng cho mọi bác sĩ trong nước, vì ta đang làm kiểm định ý nghĩa lặp lại: mỗi năm thêm dữ liệu mới và làm thêm một kiểm định. Có một lý thuyết đáng chú ý nhưng phức tạp, mang tên thú vị **"luật lôgarit lặp" (Law of the Iterated Logarithm)**, cho thấy nếu kiểm định lặp lại như vậy thì, dù giả thuyết không đúng, ta **chắc chắn** sớm muộn sẽ bác bỏ nó ở bất kỳ mức ý nghĩa nào ta chọn. Điều này rất đáng lo, vì nó có nghĩa nếu cứ kiểm định một bác sĩ đủ lâu, ta chắc chắn sẽ có lúc nghĩ đã tìm thấy bằng chứng tử vong vượt, dù thực tế bệnh nhân của bác sĩ đó không chịu nguy cơ vượt nào.

#### Kiểm định tuần tự và SPRT

May là có các phương pháp thống kê để xử lý vấn đề **kiểm định tuần tự** này, phát triển lần đầu trong Thế chiến II bởi các nhóm nhà thống kê chẳng liên quan gì tới y tế, mà làm kiểm soát chất lượng công nghiệp cho vũ khí và vật tư chiến tranh. Các sản phẩm ra khỏi dây chuyền được kiểm tra xem có đạt chuẩn không, và toàn bộ quy trình được giám sát bằng cách cộng dồn đều đặn tổng độ lệch so với chuẩn, giống như theo dõi tử vong vượt. Các nhà khoa học này nhận ra luật lôgarit lặp có nghĩa là kiểm định ý nghĩa lặp lại sớm muộn sẽ luôn báo động rằng quy trình công nghiệp đã mất kiểm soát, kể cả khi thật ra mọi thứ vẫn vận hành tốt. Các nhà thống kê ở Mỹ và Anh, làm việc độc lập, đã phát triển cái về sau được gọi là **Kiểm định tỷ số xác suất tuần tự (SPRT)**: một thống kê theo dõi bằng chứng tích luỹ về độ lệch và có thể so bất cứ lúc nào với các ngưỡng đơn giản — ngay khi một ngưỡng bị vượt, báo động được phát ra và dây chuyền được kiểm tra. (Chú thích của tác giả: nhóm ở Mỹ do Abraham Wald dẫn dắt, ở Anh do George Barnard. Barnard là một người dễ mến, trước chiến tranh là nhà toán học thuần tuý (và đảng viên cộng sản), như nhiều người khác đã chuyển kỹ năng sang công việc thống kê thời chiến; về sau ông xây dựng tiêu chuẩn chính thức của Anh cho bao cao su, BS 3704.) Các kỹ thuật này làm quy trình công nghiệp hiệu quả hơn, và về sau được điều chỉnh để dùng trong các thử nghiệm lâm sàng tuần tự, nơi kết quả tích luỹ được theo dõi lặp lại để xem đã vượt ngưỡng cho thấy phương pháp điều trị có lợi hay chưa.

Spiegelhalter là thành viên nhóm phát triển một phiên bản SPRT áp dụng được cho dữ liệu Shipman, với giả thuyết đối rằng Shipman có tỷ lệ tử vong gấp đôi đồng nghiệp. Theo chú thích cuối chương, thống kê kiểm định có dạng đơn giản:

SPRT = 0,69 × số tử vong quan sát cộng dồn − số tử vong kỳ vọng cộng dồn

và các ngưỡng bằng log((1 − β)/α) (lôgarit tự nhiên). (Người tổng hợp giải thích: 0,69 ≈ ln 2. Với số đếm Poisson, lôgarit tỷ số khả năng giữa giả thuyết "tỷ lệ gấp đôi" và giả thuyết "tỷ lệ bình thường" là O × ln 2 − (2E − E) = 0,69 × O − E, với O là số quan sát và E là số kỳ vọng cộng dồn.) Các ngưỡng được chọn để kiểm soát xác suất sai lầm loại I (α) và loại II (β) ở các giá trị 1 trên 100, 1 trên 10.000 và 1 trên 1.000.000: sai lầm loại I là xác suất tổng thể thống kê vượt ngưỡng vào lúc nào đó, khi Shipman có tỷ lệ tử vong như kỳ vọng; sai lầm loại II là xác suất tổng thể thống kê không bao giờ vượt ngưỡng, khi Shipman có tỷ lệ tử vong gấp đôi kỳ vọng.

**Hình: Thống kê SPRT để phát hiện nguy cơ tử vong tăng gấp đôi, bệnh nhân trên 64 tuổi chết tại nhà hoặc phòng khám (Figure 10.4 trong sách; đồ thị không ghi số, các giá trị là ước lượng của người tổng hợp đọc từ trục).** Các đường ngang là ngưỡng "báo động", cho tỷ lệ sai lầm loại I và loại II tổng thể như ghi, với giả định α = β. Người tổng hợp tính các ngưỡng: α = β = 0,01 cho ln(0,99/0,01) ≈ 4,6; α = β = 0,0001 cho ln(0,9999/0,0001) ≈ 9,2; α = β = 0,000001 cho ln(0,999999/0,000001) ≈ 13,8 — khớp vị trí ba vạch ngang trên hình.

| Năm | SPRT nữ (ước lượng) | SPRT nam (ước lượng) |
|---|---:|---:|
| 1977 | khoảng −1 | khoảng −5 |
| 1979 | khoảng 7 | khoảng −4 |
| 1981 | khoảng 10,5 | khoảng −1 |
| 1983 | khoảng 8,5 | khoảng 0 |
| 1984 | khoảng 13,5 | khoảng 1,5 |
| 1985 | khoảng 19,5 | khoảng 3,5 |
| 1988 | khoảng 31 | khoảng 2,5 |
| 1990 | khoảng 35 | khoảng 3 |
| 1992 | khoảng 36 | khoảng 1,5 |
| 1994 | khoảng 49 | khoảng 3,5 |
| 1996 | khoảng 75 | khoảng 15,5 |
| 1998 | khoảng 106 | khoảng 17 |

Đọc từ hình: đường của nữ vượt ngưỡng 1/100 (4,6) từ khoảng 1979, vượt ngưỡng 1/10.000 (9,2) khoảng 1981, và vượt ngưỡng ngoài cùng 1 phần triệu (13,8) năm 1985; đường của nam chỉ vượt các ngưỡng khoảng 1995–1996.

Vì có khoảng 25.000 bác sĩ đa khoa, ngưỡng P 0,05/25.000 = 1 trên 500.000 có thể là hợp lý. Chỉ xét bệnh nhân nữ, Shipman sẽ vượt ngưỡng chặt hơn α = 0,000001 (1 phần triệu) năm 1985; nếu gộp cả nam và nữ thì năm 1984. Vậy trong trường hợp này, phép kiểm định tuần tự đúng đắn sẽ báo động cùng lúc với phép kiểm định ý nghĩa lặp lại ngây thơ.

#### Kết luận cho cuộc điều tra và bài học về báo động oan

Kết luận của nhóm gửi cuộc điều tra công khai là: nếu có người thực hiện việc giám sát này, và Shipman bị điều tra năm 1984 rồi bị truy tố, thì khoảng 175 sinh mạng có thể đã được cứu — tất cả nhờ áp dụng thường quy một thủ tục giám sát thống kê đơn giản.

Sau đó, một hệ thống giám sát bác sĩ đa khoa được thí điểm, và nó lập tức phát hiện một bác sĩ có tỷ lệ tử vong còn cao hơn Shipman! Điều tra cho thấy bác sĩ này hành nghề ở một thị trấn ven biển phía nam có nhiều nhà dưỡng lão với nhiều người già, và ông tận tâm giúp nhiều bệnh nhân được ở ngoài bệnh viện khi qua đời. Để bác sĩ này bị công khai vì tỷ lệ ký giấy chứng tử có vẻ cao là hoàn toàn không phù hợp. Bài học: hệ thống thống kê có thể phát hiện kết cục bất thường, nhưng không đưa ra được lý do vì sao chúng xảy ra, nên cần triển khai cẩn thận để tránh buộc tội oan. Thêm một lý do để thận trọng với các thuật toán.

### 9. Giá trị P có thể sai ở đâu? (khung câu hỏi "What could go wrong with P-values?", trang PDF 196–201)

#### Từ một kiểm định đơn lẻ tới "tiền tệ" của nghiên cứu

Fisher phát triển ý tưởng giá trị P như một thước đo mức tương thích của dữ liệu với một giả thuyết đặt ra từ trước. Nếu tính được giá trị P nhỏ, nghĩa là khó có khả năng thống kê tóm tắt cực đoan như vậy nếu giả thuyết đúng, nên hoặc điều bất ngờ đã xảy ra, hoặc giả thuyết ban đầu sai. Logic có thể rắc rối, nhưng ý tưởng cơ bản rất hữu ích. Vậy điều gì có thể sai?

Hoá ra khá nhiều. Fisher hình dung tình huống như các ví dụ đầu chương: một bộ dữ liệu, một thước đo kết cục tóm tắt, và một kiểm định tương thích. Nhưng trong vài thập kỷ gần đây, giá trị P đã thành "tiền tệ" của nghiên cứu, xuất hiện với số lượng khổng lồ trong tài liệu khoa học — một nghiên cứu đã gom khoảng 30.000 thống kê t và giá trị P đi kèm chỉ từ ba năm bài báo trên mười tám tạp chí tâm lý học và thần kinh học (Szucs và Ioannidis, PLOS Biology 2017).

#### Cây tần số 1.000 nghiên cứu

Hãy xem điều gì sẽ xảy ra với, chẳng hạn, 1.000 nghiên cứu, mỗi nghiên cứu được thiết kế với mức α = 5% và lực 1 − β = 80%, lưu ý rằng thực tế phần lớn nghiên cứu có lực thấp hơn 80% đáng kể. Trong thế giới nghiên cứu thật, dù thí nghiệm được làm với hy vọng phát hiện điều mới, người ta thừa nhận rằng phần lớn giả thuyết không (ít nhất là xấp xỉ) đúng. Giả sử chỉ 10% giả thuyết không được kiểm định thật sự sai — ngay cả con số này có lẽ đã khá cao đối với thuốc mới, vốn nổi tiếng có tỷ lệ thành công thấp. Theo cách tương tự các ví dụ sàng lọc ở Chương 8, ta có các tần số kỳ vọng:

**Hình: Tần số kỳ vọng của kết cục 1.000 kiểm định giả thuyết với mức 5% và lực 80% (Figure 10.5 trong sách, cây tần số có ghi số)**

```text
                                    ┌─ bác bỏ H0 ............. 80  (phát hiện đúng)
             ┌─ H0 sai: 100 ────────┤
             │                      └─ không bác bỏ H0 ....... 20  (bỏ sót)
   1.000 ────┤
             │                      ┌─ bác bỏ H0 ............. 45  (phát hiện sai, 5%)
             └─ H0 đúng: 900 ───────┤
                                    └─ không bác bỏ H0 ...... 855
```

| | Bác bỏ giả thuyết không ("phát hiện") | Không bác bỏ | Tổng |
|---|---:|---:|---:|
| Giả thuyết không sai (có hiệu ứng thật) | 80 | 20 | 100 |
| Giả thuyết không đúng (không có hiệu ứng) | 45 | 855 | 900 |
| Tổng | 125 | 875 | 1.000 |

Từng bước: 10% của 1.000 là 100 giả thuyết không sai; lực 80% phát hiện đúng 80 trong số đó. 900 giả thuyết không đúng; mức 5% bác bỏ nhầm 900 × 0,05 = 45. Tổng số "phát hiện" là 80 + 45 = 125, trong đó 45 là dương tính giả: 45/125 = 36%, tức hơn một phần ba số giả thuyết không bị bác bỏ (các "phát hiện") là tuyên bố sai. Bức tranh khá ảm đạm này còn tệ hơn khi xét những gì thực sự được đăng trên tài liệu khoa học, vì các tạp chí thiên về đăng kết quả dương tính. Một phân tích tương tự về các nghiên cứu khoa học đã dẫn giáo sư y khoa và thống kê John Ioannidis ở Đại học Stanford tới tuyên bố nổi tiếng năm 2005 rằng "phần lớn kết quả nghiên cứu được công bố là sai". Chương 12 sẽ quay lại các lý do cho kết luận u ám này.

#### Lệnh cấm NHST và sáu nguyên tắc của ASA

Vì mọi phát hiện sai này đều dựa trên một giá trị P cho thấy kết quả "có ý nghĩa", giá trị P ngày càng bị đổ lỗi cho một làn sóng kết luận khoa học sai. Năm 2015, một tạp chí tâm lý học có uy tín còn tuyên bố cấm dùng NHST. Cuối cùng, năm 2016, Hiệp hội Thống kê Mỹ (American Statistical Association, ASA) đã đưa được một nhóm nhà thống kê đồng ý với sáu nguyên tắc về giá trị P. (Chú thích của tác giả, đùa: đây là một thành tựu đáng kể, vì danh từ tập hợp chỉ một nhóm nhà thống kê từng được nói đùa là một "phương sai" — variance, cũng có nghĩa "bất đồng".)

**Nguyên tắc 1 — giá trị P làm được gì:** *Giá trị P có thể cho biết dữ liệu không tương thích đến đâu với một mô hình thống kê cụ thể.* Như đã thấy nhiều lần, giá trị P làm điều này bằng cách đo về cơ bản dữ liệu bất ngờ đến đâu, khi cho trước một giả thuyết không rằng điều gì đó không tồn tại. Chẳng hạn, ta hỏi dữ liệu có không tương thích với việc thuốc không có tác dụng không. Logic có thể khó, nhưng hữu ích.

**Nguyên tắc 2 — sửa lỗi diễn giải:** *Giá trị P không đo xác suất giả thuyết được nghiên cứu là đúng, cũng không đo xác suất dữ liệu được tạo ra chỉ bởi ngẫu nhiên.* Ở Chương 8, sách đã cẩn thận phân biệt câu xác suất có điều kiện đúng như "chỉ 10% phụ nữ không bị ung thư vú có kết quả chụp nhũ ảnh dương tính" với câu sai "chỉ 10% phụ nữ có kết quả dương tính không bị ung thư vú". Đó là lỗi gọi là **ngộ nhận của bên công tố**, và có cách gọn để sửa: nghĩ xem điều gì sẽ xảy ra với 1.000 phụ nữ được xét nghiệm. Vấn đề tương tự xảy ra với giá trị P: nó đo khả năng dữ liệu cực đoan như vậy xuất hiện **nếu giả thuyết không đúng**, chứ **không** đo khả năng giả thuyết không đúng **khi đã thấy** dữ liệu cực đoan như vậy. Đây là khác biệt tinh tế nhưng cốt yếu.

Khi các nhóm ở CERN công bố kết quả "năm sigma" cho hạt Higgs, ứng với giá trị P khoảng 1 trên 3,5 triệu, BBC diễn đạt đúng: "khoảng một phần 3,5 triệu khả năng tín hiệu họ thấy sẽ xuất hiện nếu không có hạt Higgs". Nhưng gần như mọi cơ quan báo chí khác hiểu sai. Ví dụ, tạp chí *Forbes* viết "khả năng đó không phải hạt Higgs là dưới 1 phần triệu" — một ví dụ rõ ràng của ngộ nhận của bên công tố. Báo *The Independent* tiêu biểu khi viết "có ít hơn một phần triệu khả năng kết quả của họ là một sự tình cờ thống kê". Câu này có thể không sai trắng trợn như *Forbes*, nhưng vẫn gán xác suất nhỏ cho việc "kết quả của họ là sự tình cờ thống kê", mà về logic chính là nói đây là xác suất của giả thuyết không được kiểm định. Đó là lý do ASA nhấn mạnh rằng giá trị P **không** phải "xác suất dữ liệu được tạo ra chỉ bởi ngẫu nhiên".

**Nguyên tắc 3 — chống ám ảnh với ý nghĩa thống kê:** *Kết luận khoa học và quyết định kinh doanh hay chính sách không nên chỉ dựa vào việc giá trị P có vượt qua một ngưỡng cụ thể hay không.* Khi Fisher bắt đầu công bố các bảng giá trị thống kê vừa đủ để kết quả đạt "P < 0,05" hay "P < 0,01", có lẽ ông không ngờ các ngưỡng khá tuỳ tiện này sẽ chi phối các ấn phẩm khoa học, khiến mọi kết quả bị chia thành "có ý nghĩa" hoặc "không có ý nghĩa". Từ đó chỉ còn một bước ngắn để coi kết quả "có ý nghĩa" là phát hiện đã được chứng minh, tạo ra một tiền lệ quá đơn giản và nguy hiểm: đi thẳng từ dữ liệu tới kết luận mà không dừng lại suy nghĩ.

Một hậu quả tệ hại của phép chia đôi đơn giản này là hiểu sai "không có ý nghĩa". Giá trị P không có ý nghĩa cho thấy dữ liệu tương thích với giả thuyết không, nhưng không có nghĩa giả thuyết không đúng chính xác. Xét cho cùng, không có bằng chứng trực tiếp rằng một tội phạm có mặt ở hiện trường không có nghĩa là hắn vô tội. Nhưng lỗi này phổ biến đáng ngạc nhiên. Hãy xét cuộc tranh luận khoa học lớn về việc một lượng nhỏ rượu, chẳng hạn một ly mỗi ngày, có tốt cho sức khoẻ không. Một nghiên cứu (Knott và cộng sự, British Medical Journal, tháng 2/2015, gộp số liệu tới 10 nhóm thuần tập) khẳng định chỉ phụ nữ lớn tuổi có thể được lợi từ uống rượu vừa phải; nhưng xem kỹ thì các nhóm khác cũng có lợi ích, chỉ là không có ý nghĩa thống kê, vì khoảng tin cậy quanh lợi ích ước lượng ở các nhóm này rất rộng. Dù các khoảng tin cậy chứa 0 nên hiệu ứng không có ý nghĩa thống kê, dữ liệu hoàn toàn tương thích với mức giảm nguy cơ tử vong 10% tới 20% từng được đề xuất trước đó. Thế nhưng báo *The Times* (11/2/2015) giật tít "Rượu rốt cuộc chẳng có lợi gì cho sức khoẻ". Tóm lại, diễn giải "không khác 0 một cách có ý nghĩa" thành "hiệu ứng thật bằng 0" là rất sai lệch, nhất là với nghiên cứu nhỏ, lực thấp và khoảng tin cậy rộng.

**Nguyên tắc 4 — minh bạch:** *Suy luận đúng đắn đòi hỏi báo cáo đầy đủ và minh bạch.* Nhu cầu hiển nhiên nhất là báo cáo rõ đã thực sự làm bao nhiêu kiểm định, để nếu kết quả có ý nghĩa nhất được nhấn mạnh, ta có thể áp dụng một dạng hiệu chỉnh như Bonferroni. Nhưng vấn đề báo cáo chọn lọc có thể tinh vi hơn nhiều, như chương sau sẽ thấy. Chỉ khi biết kế hoạch nghiên cứu và những gì thực sự đã làm mới tránh được các vấn đề với giá trị P.

**Nguyên tắc 5 — ý nghĩa thống kê không phải tầm quan trọng:** *Giá trị P, hay ý nghĩa thống kê, không đo độ lớn của hiệu ứng hay tầm quan trọng của kết quả.* Bạn đã lập kế hoạch nghiên cứu, thu dữ liệu, phân tích và có kết quả "có ý nghĩa". Chắc hẳn đây là một phát hiện quan trọng? Nguyên tắc thứ năm cảnh báo đừng quá tự mãn. Ví dụ sau cho thấy, nhất là với mẫu lớn, ta có thể khá chắc một liên hệ tồn tại mà vẫn chẳng mấy ấn tượng về tầm quan trọng của nó.

*Khung ví dụ "Why Going to University Increases Risk of Getting a Brain Tumour" — "Vì sao học đại học làm tăng nguy cơ u não".* Tít báo này đã xuất hiện ở Chương 4. Sau khi điều chỉnh theo tình trạng hôn nhân và thu nhập trong một phân tích hồi quy, các nhà nghiên cứu Thuỵ Điển thấy nguy cơ tăng tương đối 19% giữa nhóm học vấn thấp nhất (chỉ tiểu học) và cao nhất (bằng đại học bậc cao), với khoảng tin cậy 95% từ 7% tới 33%. Thú vị là bài báo không báo cáo giá trị P nào, nhưng vì khoảng 95% của nguy cơ tương đối loại trừ 1 (tức loại trừ mức tăng 0%), ta có thể kết luận P < 0,05. Người đọc lúc này hẳn đã có sẵn danh sách lo ngại về kết luận, nhưng các tác giả đã nêu trước. Bên cạnh kết quả, họ thừa nhận: không thể diễn giải nhân quả; chưa điều chỉnh các yếu tố gây nhiễu thuộc lối sống như uống rượu; và người có địa vị kinh tế cao hơn có xu hướng đi khám nhiều hơn, nên có thể có thiên lệch báo cáo.

Nhưng một đặc điểm quan trọng không được nhắc tới: liên hệ có vẻ tồn tại này rất nhỏ. Mức tăng 19% giữa nhóm học vấn thấp nhất và cao nhất thấp hơn nhiều so với nhiều loại ung thư khác. Bài báo cho biết 3.715 ca u não được chẩn đoán trong hơn 2.000.000 nam giới theo dõi 18 năm (khoảng 1 trên 600), nên theo cách ở Chương 1 để chuyển nguy cơ tương đối thành thay đổi nguy cơ tuyệt đối:

- trong khoảng 3.000 nam giới ở nhóm học vấn thấp nhất, kỳ vọng khoảng 5 ca u não được chẩn đoán (nguy cơ nền 1 trên 600: 3.000/600 = 5);
- trong 3.000 nam giới ở nhóm học vấn cao nhất, kỳ vọng 6 ca (tăng tương đối 19%: 5 × 1,19 = 5,95 ≈ 6).

Cách trình bày này cho ấn tượng khác hẳn, và thật ra khá trấn an. Một mức tăng nguy cơ nhỏ như vậy ở một loại ung thư hiếm chỉ có thể có ý nghĩa thống kê khi nghiên cứu số người khổng lồ — ở đây hơn hai triệu nam giới. Bài học chính từ nghiên cứu này có thể là: (a) "dữ liệu lớn" dễ dẫn tới kết quả có ý nghĩa thống kê nhưng không có **ý nghĩa thực tế (practical significance)**; và (b) bạn không cần lo việc học lấy bằng sẽ khiến mình bị u não.

**Nguyên tắc 6 — giá trị P không phải thước đo bằng chứng tốt:** *Tự nó, giá trị P không phải thước đo tốt về bằng chứng liên quan tới một mô hình hay giả thuyết. Ví dụ, giá trị P gần 0,05 tự nó chỉ là bằng chứng yếu chống lại giả thuyết không.* Khẳng định này, một phần dựa trên lập luận Bayes ở chương sau, đã khiến một nhóm nhà thống kê nổi tiếng (Benjamin và cộng sự, Nature Human Behaviour 2018) đề nghị đổi ngưỡng chuẩn để công nhận "phát hiện" một hiệu ứng mới thành P < 0,005.

Tác động sẽ ra sao? Đổi tiêu chí "có ý nghĩa" từ 0,05 (1 trên 20) thành 0,005 (1 trên 200) trong cây tần số 1.000 nghiên cứu ở trên nghĩa là thay vì 45 "phát hiện" dương tính giả, chỉ còn 900 × 0,005 = 4,5. Tổng số phát hiện giảm còn 80 + 4,5 = 84,5, và trong đó chỉ 4,5 (4,5/84,5 = 5,3%, sách làm tròn 5%) là phát hiện sai — cải thiện đáng kể so với 36%. (Người tổng hợp lưu ý: phép tính này giữ nguyên lực 80%; với cùng cỡ mẫu, ngưỡng chặt hơn sẽ làm giảm lực, nên muốn giữ 80 phát hiện đúng thì nghiên cứu phải lớn hơn.)

#### Kết thúc chương: "giả kim thuật" biến bất định thành chắc chắn

Ý tưởng kiểm định giả thuyết ban đầu của Fisher đã đem lại lợi ích lớn cho thực hành thống kê và cho việc ngăn các tuyên bố khoa học thiếu căn cứ. Nhưng các nhà thống kê thường phàn nàn rằng một số nhà nghiên cứu sẵn sàng nhảy tuỳ tiện từ giá trị P của những nghiên cứu thiết kế kém tới những suy luận khái quát đầy tự tin — một kiểu giả kim thuật biến bất định thành chắc chắn, áp dụng máy móc các kiểm định thống kê để chia mọi kết quả thành "có ý nghĩa" và "không có ý nghĩa". Chương 12 sẽ cho thấy một số hậu quả tệ của hành vi này; nhưng trước đó, Chương 11 chuyển sang một cách tiếp cận suy luận thống kê khác, bác bỏ hoàn toàn ý tưởng kiểm định ý nghĩa giả thuyết không. Vì vậy, như một đòi hỏi "căng não" nữa của khoa học thống kê, tác giả mong người đọc (tạm thời) quên hết những gì có thể đã học từ chương này và các chương trước.

### 10. Tóm tắt (Summary, trang PDF 202)

- Kiểm định giả thuyết không — các giả định mặc định về mô hình thống kê — là một phần lớn của thực hành thống kê.
- Giá trị P là thước đo mức không tương thích giữa dữ liệu quan sát và một giả thuyết không: chính thức, đó là xác suất quan sát được một kết quả cực đoan như vậy nếu giả thuyết không đúng.
- Theo truyền thống, các ngưỡng giá trị P 0,05 và 0,01 được đặt ra để tuyên bố "có ý nghĩa thống kê".
- Các ngưỡng này cần được điều chỉnh nếu làm nhiều kiểm định, chẳng hạn trên các tập con khác nhau của dữ liệu hoặc nhiều thước đo kết cục.
- Có sự tương ứng chính xác giữa khoảng tin cậy và giá trị P: nếu, chẳng hạn, khoảng 95% loại trừ 0, ta có thể bác bỏ giả thuyết không "bằng 0" ở P < 0,05.
- Lý thuyết Neyman–Pearson nêu rõ một giả thuyết đối, và cố định tỷ lệ sai lầm loại I và loại II cho hai loại sai lầm có thể có trong một kiểm định giả thuyết.
- Có các dạng kiểm định giả thuyết riêng được phát triển cho kiểm định tuần tự.
- Giá trị P thường bị hiểu sai: đặc biệt, chúng không cho biết xác suất giả thuyết không đúng, và một kết quả không có ý nghĩa không có nghĩa là giả thuyết không đúng.

## Luận điểm cốt lõi

### Mệnh đề

Kiểm định giả thuyết là một thủ tục để chống lại phát hiện giả: giữ một giả thuyết không cho tới khi dữ liệu đủ bất ngờ dưới giả thuyết đó, đo mức bất ngờ bằng giá trị P. Thủ tục này hữu ích khi dùng đúng — một câu hỏi định trước, một kiểm định, ngưỡng được điều chỉnh cho số kiểm định đã làm — nhưng giá trị P chỉ là xác suất của dữ liệu khi giả thuyết không đúng; nó không phải xác suất giả thuyết đúng, không đo độ lớn hay tầm quan trọng của hiệu ứng, và việc chia máy móc kết quả thành "có" và "không có ý nghĩa" sinh ra rất nhiều kết luận sai.

### Giả định

- Mọi giá trị P đều tính dưới giả thuyết không **cùng với** mọi giả định khác của mô hình (không thiên lệch hệ thống, quan sát độc lập, phân phối đúng dạng như Poisson…); nếu các giả định đó sai, giá trị P sai.
- Giả thuyết không gần như không bao giờ đúng tuyệt đối; nó chỉ là giả định làm việc.
- Câu hỏi và thống kê kiểm định được chọn **trước khi** nhìn dữ liệu; nếu chọn sau, hoặc chọn kết quả tốt nhất trong nhiều kết quả, ngưỡng thông thường mất ý nghĩa.
- Trong thực tế nghiên cứu, phần lớn giả thuyết không được kiểm định là (xấp xỉ) đúng — giả định then chốt của cây tần số 1.000 nghiên cứu (chỉ 10% có hiệu ứng thật).
- Số tử vong và số vụ giết người theo phân phối Poisson (được kiểm tra với P = 0,96 cho dữ liệu giết người).

### Cơ chế

1. Đặt giả thuyết không H0 (và, theo Neyman–Pearson, một giả thuyết đối).
2. Chọn thống kê kiểm định mà giá trị cực đoan sẽ làm ta nghi H0.
3. Tạo phân phối của thống kê dưới H0: bằng hoán vị/mô phỏng, hoặc bằng lý thuyết (siêu bội, khi bình phương, t).
4. Tính giá trị P (diện tích đuôi, một hay hai phía).
5. So với ngưỡng α; ngưỡng phải được điều chỉnh cho kiểm định nhiều lần (Bonferroni, tỷ lệ phát hiện sai) và cho kiểm định lặp lại trên dữ liệu tích luỹ (SPRT).
6. Khi lập kế hoạch: chọn α và lực 1 − β cho một hiệu ứng hợp lý, quan trọng, từ đó ra cỡ mẫu.
7. Khi báo cáo: kèm khoảng tin cậy (tương đương với kiểm định), độ lớn hiệu ứng theo nguy cơ tuyệt đối, số kiểm định đã làm, và đòi lặp lại trước khi coi là phát hiện.

### Bằng chứng và ví dụ tác giả đưa ra

- Arbuthnot (1710): 82 năm liền bé trai nhiều hơn bé gái ở London; P = 1/2⁸² (một phía), 1/2⁸¹ (hai phía).
- Khoanh tay (54 nghiên cứu sinh, 2013): nữ 64%, nam 57% tay phải ở trên; kiểm định hoán vị cho P một phía 0,45, hai phía 0,89; kiểm định khi bình phương 0,02, P = 0,90.
- Nếm trà của Fisher: đoán đúng cả 4 cốc, P = 1/70.
- Giết người ở Anh và xứ Wales: 1.545 vụ trong 1.095 ngày; khớp Poisson với P = 0,96.
- Thất nghiệp ở Anh: −3.000 ± 77.000; khoảng tin cậy chứa 0, không có ý nghĩa.
- HPS: statin giảm nhồi máu cơ tim 27% (21%–33%), đột quỵ 25% (15%–34%), tử vong mọi nguyên nhân 13% (6%–19%, P = 0,0003); thiết kế với lực trên 90% ở α = 0,01 nên cần hơn 20.000 người.
- Hồi quy Galton trong R: hệ số chiều cao mẹ 0,334 (t = 7,25), bố 0,412 (t = 8,82).
- Titanic: cây phân loại hơn mạng nơ-ron 0,003 điểm Brier, t = −0,54, P = 0,59.
- Kiểm định nhiều lần: 10 thử nghiệm thuốc vô dụng cho 40% khả năng có ít nhất một "phát hiện"; cá hồi chết: 16/8.064 vùng não "có ý nghĩa".
- FDA: hai thử nghiệm, xác suất duyệt nhầm 1/400; hệ gen: ngưỡng 1 trên 20 triệu; Higgs: năm sigma, P khoảng 1 trên 3,5 triệu.
- Shipman: vượt 174 nữ và 49 nam đến 1998; P = 0,004 năm 1979 nếu kiểm định ngây thơ; Bonferroni và SPRT đều báo động năm 1984; khoảng 175 người có thể được cứu; một bác sĩ khác bị báo động vì chăm sóc người già tại nhà.
- Cây tần số 1.000 nghiên cứu: 36% phát hiện là sai ở ngưỡng 0,05; 5% ở ngưỡng 0,005.
- Báo chí đưa tin về Higgs (Forbes, The Independent sai; BBC đúng); The Times về rượu; nghiên cứu Thuỵ Điển về học vấn và u não (tăng 19%, tức 5 so với 6 ca trên 3.000 người).

### Kết luận và hàm ý cho người đọc số liệu

- Khi thấy "có ý nghĩa thống kê", hãy hỏi: đã làm bao nhiêu kiểm định? giá trị P chính xác là bao nhiêu (0,049 chỉ là bằng chứng yếu)? hiệu ứng lớn đến đâu theo số tuyệt đối? đã được lặp lại chưa?
- Khi thấy "không có ý nghĩa thống kê", hãy xem khoảng tin cậy: nếu khoảng rộng và chứa cả những hiệu ứng quan trọng, kết luận đúng là "chưa biết", không phải "không có tác dụng".
- Đừng đọc giá trị P thành "xác suất kết quả là tình cờ" hay "xác suất giả thuyết sai".
- Khi giám sát liên tục (bác sĩ, bệnh viện, dây chuyền sản xuất, chỉ số kinh tế theo tháng), kiểm định lặp lại với ngưỡng cố định chắc chắn cho báo động giả; cần phương pháp tuần tự và ngưỡng điều chỉnh cho số đơn vị được giám sát.
- Một báo động thống kê chỉ là tín hiệu để điều tra, không phải bằng chứng về nguyên nhân hay về lỗi của ai.

### Trong ngôn ngữ thống kê

Chương trình bày khung kiểm định giả thuyết tần suất: giá trị P = Pr(T ≥ t | H0) (một phía) hoặc tổng xác suất hai đuôi; ý nghĩa thống kê khi P < α. Các phân phối dưới H0: phân phối hoán vị (kiểm định chính xác Fisher qua phân phối siêu bội), xấp xỉ khi bình phương X² = Σ(o − e)²/e cho bảng tiếp liên và độ khớp, thống kê t = ước lượng/SE cho hệ số hồi quy và kiểm định ghép cặp. Tính đối ngẫu giữa kiểm định và khoảng tin cậy: khoảng tin cậy 100(1 − α)% là tập các giá trị tham số không bị bác bỏ ở mức α hai phía. Khung Neyman–Pearson: α = Pr(bác bỏ H0 | H0), β = Pr(không bác bỏ | H1), lực = 1 − β, cỡ mẫu xác định từ (α, β, hiệu ứng tối thiểu). Kiểm định nhiều lần: kiểm soát sai số theo họ (familywise error rate) bằng Bonferroni α/n, kiểm soát tỷ lệ phát hiện sai (theo hiểu biết của người tổng hợp, "kỹ thuật đơn giản" sách nhắc tới chính là thủ tục Benjamini–Hochberg). Kiểm định tuần tự: SPRT của Wald với log tỷ số khả năng tích luỹ so với ngưỡng ln((1 − β)/α). Giá trị dự báo dương của một "phát hiện" (1 − tỷ lệ phát hiện sai) phụ thuộc vào xác suất tiên nghiệm của giả thuyết đối: PPV = (1 − β)π / [(1 − β)π + α(1 − π)], với π = 0,1, α = 0,05, 1 − β = 0,8 cho 0,08/0,125 = 64%.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| hypothesis | giả thuyết | giả định tạm thời về một thành phần của mô hình thống kê |
| hypothesis testing | kiểm định giả thuyết | thủ tục đánh giá dữ liệu ủng hộ hay chống một giả thuyết đến đâu |
| null hypothesis (H0) | giả thuyết không | giả định mặc định "không có hiệu ứng", giữ cho tới khi bị bác bỏ |
| alternative hypothesis | giả thuyết đối | lời giải thích thay thế, thường là một hiệu ứng hợp lý và quan trọng |
| apophenia | ảo giác quy luật (apophenia) | xu hướng thấy quy luật ở nơi không có |
| sex ratio | tỷ số giới tính | số bé trai trên 100 bé gái |
| cross-tabulation / contingency table | bảng chéo / bảng tiếp liên | bảng đếm theo hai biến phân loại |
| test statistic | thống kê kiểm định | con số tóm tắt dữ liệu dùng để kiểm định |
| permutation / randomization test | kiểm định hoán vị / ngẫu nhiên hoá | tạo phân phối dưới H0 bằng cách xáo nhãn |
| hypergeometric distribution | phân phối siêu bội | xác suất khi rút không hoàn lại từ tổng thể hữu hạn |
| P-value | giá trị P | xác suất có kết quả cực đoan ít nhất như đã thấy nếu H0 đúng |
| tail-area | diện tích đuôi | phần xác suất ở đuôi phân phối, chính là giá trị P |
| one-sided / two-sided test | kiểm định một phía / hai phía | coi giá trị cực đoan theo một chiều hay cả hai chiều |
| one-tailed / two-tailed P-value | giá trị P một đuôi / hai đuôi | giá trị P của kiểm định một phía / hai phía |
| statistical significance | ý nghĩa thống kê | P nhỏ hơn ngưỡng định trước |
| Null Hypothesis Significance Testing (NHST) | kiểm định ý nghĩa giả thuyết không | quy trình sáu bước của Fisher |
| chi-squared test of association | kiểm định khi bình phương về liên hệ | so số quan sát với số kỳ vọng trong bảng tiếp liên |
| chi-squared goodness-of-fit test | kiểm định khi bình phương về độ khớp | so phân phối quan sát với một phân phối giả định |
| t-statistic / t-value, Student's t | thống kê t / giá trị t, t của Student | ước lượng chia sai số chuẩn |
| paired t-test | kiểm định t ghép cặp | kiểm định t trên các hiệu số theo cặp |
| Brier score | điểm Brier | sai số dự báo bình phương trung bình |
| false-positive | dương tính giả | tuyên bố có hiệu ứng khi không có |
| multiple testing | kiểm định nhiều lần | làm nhiều kiểm định rồi chọn kết quả nổi bật |
| Bonferroni correction | hiệu chỉnh Bonferroni | dùng ngưỡng α/n cho mỗi kiểm định |
| false discovery rate | tỷ lệ phát hiện sai | tỷ lệ "phát hiện" hoá ra là sai |
| replication | lặp lại nghiên cứu | làm lại thí nghiệm trong hoàn cảnh khác cùng quy trình |
| five-sigma | năm sigma | cách giả thuyết không 5 sai số chuẩn |
| look elsewhere effect | hiệu ứng nhìn chỗ khác | tên trong vật lý của hiệu chỉnh kiểm định nhiều lần |
| inductive behaviour | hành vi quy nạp | quan điểm Neyman–Pearson coi kiểm định là quy tắc ra quyết định |
| Type I error | sai lầm loại I | bác bỏ H0 khi H0 đúng (kết tội oan) |
| Type II error | sai lầm loại II | không bác bỏ H0 khi giả thuyết đối đúng (tha kẻ có tội) |
| size of a test (α) | mức của kiểm định (α) | xác suất sai lầm loại I, cũng là ngưỡng của P |
| power of a test (1 − β) | lực kiểm định (1 − β) | xác suất phát hiện đúng hiệu ứng thật |
| sequential testing | kiểm định tuần tự | kiểm định lặp lại trên dữ liệu tích luỹ |
| Law of the Iterated Logarithm | luật lôgarit lặp | định lý cho thấy kiểm định lặp lại chắc chắn sẽ bác bỏ H0 |
| Sequential Probability Ratio Test (SPRT) | kiểm định tỷ số xác suất tuần tự | thống kê tích luỹ so với ngưỡng cố định, kiểm soát α và β |
| excess mortality | tử vong vượt kỳ vọng | số tử vong quan sát trừ số kỳ vọng |
| prosecutor's fallacy | ngộ nhận của bên công tố | đảo chiều xác suất có điều kiện |
| practical significance | ý nghĩa thực tế | hiệu ứng có tầm quan trọng thật |
| relative / absolute risk | nguy cơ tương đối / tuyệt đối | tỷ lệ tăng so với nền / số ca thay đổi thực |

## Câu nói đáng nhớ

> "It is relentlessly negative, denying all progress and change." — mục "Why Do We Need Formal Testing of Null Hypotheses?"
>
> *Dịch: Nó (giả thuyết không) phủ định một cách kiên định, chối bỏ mọi tiến bộ và thay đổi.*

> "The null hypothesis is never proved or established, but is possibly disproved, in the course of experimentation." — Ronald Fisher, được trích trong mục "Why Do We Need Formal Testing of Null Hypotheses?"
>
> *Dịch: Giả thuyết không không bao giờ được chứng minh hay xác lập, mà chỉ có thể bị bác bỏ, trong quá trình thực nghiệm.*

> "A P-value is the probability of getting a result at least as extreme as we did, if the null hypothesis (and all other modelling assumptions) were really true." — mục "Why Do We Need Formal Testing of Null Hypotheses?"
>
> *Dịch: Giá trị P là xác suất có được một kết quả cực đoan ít nhất như kết quả ta đã có, nếu giả thuyết không (và mọi giả định khác của mô hình) thật sự đúng.*

> "The lesson here is that while statistical systems can detect outlying outcomes, they cannot offer reasons why these might have occurred." — khung câu hỏi về Harold Shipman
>
> *Dịch: Bài học ở đây là hệ thống thống kê có thể phát hiện kết cục bất thường, nhưng không đưa ra được lý do vì sao chúng xảy ra.*

> "P-values do not measure the probability that the studied hypothesis is true, or the probability that the data were produced by random chance alone." — nguyên tắc thứ hai của ASA, được trích trong khung "What could go wrong with P-values?"
>
> *Dịch: Giá trị P không đo xác suất giả thuyết được nghiên cứu là đúng, cũng không đo xác suất dữ liệu được tạo ra chỉ bởi ngẫu nhiên.*

> "After all, just because there's no direct evidence that a criminal was at the scene of a crime, that does not mean he is innocent." — khung "What could go wrong with P-values?"
>
> *Dịch: Xét cho cùng, không có bằng chứng trực tiếp rằng một tội phạm có mặt ở hiện trường không có nghĩa là hắn vô tội.*

> "A kind of alchemy for turning uncertainty into certainty." — khung "What could go wrong with P-values?"
>
> *Dịch: Một kiểu giả kim thuật biến bất định thành chắc chắn.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: dạy kiểm định giả thuyết bằng hoán vị trước, công thức sau

Thay vì mở đầu bằng công thức và bảng tra, Spiegelhalter dựng giá trị P từ một thí nghiệm tưởng tượng ai cũng hình dung được: trộn vé khoanh tay trong mũ rồi chia lại. Người đọc thấy tận mắt phân phối dưới giả thuyết không và thấy giá trị P là một diện tích đuôi, rồi mới biết rằng phân phối siêu bội, kiểm định khi bình phương và thống kê t chỉ là những cách tính tắt cho cùng câu hỏi. Đây cũng là cách tiếp cận mà theo hiểu biết của người tổng hợp nhiều giáo trình thống kê nhập môn hiện đại (dạy bằng mô phỏng) đã chọn. Việc chạy lại năm câu hỏi xuyên suốt sách dưới lăng kính kiểm định — từ Poisson, thất nghiệp, statin, Galton tới Higgs — giúp nối chương này với toàn bộ phần trước và cho thấy cùng một logic áp dụng cho mọi loại câu hỏi.

### Điểm mạnh: thẳng thắn về giới hạn của chính công cụ mình dạy

Gần một phần ba chương dành cho những cách giá trị P sai: kiểm định nhiều lần, kiểm định lặp lại, ngộ nhận của bên công tố, "không có ý nghĩa" bị hiểu thành "không có tác dụng", "có ý nghĩa" bị hiểu thành "quan trọng". Cây tần số 1.000 nghiên cứu là công cụ trực quan rất mạnh: nó cho thấy tỷ lệ phát hiện sai phụ thuộc vào tỷ lệ giả thuyết thật sự đúng — điều không giá trị P nào cho biết — và nối thẳng sang lập luận Bayes ở Chương 11. Ví dụ Shipman, nơi tác giả là người trong cuộc, vừa chứng minh sức mạnh của giám sát thống kê (175 sinh mạng) vừa cho thấy rủi ro buộc tội oan (bác sĩ chăm sóc người già tại nhà) — một cân bằng hiếm thấy.

### Điểm yếu và đơn giản hoá

- **Một số lỗi kỹ thuật** (đã nêu ở khối Lưu ý): Higgs được gọi là "hai phía"; ký hiệu β bị dùng thay cho lực 1 − β; chú thích Shipman ghi 22,5 thay vì 25,3; thống kê khi bình phương 0,02 thực ra là bản hiệu chỉnh Yates mà sách không nêu; giá trị P hai phía 0,89 không khớp với định nghĩa "ít nhất 7% theo cả hai chiều" (≈ 0,76). Với một chương dạy người đọc cẩn thận với giá trị P, những chỗ này đáng tiếc, dù không chỗ nào làm đổi kết luận.
- **Phép tính ngưỡng 0,005 giữ nguyên lực 80%.** Theo hiểu biết của người tổng hợp, với cùng cỡ mẫu, chuyển từ α = 0,05 sang 0,005 làm lực giảm (một nghiên cứu có lực 80% ở α = 0,05 hai phía chỉ còn khoảng 50% ở α = 0,005); muốn giữ lực 80% cần tăng cỡ mẫu khoảng 70%. Như vậy con số "5% phát hiện sai" đúng với điều kiện nghiên cứu lớn hơn; với cùng nguồn lực, số phát hiện đúng sẽ giảm. Đánh đổi này — chính là đánh đổi α và lực mà mục Neyman–Pearson vừa giải thích — không được nhắc tới.
- **Quy tắc FDA "1 trên 400".** Theo hiểu biết của người tổng hợp, yêu cầu P < 0,05 hai phía thường được hiểu là phải có lợi ích theo đúng chiều, tức mức 0,025 mỗi thử nghiệm; khi đó xác suất hai thử nghiệm đều "có lợi" nhầm là 0,025² = 1 trên 1.600. Con số 1/400 của sách là cận trên đơn giản hoá.
- **Cây tần số giả định lực 80% và 10% giả thuyết đúng.** Tác giả có nói thực tế lực thường thấp hơn; với lực thấp hơn, tỷ lệ phát hiện sai còn cao hơn (ví dụ lực 40%: 45/(40 + 45) = 53%, người tổng hợp tính).
- **Kiểm định giả thuyết về giới hạn của mô hình được nói tới nhưng chưa được minh hoạ.** Sách nhắc nhiều lần rằng giá trị P phụ thuộc mọi giả định của mô hình, nhưng không có ví dụ nào cho thấy giá trị P sai khi giả định độc lập hay không thiên lệch bị vi phạm; phần này được để cho Chương 12.

### Điều đã thay đổi từ 2019 (theo hiểu biết của người tổng hợp, không tra cứu)

- Ngay tháng 3/2019 (cùng lúc sách ra ở Anh), tạp chí *The American Statistician* của ASA ra số đặc biệt "A World Beyond p < 0.05" với bài xã luận khuyên ngừng dùng cụm "statistically significant"; cùng tháng, bài bình luận "Retire statistical significance" trên *Nature* (Amrhein, Greenland, McShane) có hơn 800 nhà khoa học ký tên. Năm 2021, một nhóm công tác do chủ tịch ASA lập lại ra tuyên bố cân bằng hơn rằng giá trị P và kiểm định ý nghĩa, dùng đúng, giúp tăng độ chặt chẽ. Tranh luận giữa "bỏ ngưỡng", "hạ ngưỡng xuống 0,005" và "giữ nguyên nhưng dùng đúng" vẫn chưa ngã ngũ.
- Các biện pháp chống báo cáo chọn lọc mà nguyên tắc 4 của ASA đòi hỏi đã phổ biến hơn: đăng ký trước kế hoạch phân tích, hình thức bài báo "registered report" (tạp chí nhận đăng dựa trên đề cương trước khi có kết quả), và các dự án lặp lại quy mô lớn trong tâm lý học, kinh tế học thực nghiệm.
- Trong đại dịch COVID-19 (2020–2022), nhiều thử nghiệm lâm sàng (như RECOVERY ở Anh) dùng thiết kế thích ứng với các lần phân tích giữa kỳ được kiểm soát theo kiểu tuần tự — đúng loại phương pháp bắt nguồn từ SPRT mà chương mô tả; đồng thời làn sóng tiền ấn phẩm với giá trị P "có ý nghĩa" từ các nghiên cứu nhỏ (ví dụ về hydroxychloroquine, ivermectin) minh hoạ sinh động các cảnh báo của chương.
- Giám sát kết cục của bác sĩ và bệnh viện bằng các biểu đồ tích luỹ (CUSUM, SPRT điều chỉnh rủi ro) đã thành thông lệ ở Anh sau vụ Shipman và vụ Bristol.

### Liên hệ các chương khác

- [00-gioi-thieu.md](00-gioi-thieu.md): vụ Harold Shipman và chu trình PPDAC lần đầu xuất hiện; Chương 10 trả lời câu hỏi "có thể bắt ông ta sớm hơn không".
- [C01-ty-le-du-lieu-phan-loai-va-phan-tram.md](C01-ty-le-du-lieu-phan-loai-va-phan-tram.md): cách chuyển nguy cơ tương đối thành nguy cơ tuyệt đối, dùng lại cho ví dụ u não (19% thành 5 so với 6 ca trên 3.000 người).
- [C04-cai-gi-gay-ra-cai-gi.md](C04-cai-gi-gay-ra-cai-gi.md): ngẫu nhiên hoá của Fisher, kết quả HPS (bảng statin) và tít báo về học đại học và u não.
- [C05-mo-hinh-hoa-quan-he-bang-hoi-quy.md](C05-mo-hinh-hoa-quan-he-bang-hoi-quy.md): mô hình "quan sát = tất định + sai số" và hồi quy bội chiều cao của Galton, nay được kèm giá trị t và giá trị P.
- [C06-thuat-toan-phan-tich-va-du-bao.md](C06-thuat-toan-phan-tich-va-du-bao.md): cuộc thi dự báo Titanic và điểm Brier; Chương 10 chỉ ra chiến thắng không có ý nghĩa thống kê.
- [C07-uoc-luong-va-khoang.md](C07-uoc-luong-va-khoang.md): khoảng tin cậy, biên sai số thất nghiệp ± 77.000 và Neyman–Pearson với tư cách người đặt ra khoảng tin cậy; Chương 10 chứng minh tính đối ngẫu giữa khoảng tin cậy và kiểm định.
- [C08-xac-suat-ngon-ngu-cua-bat-dinh.md](C08-xac-suat-ngon-ngu-cua-bat-dinh.md): phân phối Poisson cho số vụ giết người, cây tần số sàng lọc 1.000 phụ nữ và ngộ nhận của bên công tố — được dùng lại cho cây 1.000 nghiên cứu và cho cách báo chí đưa tin về Higgs.
- [C09-ket-hop-xac-suat-va-thong-ke.md](C09-ket-hop-xac-suat-va-thong-ke.md): dùng lý thuyết xác suất để tính khoảng tin cậy và đánh giá thay đổi tỷ lệ giết người, dựa trên giả định Poisson được kiểm định ở đây.
- [C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md](C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md): cách tiếp cận Bayes bác bỏ kiểm định giả thuyết không; giải thích vì sao P gần 0,05 chỉ là bằng chứng yếu; kể cuộc tranh cãi giữa Fisher và Neyman–Pearson.
- [C12-nhung-dieu-co-the-sai.md](C12-nhung-dieu-co-the-sai.md): Ioannidis và "phần lớn kết quả công bố là sai", khủng hoảng lặp lại, báo cáo chọn lọc.
- [C13-lam-thong-ke-tot-hon.md](C13-lam-thong-ke-tot-hon.md) và [C14-ket-luan.md](C14-ket-luan.md): cách làm và truyền đạt thống kê đáng tin hơn; [PL-bang-thuat-ngu.md](PL-bang-thuat-ngu.md): định nghĩa giá trị P, lực, mức, Bonferroni, kiểm định tuần tự.

### Vận dụng

- **Cho người đọc báo:** khi thấy "nghiên cứu cho thấy X liên quan tới Y", hãy tìm (1) khoảng tin cậy hoặc ít nhất là cỡ mẫu, (2) độ lớn theo số ca tuyệt đối thay vì phần trăm tương đối, (3) đây là một kết quả đơn lẻ hay đã được lặp lại. Câu "ít hơn một phần triệu khả năng là tình cờ" gần như chắc chắn là diễn giải sai một giá trị P. Câu "không tìm thấy lợi ích" có thể chỉ có nghĩa là nghiên cứu quá nhỏ để thấy.
- **Cho nhà phân tích:** ghi lại trước những gì sẽ kiểm định; đếm và báo cáo tổng số kiểm định đã làm, kể cả các phân tích nhóm con; điều chỉnh ngưỡng (Bonferroni hay tỷ lệ phát hiện sai) khi quét nhiều biến, nhiều sản phẩm, nhiều khu vực; báo cáo giá trị P chính xác kèm khoảng tin cậy và độ lớn hiệu ứng; khi so sánh mô hình dự báo, kiểm định chênh lệch (như kiểm định t ghép cặp trên sai số) trước khi tuyên bố mô hình nào "tốt hơn"; khi theo dõi một chỉ số theo thời gian, đừng kiểm định lại mỗi kỳ với ngưỡng 0,05 mà dùng phương pháp tuần tự.
- **Cho người làm chính sách:** một hệ thống giám sát hàng nghìn đơn vị (bệnh viện, trường học, chi nhánh, doanh nghiệp) với ngưỡng 5% sẽ đều đặn "phát hiện" khoảng 5% đơn vị vô tội mỗi kỳ; cần ngưỡng điều chỉnh theo số đơn vị, phương pháp tuần tự, và quy trình điều tra kín trước khi công bố tên. Không nên ra quyết định chỉ vì một kết quả qua hay không qua ngưỡng 0,05 (nguyên tắc 3 của ASA); khi đặt hàng nghiên cứu đánh giá chính sách, hãy đòi tính lực kiểm định trước để tránh tốn tiền cho một nghiên cứu quá nhỏ, rồi kết luận sai rằng chính sách "không có tác dụng".
