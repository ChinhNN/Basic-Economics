# Elections Matter: Capital Flows and Political Cycles — Bầu cử có vai trò: dòng vốn và chu kỳ chính trị

**Nguồn:** IMF Working Paper WP/2025/243.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 3, không có trang bìa và trang tác giả).
**Ý chính:** Bài dùng bầu cử làm đại diện cho bất định chính trị và tìm thấy rằng dòng vốn tư nhân vào các nền kinh tế mới nổi giảm trong quý bầu cử, nhưng điều đáng chú ý nhất không phải là hiệu ứng trung bình mà là **mức độ phân hoá giữa các nước**. Nhóm nước thuộc phần tư thấp nhất về ổn định chính trị mất **28% dòng vốn vào** trong quý bầu cử, và con số này vọt lên **hơn 50%** khi đương nhiệm thua hoặc bầu cử diễn ra ngoài lịch định sẵn. Ngược lại, các nước có điểm ổn định chính trị **trên mức trung bình không chịu tác động nào có ý nghĩa thống kê**. Một phát hiện tinh tế nữa: độ sâu tài chính giúp chống đỡ cú sốc bất định **toàn cầu** nhưng **không** chống đỡ được bất định **chính trị trong nước** — chỉ chất lượng thể chế mới làm được điều đó.

> **Lưu ý:** bản PDF bắt đầu từ trang 3 (phần Giới thiệu), không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau.

## Sơ đồ

### Vì sao bầu cử là công cụ nghiên cứu tốt

```text
       LẬP LUẬN CỐT LÕI
       ★ KHÔNG PHẢI thay đổi chính sách CUỐI CÙNG mới quan trọng,
         mà chính SỰ BẤT ĐỊNH quanh các thay đổi CÓ THỂ XẢY RA —
         BẤT KỂ chúng có thành hiện thực hay không — đã đủ ảnh
         hưởng tới hành vi nhà đầu tư (Ahir và cộng sự 2022)
       → nhà đầu tư RÚT hoặc GIẢM phơi nhiễm TRƯỚC, TRONG và NGAY
         SAU khi bỏ phiếu (Julio và Yook 2016)
       ═══════════════════════════════════════════════════════════
       NỀN TẢNG LÝ THUYẾT
       Bernanke (1983) về đầu tư dưới bất định: bất định về hàm ý
       DÀI HẠN của một sự kiện làm TRÌ HOÃN quyết định đầu tư, vì
       chủ thể kinh tế ĐỊNH GIÁ CHO VIỆC CHỜ THÊM THÔNG TIN
       → khung này áp dụng được cho CẢ doanh nghiệp LẪN nhà đầu tư
       ═══════════════════════════════════════════════════════════
       ★ VÌ SAO BẦU CỬ LÀ "THÍ NGHIỆM TỰ NHIÊN GẦN ĐÚNG"
       thời điểm bầu cử thường được ẤN ĐỊNH TRƯỚC bởi hiến pháp,
       KHÔNG chịu ảnh hưởng của nhà đầu tư cụ thể hay môi trường
       kinh tế hiện hành, và LẶP LẠI theo chu kỳ đều đặn
                              │
                              ▼
       ⚠ NHƯNG CÓ VẤN ĐỀ NỘI SINH — bài xử lý bằng NĂM cách
       ① BIẾN CÔNG CỤ · dùng THỜI GIAN KỂ TỪ LẦN BẦU CỬ TRƯỚC làm
          công cụ (một biến dự báo CƠ HỌC cho xác suất sắp bầu cử)
          ★ kiểm định Durbin-Wu-Hausman KHÔNG BÁC BỎ giả thuyết
            ngoại sinh → coi bầu cử là ngoại sinh là ĐÚNG về mặt
            thống kê
       ② NHÂN QUẢ GRANGER · bầu cử Granger-gây ra dòng vốn, NHƯNG
          dòng vốn KHÔNG Granger-gây ra bầu cử
       ③ HỒI QUY GIẢ DƯỢC dùng biến dẫn
       ④ mô hình LOGIT về thời điểm bầu cử
       ⑤ ★ MẪU CON chỉ gồm bầu cử theo LỊCH ĐỊNH SẴN (80% mẫu)
       ⚠ VÌ SAO CẦN: theo tài liệu chu kỳ kinh doanh chính trị từ
         Nordhaus (1975), người đương nhiệm cơ hội có thể tung
         kích thích TÀI KHOÁ và TIỀN TỆ trước bầu cử để đẩy tăng
         trưởng ngắn hạn → bầu cử có thể tác động tới kết quả vĩ
         mô TRỰC TIẾP, độc lập với bất định
```

### Dữ liệu và bối cảnh

```text
       MẪU: 38 NỀN KINH TẾ MỚI NỔI · tần suất QUÝ · 1990–2020
       ⚠ dừng ở 2020 vì cơ sở dữ liệu biến chính trị cập nhật CHẬM
       ⚠ ★ KHÔNG CÓ TRUNG QUỐC — một nước nhận vốn quan trọng —
         vì thiếu dữ liệu ngày bầu cử trong cả DPI lẫn NELDA
       ═══════════════════════════════════════════════════════════
       XỬ LÝ DỮ LIỆU DÒNG VỐN — BA BƯỚC QUAN TRỌNG
       ① CHUẨN HOÁ theo GDP XU HƯỚNG (lọc HP trên GDP quý ước từ
          số liệu năm của Triển vọng Kinh tế Thế giới; thêm hai
          năm sau điểm cuối để giảm chệch đầu mút)
       ② ★ TÁCH DÒNG VỐN CHÍNH THỨC KHỎI DÒNG VỐN TƯ NHÂN
          trừ khỏi dòng vào: nợ của ngân hàng trung ương và chính
            phủ với người không cư trú, cùng phân bổ quyền rút vốn
            đặc biệt
          trừ khỏi dòng ra: tài sản tài chính do ngân hàng trung
            ương và chính phủ mua
          ⚠ VÌ SAO QUAN TRỌNG: chủ nợ chính thức có thể được huy
            động để NGĂN khủng hoảng bằng cách BÙ ĐẮP dòng vốn tư
            nhân chảy ra → điều đó sẽ TRIỆT TIÊU đúng tác động
            bất định mà bài muốn đo
       ③ TẬP TRUNG VÀO DÒNG VÀO GỘP vì dòng ròng che giấu biến
          động lớn trong giao dịch của người cư trú và không cư trú
          ★ và vì bất định chính trị cảm nhận được LỚN HƠN với
            nhà đầu tư NƯỚC NGOÀI so với trong nước
       ═══════════════════════════════════════════════════════════
       DIỄN BIẾN DÒNG VỐN (Hình 1 và 2)
       đỉnh trước khủng hoảng tài chính toàn cầu: TRÊN 10% GDP
       quý xu hướng
       ⚠ dòng vào KHÔNG TRỞ LẠI mức trước khủng hoảng, trong khi
         dòng ra TĂNG từ DƯỚI 1% thập niên 1990 lên TRÊN 3% thập
         kỷ gần đây → khoảng cách THU HẸP DẦN
         (phản ánh sự nổi lên của nhà đầu tư tổ chức ở thị trường
          mới nổi và quá trình tự do hoá tài khoản vốn từng bước)
       cơ cấu: FDI lớn nhất, ỔN ĐỊNH ở 2% GDP suốt 25 năm KỂ CẢ
       trong COVID
       ★ năm 2007, dòng vốn khu vực NGÂN HÀNG chiếm GẦN MỘT NỬA
         tổng dòng vào, rồi SỤP ĐỔ khi thanh khoản toàn cầu thắt
         chặt — chủ yếu do đảo chiều của cho vay ngân hàng NGẮN HẠN
       ═══════════════════════════════════════════════════════════
       ĐẶC ĐIỂM BẦU CỬ (Bảng 1) — 261 CUỘC BẦU CỬ
       độ dài nhiệm kỳ ············ 15,6 quý (≈ 4 năm), sd 4,6
       biên độ đa số ·············· 57,3%, sd 16,5
       tỷ lệ chủ thể phủ quyết rời  14,3%, sd 28,5
       phân cực ··················· 0,6 (thang 0–2), sd 0,8
       ── TỶ LỆ CÁC CUỘC BẦU CỬ CÓ ĐẶC ĐIỂM ──────────────────
       có thăm dò đáng tin và THUẬN LỢI cho đương nhiệm ··· 34,5%
       có BẠO LỰC gây chết người dân thường ··············· 25,7%
       KHÔNG theo lịch định sẵn ··························· 19,9%
       ★ ĐƯƠNG NHIỆM THUA ································· 58,2%
```

### Kết quả cơ sở: điều gì thúc đẩy dòng vốn

```text
       BẢNG 2 — DÒNG VỐN TƯ NHÂN VÀO GỘP (% GDP xu hướng)
       sai số chuẩn Driscoll-Kraay (đã kiểm định phụ thuộc chéo
       bằng kiểm định Pesaran và XÁC NHẬN có phụ thuộc)
       ┌──────────────────────────┬──────────┬────────────────────┐
       │ BIẾN                     │ CƠ SỞ    │ ĐẦY ĐỦ (cột 5)     │
       ├──────────────────────────┼──────────┼────────────────────┤
       │ ★ VIX (log)              │ −4,24*** │ −4,47***           │
       │   Thanh khoản toàn cầu   │ +0,23**  │ +0,24**            │
       │ ⚠ Chênh lệch lãi suất    │ −0,043   │ −0,055             │
       │   thực                   │ KHÔNG ý  │ KHÔNG ý nghĩa      │
       │   ★ Chênh lệch tăng      │ +0,38*** │ +0,42***           │
       │     trưởng               │          │                    │
       │   Phát triển thị trường  │ +7,70**  │ +10,4**            │
       │     tài chính            │          │                    │
       │ ⚠ Chỉ số Chinn-Ito       │ +0,33    │ +0,44              │
       │   (độ mở tài khoản vốn)  │ KHÔNG ý  │ KHÔNG ý nghĩa      │
       │ ★ Ổn định chính trị ICRG │ +0,20*** │ +0,19***           │
       ├──────────────────────────┼──────────┼────────────────────┤
       │ Bầu cử (đứng MỘT MÌNH)   │  +0,64   │ —                  │
       │                          │ KHÔNG ý  │                    │
       │ ★★ Bầu cử (khi CÓ tương  │    —     │ ★ −11,5**          │
       │    tác)                  │          │                    │
       │ ★★ Bầu cử × Ổn định      │    —     │ ★ +0,18**          │
       │    chính trị ICRG        │          │                    │
       │ Trước bầu cử 3–4 quý     │    —     │  +0,61             │
       │ Trước bầu cử 1–2 quý     │    —     │  −0,53             │
       │ ★ SAU bầu cử 1–2 quý     │    —     │ ★ −0,96**          │
       │ Sau bầu cử 3–4 quý       │    —     │  +0,043            │
       └──────────────────────────┴──────────┴────────────────────┘
       ★★★ ĐỌC HAI DÒNG TƯƠNG TÁC — ĐÂY LÀ TRỌNG TÂM CỦA BÀI
       khi đứng MỘT MÌNH, biến giả bầu cử KHÔNG CÓ Ý NGHĨA
       nhưng khi ĐƯA VÀO CÙNG chỉ số ổn định chính trị VÀ số hạng
       tương tác, CẢ BA đều trở nên CÓ Ý NGHĨA
       → nghĩa là: bầu cử ĐÚNG LÀ có tác động tiêu cực, NHƯNG tác
         động đó ĐƯỢC LÀM DỊU trong môi trường chính trị ổn định
         hơn — nên hiệu ứng TRUNG BÌNH bị TRIỆT TIÊU và không
         nhìn thấy được nếu không tách ra
       ⚠ KHÔNG có sụt giảm có ý nghĩa TRƯỚC bầu cử; cú sốc rơi vào
         QUÝ BẦU CỬ và HAI QUÝ SAU ĐÓ
       ⚠ R bình phương trong nhóm chỉ 0,19–0,23 — bài nói thẳng
         rằng phần lớn biến thiên của dòng vốn vẫn KHÔNG GIẢI
         THÍCH ĐƯỢC, và đây là đặc điểm CHUNG của mọi nghiên cứu
         về dòng vốn
```

### Loại dòng vốn nào nhạy cảm nhất

```text
       BẢNG 3 — HỆ SỐ BIẾN GIẢ BẦU CỬ THEO TỪNG LOẠI
       ┌────────────────────┬───────────┬──────────────────────────┐
       │ LOẠI DÒNG VỐN      │ BẦU CỬ    │ SAU BẦU CỬ 1–2 QUÝ       │
       ├────────────────────┼───────────┼──────────────────────────┤
       │ ★★ NỢ              │ −6,08**   │  −0,48 (không ý nghĩa)   │
       │   PHI NỢ           │ −3,84*    │ ★ −0,37**                │
       │ ── theo công cụ ── │           │                          │
       │ ★ FDI              │ −3,60*    │ ★ −0,35**                │
       │ ⚠ DANH MỤC         │  −1,27    │  −0,13 (không ý nghĩa)   │
       │                    │ KHÔNG ý   │                          │
       │ ★ ĐẦU TƯ KHÁC      │ −4,83*    │  −0,40*                  │
       │ ── tổng hợp ──     │           │                          │
       │ DÒNG VÀO gộp       │ −11,5**   │ ★ −0,96**                │
       │ ⚠ DÒNG RA          │  −2,08    │ ★ −0,85***               │
       │                    │ KHÔNG ý   │                          │
       │ DÒNG RÒNG          │ −8,22*    │ −0,00093 (không ý nghĩa) │
       └────────────────────┴───────────┴──────────────────────────┘
       ★★ HAI CÁCH ĐỌC ĐỐI LẬP NHAU
       ① VỀ CÚ SỐC TỨC THỜI: dòng NỢ chịu đòn NẶNG NHẤT (−6,08)
       ② ★ VỀ ĐỘ DAI DẲNG: dòng PHI NỢ (mà chủ yếu là FDI) mới là
          loại KÉO DÀI sang hai quý sau
          → giải thích: nhà đầu tư TRỰC TIẾP đối mặt rủi ro CAO
            HƠN nên THẬN TRỌNG hơn về việc quay lại cho tới khi có
            RÕ RÀNG HƠN về hướng chính sách sau bầu cử
       ★ DÒNG DANH MỤC gần như MIỄN NHIỄM với bất định bầu cử
         → vì chúng có thể ĐẢO NGƯỢC NHANH, nhà đầu tư không cần
           "chờ xem" như với khoản đầu tư khó rút
       ✔ khớp với tài liệu: tác động mạnh nhất ở các hình thức dòng
         vốn KHÓ ĐẢO NGƯỢC (Honig 2020; Julio và Yook 2016)
       ─────────────────────────────────────────────────────────
       ★ VỀ DÒNG RA — MỘT PHÁT HIỆN ĐÁNG CHÚ Ý
       KHÔNG có phản ứng CÙNG THỜI với bầu cử: cả ổn định chính
       trị, bầu cử LẪN tương tác đều KHÔNG có ý nghĩa
       → HAI CÁCH GIẢI THÍCH bài nêu ra
         · nhà đầu tư TRONG NƯỚC đã QUEN với rủi ro chính trị nội
           địa, hoặc ĐỌC ĐƯỢC chúng tốt hơn
         · nhà đầu tư NƯỚC NGOÀI có thông tin HẠN CHẾ về nước chủ
           nhà và được bảo vệ YẾU HƠN dưới thể chế pháp lý và
           chính trị của nước đó (Dixit 2011)
       ★ NHƯNG có điều chỉnh danh mục SAU bầu cử 1–2 quý (−0,85***)
       ⚠ CHINN-ITO chỉ có ý nghĩa với DÒNG RA (0,55**), không với
         dòng vào → kiểm soát vốn ràng buộc người CƯ TRÚ nhiều hơn
       ─────────────────────────────────────────────────────────
       VỀ CÁC YẾU TỐ ĐẨY — VIX
       nợ −3,37*** so với phi nợ −1,14*** → dòng NỢ nhạy hơn GẤP BA
       FDI chỉ −0,58* → ÍT phản ứng nhất với biến động thị trường
       ngắn hạn vì mang tính DÀI HẠN và CHIẾN LƯỢC
       ★ thanh khoản toàn cầu CHỈ có ý nghĩa với dòng NỢ (0,19**)
         → vì chúng thường KỲ HẠN NGẮN, dựa vào huy động bán buôn
           nên chịu RỦI RO ĐẢO NỢ
```

### Bầu cử nào gây bất định lâu nhất

```text
       ❶ BỐN BIẾN TRƯỚC BẦU CỬ — KẾT QUẢ PHẦN LỚN LÀ ÂM TÍNH
       (Bảng 4, đều KHÔNG có tương tác đáng kể với bầu cử)
       BIÊN ĐỘ ĐA SỐ ······· hệ số 2,77* nhưng tương tác 0,63 ns
         → ✔ khớp với tài liệu rằng CHÍNH PHỦ THIỂU SỐ CÓ THỂ ỔN
           ĐỊNH NGANG chính phủ đa số (Thürk và Krauss 2023)
       KIỂM SOÁT VÀ CÂN BẰNG · 0,23 ns, tương tác −0,33 ns
       PHÂN CỰC ············· 0,21 ns, tương tác −0,44 ns
       ⚠ THĂM DÒ THUẬN LỢI ·· −0,32 ns
         → giải thích: thăm dò đáng tin CHỈ CÓ ở khoảng MỘT PHẦN
           BA số cuộc bầu cử trong mẫu các thị trường mới nổi
       ★ trụ cột CHÍNH TRỊ của ICRG có tương tác 0,37* — gợi ý
         rằng sức mạnh lập pháp, kiểm soát cân bằng và trách nhiệm
         giải trình dân chủ CÓ tác dụng đệm
       → KẾT LUẬN PHẦN NÀY: bằng chứng chỉ ở mức THĂM DÒ, và các
         tác động ước lượng NHÌN CHUNG KHIÊM TỐN
       ═══════════════════════════════════════════════════════════
       ❷ ★★ BA ĐẶC ĐIỂM THỰC SỰ QUAN TRỌNG (Bảng 5)
       nguyên tắc chung: điều quyết định KHÔNG phải cú sốc trong
       quý bầu cử, mà là bất định có KÉO DÀI SAU đó hay không
       ┌────────────────┬──────────┬────────────┬────────────────┐
       │ TÌNH HUỐNG     │ QUÝ BẦU  │ SAU 1–2 QUÝ│ SAU 3–4 QUÝ    │
       │                │ CỬ       │            │                │
       ├────────────────┼──────────┼────────────┼────────────────┤
       │ ★ CÓ BẠO LỰC   │ −11,6**  │ ★ −2,20*** │  −0,47 (ns)    │
       │   KHÔNG bạo lực│ −11,5**  │  −0,66 (ns)│  +0,19 (ns)    │
       ├────────────────┼──────────┼────────────┼────────────────┤
       │ ★★ NGOÀI LỊCH  │ −12,4**  │ ★ −3,50*** │ ★ −1,91**      │
       │   THEO lịch    │ −10,5**  │  −0,42 (ns)│  +0,44 (ns)    │
       ├────────────────┼──────────┼────────────┼────────────────┤
       │ ★ ĐƯƠNG NHIỆM  │ −10,5**  │ ★ −1,53**  │ −0,0022 (ns)   │
       │   THUA         │          │            │                │
       │   ĐƯƠNG NHIỆM  │ −7,64*   │  −0,12 (ns)│  +0,25 (ns)    │
       │   THẮNG        │          │            │                │
       └────────────────┴──────────┴────────────┴────────────────┘
       ★★★ ĐỌC BẢNG NÀY THEO CỘT, KHÔNG THEO HÀNG
       trong QUÝ BẦU CỬ, ba cặp gần như KHÔNG KHÁC NHAU (−10 tới
       −12 ở mọi tình huống)
       ★ KHÁC BIỆT NẰM HOÀN TOÀN Ở CÁC QUÝ SAU
         bầu cử "bình thường" — hoà bình, đúng lịch, đương nhiệm
         thắng — có tác động NGẮN NGỦI, GIỚI HẠN trong quý bầu cử
         bầu cử "bất thường" — bạo lực, ngoài lịch, đổi lãnh đạo —
         có tác động KÉO DÀI ÍT NHẤT HAI QUÝ, và với bầu cử ngoài
         lịch thì KÉO TỚI BỐN QUÝ
       ★ ĐÂY CHÍNH LÀ LỜI GIẢI cho mức sụt dai dẳng thấy ở Bảng 2
       ⚠ về bầu cử ngoài lịch: trong mẫu này chúng THƯỜNG được kích
         hoạt bởi BẤT ỔN CHÍNH TRỊ hoặc KHỦNG HOẢNG — chính phủ sụp
         đổ, bỏ phiếu bất tín nhiệm, biểu tình
```

### Định lượng: ai thực sự chịu thiệt

```text
       ★★★ BẢNG 6 — CHỈ NHÓM PHẦN TƯ THẤP NHẤT VỀ ỔN ĐỊNH ICRG
       ┌────────────────────────────┬────────────┬───────────────┐
       │ LOẠI DÒNG VỐN / TÌNH HUỐNG │ THAY ĐỔI   │ THAY ĐỔI      │
       │                            │ TUYỆT ĐỐI  │ TƯƠNG ĐỐI     │
       │                            │ (% GDP xu  │ (so với 6     │
       │                            │  hướng)    │ tháng trước)  │
       ├────────────────────────────┼────────────┼───────────────┤
       │ ★ Dòng vào gộp             │  −1,25     │ ★ −28,3%      │
       │ ★★ Dòng vào RÒNG           │  −1,39     │ ★★ −62,2%     │
       │   Dòng vào PHI NỢ          │  −0,25     │  −11,0%       │
       │ ★ Dòng vào NỢ              │  −0,95     │ ★ −44,8%      │
       │   Dòng vào FDI             │  −0,35     │  −16,4%       │
       │   Đầu tư khác              │  −0,39     │  −30,5%       │
       ├────────────────────────────┼────────────┼───────────────┤
       │   Bầu cử THEO LỊCH         │  −0,25     │  −5,6%        │
       │ ★★ Bầu cử NGOÀI LỊCH       │  −2,15     │ ★★ −48,7%     │
       │ ★★ ĐƯƠNG NHIỆM THUA        │  −2,53     │ ★★ −57,3%     │
       │ ★ ĐƯƠNG NHIỆM THẮNG        │ ★ +0,33    │ ★ +7,6%       │
       └────────────────────────────┴────────────┴───────────────┘
       ★★★ ĐỌC HAI DÒNG CUỐI CÙNG NHAU
       cùng một nước, cùng mức ổn định chính trị thấp, nhưng
       KẾT QUẢ BẦU CỬ quyết định chênh lệch từ −57% tới +8%
       → tức là CHÊNH LỆCH 65 ĐIỂM PHẦN TRĂM chỉ do việc đương
         nhiệm thắng hay thua
       ★ và khi đương nhiệm THẮNG, dòng vốn thậm chí TĂNG NHẸ —
         phù hợp với giả thuyết TÍNH LIÊN TỤC CHÍNH SÁCH làm GIẢM
         bất định và ỔN ĐỊNH dòng vốn
       ═══════════════════════════════════════════════════════════
       ⚠ CHÊNH LỆCH THEO LOẠI DÒNG VỐN CŨNG ĐÁNG CHÚ Ý
       dòng vào GỘP, PHI NỢ và FDI · tác động tiêu cực CHỈ xuất
         hiện ở nhóm phần tư THẤP NHẤT
       ★ dòng RÒNG và dòng NỢ · tác động lan sang CẢ nhóm phần tư
         THỨ HAI
       ★★ khi đương nhiệm thua hoặc bầu cử ngoài lịch, ngay cả
          nhóm phần tư THỨ BA cũng chứng kiến dòng vào giảm
       ═══════════════════════════════════════════════════════════
       ★ KẾT LUẬN QUAN TRỌNG NHẤT VỀ PHÂN HOÁ
       các nước có điểm ổn định chính trị TRÊN MỨC TRUNG BÌNH
       KHÔNG chịu sụt giảm có ý nghĩa thống kê nào quanh bầu cử
       → bất định bầu cử KHÔNG phải vấn đề PHỔ QUÁT; nó là vấn đề
         của CÁC NƯỚC ĐÃ MONG MANH SẴN
```

### Thể chế nào đóng vai trò đệm

```text
       ❶ PHÂN RÃ ICRG THÀNH NĂM TRỤ CỘT (Bảng 7)
       ┌─────────────────────┬───────────┬──────────────────────┐
       │ TRỤ CỘT             │ TÁC ĐỘNG  │ TƯƠNG TÁC VỚI        │
       │                     │ ĐỘC LẬP   │ BẦU CỬ (hiệu ứng đệm)│
       ├─────────────────────┼───────────┼──────────────────────┤
       │ Chính trị (ổn định  │  0,11 ns  │ ★ 0,37*              │
       │ chính phủ, quân đội │           │                      │
       │ trong chính trị,    │           │                      │
       │ trách nhiệm dân chủ)│           │                      │
       │ ★ Điều kiện kinh tế │ 0,99***   │ ★★ 1,01**            │
       │   xã hội            │           │                      │
       │ ★ Rủi ro đầu tư     │ 0,68***   │ ★ 0,83*              │
       │   (thực thi hợp     │           │                      │
       │   đồng, chậm thanh  │           │                      │
       │   toán, hồi hương   │           │                      │
       │   lợi nhuận)        │           │                      │
       │ ⚠ Thể chế (tham     │ 0,085 ns  │ ★ 0,62**             │
       │   nhũng, pháp quyền,│           │                      │
       │   bộ máy)           │           │                      │
       │ ⚠⚠ Căng thẳng và    │ 0,23**    │ ★ 0,14 KHÔNG Ý NGHĨA │
       │    xung đột         │           │                      │
       └─────────────────────┴───────────┴──────────────────────┘
       ★★ HAI DÒNG CUỐI LÀ HAI TRƯỜNG HỢP NGƯỢC NHAU
       ⚠ THỂ CHẾ · KHÔNG có tác động độc lập, NHƯNG CÓ tác dụng
         đệm rõ → chất lượng thể chế chỉ "lộ ra" KHI CÓ BẤT ĐỊNH
       ⚠⚠ CĂNG THẲNG VÀ XUNG ĐỘT · CÓ tác động độc lập NHƯNG
         KHÔNG có tác dụng đệm → đây là YẾU TỐ CẢN TRỞ DAI DẲNG
         với dòng vốn, KHÔNG PHỤ THUỘC vào chu kỳ bầu cử
       ═══════════════════════════════════════════════════════════
       ❷ ĐỐI CHIẾU VỚI CHỈ SỐ QUẢN TRỊ CỦA NGÂN HÀNG THẾ GIỚI
       (Bảng 8 — dùng để kiểm chứng, dù tần suất NĂM nên kém khớp
        với các biến vĩ mô theo quý, đó là lý do ICRG là bộ chính)
       ┌──────────────────────────┬──────────┬─────────────────┐
       │ CHIỀU QUẢN TRỊ           │ ĐỘC LẬP  │ TƯƠNG TÁC       │
       ├──────────────────────────┼──────────┼─────────────────┤
       │ ★ Điểm tổng hợp          │ 0,20***  │ ★ 0,088**       │
       │ ★ Kiểm soát tham nhũng   │ 0,093*** │ ★ 0,064**       │
       │ ★ Hiệu quả chính phủ     │ 0,071**  │ ★ 0,094**       │
       │ ★ Pháp quyền             │ 0,18***  │ ★ 0,078**       │
       │ ★ Chất lượng quản lý     │ 0,12***  │ ★ 0,092**       │
       │ ⚠ Tiếng nói và trách     │ −0,034 ns│  0,058*         │
       │   nhiệm giải trình       │          │                 │
       │ ⚠ Ổn định chính trị và   │ 0,021 ns │  0,049 ns       │
       │   vắng bạo lực           │          │                 │
       └──────────────────────────┴──────────┴─────────────────┘
       ★ BỐN CHIỀU NỔI BẬT: kiểm soát tham nhũng, hiệu quả chính
         phủ, pháp quyền, chất lượng quản lý
       ★★ TÍNH TOÁN TÁC ĐỘNG BIÊN: ở nước có quản trị TRUNG BÌNH
          hoặc TRÊN trung bình, ảnh hưởng ỔN ĐỊNH của thể chế
          MẠNH BÙ ĐẮP HOÀN TOÀN tác động tiêu cực của bất định
          bầu cử; chỉ nhóm phần tư THẤP NHẤT còn dễ tổn thương
       ═══════════════════════════════════════════════════════════
       ★★★ PHÁT HIỆN TINH TẾ NHẤT CỦA CẢ BÀI
       ĐỘ SÂU TÀI CHÍNH có tác động ĐỘC LẬP DƯƠNG rõ rệt lên dòng
       vốn vào, NHƯNG khi tương tác với biến giả bầu cử thì số
       hạng tương tác KHÔNG CÓ Ý NGHĨA
       ┌─────────────────────────────────────────────────────────┐
       │ SO SÁNH HAI LOẠI CÚ SỐC                                 │
       │ CÚ SỐC BẤT ĐỊNH TOÀN CẦU (đo bằng VIX)                  │
       │   → khả năng chống chịu phụ thuộc vào ĐỘ SÂU TÀI CHÍNH  │
       │     TRONG NƯỚC và khả năng hấp thụ cú sốc từ thị trường │
       │     vốn quốc tế (Carrière-Swallow và Céspedes 2013: khi │
       │     thanh khoản toàn cầu thắt chặt, nước có hệ thống    │
       │     tài chính NÔNG gặp ràng buộc tín dụng khuếch đại    │
       │     mức co hẹp đầu tư)                                  │
       │ ★ CÚ SỐC BẤT ĐỊNH CHÍNH TRỊ TRONG NƯỚC                  │
       │   → độ sâu tài chính KHÔNG ĐỦ để chống đỡ               │
       │   → chỉ KHUNG THỂ CHẾ MẠNH mới trấn an được nhà đầu tư  │
       │ ★★ VÌ SAO KHÁC NHAU: bầu cử tạo bất định về HƯỚNG CHÍNH  │
       │    SÁCH DÀI HẠN, làm xói mòn niềm tin nhà đầu tư. Trong │
       │    bối cảnh đó, khung thể chế mạnh mang lại sự trấn an  │
       │    BÙ ĐẮP PHẦN NÀO cho việc thiếu rõ ràng về chính sách │
       └─────────────────────────────────────────────────────────┘
```

### Kiểm chứng độ vững

```text
       ❶ ★ THƯỚC ĐO BẤT ĐỊNH THAY THẾ (Bảng 9)
       CHỈ SỐ BẤT ĐỊNH THẾ GIỚI (WUI) · đếm tần suất từ "bất định"
         trong báo cáo quốc gia của Economist Intelligence Unit
       CHỈ SỐ BẤT ĐỊNH CHÍNH SÁCH KINH TẾ (EPU) · tỷ lệ bài báo
         đồng thời nhắc tới kinh tế, chính sách và bất định
       ★★ KẾT QUẢ: qua BẢY đặc tả, CẢ hệ số của WUI LẪN tương tác
          của nó với bầu cử đều KHÔNG CÓ Ý NGHĨA, trong khi các
          biến liên quan bầu cử VẪN VỮNG
       → bất định liên quan bầu cử, nhất là khi ĐIỀU KIỆN HOÁ theo
         ổn định chính trị, đóng vai trò RIÊNG BIỆT VÀ VỮNG, VƯỢT
         RA NGOÀI những gì các thước đo bất định cấp quốc gia rộng
         hơn nắm bắt được
       ⚠ hạn chế của EPU: chỉ có cho 8 trong 38 nước, nên phải
         dùng chỉ số TOÀN CẦU (bình quân gia quyền GDP của 18 nước)
       ═══════════════════════════════════════════════════════════
       ❷ ⚠ KHÔNG CÓ "PHẦN THƯỞNG DÂN CHỦ" (Bảng 10)
       thử bốn thước đo: điểm Polity (−10 tới +10), thay đổi Polity
       hàng năm, chỉ số cạnh tranh bầu cử liên tục của DPI (1 tới
       7), và biến nhị phân từ chỉ số đó
       ★ TẤT CẢ đều KHÔNG CÓ Ý NGHĨA, trong khi bất định bầu cử
         VẪN là yếu tố tiêu cực
       → nước dân chủ hơn KHÔNG thu hút nhiều vốn hơn và cũng
         KHÔNG ít nhạy cảm hơn với bất định bầu cử
       ═══════════════════════════════════════════════════════════
       ❸ MƯỜI MỘT ĐẶC TẢ THAY THẾ (Bảng 11)
       ① chia theo GDP QUÝ thay vì GDP xu hướng
          ★ khác biệt DUY NHẤT: tác động tiêu cực nay XUẤT HIỆN CẢ
            ở HAI QUÝ TRƯỚC bầu cử
       ②–④ bỏ xu hướng thời gian theo nước · thêm xu hướng chung ·
          hiệu ứng cố định năm → kết luận KHÔNG ĐỔI
       ⑤ loại năm 2020 (COVID) · ⑥ thêm biến giả khủng hoảng tài
          chính toàn cầu → biến giả KHÔNG có ý nghĩa, có lẽ vì căng
          thẳng giai đoạn đó đã được VIX nắm bắt
       ⑦–⑧ ★ THÊM BIẾN GIẢ BẦU CỬ HOA KỲ (như một yếu tố đẩy)
          → KHÔNG có quan hệ có ý nghĩa nào, trong khi hệ số bầu
            cử TRONG NƯỚC vẫn âm và có ý nghĩa
          ★★ bất định chính trị TRONG NƯỚC tác động MẠNH HƠN bất
             định chính trị ở Hoa Kỳ — có thể vì nhà đầu tư nhạy
             cảm hơn với bất định ở các nước mới nổi nơi khung thể
             chế YẾU HƠN
          ⚠ đối chiếu: Julio và Yook (2016) cho thấy nếu CHỈ nhìn
            nhà đầu tư MỸ thì FDI của họ ra nước ngoài GIẢM MẠNH
            trong quý trước bầu cử Mỹ
       ⑨ thêm bình quân chéo theo quý của dòng vốn (đại diện cho
          yếu tố toàn cầu không quan sát được)
       ⑩ hiệu ứng cố định năm-vùng (bốn vùng)
       ⑪ ★ MẪU CON CHỈ GỒM BẦU CỬ THEO LỊCH ĐỊNH SẴN
          → kết luận về sụt giảm trong quý bầu cử và tác dụng đệm
            của ổn định chính trị ĐƯỢC XÁC NHẬN
          → nhất quán với giả định thời điểm bầu cử là NGOẠI SINH
```

## Ba câu hỏi bài viết trả lời

1. Bất định chính trị có ảnh hưởng tới dòng vốn quốc tế vào các thị trường mới nổi không, và ở giai đoạn nào của chu kỳ bầu cử?
2. Loại dòng vốn nào nhạy cảm nhất, và vì sao?
3. Điều gì làm dịu hoặc khuếch đại tác động đó?

## Khái niệm cần biết

**Bất định chính trị và giá trị của việc chờ (political uncertainty, option value of waiting).** Bất định chính trị là việc nhà đầu tư không biết chính sách sẽ đi về đâu sau một sự kiện chính trị. Theo Bernanke (1983), khi một khoản đầu tư khó rút lại và tương lai chưa rõ, việc chờ thêm thông tin có giá trị, nên người ta hoãn đầu tư. Ví dụ minh hoạ: một công ty định xây nhà máy 100 triệu USD ở một nước sắp bầu cử, nếu ứng viên đối lập có thể đổi luật thuế, công ty sẽ chờ qua bầu cử rồi mới quyết, dù cuối cùng luật không đổi. Đây là cơ chế giải thích vì sao dòng vốn giảm quanh bầu cử ngay cả khi chính sách không thay đổi.

**Yếu tố đẩy và yếu tố kéo (push / pull factors).** Yếu tố đẩy là điều kiện bên ngoài đẩy vốn vào hay ra khỏi các nước mới nổi, như mức ngại rủi ro toàn cầu (đo bằng chỉ số VIX) hay thanh khoản toàn cầu. Yếu tố kéo là đặc điểm của chính nước nhận vốn, như tăng trưởng, độ sâu tài chính, chất lượng thể chế. Ví dụ trong bài: VIX tăng làm dòng vốn vào giảm (yếu tố đẩy); chênh lệch tăng trưởng so với nước phát triển cao hơn làm dòng vốn vào tăng (yếu tố kéo). Bài đặt bất định bầu cử vào khung này như một yếu tố kéo mới.

**Dòng vốn tư nhân vào gộp (gross private inflows).** Tiền mà nhà đầu tư nước ngoài (không phải chính phủ hay ngân hàng trung ương) đưa vào một nước, chưa trừ đi tiền người trong nước đưa ra. Ví dụ minh hoạ: trong một quý, nhà đầu tư nước ngoài mua 5 tỷ USD tài sản trong nước, người trong nước mua 2 tỷ USD tài sản nước ngoài, thì dòng vào gộp là 5, dòng ra gộp là 2, dòng ròng là 3 tỷ USD. Đây là biến kết quả chính của bài, vì bất định chính trị tác động mạnh nhất lên nhà đầu tư nước ngoài, và dòng ròng có thể che mất các biến động lớn của hai chiều.

**GDP xu hướng (trend GDP).** Mức GDP "bình thường" sau khi đã loại các dao động ngắn hạn, thường tính bằng bộ lọc Hodrick–Prescott (lọc HP). Ví dụ minh hoạ: nếu GDP xu hướng của một nước là 100 tỷ USD mỗi quý mà dòng vốn vào là 5 tỷ thì dòng vốn bằng 5% GDP xu hướng. Bài chia dòng vốn cho GDP xu hướng chứ không cho GDP thực tế, để mẫu số không nhảy theo chính chu kỳ kinh tế quanh bầu cử.

**Biến giả và số hạng tương tác (dummy variable, interaction term).** Biến giả bằng 1 khi một sự kiện xảy ra (ở đây là quý có bầu cử) và bằng 0 khi không. Số hạng tương tác là tích của hai biến, cho phép tác động của biến này thay đổi theo mức của biến kia. Ví dụ minh hoạ từ hệ số của bài: tác động của bầu cử bằng −11,5 cộng 0,18 nhân điểm ổn định chính trị; ở nước có điểm 50, tác động là −11,5 + 9 = −2,5 điểm phần trăm GDP xu hướng; ở nước có điểm 70, tác động là −11,5 + 12,6 = +1,1. Toàn bộ kết quả trọng tâm của bài nằm ở số hạng tương tác này.

**Chỉ số ICRG.** Hướng dẫn Rủi ro Quốc gia Quốc tế (International Country Risk Guide), chấm điểm rủi ro chính trị của mỗi nước trên thang 0–100 từ 12 biến, nhóm thành năm trụ cột: chính trị, điều kiện kinh tế xã hội, rủi ro đầu tư, thể chế, căng thẳng và xung đột. Điểm càng cao thì càng ổn định. Bài dùng ICRG làm thước đo ổn định chính trị chính vì nó có tần suất cao hơn các bộ chỉ số theo năm, nên khớp được với số liệu dòng vốn theo quý.

**Nội sinh và biến công cụ (endogeneity, instrumental variable).** Một biến là nội sinh khi chính nó chịu ảnh hưởng của kết quả hoặc cùng chịu một nguyên nhân ẩn với kết quả, khiến ước lượng bị chệch. Biến công cụ là một biến ảnh hưởng tới biến cần nghiên cứu nhưng không ảnh hưởng trực tiếp tới kết quả. Ví dụ trong bài: thời gian kể từ lần bầu cử trước dự báo được khả năng sắp có bầu cử (nhiệm kỳ khoảng 4 năm thì sau 15–16 quý gần như chắc có bầu cử), nhưng tự nó không làm dòng vốn thay đổi. Bài dùng công cụ này để kiểm tra rằng thời điểm bầu cử không bị chính điều kiện kinh tế quyết định.

**Phần tư (tứ phân vị, quartile).** Chia các nước thành bốn nhóm bằng nhau theo một tiêu chí. Ví dụ: xếp các nước theo điểm ổn định chính trị, một phần tư nước có điểm thấp nhất là "nhóm phần tư thấp nhất". Kết quả định lượng chính của bài (dòng vốn vào giảm 28% trong quý bầu cử) là của nhóm này, còn nhóm trên mức trung bình không chịu tác động có ý nghĩa.

## Nội dung chi tiết

### 1. Vấn đề và cách tiếp cận

Tài liệu về dòng vốn nói chung rất phong phú, nhưng quan hệ giữa dòng vốn quốc tế và bất định chính trị ở các nền kinh tế mới nổi cho tới nay nhận được rất ít chú ý. Bầu cử là ví dụ điển hình của một giai đoạn bất định gia tăng làm mờ triển vọng. Ngay cả khi không có khủng hoảng hay đảo lộn chính trị lớn, bầu cử vẫn định kỳ mở ra khả năng thay đổi chưa biết trước trong môi trường kinh tế, thể chế và quản lý.

**Lập luận trung tâm.** Không chỉ những thay đổi chính sách cuối cùng mới quan trọng; chính sự bất định quanh những thay đổi có thể xảy ra, bất kể chúng có thành hiện thực hay không, đã đủ ảnh hưởng tới hành vi nhà đầu tư (Ahir và cộng sự 2022). Điều này có thể khiến nhà đầu tư, ít nhất tạm thời, rút khỏi hoặc giảm phơi nhiễm với thị trường nội địa trước, trong và ngay sau khi bỏ phiếu (Julio và Yook 2016).

**Nền tảng lý thuyết.** Bài dựa trên Bernanke (1983) về đầu tư dưới bất định: bất định về hàm ý dài hạn của một sự kiện có thể làm trì hoãn quyết định đầu tư, vì chủ thể kinh tế định giá cho việc chờ thêm thông tin. Khung này áp dụng được cho cả doanh nghiệp quyết định xây nhà máy lẫn nhà đầu tư quyết định phân bổ vốn giữa các nước.

**Vì sao bầu cử là "thí nghiệm tự nhiên gần đúng".** Thời điểm bầu cử thường được ấn định trước bởi hiến pháp, không chịu ảnh hưởng của một nhà đầu tư cụ thể hay của môi trường kinh tế lúc đó, và lặp lại theo chu kỳ đều đặn. Vì vậy so sánh dòng vốn trong quý bầu cử với các quý khác giúp tách tác động của bất định chính trị khỏi các động lực vĩ mô rộng hơn.

**Mối lo về nội sinh.** Bài thẳng thắn thừa nhận vấn đề. Theo tài liệu chu kỳ kinh doanh chính trị kinh điển từ Nordhaus (1975), người đương nhiệm cơ hội có thể tung kích thích tài khoá và tiền tệ trước bầu cử để đẩy tăng trưởng ngắn hạn và tăng khả năng tái đắc cử. Nếu vậy, bầu cử có thể tác động tới kết quả vĩ mô một cách trực tiếp, độc lập với bất định, và hệ số đo được không còn là tác động của bất định thuần tuý. Bài xử lý bằng năm cách:

1. **Biến công cụ:** dùng thời gian kể từ lần bầu cử trước làm công cụ, vì đây là một biến dự báo mang tính cơ học cho xác suất sắp có bầu cử. Kiểm định Durbin–Wu–Hausman không bác bỏ giả thuyết rằng biến bầu cử là ngoại sinh, nên coi bầu cử là ngoại sinh là phù hợp về mặt thống kê.
2. **Nhân quả Granger:** bầu cử giúp dự báo dòng vốn (bầu cử "Granger-gây ra" dòng vốn), nhưng dòng vốn không giúp dự báo bầu cử.
3. **Hồi quy giả dược với biến dẫn:** đưa biến bầu cử của các quý tương lai vào hồi quy; nếu chúng có "tác động" thì có vấn đề.
4. **Mô hình logit về thời điểm bầu cử:** kiểm tra xem điều kiện kinh tế có dự báo được thời điểm bầu cử hay không.
5. **Mẫu con chỉ gồm bầu cử theo lịch định sẵn**, chiếm 80% mẫu.

### 2. Dữ liệu

**Mẫu.** Dữ liệu theo quý cho 38 nền kinh tế mới nổi ở mọi khu vực, giai đoạn 1990–2020. Mẫu dừng ở 2020 vì các cơ sở dữ liệu biến chính trị cập nhật rất chậm. Trung Quốc, một nước nhận vốn quan trọng, không có trong mẫu vì thiếu dữ liệu ngày bầu cử trong cả hai nguồn DPI và NELDA.

**Xử lý dữ liệu dòng vốn.** Dòng vốn lấy từ cơ sở dữ liệu Thống kê Cán cân Thanh toán của IMF và được xử lý qua ba bước:

1. **Chuẩn hoá theo GDP xu hướng.** Bài ước GDP theo quý từ số liệu năm của Triển vọng Kinh tế Thế giới, rồi áp lọc HP để lấy xu hướng. Bài thêm hai năm dữ liệu sau điểm cuối mẫu để giảm chệch đầu mút (bộ lọc HP thường ước lượng kém ở hai đầu chuỗi).
2. **Tách dòng vốn chính thức khỏi dòng vốn tư nhân.** Đây là bước quan trọng nhất. Ở phía dòng vào, bài trừ đi nợ của ngân hàng trung ương và chính phủ với người không cư trú, cùng các khoản phân bổ quyền rút vốn đặc biệt (SDR) của IMF. Ở phía dòng ra, bài trừ đi tài sản tài chính do ngân hàng trung ương và chính phủ mua. Lý do: chủ nợ chính thức (như IMF hay các ngân hàng trung ương khác) có thể được huy động để ngăn khủng hoảng bằng cách bù đắp đúng phần vốn tư nhân chảy ra; nếu để chung, điều đó sẽ triệt tiêu chính tác động bất định mà bài muốn đo.
3. **Tập trung vào dòng vào gộp**, vì dòng ròng che giấu biến động lớn trong giao dịch của người cư trú và người không cư trú, và vì bất định chính trị nhiều khả năng được cảm nhận mạnh hơn bởi nhà đầu tư nước ngoài so với nhà đầu tư trong nước.

**Dữ liệu bầu cử.** Lấy chủ yếu từ Cơ sở dữ liệu Thể chế Chính trị (DPI), bổ sung bằng Bộ dữ liệu Bầu cử Quốc gia trong Chế độ Dân chủ và Chuyên chế (NELDA). Với nước theo chế độ nghị viện, bài dùng bầu cử lập pháp; với nước theo chế độ tổng thống, dùng bầu cử người đứng đầu hành pháp. Loại bầu cử được xác định theo hệ thống chính trị của nước đó trong từng quý.

**Diễn biến dòng vốn trong mẫu.**

- Dòng vào đạt đỉnh trước khủng hoảng tài chính toàn cầu, trên 10% GDP quý xu hướng, và sau đó không trở lại mức này.
- Dòng ra tăng từ dưới 1% GDP trong thập niên 1990 lên trên 3% trong thập kỷ gần đây, nên khoảng cách giữa dòng vào và dòng ra thu hẹp dần. Điều này phản ánh sự nổi lên của nhà đầu tư tổ chức (quỹ hưu trí, bảo hiểm) ở các thị trường mới nổi và quá trình tự do hoá tài khoản vốn từng bước.
- Về cơ cấu, FDI là cấu phần lớn nhất và ổn định ở khoảng 2% GDP suốt 25 năm, kể cả trong COVID.
- Năm 2007, dòng vốn qua khu vực ngân hàng chiếm gần một nửa tổng dòng vào, rồi sụp đổ khi thanh khoản toàn cầu thắt chặt, chủ yếu do các khoản cho vay ngân hàng ngắn hạn bị rút về.

**Đặc điểm của 261 cuộc bầu cử trong mẫu:**

| Đặc điểm | Giá trị bình quân | Độ lệch chuẩn |
|---|---|---|
| Độ dài nhiệm kỳ | 15,6 quý (khoảng 4 năm) | 4,6 |
| Biên độ đa số (tỷ lệ ghế phe chính phủ nắm) | 57,3% | 16,5 |
| Tỷ lệ chủ thể phủ quyết rời bỏ vị trí | 14,3% | 28,5 |
| Phân cực (thang 0–2) | 0,6 | 0,8 |

| Tỷ lệ các cuộc bầu cử có đặc điểm | |
|---|---|
| Có thăm dò đáng tin và thuận lợi cho đương nhiệm | 34,5% |
| Có bạo lực gây chết người dân thường | 25,7% |
| Không theo lịch định sẵn | 19,9% |
| Đương nhiệm thua | 58,2% |

### 3. Phương pháp

Bài dùng khung yếu tố đẩy và kéo chuẩn của tài liệu dòng vốn, mở rộng để đưa thêm bất định chính trị. Biến phụ thuộc là dòng vốn tư nhân vào gộp tính theo phần trăm GDP xu hướng. Mô hình cho phép mỗi nước có hệ số chặn riêng và xu hướng thời gian riêng.

Về sai số chuẩn, bài lập luận rằng dòng vốn chịu nhiều yếu tố chung không quan sát được và có hiệu ứng lây lan giữa các nước, nên sai số của các nước trong cùng một quý nhiều khả năng tương quan với nhau. Kiểm định phụ thuộc chéo của Pesaran xác nhận điều này, nên bài dùng sai số chuẩn hiệu chỉnh theo Driscoll và Kraay, vốn tính tới cả phụ thuộc chéo lẫn tự tương quan.

### 4. Kết quả cơ sở

Kết quả cho dòng vốn tư nhân vào gộp (% GDP xu hướng):

| Biến | Đặc tả cơ sở | Đặc tả đầy đủ (có tương tác) |
|---|---|---|
| VIX (log) | −4,24 (\*\*\*) | −4,47 (\*\*\*) |
| Thanh khoản toàn cầu | +0,23 (\*\*) | +0,24 (\*\*) |
| Chênh lệch lãi suất thực | −0,043 (không có ý nghĩa) | −0,055 (không có ý nghĩa) |
| Chênh lệch tăng trưởng | +0,38 (\*\*\*) | +0,42 (\*\*\*) |
| Phát triển thị trường tài chính | +7,70 (\*\*) | +10,4 (\*\*) |
| Chỉ số Chinn–Ito (độ mở tài khoản vốn) | +0,33 (không có ý nghĩa) | +0,44 (không có ý nghĩa) |
| Ổn định chính trị ICRG | +0,20 (\*\*\*) | +0,19 (\*\*\*) |
| Bầu cử (đứng một mình) | +0,64 (không có ý nghĩa) | |
| Bầu cử (khi có tương tác) | | −11,5 (\*\*) |
| Bầu cử × Ổn định chính trị ICRG | | +0,18 (\*\*) |
| Trước bầu cử 3–4 quý | | +0,61 |
| Trước bầu cử 1–2 quý | | −0,53 |
| Sau bầu cử 1–2 quý | | −0,96 (\*\*) |
| Sau bầu cử 3–4 quý | | +0,043 |

**Yếu tố đẩy.** Mức ngại rủi ro toàn cầu tăng (VIX cao) cản trở mạnh dòng vốn tư nhân vào các nền kinh tế mới nổi, còn thanh khoản toàn cầu dồi dào đẩy vốn vào.

**Yếu tố kéo.** Chênh lệch tăng trưởng so với nước phát triển là động lực vững. Chênh lệch lãi suất thực không có ý nghĩa thống kê; bài lưu ý rằng các nghiên cứu trước cũng chưa thống nhất về vai trò của yếu tố này. Phát triển thị trường tài chính có tác động dương. Độ mở tài khoản vốn đo bằng chỉ số Chinn–Ito không có ý nghĩa.

**Cấu trúc kết quả về bầu cử, phần quan trọng nhất của bài.** Khi đứng một mình, biến giả quý bầu cử không có ý nghĩa (+0,64). Nhưng khi đưa vào cùng lúc chỉ số ổn định chính trị và số hạng tương tác giữa hai biến, cả ba đều có ý nghĩa thống kê. Cách đọc:

- Bầu cử đúng là đi kèm tác động tiêu cực lên dòng vốn trong quý diễn ra (−11,5 là tác động tính tại mức ổn định bằng 0).
- Ổn định chính trị có tác động dương độc lập (+0,19).
- Tác động tiêu cực của bầu cử được làm dịu ở nước ổn định hơn: mỗi điểm ổn định thêm giảm tác động âm đi 0,18.

Vì tác động âm ở nước kém ổn định và tác động gần bằng không ở nước ổn định cộng lại, hiệu ứng trung bình bị triệt tiêu và không nhìn thấy được nếu không tách ra theo mức ổn định.

**Thời điểm.** Không có sụt giảm có ý nghĩa trong giai đoạn chạy đà trước bầu cử (hệ số của 3–4 quý và 1–2 quý trước đều không có ý nghĩa). Cú sốc rơi vào quý bầu cử và một đến hai quý sau đó (−0,96).

**Mức giải thích hạn chế.** R bình phương trong nhóm chỉ 0,19–0,23. Bài nói thẳng rằng dù các biến có ý nghĩa và mô hình có hiệu ứng cố định, phần lớn biến thiên của dòng vốn vẫn không giải thích được, và đây là đặc điểm chung của mọi nghiên cứu về dòng vốn.

### 5. Phân tách theo loại dòng vốn

Hệ số của biến giả bầu cử khi tách theo loại dòng vốn:

| Loại dòng vốn | Quý bầu cử | Sau bầu cử 1–2 quý |
|---|---|---|
| Nợ | −6,08 (\*\*) | −0,48 (không có ý nghĩa) |
| Phi nợ | −3,84 (\*) | −0,37 (\*\*) |
| FDI | −3,60 (\*) | −0,35 (\*\*) |
| Danh mục | −1,27 (không có ý nghĩa) | −0,13 (không có ý nghĩa) |
| Đầu tư khác | −4,83 (\*) | −0,40 (\*) |
| Dòng vào gộp | −11,5 (\*\*) | −0,96 (\*\*) |
| Dòng ra | −2,08 (không có ý nghĩa) | −0,85 (\*\*\*) |
| Dòng ròng | −8,22 (\*) | −0,00093 (không có ý nghĩa) |

**Yếu tố đẩy khác nhau theo loại dòng vốn.** Việc tách dòng vào thành nợ và phi nợ không đổi chiều hay ý nghĩa của các yếu tố đẩy và kéo, nhưng đổi tầm quan trọng tương đối. Hệ số của VIX với dòng nợ là −3,37 (\*\*\*), so với −1,14 (\*\*\*) với dòng phi nợ: dòng nợ nhạy gấp ba, phản ánh việc chúng nhạy với thay đổi niềm tin thị trường và chênh lệch lợi suất, và dễ bị lây lan. FDI chỉ có hệ số −0,58 (\*), ít phản ứng nhất với biến động thị trường ngắn hạn vì mang tính dài hạn và chiến lược. Thanh khoản toàn cầu chỉ có ý nghĩa với dòng nợ (0,19, \*\*), điều không lạ vì dòng nợ thường kỳ hạn ngắn và dựa vào huy động vốn bán buôn, nên chịu rủi ro đảo nợ.

**Tác động của bầu cử: hai cách đọc đối lập.**

- **Về cú sốc tức thời,** dòng nợ chịu đòn nặng nhất trong quý bầu cử (−6,08), với mức ý nghĩa cao hơn dòng phi nợ.
- **Về độ dai dẳng,** dòng phi nợ, mà FDI là cấu phần chính, mới là loại kéo dài sang hai quý sau (FDI −0,35 sau 1–2 quý). Bài giải thích rằng nhà đầu tư trực tiếp đối mặt rủi ro cao hơn nên thận trọng hơn về việc quay lại cho tới khi hướng chính sách sau bầu cử rõ ràng hơn.

**Dòng danh mục gần như miễn nhiễm với bất định bầu cử** (−1,27, không có ý nghĩa). Vì dòng danh mục có thể đảo ngược nhanh (bán cổ phiếu, trái phiếu trong vài ngày), nhà đầu tư không cần "chờ xem" như với khoản đầu tư khó rút. Kết quả này khớp với tài liệu rằng tác động mạnh nhất rơi vào các hình thức dòng vốn khó đảo ngược như FDI (Honig 2020; Julio và Yook 2016). Với đầu tư khác (chủ yếu là vay ngân hàng), mức giảm trong quý bầu cử nhiều khả năng gắn với việc doanh nghiệp tư nhân đầu tư ít hơn quanh bầu cử nên cần vay ít hơn.

**Dòng ra: không phản ứng cùng thời với bầu cử.** Cả ổn định chính trị, bầu cử lẫn tương tác của chúng đều không có ý nghĩa với dòng ra. Bài nêu hai cách giải thích:

- Nhà đầu tư trong nước đã quen với rủi ro chính trị nội địa, hoặc đọc được chúng tốt hơn.
- Nhà đầu tư nước ngoài có thông tin hạn chế về nước chủ nhà và được bảo vệ yếu hơn dưới thể chế pháp lý và chính trị của nước đó (Dixit 2011), nên dễ tổn thương hơn trước bất định chính sách và phản ứng mạnh hơn.

Dù vậy, nhà đầu tư trong nước có điều chỉnh danh mục một đến hai quý sau bầu cử (−0,85, \*\*\*). Đáng chú ý là chỉ số Chinn–Ito chỉ có ý nghĩa với dòng ra (0,55, \*\*), không với dòng vào: kiểm soát vốn ràng buộc người cư trú muốn đưa tiền ra nhiều hơn là người nước ngoài muốn đưa tiền vào.

**Dòng ròng** có hình mẫu khá sát dòng vào gộp, vì ở các thị trường mới nổi dòng ròng chủ yếu do dòng vào chi phối. Nhưng ý nghĩa thống kê của các biến chính trị yếu hơn, có lẽ vì tác động bị pha loãng bởi dòng ra.

### 6. Đặc điểm bầu cử

**Bốn biến về bối cảnh trước bầu cử cho kết quả phần lớn là âm tính**, tức không biến nào có tương tác đáng kể với bầu cử:

| Biến | Hệ số độc lập | Tương tác với bầu cử |
|---|---|---|
| Biên độ đa số | 2,77 (\*) | 0,63 (không có ý nghĩa) |
| Kiểm soát và cân bằng | 0,23 (không có ý nghĩa) | −0,33 (không có ý nghĩa) |
| Phân cực | 0,21 (không có ý nghĩa) | −0,44 (không có ý nghĩa) |
| Thăm dò thuận lợi cho đương nhiệm | | −0,32 (không có ý nghĩa) |

Biên độ đa số có hệ số dương yếu nhưng không có tác động khác biệt trong giai đoạn bầu cử; bài cho rằng điều này khớp với tài liệu cho thấy chính phủ thiểu số có thể ổn định ngang chính phủ đa số (Thürk và Krauss 2023). Với thăm dò, một cách giải thích là thăm dò đáng tin chỉ có ở khoảng một phần ba số cuộc bầu cử trong mẫu các thị trường mới nổi. Trụ cột chính trị của ICRG có tương tác 0,37 (\*), gợi ý rằng sức mạnh lập pháp, kiểm soát và cân bằng, trách nhiệm giải trình dân chủ có tác dụng đệm nhất định. Bài kết luận thẳng thắn: bằng chứng ở phần này chỉ ở mức thăm dò, và các tác động ước lượng nhìn chung khiêm tốn.

**Ba đặc điểm thực sự quan trọng.** Nguyên tắc chung: điều quyết định không phải cú sốc trong quý bầu cử, mà là bất định có kéo dài sau đó hay không.

| Tình huống | Quý bầu cử | Sau 1–2 quý | Sau 3–4 quý |
|---|---|---|---|
| Có bạo lực | −11,6 (\*\*) | −2,20 (\*\*\*) | −0,47 (không có ý nghĩa) |
| Không bạo lực | −11,5 (\*\*) | −0,66 (không có ý nghĩa) | +0,19 (không có ý nghĩa) |
| Ngoài lịch | −12,4 (\*\*) | −3,50 (\*\*\*) | −1,91 (\*\*) |
| Theo lịch | −10,5 (\*\*) | −0,42 (không có ý nghĩa) | +0,44 (không có ý nghĩa) |
| Đương nhiệm thua | −10,5 (\*\*) | −1,53 (\*\*) | −0,0022 (không có ý nghĩa) |
| Đương nhiệm thắng | −7,64 (\*) | −0,12 (không có ý nghĩa) | +0,25 (không có ý nghĩa) |

Bảng này nên đọc theo cột chứ không theo hàng. Trong quý bầu cử, các cặp gần như không khác nhau: mọi tình huống đều nằm trong khoảng −10 tới −12 (riêng đương nhiệm thắng nhỏ hơn, −7,64). Khác biệt nằm hoàn toàn ở các quý sau:

- **Bạo lực bầu cử:** cả hai loại đều đi kèm dòng vốn thấp hơn trong quý bầu cử, nhưng bầu cử có bạo lực để lại tác động âm kéo dài một đến hai quý sau, còn bầu cử hoà bình thì tác động ngắn ngủi, giới hạn trong quý bầu cử.
- **Thời điểm bầu cử:** khoảng 80% bầu cử diễn ra theo ngày định sẵn. Hệ số của bầu cử ngoài lịch nhỉnh hơn một chút so với theo lịch, gợi ý nhà đầu tư thận trọng hơn. Quan trọng hơn, với bầu cử ngoài lịch, tác động âm có ý nghĩa kéo dài tới bốn quý sau. Lưu ý: trong mẫu này, bầu cử ngoài lịch thường được kích hoạt bởi bất ổn chính trị hoặc khủng hoảng: chính phủ sụp đổ, bỏ phiếu bất tín nhiệm, biểu tình.
- **Kết quả bầu cử:** khi đương nhiệm thua, tác động âm và có ý nghĩa cả trong quý bầu cử lẫn một đến hai quý sau. Khi đương nhiệm giữ được quyền lực, tác động nhỏ hơn và ngắn ngủi. Điều này nhất quán với giả thuyết rằng tính liên tục chính sách làm giảm bất định và ổn định dòng vốn.

Tóm lại, bầu cử "bình thường" (hoà bình, đúng lịch, đương nhiệm thắng) chỉ có tác động ngắn ngủi trong quý bầu cử; bầu cử "bất thường" (bạo lực, ngoài lịch, đổi lãnh đạo) có tác động kéo dài ít nhất hai quý, và với bầu cử ngoài lịch thì tới bốn quý. Đây chính là lời giải cho mức sụt dai dẳng một đến hai quý sau bầu cử thấy ở kết quả cơ sở.

### 7. Định lượng

Bài quy các hệ số ra tác động cụ thể cho nhóm phần tư thấp nhất về ổn định chính trị ICRG. Thay đổi tương đối được tính so với mức dòng vốn trong 6 tháng (hai quý) trước bầu cử.

| Loại dòng vốn hoặc tình huống | Thay đổi tuyệt đối (% GDP xu hướng) | Thay đổi tương đối |
|---|---|---|
| Dòng vào gộp | −1,25 | −28,3% |
| Dòng vào ròng | −1,39 | −62,2% |
| Dòng vào phi nợ | −0,25 | −11,0% |
| Dòng vào nợ | −0,95 | −44,8% |
| Dòng vào FDI | −0,35 | −16,4% |
| Đầu tư khác | −0,39 | −30,5% |
| Bầu cử theo lịch | −0,25 | −5,6% |
| Bầu cử ngoài lịch | −2,15 | −48,7% |
| Đương nhiệm thua | −2,53 | −57,3% |
| Đương nhiệm thắng | +0,33 | +7,6% |

**Đọc bảng.**

- Ở nhóm kém ổn định nhất, dòng vào gộp giảm 1,25% GDP xu hướng trong quý bầu cử, tức khoảng 28% so với mức của hai quý trước.
- Tác động mạnh nhất khi đương nhiệm thua hoặc bầu cử ngoài lịch, những tình huống thường gắn với bất định cao: dòng vào giảm khoảng một nửa (−57,3% và −48,7%).
- Hai dòng cuối cần đọc cùng nhau. Cùng một nhóm nước, cùng mức ổn định chính trị thấp, nhưng kết quả bầu cử quyết định chênh lệch từ khoảng −57% tới khoảng +8%, tức chênh lệch khoảng 65 điểm phần trăm chỉ do việc đương nhiệm thắng hay thua. Khi đương nhiệm thắng, dòng vốn thậm chí tăng nhẹ, phù hợp với giả thuyết tính liên tục chính sách.

**Phạm vi lan sang các nhóm khác.** Với dòng vào gộp, dòng phi nợ và FDI, tác động tiêu cực chỉ xuất hiện ở nhóm phần tư thấp nhất. Với dòng ròng và dòng nợ, tác động lan sang cả nhóm phần tư thứ hai. Khi đương nhiệm thua hoặc bầu cử ngoài lịch, ngay cả nhóm phần tư thứ ba cũng chứng kiến dòng vào giảm.

**Kết luận quan trọng nhất về phân hoá:** các nước có điểm ổn định chính trị trên mức trung bình không chịu sụt giảm có ý nghĩa thống kê nào quanh bầu cử. Bất định bầu cử không phải vấn đề chung của mọi nước mới nổi; nó là vấn đề của các nước vốn đã mong manh.

### 8. Vai trò của năng lực thể chế

**Phân rã ICRG thành năm trụ cột.**

| Trụ cột | Nội dung | Tác động độc lập | Tương tác với bầu cử (hiệu ứng đệm) |
|---|---|---|---|
| Chính trị | Ổn định chính phủ, vai trò quân đội trong chính trị, trách nhiệm giải trình dân chủ | 0,11 (không có ý nghĩa) | 0,37 (\*) |
| Điều kiện kinh tế xã hội | | 0,99 (\*\*\*) | 1,01 (\*\*) |
| Rủi ro đầu tư | Thực thi hợp đồng, chậm thanh toán, hồi hương lợi nhuận | 0,68 (\*\*\*) | 0,83 (\*) |
| Thể chế | Tham nhũng, pháp quyền, chất lượng bộ máy hành chính | 0,085 (không có ý nghĩa) | 0,62 (\*\*) |
| Căng thẳng và xung đột | | 0,23 (\*\*) | 0,14 (không có ý nghĩa) |

Điều kiện kinh tế xã hội, rủi ro đầu tư, căng thẳng và xung đột đều có ý nghĩa độc lập: điểm cao hơn đi kèm dòng vào lớn hơn, nhất quán với việc nhà đầu tư nhạy với rủi ro cơ cấu và vận hành. Số hạng tương tác dương và có ý nghĩa với gần như mọi trụ cột, nghĩa là thể chế mạnh, rủi ro đầu tư thấp, ổn định chính trị và hiệu quả kinh tế tốt đều đệm cho dòng vốn trong giai đoạn bầu cử.

Hai trụ cột cuối là hai trường hợp ngược nhau:

- **Thể chế** không có tác động độc lập nhưng có tác dụng đệm rõ: chất lượng thể chế chỉ "lộ ra" khi có bất định.
- **Căng thẳng và xung đột** có tác động độc lập nhưng không có tác dụng đệm trong giai đoạn bầu cử: đây là yếu tố cản trở dòng vốn thường trực, không phụ thuộc chu kỳ bầu cử.

**Đối chiếu với bộ chỉ số quản trị của Ngân hàng Thế giới.** Bộ chỉ số này chỉ có theo năm, kém khớp với các biến vĩ mô theo quý, nên ICRG là bộ chính và bộ của Ngân hàng Thế giới chỉ dùng để kiểm chứng.

| Chiều quản trị | Tác động độc lập | Tương tác với bầu cử |
|---|---|---|
| Điểm tổng hợp | 0,20 (\*\*\*) | 0,088 (\*\*) |
| Kiểm soát tham nhũng | 0,093 (\*\*\*) | 0,064 (\*\*) |
| Hiệu quả chính phủ | 0,071 (\*\*) | 0,094 (\*\*) |
| Pháp quyền | 0,18 (\*\*\*) | 0,078 (\*\*) |
| Chất lượng quản lý | 0,12 (\*\*\*) | 0,092 (\*\*) |
| Tiếng nói và trách nhiệm giải trình | −0,034 (không có ý nghĩa) | 0,058 (\*) |
| Ổn định chính trị và vắng bạo lực | 0,021 (không có ý nghĩa) | 0,049 (không có ý nghĩa) |

Bốn chiều nổi bật là kiểm soát tham nhũng, hiệu quả chính phủ, pháp quyền và chất lượng quản lý. Tính toán tác động biên cho thấy ở nước có quản trị trung bình hoặc trên trung bình, ảnh hưởng ổn định của thể chế mạnh bù đắp hoàn toàn tác động tiêu cực của bất định bầu cử. Chỉ nhóm phần tư thấp nhất về quản trị còn dễ tổn thương trước biến động dòng vốn trong chu kỳ bầu cử.

**Phát hiện tinh tế nhất: độ sâu tài chính không đệm được bất định chính trị.** Trong đặc tả của bài, độ sâu tài chính có tác động độc lập dương rõ rệt lên dòng vốn vào. Nhưng khi cho nó tương tác với biến giả bầu cử, số hạng tương tác không có ý nghĩa. So sánh hai loại cú sốc:

| Loại cú sốc | Điều gì giúp chống chịu |
|---|---|
| Bất định toàn cầu (đo bằng VIX) | Độ sâu tài chính trong nước và khả năng hấp thụ cú sốc từ thị trường vốn quốc tế. Carrière-Swallow và Céspedes (2013) cho thấy khi thanh khoản toàn cầu thắt chặt, nước có hệ thống tài chính nông gặp ràng buộc tín dụng làm khuếch đại mức co hẹp đầu tư |
| Bất định chính trị trong nước | Độ sâu tài chính không đủ; chỉ khung thể chế mạnh mới trấn an được nhà đầu tư |

Lý do khác nhau: bầu cử tạo bất định về hướng chính sách dài hạn, làm xói mòn niềm tin nhà đầu tư. Thị trường tài chính sâu giúp vay mượn dễ hơn nhưng không trả lời được câu hỏi chính sách sẽ đi về đâu; trong bối cảnh đó, khung thể chế mạnh mang lại sự trấn an bù đắp phần nào cho việc thiếu rõ ràng về chính sách.

### 9. Kiểm chứng độ vững

**Thứ nhất, thước đo bất định thay thế.** Bài thử hai chỉ số:

- **Chỉ số Bất định Thế giới (WUI):** đếm tần suất từ "bất định" trong báo cáo quốc gia của Economist Intelligence Unit. Qua bảy đặc tả, cả hệ số của WUI lẫn tương tác của nó với bầu cử đều không có ý nghĩa, trong khi các biến liên quan bầu cử vẫn vững.
- **Chỉ số Bất định Chính sách Kinh tế (EPU):** tỷ lệ bài báo đồng thời nhắc tới kinh tế, chính sách và bất định. Hạn chế là chỉ có cho 8 trong 38 nước, nên bài phải dùng chỉ số toàn cầu (bình quân gia quyền theo GDP của 18 nước). Biến này cũng không có ý nghĩa, còn các biến giả bầu cử vẫn vững.

Kết luận: bất định liên quan bầu cử, nhất là khi xét theo mức ổn định chính trị, đóng vai trò riêng biệt và vững, vượt ra ngoài những gì các thước đo bất định cấp quốc gia rộng hơn nắm bắt được.

**Thứ hai, không có "phần thưởng dân chủ".** Bài thử bốn thước đo phát triển dân chủ: điểm Polity (thang −10 tới +10), thay đổi điểm Polity hằng năm, chỉ số cạnh tranh bầu cử liên tục của DPI (thang 1 tới 7), và một biến nhị phân lập từ chỉ số đó. Tất cả đều không có ý nghĩa, trong khi bất định bầu cử vẫn là yếu tố tiêu cực. Nước dân chủ hơn không thu hút nhiều vốn hơn, và cũng không ít nhạy cảm hơn với bất định bầu cử.

**Thứ ba, mười một đặc tả thay thế:**

- **Đặc tả 1:** chia dòng vốn theo GDP quý thực tế thay vì GDP xu hướng. Đây là khác biệt duy nhất đáng chú ý: tác động tiêu cực nay xuất hiện cả ở hai quý trước bầu cử.
- **Đặc tả 2 đến 4:** bỏ xu hướng thời gian theo nước; thêm xu hướng chung; dùng hiệu ứng cố định năm. Kết luận không đổi.
- **Đặc tả 5:** loại năm 2020 (COVID).
- **Đặc tả 6:** thêm biến giả khủng hoảng tài chính toàn cầu. Biến này không có ý nghĩa, có lẽ vì căng thẳng giai đoạn đó đã được VIX nắm bắt.
- **Đặc tả 7 và 8:** thêm biến giả bầu cử Hoa Kỳ như một yếu tố đẩy. Không có quan hệ có ý nghĩa nào, trong khi hệ số bầu cử trong nước vẫn âm và có ý nghĩa. Bài diễn giải rằng bất định chính trị trong nước tác động mạnh hơn bất định chính trị ở Hoa Kỳ, có thể vì nhà đầu tư nhạy cảm hơn với bất định ở các nước mới nổi nơi khung thể chế yếu hơn. Để đối chiếu, bài dẫn Julio và Yook (2016): nếu chỉ nhìn riêng nhà đầu tư Mỹ thì FDI của họ ra nước ngoài giảm mạnh trong quý trước bầu cử Mỹ.
- **Đặc tả 9:** thêm bình quân chéo theo quý của dòng vốn các nước, làm đại diện cho các yếu tố toàn cầu không quan sát được.
- **Đặc tả 10:** dùng hiệu ứng cố định năm–vùng (bốn vùng).
- **Đặc tả 11:** mẫu con chỉ gồm bầu cử có ngày định sẵn theo hiến pháp. Các kết luận về sụt giảm trong quý bầu cử và tác dụng đệm của ổn định chính trị đều được xác nhận, nhất quán với giả định rằng thời điểm bầu cử là ngoại sinh.

### 10. Hàm ý chính sách

- **Biến động dòng vốn quanh bầu cử đặc biệt gây hại cho các thị trường mới nổi**, vốn thường phụ thuộc nhiều vào dòng vốn vào liên tục. Bất kỳ đợt đình trệ tạm thời nào cũng có thể ảnh hưởng xấu tới ổn định đồng tiền, nguồn cung tín dụng, khả năng đảo nợ và ổn định tài chính nói chung.
- **Cải cách cơ cấu có lợi ích ổn định vĩ mô.** Tăng cường chất lượng thể chế không chỉ phục vụ mục tiêu phát triển dài hạn mà còn hoạt động như tấm đệm chống các cú sốc từng đợt như cú sốc của chu kỳ bầu cử. Bằng cách giảm bất định, cải cách như vậy củng cố niềm tin nhà đầu tư và tăng khả năng chống chịu tài chính.
- **Nền tảng vĩ mô và bảo vệ nhà đầu tư.** Điều kiện kinh tế xã hội thuận lợi và hồ sơ rủi ro đầu tư tốt hơn giúp giảm nhẹ tác động của bất định chính trị. Muốn giữ sức hấp dẫn với dòng vốn qua mọi giai đoạn của chu kỳ bầu cử, cần củng cố nền tảng vĩ mô và bảo vệ quyền lợi nhà đầu tư (thực thi hợp đồng, thanh toán đúng hạn, cho phép hồi hương lợi nhuận).

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Political uncertainty | Bất định chính trị, đại diện bằng chu kỳ bầu cử |
| Push factor | Yếu tố đẩy từ bên ngoài: VIX, thanh khoản toàn cầu |
| Pull factor | Yếu tố kéo từ bên trong: tăng trưởng, thể chế, độ sâu tài chính |
| Gross private inflows | Dòng vốn tư nhân vào gộp, biến kết quả chính |
| Official flows | Dòng vốn chính thức từ ngân hàng trung ương và chính phủ |
| Trend GDP | GDP xu hướng, dùng để chuẩn hoá, tính bằng lọc HP |
| VIX | Chỉ số biến động ngụ ý của S&P 500, đại diện ngại rủi ro toàn cầu |
| Shadow federal funds rate | Lãi suất quỹ liên bang bóng của Wu và Xia, tính tới chính sách phi quy ước |
| ICRG | Hướng dẫn Rủi ro Quốc gia Quốc tế, chỉ số 0–100, 12 biến |
| DPI | Cơ sở dữ liệu Thể chế Chính trị, nguồn ngày bầu cử |
| NELDA | Bộ dữ liệu Bầu cử Quốc gia trong Chế độ Dân chủ và Chuyên chế |
| Margin of majority | Biên độ đa số, tỷ lệ ghế chính phủ nắm giữ |
| Veto player | Chủ thể phủ quyết, dùng để đo mức luân chuyển chính trị |
| Polarization | Phân cực, khoảng cách ý thức hệ giữa chính phủ và đối lập |
| Predetermined election | Bầu cử theo lịch định sẵn trong hiến pháp |
| Snap election | Bầu cử bất thường, tổ chức sớm hoặc muộn hơn lịch |
| Incumbent turnover | Đương nhiệm thua, dẫn tới đổi lãnh đạo |
| Irreversibility | Tính khó đảo ngược của khoản đầu tư, giải thích độ nhạy của FDI |
| Rollover risk | Rủi ro đảo nợ của dòng vốn kỳ hạn ngắn |
| Driscoll-Kraay | Hiệu chỉnh sai số chuẩn cho phụ thuộc chéo và tự tương quan |
| Pesaran CD test | Kiểm định phụ thuộc chéo trong dữ liệu bảng |
| Durbin-Wu-Hausman | Kiểm định ngoại sinh của biến giải thích |
| Granger causality | Nhân quả Granger, quan hệ dự báo một chiều |
| Placebo lead regression | Hồi quy giả dược dùng biến dẫn để kiểm tra nội sinh |
| Political business cycle | Chu kỳ kinh doanh chính trị, từ Nordhaus (1975) |
| WUI | Chỉ số Bất định Thế giới, đếm từ khoá trong báo cáo EIU |
| EPU | Chỉ số Bất định Chính sách Kinh tế, đếm bài báo |
| Polity V | Thang đo phát triển dân chủ từ −10 tới +10 |
| Democratic premium | Phần thưởng dân chủ, giả thuyết bị bác bỏ trong bài |
| Financial depth | Độ sâu tài chính, chống được cú sốc toàn cầu nhưng không chống được bất định chính trị |

## Câu nói đáng nhớ

> "Countries in the lowest quartile of political stability experience, on average, a 28 percent decline in gross capital inflows during election quarters."

> "This negative effect is absent in countries with above-average political stability scores."

> "In contrast to global shocks, a deeper financial system may not be sufficient to cushion against political uncertainty."

## Đánh giá và phát hiện đáng chú ý

### Nhan đề nói ngược với kết quả cốt lõi: bầu cử không quan trọng, sự mong manh mới quan trọng

Biến giả bầu cử **đứng một mình thì dương và không có ý nghĩa thống kê**: hệ số +0,64. Toàn bộ kết quả của bài chỉ xuất hiện khi đưa thêm chỉ số ổn định chính trị và số hạng tương tác vào cùng lúc.

Cách đọc trung thực nhất vì thế không phải "bầu cử làm dòng vốn giảm" mà là: **bầu cử không tự nó gây ra gì cả; nó là thời điểm mà sự mong manh sẵn có của một nước bộc lộ thành giá.** Ở một nước thể chế vững, kỳ bầu cử là một sự kiện lịch, không phải một sự kiện tài chính.

Điều này cũng có nghĩa là hệ số −11,5 **không được diễn giải như một tác động trung bình**: trong đặc tả có tương tác, đó là tác động tại điểm chỉ số ổn định chính trị bằng 0, một nước không tồn tại trong mẫu. Ghép hai hệ số lại, điểm hoà vốn nằm ở mức chỉ số khoảng 64 (vì 11,5 chia 0,18 ra xấp xỉ 63,9): dưới ngưỡng đó bầu cử rút vốn ra, trên ngưỡng đó bầu cử hút vốn nhẹ vào. Con số này khớp đúng với phát biểu của bài rằng các nước trên mức trung bình không chịu tác động nào, và là cách hữu ích hơn nhiều để ghi nhớ kết quả so với việc trích hệ số thô.

### Con số ấn tượng nhất của bài cũng là con số ít được nhận dạng nhất

Chênh lệch 65 điểm phần trăm giữa việc đương nhiệm thua (−57,3%) và đương nhiệm thắng (+7,6%) sẽ được trích nhiều nhất, và cũng là phát hiện yếu nhất về mặt nhận dạng.

Cả năm biện pháp chống nội sinh của bài — biến công cụ thời gian kể từ lần bầu cử trước, kiểm định Granger, hồi quy giả dược, mô hình logit, mẫu con bầu cử theo lịch — đều nhắm vào **thời điểm** bầu cử. Không biện pháp nào nhắm vào **kết quả** bầu cử. Nhưng kết quả bầu cử hiển nhiên nội sinh với điều kiện kinh tế: đương nhiệm thua khi nền kinh tế xấu, và vốn rút đi khi nền kinh tế xấu.

Điều tương tự đúng với bầu cử ngoài lịch. Bài nói thẳng rằng trong mẫu này chúng **thường được kích hoạt bởi bất ổn chính trị hoặc khủng hoảng**. Nếu vậy thì −48,7% không đo tác động của việc tổ chức bầu cử sớm mà đo tác động của cuộc khủng hoảng đã làm nó phải diễn ra. Nên trích các con số của nhóm phần tư thấp nhất trong quý bầu cử như ước lượng có cơ sở, và trích −57% cùng −49% như **mô tả tương quan trong tình huống khủng hoảng**, không như hiệu ứng nhân quả của kết quả bỏ phiếu.

### Dòng danh mục miễn nhiễm còn FDI thì dai dẳng, và điều đó đảo ngược thứ tự ưu tiên chính sách

Trực giác phổ biến — và toàn bộ bộ công cụ chống dừng đột ngột được xây quanh nó — là "tiền nóng chạy trước khi có biến". Số liệu ở đây nói ngược: **dòng danh mục có hệ số −1,27 và không có ý nghĩa thống kê**. Trong khi đó FDI giảm −3,60 trong quý bầu cử và **vẫn còn âm có ý nghĩa hai quý sau (−0,35)**, còn dòng nợ tuy chịu đòn nặng nhất trong quý bầu cử (−6,08) thì lại không để lại dấu vết dai dẳng nào.

Hệ quả lớn hơn bài nói ra. Nếu bất định chính trị chủ yếu làm chậm FDI chứ không gây tháo chạy danh mục thì **đó không phải là một vấn đề ổn định tài chính mà là một vấn đề năng lực sản xuất**, và hai loại vấn đề này dùng hai bộ công cụ khác hẳn nhau. Dự trữ ngoại hối, hạn mức hoán đổi tiền tệ, biện pháp an toàn vĩ mô, thậm chí một chương trình của IMF — tất cả đều để cầm máu dòng danh mục, và không thứ nào làm một nhà máy bị hoãn khởi công sớm hơn một quý. Thiệt hại không hiện ra trong cán cân thanh toán năm đó; nó hiện ra trong tăng trưởng vài năm sau.

### Một câu ngắn bác bỏ gần như toàn bộ chương trình nghị sự chống chịu quen thuộc

Câu kết của bài — độ sâu tài chính chống được cú sốc toàn cầu nhưng không chống được bất định chính trị trong nước — được viết nhẹ nhàng như một sắc thái bổ sung, nhưng nó là một mệnh đề mạnh.

Chương trình nghị sự chống chịu tiêu chuẩn cho một nền kinh tế mới nổi gồm phát triển thị trường trái phiếu nội tệ, mở rộng cơ sở nhà đầu tư tổ chức, tăng độ sâu hệ thống ngân hàng. Bài này nói rằng với loại cú sốc đang bàn, **toàn bộ danh mục đó có tác động độc lập dương nhưng không có tác dụng đệm nào**. Thứ duy nhất có tác dụng đệm là chất lượng thể chế.

Và trong bảng phân rã trụ cột, trường hợp đáng suy nghĩ nhất là trụ cột thể chế: tác động độc lập chỉ 0,085 và **không có ý nghĩa**, nhưng tương tác 0,62 và có ý nghĩa. Nói cách khác, **chất lượng thể chế gần như không được định giá trong thời bình; nó chỉ lộ giá trị khi có bất định.** Đó cũng là lời giải thích lạnh lùng cho việc vì sao cải cách thể chế luôn bị hoãn: lợi ích của nó không xuất hiện trong số liệu của những năm yên ả.

### Không có phần thưởng dân chủ, nhưng có phần thưởng cho hợp đồng

Bài thử bốn thước đo dân chủ hoá và không thước đo nào có ý nghĩa. Đặt cạnh bảng chỉ số quản trị của Ngân hàng Thế giới thì bức tranh còn sắc hơn: **"tiếng nói và trách nhiệm giải trình" có hệ số độc lập −0,034 và không có ý nghĩa, trong khi pháp quyền là 0,18 và kiểm soát tham nhũng 0,093, cả hai đều có ý nghĩa ở mức cao nhất.** Thông điệp ngầm rất rõ và bài không phát biểu nó: nhà đầu tư quốc tế không trả tiền cho tính đại diện, họ trả tiền cho khả năng dự đoán và khả năng thực thi hợp đồng.

Cần đọc kèm hai hạn chế mà bài nói thẳng: R bình phương trong nhóm chỉ 0,19–0,23, tức bốn phần năm biến thiên của dòng vốn vẫn không giải thích được; và **mẫu không có Trung Quốc** vì thiếu dữ liệu ngày bầu cử, tức mất luôn mô hình đối chứng quan trọng nhất là một nước hút vốn khổng lồ mà không có bất kỳ bất định bầu cử nào.

### Với Việt Nam: đúng mô hình đối chứng bị loại khỏi mẫu, và một chu kỳ tương đương không nằm trong cơ sở dữ liệu nào

Việt Nam thuộc đúng nhóm bị mẫu bỏ qua vì lý do như Trung Quốc. Theo thước đo của bài, bất định bầu cử của Việt Nam bằng không, và kết quả "không có phần thưởng dân chủ" xác nhận rằng điều đó không gây thiệt hại gì cho khả năng thu hút vốn. Tính liên tục chính sách — thứ mà bài đo được giá trị qua mức +7,6% khi đương nhiệm thắng — là tài sản thật và Việt Nam sở hữu nó ở mức cao.

Nhưng cơ chế thực của bài không phải bầu cử mà là **bất định về hướng chính sách dài hạn**, và loại bất định đó không biến mất khi không có lá phiếu, nó chỉ chuyển sang lịch khác: chu kỳ đại hội năm năm, các đợt chuyển giao nhân sự cấp cao, các chiến dịch chỉnh đốn làm chậm phê duyệt dự án trên diện rộng. Không cơ sở dữ liệu bầu cử nào ghi nhận những mốc này, nên theo logic của bài thì có một tác động lẽ ra phải đo mà chưa ai đo.

Hai kết quả ghép lại thành một cảnh báo cụ thể. Loại dòng vốn chịu tác động **dai dẳng** nhất là FDI; và trong tài liệu cùng thư mục về tách lượng khỏi giá, FDI cũng là loại có tới 93% biến động do yếu tố riêng của từng nước quyết định. Với Việt Nam, nơi FDI là dòng vốn chủ lực, hai kết quả này khoá vào nhau: **dòng vốn quan trọng nhất của Việt Nam vừa là dòng ít chịu chu kỳ toàn cầu nhất, vừa là dòng nhạy nhất với bất định chính sách trong nước.**

Các trụ cột mà bài đo được tác dụng đệm — kiểm soát tham nhũng, pháp quyền, chất lượng quản lý, và đặc biệt trụ cột rủi ro đầu tư gồm thực thi hợp đồng, chậm thanh toán và hồi hương lợi nhuận — là đúng những chiều mà chương trình cải cách trong tài liệu Việt Nam 2035 đặt làm trọng tâm. Bài này thêm một lý do định lượng ở chiều mà Việt Nam 2035 không đo: giá trị của thể chế không nằm ở mức dòng vốn trung bình mà ở việc dòng vốn có đứt hay không vào đúng lúc bất định lên cao.
