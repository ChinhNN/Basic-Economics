# Beyond Binary: A Policy-Intensity Measure of Capital Flow Management — Vượt khỏi nhị phân: một thước đo cường độ chính sách quản lý dòng vốn

**Nguồn:** IMF Working Paper WP/2026/021.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Mọi chỉ số kiểm soát vốn được dùng rộng rãi hiện nay đều dựa trên nhãn nhị phân có hoặc không, nên chúng không nhìn thấy được điều quan trọng nhất: các nước như Trung Quốc tự do hoá bằng hàng trăm bước nhỏ mà không bao giờ mở hẳn một hạng mục nào. Bài xây chỉ số FinOpen bằng cách nối hai thứ mà tài liệu trước đây tách rời — **mức độ mở cửa** đọc từ văn bản tường thuật theo thang năm bậc, và **từng thay đổi chính sách** với ngày hiệu lực cụ thể — rồi gán trọng số cho mỗi thay đổi sao cho tổng các bước nhỏ khớp đúng với bước nhảy mức. Kết quả là một chỉ số **193 nước, theo ngày, 12 tiểu chỉ số**, và nó lật ngược một niềm tin cũ: kiểm soát vốn **không dai dẳng** như người ta nghĩ, mà được điều chỉnh thường xuyên hơn chế độ tỷ giá.

> **Lưu ý:** bản PDF bắt đầu từ phần Giới thiệu, không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau.

## Sơ đồ

### Bốn trường phái đo lường và điều mỗi trường phái bỏ lỡ

```text
       ❶ NHÃN NHỊ PHÂN — Chinn–Ito (2006), FKRSU (2016)
         gộp các nhãn "có / không" theo từng loại giao dịch vốn
         ✔ NHẤT QUÁN giữa các nước
         ✘ QUÁ THÔ: không thấy thay đổi từng phần
                              │
       ❷ THANG 0–4 TỪ VĂN BẢN — Quinn (1997, 2003)
         nước cho phép đầu tư nước ngoài NHƯNG cần phê duyệt thì
         được điểm TRUNG GIAN, không phải 0 hay 1
         ✔ bắt được CƯỜNG ĐỘ
         ✘ vẫn chỉ THEO NĂM, không thấy thay đổi trong năm
                              │
       ❸ ĐẾM SỐ BIỆN PHÁP — Pasricha và cộng sự (2018)
         đếm số lần siết và nới theo QUÝ
         ✔ bắt được thay đổi TRONG NĂM
         ✘ coi SỐ LƯỢNG hành động là đại diện cho CƯỜNG ĐỘ →
           không rõ có so sánh được giữa các nước hay không
                              │
       ❹ CƠ SỞ DỮ LIỆU SỰ KIỆN
         Forbes và cộng sự (2015): 220 sự kiện theo tuần, 2009–2011
         Phân loại CFM của IMF: ~500 trường hợp, 44 nước, 2008–2022
         ✔ phân loại theo NHIỀU CHIỀU
         ✘ DỪNG LẠI ở đó, không gộp thành một chỉ số LIÊN TỤC
       ═══════════════════════════════════════════════════════════
       ★★ CÙNG THỜI ĐIỂM có HAI NỖ LỰC SONG SONG
       Baba và cộng sự (2026) · chỉ số FARI 1999–2022, nhãn nhị
         phân được nhân viên IMF XÁC NHẬN LẠI, kèm phân loại
         siết / nới
       Bergant và cộng sự · khung dựa trên AI lượng hoá PHẠM VI
         RỘNG các hạn chế hối đoái và thương mại 1950–2022
       → ba bài cùng tấn công MỘT khoảng trống từ BA HƯỚNG khác nhau
       ═══════════════════════════════════════════════════════════
       ★ FinOpen: NỐI ❷ VỚI ❸
         mức độ mở cửa (level) ◂──── nối ────▸ thay đổi (change)
         giả định then chốt: BƯỚC NHẢY MỨC = TỔNG các thay đổi
         chính sách tích luỹ trong giai đoạn đó
```

### Vì sao nhãn nhị phân không đủ: một ví dụ

```text
       HÌNH 1 — TRUNG QUỐC so với INDONESIA
       nhãn nhị phân AREAER về việc người không cư trú mua trái
       phiếu: CẢ HAI NƯỚC đều ghi "CÓ KIỂM SOÁT", GIỐNG HỆT NHAU
       trong suốt 2005–2024 — một đường thẳng, KHÔNG THÔNG TIN
                              │
                              ▼
       NHƯNG THỰC TẾ KHÁC HẲN
       ┌──────────────────────┬──────────────────────────────────┐
       │ TRUNG QUỐC           │ INDONESIA                        │
       │ FinOpen tăng ĐỀU ĐẶN │ FinOpen ở mức CAO và TƯƠNG ĐỐI   │
       │ từ ~0,2 lên ~0,55    │ ỔN ĐỊNH quanh 0,78               │
       │ suốt gần hai thập kỷ │                                  │
       │ tỷ lệ nước ngoài nắm │ tỷ lệ nước ngoài nắm trái phiếu  │
       │ trái phiếu chính phủ │ chính phủ CAO HƠN HẲN, đạt đỉnh  │
       │ vẫn THẤP nhưng TĂNG  │ khoảng 40% giữa những năm 2010   │
       └──────────────────────┴──────────────────────────────────┘
       ★ FinOpen khớp với DỮ LIỆU THỰC TẾ về sở hữu nước ngoài,
         còn nhãn nhị phân thì KHÔNG
       ⚠ GIỚI HẠN ĐÁNH ĐỔI: Chinn–Ito lùi tới 1970, FinOpen bắt
         đầu 1996 — nhưng với 42 NƯỚC MỚI NỔI LỚN NHẤT theo GDP
         2022, chuỗi được KÉO DÀI VỀ 1960
```

### Cách chấm điểm: từ văn bản tới con số

```text
       BƯỚC ❶ — ĐỌC VĂN BẢN, CHẤM THANG NĂM BẬC (Bảng 2)
       ┌─────┬────────────────────────────────────────────────────┐
       │ 4   │ KHÔNG cần phê duyệt, KHÔNG hạn chế hối đoái;       │
       │     │ chuyển vốn tự do                                   │
       │ 3,5 │ ★ giao dịch CHÍNH đã tự do (ví dụ: chỉ hạn chế    │
       │     │ PHÁT HÀNH chứng khoán, hoặc chỉ hạn chế FDI ở     │
       │     │ NGÀNH NHẠY CẢM); các nước châu Âu tự do với nhau  │
       │ 3   │ phê duyệt NHÌN CHUNG ĐƯỢC CẤP; ngưỡng định lượng  │
       │     │ nhỏ hoặc biện pháp giá hạn chế                     │
       │ 2   │ phê duyệt / cấp phép / kiểm soát hối đoái với PHẦN │
       │     │ LỚN giao dịch; kiểm soát giá hoặc lượng VỪA PHẢI  │
       │ 1   │ phê duyệt NGHIÊM NGẶT; trần định lượng chặt hoặc  │
       │     │ biện pháp giá mang tính NGĂN CẤM                   │
       │ 0   │ CẤM CHUNG; tài khoản vốn ĐÓNG                      │
       └─────┴────────────────────────────────────────────────────┘
       BƯỚC ❷ — GẮN NĂM NHÃN CHO TỪNG BIỆN PHÁP (Bảng 1)
       ① LOẠI DÒNG ···· đầu tư trực tiếp / cổ phiếu danh mục /
                        nợ danh mục / đầu tư khác
       ② NƠI CƯ TRÚ ··· người không cư trú / người cư trú
       ③ CHIỀU DÒNG ··· vào / ra
       ④ CHIỀU BIỆN PHÁP  siết (−) / nới (+)
       ⑤ LOẠI BIỆN PHÁP   HÀNH CHÍNH / GIÁ / LƯỢNG / HỐI ĐOÁI
       ★ VÍ DỤ: Brazil ngày 4/10/2010 nâng thuế từ 2% lên 4% với
         dòng vào công cụ thu nhập cố định
         → SIẾT · nợ danh mục · người không cư trú · dòng vào ·
           DỰA TRÊN GIÁ
       BƯỚC ❸ — GÁN TRỌNG SỐ sao cho tổng các thay đổi KHỚP với
                bước nhảy mức
       ═══════════════════════════════════════════════════════════
       ★★ MƯỜI HAI TIỂU CHỈ SỐ
       4 loại dòng × 3 tổ hợp cư trú-chiều:
         · dòng VÀO của người KHÔNG CƯ TRÚ
         · dòng RA của người KHÔNG CƯ TRÚ
         · dòng RA của người CƯ TRÚ
       ⚠ KHÔNG có tiểu chỉ số "dòng VÀO của người CƯ TRÚ" —
         không nước nào hạn chế công dân mình mang tiền VỀ
       ★ ĐÂY LÀ BÀI ĐẦU TIÊN tách dòng RA của người KHÔNG CƯ TRÚ
         khỏi dòng RA của người CƯ TRÚ, và Sự thật 2 cho thấy hai
         thứ này KHÁC NHAU RẤT XA
```

### Hai kịch bản chấm điểm, minh hoạ bằng số thật

```text
       KỊCH BẢN A — CÓ MỘT BIỆN PHÁP ĐÓNG VAI TRÒ QUYẾT ĐỊNH
       TRUNG QUỐC · cổ phiếu danh mục · dòng vào của người không
       cư trú · chuyển từ MỨC 1 sang MỨC 2 giữa 2018 và 2019
       ┌─────────────────────────────────────────────────────────┐
       │ MỨC 1 (trước) · nhà đầu tư tổ chức nước ngoài đủ điều   │
       │   kiện (QFII) được đầu tư NHƯNG bị HẠN NGẠCH            │
       │ MỨC 2 (sau) · ★ 10/9/2019 XOÁ BỎ HOÀN TOÀN hạn ngạch   │
       │   cho QFII và RQFII                                     │
       ├─────────────────────────────────────────────────────────┤
       │ TỔNG CỘNG 17 BIỆN PHÁP NỚI trong giai đoạn chuyển       │
       │ · 16 biện pháp gia tăng ····· mỗi biện pháp 0,05        │
       │ · ★ biện pháp 10/9/2019 ····· 0,2 (ĐỘNG LỰC CHÍNH)      │
       └─────────────────────────────────────────────────────────┘
                              │
       KỊCH BẢN B — NHIỀU BIỆN PHÁP ĐÓNG GÓP NGANG NHAU
       ARGENTINA · dòng ra của người cư trú · MỨC 3 (2015) sang
       MỨC 4 (2017)
       mức 3: được mua tới 2 TRIỆU ĐÔ mỗi tháng không cần phê duyệt
       mức 4: GỠ BỎ MỌI hạn chế
       năm biện pháp, MỖI BIỆN PHÁP 0,2:
       ① cho tiếp cận thị trường hối đoái tự do và thống nhất
       ② nâng hạn mức tháng lên 5 TRIỆU ĐÔ
       ③ nới phương thức giao dịch ngoài ghi nợ tài khoản vãng lai
       ④ gỡ hạn mức số tiền còn lại
       ⑤ xoá mọi hạn chế còn sót
       ═══════════════════════════════════════════════════════════
       HAI QUY TẮC BỔ SUNG
       ★ BIỆN PHÁP "TRỌNG YẾU VĨ MÔ" theo phân loại CFM của IMF
         mà KHÔNG gây chuyển mức → chấm 0,5
         ví dụ: 5/2016 Trung Quốc cho định chế tài chính và doanh
         nghiệp pháp nhân TỰ DO huy động vốn xuyên biên giới trong
         hạn mức theo vốn và tài sản ròng
       ★ BIỆN PHÁP THUẾ · điểm = 0,2 × mức thay đổi thuế suất (đ.p)
         Ecuador 2012: thuế dòng ra 2% → 5% ······ điểm 0,6
         Ecuador 7/2023: 3,75% → 3,5% ············ điểm 0,05
       ★ RÀNG BUỘC TRẦN: tích luỹ các thay đổi KHÔNG ĐƯỢC đẩy chỉ
         số vượt qua mức hiện hành trên thang 0–4, trừ khi văn bản
         XÁC NHẬN đã chuyển mức
```

### Sáu sự thật cách điệu

```text
       ❶ TỰ DO HOÁ CHUNG, NHƯNG KHOẢNG CÁCH VẪN GIỮ NGUYÊN
         nước TIÊN TIẾN > nước MỚI NỔI > nước THU NHẬP THẤP,
         khoảng cách giữa ba nhóm ỔN ĐỊNH theo thời gian
         ⚠ ĐẢO CHIỀU CÓ THẬT VÀ KÉO DÀI
           nước tiên tiến · giảm trong khủng hoảng tài chính toàn
             cầu và khủng hoảng nợ công châu Âu
           nước mới nổi · giảm trong COVID và sau chiến tranh
             Nga–Ukraine, và ★ TỚI NAY VẪN CHƯA HỒI PHỤC
         chuỗi 1960–2022 cho 42 nước: kiểm soát chặt thời Bretton
         Woods → tự do hoá đều từ đầu 1990 → ★ BƯỚC NHỎ HƠN sau
         Quan điểm Thể chế 2012 của IMF
         → chính sách chuyển từ "mở hết là mục tiêu" sang "mở đến
           đâu tuỳ hoàn cảnh nước mình"
                              │
       ❷ ★★ THỨ TỰ MỞ CỬA GIẢM DẦN — PHÁT HIỆN MỚI
         DÒNG RA của người KHÔNG CƯ TRÚ ······ MỞ NHẤT
         DÒNG VÀO của người KHÔNG CƯ TRÚ ····· ở giữa
         DÒNG RA của người CƯ TRÚ ············ ĐÓNG NHẤT
         → khi hạn chế vốn nước ngoài, chính phủ nhắm vào DÒNG VÀO;
           hạn chế dòng RA của nước ngoài rất ít, và chỉ siết
           TRONG KHỦNG HOẢNG (Hy Lạp, Síp là ví dụ)
         ⚠ Ở NƯỚC THU NHẬP THẤP, khoảng cách giữa dòng vào của
           nước ngoài và dòng ra của dân trong nước LỚN NHẤT →
           dấu hiệu của ĐÀN ÁP TÀI CHÍNH: giữ vốn ở lại trong
           nước và hạn chế nhu cầu ngoại tệ
                              │
       ❸ NGHIÊNG VỀ CỔ PHIẾU
         nước TIÊN TIẾN · gần như mở hết dòng vào TRỪ FDI, nơi
           vẫn cấm ở các ngành vì AN NINH QUỐC GIA
         nước MỚI NỔI · cổ phiếu được quản lý LỎNG HƠN nợ —
           đúng trình tự mà tài liệu khuyến nghị: MỞ CỔ PHIẾU
           TRƯỚC, MỞ NỢ SAU, vì dòng nợ kém ổn định và vay nước
           ngoài quá mức đe doạ bền vững đối ngoại
         về dòng RA của người cư trú: nước tiên tiến và mới nổi
           mở hơn với FDI RA NGOÀI; ★ nước thu nhập thấp KHÔNG
           PHÂN BIỆT giữa các loại — vừa vì năng lực đầu tư ra
           ngoài hạn chế, vừa để TRÁNH KẼ HỞ cho vốn chảy ra qua
           kênh FDI
                              │
       ❹ KHÁC BIỆT RẤT LỚN GIỮA CÁC NƯỚC
         ★ MƯỜI nước hoạt động mạnh nhất chiếm 56% TỔNG SỐ biện
           pháp của 42 nước mới nổi trong 1960–2022
         mức mở 2022: Hong Kong, Hàn Quốc, Ai Cập gần mở hoàn
           toàn · Nga, Sri Lanka, Zimbabwe, Ethiopia rất chặt
         ★ HAI PHONG CÁCH ĐỐI LẬP
           TRUNG QUỐC · điều chỉnh DẦN DẦN bằng biện pháp cường
             độ thấp → đường FinOpen đi lên MƯỢT
           ARGENTINA · dùng biện pháp CƯỜNG ĐỘ CAO → đường
             FinOpen DAO ĐỘNG MẠNH, lên xuống dốc đứng
                              │
       ❺ KHÁC BIỆT THEO KHU VỰC
         mức mở 2022 · châu Âu CAO NHẤT, châu Phi hạ Sahara
           THẤP NHẤT
         tần suất dùng · châu Á, Mỹ Latin và Cộng đồng các Quốc
           gia Độc lập dùng NHIỀU NHẤT
         Mỹ Latin có tỷ lệ biện pháp SIẾT cao hơn
         ★ Mỹ Latin và CIS tập trung vào DÒNG RA CỦA NGƯỜI KHÔNG
           CƯ TRÚ và dùng nhiều biện pháp DỰA TRÊN HỐI ĐOÁI và
           DỰA TRÊN GIÁ; các nơi khác chủ yếu dùng HÀNH CHÍNH
                              │
       ❻ ★★ KIỂM SOÁT VỐN KHÔNG DAI DẲNG NHƯ NGƯỜI TA NGHĨ
         quan niệm cũ (Eichengreen–Rose 2014; Fernández và cộng
         sự 2015): các nước giữ NGUYÊN mức kiểm soát HÀNG THẬP KỶ
         ⚠ quan niệm đó ĐÚNG khi nhìn NHÃN NHỊ PHÂN, vốn chỉ đổi
           khi giao dịch được tự do HOÀN TOÀN
         ★ nhưng khi ĐẾM SỐ HÀNH ĐỘNG thì khác hẳn:
         ┌──────────────────────────────────────────────────────┐
         │ TẦN SUẤT ĐIỀU CHỈNH — so sánh trong "bộ ba bất khả   │
         │ thi", 131 nước, 1996–2018                            │
         │ CHÍNH SÁCH TIỀN TỆ ······ thay đổi NHIỀU NHẤT        │
         │   (phần lớn nước: HƠN 40 lần)                        │
         │ CHÍNH SÁCH VĨ MÔ THẬN TRỌNG · nhiều hơn CFM          │
         │ ★ KIỂM SOÁT VỐN ········· Ở GIỮA                      │
         │ CHẾ ĐỘ TỶ GIÁ ··········· thay đổi ÍT NHẤT           │
         │   (phần lớn nước: 0 hoặc 1 lần)                      │
         └──────────────────────────────────────────────────────┘
         → một số nhà hoạch định thực sự dùng kiểm soát vốn như
           CÔNG CỤ QUẢN LÝ THEO CHU KỲ, đúng tinh thần Khuôn khổ
           Chính sách Tích hợp của IMF
```

### Kiểm chứng: so với chỉ số cũ và với thực tế

```text
       TƯƠNG QUAN VỚI CÁC CHỈ SỐ SẴN CÓ (giá trị trung bình nước)
       Quinn ····· 0,89  ★ CAO NHẤT — và Quinn cũng là chỉ số
                         DUY NHẤT đo CƯỜNG ĐỘ
       FKRSU ····· 0,86
       Chinn–Ito · 0,84
       FARI ······ 0,79
       ⚠ Biểu đồ phân tán cho thấy các nước MỞ bám sát đường khớp,
         còn các nước ĐÓNG thì PHÂN TÁN RỘNG → chênh lệch lớn
         nhất xuất hiện đúng ở nơi tài khoản vốn bị kiểm soát chặt
       ═══════════════════════════════════════════════════════════
       ★★ HAI NGHIÊN CỨU TÌNH HUỐNG CHO THẤY CHÊNH LỆCH ĐẾN TỪ ĐÂU
       ARGENTINA 2012
         Chinn–Ito và FKRSU · báo hiệu tài khoản vốn ĐÓNG GẦN NHƯ
           HOÀN TOÀN, vì mọi nhãn nhị phân đều ghi "có kiểm soát"
         ★ THỰC TẾ · dòng vào VẪN ĐƯỢC PHÉP, chỉ chịu yêu cầu dự
           trữ KHÔNG HƯỞNG LÃI 30%; dòng ra cần phê duyệt để mua
           ngoại tệ
         → FinOpen cho thấy mức còn XA MỨC ĐÓNG HOÀN TOÀN
       TRUNG QUỐC
         Chinn–Ito và FKRSU · TĨNH và rất hạn chế suốt hai thập kỷ
         ★ FinOpen · quá trình tự do hoá ĐỀU ĐẶN
         → vì cải cách Trung Quốc gồm các điều chỉnh GIA TĂNG,
           KHÔNG BAO GIỜ mở hẳn một hạng mục nào → nhãn nhị phân
           ĐỨNG YÊN
         ✔ chỉ số Quinn, vốn cũng đo cường độ, CŨNG ghi nhận xu
           hướng tự do hoá này → xác nhận rằng vấn đề nằm ở
           PHƯƠNG PHÁP nhị phân, không phải ở dữ liệu
       ═══════════════════════════════════════════════════════════
       KIỂM CHỨNG CUỐI: SO VỚI ĐỘ MỞ THỰC TẾ
       thước đo thực tế = (tài sản + nợ đối ngoại) / GDP, loại dự trữ
       tương quan với thước đo này, tính theo nước rồi bình quân vùng:
       ┌──────────────────┬────────────────────────────────────────┐
       │ Châu Âu          │ ★ CAO NHẤT với mọi chỉ số              │
       │ ★ CHÂU Á         │ FinOpen ≈ 0,38 CAO HƠN Chinn–Ito       │
       │                  │ (≈0,09), FKRSU (≈0,30), FARI (≈0,27)   │
       │ ★ MỸ LATIN       │ FinOpen ≈ 0,44 CAO HƠN HẲN Chinn–Ito   │
       │                  │ (≈0,03) và FKRSU (≈0,01)               │
       │ CIS, SSA, MENA   │ tất cả các chỉ số đều THẤP             │
       └──────────────────┴────────────────────────────────────────┘
       ★★ ĐỌC BẢNG NÀY: châu Á và Mỹ Latin ĐÚNG LÀ hai khu vực
          DÙNG KIỂM SOÁT VỐN NHIỀU NHẤT (Sự thật 5) — và đó cũng
          chính là nơi việc ĐO CƯỜNG ĐỘ tạo ra khác biệt lớn nhất
          → khi chính sách được điều chỉnh tích cực, chỉ số nhị
            phân MẤT gần hết thông tin
       ⚠ Ở Trung Đông, CIS và châu Phi hạ Sahara, tương quan thấp
         với MỌI chỉ số → ở đó trình độ phát triển tài chính, chất
         lượng thể chế và đặc điểm cơ cấu mới là yếu tố chi phối
         vị thế đối ngoại, không phải mức mở pháp lý
```

## Ba câu hỏi bài viết trả lời

1. Vì sao các chỉ số kiểm soát vốn hiện có không nhìn thấy được quá trình tự do hoá của những nước như Trung Quốc?
2. Làm thế nào để nối mức độ mở cửa với từng thay đổi chính sách thành một chỉ số liên tục theo ngày?
3. Kiểm soát vốn có thực sự dai dẳng như tài liệu vẫn nói không?

## Dàn ý chi tiết

### 1. Vấn đề đo lường

- Tranh luận về hiệu quả của các biện pháp quản lý dòng vốn chưa có đồng thuận, và bài chỉ ra nguyên nhân chính nằm ở khâu đo lường. Khác chính sách tiền tệ vốn có thể đại diện bằng một lãi suất chính sách, các biện pháp quản lý dòng vốn biến thiên theo nhiều chiều cùng lúc: chiều thay đổi, nơi cư trú của chủ thể, chiều dòng vốn, loại dòng vốn, và loại công cụ.
- Bài dùng thuật ngữ trung tính là biện pháp quản lý dòng vốn thay vì kiểm soát vốn, theo cách gọi của IMF từ năm 2013, và giải thích rằng việc đổi tên phản ánh chuyển biến trong quan điểm học thuật. Trong thập niên 1980 và 1990, quan điểm chủ đạo cho rằng mở tài khoản vốn cải thiện tiếp cận vốn nước ngoài và thúc đẩy tăng trưởng, cho tới khi các cuộc khủng hoảng phơi bày hậu quả tiêu cực tiềm tàng của dòng vốn.
- Nguồn dữ liệu chính là Báo cáo Thường niên về Cơ chế và Hạn chế Hối đoái của IMF với mười một hạng mục. Mỗi hạng mục có hai phần: mô tả tường thuật về quy định hiện hành, và ghi chép các biện pháp mới kèm ngày hiệu lực. Từ năm 1996, quy định về giao dịch vốn được phân thành các loại tài sản chi tiết hơn, có tách riêng kiểm soát dòng vào và dòng ra, và mỗi phân mục được gắn nhãn nhị phân.

### 2. Phạm vi và định nghĩa

- Bài theo định nghĩa của IMF về biện pháp quản lý dòng vốn, rộng hơn khái niệm kiểm soát vốn truyền thống vốn chỉ tập trung vào các biện pháp phân biệt theo nơi cư trú.
- Ví dụ minh hoạ cho biện pháp dựa trên nơi cư trú là việc Ngân hàng Nhân dân Trung Quốc trong giai đoạn thị trường chứng khoán biến động 2015 và 2016 đã ngừng phê duyệt hạn ngạch mới cho nhà đầu tư tổ chức trong nước đủ điều kiện bằng nhân dân tệ thông qua chỉ đạo cửa sổ.
- Biện pháp không dựa trên nơi cư trú chủ yếu là chính sách quản lý ngoại hối, như yêu cầu dự trữ với tiền gửi ngoại tệ hoặc giới hạn trạng thái ngoại hối. Nhóm này chồng lấn một phần với chính sách vĩ mô thận trọng, dù mục tiêu khác nhau.
- Quan trọng về mặt phương pháp: các biện pháp không phân biệt theo nơi cư trú có tác động mơ hồ lên dòng vốn. Ví dụ, hạn chế cho vay ngoại tệ trong nước vừa có thể giảm vay nước ngoài vừa có thể giảm đầu tư ra ngoài của người cư trú. Vì vậy chúng chỉ được gắn nhãn về chiều dòng và chiều biện pháp, và bị loại khỏi phần tính chỉ số, dù vẫn được ghi lại để cho thấy bức tranh đầy đủ về bộ công cụ.
- Bài cũng nêu một hạn chế đáng chú ý về độ phủ: đối chiếu chéo cho Trung Quốc từ tháng 7/1979 tới tháng 4/2020 cho thấy nguồn chính thức của chính phủ công bố 199 biện pháp, trong khi báo cáo AREAER chỉ ghi nhận 97.

### 3. Quy trình xây dựng chỉ số

- Bước thứ nhất ước lượng mức độ mở cửa theo năm từ 1996 tới 2022 dựa trên văn bản tường thuật, dùng thang năm bậc phỏng theo phương pháp của Quinn. Có thêm mức 3,5 cho các trường hợp giao dịch chính đã tự do.
- Bước thứ hai gắn năm nhãn cho từng biện pháp. Điểm quan trọng là nơi cư trú được xác định theo chủ sở hữu khoản đầu tư xuyên biên giới chứ không theo đối tượng trực tiếp của quy định. Chẳng hạn biện pháp hạn chế khả năng cho vay ra nước ngoài của người cư trú được gắn nhãn ảnh hưởng tới người không cư trú, vì mục tiêu của nó là hạn chế dòng nợ nước ngoài chảy vào.
- Bước thứ ba là gán trọng số. Liên kết giữa mức và thay đổi dựa trên giả định rằng bước nhảy mức bằng tổng tích luỹ các thay đổi chính sách trong giai đoạn đó. Hai kịch bản được xử lý khác nhau: khi có một biện pháp rõ ràng đóng vai trò quyết định thì biện pháp đó nhận phần lớn điểm, còn khi nhiều biện pháp đóng góp tương đương thì điểm được chia đều.
- Giữa lần chuyển mức gần nhất và năm 2022, các biện pháp mới được gán cùng mức điểm với biện pháp gần nhất, dựa trên giả định rằng nhà chức trách có xu hướng duy trì cùng một phong cách quản lý theo thời gian. Có ràng buộc trần để tích luỹ các thay đổi không đẩy chỉ số vượt qua mức hiện hành.
- Hai quy tắc bổ sung: biện pháp được nhân viên IMF đánh giá là trọng yếu vĩ mô nhưng không gây chuyển mức thì chấm 0,5, và biện pháp thuế được chấm theo công thức 0,2 nhân mức thay đổi thuế suất tính bằng điểm phần trăm.
- Kết quả là mười hai tiểu chỉ số, được chuẩn hoá về khoảng từ 0 tới 1 với giá trị cao hơn nghĩa là mở hơn. Chỉ số theo tháng được tính bằng giá trị ngày cuối tháng, chứ không phải trung bình tháng, để tránh tạo ra biện pháp giả.

### 4. Hai cách gộp

- Cách gộp trung bình đơn giản coi mọi loại dòng và mọi chủ thể là quan trọng như nhau, với năm công thức gộp dần từ tiểu chỉ số lên chỉ số tổng.
- Cách gộp có trọng số dùng tỷ trọng của từng vị thế đầu tư trong tổng tài sản và nợ đối ngoại, lấy từ cơ sở dữ liệu Của cải Đối ngoại của các Quốc gia. Trọng số được tính bằng trung bình trượt trễ năm năm để giảm tính đồng thời giữa biện pháp và dòng vốn, và để phản ánh đặc điểm cơ cấu bền vững hơn là phản ứng ngắn hạn.
- So sánh hai cách cho Peru và Malaysia cho thấy chỉ số có trọng số cao hơn ở giai đoạn đầu, vì tỷ trọng tài sản nước ngoài nhỏ trong khi kiểm soát dòng ra của người cư trú lại chặt. Với Peru, khoảng cách thu hẹp dần từ 1991 tới 2015 khi tỷ trọng nợ nước ngoài giảm từ 94 xuống 26 phần trăm tổng nợ đối ngoại.
- Bài lưu ý rằng phân tích thành phần chính cho kết quả rất giống trung bình đơn giản, nên trung bình đơn giản được chọn vì dễ diễn giải hơn.

### 5. Ba hạn chế được nêu thẳng

- Thứ nhất, chỉ số có thể không phản ánh được việc thực thi trên thực tế các biện pháp hành chính. Nhà chức trách có thể trì hoãn phê duyệt mà không thay đổi quy định chính thức, và khoảng cách giữa pháp lý và thực tế có thể rất lớn.
- Thứ hai, việc cộng gộp các loại biện pháp khác nhau vẫn còn là câu hỏi mở. Cộng đơn giản hàm ý mỗi biện pháp có tác động độc lập, trong khi thực tế chúng có thể tương tác hoặc chồng lấn.
- Thứ ba, chỉ số phân loại biện pháp chỉ theo chiều nới hoặc siết, nên bỏ lỡ các mục tiêu phức tạp hơn. Ví dụ được nêu rất rõ: năm 1972 Brazil vừa miễn thuế khấu trừ 25 phần trăm với khoản vay nước ngoài vừa áp yêu cầu kỳ hạn tối thiểu 60 tháng. Chính sách này nhằm hạ chi phí vay đồng thời kéo dài kỳ hạn nợ để giảm rủi ro nợ đối ngoại, nhưng chỉ số không nắm bắt được vì hai tác động triệt tiêu nhau.

### 6. Sáu sự thật cách điệu

- Sự thật thứ nhất: các nước nhìn chung tiến tới mở cửa hơn, nhưng khoảng cách giữa ba nhóm thu nhập vẫn ổn định theo thời gian. Quan trọng hơn, tự do hoá không phải là quá trình một chiều: các nước tiên tiến đảo chiều trong khủng hoảng tài chính toàn cầu và khủng hoảng nợ công châu Âu, còn các nước mới nổi đảo chiều trong COVID và sau chiến tranh Nga và Ukraine mà tới nay vẫn chưa hồi phục.
- Bài cũng lưu ý một điểm khác biệt với nghiên cứu trước: Bergant và Forbes năm 2022 ghi nhận việc sử dụng biện pháp quản lý dòng vốn giảm trong đại dịch. Hai lý do được nêu để giải thích. Thứ nhất, nghiên cứu đó dựa trên dữ liệu tự báo cáo từ công cụ theo dõi chính sách của IMF, nơi việc sử dụng có thể bị khai thiếu nếu nhà chức trách dùng thuật ngữ khác để tránh định kiến gắn với cụm từ kiểm soát vốn. Thứ hai, nghiên cứu đó tập trung vào biện pháp nhằm giảm dòng ra ròng và chỉ dùng hai biến nhị phân, trong khi FinOpen phủ cả nới lẫn siết ở cả hai chiều.
- Sự thật thứ hai là phát hiện mới nhất của bài. Theo hiểu biết của tác giả, đây là bài đầu tiên tách dòng ra của người không cư trú khỏi dòng ra của người cư trú, và sự khác biệt giữa hai nhóm cho thấy cần phân tích riêng. Thứ tự mở cửa giảm dần từ dòng ra của người không cư trú, tới dòng vào của người không cư trú, rồi tới dòng ra của người cư trú. Ở các nước thu nhập thấp, khoảng cách giữa dòng vào của nước ngoài và dòng ra của dân trong nước là lớn nhất, phản ánh mức độ đàn áp tài chính cao.
- Sự thật thứ ba cho thấy xu hướng ưu ái cổ phiếu hơn nợ, đúng với trình tự tự do hoá mà tài liệu khuyến nghị. Ở nước thu nhập thấp không có sự phân biệt giữa các loại dòng ra của người cư trú, điều mà bài giải thích vừa bằng năng lực đầu tư ra ngoài hạn chế vừa bằng mục tiêu tránh kẽ hở cho vốn trong nước chảy ra qua kênh đầu tư trực tiếp.
- Sự thật thứ tư ghi nhận mức độ tập trung rất cao trong hoạt động chính sách: mười nước hoạt động mạnh nhất chiếm năm mươi sáu phần trăm tổng số biện pháp. Bài cũng đối lập hai phong cách quản lý, với Trung Quốc điều chỉnh dần bằng biện pháp cường độ thấp và Argentina dùng biện pháp cường độ cao gây dao động mạnh.
- Sự thật thứ năm cho thấy khác biệt vùng miền cả về mức mở lẫn về công cụ được ưa dùng, với Mỹ Latin và Cộng đồng các Quốc gia Độc lập nghiêng về biện pháp hối đoái và giá trong khi các nơi khác chủ yếu dùng biện pháp hành chính.
- Sự thật thứ sáu lật ngược quan niệm cũ. Tài liệu truyền thống cho rằng kiểm soát vốn rất dai dẳng và các nước hiếm khi điều chỉnh chúng theo biến động ngắn hạn. Bài chỉ ra rằng quan niệm này đúng khi nhìn nhãn nhị phân, vốn chỉ đổi khi giao dịch được tự do hoàn toàn, nhưng sai khi đếm số hành động chính sách. Trong so sánh ba chiều của bộ ba bất khả thi, biện pháp quản lý dòng vốn được điều chỉnh ít hơn công cụ tiền tệ nhưng nhiều hơn chế độ tỷ giá.

### 7. Kiểm chứng

- Tương quan với bốn chỉ số sẵn có đều cao, với chỉ số Quinn cao nhất ở mức 0,89. Điều này có ý nghĩa vì Quinn là chỉ số duy nhất khác cũng đo cường độ một cách hệ thống.
- Biểu đồ phân tán tiết lộ một mẫu hình quan trọng: các nước rất mở bám sát đường khớp, còn các nước kiểm soát chặt thì phân tán rộng. Nói cách khác, chênh lệch giữa FinOpen và các chỉ số nhị phân lớn nhất đúng ở nơi tài khoản vốn bị kiểm soát chặt, tức đúng ở nơi việc đo lường chính xác quan trọng nhất.
- Hai nghiên cứu tình huống làm rõ nguồn gốc chênh lệch. Với Argentina năm 2012, chỉ số nhị phân báo hiệu tài khoản vốn đóng gần như hoàn toàn, nhưng thực tế dòng vào vẫn được phép với yêu cầu dự trữ không hưởng lãi ba mươi phần trăm và dòng ra cần phê duyệt mua ngoại tệ. Với Trung Quốc, chỉ số nhị phân cho thấy bức tranh tĩnh và rất hạn chế, còn FinOpen cho thấy quá trình tự do hoá đều đặn. Điều xác nhận chẩn đoán là chỉ số Quinn, vốn cũng đo cường độ, cũng ghi nhận xu hướng tự do hoá này.
- Bài cũng nêu trường hợp ngược lại để công bằng: có lúc các chỉ số cũ biến thiên mà FinOpen không thấy. Chẳng hạn biện pháp về đầu tư danh mục tạo biến thiên lớn hơn trong chỉ số FKRSU vì năm trong mười loại tài sản của chỉ số đó chịu tác động trực tiếp. Ngoài ra, một số thay đổi nhãn nhị phân không có biện pháp hay văn bản tương ứng nên FinOpen không nắm bắt được.
- Kiểm chứng cuối cùng so với thước đo thực tế là tổng tài sản và nợ đối ngoại trên GDP. Kết quả có ý nghĩa nhất là ở châu Á và Mỹ Latin, hai khu vực dùng biện pháp quản lý dòng vốn tích cực nhất, FinOpen có tương quan cao hơn các chỉ số pháp lý khác. Điều này gợi ý rằng khi chính sách được điều chỉnh tích cực, việc đo cường độ cải thiện đáng kể khả năng nắm bắt độ mở thực tế.

### 8. Hướng tiếp theo

- Hai hướng mở rộng được nêu. Thứ nhất, dù cơ sở dữ liệu đã lùi về 1960 cho 42 nước mới nổi, việc áp dụng cùng phương pháp cho các nước còn lại sẽ cho một chuỗi toàn diện từ 1960 tới 2022.
- Thứ hai, chất lượng chỉ số phụ thuộc vào độ phủ của các biện pháp được ghi nhận. Mở rộng nguồn dữ liệu ra ngoài AREAER, chẳng hạn bằng cách bổ sung thông tin từ trang web chính thức của cơ quan quản lý, sẽ tăng độ đầy đủ và chính xác.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| FinOpen | Chỉ số mở cửa tài chính mới, 193 nước, tần suất ngày |
| CFM | Biện pháp quản lý dòng vốn, cách gọi trung tính của IMF |
| AREAER | Báo cáo Thường niên về Cơ chế và Hạn chế Hối đoái |
| Binary label | Nhãn nhị phân có hoặc không có kiểm soát |
| Policy intensity | Cường độ chính sách, mức độ chặt của một biện pháp |
| Narrative information | Thông tin tường thuật, mô tả bằng văn bản trong AREAER |
| Level versus change | Mức độ mở cửa so với từng thay đổi chính sách |
| Enforcement date | Ngày hiệu lực của biện pháp |
| Flow category | Loại dòng: FDI, cổ phiếu danh mục, nợ danh mục, đầu tư khác |
| Flow residency | Nơi cư trú của chủ sở hữu khoản đầu tư |
| Nonresidents' outflows | Dòng ra của người không cư trú, tức rút vốn nước ngoài về |
| Residents' outflows | Dòng ra của người cư trú, tức dân trong nước đầu tư ra ngoài |
| Administrative-based | Biện pháp hành chính: cho phép, cấm, phê duyệt |
| Price-based | Biện pháp dựa trên giá: thuế, yêu cầu dự trữ |
| Quantity-based | Biện pháp dựa trên lượng: hạn mức, hạn ngạch |
| FX-based | Biện pháp hối đoái: kiểm soát tiếp cận ngoại tệ |
| URR | Yêu cầu dự trữ không hưởng lãi, biện pháp giá của Argentina |
| QFII / RQFII | Nhà đầu tư tổ chức nước ngoài đủ điều kiện của Trung Quốc |
| Macro-critical | Trọng yếu vĩ mô, phân loại của nhân viên IMF |
| Holding period | Yêu cầu nắm giữ tối thiểu, hạn chế dòng ra |
| Minimum maturity | Yêu cầu kỳ hạn tối thiểu, hạn chế vay ngắn hạn |
| Repatriation requirement | Yêu cầu hồi hương nguồn thu về nước |
| Surrender requirement | Yêu cầu nộp lại ngoại tệ |
| De jure / de facto | Theo pháp lý so với theo thực tế |
| Financial repression | Đàn áp tài chính, giữ vốn ở lại trong nước |
| Sequencing | Trình tự tự do hoá: cổ phiếu trước, nợ sau |
| Stickiness | Tính dai dẳng, mức độ ít thay đổi của chính sách |
| Impossible trinity | Bộ ba bất khả thi: tiền tệ độc lập, tỷ giá ổn định, vốn tự do |
| Institutional View | Quan điểm Thể chế năm 2012 của IMF |
| EWN database | Cơ sở dữ liệu Của cải Đối ngoại của các Quốc gia |
| Window guidance | Chỉ đạo cửa sổ, cách can thiệp phi chính thức của Trung Quốc |

## Câu nói đáng nhớ

> "Binary AREAER labels indicate identical treatment of bond purchases by nonresidents in China and Indonesia, but FinOpen differentiates between the two."

> "Capital controls show a lower degree of stickiness than previously expected."

> "When CFMs are used actively, measuring policy intensity could substantially improve the ability of de jure indices to capture effective openness."

## Đánh giá và phát hiện đáng chú ý

### Giá trị thật nằm ở chỗ chỉ số này làm được việc mà chỉ số cũ không làm được, chứ không nằm ở chỗ nó đo đúng hơn

Cần tách bạch hai lời hứa mà bài trộn vào nhau. Lời hứa thứ nhất là FinOpen **đo độ mở chính xác hơn**. Lời hứa thứ hai là FinOpen **cho phép nghiên cứu những câu hỏi mà chỉ số cũ không cho phép**. Chỉ lời hứa thứ hai được chứng minh, và nó cũng là lời hứa quan trọng hơn.

Bằng chứng cho lời hứa thứ nhất mỏng hơn vẻ ngoài, và điều này bắt đầu ngay từ phép kiểm chứng mà bài coi là thuyết phục nhất. Tương quan **0,89 với chỉ số Quinn** được viện dẫn với lý lẽ rằng Quinn là chỉ số duy nhất khác cũng đo cường độ. Nhưng lập luận đó lẽ ra phải đi theo chiều ngược lại: Quinn và FinOpen **đọc cùng một nguồn văn bản AREAER, theo cùng một logic thang bậc, bằng cùng một loại phán đoán của con người**. Hai cách đọc gần giống nhau cho kết quả giống nhau là điều đáng mong đợi, không phải một xác nhận độc lập. Đáng chú ý là tương quan **thấp nhất, 0,79, lại là với FARI** — chỉ số được xây bằng phương pháp khác biệt nhất, tức là phép đối chiếu mang nhiều thông tin nhất lại cho kết quả kém khớp nhất.

Kiểm chứng thực sự có sức nặng là đối chiếu với độ mở thực tế. Tương quan với thước đo đó — tổng tài sản và nợ đối ngoại trên GDP — là khoảng **0,38 ở châu Á và 0,44 ở Mỹ Latin**. Đây được trình bày như một chiến thắng vì Chinn–Ito chỉ đạt khoảng 0,09 và 0,03 ở hai khu vực đó. Nhưng đọc theo giá trị tuyệt đối thì một chỉ số tương quan 0,4 với thực tế để lại hơn **84% biến thiên không giải thích được**. Cách đọc trung thực là: mọi chỉ số pháp lý đều là đại diện yếu cho độ mở thực tế, và FinOpen là cái ít yếu nhất. Ở Trung Đông, CIS và châu Phi hạ Sahara thì mọi chỉ số đều thấp, kể cả chỉ số này.

Giá trị thật là ở chiều khác. Mọi chỉ số trước đó đều **theo năm**; FinOpen có **ngày hiệu lực**. Điều đó mở ra cả một lớp câu hỏi không thể đặt ra trước đây: phản ứng của dòng vốn và tỷ giá quanh ngày ban hành biện pháp, thứ tự giữa biện pháp quản lý dòng vốn và quyết định lãi suất, tương tác với can thiệp ngoại hối. Đây là bước chuyển giống như bước chuyển từ đo chính sách tiền tệ bằng mức lãi suất bình quân năm sang đo bằng cú sốc trong cửa sổ hẹp quanh thông báo. Và cũng giống như ở đó, **giá trị nằm ở tần suất và thời điểm, không nằm ở việc mức được đo chính xác hơn.**

Đóng góp thứ hai ít được quảng cáo nhưng có sức nặng riêng: đây là chỉ số đầu tiên tách **dòng ra của người không cư trú** khỏi **dòng ra của người cư trú**. Hai thứ này bị gộp trong mọi chỉ số trước, và Sự thật 2 cho thấy chúng cách nhau rất xa.

### Mâu thuẫn nội tại nghiêm trọng nhất: kết luận phá quan niệm cũ lại được rút ra bằng đúng phương pháp mà bài chê

Sự thật 6 — kiểm soát vốn không dai dẳng như người ta nghĩ — được đặt ở vị trí phát hiện lật ngược văn liệu. Nó cũng là kết luận đứng trên nền yếu nhất.

Lập luận của bài là: quan niệm cũ đúng khi nhìn nhãn nhị phân, vì nhãn chỉ đổi khi một hạng mục được tự do hoàn toàn; nhưng khi **đếm số hành động chính sách** thì thấy các nước điều chỉnh thường xuyên. Vấn đề là **đếm số hành động chính xác là phương pháp ❸ mà bài chỉ trích ngay ở phần mở đầu**, với lý do "coi số lượng hành động là đại diện cho cường độ, không rõ có so sánh được giữa các nước hay không". Toàn bộ động cơ xây FinOpen là để vượt qua giới hạn đó. Vậy mà khi cần một kết luận gây ấn tượng, bài quay lại dùng chính phép đếm đó, chứ không dùng chỉ số cường độ mà nó vừa xây.

Phép so sánh trong bộ ba bất khả thi còn có vấn đề nặng hơn: **ba đối tượng được so không cùng loại.** Chính sách tiền tệ là một biến liên tục được điều chỉnh theo lịch họp định kỳ, nên đếm ra "hơn 40 lần thay đổi" là gần như tất yếu. Chế độ tỷ giá là một **phân loại** chỉ đổi khi chuyển hẳn chế độ, nên "0 hoặc 1 lần" cũng gần như tất yếu. Đặt số biện pháp quản lý dòng vốn vào giữa hai thứ đó rồi kết luận rằng nó "được điều chỉnh nhiều hơn chế độ tỷ giá" là một mệnh đề gần như đúng theo định nghĩa, không phải một phát hiện thực nghiệm.

Điều đáng tiếc là bài có sẵn công cụ để làm đúng: FinOpen là chuỗi liên tục, hoàn toàn có thể đo độ dai dẳng bằng hệ số tự hồi quy, bằng phương sai của thay đổi, hoặc bằng thời gian trung bình giữa hai lần chỉ số dịch chuyển quá một ngưỡng. Không phép đo nào trong số đó được thực hiện.

### Ba chỗ chấm điểm mang tính phán đoán, và một lỗ hổng rơi đúng vào ca minh hoạ chủ lực

Bài thẳng thắn liệt kê ba hạn chế ở mục riêng, nhưng cả ba đều ở tầng khái niệm. Những chỗ mỏng cụ thể hơn nằm trong chính các ví dụ chấm điểm.

**Thứ nhất, giả định nối mức với thay đổi là một ràng buộc kế toán, không phải một phép đo.** Trọng số được gán sao cho tổng các thay đổi khớp đúng với bước nhảy mức. Điều đó có nghĩa là chuỗi thay đổi **không mang thông tin độc lập** với chuỗi mức; nó là chuỗi mức được nội suy theo ngày, với cách phân bổ giữa các ngày do người chấm quyết định. Tương quan 0,89 với chỉ số Quinn — chỉ số đo mức theo năm — phù hợp với cách đọc này. FinOpen nên được hiểu là **Quinn có ngày tháng**, và đó đã là một đóng góp đủ lớn; việc trình bày nó như một phép đo mức tốt hơn là đòi hỏi quá nhiều.

**Thứ hai, quy tắc chấm thuế không cùng thang với quy tắc chấm biện pháp hành chính.** Ecuador nâng thuế dòng ra từ 2% lên 5% được chấm **0,6 điểm**; trong khi Trung Quốc **xoá bỏ hoàn toàn hạn ngạch QFII và RQFII** ngày 10/9/2019 — gỡ bỏ toàn bộ rào cản định lượng với nhà đầu tư tổ chức nước ngoài trên thị trường cổ phiếu — được chấm **0,2 điểm**. Trên cùng thang 0–4, một thay đổi thuế ba điểm phần trăm được tính nặng gấp ba lần việc dỡ bỏ cả một hệ thống hạn ngạch. Lý do là công thức thuế tuyến tính và không bị chặn, còn biện pháp hành chính thì bị ràng buộc bởi trần mức. Hai quy tắc này không thể cộng vào cùng một chỉ số mà không tạo méo mó, và bài không bàn tới.

**Thứ ba, quy tắc ngoại suy sau lần chuyển mức cuối cùng dựa trên một giả định về hành vi.** Các biện pháp mới sau lần chuyển mức gần nhất được gán cùng mức điểm với biện pháp gần nhất, "dựa trên giả định rằng nhà chức trách có xu hướng duy trì cùng một phong cách quản lý". Với một chỉ số chạy tới 2022 và đặt điểm chuẩn mức ở 2022, phần đuôi gần đây của chuỗi — chính là phần mà người dùng quan tâm nhất — được xây trên giả định này nhiều hơn trên văn bản.

Và lỗ hổng lớn nhất rơi đúng vào ca minh hoạ chủ lực. Trung Quốc xuất hiện ở khắp nơi trong bài: ở hình mở đầu so với Indonesia, ở kịch bản chấm điểm A, ở Sự thật 4 như một trong hai phong cách quản lý, và ở nghiên cứu tình huống kiểm chứng. Lập luận rất thuyết phục: nhãn nhị phân cho một đường thẳng trong suốt 2005–2024, trong khi FinOpen ghi nhận mức tăng từ khoảng 0,2 lên 0,55 — và tỷ lệ nắm giữ trái phiếu của nhà đầu tư nước ngoài trên thực tế xác nhận chiều của FinOpen.

Nhưng hai chi tiết khác trong cùng bài làm suy yếu chính ca minh hoạ này, và chúng nằm cách nhau vài mục nên không bao giờ được đặt cạnh nhau.

Chi tiết thứ nhất: đối chiếu chéo cho giai đoạn 7/1979 đến 4/2020 cho thấy nguồn chính thức của chính phủ Trung Quốc công bố **199 biện pháp**, trong khi AREAER — nguồn dữ liệu duy nhất của chỉ số — chỉ ghi nhận **97**. Nghĩa là với nước được dùng làm ví dụ hàng đầu, cơ sở dữ liệu nguồn bỏ sót hơn một nửa số biện pháp. Nếu phần bỏ sót phân bố không đều theo thời gian — mà khó có lý do để tin là nó đều — thì hình dạng của đường FinOpen cho Trung Quốc phụ thuộc vào những biện pháp nào tình cờ được ghi lại.

Chi tiết thứ hai sắc hơn. Bài tự nêu một ví dụ về biện pháp dựa trên nơi cư trú: trong đợt biến động thị trường chứng khoán 2015–2016, Ngân hàng Nhân dân Trung Quốc **ngừng phê duyệt hạn ngạch mới bằng chỉ đạo cửa sổ**. Chỉ đạo cửa sổ theo định nghĩa là can thiệp phi văn bản, không có ngày hiệu lực, không xuất hiện trong bất kỳ báo cáo quy định nào. Đây chính là hạn chế thứ nhất mà bài thừa nhận — chỉ số không phản ánh được việc thực thi trên thực tế.

Ghép hai chi tiết lại thì có một kết luận khá nặng: **nước mà tính gia tăng của nó là lý do tồn tại của chỉ số này cũng là nước mà công cụ chính sách chủ đạo của nó vô hình với chỉ số.** Điều đó không làm chỉ số vô dụng, nhưng nó có nghĩa là đường FinOpen của Trung Quốc mượt mà và đều đặn một phần vì các đợt siết đột ngột bằng chỉ đạo miệng không được ghi vào.

### Sự thật 2 chứa một phát biểu về chính trị kinh tế mà bài để nguyên dưới dạng số liệu

Thứ tự mở cửa giảm dần — dòng ra của người không cư trú mở nhất, dòng vào của người không cư trú ở giữa, **dòng ra của người cư trú đóng nhất** — được trình bày như một sự thật mô tả. Nhưng nó là kết quả có nội dung nhất trong cả bài.

Nó nói rằng các chính phủ, trên thực tế, **sợ công dân của chính mình mang tiền ra hơn là sợ nhà đầu tư nước ngoài rút tiền về.** Người nước ngoài được tự do ra đi gần như ở mọi nơi, chỉ bị chặn trong khủng hoảng cấp tính như Hy Lạp hay Síp. Người trong nước thì bị chặn thường trực. Đây là sở thích bộc lộ của nhà hoạch định chính sách, và nó khó biện minh bằng lý lẽ ổn định tài chính thông thường: nếu lo dừng đột ngột thì nhóm đáng lo là nhà đầu tư nước ngoài có thể rút hàng loạt, chứ không phải hộ gia đình trong nước.

Bài đi gần tới câu trả lời khi ghi nhận rằng khoảng cách giữa hai chiều này **lớn nhất ở các nước thu nhập thấp** và gọi đó là dấu hiệu của đàn áp tài chính. Nhưng nó dừng ở nhãn. Tài liệu trong thư mục Asean 2026 về hạn chế thanh toán thương mại và kiểm soát vốn cung cấp mảnh còn thiếu: ở đó, kiểm soát dòng vốn ra làm **tăng đầu tư công** trong khi đầu tư tư nhân không đổi, và tác giả giải thích rằng nhốt tiết kiệm trong nước lại giúp nhà nước hạ chi phí vay của chính mình. Ghép hai tài liệu thì bức tranh rõ: **kiểm soát dòng vốn ra của người cư trú chủ yếu là một công cụ tài khoá được khoác áo công cụ ổn định**, và Sự thật 2 của bài này là bằng chứng mô tả trên phạm vi 193 nước cho luận điểm đó.

Sự thật 3 thì đi cùng hướng với phần còn lại của thư mục: các nước mới nổi quản lý cổ phiếu lỏng hơn nợ, đúng trình tự mà văn liệu khuyến nghị và đúng với kết quả rằng chỉ kiểm soát vốn nợ mới có tác dụng lên cán cân vãng lai. Điều đáng chú ý là ở đây trình tự đó được quan sát như **hành vi thực tế của các chính phủ**, chứ không phải như khuyến nghị — tức là các nhà hoạch định đã làm đúng trước khi có bằng chứng thực nghiệm ủng hộ.

### Hệ quả cho toàn bộ văn liệu về hiệu quả của kiểm soát vốn, và bài không dám nói ra

Bài mở đầu bằng nhận định rằng tranh luận về hiệu quả của biện pháp quản lý dòng vốn chưa có đồng thuận, và quy nguyên nhân chính cho khâu đo lường.

Nếu chẩn đoán đó đúng — và biểu đồ phân tán ủng hộ nó rất mạnh, vì chênh lệch giữa FinOpen và chỉ số nhị phân **lớn nhất đúng ở những nước kiểm soát chặt**, tức đúng ở nhóm nước mà mọi nghiên cứu về kiểm soát vốn tập trung vào — thì hệ quả đi xa hơn nhiều so với mức bài phát biểu. Nó có nghĩa là **một phần đáng kể các kết quả thực nghiệm đã công bố về hiệu quả của kiểm soát vốn được ước lượng bằng biến giải thích sai**, và những kết quả "không có ý nghĩa thống kê" trong nhóm đó không nên được đọc là bằng chứng về sự vô hiệu của công cụ.

Điều này chạm trực tiếp vào các tài liệu khác trong cùng thư mục. Nghiên cứu về phát hành trái phiếu doanh nghiệp dùng bộ chỉ số Fernández và cộng sự — chính là FKRSU, một chỉ số nhị phân theo năm — làm biến chính sách trung tâm, với 19 lần bật tắt trong 22 năm. Theo logic của bài này, phần lớn biến thiên chính sách thực trong mẫu đó không được ghi nhận, và các hệ số ước lượng được tương ứng với việc **đi từ có kiểm soát sang không kiểm soát hoàn toàn**, chứ không phải với những điều chỉnh cường độ mà các nước thực sự làm.

Bài không nói câu này, có lẽ vì nó đặt dấu hỏi lên một phần lớn văn liệu, trong đó có nhiều bài của chính IMF. Nhưng nó là hệ quả logic trực tiếp của điều bài chứng minh.

### Với Việt Nam: đúng ca mà chỉ số cũ không nhìn thấy, và một chi phí đo lường rất cụ thể

Việt Nam nằm trong 193 nước của FinOpen, và thuộc đúng loại mà bài dùng Trung Quốc làm đại diện: **tự do hoá bằng nhiều bước nhỏ, hiếm khi mở hẳn một hạng mục nào.** Nới room ngoại cho từng nhóm ngành, mở dần cho nhà đầu tư nước ngoài trên thị trường trái phiếu, điều chỉnh quy định về vay nước ngoài của doanh nghiệp, nới hạn mức chuyển tiền — tất cả đều là những điều chỉnh gia tăng không làm đổi nhãn nhị phân.

Hệ quả thứ nhất mang tính nghiên cứu: **mọi nghiên cứu về Việt Nam dùng Chinn–Ito hay FKRSU đều đang làm việc với một biến gần như không đổi.** Nếu độ mở pháp lý của Việt Nam là một đường thẳng trong bộ dữ liệu, thì không hồi quy nào có thể tìm ra tác động của việc tự do hoá tài khoản vốn, và kết quả "không có ý nghĩa" phải được đọc là "không đo được", không phải "không có".

Hệ quả thứ hai mang tính thực tiễn và ít được chú ý. Độ mở pháp lý được các chỉ số quốc tế ghi nhận không chỉ là vấn đề học thuật: nó đi vào đánh giá của tổ chức xếp hạng, vào tiêu chí nâng hạng thị trường của các nhà cung cấp chỉ số, và vào nhận định của nhà đầu tư tổ chức về khả năng tiếp cận và khả năng rút vốn. Một nước tự do hoá bằng trăm bước nhỏ mà không bước nào làm đổi nhãn sẽ **không được ghi nhận là đã tự do hoá** — chi phí thật của việc bị đo sai. Bài này cho thấy cách khắc phục nằm ở đâu: chỉ số dựa hoàn toàn vào AREAER, và AREAER dựa vào những gì nhà chức trách báo cáo. Việc ghi chép đầy đủ từng biện pháp kèm ngày hiệu lực vì vậy là một hành động có lợi ích trực tiếp, chứ không phải một nghĩa vụ hành chính.

Hệ quả thứ ba là một lời cảnh báo. Hạn chế lớn nhất mà bài thừa nhận — khoảng cách giữa pháp lý và thực tế, khi nhà chức trách có thể trì hoãn phê duyệt mà không đổi quy định — mô tả khá chính xác cách vận hành trên thực tế của nhiều kênh vốn ở Việt Nam. Điều đó có nghĩa là ngay cả FinOpen cũng sẽ đo Việt Nam mở hơn thực tế. Với một nền kinh tế rất mở về thương mại nhưng còn kiểm soát tài khoản vốn và chưa có đồng tiền chuyển đổi tự do, khoảng cách giữa văn bản và thực thi chính là phần quan trọng nhất của chính sách — và không chỉ số nào hiện có đo được nó.
