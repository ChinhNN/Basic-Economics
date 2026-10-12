# Cuốn sách nhỏ về định giá — Aswath Damodaran (bản thảo đầu tiên, 2010)

*The Little Book of Valuation: How to Value a Company, Pick a Stock and Profit.* Mỗi chương được tổng hợp thành một file riêng. File nào cũng đi qua đủ từng mục của chương theo đúng thứ tự, chép lại mọi bảng và hình, trình bày từng bước mọi ví dụ định giá (DCF và bội số) với đủ giả định, và **mọi phép tính đã được người tổng hợp tính lại**. Sau đó là các khái niệm cần biết, luận điểm cốt lõi, bảng thuật ngữ Anh–Việt và phần đánh giá: chỗ nào bản thảo tính sai, điều gì đã thay đổi từ năm 2010, cách vận dụng cho nhà đầu tư và nhà phân tích.

**Tác giả:** Aswath Damodaran, giáo sư tài chính Trường Kinh doanh Stern, Đại học New York (NYU), chuyên về định giá doanh nghiệp và tài chính doanh nghiệp. Cuốn sách là bản rút gọn, viết cho nhà đầu tư không chuyên, của các giáo trình định giá dày của ông.

**Nguồn:** bản thảo đầu tiên (First draft: October 14, 2010), bản PDF tiếng Anh 311 trang, có lớp chữ và hình. Bản in là *The Little Book of Valuation* (John Wiley & Sons, 2011).

> **Lưu ý về nguồn:**
> - **Đây là bản thảo, không phải bản in.** Bản in của Wiley có thể khác về tên chương, cách đánh số, ví dụ và câu chữ. Bản thảo còn nhiều dấu vết chưa hoàn thiện, đều được ghi trong khối **Lưu ý** ở đầu từng file:
>   - lỗi đánh số: chương về tài sản vô hình ghi nhầm là "Chapter 12" (repo đánh số lại thành Chương 11); nhiều bảng, hình, minh hoạ mang số của tài liệu khác ("Table 11.13" trong Chương 7, "illustration 14.1" trong Chương 9);
>   - dẫn chiếu tới chương hoặc mục không có trong bản thảo (ví dụ "the dark side", "chapter on technology companies"); Chương 12 có vẻ chép gần nguyên văn từ cuốn *The Dark Side of Valuation* của cùng tác giả nên mọi số chương được dẫn đều lệch (nhận định của người tổng hợp);
>   - câu bị cụt, danh sách hứa "ba" mà chỉ nêu hai.
> - **Bản thảo có lỗi tính toán; bản tổng hợp ghi cả số của sách và số đúng.** Các lỗi đáng kể nhất:
>   - Chương 3 (3M): tỷ lệ tái đầu tư ghi 36,37%, đúng là 31,57%, kéo theo tăng trưởng cơ bản 9,21% thay vì 7,99%; giá trị tài sản hoạt động hiển thị 64.291, đúng là 64.036 (kết quả 86,95 USD/cổ phiếu vẫn đúng).
>   - Chương 5 (Evergreen Solar): giá trị cuối kỳ 1.255 không khớp công thức ghi kèm (đúng là 1.112), làm giá trị mỗi cổ phiếu giảm từ 0,63 USD xuống khoảng 0,26 USD; xác suất thất bại "38%" không khớp dữ liệu của chính ví dụ.
>   - Chương 4: phép tính "hai sai số chuẩn" sai số học và sai khái niệm.
>   - Chương 7, 8, 9, 11: nhiều ô bảng hiển thị sai (chi phí vốn "0,10%", giá trị hiện tại 5.655 thay vì khoảng 4.737, vốn hoá Goldman Sachs không khớp giá × số cổ phiếu, ba lỗi số trong hình định giá Amgen) dù phần lớn kết quả cuối vẫn đúng.
> - **Số liệu thị trường của bản thảo thuộc giai đoạn 2008–2010** (lãi suất phi rủi ro khoảng 3%, phần bù rủi ro vốn cổ phần khoảng 6%, thuế suất doanh nghiệp Mỹ 35–40%; ví dụ định giá dùng dữ liệu ngay giữa khủng hoảng tài chính 2008). Những thay đổi sau đó (lãi suất gần 0 kéo dài rồi tăng lại từ 2022, thuế suất liên bang Mỹ 21% từ 2018, chuẩn mực thuê tài sản 2019, số phận các công ty ví dụ như Evergreen Solar phá sản năm 2011, Sears năm 2018) được nêu ở mức định tính, theo hiểu biết của người tổng hợp, không tra cứu.
> - **Một vài hình là đồ thị không ghi số.** Số liệu đọc từ trục được ghi rõ là ước lượng; ở Chương 10, người tổng hợp đọc số liệu từ đồ thị rồi chạy lại hồi quy và ra kết quả sát với sách.
> - **Sách còn bản quyền.** Bản tổng hợp diễn đạt lại bằng lời mới; câu trích nguyên văn chủ yếu nằm ở mục "Câu nói đáng nhớ".
> - **Trang:** bản thảo đánh số trang trùng với trang PDF.

## Chuỗi lập luận của cả cuốn sách

```text
       CHƯƠNG 1 — GIÁ TRỊ LÀ GÌ
       · giá bạn trả cho một tài sản phải phản ánh dòng tiền nó tạo ra;
         không thể biện minh giá chỉ bằng việc sẽ có người khác mua cao hơn
       · hai cách định giá: NỘI TẠI (từ dòng tiền, tăng trưởng, rủi ro) và
         TƯƠNG ĐỐI (từ giá thị trường của tài sản tương tự)
       · mọi định giá đều có thiên kiến và sai số; đơn giản thường tốt hơn
                                │
                                ▼
       PHẦN 1 — ĐẶT NỀN MÓNG (Chương 2–4)
       · C2: công cụ — giá trị thời gian của tiền, đo rủi ro (beta, phần
         bù rủi ro), số liệu kế toán, thống kê và hồi quy
       · C3: định giá nội tại bằng DCF — bốn đầu vào: dòng tiền hiện tại,
         tăng trưởng kỳ vọng, khi nào tăng trưởng ổn định, rủi ro (suất
         chiết khấu); ví dụ định giá 3M
       · C4: định giá tương đối — bốn bước dùng bội số: định nghĩa nhất
         quán, mô tả phân phối, phân tích biến quyết định bội số, chọn
         công ty so sánh; ví dụ ngành đồ uống
                                │
                                ▼
       PHẦN 2 — ĐỊNH GIÁ THEO VÒNG ĐỜI DOANH NGHIỆP (Chương 5–8)
       · C5 công ty trẻ (Evergreen Solar): ít lịch sử, lỗ, xác suất thất
         bại cao; cách xử lý là ước tính doanh thu và biên lợi nhuận mục
         tiêu
       · C6 công ty tăng trưởng (Under Armour): tăng trưởng phải trả bằng
         tái đầu tư; giữ nhất quán giữa tăng trưởng, rủi ro và tái đầu tư
       · C7 công ty trưởng thành (Hormel Foods): giá trị nằm ở tài sản hiện
         có; định giá thêm kịch bản thay đổi ban điều hành
       · C8 công ty suy thoái, kiệt quệ (Sears, Las Vegas Sands): tính
         riêng xác suất phá sản và giá trị bán tháo
                                │
                                ▼
       PHẦN 3 — TÌNH HUỐNG ĐẶC BIỆT (Chương 9–11)
       · C9 công ty dịch vụ tài chính (Wells Fargo, Goldman Sachs): không
         tách được nợ khỏi hoạt động, nên định giá thẳng vốn chủ sở hữu,
         thường bằng cổ tức
       · C10 công ty chu kỳ và hàng hoá cơ bản (Toyota, Exxon): chuẩn hoá
         lợi nhuận theo cả chu kỳ, gắn giá trị với giá hàng hoá
       · C11 công ty có tài sản vô hình (Amgen, Google): vốn hoá chi phí
         R&D, xử lý quyền chọn cổ phiếu cho nhân viên
                                │
                                ▼
       PHẦN 4 — CHƯƠNG 12: MƯỜI BÀI HỌC VỀ ĐỊNH GIÁ
       · mọi tài sản đều định giá được; giá trị nằm ở các yếu tố cơ bản;
         tăng trưởng chỉ có giá trị khi lợi nhuận trên vốn cao hơn chi phí
         vốn; định giá luôn bất định nhưng vẫn cần làm
```

## Mục lục

- [Lời nói đầu và mục lục](00-loi-noi-dau.md) (Preface, Table of Contents): định giá về cốt lõi là đơn giản; phần lớn giá trị dựa vào một hoặc hai yếu tố then chốt; mục lục đầy đủ của bản thảo

### Mở đầu
- [Chương 1 — Giới thiệu về giá trị](C01-gioi-thieu-ve-gia-tri.md) (Introduction to Value): giá trị nội tại và tương đối; định giá có ích cho mọi trường phái nhà đầu tư; những sự thật về định giá (thiên kiến, sai số, đơn giản hơn chưa chắc kém)

### Phần 1 — Đặt nền móng (Laying the groundwork)
- [Chương 2 — Công cụ của nghề định giá](C02-cong-cu-cua-nghe-dinh-gia.md) (The Tools of the trade): giá trị thời gian của tiền, niên kim, đo lường rủi ro, ba báo cáo kế toán, thống kê và hồi quy
- [Chương 3 — Giá trị nội tại](C03-gia-tri-noi-tai.md) (Intrinsic Value): dòng tiền tự do, chi phí vốn, tăng trưởng, giá trị cuối kỳ; định giá DCF công ty 3M
- [Chương 4 — Định giá tương đối](C04-dinh-gia-tuong-doi.md) (Relative Valuation): bội số chuẩn hoá; bốn chìa khoá dùng bội số; PEG; hồi quy P/E trong ngành đồ uống; đối chiếu định giá tương đối với nội tại

### Phần 2 — Định giá theo vòng đời doanh nghiệp (Valuing across the life cycle)
- [Chương 5 — Định giá công ty trẻ đang tăng trưởng](C05-dinh-gia-cong-ty-tre-tang-truong.md) (Valuing young growth companies and businesses): Evergreen Solar; xác suất sống sót; chiết khấu kém thanh khoản; định giá theo bội số tương lai
- [Chương 6 — Định giá công ty tăng trưởng](C06-dinh-gia-cong-ty-tang-truong.md) (Valuing growth companies): Under Armour; tăng trưởng doanh thu và biên lợi nhuận mục tiêu; tái đầu tư; PEG và hồi quy P/E ngành may mặc
- [Chương 7 — Định giá công ty trưởng thành](C07-dinh-gia-cong-ty-truong-thanh.md) (Valuing Mature Companies): Hormel Foods; giá trị hiện trạng và giá trị khi quản lý tối ưu; giá trị của quyền kiểm soát
- [Chương 8 — Định giá công ty suy thoái và kiệt quệ tài chính](C08-dinh-gia-cong-ty-suy-thoai-va-kiet-que.md) (Valuing Declining and Distressed Companies): Sears, Las Vegas Sands; xác suất phá sản theo hạng tín nhiệm; giá trị bán tháo; vốn chủ sở hữu như quyền chọn

### Phần 3 — Tình huống đặc biệt (Special Situations in Valuation)
- [Chương 9 — Định giá công ty dịch vụ tài chính](C09-dinh-gia-cong-ty-dich-vu-tai-chinh.md) (Valuing Financial Service Companies): mô hình chiết khấu cổ tức; Wells Fargo, Goldman Sachs; P/B theo ROE; vốn theo quy định
- [Chương 10 — Định giá công ty có tính chu kỳ và công ty hàng hoá cơ bản](C10-dinh-gia-cong-ty-chu-ky-va-hang-hoa.md) (Valuing Cyclical and Commodity Companies): lợi nhuận chuẩn hoá; Toyota; Exxon và giá dầu
- [Chương 11 — Định giá công ty có tài sản vô hình](C11-dinh-gia-cong-ty-co-tai-san-vo-hinh.md) (Valuing companies with intangible assets): vốn hoá chi phí R&D (Amgen); thương hiệu (Coca Cola); quyền chọn cổ phiếu cho nhân viên (Google)

### Phần 4 — Tổng kết (Mopping up)
- [Chương 12 — Những bài học về định giá](C12-bai-hoc-ve-dinh-gia.md) (Valuation Lessons): mười mệnh đề về định giá

## Gợi ý đọc

- **Đọc trước tiên:** Chương 1, rồi Chương 3 (DCF) và Chương 4 (bội số); Chương 12 là bản tóm tắt ngắn của cả sách.
- **Thiếu nền tảng tài chính:** đọc Chương 2 trước Chương 3. Đọc kèm *How to Read a Financial Report*, [Chương 2 — Ba báo cáo tài chính](../How%20to%20Read%20a%20Financial%20Report/C02-ba-bao-cao-tai-chinh.md) và [Chương 13 — Dòng tiền từ hoạt động kinh doanh](../How%20to%20Read%20a%20Financial%20Report/C13-dong-tien-tu-hoat-dong-kinh-doanh.md).
- **Theo loại công ty đang phân tích:** chọn chương tương ứng trong Phần 2 và Phần 3; các chương này dùng chung một khung (đặc điểm, vấn đề, giải pháp, cách tận dụng) nên có thể đọc riêng.
- **Giá trị, giá và biên an toàn:** đọc kèm *The Intelligent Investor*, [Chương 20 — Biên an toàn](../The%20Intelligent%20Investor/C20-bien-an-toan.md) và [Chương 11 — Phân tích chứng khoán cho nhà đầu tư không chuyên](../The%20Intelligent%20Investor/C11-phan-tich-chung-khoan-cho-nha-dau-tu-khong-chuyen.md) (công thức định giá cổ phiếu tăng trưởng của Graham).
- **Lãi suất, rủi ro và giá trị hiện tại trong kinh tế học:** đọc kèm *Basic Economics*, [Chương 15 — Các vấn đề đặc biệt về thời gian và rủi ro](../Basic%20Economics/C15-cac-van-de-dac-biet-ve-thoi-gian-va-rui-ro.md).
