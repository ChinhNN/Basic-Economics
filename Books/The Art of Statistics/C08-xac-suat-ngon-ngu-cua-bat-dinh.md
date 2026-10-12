# Chương 8 — Xác suất: ngôn ngữ của bất định và biến thiên (Probability—the Language of Uncertainty and Variability)

**Nguồn:** David Spiegelhalter, *The Art of Statistics: How to Learn from Data*, Basic Books (Hachette), 2019 (bản Mỹ đầu tiên; bản gốc Pelican, Anh, 3/2019), Chương 8 "Probability—the Language of Uncertainty and Variability", trang PDF 144–158 (ebook không có số trang in; chú thích cuối chương và chú thích dấu sao nằm ở phần cuối sách).
**Tác giả:** Sir David Spiegelhalter, nhà thống kê, chủ tịch Trung tâm Winton về Truyền đạt Rủi ro và Bằng chứng (Winton Centre for Risk and Evidence Communication), Phòng Thí nghiệm Thống kê, Đại học Cambridge; nguyên chủ tịch Hội Thống kê Hoàng gia Anh (Royal Statistical Society); được phong tước hiệp sĩ vì đóng góp cho thống kê.
**Vị trí trong lập luận của cả cuốn sách:** Bảy chương đầu cố ý đi xa nhất có thể mà không cần lý thuyết xác suất chính thức: Chương 1 ([C01-ty-le-du-lieu-phan-loai-va-phan-tram.md](C01-ty-le-du-lieu-phan-loai-va-phan-tram.md)) và Chương 2 ([C02-tom-tat-va-truyen-dat-con-so.md](C02-tom-tat-va-truyen-dat-con-so.md)) bàn cách tóm tắt và truyền đạt số liệu; Chương 3 ([C03-tong-the-va-do-luong.md](C03-tong-the-va-do-luong.md)) đưa ra ý tưởng "rút ngẫu nhiên" từ một tổng thể, phân phối chuẩn, và khái niệm tổng thể ẩn dụ (metaphorical population) khi ta đã có toàn bộ dữ liệu; Chương 4–6 ([C04-cai-gi-gay-ra-cai-gi.md](C04-cai-gi-gay-ra-cai-gi.md), [C05-mo-hinh-hoa-quan-he-bang-hoi-quy.md](C05-mo-hinh-hoa-quan-he-bang-hoi-quy.md), [C06-thuat-toan-phan-tich-va-du-bao.md](C06-thuat-toan-phan-tich-va-du-bao.md)) bàn nhân quả, hồi quy và thuật toán; Chương 7 ([C07-uoc-luong-va-khoang.md](C07-uoc-luong-va-khoang.md)) dùng bootstrap (lấy mẫu lặp lại từ chính dữ liệu bằng máy tính) để đo độ bất định của ước lượng. Chương 8 là nơi lý thuyết xác suất chính thức lần đầu bước vào: nó đưa ra các quy tắc xác suất, xác suất có điều kiện, các cách hiểu khác nhau về "xác suất", và lập luận rằng xác suất áp dụng được cả khi dữ liệu không sinh ra từ một cơ chế ngẫu nhiên nào. Chương 9 ([C09-ket-hop-xac-suat-va-thong-ke.md](C09-ket-hop-xac-suat-va-thong-ke.md)) dùng nền móng này để suy ra phân phối của các thống kê, định lý giới hạn trung tâm và khoảng tin cậy; Chương 10 ([C10-tra-loi-cau-hoi-va-tuyen-bo-phat-hien.md](C10-tra-loi-cau-hoi-va-tuyen-bo-phat-hien.md)) dùng nó cho kiểm định giả thuyết (kể cả kiểm định xem phân phối Poisson trong chương này có hợp lý không); Chương 11 ([C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md](C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md)) phát triển cách hiểu xác suất chủ quan mà tác giả ưa chuộng thành suy luận Bayes.
**Ý chính:** Spiegelhalter muốn người đọc hiểu rằng **xác suất là ngôn ngữ toán học chung cho hai thứ: tính ngẫu nhiên "thuần tuý" (đồng xu, xúc xắc, máy sinh số ngẫu nhiên) và biến thiên tự nhiên không tránh được của thế giới (cân nặng sơ sinh, số vụ giết người mỗi ngày, kết quả phẫu thuật); xác suất khó và phản trực giác thật, nhưng nghĩ theo "tần số kỳ vọng" — điều gì sẽ xảy ra với 4 lần tung, với 1.000 phụ nữ — giúp lập luận đúng; và ta có thể, thậm chí nên, hành xử "như thể" dữ liệu được sinh ngẫu nhiên kể cả khi biết rõ là không, vì cách làm này mô tả dữ liệu tốt đến kinh ngạc.** Mở đầu chương là bài toán cờ bạc của Chevalier de Méré ở Pháp thập niên 1650: thắng nếu tung một xúc xắc tối đa 4 lần ra mặt sáu (xác suất thắng khoảng 52%), hay tung hai xúc xắc tối đa 24 lần ra đôi sáu (khoảng 49%); câu hỏi của ông đưa Pascal và Fermat đến những bước đầu của lý thuyết xác suất. Mục "The Rules of Probability Made, Possibly, a Bit Simpler" dùng câu hỏi tung hai đồng xu (60 trong 97 nghị sĩ Anh năm 2012 trả lời sai) để giới thiệu cây tần số kỳ vọng, cây xác suất và bốn quy tắc: xác suất nằm giữa 0 và 1, quy tắc phần bù, quy tắc cộng (HOẶC) cho biến cố xung khắc, quy tắc nhân (VÀ) cho biến cố độc lập; mọi xác suất đều là có điều kiện. Mục "Conditional Probability" dùng ví dụ chụp X-quang tuyến vú chính xác 90% với tỷ lệ mắc 1%: trong 1.000 phụ nữ có 108 người dương tính, nhưng chỉ 9 người thật sự mắc ung thư (8%); nhầm "xác suất dương tính khi có ung thư" với "xác suất có ung thư khi dương tính" là ngụy biện của công tố viên. Mục "What Is 'Probability' Anyway?" điểm năm cách hiểu xác suất (cổ điển, liệt kê, tần suất dài hạn, khuynh hướng, chủ quan), tác giả chọn cách hiểu chủ quan, rồi phân biệt ba tình huống dữ liệu: sinh ra bởi thiết bị ngẫu nhiên, được chọn bởi thiết bị ngẫu nhiên, và không có ngẫu nhiên nào nhưng ta hành xử như thể có. Mục "If We Observe Everything, Where Does Probability Come In?" cho thấy số vụ giết người mỗi ngày ở Anh và xứ Wales (trung bình 1,41) khớp gần như hoàn hảo với phân phối Poisson: dự kiến 12,4 ngày có đúng 5 vụ, thực tế 13 ngày; xác suất một ngày có từ 7 vụ trở lên là 0,07%, tức khoảng bốn năm một lần. Chương kết bằng Quetelet và "vật lý xã hội": từng sự kiện riêng lẻ không đoán được, nhưng tổng thể lại đều đặn đến kinh ngạc.

> **Lưu ý:**
> - **Mâu thuẫn về khoảng thời gian của số liệu giết người (nhận xét của người tổng hợp):** sách viết "ba năm (1.095 ngày) giữa tháng 4/2014 và tháng 3/2016", nhưng từ tháng 4/2014 đến tháng 3/2016 chỉ là hai năm (khoảng 731 ngày). Con số 1.545 vụ trong 1.095 ngày (khoảng 515 vụ/năm) và 1.095 ngày đúng là ba năm, nên khả năng cao giai đoạn thật là tháng 4/2013 – tháng 3/2016. Chú thích hình (Figure 8.5) ghi "2014 to 2016" cũng theo cách viết này. Chương 9 dùng số liệu giết người theo năm của chính hai năm 2014–2015 (497) và 2015–2016 (557), tổng 1.054 — không thể chứa 1.545 vụ, càng cho thấy giai đoạn ba năm phải bắt đầu từ 2013. (Lưu ý thêm: "vụ giết người" (homicide incident) ở Chương 8 khác "số nạn nhân" (homicides) ở Chương 9, vì một vụ có thể có nhiều nạn nhân.)
> - **Lỗi nhãn trên cây xác suất (Figure 8.3):** ở nhánh dưới của lần tung thứ nhất, hình ghi "Head" (ngửa), đúng ra phải là "Tail" (sấp), vì hai kết cục cuối của nhánh này là "Tail and head" và "Two tails". Bản tổng hợp chép lại với nhãn đúng.
> - **Các công thức bị mất trong lớp chữ:** chú thích cuối chương số 1 (lời giải bài toán Chevalier de Méré) bị mất các phân số và lũy thừa. Người tổng hợp khôi phục: xác suất không ra mặt sáu trong một lần tung là 5/6; bốn lần liền không ra sáu là (5/6)⁴ = 625/1.296 = 0,482; xác suất thắng Trò 1 là 1 − 0,482 = 0,518 (sách làm tròn 0,52). Với Trò 2: (35/36)²⁴ = 0,509; xác suất thắng 1 − 0,509 = 0,491 (sách: 0,49). Cả hai đều khớp với số trong sách.
> - **Các phép tính đã tự kiểm tra:** ½ × ½ = ¼; 1 − ¼ = ¾; 9 + 99 = 108; 108/1.000 = 10,8% ("khoảng 11%"); 9/108 = 8,3% ("8%"); 1.545/1.095 = 1,411 vụ/ngày; xác suất Poisson của đúng 5 vụ với trung bình 1,41 là e^(−1,41) × 1,41⁵ / 120 = 0,01134, nhân 1.095 ngày ra 12,4 ngày; xác suất từ 7 vụ trở lên là 0,00065 (0,065%, sách làm tròn 0,07%), nghịch đảo khoảng 1.540 ngày (sách: 1.535, tức khoảng 4,2 năm — khớp nếu dùng trung bình chưa làm tròn 1,411). Mọi con số của sách đều đúng.
> - **Đồ thị không ghi số:** Figure 8.1 (mô phỏng 10.000 ván) và Figure 8.5 (số ngày có 0, 1, 2… vụ giết người) là đồ thị không ghi số trên cột hoặc đường. Các số đọc từ trục trong bản tổng hợp là **ước lượng** của người tổng hợp. Riêng số "dự kiến" của Figure 8.5, người tổng hợp tính lại từ công thức Poisson; số "quan sát" (trừ con số 13 ngày có 5 vụ do sách nêu) chỉ là đọc từ hình, sai số khoảng ±5 ngày. Trục tung của Figure 8.5 có lỗi chính tả "occurences" (đúng là "occurrences").
> - **Danh sách chú thích dấu sao trong file chương bị lệch:** danh sách footnote đi kèm chương trong bộ chữ trích ra thực chất thuộc Chương 10. Bảy footnote đúng của Chương 8 (lỗi tính của Chevalier, đáp án ¼, "luật đảo điều kiện", Philip Dawid, máy sinh số giả ngẫu nhiên, cơ học lượng tử, định nghĩa "vụ giết người") đã được lấy từ danh sách footnote toàn sách và đưa vào đúng chỗ.
> - **Lời văn chưa chặt (nhận xét của người tổng hợp):** sách nói Chevalier de Méré phải tới khoảng 400 ván mới thấy Trò 1 tốt hơn, nhưng chênh lệch thật chỉ là 51,8% so với 49,1%, tức 2,7 điểm phần trăm. Với 400 ván mỗi trò, sai số chuẩn của tỷ lệ thắng là khoảng √(0,25/400) = 2,5 điểm phần trăm, nên ở mốc này chênh lệch vẫn dễ bị may rủi che lấp; trên đồ thị mô phỏng, hai đường chỉ tách hẳn sau khoảng 1.000–2.000 ván. Câu "it becomes clear" vì vậy hơi lạc quan.

## Sơ đồ

### Phần mở đầu chương (trước mục đầu tiên, trang PDF 144–146) — bài toán của Chevalier de Méré và vì sao cần xác suất

```text
       Pháp, thập niên 1650: Chevalier de Méré (tên thật Antoine Gombaud)
       muốn biết trò nào dễ thắng hơn
       · Trò 1: tung một xúc xắc tối đa 4 lần, thắng nếu ra mặt sáu
       · Trò 2: tung hai xúc xắc tối đa 24 lần, thắng nếu ra đôi sáu
                                │
                                ▼
       Ông tính sai: 4 × 1/6 = 2/3 và 24 × 1/36 = 2/3, hai trò như nhau
       (cộng xác suất của các biến cố KHÔNG xung khắc; theo lối đó, tung
       12 lần sẽ có "xác suất" 12/6 = 2, vô lý)
                                │
                                ▼
       Ông chơi thật rất nhiều lần; mô phỏng 10.000 ván trên máy tính cho
       cùng kết luận:
       · 100 ván đầu: Trò 2 trông có vẻ tốt hơn (khoảng 0,52 so với 0,41)
       · sau khoảng 400 ván: rõ là Trò 1 tốt hơn
       · rất dài hạn: Trò 1 thắng khoảng 52%, Trò 2 khoảng 49%
                                │
                                ▼
       Ông hỏi nhóm Salon Mersenne ở Paris → Pascal viết thư cho Fermat
       → những bước đầu tiên của lý thuyết xác suất
                                │
                                ▼
       Vì sao thống kê cần xác suất?
       · dữ liệu "rút ngẫu nhiên" từ tổng thể (Chương 3)
       · kết luận suy diễn luôn kèm bất định
       · bootstrap (Chương 7) dùng mô phỏng: mạnh nhưng vụng về, "sức trâu"
                                │
                                ▼
       Tác giả: xác suất khó và phản trực giác THẬT; sau 40 năm, ông vẫn phải
       ngồi im với giấy bút khi giải một câu hỏi xác suất cấp phổ thông
```

### Mục "The Rules of Probability Made, Possibly, a Bit Simpler" — các quy tắc xác suất, có lẽ đơn giản hơn một chút (trang PDF 146–150)

```text
       2012: hỏi 97 nghị sĩ Anh "tung một đồng xu hai lần, xác suất ra hai
       mặt ngửa là bao nhiêu?" → 60/97 trả lời sai (đáp án: 1/4)
                                │
                                ▼
       Kỹ thuật ưa thích của tác giả: TẦN SỐ KỲ VỌNG
       "nếu làm thí nghiệm nhiều lần, ta dự kiến điều gì xảy ra?"
                                │
                                ▼
       CÂY TẦN SỐ KỲ VỌNG (4 lần làm thí nghiệm)
              4 ──ngửa──▶ 2 ──ngửa──▶ 1   (ngửa, ngửa)
                │             └─sấp───▶ 1   (ngửa, sấp)
                └─sấp───▶ 2 ──ngửa──▶ 1   (sấp, ngửa)
                              └─sấp───▶ 1   (sấp, sấp)
       → 1 trong 4 lần ra hai ngửa → xác suất 1/4
                                │
                                ▼
       CÂY XÁC SUẤT: ghi tỷ lệ 1/2 trên mỗi nhánh rẽ; xác suất của cả một
       nhánh bằng tích các tỷ lệ dọc nhánh: 1/2 × 1/2 = 1/4
                                │
                                ▼
       BỐN QUY TẮC
       1. xác suất nằm trong [0, 1]: 0 là không thể, 1 là chắc chắn
       2. phần bù: P(ít nhất một sấp) = 1 − P(hai ngửa) = 1 − 1/4 = 3/4
       3. cộng (HOẶC), cho biến cố xung khắc: P(ít nhất một ngửa)
          = 1/4 + 1/4 + 1/4 = 3/4
       4. nhân (VÀ), cho biến cố độc lập: P(ngửa VÀ ngửa) = 1/2 × 1/2
                                │
                                ▼
       Áp dụng cho Chevalier: P(thắng Trò 1) = 1 − (5/6)^4 = 0,52;
       P(thắng Trò 2) = 1 − (35/36)^24 = 0,49
                                │
                                ▼
       Mọi xác suất đều CÓ ĐIỀU KIỆN: đồng xu cân, tung đúng cách, không
       đứng cạnh, không có thiên thạch rơi... — luôn có giả định đi kèm
```

### Mục "Conditional Probability—When Our Probabilities Depend on Other Events" — xác suất có điều kiện (trang PDF 150–152)

```text
       Chụp X-quang tuyến vú "chính xác khoảng 90%": phân loại đúng 90% người
       có ung thư và 90% người không có; 1% người được sàng lọc có ung thư
                                │
                                ▼
       CÂY TẦN SỐ KỲ VỌNG cho 1.000 phụ nữ
       1.000 ─ung thư (1%)────▶ 10 ─dương tính (90%)─▶ 9
                                    └─âm tính─────────▶ 1
             └─không ung thư──▶ 990 ─dương tính (10%)─▶ 99
                                    └─âm tính─────────▶ 891
                                │
                                ▼
       · tổng dương tính: 9 + 99 = 108 → P(dương tính) = 108/1.000 ≈ 11%
       · trong 108 người dương tính chỉ 9 người có ung thư
         → P(ung thư | dương tính) = 9/108 ≈ 8%
                                │
                                ▼
       Kết quả phản trực giác: dù "chính xác 90%", phần lớn người dương tính
       KHÔNG có ung thư
                                │
                                ▼
       NGỤY BIỆN CỦA CÔNG TỐ VIÊN (luật đảo điều kiện)
       · nhầm P(dương tính | ung thư) với P(ung thư | dương tính)
       · tòa án: "nếu vô tội, chỉ 1 phần tỷ khả năng khớp ADN" bị hiểu sai
         thành "với bằng chứng ADN, chỉ 1 phần tỷ khả năng vô tội"
       · cùng lỗi với: "là Giáo hoàng thì là người Công giáo" → "là người
         Công giáo thì là Giáo hoàng"
```

### Mục "What Is 'Probability' Anyway?" — rốt cuộc "xác suất" là gì? (trang PDF 152–154)

```text
       Không có "máy đo xác suất": xác suất là đại lượng ta gán số được
       nhưng không đo trực tiếp được; chuyên gia đồng ý về toán, bất đồng
       về ý nghĩa
                                │
                                ▼
       NĂM CÁCH HIỂU
       1. cổ điển: số kết cục thuận lợi / tổng số kết cục đồng khả năng
          (xúc xắc ra mặt một: 1/6) — vòng vo vì phải định nghĩa "đồng khả năng"
       2. liệt kê: rút ngẫu nhiên từ tập vật thể (3 tất trắng, 4 tất đen:
          P(trắng) = 3/7) — mở rộng của cách cổ điển
       3. tần suất dài hạn: tỷ lệ xảy ra trong chuỗi vô hạn thí nghiệm giống
          hệt (như mô phỏng trò Chevalier) — không dùng được cho sự kiện
          duy nhất (đua ngựa, thời tiết ngày mai)
       4. khuynh hướng / "cơ hội": xu hướng khách quan của tình huống —
          hấp dẫn nhưng người thường không có cách ước tính
       5. chủ quan / cá nhân: phán đoán của một người cho một tình huống,
          theo tỷ lệ cược thấy hợp lý (đặt 60 xu để được 1 bảng → 0,6)
                                │
                                ▼
       Tác giả chọn cách 5: xác suất được KIẾN TẠO từ hiểu biết hiện có,
       "không thực sự tồn tại" (trừ có thể ở cấp hạ nguyên tử) → nền của
       trường phái Bayes (Chương 11)
                                │
                                ▼
       Nhưng không cần đồng ý: cứ hành xử NHƯ THỂ đồng xu, máy sinh số
       giả ngẫu nhiên là ngẫu nhiên khách quan
                                │
                                ▼
       BA TÌNH HUỐNG DỮ LIỆU
       1. dữ liệu được SINH RA bởi thiết bị ngẫu nhiên (xúc xắc, phân bổ
          ngẫu nhiên bệnh nhân vào nhóm điều trị)
       2. dữ liệu có sẵn được CHỌN bởi thiết bị ngẫu nhiên (điều tra chọn mẫu)
       3. KHÔNG có ngẫu nhiên nào, nhưng hành xử như thể có (cân nặng
          em bé của người bạn, tỷ lệ sống sau phẫu thuật tim ở các bệnh
          viện, toàn bộ điểm thi) — phần lớn ứng dụng thống kê ở đây
                                │
                                ▼
       Tình huống 1 và 2: gán số cho mỗi kết cục (sấp = 0, ngửa = 1) ta có
       BIẾN NGẪU NHIÊN với một PHÂN PHỐI XÁC SUẤT; khi quan sát xong, mọi
       khả năng "sụp" về một giá trị thực tế
```

### Mục "If We Observe Everything, Where Does Probability Come In?" — nếu quan sát được mọi thứ, xác suất xuất hiện ở đâu? (trang PDF 154–157)

```text
       Câu hỏi: bao lâu thì Anh và xứ Wales có một ngày với từ 7 vụ giết
       người trở lên?
                                │
                                ▼
       Dữ liệu: 1.545 vụ trong 1.095 ngày → trung bình 1,41 vụ/ngày;
       không có ngày nào ≥ 7 vụ — nhưng không có nghĩa là không thể
                                │
                                ▼
       Số vụ mỗi ngày là sự thật, không có lấy mẫu; vẫn HÀNH XỬ NHƯ THỂ do
       một quá trình ngẫu nhiên sinh ra: rất nhiều người, mỗi người một xác
       suất rất nhỏ → PHÂN PHỐI POISSON (Poisson, Pháp, thập niên 1830)
       · chỉ cần một tham số: trung bình (ở đây 1,41)
                                │
                                ▼
       Kiểm tra độ khớp:
       · P(đúng 5 vụ) = 0,01134 → dự kiến 1.095 × 0,01134 = 12,4 ngày;
         thực tế: 13 ngày
       · cả phân phối 0, 1, 2, ..., 6, ≥7 vụ khớp rất sát (kiểm định
         chính thức ở Chương 10)
                                │
                                ▼
       Trả lời: P(≥ 7 vụ trong một ngày) = 0,07% → trung bình 1.535 ngày một
       lần, khoảng 4 năm một lần: hiếm, nhưng không phải không thể
                                │
                                ▼
       Cách hiểu: ta quan sát MỘT trong nhiều "thế giới có thể đã xảy ra"
                                │
                                ▼
       Quetelet (Bỉ, giữa thế kỷ 19): "con người trung bình", "vật lý xã
       hội" — từng đời người không đoán được, nhưng tỷ lệ tự tử quốc gia
       gần như không đổi qua các năm
                                │
                                ▼
       Xác suất là nền toán học cho cả ngẫu nhiên "thuần tuý" lẫn BIẾN
       THIÊN TỰ NHIÊN không tránh được
```

### Mục "Summary" — tóm tắt (trang PDF 158)

```text
       · lý thuyết xác suất cho ngôn ngữ và toán học chính thức để xử lý
         các hiện tượng may rủi
       · hệ quả của xác suất không trực giác, nhưng nghĩ theo tần số kỳ
         vọng giúp hiểu tốt hơn
       · ý tưởng xác suất hữu ích cả khi không có cơ chế ngẫu nhiên tường minh
       · nhiều hiện tượng xã hội đều đặn đáng kinh ngạc ở tổng thể, dù từng
         sự kiện hoàn toàn không đoán được
```

## Ba câu hỏi chương này trả lời

1. **Làm sao lập luận đúng về xác suất khi trực giác dễ sai?** Bằng cách nghĩ theo tần số kỳ vọng: hình dung thí nghiệm lặp lại nhiều lần (4 lần tung hai đồng xu, 1.000 phụ nữ đi sàng lọc) rồi đếm số trường hợp dự kiến ở mỗi nhánh. Từ cây tần số kỳ vọng suy ra cây xác suất và bốn quy tắc: xác suất nằm giữa 0 và 1; quy tắc phần bù; quy tắc cộng cho biến cố xung khắc; quy tắc nhân cho biến cố độc lập. Với các quy tắc này, xác suất thắng hai trò của Chevalier de Méré là 52% và 49%, và xác suất ra hai mặt ngửa là ¼.
2. **Vì sao một xét nghiệm "chính xác 90%" mà phần lớn người dương tính lại không mắc bệnh?** Vì bệnh hiếm: với tỷ lệ mắc 1%, trong 1.000 phụ nữ chỉ có 10 người mắc (9 người dương tính), nhưng 10% của 990 người không mắc, tức 99 người, cũng dương tính. Xác suất mắc bệnh khi dương tính chỉ là 9/108, khoảng 8%. Nhầm xác suất của bằng chứng khi biết giả thuyết với xác suất của giả thuyết khi biết bằng chứng là ngụy biện của công tố viên.
3. **Xác suất nghĩa là gì, và vì sao dùng được cả khi dữ liệu không do may rủi sinh ra?** Có năm cách hiểu (cổ điển, liệt kê, tần suất dài hạn, khuynh hướng, chủ quan); tác giả chọn cách hiểu chủ quan. Dù hiểu theo cách nào, ta có thể hành xử như thể dữ liệu được sinh ngẫu nhiên từ một tổng thể ẩn dụ gồm các "thế giới có thể đã xảy ra"; cách làm này mô tả tốt đến kinh ngạc, như số vụ giết người mỗi ngày ở Anh và xứ Wales khớp phân phối Poisson với trung bình 1,41, và cho phép trả lời những câu hỏi mà dữ liệu thô không trả lời được (một ngày có từ 7 vụ trở lên xảy ra khoảng bốn năm một lần).

## Khái niệm cần biết

- **Xác suất (probability):** một con số từ 0 đến 1 diễn đạt mức độ có thể xảy ra của một biến cố; 0 là không thể, 1 là chắc chắn. Ví dụ: xác suất ra hai mặt ngửa khi tung hai đồng xu là ¼. Quan trọng vì chương này coi xác suất là "ngôn ngữ của bất định" mà mọi suy luận thống kê sau này dùng tới.
- **Tần số kỳ vọng (expected frequency):** số lần một kết cục được dự kiến xảy ra nếu ta lặp lại tình huống một số lần cho trước. Ví dụ: trong 1.000 phụ nữ đi sàng lọc, dự kiến 10 người mắc ung thư, 108 người có kết quả dương tính. Quan trọng vì các thí nghiệm tâm lý cho thấy cách trình bày này giúp người ta lập luận về xác suất đúng hơn hẳn.
- **Cây tần số kỳ vọng (expected frequency tree) và cây xác suất (probability tree):** sơ đồ rẽ nhánh; cây thứ nhất ghi số trường hợp ở mỗi nút, cây thứ hai ghi tỷ lệ trên mỗi nhánh rẽ. Xác suất của cả một nhánh bằng tích các tỷ lệ dọc nhánh. Ví dụ: ½ × ½ = ¼ cho "ngửa rồi ngửa". Quan trọng vì đây là công cụ dạy xác suất hiệu quả nhất mà tác giả nêu.
- **Quy tắc phần bù (complement rule):** xác suất một biến cố xảy ra bằng 1 trừ xác suất nó không xảy ra. Ví dụ: P(ít nhất một mặt sấp) = 1 − ¼ = ¾; P(thắng Trò 1) = 1 − (5/6)⁴ = 0,52. Quan trọng vì nhiều bài toán "ít nhất một lần" dễ giải hơn khi tính xác suất của trường hợp ngược lại.
- **Biến cố xung khắc (mutually exclusive events) và quy tắc cộng (addition rule, quy tắc HOẶC):** hai biến cố xung khắc khi không thể cùng xảy ra; khi đó xác suất "A hoặc B" bằng tổng hai xác suất. Ví dụ: P(ít nhất một ngửa) = ¼ + ¼ + ¼ = ¾ (ngửa-ngửa, ngửa-sấp, sấp-ngửa). Quan trọng vì lỗi của Chevalier de Méré chính là cộng xác suất của những biến cố không xung khắc.
- **Biến cố độc lập (independent events) và quy tắc nhân (multiplication rule, quy tắc VÀ):** hai biến cố độc lập khi biến cố này xảy ra không làm thay đổi xác suất của biến cố kia; khi đó xác suất cả hai cùng xảy ra bằng tích hai xác suất. Ví dụ: bốn lần tung liền không ra mặt sáu có xác suất (5/6)⁴ = 0,48.
- **Xác suất có điều kiện (conditional probability):** xác suất của một biến cố khi biết một biến cố khác đã xảy ra. Ví dụ: P(dương tính | có ung thư) = 90%, nhưng P(có ung thư | dương tính) = 9/108 ≈ 8%. Quan trọng vì tác giả nhấn mạnh mọi xác suất đều là có điều kiện — luôn có giả định đi kèm.
- **Biến cố phụ thuộc (dependent events):** biến cố mà xác suất của nó thay đổi tuỳ biến cố khác; ví dụ kết quả chụp X-quang phụ thuộc vào việc người đó có ung thư hay không.
- **Ngụy biện của công tố viên (prosecutor's fallacy), còn gọi là luật đảo điều kiện (law of the transposed conditional):** nhầm "xác suất của bằng chứng nếu bị cáo vô tội" với "xác suất bị cáo vô tội khi có bằng chứng". Ví dụ: "nếu vô tội, chỉ có 1 phần tỷ khả năng khớp ADN" không có nghĩa là "chỉ có 1 phần tỷ khả năng bị cáo vô tội". Quan trọng vì lỗi này phổ biến ở tòa án và trong đọc kết quả xét nghiệm.
- **Xác suất cổ điển (classical probability):** tỷ số giữa số kết cục thuận lợi và tổng số kết cục, khi mọi kết cục đồng khả năng. Ví dụ: xúc xắc cân ra mặt một với xác suất 1/6. Hạn chế: định nghĩa vòng vo, vì phải định nghĩa trước "đồng khả năng".
- **Xác suất liệt kê (enumerative probability):** xác suất có được bằng cách đếm các khả năng khi rút ngẫu nhiên từ một tập vật thể cụ thể. Ví dụ: ngăn kéo có 3 tất trắng và 4 tất đen, xác suất rút được tất trắng là 3/7 ≈ 0,43. Quan trọng vì đây là ý tưởng "rút ngẫu nhiên một điểm dữ liệu từ tổng thể" dùng xuyên suốt cuốn sách.
- **Xác suất theo tần suất dài hạn (long-run frequency probability):** tỷ lệ xảy ra của biến cố trong một chuỗi vô hạn thí nghiệm giống hệt nhau. Ví dụ: tỷ lệ thắng Trò 1 trong mô phỏng tiến dần về 52%. Hạn chế: hầu như không tình huống thực tế nào lặp lại vô hạn được (một cuộc đua ngựa, thời tiết ngày mai).
- **Khuynh hướng hay "cơ hội" (propensity, chance):** ý tưởng rằng tình huống có một xu hướng khách quan tạo ra biến cố. Hấp dẫn bề ngoài nhưng người thường không có cơ sở để ước tính "cơ hội thật" mang tính siêu hình này.
- **Xác suất chủ quan hay cá nhân (subjective / personal probability):** phán đoán của một người cụ thể về một tình huống cụ thể dựa trên hiểu biết hiện có, diễn giải qua tỷ lệ cược mà người đó thấy hợp lý (với tiền cược nhỏ). Ví dụ: sẵn sàng đặt 60 xu (không hoàn lại) để được 1 bảng Anh nếu tung hứng được ba quả bóng trong năm phút, thì xác suất của người đó cho biến cố này là 0,6. Quan trọng vì tác giả chọn cách hiểu này và nó là nền của suy luận Bayes.
- **Máy sinh số giả ngẫu nhiên (pseudo-random-number generator):** chương trình tạo dãy số bằng phép tính hoàn toàn xác định và đoán trước được, nhưng phức tạp đến mức không phân biệt được với dãy ngẫu nhiên thật. Quan trọng vì nó là ví dụ cực đoan nhất của việc hành xử "như thể" một thứ là ngẫu nhiên dù biết là không.
- **Biến ngẫu nhiên (random variable) và phân phối xác suất (probability distribution):** khi gán một con số cho mỗi kết cục có thể (sấp là 0, ngửa là 1), kèm xác suất của từng kết cục, ta có một biến ngẫu nhiên với một phân phối xác suất. Ví dụ: một lần tung đồng xu cân là biến ngẫu nhiên nhận 0 hoặc 1, mỗi giá trị với xác suất ½. Quan trọng vì đây là bước nối giữa xác suất và dữ liệu, được dùng tiếp ở Chương 9.
- **Tổng thể ẩn dụ (metaphorical population):** tập hợp tưởng tượng gồm mọi kết cục có thể đã xảy ra nhưng phần lớn không xảy ra; dữ liệu quan sát được coi như một lần rút từ tổng thể đó. Ví dụ: số vụ giết người năm nay là một trong nhiều "lịch sử có thể" — những người khác lẽ ra có thể bị giết nhưng đã không. Quan trọng vì nó cho phép dùng xác suất cả khi ta đã có toàn bộ dữ liệu.
- **Phân phối Poisson (Poisson distribution):** phân phối cho số lần một biến cố xảy ra khi có rất nhiều cơ hội, mỗi cơ hội có xác suất rất nhỏ. Chỉ có một tham số là trung bình μ; xác suất có đúng x biến cố là e^(−μ) × μ^x / x!. Ví dụ: với μ = 1,41 vụ giết người mỗi ngày, xác suất một ngày có đúng 5 vụ là 0,01134. Quan trọng vì nó mô tả gần như hoàn hảo số vụ giết người mỗi ngày, và được dùng lại ở Chương 9 và 10.
- **Biến thiên tự nhiên (natural variability):** sự khó đoán không tránh được của thế giới, mà giả định "may rủi" gói gọn lại. Ví dụ: cân nặng sơ sinh, tỷ lệ sống sau phẫu thuật, số vụ giết người. Quan trọng vì chương kết luận rằng xác suất là nền toán học phù hợp cho cả loại biến thiên này, không riêng ngẫu nhiên "thuần tuý".

## Nội dung chi tiết

### 1. Bài toán của Chevalier de Méré và vì sao thống kê cần xác suất (phần mở đầu chương, trang PDF 144–146)

Ở Pháp thập niên 1650, nhân vật tự xưng là Chevalier de Méré (tên thật Antoine Gombaud) có một "vấn đề cờ bạc". Vấn đề không phải ông chơi quá nhiều (dù đúng là ông chơi nhiều), mà là ông muốn biết trong hai trò sau, trò nào cho ông cơ hội thắng cao hơn:

- **Trò 1:** tung một xúc xắc cân tối đa bốn lần, thắng nếu ra một mặt sáu.
- **Trò 2:** tung hai xúc xắc cân tối đa hai mươi bốn lần, thắng nếu ra một đôi sáu.

Theo đúng nguyên tắc thống kê thực nghiệm, ông quyết định chơi cả hai trò rất nhiều lần và đếm số lần thắng. Việc này tốn rất nhiều thời gian và công sức. Spiegelhalter hình dung một "vũ trụ song song" có máy tính mà chưa có lý thuyết xác suất: ở đó, Chevalier chỉ cần mô phỏng hàng nghìn ván.

**Hình: Mô phỏng trên máy tính 10.000 ván mỗi trò (Figure 8.1 trong sách).** Hình gồm hai đồ thị đường, trục tung là tỷ lệ số ván thắng, trục hoành là số ván đã chơi; đường xám là Trò 1 (một xúc xắc), đường đen là Trò 2 (hai xúc xắc), có một đường đứt nét nằm ngang ở mức 0,5. Đồ thị không ghi số; các giá trị dưới đây là ước lượng của người tổng hợp đọc từ trục.

| Giai đoạn | Trò 1 (một xúc xắc) | Trò 2 (hai xúc xắc) | Nhận xét |
|---|---|---|---|
| 100 ván đầu (đồ thị trên, trục tung 0–1) | dao động mạnh, lên tới khoảng 0,62 ở khoảng ván 13, rồi giảm và ở quanh 0,40–0,43 từ khoảng ván 50; khoảng 0,41 ở ván 100 | dao động 0,35–0,50 trong 40 ván đầu, sau đó vượt lên và ở quanh 0,50–0,55; khoảng 0,52 ở ván 100 | Trò 2 trông có vẻ tốt hơn |
| 10.000 ván (đồ thị dưới, trục tung 0,40–0,60) | sau vài trăm ván đầu nằm trên đường 0,5, giảm dần từ khoảng 0,52–0,53 về khoảng 0,515 ở ván 10.000 | sau vài trăm ván đầu nằm quanh hoặc dưới 0,5, giảm dần về khoảng 0,49 ở ván 10.000 | Trò 1 tốt hơn một chút |

Theo lời văn, tuy Trò 2 trông tốt hơn một thời gian, sau khoảng 400 ván mỗi trò thì Trò 1 tỏ ra tốt hơn, và về rất dài hạn Chevalier có thể kỳ vọng thắng khoảng 52% số ván Trò 1 và chỉ khoảng 49% số ván Trò 2.

Điều đáng nể là Chevalier đã chơi nhiều đến mức tự đi tới cùng kết luận: Trò 1 nhỉnh hơn một chút. Kết luận này trái với phép tính (sai) của ông. Theo chú thích của tác giả, ông nghĩ rằng bốn lần tung, mỗi lần có 1/6 cơ hội, cho cơ hội thắng 4 × 1/6 = 2/3; tương tự, 24 lần tung, mỗi lần 1/36 cơ hội, cho 24/36 = 2/3 — tức hai trò như nhau. Tác giả lưu ý đây vẫn là lỗi phổ biến của sinh viên; để thấy nó không thể đúng, chỉ cần hỏi: nếu tung 12 lần trong Trò 1 thì "cơ hội thắng" là 12 × 1/6 = 2 sao? Bối rối, ông tìm đến Salon Mersenne, một nhóm trí thức thời thượng ở Paris. May thay, triết gia Blaise Pascal cũng là thành viên; Pascal viết thư cho bạn mình là Pierre de Fermat (người của "Định lý cuối cùng" nổi tiếng) về các bài toán của Chevalier. Cùng nhau, hai ông đặt những bước đầu tiên của lý thuyết xác suất.

Con người đã đánh cược vào cách những mẩu xương hay con xúc xắc rơi xuống trong hàng nghìn năm, nhưng lý thuyết xác suất chính thức là ý tưởng khá mới. Sau công trình của Pascal và Fermat thập niên 1650, các nền tảng toán học được hoàn thiện trong khoảng năm mươi năm tiếp theo, và ngày nay xác suất được dùng trong vật lý, bảo hiểm, hưu trí, giao dịch tài chính, dự báo và tất nhiên là cờ bạc.

Vậy tại sao làm thống kê lại cần lý thuyết xác suất? Tác giả nhắc lại những gì đã gặp:

- Ý tưởng các điểm dữ liệu được "rút ngẫu nhiên" từ một phân phối tổng thể — câu chuyện người bạn sinh con nhẹ cân ở Chương 3 là lần đầu cuốn sách chạm tới xác suất. Ta phải giả định mọi người trong tổng thể đều có khả năng như nhau được chọn vào mẫu, như phép so sánh của Gallup: khuấy nồi súp thật đều trước khi nếm.
- Khi muốn suy luận thống kê về những khía cạnh chưa biết của thế giới, kể cả dự đoán hay dự báo, kết luận luôn kèm một mức bất định.
- Ở Chương 7, bootstrap cho biết thống kê tóm tắt sẽ biến thiên bao nhiêu nếu lặp lại quá trình lấy mẫu nhiều lần, và dùng biến thiên đó để diễn đạt độ bất định về đặc điểm thật nhưng chưa biết của tổng thể. Cách này cũng chỉ cần ý tưởng "chọn ngẫu nhiên", điều mà trẻ nhỏ cũng hiểu là một cách chọn công bằng.

Theo truyền thống, một khóa thống kê bắt đầu bằng xác suất — Spiegelhalter cho biết ông vẫn luôn dạy như vậy ở Cambridge — nhưng phần nhập môn nặng toán này có thể cản trở việc nắm những ý tưởng quan trọng không cần tới lý thuyết xác suất. Cuốn sách thuộc một "làn sóng mới" trong dạy thống kê, trong đó lý thuyết xác suất chính thức làm nền cho suy luận thống kê được đưa vào muộn hơn nhiều. (Chú thích cuối chương dẫn hai nguồn về phương pháp dạy dựa trên mô phỏng: bài của M. Pfannkuch và cộng sự, "Bootstrapping Students' Understanding of Statistical Inference", TLRI, 2013; và bài của K. Lock Morgan và cộng sự về bộ công cụ trực tuyến STATKEY cho khoảng bootstrap và kiểm định ngẫu nhiên hoá, ICOTS 9, 2014.) Mô phỏng trên máy tính là công cụ rất mạnh để khám phá các sự kiện tương lai có thể xảy ra và để bootstrap dữ liệu quá khứ, nhưng là cách phân tích thống kê khá vụng về và "dùng sức trâu". Vì vậy, dù đã đi được một quãng xa mà không cần lý thuyết xác suất chính thức, đã đến lúc đối diện với vai trò sống còn của nó trong việc cung cấp "ngôn ngữ của bất định".

Tại sao lại ngại dùng một lý thuyết xuất sắc đã phát triển suốt 350 năm? Tác giả thường được hỏi vì sao người ta thấy xác suất khó và phản trực giác, và câu trả lời của ông, sau bốn mươi năm nghiên cứu và giảng dạy, là: vì xác suất *thật sự* khó và phản trực giác. Ông thông cảm với bất kỳ ai thấy xác suất rắc rối; chính ông, sau nhiều thập kỷ làm thống kê, khi được hỏi một câu xác suất cấp phổ thông vẫn phải đi ra chỗ khác, ngồi im với giấy bút, thử vài cách, rồi mới công bố điều ông hy vọng là đáp án đúng.

### 2. Các quy tắc xác suất, có lẽ đơn giản hơn một chút (The Rules of Probability Made, Possibly, a Bit Simpler, trang PDF 146–150)

Năm 2012, 97 nghị sĩ ở London được hỏi: "Nếu tung một đồng xu hai lần, xác suất ra hai mặt ngửa là bao nhiêu?" Đa số, 60 trên 97 người (62%), không trả lời đúng. (Đáp án, theo chú thích của tác giả: ¼, tức 25%, tức 0,25.) Các nghị sĩ có thể làm tốt hơn thế nào? Lẽ ra họ nên biết các quy tắc xác suất, nhưng phần lớn mọi người không biết. Một lối khác là dùng một ý tưởng trực giác hơn, mà nhiều thí nghiệm tâm lý học đã chứng minh giúp người ta lập luận về xác suất tốt hơn: **tần số kỳ vọng**.

Khi gặp bài toán hai đồng xu, hãy tự hỏi: "Nếu làm thí nghiệm này một số lần, tôi dự kiến điều gì xảy ra?" Giả sử tung đồng xu thứ nhất rồi đồng xu thứ hai, tổng cộng bốn lần. Tác giả đoán rằng ngay cả một chính khách, nghĩ một chút, cũng sẽ đi tới kết quả sau.

**Hình: Cây tần số kỳ vọng cho hai lần tung đồng xu, lặp lại bốn lần (Figure 8.2 trong sách)**

```text
   Lần tung thứ nhất        Lần tung thứ hai
                         ┌── ngửa ──▶ 1
          ┌── ngửa ──▶ 2 ┤
          │              └── sấp ───▶ 1
     4 ───┤
          │              ┌── ngửa ──▶ 1
          └── sấp ───▶ 2 ┤
                         └── sấp ───▶ 1
```

Trong bốn lần tung đầu, dự kiến hai lần ra ngửa; trong mỗi nhóm hai lần đó, lần tung thứ hai dự kiến ra một ngửa và một sấp. Vậy dự kiến 1 trong 4 lần ra hai mặt ngửa, nên xác suất ra hai mặt ngửa ở một lần thử cụ thể là 1 trên 4, tức ¼ — may thay, đó là đáp án đúng.

Cây tần số kỳ vọng có thể chuyển thành **cây xác suất** bằng cách ghi trên mỗi nhánh rẽ tỷ lệ số lần nhánh đó được đi.

**Hình: Cây xác suất cho việc tung hai đồng xu (Figure 8.3 trong sách; nhãn nhánh dưới của lần tung thứ nhất đã sửa thành "sấp")**

| Lần tung thứ nhất | Lần tung thứ hai | Kết cục cuối | Xác suất của cả nhánh |
|---|---|---|---|
| ngửa (½) | ngửa (½) | hai mặt ngửa | ½ × ½ = ¼ |
| ngửa (½) | sấp (½) | ngửa rồi sấp | ¼ |
| sấp (½) | ngửa (½) | sấp rồi ngửa | ¼ |
| sấp (½) | sấp (½) | hai mặt sấp | ¼ |

Xác suất của cả một nhánh (chẳng hạn ngửa rồi ngửa) bằng tích các tỷ lệ trên những nhánh rẽ dọc theo nó: ½ × ½ = ¼. Cây xác suất là cách dạy xác suất phổ biến và cực kỳ hiệu quả ở trường phổ thông. Chỉ với ví dụ hai đồng xu, ta đã thấy được mọi quy tắc xác suất:

1. **Xác suất của một biến cố là một số từ 0 đến 1:** 0 cho biến cố không thể (ví dụ không ra mặt ngửa cũng không ra mặt sấp), 1 cho biến cố chắc chắn (ra một trong bốn tổ hợp có thể).
2. **Quy tắc phần bù:** xác suất một biến cố xảy ra bằng một trừ xác suất nó không xảy ra. Ví dụ: xác suất "ít nhất một mặt sấp" bằng một trừ xác suất "hai mặt ngửa": 1 − ¼ = ¾.
3. **Quy tắc cộng (quy tắc HOẶC):** cộng xác suất của các biến cố xung khắc (không thể cùng xảy ra) để được xác suất tổng. Ví dụ: xác suất "ít nhất một mặt ngửa" là ¾, vì biến cố này gồm "hai ngửa" HOẶC "ngửa rồi sấp" HOẶC "sấp rồi ngửa", mỗi trường hợp có xác suất ¼.
4. **Quy tắc nhân (quy tắc VÀ):** nhân các xác suất để được xác suất của một chuỗi biến cố độc lập (biến cố này không ảnh hưởng biến cố kia) cùng xảy ra. Ví dụ: xác suất ngửa VÀ ngửa là ½ × ½ = ¼.

Các quy tắc cơ bản này đủ để giải bài toán của Chevalier de Méré: ông có 52% cơ hội thắng Trò 1 và 49% cơ hội thắng Trò 2. Lời giải (chú thích cuối chương, người tổng hợp khôi phục các phân số bị mất và tính lại):

- **Trò 1.** Có nhiều cách thắng nhưng chỉ một cách thua: bốn lần liền không ra mặt sáu. Vì vậy tính xác suất thua dễ hơn — một mẹo phổ biến. Xác suất một lần tung không ra sáu là 1 − 1/6 = 5/6 (quy tắc phần bù). Xác suất bốn lần liền không ra sáu là (5/6) × (5/6) × (5/6) × (5/6) = 625/1.296 = 0,482 (quy tắc nhân, vì các lần tung độc lập). Xác suất thắng là 1 − 0,482 = 0,518, làm tròn 0,52 (quy tắc phần bù lần nữa).
- **Trò 2.** Xác suất một lần tung hai xúc xắc không ra đôi sáu là 1 − 1/36 = 35/36. Xác suất 24 lần liền không ra đôi sáu là (35/36)²⁴ = 0,509. Xác suất thắng là 1 − 0,509 = 0,491, làm tròn 0,49.
- Vậy Trò 1 nhỉnh hơn một chút. Các quy tắc này cũng chỉ ra lỗi của Chevalier: ông đã **cộng** xác suất của những biến cố **không xung khắc** (ra sáu ở lần tung thứ nhất và ra sáu ở lần tung thứ hai hoàn toàn có thể cùng xảy ra). Theo lối nghĩ đó, cơ hội ra một mặt sáu khi tung 12 lần sẽ là 12/6 = 2, điều không hợp lý.

Ngay cả trong ví dụ tung đồng xu đơn giản này, ta vẫn đang đưa ra những giả định mạnh: đồng xu cân và đều, được tung đúng cách để kết quả không đoán trước được, không rơi đứng cạnh, không có thiên thạch lao xuống sau lần tung đầu, và vân vân. Đó là những cân nhắc nghiêm túc (có lẽ trừ thiên thạch), và chúng nhấn mạnh rằng **mọi xác suất ta dùng đều là có điều kiện**: không có cái gọi là xác suất vô điều kiện của một biến cố; luôn có các giả định và yếu tố khác có thể ảnh hưởng tới xác suất. Và như phần tiếp theo cho thấy, ta cần cẩn thận về việc mình đang lấy điều kiện theo cái gì.

### 3. Xác suất có điều kiện: khi xác suất phụ thuộc vào biến cố khác (Conditional Probability—When Our Probabilities Depend on Other Events, trang PDF 150–152)

Câu hỏi mở đầu mục: khi sàng lọc ung thư vú, chụp X-quang tuyến vú (mammography) chính xác khoảng 90%, theo nghĩa 90% phụ nữ có ung thư và 90% phụ nữ không có ung thư được phân loại đúng. Giả sử 1% phụ nữ được sàng lọc thực sự có ung thư. Xác suất một phụ nữ chọn ngẫu nhiên có kết quả dương tính là bao nhiêu, và nếu dương tính thì khả năng bà ấy thật sự mắc ung thư là bao nhiêu?

Trong ví dụ hai đồng xu, các biến cố là độc lập: xác suất ra ngửa ở lần thứ hai không phụ thuộc lần thứ nhất ra gì. Ở trường, ta thường học về **biến cố phụ thuộc** qua những câu hỏi khá nhàm chán kiểu lần lượt rút những chiếc tất khác màu trong ngăn kéo; ví dụ trên gần đời sống hơn. Đây là bài toán kinh điển trong các bài kiểm tra trí tuệ và không dễ, nhưng với ý tưởng tần số kỳ vọng nó trở nên đơn giản đáng ngạc nhiên. Ý then chốt là nghĩ xem điều gì dự kiến xảy ra với một nhóm lớn phụ nữ, chẳng hạn 1.000 người.

**Hình: Cây tần số kỳ vọng cho 1.000 phụ nữ đi sàng lọc ung thư vú (Figure 8.4 trong sách)** — giả định 1% có ung thư, chụp X-quang phân loại đúng 90% người có ung thư và 90% người không có.

```text
   Tình trạng thật                    Kết quả chụp X-quang
                                     ┌── dương tính ──▶ 9
          ┌── ung thư ─────────▶ 10 ─┤
          │                          └── âm tính ─────▶ 1
   1.000 ─┤
          │                          ┌── dương tính ──▶ 99
          └── không ung thư ──▶ 990 ─┤
                                     └── âm tính ─────▶ 891
```

Từng bước:

1. Trong 1.000 phụ nữ, 1% tức 10 người thật sự có ung thư; 990 người không có.
2. Trong 10 người có ung thư, 90% tức 9 người có kết quả dương tính; 1 người âm tính (bị bỏ sót).
3. Trong 990 người không có ung thư, 10% tức 99 người bị cho kết quả dương tính sai; 891 người âm tính đúng.
4. Tổng số kết quả dương tính: 9 + 99 = 108. Vậy xác suất một phụ nữ chọn ngẫu nhiên có kết quả dương tính là 108/1.000, khoảng 11% (chính xác 10,8%).
5. Nhưng trong 108 người dương tính chỉ 9 người thật sự có ung thư, nên xác suất một phụ nữ dương tính thật sự mắc ung thư chỉ là 9/108 ≈ 8% (chính xác 8,3%).

(Người tổng hợp bổ sung từ cùng cây: trong 892 người âm tính có 891 người không mắc, nên một kết quả âm tính đáng tin tới 99,9%.)

Bài tập về xác suất có điều kiện này giúp hiểu một kết quả rất phản trực giác: dù phép chụp "chính xác 90%", **phần lớn phụ nữ có kết quả dương tính không mắc ung thư vú**. Rất dễ nhầm xác suất dương tính *khi biết có ung thư* với xác suất có ung thư *khi biết dương tính*.

Kiểu nhầm lẫn này thường được gọi là **ngụy biện của công tố viên**, vì nó rất phổ biến trong các vụ án có bằng chứng ADN. Một chuyên gia pháp y có thể nói: "nếu bị cáo vô tội, chỉ có 1 phần tỷ khả năng người đó khớp với ADN tìm thấy tại hiện trường". Câu này bị hiểu sai thành: "với bằng chứng ADN, chỉ có 1 phần tỷ khả năng bị cáo vô tội". Theo chú thích của tác giả, lỗi này còn có tên là "luật đảo điều kiện" (law of the transposed conditional) — nghe tối nghĩa một cách thú vị, nhưng chỉ có nghĩa là *xác suất của A khi biết B* bị nhầm với *xác suất của B khi biết A*. Lỗi này dễ mắc, nhưng logic của nó sai y như đi từ câu "nếu bạn là Giáo hoàng thì bạn là người Công giáo" sang câu "nếu bạn là người Công giáo thì bạn là Giáo hoàng" — ở đây cái sai dễ thấy hơn nhiều.

### 4. Rốt cuộc "xác suất" là gì? (What Is 'Probability' Anyway?, trang PDF 152–154)

Ở trường ta học toán về khoảng cách, khối lượng và thời gian — những thứ đo được bằng thước, cân hay đồng hồ. Nhưng đo xác suất bằng gì? Không có "máy đo xác suất". Xác suất giống một đại lượng "ảo": ta gán được cho nó một con số, nhưng không bao giờ đo trực tiếp được.

Đáng lo hơn là một câu hỏi hiển nhiên: rốt cuộc xác suất *nghĩa là gì*, định nghĩa tốt là gì? Câu hỏi có vẻ chẻ sợi tóc, nhưng triết học về xác suất vừa là đề tài hấp dẫn tự thân, vừa có vai trò lớn trong ứng dụng thống kê thực tế. Đừng chờ một sự đồng thuận gọn gàng từ "các chuyên gia": họ có thể đồng ý về toán học của xác suất, nhưng các triết gia và nhà thống kê đưa ra đủ loại ý tưởng khác nhau về ý nghĩa của những con số khó nắm bắt này và tranh cãi dữ dội. Một số đề xuất phổ biến:

- **Xác suất cổ điển:** cách được dạy ở trường, dựa trên tính đối xứng của đồng xu, xúc xắc, bộ bài…, định nghĩa là "tỷ số giữa số kết cục thuận lợi cho biến cố và tổng số kết cục có thể, giả định mọi kết cục đồng khả năng". Ví dụ: xác suất tung ra mặt một với xúc xắc cân là 1/6 vì xúc xắc có sáu mặt. Nhưng định nghĩa này có phần vòng vo, vì cần định nghĩa trước thế nào là "đồng khả năng".
- **Xác suất "liệt kê":** (thuật ngữ này, theo chú thích của tác giả, có vẻ do Philip Dawid đặt ra). Giả sử trong ngăn kéo có ba chiếc tất trắng và bốn chiếc tất đen, rút ngẫu nhiên một chiếc thì xác suất được tất trắng là bao nhiêu? Đáp án là 3/7, có được bằng cách liệt kê các khả năng. Nhiều người đã phải chịu đựng loại câu hỏi này ở trường; về bản chất nó là mở rộng của cách hiểu cổ điển, cần ý tưởng "chọn ngẫu nhiên" từ một tập vật thể có thật. Cuốn sách đã dùng ý tưởng này rất nhiều khi mô tả một điểm dữ liệu như được rút ngẫu nhiên từ một tổng thể.
- **Xác suất theo "tần suất dài hạn":** dựa trên tỷ lệ số lần biến cố xảy ra trong một chuỗi vô hạn thí nghiệm giống hệt nhau, đúng như khi mô phỏng các trò của Chevalier. Cách này có thể hợp lý (ít nhất về lý thuyết) với biến cố lặp lại vô hạn được, nhưng còn những dịp duy nhất như một cuộc đua ngựa hay thời tiết ngày mai thì sao? Thực ra, hầu như không tình huống thực tế nào lặp lại vô hạn được, kể cả về nguyên tắc.
- **Khuynh hướng hay "cơ hội":** ý tưởng rằng tình huống có một xu hướng khách quan nào đó tạo ra biến cố. Bề ngoài hấp dẫn — nếu là một đấng biết hết, có lẽ bạn sẽ nói được có một xác suất cụ thể để chuyến xe buýt sắp đến, hay để bạn bị xe đâm hôm nay. Nhưng nó dường như không cho người phàm chúng ta cơ sở nào để ước tính "cơ hội thật" khá siêu hình này.
- **Xác suất chủ quan hay "cá nhân":** phán đoán của một người cụ thể về một tình huống cụ thể, dựa trên hiểu biết hiện có của họ, và được diễn giải đại khái qua tỷ lệ cược (với tiền cược nhỏ) mà họ thấy hợp lý. Ví dụ: nếu tác giả sẽ được 1 bảng Anh nếu tung hứng được ba quả bóng trong năm phút, và ông sẵn sàng đặt cược 60 xu (không hoàn lại) cho vụ cược này, thì xác suất của ông cho biến cố đó là 60/100 = 0,6.

Mỗi "chuyên gia" có lựa chọn riêng trong các cách hiểu này; cá nhân Spiegelhalter thích cách cuối cùng — xác suất chủ quan. Nghĩa là ông cho rằng mọi xác suất bằng số về bản chất đều được *kiến tạo* theo những gì đã biết trong tình huống hiện tại — thực ra xác suất không thực sự "tồn tại" (trừ có thể ở cấp hạ nguyên tử). Cách tiếp cận này là nền tảng của trường phái suy luận thống kê **Bayes**, được bàn chi tiết ở Chương 11.

May là người đọc không cần đồng ý với lập trường (khá gây tranh cãi) của tác giả rằng xác suất bằng số không tồn tại khách quan. Hoàn toàn ổn khi giả định đồng xu và các thiết bị ngẫu nhiên hoá khác là ngẫu nhiên khách quan, theo nghĩa chúng tạo ra dữ liệu khó đoán đến mức không phân biệt được với dữ liệu sinh ra từ xác suất "khách quan". Vì vậy ta thường hành xử *như thể* các quan sát là ngẫu nhiên, ngay cả khi biết điều đó không hoàn toàn đúng. Ví dụ cực đoan nhất là **máy sinh số giả ngẫu nhiên**: chúng dựa trên những phép tính logic, hoàn toàn đoán trước được, không chứa chút ngẫu nhiên nào, nhưng cơ chế phức tạp đến mức trên thực tế không phân biệt được với các dãy thực sự ngẫu nhiên — chẳng hạn dãy lấy từ một nguồn hạt hạ nguyên tử. (Chú thích của tác giả: điều này giả định máy sinh số được thiết kế tốt và các số được dùng cho mô hình thống kê hay việc tương tự; chúng không đủ tốt cho ứng dụng mật mã, nơi tính đoán trước được có thể bị khai thác để phá mã.) Khả năng khá kỳ quặc này — hành xử như thể một điều là thật trong khi biết nó không thật — thường bị coi là phi lý nguy hiểm, nhưng nó sẽ rất hữu ích khi dùng xác suất làm nền cho phân tích thống kê.

Tiếp theo là bước then chốt nhưng khó: nêu mối liên hệ chung giữa lý thuyết xác suất, dữ liệu và việc tìm hiểu tổng thể mục tiêu. Tác giả phân biệt ba tình huống:

1. **Tình huống 1 — điểm dữ liệu được *sinh ra* bởi một thiết bị ngẫu nhiên hoá:** ví dụ tung xúc xắc, tung đồng xu, hay dùng máy sinh số giả ngẫu nhiên để phân bổ ngẫu nhiên một người vào một phác đồ điều trị rồi ghi lại kết quả điều trị. Lý thuyết xác suất đương nhiên áp dụng ở đây.
2. **Tình huống 2 — một điểm dữ liệu có sẵn được *chọn* bởi một thiết bị ngẫu nhiên hoá:** ví dụ chọn người tham gia một cuộc điều tra.
3. **Tình huống 3 — không có chút ngẫu nhiên nào, nhưng ta hành xử như thể điểm dữ liệu được sinh ra từ một quá trình ngẫu nhiên:** ví dụ khi diễn giải cân nặng sơ sinh của em bé nhà người bạn. Phần lớn dữ liệu rơi vào tình huống này.

Hầu hết sách vở không nói rõ những phân biệt này: xác suất thường được dạy qua thiết bị ngẫu nhiên hoá (tình huống 1) và thống kê được dạy qua ý tưởng "lấy mẫu ngẫu nhiên" (tình huống 2), trong khi thực tế phần lớn ứng dụng của thống kê không có thiết bị ngẫu nhiên hay lấy mẫu ngẫu nhiên nào (tình huống 3).

Xét trước tình huống 1 và 2. Ngay trước khi vận hành thiết bị ngẫu nhiên hoá, ta giả định có một tập các kết quả có thể quan sát được, cùng xác suất của từng kết quả — ví dụ đồng xu có thể ra ngửa hoặc sấp, mỗi mặt với xác suất ½. Nếu gán cho mỗi kết quả có thể một con số, ở đây 0 cho sấp và 1 cho ngửa, ta nói có một **biến ngẫu nhiên** với một **phân phối xác suất**. Trong tình huống 1, thiết bị ngẫu nhiên hoá bảo đảm quan sát được sinh ngẫu nhiên từ phân phối này; khi đã quan sát, tính ngẫu nhiên biến mất và mọi tương lai tiềm năng "sụp" về quan sát thực tế. (Chú thích của tác giả: có thể coi điều này tương tự cơ học lượng tử, nơi trạng thái hiện tại của, chẳng hạn, một electron được mô tả bằng một hàm sóng, và hàm sóng sụp về một trạng thái duy nhất khi electron thực sự được quan sát.) Tương tự, trong tình huống 2, nếu rút ngẫu nhiên một người và đo thu nhập của họ, về bản chất ta đã rút ngẫu nhiên một quan sát từ phân phối thu nhập của tổng thể.

Vậy xác suất rõ ràng liên quan khi có thiết bị ngẫu nhiên hoá. Nhưng phần lớn thời gian ta chỉ xét mọi số đo có trong tay, có thể được thu thập không chính thức, hoặc — như Chương 3 đã nói — thậm chí là mọi quan sát có thể có: tỷ lệ sống sót sau phẫu thuật tim cho trẻ em ở các bệnh viện, hay toàn bộ kết quả thi của học sinh Anh. Cả hai đều là toàn bộ dữ liệu, không hề có lấy mẫu ngẫu nhiên. Chương 3 đã nêu ý tưởng **tổng thể ẩn dụ**, gồm những khả năng lẽ ra có thể xảy ra nhưng phần lớn đã không xảy ra. Giờ ta phải chuẩn bị cho một bước có vẻ phi lý: hành xử *như thể* dữ liệu được sinh ra bởi một cơ chế ngẫu nhiên từ tổng thể đó, dù biết rõ là không.

### 5. Nếu quan sát được mọi thứ, xác suất xuất hiện ở đâu? (If We Observe Everything, Where Does Probability Come In?, trang PDF 154–157)

Câu hỏi mở đầu mục: bao lâu thì ta dự kiến thấy một ngày có từ bảy vụ giết người riêng biệt trở lên ở Anh và xứ Wales?

Khi những sự kiện cực đoan xảy ra sát nhau, như nhiều vụ rơi máy bay hay thiên tai liên tiếp, người ta có xu hướng tự nhiên cảm thấy chúng liên quan với nhau theo cách nào đó. Khi ấy cần tính xem những sự kiện như vậy bất thường đến đâu, và ví dụ sau cho thấy cách làm.

**Dữ liệu.** Để đánh giá một "cụm" từ bảy vụ giết người trở lên trong một ngày hiếm đến mức nào, tác giả xét dữ liệu ba năm (1.095 ngày) "giữa tháng 4/2014 và tháng 3/2016" (khoảng thời gian ghi trong sách mâu thuẫn với độ dài ba năm; xem khối Lưu ý): có 1.545 vụ giết người ở Anh và xứ Wales, trung bình 1.545/1.095 = 1,41 vụ mỗi ngày. (Chú thích của tác giả: một "vụ giết người" (homicide incident) là khi cùng một người hoặc nhóm người bị nghi là gây ra một hoặc nhiều vụ giết người liên quan với nhau; vì vậy một vụ xả súng hàng loạt hay một vụ tấn công khủng bố được tính là một vụ.) Trong giai đoạn này không có ngày nào có từ bảy vụ trở lên, nhưng sẽ rất ngây thơ nếu kết luận điều đó là không thể. Nếu xây dựng được một phân phối xác suất hợp lý cho số vụ giết người mỗi ngày, ta trả lời được câu hỏi.

**Lý do để dùng một phân phối xác suất.** Số vụ giết người ghi nhận mỗi ngày ở một nước đơn giản là sự thật: không có lấy mẫu, không có yếu tố ngẫu nhiên tường minh nào tạo ra từng sự kiện đau lòng — chỉ có một thế giới vô cùng phức tạp và khó đoán. Nhưng dù triết lý cá nhân về may rủi của ta là gì, hoá ra hành xử *như thể* các sự kiện này được tạo ra bởi một quá trình ngẫu nhiên vận hành theo xác suất là hữu ích. Có thể hình dung đầu mỗi ngày có một tổng thể rất lớn gồm nhiều người, mỗi người có một khả năng rất nhỏ trở thành nạn nhân. Dữ liệu kiểu này có thể được biểu diễn như các quan sát từ một **phân phối Poisson**, do Siméon Denis Poisson xây dựng ở Pháp thập niên 1830 để mô tả số vụ kết án oan mỗi năm. Từ đó, phân phối này được dùng để mô hình hoá đủ thứ: số bàn thắng một đội bóng ghi trong một trận, số vé số trúng thưởng mỗi tuần, cho tới số sĩ quan Phổ bị ngựa đá chết mỗi năm. Trong mỗi tình huống đó đều có rất nhiều cơ hội để sự kiện xảy ra, nhưng mỗi cơ hội có xác suất rất thấp, và điều này sinh ra phân phối Poisson vô cùng linh hoạt.

Phân phối chuẩn (Gauss) ở Chương 3 cần hai tham số — trung bình tổng thể và độ lệch chuẩn — còn phân phối Poisson chỉ phụ thuộc vào trung bình. Ở đây trung bình là số vụ giết người kỳ vọng mỗi ngày, giả định bằng 1,41, mức trung bình của giai đoạn ba năm. Tuy nhiên cần kiểm tra cẩn thận xem giả định Poisson có hợp lý không, tức có hợp lý không khi hành xử như thể số vụ giết người mỗi ngày là một quan sát ngẫu nhiên rút từ phân phối Poisson với trung bình 1,41.

**Một phép kiểm tra cụ thể.** Chỉ từ mức trung bình, dùng công thức phân phối Poisson hoặc phần mềm thông dụng, ta tính được xác suất có đúng năm vụ trong một ngày là 0,01134. Công thức (theo bảng thuật ngữ cuối sách): xác suất có đúng x vụ khi trung bình là μ bằng e^(−μ) × μ^x / x!. Người tổng hợp tính lại: 1,41⁵ = 5,573; 5! = 120; e^(−1,41) = 0,2441; vậy 0,2441 × 5,573 / 120 = 0,01134, đúng. Nghĩa là trong 1.095 ngày, dự kiến có 1.095 × 0,01134 = 12,4 ngày có đúng năm vụ. Đáng kinh ngạc là số ngày thực tế có năm vụ trong ba năm là… 13.

**Hình: Số ngày có 0, 1, 2… vụ giết người — quan sát và dự kiến theo phân phối Poisson, Anh và xứ Wales (Figure 8.5 trong sách).** Hình là đồ thị cột đôi (cột đen là số dự kiến, cột xám là số quan sát), trục tung là số ngày trong ba năm (0–400), trục hoành là số vụ mỗi ngày (0, 1, …, 6, "7 trở lên"). Cột "dự kiến" dưới đây do người tổng hợp tính bằng công thức Poisson với μ = 1,41; cột "quan sát" là ước lượng đọc từ đồ thị (trừ con số 13 do sách nêu).

| Số vụ trong ngày | Xác suất Poisson (μ = 1,41) | Số ngày dự kiến (× 1.095) | Số ngày quan sát (đọc từ đồ thị, ước lượng) |
|---:|---:|---:|---:|
| 0 | 0,2441 | 267,3 | khoảng 258 |
| 1 | 0,3442 | 376,9 | khoảng 385 |
| 2 | 0,2427 | 265,7 | khoảng 260 |
| 3 | 0,1141 | 124,9 | khoảng 131 |
| 4 | 0,0402 | 44,0 | khoảng 38 |
| 5 | 0,01134 | 12,4 | 13 (sách nêu) |
| 6 | 0,0027 | 2,9 | khoảng 3 |
| 7 trở lên | 0,00065 | 0,7 | 0 |
| **Tổng** | **1,0000** | **1.095** | **khoảng 1.088 (do sai số đọc hình)** |

Hai bộ cột gần như trùng nhau: chênh lệch lớn nhất chỉ khoảng 5–10 ngày ở các cột 0, 1, 3 và 4. Đồ thị có dạng lệch phải: đỉnh ở 1 vụ, rồi giảm nhanh, gần như bằng không từ 6 vụ trở lên. Tác giả nhận xét sự khớp là "rất sát", và hứa ở Chương 10 sẽ trình bày cách kiểm định chính thức xem giả định Poisson có chính đáng không.

**Trả lời câu hỏi ban đầu.** Từ phân phối Poisson, xác suất có từ bảy vụ trở lên trong một ngày là 0,07%. Người tổng hợp kiểm tra: tổng xác suất từ 0 đến 6 vụ là 0,99935, nên xác suất từ 7 vụ trở lên là 1 − 0,99935 = 0,00065 (0,065%, làm tròn 0,07%). Điều này có nghĩa là trung bình cứ khoảng 1.535 ngày mới có một ngày như vậy (1/0,00065 ≈ 1.540; khác biệt nhỏ do làm tròn trung bình), tức đại khái bốn năm một lần (1.535/365 = 4,2 năm). Kết luận: sự kiện này khá khó xảy ra trong diễn biến bình thường, nhưng không phải không thể.

Độ khớp của phân phối xác suất toán học này với dữ liệu thực nghiệm tốt "gần như đến mức đáng lo". Dù đằng sau mỗi sự kiện bi thảm là một câu chuyện riêng, và phần lớn không đoán trước được, dữ liệu lại hành xử như thể được sinh ra bởi một cơ chế ngẫu nhiên đã biết. Một cách nhìn là: những người khác lẽ ra có thể đã bị giết nhưng đã không — ta quan sát *một* trong nhiều thế giới có thể đã xảy ra, giống như khi tung đồng xu ta quan sát một trong nhiều dãy kết quả có thể.

**Quetelet và "vật lý xã hội".** Adolphe Quetelet, nhà thiên văn, nhà thống kê và nhà xã hội học người Bỉ giữa thế kỷ 19, là một trong những người đầu tiên chỉ ra tính dự đoán được đáng kinh ngạc của những mô hình tổng thể tạo nên từ các sự kiện riêng lẻ không đoán được. Ông bị cuốn hút bởi sự xuất hiện của phân phối chuẩn trong các hiện tượng tự nhiên, như phân phối cân nặng sơ sinh ở Chương 3, và đặt ra ý tưởng "l'homme moyen" (con người trung bình), người mang giá trị trung bình của mọi đặc điểm này. Ông phát triển ý tưởng "vật lý xã hội", vì tính đều đặn của các thống kê xã hội dường như phản ánh một quá trình bên dưới gần như cơ học. Giống như các phân tử chuyển động ngẫu nhiên của chất khí hợp lại thành những tính chất vật lý đoán trước được, hoạt động không đoán trước được của hàng triệu cuộc đời riêng lẻ hợp lại tạo nên, chẳng hạn, tỷ lệ tự tử quốc gia hầu như không đổi từ năm này sang năm khác.

May là ta không cần tin rằng các sự kiện thực sự do một sự ngẫu nhiên thuần tuý (dù đó là gì) điều khiển. Đơn giản là giả định "may rủi" gói gọn mọi sự khó đoán không tránh được của thế giới, đôi khi gọi là **biến thiên tự nhiên**. Vậy chương đã xác lập rằng xác suất là nền móng toán học phù hợp cho *cả* tính ngẫu nhiên "thuần tuý" — ở hạt hạ nguyên tử, đồng xu, xúc xắc… — *lẫn* biến thiên "tự nhiên" không tránh được, như ở cân nặng sơ sinh, khả năng sống sau phẫu thuật, kết quả thi, các vụ giết người, và mọi hiện tượng khác không hoàn toàn đoán trước được. Chương tiếp theo sẽ trình bày điều tác giả gọi là một bước phát triển thực sự đáng chú ý trong lịch sử hiểu biết của loài người: cách hai khía cạnh này của xác suất được kết hợp để tạo nền móng chặt chẽ cho suy luận thống kê chính thức.

### 6. Tóm tắt (Summary, trang PDF 158)

- Lý thuyết xác suất cung cấp một ngôn ngữ và bộ công cụ toán học chính thức để xử lý các hiện tượng may rủi.
- Hệ quả của xác suất không trực giác, nhưng có thể hiểu tốt hơn bằng ý tưởng tần số kỳ vọng.
- Các ý tưởng xác suất hữu ích ngay cả khi không có cơ chế ngẫu nhiên hoá tường minh nào.
- Nhiều hiện tượng xã hội cho thấy một sự đều đặn đáng kinh ngạc ở mô hình tổng thể, trong khi từng sự kiện riêng lẻ hoàn toàn không đoán trước được.

## Luận điểm cốt lõi

### Mệnh đề

Xác suất là ngôn ngữ toán học phù hợp để diễn đạt cả tính ngẫu nhiên thuần tuý lẫn biến thiên tự nhiên của thế giới; nó khó và phản trực giác, nhưng có thể lập luận đúng bằng tần số kỳ vọng; và ta được phép, thậm chí nên, hành xử như thể dữ liệu được sinh ra ngẫu nhiên từ một tổng thể (thật hoặc ẩn dụ) ngay cả khi không có cơ chế ngẫu nhiên nào, vì cách làm này mô tả dữ liệu tốt và cho phép trả lời những câu hỏi mà dữ liệu thô không trả lời được.

### Giả định

- Mọi xác suất đều có điều kiện: luôn dựa trên giả định về tình huống (đồng xu cân, tung đúng cách, tỷ lệ mắc bệnh 1%…).
- Các lần tung đồng xu, xúc xắc là độc lập; mỗi người trong tổng thể có khả năng như nhau được chọn vào mẫu.
- Có thể coi các sự kiện như vụ giết người là kết quả của rất nhiều cơ hội, mỗi cơ hội có xác suất rất nhỏ, và mức trung bình (1,41 vụ/ngày) ổn định trong suốt giai đoạn xét.
- Dữ liệu quan sát được là một trong nhiều "thế giới có thể đã xảy ra" (tổng thể ẩn dụ).
- Về triết học: tác giả cho rằng xác suất bằng số không tồn tại khách quan mà được kiến tạo từ hiểu biết hiện có; nhưng ông thừa nhận người đọc có thể hành xử như thể thiết bị ngẫu nhiên là ngẫu nhiên khách quan.

### Cơ chế

1. Thay câu hỏi "xác suất là bao nhiêu" bằng "trong N lần, dự kiến bao nhiêu lần" và vẽ cây tần số kỳ vọng.
2. Chuyển cây tần số thành cây xác suất; nhân dọc nhánh (quy tắc nhân cho biến cố độc lập), cộng giữa các nhánh xung khắc (quy tắc cộng), dùng phần bù khi "ít nhất một lần" khó tính trực tiếp.
3. Với xác suất có điều kiện, đọc cây theo cả hai chiều: từ tình trạng thật sang kết quả xét nghiệm (90%), và ngược lại từ kết quả xét nghiệm về tình trạng thật (9/108 ≈ 8%); hai chiều cho hai con số rất khác nhau, nhất là khi tình trạng thật hiếm.
4. Xác định dữ liệu thuộc tình huống nào: sinh ra bởi thiết bị ngẫu nhiên, được chọn bởi thiết bị ngẫu nhiên, hay không có ngẫu nhiên nào.
5. Ở tình huống không có ngẫu nhiên, chọn một phân phối xác suất hợp lý (Poisson cho số đếm sự kiện hiếm), ước tính tham số từ dữ liệu, kiểm tra độ khớp, rồi dùng phân phối để tính xác suất của những sự kiện chưa từng quan sát (từ 7 vụ trở lên trong một ngày).

### Bằng chứng và ví dụ tác giả đưa ra

- Bài toán Chevalier de Méré: mô phỏng 10.000 ván và lời giải bằng quy tắc xác suất cho cùng kết quả, Trò 1 thắng 52%, Trò 2 thắng 49%; phép tính sai của Chevalier (2/3 cho cả hai) do cộng xác suất của biến cố không xung khắc.
- Khảo sát 97 nghị sĩ Anh năm 2012: 60 người trả lời sai câu hỏi hai đồng xu (đáp án ¼).
- Sàng lọc ung thư vú: 1.000 phụ nữ, 10 người mắc, 108 người dương tính, chỉ 9 người dương tính thật sự mắc (8%).
- Ngụy biện của công tố viên trong các vụ án ADN ("1 phần tỷ"), và phép so sánh Giáo hoàng – người Công giáo.
- Năm cách hiểu xác suất với ví dụ: xúc xắc 1/6, tất trắng 3/7, mô phỏng trò Chevalier, xe buýt hay tai nạn, vụ cược tung hứng 60 xu cho 1 bảng.
- Số vụ giết người ở Anh và xứ Wales: 1.545 vụ trong 1.095 ngày; Poisson dự kiến 12,4 ngày có đúng 5 vụ, thực tế 13; cả phân phối khớp rất sát; xác suất từ 7 vụ trở lên mỗi ngày là 0,07%, khoảng 4 năm một lần.
- Lịch sử dùng phân phối Poisson: số vụ kết án oan, bàn thắng bóng đá, vé số trúng thưởng, sĩ quan Phổ bị ngựa đá chết.
- Quetelet: phân phối chuẩn trong tự nhiên, "con người trung bình", tỷ lệ tự tử quốc gia hầu như không đổi qua các năm.

### Kết luận và hàm ý cho người đọc số liệu

- Khi gặp một con số xác suất, hãy chuyển nó thành tần số: "trong 1.000 người như thế này, bao nhiêu người…". Cách này làm lộ ra ngay những lỗi như nhầm độ chính xác của xét nghiệm với khả năng mắc bệnh.
- Luôn hỏi "xác suất của cái gì, với điều kiện gì": P(bằng chứng | vô tội) không phải P(vô tội | bằng chứng); P(dương tính | bệnh) không phải P(bệnh | dương tính). Tỷ lệ nền (mức phổ biến của tình trạng) quyết định rất nhiều.
- Đừng cộng xác suất của các lần thử lặp lại; với "ít nhất một lần", hãy tính 1 trừ xác suất "không lần nào".
- Việc chưa từng quan sát một sự kiện cực đoan trong dữ liệu không có nghĩa là nó không thể xảy ra; một mô hình xác suất được kiểm tra kỹ giúp ước tính tần suất của nó.
- Một chuỗi sự kiện xấu xảy ra sát nhau chưa chắc có liên hệ; trước khi tìm nguyên nhân chung, hãy hỏi may rủi đơn thuần tạo ra cụm như vậy thường xuyên đến đâu.

### Trong ngôn ngữ thống kê

Chương trình bày các tiên đề cơ bản của xác suất (0 ≤ P(A) ≤ 1; P(không A) = 1 − P(A); P(A hoặc B) = P(A) + P(B) khi A, B xung khắc; P(A và B) = P(A) × P(B) khi A, B độc lập), xác suất có điều kiện và — ngầm định, không nêu tên — định lý Bayes qua ví dụ giá trị dự báo dương tính: P(ung thư | dương tính) = P(dương tính | ung thư) × P(ung thư) / P(dương tính) = 0,9 × 0,01 / 0,108 = 0,083. Về triết học, chương so sánh các cách diễn giải xác suất (cổ điển, tần suất, khuynh hướng, chủ quan/Bayes). Về mô hình hoá, chương giới thiệu biến ngẫu nhiên, phân phối xác suất và phân phối Poisson P(X = x) = e^(−μ) μ^x / x! với E(X) = Var(X) = μ, như xấp xỉ của phân phối nhị thức khi số cơ hội n rất lớn và xác suất mỗi cơ hội p rất nhỏ (μ = np), kèm một phép so sánh tần số quan sát với tần số kỳ vọng — tiền đề của kiểm định khi-bình phương về độ phù hợp ở Chương 10.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| probability | xác suất | số từ 0 đến 1 diễn đạt mức có thể xảy ra của biến cố |
| expected frequency | tần số kỳ vọng | số lần dự kiến xảy ra trong một số lần lặp cho trước |
| expected frequency tree | cây tần số kỳ vọng | sơ đồ rẽ nhánh ghi số trường hợp dự kiến ở mỗi nút |
| probability tree | cây xác suất | sơ đồ rẽ nhánh ghi tỷ lệ trên mỗi nhánh; nhân dọc nhánh |
| complement rule | quy tắc phần bù | P(A) = 1 − P(không A) |
| addition rule (OR rule) | quy tắc cộng (quy tắc HOẶC) | cộng xác suất của biến cố xung khắc |
| mutually exclusive events | biến cố xung khắc | không thể cùng xảy ra |
| multiplication rule (AND rule) | quy tắc nhân (quy tắc VÀ) | nhân xác suất của biến cố độc lập |
| independent / dependent events | biến cố độc lập / phụ thuộc | không ảnh hưởng / có ảnh hưởng tới xác suất của nhau |
| conditional probability | xác suất có điều kiện | xác suất khi biết một biến cố khác đã xảy ra |
| mammography | chụp X-quang tuyến vú | phép sàng lọc ung thư vú trong ví dụ |
| prosecutor's fallacy | ngụy biện của công tố viên | nhầm P(bằng chứng \| vô tội) với P(vô tội \| bằng chứng) |
| law of the transposed conditional | luật đảo điều kiện | tên khác của ngụy biện trên: nhầm P(A \| B) với P(B \| A) |
| classical probability | xác suất cổ điển | kết cục thuận lợi / tổng kết cục đồng khả năng |
| enumerative probability | xác suất liệt kê | đếm khả năng khi rút ngẫu nhiên từ tập vật thể |
| long-run frequency probability | xác suất theo tần suất dài hạn | tỷ lệ trong chuỗi vô hạn thí nghiệm giống hệt |
| propensity, chance | khuynh hướng, cơ hội | xu hướng khách quan của tình huống tạo ra biến cố |
| subjective / personal probability | xác suất chủ quan / cá nhân | phán đoán của một người, diễn giải qua tỷ lệ cược |
| Bayesian | (trường phái) Bayes | suy luận thống kê dựa trên xác suất chủ quan (Chương 11) |
| pseudo-random-number generator | máy sinh số giả ngẫu nhiên | phép tính xác định nhưng cho dãy trông như ngẫu nhiên |
| randomizing device | thiết bị ngẫu nhiên hoá | đồng xu, xúc xắc, máy sinh số ngẫu nhiên |
| random variable | biến ngẫu nhiên | đại lượng nhận các giá trị theo một phân phối xác suất |
| probability distribution | phân phối xác suất | danh sách giá trị có thể và xác suất của chúng |
| metaphorical population | tổng thể ẩn dụ | tập các kết cục có thể đã xảy ra nhưng phần lớn không |
| homicide incident | vụ giết người | một hoặc nhiều vụ giết người liên quan do cùng người/nhóm |
| Poisson distribution | phân phối Poisson | phân phối số đếm sự kiện hiếm; một tham số là trung bình |
| normal (Gaussian) distribution | phân phối chuẩn (Gauss) | đường cong hình chuông; hai tham số trung bình và độ lệch chuẩn |
| l'homme moyen (the average man) | con người trung bình | ý tưởng của Quetelet về người mang mọi giá trị trung bình |
| social physics | vật lý xã hội | ý tưởng của Quetelet về tính đều đặn gần như cơ học của xã hội |
| natural variability | biến thiên tự nhiên | sự khó đoán không tránh được của thế giới |

## Câu nói đáng nhớ

> "I have finally concluded that it is because probability really *is* a difficult and unintuitive idea." — Spiegelhalter, phần mở đầu chương
>
> *Dịch: Cuối cùng tôi đã kết luận rằng đó là vì xác suất thật sự là một ý tưởng khó và phản trực giác.*

> "There is no such thing as the unconditional probability of an event; there are always assumptions and other factors that could affect the probability." — mục "The Rules of Probability Made, Possibly, a Bit Simpler"
>
> *Dịch: Không có cái gọi là xác suất vô điều kiện của một biến cố; luôn có những giả định và yếu tố khác có thể ảnh hưởng tới xác suất.*

> "It is easy to confuse the probability of a positive test, given cancer, with the probability of cancer, given a positive test." — mục "Conditional Probability"
>
> *Dịch: Rất dễ nhầm xác suất xét nghiệm dương tính khi có ung thư với xác suất có ung thư khi xét nghiệm dương tính.*

> "There is no probability-ometer." — mục "What Is 'Probability' Anyway?"
>
> *Dịch: Không có máy đo xác suất.*

> "Indeed probability doesn't really 'exist' at all (except possibly at the subatomic level)." — mục "What Is 'Probability' Anyway?"
>
> *Dịch: Thực ra xác suất không thực sự "tồn tại" (trừ có thể ở cấp hạ nguyên tử).*

> "We have observed one of many possible worlds that could have occurred, just as when we flip coins we observe one of the many possible sequences." — mục "If We Observe Everything, Where Does Probability Come In?"
>
> *Dịch: Ta đã quan sát một trong nhiều thế giới có thể đã xảy ra, giống như khi tung đồng xu ta quan sát một trong nhiều dãy kết quả có thể.*

## Đánh giá và phát hiện đáng chú ý

### Điểm mạnh: dạy xác suất bằng tần số kỳ vọng, không bằng công thức

Chương làm được điều hiếm có: trình bày đủ bốn quy tắc xác suất và xác suất có điều kiện mà gần như không cần ký hiệu. Cây tần số kỳ vọng (4 lần tung, 1.000 phụ nữ) biến bài toán "kinh điển trong bài kiểm tra trí tuệ" thành phép đếm cấp tiểu học: 9 trong 108. Đây cũng là cách tác giả và nhóm Winton Centre khuyến nghị khi truyền đạt rủi ro cho công chúng (theo hiểu biết của người tổng hợp, cách trình bày bằng "tần số tự nhiên" này gắn với nghiên cứu của Gerd Gigerenzer và cộng sự). Lựa chọn đưa xác suất vào ở Chương 8, sau khi người đọc đã quen với dữ liệu, tóm tắt và bootstrap, cũng giúp xác suất xuất hiện như câu trả lời cho một nhu cầu chứ không phải một rào cản toán học.

### Điểm mạnh: phân biệt ba tình huống dữ liệu

Việc nói thẳng rằng phần lớn ứng dụng thống kê thuộc "tình huống 3" — không có lấy mẫu ngẫu nhiên, không có thiết bị ngẫu nhiên — là điểm sắc nhất của chương. Sách giáo khoa thường lặng lẽ áp mô hình lấy mẫu ngẫu nhiên lên dữ liệu toàn bộ (điểm thi, số vụ giết người, kết quả các bệnh viện) mà không giải thích. Spiegelhalter gọi tên bước "có vẻ phi lý" này và biện minh cho nó bằng độ khớp thực nghiệm (Poisson và số vụ giết người) và bằng khái niệm tổng thể ẩn dụ.

### Điểm yếu và đơn giản hoá

- Lập trường "xác suất không tồn tại" được nêu như sở thích cá nhân, nhưng chương không giải thích vì sao một người theo cách hiểu chủ quan vẫn có thể yên tâm kiểm tra mô hình Poisson bằng tần số quan sát — tức đang dùng ngầm cách hiểu tần suất. Sự căng thẳng giữa hai cách hiểu được để dành cho Chương 11 (nhận xét của người tổng hợp).
- Ví dụ sàng lọc ung thư vú dùng con số đơn giản hoá (90% cho cả độ nhạy và độ đặc hiệu, tỷ lệ mắc 1%). Theo hiểu biết của người tổng hợp, độ đặc hiệu thực tế của chụp X-quang tuyến vú thường cao hơn 90%, nên tỷ lệ dương tính giả trong thực tế thấp hơn ví dụ; nhưng thông điệp định tính — phần lớn người dương tính trong sàng lọc dân số rộng không mắc bệnh — vẫn đúng.
- Việc kiểm tra giả định Poisson chỉ dựa trên so sánh bằng mắt; chương không bàn những lý do Poisson có thể sai (mức trung bình thay đổi theo mùa, theo ngày trong tuần, hay các vụ giết người không độc lập với nhau). Định nghĩa "vụ giết người" gộp các vụ xả súng hàng loạt thành một vụ chính là một cách xử lý vấn đề không độc lập này.
- Khoảng thời gian dữ liệu giết người bị ghi sai (xem khối Lưu ý), và nhãn cây xác suất hai đồng xu có lỗi — những lỗi nhỏ nhưng đáng tiếc trong một chương dạy sự chính xác.

### Những gì đã thay đổi từ 2019 (theo hiểu biết của người tổng hợp)

Nội dung xác suất cơ bản của chương không lỗi thời. Hai điểm liên quan đã thay đổi: (1) đại dịch COVID-19 (2020–2022) biến ví dụ về xét nghiệm dương tính giả và tỷ lệ nền thành chuyện thời sự hằng ngày — khi tỷ lệ nhiễm trong cộng đồng thấp, tỷ lệ "dương tính nhưng không nhiễm" của xét nghiệm nhanh tăng lên đúng như logic cây tần số của chương, và chính tác giả xuất hiện nhiều trên truyền thông Anh để giải thích điều này; (2) số vụ giết người ở Anh và xứ Wales sau giai đoạn trong sách có tăng lên trong vài năm cuối thập niên 2010 rồi biến động, nên mức trung bình 1,41 vụ/ngày chỉ đúng cho giai đoạn xét — một lời nhắc rằng tham số của phân phối Poisson không cố định mãi.

### Liên hệ các chương khác

- Chương 3 ([C03-tong-the-va-do-luong.md](C03-tong-the-va-do-luong.md)): nơi đưa ra ý tưởng rút ngẫu nhiên, phân phối chuẩn của cân nặng sơ sinh, và tổng thể ẩn dụ; Chương 8 cho các ý tưởng này một nền tảng xác suất chính thức.
- Chương 7 ([C07-uoc-luong-va-khoang.md](C07-uoc-luong-va-khoang.md)): bootstrap là cách đo bất định bằng mô phỏng mà không cần lý thuyết xác suất; Chương 8 giải thích vì sao vẫn cần lý thuyết này.
- Chương 9 ([C09-ket-hop-xac-suat-va-thong-ke.md](C09-ket-hop-xac-suat-va-thong-ke.md)): dùng phân phối nhị thức, định lý giới hạn trung tâm và lại dùng phân phối Poisson của số vụ giết người để dựng khoảng tin cậy cho "tỷ lệ giết người thật".
- Chương 10 ([C10-tra-loi-cau-hoi-va-tuyen-bo-phat-hien.md](C10-tra-loi-cau-hoi-va-tuyen-bo-phat-hien.md)): kiểm định chính thức xem dữ liệu giết người có khớp phân phối Poisson không.
- Chương 11 ([C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md](C11-hoc-tu-kinh-nghiem-theo-cach-bayes.md)): phát triển cách hiểu xác suất chủ quan và xác suất có điều kiện thành định lý Bayes; ví dụ sàng lọc và ADN được mở rộng thành tỷ số khả năng.

### Vận dụng

- **Cho người đọc báo:** khi đọc "xét nghiệm chính xác 99%" hay "chỉ 1 phần triệu khả năng trùng hợp", hãy hỏi ngay tỷ lệ nền và chiều của điều kiện. Khi thấy tin "nhiều tai nạn liên tiếp", hãy nhớ rằng những cụm sự kiện hiếm vẫn xảy ra theo may rủi đơn thuần, ví dụ một ngày có từ 7 vụ giết người trở lên ở Anh và xứ Wales được dự kiến khoảng bốn năm một lần.
- **Cho nhà phân tích:** trình bày rủi ro cho người không chuyên bằng tần số tự nhiên ("9 trong 108") thay vì phần trăm có điều kiện. Với dữ liệu đếm (số khiếu nại, số sự cố, số ca bệnh mỗi ngày), thử so với phân phối Poisson trước khi kết luận có "bất thường"; nếu dữ liệu biến động nhiều hơn Poisson, đó là dấu hiệu có yếu tố hệ thống. Ghi rõ dữ liệu của mình thuộc tình huống nào trong ba tình huống, và nói rõ khi đang dùng một mô hình xác suất cho dữ liệu toàn bộ.
- **Cho người làm chính sách:** chương trình sàng lọc dân số rộng cho bệnh hiếm sẽ sinh ra nhiều dương tính giả hơn dương tính thật; cần tính trước bằng cây tần số và chuẩn bị cách truyền đạt kết quả. Trước khi phản ứng với một "cụm" sự kiện xấu, hãy hỏi chuyên gia thống kê xem cụm đó có vượt khỏi biến thiên tự nhiên không.
