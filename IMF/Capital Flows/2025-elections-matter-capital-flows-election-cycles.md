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

## Dàn ý chi tiết

### 1. Vấn đề và cách tiếp cận

- Quan hệ giữa dòng vốn quốc tế và bất định chính trị ở các nền kinh tế mới nổi cho tới nay nhận được rất ít chú ý, dù tài liệu về dòng vốn nói chung rất phong phú. Bầu cử là ví dụ điển hình của giai đoạn mà bất định gia tăng có thể làm mờ triển vọng. Ngay cả khi không có khủng hoảng hay đảo lộn chính trị lớn, bầu cử vẫn định kỳ mở ra khả năng thay đổi chưa biết trước trong môi trường kinh tế, thể chế và quản lý.
- Lập luận trung tâm là không chỉ các thay đổi chính sách cuối cùng mới quan trọng, mà chính sự bất định quanh những thay đổi có thể xảy ra, bất kể chúng có thành hiện thực hay không, cũng đủ ảnh hưởng tới hành vi nhà đầu tư. Điều này có thể khiến nhà đầu tư ít nhất tạm thời rút khỏi hoặc giảm phơi nhiễm với thị trường nội địa trước, trong và ngay sau khi bỏ phiếu.
- Về mặt lý thuyết, bài dựa trên Bernanke năm 1983 về đầu tư dưới bất định: bất định về hàm ý dài hạn của một sự kiện có thể làm trì hoãn quyết định đầu tư, vì chủ thể kinh tế định giá cho việc chờ thêm thông tin. Khung này áp dụng được cho cả doanh nghiệp lẫn nhà đầu tư phân bổ vốn.
- Bầu cử tạo ra một môi trường thí nghiệm tự nhiên gần đúng, giúp tách tác động của bất định chính trị khỏi các động lực vĩ mô rộng hơn, vì thời điểm bầu cử thường được ấn định trước bởi quy tắc hiến pháp và không chịu ảnh hưởng của nhà đầu tư cụ thể hay môi trường kinh tế hiện hành.
- Bài thẳng thắn nêu mối lo về nội sinh và xử lý bằng năm cách. Quan ngại bắt nguồn từ tài liệu chu kỳ kinh doanh chính trị kinh điển từ Nordhaus năm 1975, theo đó người đương nhiệm cơ hội có thể triển khai kích thích tài khoá và tiền tệ trước bầu cử để đẩy tăng trưởng ngắn hạn và tăng khả năng tái đắc cử. Cơ chế này hàm ý bầu cử có thể tác động tới kết quả vĩ mô một cách trực tiếp, độc lập với bất định.
- Năm cách xử lý gồm: dùng thời gian kể từ lần bầu cử trước làm biến công cụ, với kiểm định Durbin, Wu và Hausman không bác bỏ giả thuyết ngoại sinh; kiểm định nhân quả Granger cho thấy bầu cử Granger-gây ra dòng vốn nhưng không có chiều ngược lại; hồi quy giả dược dùng biến dẫn; mô hình logit về thời điểm bầu cử; và mẫu con chỉ gồm bầu cử theo lịch định sẵn.

### 2. Dữ liệu

- Bộ dữ liệu theo quý cho 38 nền kinh tế mới nổi ở mọi khu vực, giai đoạn 1990 tới 2020. Điểm cuối bị ràng buộc bởi độ trễ đáng kể trong việc cập nhật các cơ sở dữ liệu biến chính trị. Trung Quốc, một nước nhận vốn quan trọng, không nằm trong mẫu do thiếu dữ liệu ngày bầu cử trong cả DPI lẫn NELDA.
- Dòng vốn lấy từ cơ sở dữ liệu Thống kê Cán cân Thanh toán của IMF, chuẩn hoá theo GDP xu hướng bằng cách áp lọc HP lên GDP quý ước tính từ số liệu năm của Triển vọng Kinh tế Thế giới, với hai năm dữ liệu bổ sung sau điểm cuối để giảm chệch đầu mút.
- Bước điều chỉnh quan trọng nhất là tách dòng vốn chính thức khỏi dòng vốn tư nhân. Ở phía dòng vào, bài trừ nợ của ngân hàng trung ương và chính phủ với người không cư trú cùng phân bổ quyền rút vốn đặc biệt. Ở phía dòng ra, trừ tài sản tài chính do ngân hàng trung ương và chính phủ mua. Lý do được nêu rất rõ: chủ nợ chính thức có thể được huy động để ngăn khủng hoảng bằng cách bù đắp dòng vốn tư nhân chảy ra, điều đó sẽ triệt tiêu chính tác động bất định mà bài muốn đo.
- Bài tập trung vào dòng vào gộp vì dòng ròng che giấu biến động cao trong giao dịch của người cư trú và không cư trú, và vì bất định chính trị cảm nhận được có khả năng lớn hơn với nhà đầu tư nước ngoài so với trong nước.
- Dữ liệu bầu cử lấy chủ yếu từ Cơ sở dữ liệu Thể chế Chính trị, bổ sung bằng Bộ dữ liệu Bầu cử Quốc gia trong Chế độ Dân chủ và Chuyên chế. Với nước theo chế độ nghị viện thì dùng bầu cử lập pháp, với nước theo chế độ tổng thống thì dùng bầu cử cơ quan hành pháp, và loại bầu cử được xác định theo hệ thống chính trị của nước đó trong từng quý cụ thể.
- Về diễn biến dòng vốn, đỉnh trước khủng hoảng tài chính toàn cầu đạt trên mười phần trăm GDP quý xu hướng. Dòng vào không trở lại mức trước khủng hoảng, trong khi dòng ra tăng từ dưới một phần trăm trong thập niên 1990 lên trên ba phần trăm trong thập kỷ gần đây, phản ánh sự nổi lên của nhà đầu tư tổ chức ở thị trường mới nổi và quá trình tự do hoá tài khoản vốn từng bước.
- Về cơ cấu, FDI chiếm tỷ trọng lớn nhất và ổn định ở hai phần trăm GDP suốt hai mươi lăm năm, kể cả trong COVID. Năm 2007, dòng vốn khu vực ngân hàng chiếm gần một nửa tổng dòng vào rồi sụp đổ khi thanh khoản toàn cầu thắt chặt, chủ yếu do đảo chiều của hoạt động cho vay ngân hàng ngắn hạn.

### 3. Phương pháp

- Bài dùng khung đẩy và kéo chuẩn, mở rộng để tính tới bất định chính trị. Mô hình cho phép hệ số chặn khác nhau theo nước và xu hướng thời gian khác nhau theo nước.
- Về sai số chuẩn, bài lập luận rằng do bản chất của các yếu tố ảnh hưởng tới dòng vốn, hiệu ứng lây lan và các yếu tố chung không quan sát được có khả năng đóng vai trò, làm tăng nguy cơ tương quan không gian trong sai số. Kiểm định phụ thuộc chéo của Pesaran xác nhận suy đoán này, nên bài dùng hiệu chỉnh Driscoll và Kraay.

### 4. Kết quả cơ sở

- Về yếu tố đẩy, mức ngại rủi ro toàn cầu tăng cản trở đáng kể dòng vốn tư nhân vào các nền kinh tế mới nổi, trong khi nới lỏng thanh khoản toàn cầu đẩy vốn vào các nước này.
- Về yếu tố kéo, chênh lệch tăng trưởng so với nước phát triển là động lực vững, còn chênh lệch lãi suất thực không có ý nghĩa thống kê. Bài lưu ý rằng kết quả thực nghiệm trong tài liệu cũng khá thiếu kết luận về vai trò của yếu tố này. Phát triển thị trường tài chính có tác động dương, còn độ mở tài khoản vốn đo bằng chỉ số Chinn và Ito không có ý nghĩa.
- Phần quan trọng nhất là cấu trúc kết quả về bầu cử. Khi đứng một mình, biến giả quý bầu cử không có ý nghĩa. Nhưng khi ước lượng đồng thời cùng chỉ số ổn định chính trị và số hạng tương tác, cả ba đều trở nên có ý nghĩa thống kê. Điều này hàm ý rằng bầu cử trung bình đúng là đi kèm tác động tiêu cực lên dòng vốn trong quý diễn ra, ổn định chính trị tác động độc lập, và tác động tiêu cực liên quan bầu cử được làm dịu trong môi trường chính trị ổn định hơn.
- Về thời điểm, không có sụt giảm có ý nghĩa trong giai đoạn chạy đà trước bầu cử. Cú sốc rơi vào quý bầu cử và một tới hai quý sau đó.
- Bài cũng thừa nhận rằng dù các biến giải thích có ý nghĩa thống kê và có hiệu ứng cố định, phần lớn biến thiên của dòng vốn vẫn không giải thích được, thể hiện qua R bình phương thấp, và đây là đặc điểm chung của mọi nghiên cứu về dòng vốn.

### 5. Phân tách theo loại dòng vốn

- Việc tách dòng vào thành nợ và phi nợ không làm thay đổi hình mẫu chung về chiều hay ý nghĩa của các yếu tố đẩy và kéo, nhưng tầm quan trọng tương đối khác nhau. Mức ngại rủi ro toàn cầu tăng đi kèm mức giảm lớn hơn nhiều ở dòng nợ, phản ánh độ nhạy của chúng với thay đổi niềm tin thị trường và chênh lệch lợi suất cùng khả năng dễ bị lây lan. Thanh khoản toàn cầu chỉ có ý nghĩa với dòng nợ, điều không đáng ngạc nhiên vì chúng thường kỳ hạn ngắn, dựa vào huy động bán buôn nên chịu rủi ro đảo nợ.
- Về bầu cử, tác động tiêu cực được xác nhận cho cả dòng nợ lẫn phi nợ, với cú đánh lớn hơn và có ý nghĩa cao hơn với dòng nợ. Theo loại công cụ, tác động có ý nghĩa được xác nhận cho FDI và đầu tư khác, nhưng không cho dòng danh mục. Bài giải thích rằng dòng danh mục có thể đảo ngược nhanh nên dường như miễn nhiễm với bất định bầu cử, còn tài liệu cũng tìm thấy tác động đặc biệt mạnh lên các hình thức dòng vốn khó đảo ngược như FDI.
- Với đầu tư khác, mức giảm trong quý bầu cử nhiều khả năng gắn với hoạt động đầu tư tư nhân thấp hơn quanh thời điểm bầu cử và nhu cầu tài trợ tương ứng thấp hơn.
- Về độ dai dẳng, mức giảm dường như bền hơn với dòng phi nợ mà FDI là cấu phần chính, có thể vì nhà đầu tư trực tiếp đối mặt rủi ro cao hơn nên thận trọng hơn về việc quay lại cho tới khi có rõ ràng hơn về các thay đổi chính sách khả dĩ sau bầu cử.
- Với dòng ra, kết quả đáng chú ý là cả ổn định chính trị, bầu cử lẫn tương tác của chúng đều không có liên hệ có ý nghĩa. Bài nêu hai cách giải thích khả dĩ: nhà đầu tư trong nước đã quen với rủi ro chính trị nội địa hoặc đọc được chúng tốt hơn; hoặc nhà đầu tư nước ngoài có thông tin hạn chế về nước chủ nhà và được bảo vệ yếu hơn dưới thể chế pháp lý và chính trị của nước đó, khiến họ dễ tổn thương hơn trước bất định chính sách. Dù vậy, nhà đầu tư trong nước có vẻ điều chỉnh danh mục một tới hai quý sau bầu cử.
- Đáng chú ý là hạn chế tài khoản vốn chỉ là động lực có ý nghĩa với dòng ra chứ không với dòng vào.
- Với dòng ròng, hình mẫu khá sát dòng vào gộp, phản ánh việc dòng ròng ở thị trường mới nổi chủ yếu do dòng vào chi phối. Nhưng ý nghĩa của các biến chính trị yếu hơn, có lẽ vì tác động bị pha loãng bởi dòng ra.

### 6. Đặc điểm bầu cử

- Nhóm biến trước bầu cử cho kết quả phần lớn là âm tính. Biên độ đa số có hệ số dương yếu nhưng không có tác động khác biệt trong giai đoạn bầu cử, kết quả mà bài cho là ủng hộ phát hiện trong tài liệu rằng chính phủ thiểu số có thể ổn định ngang chính phủ đa số. Kiểm soát và cân bằng, phân cực, cùng thăm dò thuận lợi đều không có ý nghĩa. Với thăm dò, một cách giải thích được nêu là thăm dò đáng tin chỉ có ở khoảng một phần ba số cuộc bầu cử được phân tích.
- Kết luận của phần này được nêu thẳng thắn: bằng chứng chỉ ở mức thăm dò và các tác động ước lượng nhìn chung khiêm tốn.
- Ba đặc điểm thực sự quan trọng nằm ở chỗ bất định có kéo dài sau bầu cử hay không. Với bạo lực bầu cử, cả hai loại đều đi kèm dòng vốn thấp hơn trong quý bầu cử, nhưng bầu cử có bạo lực thể hiện tác động tiêu cực dai dẳng kéo dài một tới hai quý sau, trong khi với bầu cử hoà bình thì tác động ngắn ngủi và giới hạn trong quý bầu cử.
- Với thời điểm bầu cử, khoảng tám mươi phần trăm diễn ra theo ngày định sẵn. Hệ số của bầu cử ngoài lịch nhỉnh hơn một chút so với bầu cử theo lịch, gợi ý nhà đầu tư thận trọng hơn. Quan trọng hơn, với bầu cử ngoài lịch, tác động tiêu cực có ý nghĩa kéo dài tới bốn quý sau, trong khi với bầu cử theo lịch thì giới hạn trong quý bầu cử.
- Với kết quả bầu cử, khi đương nhiệm thua, tác động âm và có ý nghĩa cả trong quý bầu cử lẫn tới hai quý sau. Khi đương nhiệm giữ được quyền lực, tác động nhỏ hơn về độ lớn và ngắn ngủi. Hình mẫu này nhất quán với giả thuyết rằng tính liên tục chính sách làm giảm bất định và ổn định dòng vốn.

### 7. Định lượng

- Với các nước thuộc phần tư thấp nhất về ổn định chính trị, tác động trung bình là âm một phẩy hai lăm phần trăm GDP xu hướng trong quý bầu cử, tương ứng với mức giảm hai mươi tám phần trăm so với mức trong hai quý trước bầu cử.
- Tác động tiêu cực rõ rệt nhất xảy ra khi đương nhiệm thua hoặc khi bầu cử không theo lịch định sẵn, những tình huống thường gắn với bất định cao. Trong các trường hợp đó, dòng vốn vào gộp của các nước kém ổn định nhất giảm khoảng năm mươi phần trăm.
- Điểm đáng chú ý nhất là khi đương nhiệm thắng, dòng vốn thậm chí tăng nhẹ, tạo ra chênh lệch khoảng sáu mươi lăm điểm phần trăm chỉ do kết quả bầu cử.
- Với một số loại dòng vốn gồm dòng vào gộp, dòng phi nợ và FDI, tác động tiêu cực chỉ xuất hiện ở nhóm phần tư thấp nhất. Nhưng với dòng ròng và dòng nợ, tác động lan sang cả nhóm phần tư thứ hai. Khi đương nhiệm thua hoặc bầu cử ngoài lịch, ngay cả nhóm phần tư thứ ba cũng chứng kiến dòng vào giảm.
- Kết luận quan trọng nhất về phân hoá: các nước có điểm ổn định chính trị trên mức trung bình không chịu sụt giảm có ý nghĩa thống kê nào quanh bầu cử.

### 8. Vai trò của năng lực thể chế

- Khi phân rã chỉ số ICRG thành năm trụ cột, điều kiện kinh tế xã hội, rủi ro đầu tư, cùng căng thẳng và xung đột đều có ý nghĩa độc lập trong việc giải thích dòng vốn. Điểm cao hơn đi kèm dòng vào lớn hơn, nhất quán với độ nhạy của nhà đầu tư với rủi ro cơ cấu và vận hành.
- Số hạng tương tác với biến giả bầu cử dương và có ý nghĩa với gần như mọi trụ cột, gợi ý rằng thể chế mạnh, rủi ro đầu tư thấp, ổn định chính trị và hiệu quả kinh tế tốt đều đóng vai trò đệm cho dòng vốn trong giai đoạn bầu cử.
- Hai trường hợp đối lập đáng chú ý. Trụ cột thể chế, gồm tham nhũng, pháp quyền và bộ máy hành chính, không có tác động độc lập nhưng có tác dụng đệm rõ, tức chất lượng thể chế chỉ lộ ra khi có bất định. Ngược lại, căng thẳng và xung đột có ý nghĩa với tư cách biến độc lập nhưng không có tương tác đáng kể với giai đoạn bầu cử, hàm ý rằng đây là yếu tố cản trở dai dẳng với dòng vốn chứ không phụ thuộc vào chu kỳ bầu cử.
- Khi dùng bộ chỉ số quản trị của Ngân hàng Thế giới để kiểm chứng, bốn chiều nổi bật là kiểm soát tham nhũng, hiệu quả chính phủ, pháp quyền và chất lượng quản lý. Bài lưu ý rằng chỉ số của Ngân hàng Thế giới chỉ có ở tần suất năm nên kém khớp với thời điểm của các biến vĩ mô khác, và đó là lý do chính khiến ICRG được dùng làm bộ chính.
- Tính toán tác động biên cho thấy ở nước có quản trị trung bình hoặc trên trung bình, ảnh hưởng ổn định của thể chế mạnh bù đắp hoàn toàn tác động tiêu cực của bất định bầu cử. Chỉ nhóm phần tư thấp nhất về xếp hạng quản trị còn dễ tổn thương trước biến động dòng vốn trong chu kỳ bầu cử.
- Phát hiện tinh tế nhất là về độ sâu tài chính. Trong đặc tả của bài, độ sâu tài chính là yếu tố quyết định dương có ý nghĩa của dòng vốn vào. Nhưng khi tương tác với biến giả bầu cử để đánh giá tác dụng điều tiết, số hạng tương tác không có ý nghĩa. Bài đối chiếu trực tiếp với Carrière-Swallow và Céspedes năm 2013, vốn nhấn mạnh rằng khi thanh khoản toàn cầu thắt chặt, các nước có hệ thống tài chính nông gặp ràng buộc tín dụng làm khuếch đại mức co hẹp đầu tư. Kết luận là khác với cú sốc toàn cầu, một hệ thống tài chính sâu hơn có thể không đủ để chống đỡ bất định chính trị. Cách giải thích được đưa ra là bầu cử tạo bất định về hướng chính sách dài hạn, làm xói mòn niềm tin nhà đầu tư, và trong bối cảnh đó khung thể chế mạnh có thể mang lại sự trấn an bù đắp phần nào cho việc thiếu rõ ràng về chính sách.

### 9. Kiểm chứng độ vững

- Bài thử hai thước đo bất định thay thế. Qua bảy đặc tả kiểm soát Chỉ số Bất định Thế giới, cả hệ số của chỉ số này lẫn tương tác của nó với biến giả bầu cử đều không có ý nghĩa, trong khi các phát hiện về ý nghĩa của các biến liên quan bầu cử vẫn vững. Với Chỉ số Bất định Chính sách Kinh tế, hạn chế là chỉ có cho tám trong ba mươi tám nước nên phải dùng chỉ số toàn cầu, và biến này cũng không có ý nghĩa trong khi các biến giả bầu cử vẫn vững.
- Bài không tìm thấy bằng chứng nào về phần thưởng dân chủ. Cả bốn thước đo phát triển dân chủ đều không có ý nghĩa, trong khi bất định bầu cử vẫn là yếu tố tiêu cực với dòng vốn.
- Trong mười một đặc tả thay thế, khác biệt duy nhất đáng chú ý là khi chia theo GDP quý thay vì GDP xu hướng thì tác động tiêu cực cũng xuất hiện ở hai quý trước bầu cử.
- Kiểm chứng về bầu cử Hoa Kỳ cho kết quả không có ý nghĩa, trong khi hệ số bầu cử trong nước vẫn âm và có ý nghĩa. Bài diễn giải rằng bất định chính trị trong nước tác động mạnh hơn bất định chính trị ở Hoa Kỳ, có thể vì nhà đầu tư nhạy cảm hơn với bất định ở các nước mới nổi nơi khung thể chế yếu hơn. Nhưng bài cũng dẫn Julio và Yook năm 2016 để đối chiếu: nếu chỉ nhìn riêng nhà đầu tư Mỹ thì FDI của họ ra nước ngoài giảm mạnh trong quý trước bầu cử Mỹ.
- Cuối cùng, khi ước lượng lại trên mẫu con chỉ gồm bầu cử có ngày định sẵn theo hiến pháp, các kết luận chính về sụt giảm trong quý bầu cử và tác dụng đệm của ổn định chính trị đều được xác nhận, nhất quán với giả định rằng thời điểm bầu cử là ngoại sinh.

### 10. Hàm ý chính sách

- Bài nhấn mạnh rằng biến động dòng vốn quanh thời điểm bầu cử đặc biệt gây vấn đề cho các thị trường mới nổi, vốn thường phụ thuộc nhiều vào dòng vốn vào không gián đoạn. Bất kỳ đình trệ tạm thời nào cũng có thể gây hậu quả tiêu cực cho ổn định đồng tiền, nguồn cung tín dụng liên tục, khả năng đảo nợ và ổn định tài chính tổng thể.
- Hàm ý chính là nhấn mạnh lợi ích ổn định vĩ mô của cải cách cơ cấu. Tăng cường chất lượng thể chế không chỉ hỗ trợ mục tiêu phát triển dài hạn mà còn hoạt động như tấm đệm chống lại các cú sốc từng đợt như cú sốc do chu kỳ bầu cử gây ra. Bằng cách giảm bất định, cải cách như vậy có thể củng cố niềm tin nhà đầu tư và tăng khả năng chống chịu tài chính.
- Bài cũng chỉ ra rằng điều kiện kinh tế xã hội thuận lợi và hồ sơ rủi ro đầu tư tốt hơn giúp giảm nhẹ tác động tiêu cực của bất định chính trị, nên việc duy trì sức hấp dẫn của nền kinh tế với dòng vốn vào qua các giai đoạn khác nhau của chu kỳ bầu cử đòi hỏi củng cố nền tảng vĩ mô và bảo vệ quyền lợi nhà đầu tư.

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
