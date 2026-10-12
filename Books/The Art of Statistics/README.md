# Nghệ thuật thống kê — David Spiegelhalter (2019)

*The Art of Statistics: How to Learn from Data.* Mỗi chương được tổng hợp thành một file riêng. File nào cũng đi qua đủ từng tiểu mục của chương theo đúng thứ tự, chép lại mọi bảng, đọc số liệu từ mọi hình (số đọc từ trục được ghi là ước lượng), đưa chú thích cuối chương và chú thích dấu sao vào đúng chỗ, và **mọi phép tính của sách đã được người tổng hợp tính lại**. Sau đó là các khái niệm cần biết, luận điểm cốt lõi, bảng thuật ngữ Anh–Việt và phần đánh giá: chỗ nào sách tính nhầm hoặc viết chưa chặt, điều gì đã thay đổi từ 2019, cách vận dụng cho người đọc báo, nhà phân tích và người làm chính sách. Bảng thuật ngữ cuối sách (158 mục) được dịch đầy đủ thành một file riêng.

**Tác giả:** Sir David Spiegelhalter, nhà thống kê ở Đại học Cambridge, chủ tịch Trung tâm Winton về Truyền đạt Rủi ro và Bằng chứng, nguyên chủ tịch Hội Thống kê Hoàng gia Anh, được phong tước hiệp sĩ vì đóng góp cho thống kê. Ông nổi tiếng về truyền đạt rủi ro và bất định cho công chúng.

**Nguồn:** bản ebook PDF tiếng Anh 397 trang, bản Mỹ đầu tiên của Basic Books (tháng 9/2019); bản gốc do Pelican (Penguin) xuất bản ở Anh tháng 3/2019.

> **Lưu ý về nguồn:**
> - **Ebook không có số trang in.** Các file ghi vị trí bằng "trang PDF n" (đánh số từ 0) và bằng tên tiểu mục tiếng Anh của sách.
> - **Mọi hình trong sách là ảnh, phần lớn không ghi số.** Số liệu đọc từ đồ thị được ghi rõ là ước lượng; khi có thể, người tổng hợp tính lại từ bảng hoặc công thức để đối chiếu.
> - **Sách có một số lỗi tính toán và chỗ viết chưa chặt; bản tổng hợp ghi cả số của sách và số đúng** (nhận xét của người tổng hợp, chưa đối chiếu danh sách đính chính). Đáng kể nhất:
>   - Chương 1: số liệu HES "62 ca tử vong trên 505 (14%)", đúng là 12,3%.
>   - Chương 2: độ lệch chuẩn sau khi bỏ một lần đoán 31.337 hạt kẹo ghi 1.398, tính lại chỉ xuống khoảng 2.226.
>   - Chương 3: cân nặng sơ sinh in "2.190 g", đúng là 2.910 g.
>   - Chương 5: độ dốc hồi quy ở bảng không khớp với độ lệch chuẩn và hệ số tương quan của chính sách.
>   - Chương 6: nhãn hàng và cột của bảng ma trận lỗi Titanic có vẻ bị đảo; lời văn về cây phân loại nói ngược với hình.
>   - Chương 8–10: giai đoạn số liệu giết người ghi "4/2014–3/2016" nhưng là 1.095 ngày (ba năm), gần như chắc là 4/2013–3/2016.
>   - Chương 10: giá trị P "1 trên 3,5 triệu" của hạt Higgs là một phía, không phải hai phía.
>   - Chương 11: xác suất chia được thùng phá sảnh lớn (royal flush) là 1/649.740, không phải 1/72.000; bài toán đinh ghim trả lời cho "mũi lên" dù câu hỏi là "mũi xuống".
>   - Bảng thuật ngữ: công thức hệ số tương quan Pearson in thiếu dấu căn; nhân tố Bayes được định nghĩa ngược chiều với cách dùng ở Chương 11.
> - **Danh sách chú thích dấu sao trong ebook nằm dồn ở cuối sách** không ghi thuộc chương nào; người tổng hợp khớp từng chú thích với dấu `*` trong lời văn.
> - **Sách còn bản quyền.** Bản tổng hợp diễn đạt lại bằng lời mới; câu trích nguyên văn chủ yếu nằm ở mục "Câu nói đáng nhớ".

## Chuỗi lập luận của cả cuốn sách

```text
       GIỚI THIỆU — VÌ SAO CẦN THỐNG KÊ
       · vụ Harold Shipman: dữ liệu đã có thể phát hiện kẻ giết người sớm
         hơn nhiều năm
       · khoa học dữ liệu và thống kê; chu trình giải quyết vấn đề PPDAC:
         Vấn đề → Kế hoạch → Dữ liệu → Phân tích → Kết luận
                                │
                                ▼
       KHÁM PHÁ VÀ TRÌNH BÀY DỮ LIỆU (Chương 1–2)
       · C1: một tỷ lệ phần trăm cũng không tự nói; cách trình bày (khung,
         rủi ro tương đối hay tuyệt đối, trục đồ thị) thay đổi ấn tượng
       · C2: tóm tắt nhiều con số: trung bình, trung vị, độ phân tán,
         tương quan; vẽ dữ liệu trước khi tính
                                │
                                ▼
       TỪ DỮ LIỆU TỚI TỔNG THỂ VÀ NHÂN QUẢ (Chương 3–5)
       · C3: suy diễn quy nạp qua bốn bậc dữ liệu → mẫu → tổng thể nghiên
         cứu → tổng thể mục tiêu; chọn mẫu ngẫu nhiên; phân phối chuẩn
       · C4: tương quan không phải nhân quả; thử nghiệm ngẫu nhiên có đối
         chứng; nghịch lý Simpson; tiêu chí Bradford Hill
       · C5: hồi quy, hồi quy về giá trị trung bình, mô hình là công cụ
         đơn giản hoá
                                │
                                ▼
       DỰ BÁO BẰNG THUẬT TOÁN (Chương 6)
       · phân loại và dự báo (Titanic, dự báo mưa, ung thư vú); quá khớp;
         đánh giá trên dữ liệu mới bằng ROC, điểm Brier; minh bạch
                                │
                                ▼
       BẤT ĐỊNH VÀ XÁC SUẤT (Chương 7–9)
       · C7: ước lượng luôn cần khoảng bất định; bootstrap
       · C8: xác suất là ngôn ngữ của bất định; cây tần suất kỳ vọng;
         phân phối Poisson
       · C9: phân phối mẫu, định lý giới hạn trung tâm, khoảng tin cậy,
         biên sai số của thăm dò ý kiến, biểu đồ phễu
                                │
                                ▼
       KIỂM ĐỊNH VÀ SUY LUẬN (Chương 10–11)
       · C10: giả thuyết không, giá trị P, nhiều phép thử, kiểm định tuần
         tự (Shipman), cách giá trị P bị dùng sai
       · C11: cách Bayes: tiên nghiệm × tỷ số khả năng; Richard III,
         doping, tổng giám mục chơi bài; nhân tố Bayes
                                │
                                ▼
       KHI MỌI THỨ SAI VÀ CÁCH LÀM TỐT HƠN (Chương 12–14)
       · C12: khủng hoảng tái lập, thực hành nghiên cứu đáng ngờ, truyền
         thông thổi phồng
       · C13: làm thống kê tốt hơn: minh bạch, đáng tin cậy, đọc phê phán
       · C14: mười quy tắc đơn giản cho thực hành thống kê hiệu quả
```

## Mục lục

- [Giới thiệu — Vì sao chúng ta cần thống kê](00-gioi-thieu.md) (Introduction): vụ Harold Shipman; thống kê và khoa học dữ liệu; chu trình PPDAC; cấu trúc cuốn sách
- [Chương 1 — Đặt mọi thứ đúng tỷ lệ: dữ liệu phân loại và tỷ lệ phần trăm](C01-ty-le-du-lieu-phan-loai-va-phan-tram.md) (Getting Things in Proportion): phẫu thuật tim trẻ em ở Bristol; khung tích cực và tiêu cực; rủi ro tương đối và tuyệt đối (bánh mì thịt xông khói)
- [Chương 2 — Tóm tắt và truyền đạt con số](C02-tom-tat-va-truyen-dat-con-so.md) (Summarizing and Communicating Numbers. Lots of Numbers): đoán số kẹo; trung bình, trung vị, mốt; số bạn tình (Natsal); tương quan Pearson và Spearman; dân số thế giới
- [Chương 3 — Tổng thể và đo lường](C03-tong-the-va-do-luong.md) (Why Are We Looking at Data Anyway? Populations and Measurement): suy diễn quy nạp; chọn mẫu ngẫu nhiên; cân nặng sơ sinh và phân phối chuẩn
- [Chương 4 — Cái gì gây ra cái gì?](C04-cai-gi-gay-ra-cai-gi.md) (What Causes What?): thử nghiệm statin; biến gây nhiễu; nghịch lý Simpson (tuyển sinh Cambridge); tiêu chí Bradford Hill
- [Chương 5 — Mô hình hoá quan hệ bằng hồi quy](C05-mo-hinh-hoa-quan-he-bang-hoi-quy.md) (Modelling Relationships Using Regression): chiều cao cha mẹ và con (Galton); hồi quy về giá trị trung bình; hồi quy bội và hồi quy logistic
- [Chương 6 — Thuật toán, phân tích và dự báo](C06-thuat-toan-phan-tich-va-du-bao.md) (Algorithms, Analytics and Prediction): cây phân loại Titanic; quá khớp; ROC và điểm Brier; Predict 2.1 cho ung thư vú
- [Chương 7 — Ước lượng và khoảng](C07-uoc-luong-va-khoang.md) (How Sure Can We Be About What Is Going On? Estimates and Intervals): số liệu thất nghiệp; bootstrap; khoảng bất định
- [Chương 8 — Xác suất: ngôn ngữ của bất định và biến thiên](C08-xac-suat-ngon-ngu-cua-bat-dinh.md) (Probability—the Language of Uncertainty and Variability): trò chơi của Chevalier de Méré; cây tần suất kỳ vọng; sàng lọc ung thư vú; phân phối Poisson cho số vụ giết người
- [Chương 9 — Kết hợp xác suất và thống kê](C09-ket-hop-xac-suat-va-thong-ke.md) (Putting Probability and Statistics Together): người thuận tay trái; định lý giới hạn trung tâm; khoảng tin cậy; biểu đồ phễu; thăm dò bầu cử 2017
- [Chương 10 — Trả lời câu hỏi và tuyên bố phát hiện](C10-tra-loi-cau-hoi-va-tuyen-bo-phat-hien.md) (Answering Questions and Claiming Discoveries): giá trị P; khoanh tay; kiểm định tuần tự (Shipman); hạt Higgs; nhiều phép thử
- [Chương 11 — Học từ kinh nghiệm theo cách Bayes](C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md) (Learning from Experience the Bayesian Way): định lý Bayes; tỷ số khả năng; Richard III; tổng giám mục chơi bài; hồi quy đa mức kèm hậu phân tầng (MRP) cho thăm dò bầu cử; nhân tố Bayes
- [Chương 12 — Những điều có thể sai](C12-nhung-dieu-co-the-sai.md) (How Things Go Wrong): khủng hoảng tái lập; gian lận dữ liệu; thực hành nghiên cứu đáng ngờ; truyền thông thổi phồng
- [Chương 13 — Làm thống kê tốt hơn](C13-lam-thong-ke-tot-hon.md) (How We Can Do Statistics Better): cải thiện thực hành khoa học, truyền đạt và cách đọc thống kê
- [Chương 14 — Kết luận](C14-ket-luan.md) (In Conclusion): mười quy tắc đơn giản cho thực hành thống kê hiệu quả
- [Bảng thuật ngữ](PL-bang-thuat-ngu.md) (Glossary): 158 thuật ngữ, định nghĩa cơ bản và kỹ thuật, bảng tra nhanh Anh–Việt

## Gợi ý đọc

- **Đọc trước tiên:** phần Giới thiệu (chu trình PPDAC), rồi Chương 1 và 4: hai chương dễ áp dụng ngay khi đọc tin tức.
- **Muốn hiểu giá trị P và khoảng tin cậy:** đọc liền Chương 7 → 8 → 9 → 10; sau đó Chương 11 để so với cách Bayes.
- **Làm phân tích dữ liệu hoặc mô hình dự báo:** Chương 2, 5, 6.
- **Đánh giá một nghiên cứu hoặc bài báo:** Chương 12 và 13, dùng mười quy tắc ở Chương 14 làm danh sách kiểm tra.
- **Gặp thuật ngữ lạ:** tra [Bảng thuật ngữ](PL-bang-thuat-ngu.md); mỗi mục có liên kết tới chương dùng nó nhiều nhất.
- **Hồi quy và phân tích kinh tế lượng:** đọc kèm bài Back to Basics [Hồi quy](../../IMF/Back%20to%20Basics/2006-03-regressions.md).
