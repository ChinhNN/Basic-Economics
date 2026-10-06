# Market Access and High Spread Issuances — Tiếp cận thị trường và các đợt phát hành với chênh lệch lợi suất cao

**Nguồn:** IMF Working Paper WP/2026/010.
**Tác giả:** chưa xác định (bản PDF bắt đầu từ trang 5, không có trang bìa và trang tác giả).
**Ý chính:** Tỷ lệ các đợt phát hành trái phiếu quốc tế với chênh lệch lợi suất trên 500 điểm cơ bản đạt kỷ lục 20% năm 2020 và giữ trên 25% từ đó, cho thấy ràng buộc tiếp cận thị trường đang siết lại. Bài dựng một mô hình rủi ro đạo đức để chỉ ra rằng **chênh lệch lợi suất một mình không đủ để tóm tắt khả năng tiếp cận thị trường** — giá trị ròng của người vay, động cơ nỗ lực và chất lượng tín hiệu mà chủ nợ nhận được cũng quyết định. Kiểm chứng bằng mô hình rừng ngẫu nhiên với 99 biến cho 46 nước, bài tìm ra một quan hệ **hình chữ U ngược**: xác suất phát hành **tăng** theo chênh lệch cho tới khoảng 200 điểm cơ bản rồi mới giảm, và rơi mạnh nhất quanh 600 điểm. Ở vùng chênh lệch thấp, việc phát hành phản ánh **nhu cầu tài trợ**; ở vùng cao, nó phản ánh **nguồn cung vốn**. Đúng như mô hình dự báo, **36% các đợt phát hành ở chênh lệch cao có kèm đặc tính phi truyền thống** như bảo lãnh hay tài sản bảo đảm, và tỷ lệ lên 42% khi ngưỡng nâng lên 600 điểm.

> **Lưu ý:** bản PDF bắt đầu từ trang 5 (phần Giới thiệu), không có trang bìa và trang tác giả. Số hiệu tài liệu lấy từ trang bìa sau. Câu "tỷ lệ phát hành chênh lệch trên 500 điểm cơ bản đạt kỷ lục 20% năm 2020 và giữ trên 25% từ đó" tự mâu thuẫn: nếu sau 2020 luôn trên 25% thì 20% năm 2020 không thể là kỷ lục. Không có bản gốc để biết con số nào chép sai nên giữ nguyên.

## Sơ đồ

### Vấn đề: phát hành nhiều hơn nhưng đắt hơn

```text
       BỐI CẢNH TRƯỚC ĐẠI DỊCH
       phát hành quốc tế ròng của chính phủ các nước mới nổi TĂNG
       VỌT → giá trị danh nghĩa chứng khoán quốc tế đang lưu hành
       TĂNG GẤP BA
       ⚠ NHƯNG chi phí nợ bình quân VẪN CAO và còn TĂNG THÊM từ 2019
       ★ tỷ lệ đợt phát hành với chênh lệch TRÊN 500 ĐIỂM CƠ BẢN:
         đạt KỶ LỤC 20% năm 2020 · giữ TRÊN 25% từ đó tới nay
       ⚠ điểm tinh tế: chênh lệch EMBIG tính theo TRỌNG SỐ PHÁT
         HÀNH RÒNG lại GIẢM — vì các đợt phát hành đắt tiền chủ
         yếu để TÁI TÀI TRỢ, nên khối lượng ròng của nhóm chênh
         lệch cao NHỎ
       → gợi ý: ràng buộc tiếp cận thị trường ĐANG SIẾT LẠI
       ═══════════════════════════════════════════════════════════
       VÌ SAO GIÁ KHÔNG TỰ CÂN BẰNG THỊ TRƯỜNG?
       trong thị trường không ma sát, giá điều chỉnh để cung gặp cầu
       ★ NHƯNG PHÂN PHỐI TÍN DỤNG có thể TỒN TẠI NHƯ MỘT TRẠNG
         THÁI CÂN BẰNG do BẤT ĐỐI XỨNG THÔNG TIN
         (Jaffee–Russell 1976; Keeton 1997; Stiglitz–Weiss 1981)
       ① LỰA CHỌN NGƯỢC · lãi suất cao hơn thu hút đúng những nước
          CÓ KHẢ NĂNG VỠ NỢ CAO NHẤT
       ② RỦI RO ĐẠO ĐỨC · lãi suất cao LÀM GIẢM động cơ trả nợ, vì
          phần còn lại cho người vay khi trả được nợ đã nhỏ đi
       → giải thích vì sao thị trường ĐÓNG HẲN với các nước có phần
         bù rủi ro vượt một ngưỡng nào đó
       ★ BẰNG CHỨNG: tần suất phát hành GIẢM khi chênh
         lệch tăng, và giảm DỐC NHẤT trong khoảng 300–800 điểm
       ⚠ lãi suất PHI RỦI RO của Mỹ đóng vai trò RẤT NHỎ trong
         việc giải thích quyết định phát hành → yếu tố RỦI RO
         RIÊNG CỦA NƯỚC quan trọng hơn điều kiện tài chính toàn cầu
```

### Mô hình rủi ro đạo đức và hai mệnh đề

```text
       CẤU TRÚC: hai kỳ · người vay (chính phủ) NGẠI RỦI RO ·
       chủ nợ quốc tế TRUNG LẬP RỦI RO · hai trạng thái Tốt và Xấu
       ┌─────────────────────────────────────────────────────────┐
       │ RÀNG BUỘC NGÂN SÁCH                                     │
       │ K = A + D        (vốn đầu tư = giá trị ròng + nợ)       │
       │ C₁(Tốt) = R^G − D(1+r)                                  │
       │ C₁(Xấu) = 0      ★ luôn vỡ nợ ở trạng thái Xấu          │
       ├─────────────────────────────────────────────────────────┤
       │ NỖ LỰC · e ∈ {e_H, e_L}                                 │
       │ e_H tốn chi phí B > 0 nhưng NÂNG xác suất trạng thái Tốt│
       │ ★ trong bối cảnh vĩ mô, e là nỗ lực TĂNG THU THUẾ, CẮT │
       │   CHI, hoặc CẢI CÁCH CƠ CẤU thúc đẩy tăng trưởng        │
       │ ⚠ chủ nợ KHÔNG QUAN SÁT ĐƯỢC nỗ lực → không hợp đồng hoá│
       │   được                                                  │
       ├─────────────────────────────────────────────────────────┤
       │ ★ TÍN HIỆU · s ∈ {H, L} — ví dụ XẾP HẠNG TÍN NHIỆM      │
       │ q_H > q_L : nỗ lực cao thì DỄ ra tín hiệu tốt hơn       │
       │ → lãi suất CÓ THỂ phụ thuộc vào TÍN HIỆU (nhưng không   │
       │   phụ thuộc vào TRẠNG THÁI THỰC)                        │
       └─────────────────────────────────────────────────────────┘
       ═══════════════════════════════════════════════════════════
       ★ MỆNH ĐỀ 1 — RÀNG BUỘC TƯƠNG THÍCH ĐỘNG CƠ KHÔNG BINDING
       nếu lợi ích của nỗ lực đủ lớn, người vay KHÔNG chọn lãi
       suất phụ thuộc tín hiệu mà đặt MỘT mức duy nhất:
                        r** = 1 / π(e_H)
       → chủ nợ được đền bù vừa đủ cho rủi ro, lợi nhuận kỳ vọng
         bằng 0, KHÔNG có phân phối tín dụng. Đây là phân bổ TỐT
         NHẤT trong mô hình
       ═══════════════════════════════════════════════════════════
       ★★ MỆNH ĐỀ 2 — RÀNG BUỘC BINDING: "MACRO NGƯỢC"
       khi ràng buộc binding, người vay đặt lãi suất PHỤ THUỘC
       TÍN HIỆU và trả LÃI CAO HƠN SAU TÍN HIỆU XẤU:
                        ★ r_L** > r_H**
       ★ TRỰC GIÁC: bằng cách CAM KẾT trả lãi cao hơn khi tín
         hiệu xấu, người vay tự làm cho việc LƯỜI BIẾNG trở nên
         KÉM HẤP DẪN HƠN → nới lỏng ràng buộc động cơ → LẤY LẠI
         được quyền tiếp cận thị trường
       ⚠ ĐÂY LÀ NGƯỢC với trái phiếu gắn GDP thông thường, vốn
         trả NHIỀU HƠN khi kinh tế TỐT
       ═══════════════════════════════════════════════════════════
       ★★★ VÍ DỤ THẬT: EL SALVADOR, THÁNG 4/2024
       lãi coupon sẽ TĂNG từ 0,25% lên 4,0% kể từ 10/2025 TRỪ KHI:
       ① một thoả thuận với IMF được phê duyệt kèm rà soát định kỳ
       ② HOẶC xếp hạng tín nhiệm từ ÍT NHẤT HAI tổ chức được nâng
         so với mức ban đầu
       → chính là CƠ CHẾ CAM KẾT chống rủi ro đạo đức mà Mệnh đề 2
         mô tả, được dùng để TÁI TIẾP CẬN thị trường vốn
       ═══════════════════════════════════════════════════════════
       ★ BỐN THAM SỐ QUAN TRỌNG NGOÀI CHI PHÍ VAY
       ① GIÁ TRỊ RÒNG A · tăng A làm người vay có nhiều "phần hùn"
          hơn → nới ràng buộc động cơ → dự trữ ngoại hối, mức nợ,
          vị thế đầu tư quốc tế ròng đều quan trọng
       ② LỢI SUẤT R^H · kỳ vọng tăng trưởng và thu ngân sách cao hơn
       ③ CHI PHÍ NỖ LỰC B · chi phí kinh tế và chính trị của củng
          cố tài khoá — B thấp hơn thì nới ràng buộc
       ④ Δπ · mức độ nỗ lực làm tăng xác suất trạng thái tốt
       ★ DIỄN GIẢI HAI BIẾN KHÔNG CÓ TRONG MÔ HÌNH
         NHU CẦU TÀI TRỢ GỘP · áp lực thanh khoản và nghĩa vụ trả
           nợ sắp tới → làm GIẢM đệm tài chính → tương đương A thấp
         NỢ CHÍNH THỨC · tính ƯU TIÊN của nó làm giảm nguồn lực
           còn lại cho chủ nợ khác → hạ A trong mắt thị trường
           ⚠ NHƯNG cũng có thể NÂNG chất lượng TÍN HIỆU, cho thấy
             có giám sát và cam kết → hiệu ứng LÔI KÉO thay vì
             hiệu ứng LẤN ÁT
```

### Thiết kế thực nghiệm

```text
       VẤN ĐỀ NHẬN DIỆN CỐT LÕI
       một chính phủ KHÔNG vay trong một kỳ có thể vì:
       ① CHỦ NỢ KHÔNG MUỐN CHO VAY ······ phía CUNG
       ② CHÍNH PHỦ KHÔNG MUỐN VAY ······· phía CẦU
       ⚠ tách riêng cung và cầu là RẤT KHÓ: thiếu dữ liệu, cần giả
         định mạnh, và khi có phân phối tín dụng thì đường cung
         với đường cầu KHÔNG CẮT NHAU
       ★ bài KHÔNG nhận diện được cú sốc cung và cầu, nhưng TIẾN
         GẦN HƠN nhờ nắm bắt được TƯƠNG TÁC PHI TUYẾN — cho phép
         ước lượng tác động của một yếu tố CẦU trong khi GIỮ CỐ
         ĐỊNH một yếu tố CUNG
       ⚠ TỰ NHẬN RÕ: kết quả phản ánh LIÊN HỆ DỰ BÁO, KHÔNG PHẢI
         quan hệ NHÂN QUẢ
       ═══════════════════════════════════════════════════════════
       DỮ LIỆU VÀ QUY TRÌNH
       46 nước · 94 quý · 2000Q1–2023Q2 · 99 BIẾN GỐC
       biến phụ thuộc: NHỊ PHÂN = 1 nếu phát hành ở quý t+3 HOẶC
       t+4 → chọn khoảng này vì đó là tầm mà mô hình DÙNG ĐƯỢC
       THỜI GIAN THỰC, tính tới độ trễ công bố dữ liệu
       ★ lớp CÂN BẰNG: 58% quan sát mang giá trị 1 → không cần
         kỹ thuật lấy mẫu lại
       ─────────────────────────────────────────────────────────
       ① XỬ LÝ DỮ LIỆU · điền khuyết bằng k láng giềng gần nhất ·
          thêm biến đổi (% GDP, tăng trưởng, trung bình và phương
          sai tăng trưởng 5 quý) · chia mẫu 90/10
          HUẤN LUYỆN 2001Q1–2021Q4 · KIỂM ĐỊNH 2022Q1–2023Q2
       ② HUẤN LUYỆN · ★ CỬA SỔ MỞ RỘNG 4 nếp gấp, mỗi nếp mở rộng
          giai đoạn huấn luyện, giai đoạn kiểm định giữ nguyên
          ★★ CÓ KHOẢNG TRỐNG MỘT KỲ giữa huấn luyện và kiểm định
             → CHỐNG RÒ RỈ DỮ LIỆU, mô phỏng đúng cách dùng thực tế
          loại bỏ đặc trưng đệ quy xuống còn ~50–80 biến
       ③ ĐÁNH GIÁ · diện tích dưới đường ROC trên mẫu ngoài
       ═══════════════════════════════════════════════════════════
       ★ KẾT QUẢ ĐÁNH GIÁ MÔ HÌNH
       RỪNG NGẪU NHIÊN ······ ROC-AUC 0,84
       LOGIT tốt nhất ······· ROC-AUC 0,77
       → chênh lệch 0,07 cho thấy TƯƠNG TÁC PHI TUYẾN THỰC SỰ
         quan trọng
       siêu tham số: 500 cây · 5 biến mỗi lần chia · độ sâu tối đa
       15 · lấy mẫu bootstrap · logit dùng phạt Ridge thuần (α=0),
       λ=0,06 · ngưỡng tối đa hoá F1 = 0,52 (rừng) và 0,51 (logit)
```

### Điều gì thực sự dự báo việc phát hành

```text
       MƯỜI LĂM BIẾN QUAN TRỌNG NHẤT (giá trị Shapley)
       ★ BỐN TRONG NĂM biến đầu là về NỢ ĐỐI NGOẠI
       ┌─────────────────────────────────────────────────────────┐
       │ ① nghĩa vụ quốc tế đang lưu hành của chính phủ (%GDP)   │
       │ ② ★ DỰ TRỮ NGOẠI HỐI GỘP (%GDP)                         │
       │ ③ thay đổi nghĩa vụ quốc tế so với cùng kỳ (phát hành   │
       │    ròng)                                                │
       │ ④ nghĩa vụ quốc tế kỳ hạn còn lại DƯỚI MỘT NĂM          │
       │ ⑤ nợ đối ngoại ngắn hạn                                 │
       │ ⑥ chênh lệch EMBIG · ⑦ tỷ giá · ⑧ GDP danh nghĩa        │
       │ ⑨ cán cân thương mại · ⑩ sử dụng tín dụng IMF           │
       │ ⑪ nợ với chủ nợ chính thức · ⑫ nợ công gộp dự báo 5 năm │
       │ ⑬ nợ đối ngoại dài hạn · ⑭ pháp quyền · ⑮ nợ ròng 3 năm │
       └─────────────────────────────────────────────────────────┘
       ═══════════════════════════════════════════════════════════
       HƯỚNG TÁC ĐỘNG (biểu đồ phụ thuộc từng phần)
       ★ NGHĨA VỤ ĐANG LƯU HÀNH · nhiều hơn → DỄ phát hành hơn,
         phi tuyến, mạnh nhất ở mức VỪA rồi CHỮNG LẠI khi nợ cao
         → việc chững lại có thể là dấu hiệu RÀNG BUỘC PHÍA CUNG
       ⚠ THAY ĐỔI nghĩa vụ · dễ phát hành nhất sau mức tăng VỪA
         PHẢI; mức tăng LỚN lại LÀM GIẢM xác suất phát hành
       ★★ DỰ TRỮ NGOẠI HỐI · nhiều dự trữ → phát hành ÍT HƠN
          ⚠ NGƯỢC với lý thuyết coi dự trữ là TÍN HIỆU tín nhiệm
          → giải thích: dự trữ được DÙNG và THAY THẾ cho tài trợ
            bên ngoài. Kênh CẦU chi phối kênh CUNG trong dự báo
            của mô hình, và quan hệ âm này giữ nguyên ở mọi mẫu con
       CÁN CÂN THƯƠNG MẠI · thặng dư → phát hành ÍT HƠN (đã tự có
         ngoại tệ đáp ứng nhu cầu)
       CHẾ ĐỘ TỶ GIÁ CỐ ĐỊNH · phát hành ÍT HƠN — vì chính phủ có
         ít lựa chọn để thu ngoại tệ trả nợ
       TỶ GIÁ DANH NGHĨA HIỆU DỤNG · ★ phi tuyến rõ quanh 0: đồng
         tiền LÊN GIÁ → DỄ phát hành; xuống giá thì không rõ
       ★ DỰ BÁO CÁN CÂN TÀI KHOÁ 3 NĂM TỚI · BƯỚC NHẢY MẠNH quanh
         NGƯỠNG KHÔNG — nước dự báo THẶNG DƯ dễ phát hành hơn HẲN
         so với nước dự báo thâm hụt
       DỰ BÁO NỢ CÔNG · cao hơn → phát hành ÍT HƠN
       NỢ CHÍNH THỨC · nhiều hơn → ÍT phát hành, nhưng quan hệ
         CHỮNG LẠI ở mức cao (tác động biên giảm dần)
       LÃI SUẤT nợ chính thức mới · thấp hơn → DỄ phát hành hơn
       PHÁP QUYỀN · tốt hơn → dễ phát hành, ★ phi tuyến với tác
         động biên mạnh nhất giữa PHÂN VỊ 15 và 40
         → có LỢI SUẤT GIẢM DẦN của uy tín một khi thể chế đã
           vượt một ngưỡng nhất định
       ═══════════════════════════════════════════════════════════
       ★★★ CHÊNH LỆCH EMBIG — HÌNH CHỮ U NGƯỢC
                xác suất
                phát hành
                    │        ╭──╮
                    │      ╭─╯  ╰─╮
                    │    ╭─╯      ╰──╮
                    │  ╭─╯           ╰───╮
                    │╭─╯                 ╰──────╮
                    └─┴───┴────┴────┴────┴────┴──── chênh lệch
                      0  200  400  600  800     (điểm cơ bản)
                         ★ ĐỈNH      ★ RƠI MẠNH NHẤT
       ★★ CÁCH ĐỌC: ở mức chênh lệch THẤP, việc phát hành phản
          ánh NHU CẦU TÀI TRỢ — chênh lệch tăng nhẹ đi kèm nhu
          cầu vay lớn hơn
          ở mức chênh lệch CAO, việc phát hành phụ thuộc vào
          NGUỒN CUNG VỐN — tức vào việc nhà đầu tư CÓ CHỊU mua
          hay không, và do đó vào khả năng chính phủ CAM KẾT
          ĐÁNG TIN rằng sẽ không vỡ nợ
       ⚠ chênh lệch KHÔNG phải biến quan trọng nhất — nó chỉ thực
         sự có ý nghĩa KHI TƯƠNG TÁC với các biến khác
```

### Ba nhóm chênh lệch: bằng chứng về ràng buộc phía cung

```text
       CHIA MẪU: THẤP dưới phân vị 40 (~200 đ.c.b) · TRUNG BÌNH
       phân vị 40–80 (~200–500) · CAO trên phân vị 80 (~500)
       ★ 9 TRONG 15 biến quan trọng nhất là CHUNG cho cả ba nhóm
       → nền tảng giống nhau; KHÁC BIỆT nằm ở CHI TIẾT
       ═══════════════════════════════════════════════════════════
       ┌──────────────────┬──────────────────────────────────────┐
       │ ★ NỢ DÀI HẠN     │ CHÊNH LỆCH THẤP · nợ dài hạn nhiều   │
       │   ĐỐI NGOẠI      │   → DỄ phát hành NHẤT                │
       │   — dấu NGƯỢC    │ CHÊNH LỆCH TRUNG/CAO · ★ NGƯỢC LẠI  │
       │   nhau!          │ GIẢI THÍCH: với nước rủi ro thấp, nợ │
       │                  │ dài hạn là TÍN HIỆU uy tín, giảm rủi │
       │                  │ ro đảo nợ, và nhà đầu tư THÈM công   │
       │                  │ cụ dài hạn. Với nước rủi ro cao, nợ  │
       │                  │ dài hạn làm TĂNG rủi ro vỡ nợ qua    │
       │                  │ kênh PHA LOÃNG NỢ                    │
       ├──────────────────┼──────────────────────────────────────┤
       │ ★★ NỢ CHÍNH THỨC│ CHÊNH LỆCH CAO · nợ chính thức nhiều │
       │   so với TÍN     │   → ÍT phát hành (hiệu ứng LẤN ÁT)   │
       │   DỤNG IMF       │ ⚠ NHƯNG TÍN DỤNG IMF nhiều → PHÁT    │
       │   — dấu NGƯỢC    │   HÀNH NHIỀU HƠN                     │
       │   nhau!          │ → hiệu ứng TÍN HIỆU của chương trình │
       │                  │   IMF khôi phục niềm tin thị trường  │
       │                  │ ★ nợ chính thức ĐÃ CAM KẾT NHƯNG CHƯA│
       │                  │   GIẢI NGÂN cũng nằm trong nhóm biến │
       │                  │   quan trọng → ngay cả nghĩa vụ NGOÀI│
       │                  │   BẢNG CÂN ĐỐI cũng lấn át vốn tư    │
       │                  │ ở chênh lệch thấp/trung: gần như VÔ  │
       │                  │   CẢM với cả hai loại                │
       ├──────────────────┼──────────────────────────────────────┤
       │ ★★ TĂNG TRƯỞNG   │ CHÊNH LỆCH CAO · phát hành khi kinh  │
       │   TOÀN CẦU       │   tế thế giới MẠNH → ★ bằng chứng RÕ │
       │   — dấu NGƯỢC    │   NHẤT về ràng buộc PHÍA CUNG: chỉ   │
       │   nhau!          │   tiếp cận được khi nhà đầu tư CÓ    │
       │                  │   KHẨU VỊ RỦI RO và ĐI TÌM LỢI SUẤT  │
       │                  │ CHÊNH LỆCH THẤP · phát hành khi kinh │
       │                  │   tế thế giới YẾU → hình mẫu PHẢN    │
       │                  │   CHU KỲ, theo nhu cầu tài khoá chứ  │
       │                  │   không theo thời điểm thị trường    │
       ├──────────────────┼──────────────────────────────────────┤
       │ DỰ TRỮ           │ ★ biến QUAN TRỌNG NHẤT ở nhóm CAO —  │
       │                  │ dự trữ là hình thức TỰ BẢO HIỂM đặc  │
       │                  │ biệt quan trọng với nước rủi ro cao  │
       ├──────────────────┼──────────────────────────────────────┤
       │ CHẾ ĐỘ TỶ GIÁ    │ ★ biến quan trọng THỨ HAI ở nhóm CAO │
       │                  │ → chế độ cứng nhắc báo hiệu dễ tổn   │
       │                  │ thương trước cú sốc và ít khả năng   │
       │                  │ điều chỉnh để tạo ngoại tệ           │
       ├──────────────────┼──────────────────────────────────────┤
       │ QUẢN TRỊ         │ nhóm CAO NHẠY CẢM với kiểm soát tham │
       │                  │ nhũng và pháp quyền; nhóm thấp/trung │
       │                  │ gần như KHÔNG — vì khi tài khoá mạnh │
       │                  │ thì quản trị ít quyết định khả năng  │
       │                  │ trả nợ                               │
       ├──────────────────┼──────────────────────────────────────┤
       │ ★ THỜI ĐIỂM      │ nhóm CAO phát hành MUỘN trong năm    │
       │                  │ (quý III và IV) · nhóm thấp/trung    │
       │                  │ phát hành ĐẦU năm                    │
       │                  │ → nhóm cao phát hành mang tính PHẢN  │
       │                  │ ỨNG, có thể khi các nguồn khác đã    │
       │                  │ cạn hoặc áp lực ngân sách đã gay gắt │
       └──────────────────┴──────────────────────────────────────┘
       ⚠ Ở NHÓM CHÊNH LỆCH CAO: xác suất phát hành GIẢM NGAY CẢ
         KHI nhu cầu tái tài trợ (nợ ngắn hạn) TĂNG → chỉ dấu rõ
         ràng của ràng buộc CUNG chứ không phải thiếu nhu cầu
```

### Các đợt phát hành phi truyền thống

```text
       XÂY DỮ LIỆU MỚI: nước mới nổi NHỎ (GDP danh nghĩa DƯỚI 300
       TỶ ĐÔ) · từ 2012Q1 · chênh lệch TRÊN 437 ĐIỂM CƠ BẢN (giá
       trị trung bình của mẫu con này)
       ★ 84 ĐỢT PHÁT HÀNH · 16 NỀN KINH TẾ · chênh lệch từ 437
         tới 3.206 ĐIỂM CƠ BẢN
       năm nguồn: Bloomberg · Bond Radar · Cbonds · Perfect
       Information · bài báo trong vòng MỘT TUẦN trước và sau ngày
       phát hành
       ═══════════════════════════════════════════════════════════
       BỐN HÌNH MẪU
       ❶ phần lớn ở MỸ LATIN, bất kể dùng ngưỡng nào; và cũng là
          nơi quy mô phát hành (% GDP) LỚN NHẤT
       ❷ số đợt TĂNG theo thời gian — khoảng MỘT PHẦN BA toàn mẫu
          rơi vào 2019–2022, và quy mô bình quân cũng lớn hơn
       ❸ phần lớn diễn ra KHÔNG trong bối cảnh tái cơ cấu hay vỡ
          nợ, dù quy mô nhỏ hơn các đợt trong giai đoạn tái cơ cấu
       ❹ ★ phần lớn KHÔNG có chương trình IMF đang hoạt động,
          NHƯNG xác suất có chương trình IMF cao GẤP KHOẢNG NĂM
          LẦN so với toàn mẫu
       ═══════════════════════════════════════════════════════════
       ★★★ KIỂM CHỨNG MỆNH ĐỀ 2 CỦA MÔ HÌNH
       ┌─────────────────┬───────────────────────────────────────┐
       │ NGƯỠNG          │ TỶ LỆ CÓ ĐẶC TÍNH PHI TRUYỀN THỐNG    │
       ├─────────────────┼───────────────────────────────────────┤
       │ trên 437 đ.c.b  │ ★ 36%                                 │
       │ trên 600 đ.c.b  │ ★★ 42%                                │
       └─────────────────┴───────────────────────────────────────┘
       ba loại: BẢO LÃNH · TRÁI PHIẾU TRẢ DẦN (sinkable, phổ biến
       nhất) · TÀI SẢN BẢO ĐẢM
       ★ các đợt phi truyền thống có QUY MÔ LỚN HƠN các đợt thông
         thường ở cùng mức chênh lệch — đúng trực giác mô hình
       ═══════════════════════════════════════════════════════════
       ⚠ NHƯNG VÌ SAO MỘT SỐ NƯỚC VẪN PHÁT HÀNH TRÁI PHIẾU THÔNG
         THƯỜNG DÙ CHÊNH LỆCH CAO? Ba khả năng:
       ① CẦU ĐẦU CƠ hoặc tâm lý thị trường thuận lợi cho phép tiếp
          cận mà không cần bảo đảm thêm
       ② CẢI CÁCH CHÍNH SÁCH đáng tin hoặc cải thiện thể chế đã
          báo hiệu rủi ro vỡ nợ thấp hơn
       ③ RÀNG BUỘC PHÁP LÝ hoặc THỂ CHẾ hạn chế khả năng cấu trúc
          các công cụ phức tạp
       → lựa chọn công cụ nợ phụ thuộc vào cả điều kiện thị trường,
         chính sách VÀ thể chế, không chỉ vào mức chênh lệch
```

## Ba câu hỏi bài viết trả lời

1. Vì sao thị trường đóng lại với một số nước dù họ sẵn sàng trả lãi cao hơn?
2. Ngoài chênh lệch lợi suất, những yếu tố nào quyết định khả năng tiếp cận thị trường?
3. Các nước làm cách nào để phát hành được khi chênh lệch đã rất cao?

## Khái niệm cần biết

**Chênh lệch lợi suất và điểm cơ bản (spread, basis point).** Chênh lệch lợi suất là phần lãi mà một chính phủ phải trả thêm so với trái phiếu được coi là an toàn (thường là trái phiếu chính phủ Mỹ cùng kỳ hạn). Một điểm cơ bản bằng một phần trăm của một phần trăm, tức 0,01%. Ví dụ minh hoạ: nếu trái phiếu Mỹ trả 4% và một nước mới nổi phải trả 9% thì chênh lệch là 5 điểm phần trăm, tức 500 điểm cơ bản. Bài lấy mốc 500 điểm cơ bản để gọi là "chênh lệch cao", và chênh lệch đo bằng chỉ số EMBIG của J.P. Morgan.

**Tiếp cận thị trường (market access).** Khả năng một chính phủ bán được trái phiếu cho nhà đầu tư quốc tế. Bài đo nó bằng **lượng**: trong một quý, chính phủ có phát hành hay không. Điểm mấu chốt là tiếp cận thị trường không chỉ là chuyện giá: một nước có thể sẵn sàng trả lãi rất cao mà vẫn không ai mua.

**Phân phối tín dụng (credit rationing).** Tình trạng chủ nợ từ chối cho vay thay vì đòi lãi cao hơn, nên có những người vay không vay được ở bất kỳ mức lãi nào. Theo lý thuyết thông thường, giá (lãi suất) sẽ tăng tới khi cung gặp cầu; nhưng khi chủ nợ không biết rõ người vay, lãi cao hơn có thể làm khoản vay tệ hơn chứ không bù được rủi ro. Ví dụ minh hoạ: một ngân hàng biết rằng ai chịu vay ở lãi 30% thường là người sắp phá sản, nên thà không cho vay còn hơn nâng lãi lên 30%.

**Lựa chọn ngược và rủi ro đạo đức (adverse selection, moral hazard).** Đây là hai lý do khiến lãi cao không cứu được khoản vay. Lựa chọn ngược xảy ra trước khi vay: lãi cao hút đúng những người vay có khả năng vỡ nợ cao nhất, vì người tốt không chịu trả lãi đó. Rủi ro đạo đức xảy ra sau khi vay: lãi cao làm phần còn lại cho người vay khi trả được nợ nhỏ đi, nên họ ít cố gắng để trả. Ví dụ minh hoạ: nếu một dự án thành công đem về 110 và phải trả nợ 100, người vay chỉ giữ 10, nên động cơ cố gắng yếu hơn nhiều so với khi chỉ phải trả 60. Bài xây mô hình dựa trên rủi ro đạo đức.

**Ràng buộc tương thích động cơ (incentive compatibility constraint).** Điều kiện để người vay tự nguyện chọn nỗ lực cao: lợi ích của việc cố gắng phải ít nhất bằng chi phí của nó. Ràng buộc "binding" (ràng buộc chặt) nghĩa là điều kiện này đang ở sát giới hạn, chỉ cần lãi tăng thêm một chút là người vay sẽ chọn lười biếng. Khi đó chủ nợ không chịu cho vay theo hợp đồng thông thường. Toàn bộ hai mệnh đề của mô hình xoay quanh việc ràng buộc này có binding hay không.

**Tín hiệu (signal).** Thông tin mà mọi người đều quan sát được và có liên hệ với nỗ lực thật của người vay, ví dụ xếp hạng tín nhiệm. Nỗ lực cao thì dễ ra tín hiệu tốt hơn, nhưng không chắc chắn. Vì nỗ lực không đo được trực tiếp, hợp đồng nợ chỉ có thể gắn với tín hiệu. Đây là nền cho kết luận rằng người vay có thể "tự trói tay" bằng cách hứa trả lãi cao hơn nếu tín hiệu xấu.

**Rừng ngẫu nhiên và ROC-AUC.** Rừng ngẫu nhiên là mô hình học máy gồm rất nhiều cây quyết định, mỗi cây học trên một mẫu dữ liệu ngẫu nhiên, rồi bỏ phiếu chung; nó bắt được quan hệ phi tuyến và tương tác giữa các biến. ROC-AUC đo khả năng phân biệt hai nhóm của mô hình, từ 0,5 (đoán bừa) tới 1 (hoàn hảo). Ví dụ minh hoạ: AUC 0,84 nghĩa là nếu lấy ngẫu nhiên một quý có phát hành và một quý không phát hành, mô hình gán xác suất cao hơn cho quý có phát hành trong khoảng 84% số lần. Trong bài, rừng ngẫu nhiên đạt 0,84 so với 0,77 của logit.

**Nợ chính thức và hiệu ứng lấn át, lôi kéo (official debt, crowding out, crowding in).** Nợ chính thức là nợ với các chính phủ khác và tổ chức đa phương như IMF. Nó thường được ưu tiên trả trước, nên khi có nhiều nợ chính thức, chủ nợ tư nhân thấy phần còn lại cho mình ít đi và ngần ngại cho vay: đó là lấn át. Nhưng có chương trình IMF cũng là dấu hiệu nước đó đang bị giám sát và cam kết cải cách, có thể làm nhà đầu tư yên tâm hơn: đó là lôi kéo. Bài tìm thấy cả hai, tuỳ loại nợ chính thức.

## Nội dung chi tiết

### 1. Bối cảnh và ba nhánh tài liệu

**Phát hành nhiều hơn nhưng đắt hơn.** Trước đại dịch, phát hành quốc tế ròng của chính phủ các nước mới nổi và đang phát triển tăng vọt; giá trị danh nghĩa chứng khoán quốc tế đang lưu hành tăng gấp ba. Nhưng chi phí nợ bình quân vẫn cao và còn tăng thêm từ năm 2019. Tỷ lệ các đợt phát hành với chênh lệch trên 500 điểm cơ bản đạt kỷ lục 20% năm 2020 và từ đó tới nay giữ trên 25%.

Có một điểm tinh tế: chênh lệch EMBIG tính theo trọng số phát hành ròng lại giảm. Lý do là các đợt phát hành đắt tiền chủ yếu nhằm tái tài trợ (vay mới để trả nợ cũ đến hạn), nên khối lượng ròng của nhóm chênh lệch cao nhỏ. Tức là nhiều nước phải trả giá cao chỉ để giữ nguyên lượng nợ. Hình mẫu này gợi ý ràng buộc tiếp cận thị trường đang siết lại.

**Vì sao giá không tự cân bằng thị trường.** Trong một thị trường không có ma sát, giá điều chỉnh để cung gặp cầu: nước rủi ro hơn chỉ cần trả lãi cao hơn. Nhưng các nghiên cứu (Jaffee và Russell 1976; Stiglitz và Weiss 1981; Keeton 1997) chỉ ra rằng phân phối tín dụng có thể tồn tại như một trạng thái cân bằng khi có bất đối xứng thông tin, qua hai cơ chế:

1. **Lựa chọn ngược:** lãi suất cao hơn thu hút đúng những nước có khả năng vỡ nợ cao nhất.
2. **Rủi ro đạo đức:** lãi suất cao làm giảm động cơ trả nợ, vì phần còn lại cho người vay khi trả được nợ đã nhỏ đi.

Hai cơ chế này giải thích vì sao thị trường đóng hẳn với các nước có phần bù rủi ro vượt một ngưỡng nào đó.

**Ba nhánh tài liệu mà bài dựa vào:**

| Nhánh | Nội dung | Bài khác ở đâu |
|---|---|---|
| Khả năng phát hành nợ quốc tế của chính phủ | Nghiên cứu thực nghiệm bằng kinh tế lượng truyền thống, nhấn mạnh nền tảng của từng nước và các biến ngoại sinh: thanh khoản toàn cầu, động lực nợ trong nước, chất lượng thể chế, xếp hạng tín nhiệm, điều kiện thị trường sơ cấp và thứ cấp | Đây là nhánh gần nhất; bài dùng học máy để bắt quan hệ phi tuyến |
| Định giá nợ chính phủ và yếu tố quyết định chênh lệch | Kết quả khá không đồng nhất do khác biệt về mô hình, mẫu nước, giai đoạn và biến được xét | Bài dùng thước đo tiếp cận thị trường dựa trên lượng, nên đánh giá được chênh lệch như một biến giải thích |
| Vỡ nợ chính phủ và nợ phụ thuộc trạng thái | Mô hình vỡ nợ chiến lược cho rằng vỡ nợ tốn kém vì sau đó vay đắt hơn hoặc bị loại khỏi thị trường; thực nghiệm cho thấy hiệu ứng loại trừ giảm nhanh khi vỡ nợ được giải quyết | Bài đưa ra một dạng hợp đồng phụ thuộc tín hiệu theo chiều ngược |

### 2. Mô hình

**Cấu trúc.** Mô hình có hai kỳ. Người vay là chính phủ, ngại rủi ro. Chủ nợ quốc tế trung lập với rủi ro (chỉ quan tâm lợi nhuận kỳ vọng). Nền kinh tế có hai trạng thái, Tốt và Xấu.

| Thành phần | Nội dung |
|---|---|
| Ràng buộc ngân sách | Vốn đầu tư K bằng giá trị ròng A cộng nợ D. Ở kỳ sau, trong trạng thái Tốt, tiêu dùng bằng lợi suất R^G trừ nợ phải trả D(1+r). Trong trạng thái Xấu, lợi suất bằng 0 nên tiêu dùng bằng 0 |
| Giả định đơn giản hoá | Người vay luôn vỡ nợ ở trạng thái Xấu và chủ nợ không thu hồi được gì |
| Nỗ lực | Người vay chọn nỗ lực cao e_H hoặc thấp e_L. Nỗ lực cao tốn chi phí B lớn hơn 0 nhưng nâng xác suất trạng thái Tốt. Trong bối cảnh vĩ mô, nỗ lực là tăng thu thuế, cắt chi, hoặc cải cách cơ cấu thúc đẩy tăng trưởng |
| Thông tin | Chủ nợ không quan sát được nỗ lực, nên không thể ghi nỗ lực vào hợp đồng |
| Tín hiệu | Tín hiệu s nhận giá trị H (tốt) hoặc L (xấu), ví dụ xếp hạng tín nhiệm, quan sát được bởi mọi người. Xác suất ra tín hiệu tốt khi nỗ lực cao (q_H) lớn hơn khi nỗ lực thấp (q_L). Lãi suất có thể phụ thuộc tín hiệu, nhưng không phụ thuộc trạng thái thực |

**Vì sao lãi chỉ phụ thuộc tín hiệu, không phụ thuộc trạng thái thực.** Bài nêu rõ giới hạn của giả định này. Nếu lãi suất có thể gắn trực tiếp với trạng thái thực của nền kinh tế thì bảo hiểm hoàn toàn sẽ khả thi, kèm chuyển giao dương từ chủ nợ sang người vay ở trạng thái xấu. Nhưng giả định lãi suất chỉ phụ thuộc tín hiệu và phải dương là phù hợp với thực tế: công cụ nợ phụ thuộc trạng thái được dùng rất ít, và khi được dùng thì hiếm khi chuyển tiền cho người vay ở trạng thái xấu. Chứng quyền gắn GDP như của Argentina hay Hy Lạp trả thêm cho chủ nợ khi kinh tế tốt chứ không giảm nhẹ khi kinh tế xấu; điều khoản thiên tai như ở Grenada hay Barbados thường chỉ hoãn nghĩa vụ trả nợ tạm thời.

**Mệnh đề 1: ràng buộc tương thích động cơ không binding.** Nếu lợi ích của nỗ lực đủ lớn so với chi phí, người vay không cần lãi suất phụ thuộc tín hiệu mà đặt một mức lãi duy nhất r** = 1 / π(e_H), tức nghịch đảo của xác suất trạng thái Tốt khi nỗ lực cao. Chủ nợ được đền bù vừa đủ cho rủi ro, lợi nhuận kỳ vọng bằng 0, và không có phân phối tín dụng. Đây là phân bổ tốt nhất trong mô hình. Ví dụ minh hoạ: nếu xác suất trạng thái Tốt là 0,8 thì người vay phải trả 1 / 0,8 = 1,25 cho mỗi đồng vay, tức lãi 25%; chủ nợ thu 1,25 với xác suất 0,8 và 0 với xác suất 0,2, kỳ vọng đúng bằng 1 đồng đã cho vay.

**Mệnh đề 2: ràng buộc binding, công cụ "macro ngược".** Khi ràng buộc binding, người vay đặt lãi suất phụ thuộc tín hiệu và trả lãi cao hơn sau tín hiệu xấu: r_L** > r_H**. Trực giác: bằng cách cam kết trả lãi cao hơn khi tín hiệu xấu, người vay tự làm cho việc lười biếng trở nên kém hấp dẫn hơn (vì lười thì dễ ra tín hiệu xấu và bị phạt lãi). Điều đó nới lỏng ràng buộc động cơ và giúp người vay lấy lại quyền tiếp cận thị trường. Đây là chiều ngược với trái phiếu gắn GDP thông thường, vốn trả nhiều hơn khi kinh tế tốt.

**Ví dụ thật: El Salvador, tháng 4/2024.** El Salvador phát hành trái phiếu với lãi coupon sẽ tăng từ 0,25% lên 4,0% kể từ tháng 10/2025, trừ khi một trong hai điều kiện được đáp ứng:

1. một thoả thuận với IMF được phê duyệt, kèm các đợt rà soát định kỳ;
2. hoặc xếp hạng tín nhiệm từ ít nhất hai tổ chức được nâng so với mức ban đầu.

Đây chính là cơ chế cam kết chống rủi ro đạo đức mà Mệnh đề 2 mô tả, được dùng để tái tiếp cận thị trường vốn: chương trình IMF và nâng hạng là "tín hiệu tốt", không có chúng thì lãi tăng.

Mô hình cũng cho thấy khi ràng buộc binding, chủ nợ vẫn sẵn sàng cho vay nếu việc trả nợ được một bên thứ ba đáng tin bảo lãnh, hoặc nếu người vay thế chấp đủ tài sản bảo đảm. Đây là cơ sở cho phần kiểm chứng ở mục 7.

**Bốn tham số quan trọng ngoài chi phí vay.** Mô hình chỉ ra rằng chênh lệch không đủ để tóm tắt khả năng tiếp cận thị trường, vì các yếu tố sau cũng quyết định ràng buộc có binding hay không:

| Tham số | Ý nghĩa | Tác động |
|---|---|---|
| 1. Giá trị ròng A | "Phần hùn" của chính người vay; trong thực tế là dự trữ ngoại hối, mức nợ, vị thế đầu tư quốc tế ròng | A cao hơn thì người vay mất nhiều hơn nếu thất bại, nên ràng buộc nới ra |
| 2. Lợi suất R^H | Kỳ vọng tăng trưởng và thu ngân sách | Cao hơn thì nới ràng buộc |
| 3. Chi phí nỗ lực B | Chi phí kinh tế và chính trị của củng cố tài khoá | B thấp hơn thì nới ràng buộc |
| 4. Δπ | Mức nỗ lực làm tăng xác suất trạng thái Tốt | Lớn hơn thì nỗ lực đáng giá hơn |

Hai biến thực tế không có trong mô hình được diễn giải qua các tham số này:

- **Nhu cầu tài trợ gộp** (áp lực thanh khoản và nghĩa vụ trả nợ sắp tới) làm giảm đệm tài chính, tương đương một A thấp hơn.
- **Nợ chính thức**: vì được ưu tiên trả trước, nó làm giảm nguồn lực còn lại cho chủ nợ khác, tức hạ A trong mắt thị trường. Nhưng nó cũng có thể nâng chất lượng tín hiệu, vì cho thấy có giám sát và cam kết, tạo hiệu ứng lôi kéo thay vì lấn át.

**Giới hạn.** Mô hình là tĩnh, bỏ qua tương tác lặp lại. Nếu cho phép tương tác lặp lại thì sẽ có thêm các cơ chế động như uy tín, đe doạ trừng phạt trong tương lai, hay khuyến khích liên thời gian, cũng ảnh hưởng tới phân phối tín dụng và tiếp cận thị trường.

### 3. Định nghĩa tiếp cận thị trường

Tài liệu dùng hai loại thước đo. Thước đo dựa trên **giá** bắt nguồn từ khái niệm bất đối xứng thông tin của Stiglitz và Weiss (nhìn vào mức chênh lệch). Thước đo dựa trên **lượng** nhìn trực tiếp vào tần suất phát hành thực tế hoặc khối lượng phát hành gộp trên thị trường sơ cấp.

Bài chọn tần suất phát hành thực tế vì ba lý do:

1. Một số nước vẫn phát hành được ở chênh lệch khá cao; hiện tượng này đặc biệt quan trọng với các nền kinh tế tiên phong (nhóm mới nổi nhỏ, rủi ro cao hơn).
2. Thước đo dựa trên lượng cho phép đánh giá vai trò của sức mạnh bảng cân đối hay triển vọng vĩ mô tài khoá bên cạnh chênh lệch.
3. Nó cho phép xem các hình mẫu phi tuyến: tầm quan trọng của từng biến thay đổi thế nào ở các mức chênh lệch khác nhau.

**Bằng chứng ủng hộ.** Tần suất phát hành giảm khi chênh lệch tăng, và giảm dốc nhất trong khoảng 300–800 điểm cơ bản. Đồng thời, lãi suất phi rủi ro của Mỹ đóng vai trò rất nhỏ trong việc giải thích quyết định phát hành. Điều đó hàm ý yếu tố rủi ro riêng của từng nước, và cân nhắc về thứ tự ưu tiên các nguồn vốn, quan trọng hơn điều kiện tài chính toàn cầu.

**Hạn chế được thừa nhận.** Chỉ đếm số lần phát hành thì bỏ qua chất lượng của các đợt phát hành: kỳ hạn, giá, giao ước hay các điều khoản hợp đồng tốn kém hơn. Ngoài ra, ở một số nước chính phủ vay thay cho doanh nghiệp nhà nước, còn ở nước khác các doanh nghiệp này tự phát hành ra nước ngoài, nên nhóm sau trông như phát hành ít hơn ở cấp chính phủ một cách máy móc.

### 4. Phương pháp

**Vấn đề nhận diện cốt lõi.** Một chính phủ không vay trong một kỳ có thể vì chủ nợ không muốn cho vay (phía cung) hoặc vì chính phủ không muốn vay (phía cầu). Tách hai phía là rất khó: thiếu dữ liệu, cần giả định mạnh, và khi có phân phối tín dụng thì đường cung với đường cầu không cắt nhau. Bài không nhận diện được cú sốc cung và cầu, nhưng lập luận rằng nó tiến gần hơn nhờ các hiệu ứng tương tác phi tuyến của rừng ngẫu nhiên: chúng cho phép ước lượng tác động của một yếu tố cầu trong khi giữ cố định một yếu tố cung. Bài tự nhận rõ rằng kết quả phản ánh liên hệ dự báo, không phải quan hệ nhân quả.

**Dữ liệu.** Mẫu gồm 46 nước, 94 quý từ 2000Q1 tới 2023Q2, với 99 biến gốc. Biến phụ thuộc là nhị phân, bằng 1 nếu chính phủ phát hành ở quý t+3 hoặc t+4. Khoảng này được chọn vì đó là tầm dự báo mà mô hình dùng được trong thời gian thực, khi đã tính độ trễ công bố dữ liệu. Hai lớp khá cân bằng: 58% quan sát mang giá trị 1, nên không cần kỹ thuật lấy mẫu lại.

**Quy trình ba giai đoạn:**

| Giai đoạn | Nội dung |
|---|---|
| 1. Xử lý dữ liệu | Điền giá trị thiếu bằng k láng giềng gần nhất; thêm các biến biến đổi (% GDP, tăng trưởng, trung bình và phương sai tăng trưởng 5 quý); chia mẫu 90/10, huấn luyện 2001Q1–2021Q4, kiểm định 2022Q1–2023Q2 |
| 2. Huấn luyện | Kiểm định chéo theo cửa sổ mở rộng với 4 nếp gấp: mỗi nếp mở rộng giai đoạn huấn luyện, giai đoạn kiểm định giữ nguyên; có khoảng trống một kỳ giữa tập huấn luyện và tập kiểm định để chống rò rỉ dữ liệu (dùng nhầm thông tin tương lai) và mô phỏng đúng cách dùng thực tế. Song song, loại bỏ đặc trưng đệ quy giảm số biến xuống khoảng 50–80 |
| 3. Đánh giá | Diện tích dưới đường ROC trên mẫu ngoài |

Diện tích dưới đường ROC tăng khi số biến giảm, nghĩa là bỏ các biến ít thông tin hoặc trùng lặp làm mô hình tốt hơn.

**Kết quả đánh giá.** Rừng ngẫu nhiên đạt ROC-AUC 0,84; logit tốt nhất đạt 0,77. Chênh lệch 0,07 cho thấy tương tác phi tuyến thực sự quan trọng. Siêu tham số của rừng: 500 cây, 5 biến được xét mỗi lần chia nhánh, độ sâu tối đa 15, lấy mẫu bootstrap. Logit dùng phạt Ridge thuần (α=0) với λ=0,06. Ngưỡng xác suất tối đa hoá chỉ số F1 là 0,52 với rừng và 0,51 với logit.

**Cách đọc biểu đồ phụ thuộc từng phần.** Bài dùng loại biểu đồ này để xem hướng tác động của từng biến, và lưu ý rằng nó khác với tác động biên trong hồi quy. Vì nó lấy trung bình trên phân phối của mọi biến khác, mức thay đổi của xác suất dự báo thường khiêm tốn ngay cả khi biến đó có ảnh hưởng lớn, do phần phi tuyến và tương tác đã bị bình quân hoá.

### 5. Kết quả chính

**Mười lăm biến quan trọng nhất** (theo giá trị Shapley, tức phần đóng góp của từng biến vào dự báo), trong đó bốn trong năm biến đầu là về nợ đối ngoại:

| Thứ hạng | Biến |
|---|---|
| 1 | Nghĩa vụ quốc tế đang lưu hành của chính phủ (% GDP) |
| 2 | Dự trữ ngoại hối gộp (% GDP) |
| 3 | Thay đổi nghĩa vụ quốc tế so với cùng kỳ (phát hành ròng) |
| 4 | Nghĩa vụ quốc tế có kỳ hạn còn lại dưới một năm |
| 5 | Nợ đối ngoại ngắn hạn |
| 6 | Chênh lệch EMBIG |
| 7 | Tỷ giá |
| 8 | GDP danh nghĩa |
| 9 | Cán cân thương mại |
| 10 | Sử dụng tín dụng IMF |
| 11 | Nợ với chủ nợ chính thức |
| 12 | Nợ công gộp dự báo 5 năm |
| 13 | Nợ đối ngoại dài hạn |
| 14 | Pháp quyền |
| 15 | Nợ ròng 3 năm |

**Hướng tác động của từng biến:**

- **Nghĩa vụ đang lưu hành:** chính phủ có nhiều nghĩa vụ hơn, tức nhu cầu tài trợ lớn hơn, thì dễ phát hành hơn. Quan hệ phi tuyến, mạnh nhất ở mức nợ vừa rồi chững lại khi nợ cao. Việc chững lại có thể là dấu hiệu ràng buộc phía cung hoặc giới hạn tiếp cận khi gánh nặng nợ lên cao.
- **Thay đổi nghĩa vụ:** dễ phát hành nhất sau một mức tăng vừa phải; mức tăng lớn lại làm giảm xác suất phát hành.
- **Dự trữ ngoại hối:** nhiều dự trữ thì phát hành ít hơn. Điều này ngược với lý thuyết coi dự trữ là tín hiệu tín nhiệm. Bài giải thích rằng dự trữ được dùng và thay thế cho tài trợ bên ngoài: kênh cầu (ít cần vay) chi phối kênh cung (dễ được cho vay) trong dự báo của mô hình, và quan hệ âm này giữ nguyên ở mọi mẫu con.
- **Cán cân thương mại:** thặng dư thì phát hành ít hơn, vì đã tự có ngoại tệ đáp ứng nhu cầu.
- **Chế độ tỷ giá cố định:** phát hành ít hơn, vì chính phủ có ít lựa chọn để thu ngoại tệ trả nợ.
- **Tỷ giá danh nghĩa hiệu dụng:** phi tuyến rõ quanh mức 0; đồng tiền lên giá thì dễ phát hành, còn xuống giá thì không rõ.
- **Dự báo cán cân tài khoá 3 năm tới** (từ Triển vọng Kinh tế Thế giới): có bước nhảy mạnh quanh ngưỡng không; nước dự báo thặng dư dễ phát hành hơn hẳn nước dự báo thâm hụt.
- **Dự báo nợ công:** cao hơn thì phát hành ít hơn.
- **Nợ chính thức:** tác động được kỳ vọng là phức tạp, vì tài trợ chính thức có thể lấn át vốn tư nhân (phát tín hiệu khó khăn, gây lo ngại về thứ tự ưu tiên trả nợ) hoặc có hiệu ứng xúc tác (khôi phục niềm tin). Kết quả: nhiều nợ chính thức hơn đi kèm xác suất phát hành thấp hơn, nhưng quan hệ chững lại ở mức cao (tác động biên giảm dần).
- **Lãi suất của nợ chính thức mới:** thấp hơn thì dễ phát hành hơn.
- **GDP danh nghĩa:** là một trong các biến quan trọng nhất. Nền kinh tế lớn hơn dễ tiếp cận thị trường hơn nhờ hệ thống tài chính sâu hơn, được nhà đầu tư biết đến nhiều hơn và rủi ro đảo nợ được cảm nhận thấp hơn.
- **Pháp quyền:** tốt hơn thì dễ phát hành hơn. Quan hệ phi tuyến, tác động biên mạnh nhất giữa phân vị 15 và 40 của chỉ số pháp quyền. Nghĩa là uy tín thể chế có lợi suất giảm dần một khi thể chế đã vượt một ngưỡng nhất định.

**Ổn định theo thời gian.** Chia mẫu thành ba giai đoạn con, tầm quan trọng của các biến khá ổn định, với hai ngoại lệ. Tài trợ IMF và chế độ tỷ giá quan trọng hơn ở các giai đoạn đầu, phản ánh việc dựa nhiều hơn vào hỗ trợ đa phương và khung tỷ giá đa dạng hơn trước khủng hoảng tài chính toàn cầu. Ngược lại, các chỉ tiêu hướng về tương lai như tỷ lệ nợ dự báo nổi lên ở giai đoạn gần đây, có thể do chất lượng dự báo tốt hơn hoặc do nhà đầu tư chú ý hơn tới bền vững trung hạn.

### 6. Chênh lệch và việc tách cung với cầu

**Hình chữ U ngược.** Quan hệ giữa chênh lệch EMBIG và xác suất phát hành không đi xuống đều mà có hình chữ U ngược: xác suất tăng từ 0 lên đỉnh quanh 200 điểm cơ bản, sau đó giảm qua các mức 400, 600, 800 điểm, với mức rơi dốc nhất quanh 600 điểm.

Cách đọc của bài:

- Ở mức chênh lệch **thấp**, việc phát hành phản ánh **nhu cầu tài trợ**: chênh lệch tăng nhẹ đi kèm nhu cầu vay lớn hơn.
- Ở mức chênh lệch **cao**, việc phát hành phụ thuộc vào **nguồn cung vốn**: nhà đầu tư có chịu mua hay không, và do đó vào khả năng chính phủ cam kết đáng tin rằng sẽ không vỡ nợ.

Chênh lệch không phải biến quan trọng nhất; nó chỉ thực sự có ý nghĩa khi tương tác với các biến khác.

**Chia mẫu theo ba nhóm chênh lệch.** Nhóm thấp dưới phân vị 40 (khoảng dưới 200 điểm cơ bản), nhóm trung bình từ phân vị 40 tới 80 (khoảng 200–500 điểm), nhóm cao trên phân vị 80 (khoảng trên 500 điểm). Có 9 trong 15 biến quan trọng nhất là chung cho cả ba nhóm, nên nền tảng giống nhau; khác biệt nằm ở chi tiết, và các khác biệt đều chỉ về một hướng: nhóm chênh lệch cao chịu ràng buộc phía cung chặt hơn.

| Biến | Phát hiện | Giải thích |
|---|---|---|
| Nợ dài hạn đối ngoại (dấu ngược nhau) | Ở nhóm thấp, nợ dài hạn nhiều thì dễ phát hành nhất; ở nhóm trung bình và cao thì ngược lại | Với nước rủi ro thấp, nợ dài hạn là tín hiệu uy tín, giảm rủi ro đảo nợ, và nhà đầu tư thèm công cụ dài hạn. Với nước rủi ro cao, nợ dài hạn làm tăng rủi ro vỡ nợ qua kênh pha loãng nợ (nợ mới làm giảm giá trị nợ cũ), cùng các ràng buộc về cơ cấu nợ và đồng tiền |
| Nợ chính thức so với tín dụng IMF (dấu ngược nhau) | Ở nhóm cao, nợ chính thức nhiều thì ít phát hành (lấn át), nhưng tín dụng IMF nhiều thì phát hành nhiều hơn. Ở nhóm thấp và trung bình, gần như không nhạy với cả hai | Chương trình IMF có hiệu ứng tín hiệu khôi phục niềm tin thị trường. Nợ chính thức đã cam kết nhưng chưa giải ngân cũng nằm trong nhóm biến quan trọng, tức ngay cả nghĩa vụ ngoài bảng cân đối cũng lấn át vốn tư nhân |
| Tăng trưởng toàn cầu (dấu ngược nhau) | Nhóm cao phát hành khi kinh tế thế giới mạnh; nhóm thấp phát hành khi kinh tế thế giới yếu | Đây là bằng chứng rõ nhất về ràng buộc phía cung: nhóm rủi ro cao chỉ tiếp cận được khi nhà đầu tư có khẩu vị rủi ro và đang đi tìm lợi suất. Nhóm rủi ro thấp phát hành theo kiểu phản chu kỳ, theo nhu cầu tài khoá chứ không theo thời điểm thị trường |
| Dự trữ | Biến quan trọng nhất ở nhóm cao | Dự trữ là hình thức tự bảo hiểm đặc biệt quan trọng với nước rủi ro cao |
| Chế độ tỷ giá | Biến quan trọng thứ hai ở nhóm cao | Chế độ cứng nhắc báo hiệu dễ tổn thương trước cú sốc và ít khả năng điều chỉnh để tạo ngoại tệ |
| Quản trị | Nhóm cao nhạy với kiểm soát tham nhũng và pháp quyền; nhóm thấp và trung bình gần như không | Khi tài khoá mạnh thì quản trị ít quyết định khả năng trả nợ |
| Thời điểm trong năm | Nhóm cao phát hành muộn trong năm (quý III và IV); nhóm thấp và trung bình phát hành đầu năm | Nhóm cao phát hành mang tính phản ứng, có thể khi các nguồn khác đã cạn hoặc áp lực ngân sách đã gay gắt |

**Kết quả có ý nghĩa chẩn đoán nhất.** Ở nhóm chênh lệch cao, xác suất phát hành giảm ngay cả khi nhu cầu tái tài trợ, đo bằng nợ ngắn hạn, tăng lên. Một chính phủ có nghĩa vụ đến hạn nhiều hơn mà phát hành ít hơn thì không thể là do thiếu nhu cầu; đây là chỉ dấu rõ ràng của ràng buộc phía cung.

### 7. Phát hành ở chênh lệch cao

**Bộ dữ liệu mới.** Bài xây riêng một bộ dữ liệu cho các nền kinh tế mới nổi nhỏ (GDP danh nghĩa dưới 300 tỷ đô la), từ 2012Q1, với chênh lệch trên 437 điểm cơ bản (giá trị trung bình của mẫu con này). Kết quả là 84 đợt phát hành của 16 nền kinh tế, với chênh lệch từ 437 tới 3.206 điểm cơ bản. Thông tin về từng đợt lấy từ năm nguồn: Bloomberg, Bond Radar, Cbonds, Perfect Information, và các bài báo trong vòng một tuần trước và sau ngày phát hành.

**Bốn hình mẫu:**

1. Phần lớn các đợt ở Mỹ Latin, bất kể dùng ngưỡng nào, và đây cũng là nơi quy mô phát hành (% GDP) lớn nhất.
2. Số đợt tăng theo thời gian: khoảng một phần ba toàn mẫu rơi vào giai đoạn 2019–2022, và quy mô bình quân cũng lớn hơn.
3. Phần lớn diễn ra không trong bối cảnh tái cơ cấu hay vỡ nợ, dù quy mô nhỏ hơn các đợt trong giai đoạn tái cơ cấu.
4. Phần lớn không có chương trình IMF đang hoạt động, nhưng xác suất có chương trình IMF cao gấp khoảng năm lần so với toàn mẫu.

**Kiểm chứng Mệnh đề 2.** Mô hình dự báo rằng khi ràng buộc động cơ binding, người vay chỉ tiếp cận được thị trường nhờ công cụ đặc biệt. Dữ liệu xác nhận:

| Ngưỡng chênh lệch | Tỷ lệ đợt phát hành có đặc tính phi truyền thống |
|---|---|
| Trên 437 điểm cơ bản | 36% |
| Trên 600 điểm cơ bản | 42% |

Có ba loại đặc tính: bảo lãnh của bên thứ ba, trái phiếu trả dần (sinkable, trả gốc từng phần theo lịch thay vì một lần khi đáo hạn; đây là loại phổ biến nhất), và tài sản bảo đảm; một số đợt có điều khoản phụ thuộc trạng thái. Các đợt phi truyền thống có quy mô lớn hơn các đợt thông thường ở cùng mức chênh lệch, đúng như trực giác của mô hình: bảo đảm thêm cho phép vay nhiều hơn.

**Vì sao một số nước vẫn phát hành trái phiếu thông thường dù chênh lệch cao?** Bài nêu ba khả năng:

1. Cầu đầu cơ hoặc tâm lý thị trường thuận lợi cho phép tiếp cận mà không cần bảo đảm thêm.
2. Cải cách chính sách đáng tin hoặc cải thiện thể chế đã báo hiệu rủi ro vỡ nợ thấp hơn.
3. Ràng buộc pháp lý hoặc thể chế hạn chế khả năng cấu trúc các công cụ phức tạp.

Do đó lựa chọn công cụ nợ phụ thuộc vào cả điều kiện thị trường, chính sách và thể chế, không chỉ vào mức chênh lệch.

### 8. Kết luận và hàm ý

Bài rút ra ba bài học:

1. **Phải nhìn xa hơn chênh lệch lợi suất** khi đánh giá khả năng tiếp cận thị trường. Đóng góp cụ thể của bài là đưa các yếu tố hướng về tương lai, như dự báo cán cân tài khoá và nợ công, vào phân tích.
2. **Tính phi tuyến là quan trọng.** Tiếp cận thị trường được định hình bởi tương tác của nhiều biến, không bởi một yếu tố đơn lẻ; cùng một biến có thể đổi dấu tuỳ nhóm chênh lệch.
3. **Khi chịu sức ép, cần cả nền tảng vững lẫn công cụ tài chính được thiết kế riêng** để giữ được tiếp cận thị trường, như các đợt phát hành có bảo lãnh, trả dần hay tài sản bảo đảm.

Trong phụ lục, bài so sánh rừng ngẫu nhiên với logit. Hai mô hình nhất quán cao về các yếu tố quyết định chính, nhưng logit nhấn mạnh các chỉ tiêu phân loại và hướng về tương lai, còn rừng ngẫu nhiên ưu tiên các biến có khả năng tương tác hoặc phi tuyến cao như cơ cấu nợ, dự trữ và việc sử dụng tín dụng IMF. Hai cách nhìn được mô tả là bổ sung cho nhau chứ không mâu thuẫn.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Market access | Tiếp cận thị trường vốn quốc tế |
| Credit rationing | Phân phối tín dụng, chủ nợ từ chối cho vay ở mọi mức lãi |
| Adverse selection | Lựa chọn ngược, lãi cao hút đúng người vay rủi ro nhất |
| Moral hazard | Rủi ro đạo đức, lãi cao làm giảm động cơ trả nợ |
| Net worth (A) | Giá trị ròng của người vay, quyết định "phần hùn" |
| Signal quality | Chất lượng tín hiệu, ví dụ xếp hạng tín nhiệm |
| Participation constraint | Ràng buộc tham gia của chủ nợ |
| ICC | Ràng buộc tương thích động cơ |
| Reverse macro-contingent | Công cụ macro ngược: trả lãi cao hơn khi tín hiệu xấu |
| State-contingent debt | Nợ phụ thuộc trạng thái nền kinh tế |
| GDP-linked warrant | Chứng quyền gắn GDP, trả cho chủ nợ khi kinh tế tốt |
| Sinkable bond | Trái phiếu trả dần, hình thức phi truyền thống phổ biến nhất |
| EMBIG | Chỉ số Trái phiếu Thị trường Mới nổi Toàn cầu của J.P. Morgan |
| Basis point | Điểm cơ bản, bằng một phần trăm của một phần trăm |
| Frontier economy | Nền kinh tế tiên phong, nhóm mới nổi nhỏ và rủi ro cao hơn |
| GFN | Nhu cầu tài trợ gộp |
| Official debt | Nợ với chủ nợ chính thức, song phương và đa phương |
| Seniority | Tính ưu tiên trả nợ của chủ nợ chính thức |
| Crowding out / in | Lấn át / lôi kéo vốn tư nhân |
| Catalytic effect | Hiệu ứng xúc tác của tài trợ IMF |
| Debt dilution | Pha loãng nợ, phát hành mới làm giảm giá trị nợ cũ |
| Rollover risk | Rủi ro đảo nợ khi đến hạn |
| Search for yield | Đi tìm lợi suất, hành vi nhà đầu tư khi lãi suất thấp |
| Random forest | Rừng ngẫu nhiên, mô hình học máy phi tham số |
| Shapley value | Giá trị Shapley, đo đóng góp của từng biến vào dự báo |
| PDP | Biểu đồ phụ thuộc từng phần |
| ROC-AUC | Diện tích dưới đường đặc trưng hoạt động, đo khả năng phân loại |
| RFE | Loại bỏ đặc trưng đệ quy |
| Expanding window | Cửa sổ mở rộng, cách kiểm định chéo cho dữ liệu chuỗi thời gian |
| Data leakage | Rò rỉ dữ liệu, dùng thông tin tương lai để dự báo |
| Ridge regularization | Phạt L2, thu nhỏ hệ số mà không đưa về không |

## Câu nói đáng nhớ

> "Spreads alone, therefore, are not sufficient to summarize market access."

> "For high-spread countries, the probability of issuance declines even as refinancing needs increase, pointing toward more stringent supply constraints."

> "Thirty-six percent of these issuances include special features such as guarantees, contingencies, or collateral."

## Đánh giá và phát hiện đáng chú ý

### Mệnh đề 2 đập thẳng vào chương trình nghị sự nợ phụ thuộc trạng thái mà chính IMF cổ vũ

Đóng góp lý thuyết thật không phải chuyện phân phối tín dụng — điều đó đã có từ Stiglitz và Weiss năm 1981 — mà nằm ở chiều của công cụ: khi ràng buộc động cơ binding, hợp đồng tối ưu là **trả lãi cao hơn sau tín hiệu xấu**, r_L lớn hơn r_H.

Đây là mệnh đề khó chịu hơn nhiều so với cách bài trình bày. Suốt hơn một thập kỷ, IMF và Ngân hàng Thế giới đã vận động cho nợ phụ thuộc trạng thái theo chiều **thuận**: chứng quyền gắn GDP, điều khoản thiên tai kiểu Grenada và Barbados, điều khoản chống chịu khí hậu — tất cả nhằm giảm nhẹ nghĩa vụ đúng lúc nước vay gặp khó. Mô hình của bài nói rằng với đúng nhóm nước cần nó nhất, **công cụ theo chiều thuận làm ràng buộc siết thêm chứ không nới ra**, vì nó chính là phần thưởng cho việc không nỗ lực. Từ đó là một sự phân đôi mà giới hoạch định chính sách chưa thừa nhận: **điều khoản giảm nhẹ chỉ dành cho nước còn dư địa tín nhiệm; nước đã mất dư địa chỉ mua được quyền tiếp cận bằng điều khoản trừng phạt chính mình.**

Cái giá của điều khoản đó không nằm trong mô hình. Trái phiếu El Salvador tháng 4/2024 nâng coupon từ 0,25% lên 4,0% — gấp mười sáu lần — nếu không có thoả thuận IMF hoặc không được nâng hạng: nếu cải cách thất bại, nghĩa vụ trả nợ vọt lên đúng lúc năng lực trả nợ sụt xuống. Mô hình hai kỳ không nhìn thấy chi phí này vì không có kỳ thứ ba. Bài thừa nhận mô hình là tĩnh, nhưng mức độ nghiêm trọng bị nói nhẹ: **cơ chế mua được quyền tiếp cận hôm nay cũng chính là cơ chế nạp sẵn cuộc khủng hoảng ngày mai.**

### Bằng chứng quyết định không phải đường cong chữ U ngược mà là một dòng bị chôn ở cuối

Hình chữ U ngược, đỉnh quanh 200 điểm cơ bản và rơi dốc nhất quanh 600 điểm, sẽ là biểu đồ được trích nhiều nhất, nhưng nó chứng minh ít hơn vẻ ngoài. Đoạn đi lên từ 0 tới 200 điểm gần như chắc chắn là hiện tượng cầu: nước có chênh lệch gần bằng không thường là nước không cần vay ngoại tệ. Vì bài tự nhận không tách được cung khỏi cầu, đường cong này là hỗn hợp của hai chế độ chứ không phải một quan hệ hành vi.

Bằng chứng thật sự sắc nằm ở câu khác: **ở nhóm chênh lệch cao, xác suất phát hành giảm ngay cả khi nợ ngắn hạn — tức nhu cầu tái tài trợ — tăng lên.** Đây mới là thứ không giải thích được bằng phía cầu: một chính phủ có nghĩa vụ đến hạn lớn hơn mà lại phát hành ít hơn thì chỉ có thể là vì không được phép. Một dòng duy nhất này làm được việc mà cả đường cong chữ U không làm được, và nó bị đặt ở cuối một mục phụ.

Cùng hạng với nó là kết quả đảo dấu của tăng trưởng toàn cầu: nhóm chênh lệch cao phát hành khi kinh tế thế giới mạnh, nhóm chênh lệch thấp phát hành khi kinh tế thế giới yếu. Ý nghĩa thẳng thắn là **khả năng tiếp cận thị trường của nước rủi ro cao mang tính thuận chu kỳ hoàn toàn: họ chỉ vay được khi ít cần vay nhất.**

Hai kết quả này cũng giải thích vì sao kết luận của tài liệu cùng thư mục về tách lượng khỏi giá — Chu kỳ Tài chính Toàn cầu giải thích 64% biến động chênh lệch nhưng chỉ 8% biến động dòng vốn — không hề vô hại. Quan hệ giữa chênh lệch và khả năng phát hành **phi tuyến với một vùng sụp đổ quanh 500–800 điểm cơ bản**, nên với một nước đang ở 400 điểm, cú sốc toàn cầu đẩy chênh lệch lên thêm 250 điểm không phải chuyện giá đắt thêm mà là chuyện cửa đóng lại. **Chu kỳ toàn cầu là hiện tượng của giá ở phần lớn mẫu, và trở thành hiện tượng của lượng ở đuôi.**

### Hai kết quả về dự trữ ngoại hối mâu thuẫn nhau và bài không đối chiếu chúng

Kết quả tổng thể là dự trữ nhiều hơn đi kèm phát hành ít hơn, được diễn giải rằng dự trữ được dùng thay cho tài trợ bên ngoài — kênh cầu thắng kênh cung. Nhưng ở mẫu con chênh lệch cao, dự trữ lại là **biến quan trọng nhất** và được mô tả như hình thức tự bảo hiểm, tức ngôn ngữ của phía cung. Hai cách đọc đòi hỏi hai dấu ngược nhau, và bài không cho biết dấu trong mẫu con đó là gì.

Đây là chỗ cần dè dặt về phương pháp nói chung. Với 99 biến gốc tương quan cao với nhau, dấu của một biến đơn lẻ trên biểu đồ phụ thuộc từng phần là **đại lượng kém ổn định nhất** mà một mô hình rừng ngẫu nhiên có thể sinh ra — chính bài đã cảnh báo biểu đồ này không phải tác động biên trong hồi quy, rồi vẫn dùng nó để tuyên bố một kết quả đi ngược lý thuyết. Tương tự với ROC-AUC 0,84 so với 0,77 của logit: bốn trong năm biến quan trọng nhất đều đo quy mô và biến động của nghĩa vụ đang lưu hành, nên phần lớn năng lực dự báo có thể chỉ là **quán tính, ai đã phát hành thì lại phát hành**.

### Tín dụng IMF lôi kéo còn nợ chính thức khác lấn át: một nghịch lý về thứ tự ưu tiên bị để trống

Ở nhóm chênh lệch cao, nợ với chủ nợ chính thức làm giảm xác suất phát hành trong khi tín dụng IMF lại làm tăng; và trong bộ dữ liệu 84 đợt phát hành chênh lệch cao, xác suất có chương trình IMF đang hoạt động cao gấp khoảng năm lần toàn mẫu.

Bài quy khác biệt này cho hiệu ứng tín hiệu, đúng nhưng chưa đủ. Nếu kênh lấn át hoạt động qua thứ tự ưu tiên trả nợ thì **IMF lẽ ra phải là chủ nợ lấn át mạnh nhất**, do nó đứng trên tất cả. Việc thị trường vẫn phản ứng tích cực với IMF có nghĩa là hiệu ứng tín hiệu phải **lớn hơn hiệu ứng ưu tiên** ở riêng trường hợp này, và ngược lại ở mọi chủ nợ chính thức khác — một mệnh đề mạnh về việc thị trường định giá chất lượng giám sát, mà bài không nói ra.

Chi tiết sắc nhất là nợ chính thức **đã cam kết nhưng chưa giải ngân** cũng nằm trong nhóm biến quan trọng: nghĩa vụ chưa nằm trên bảng cân đối đã lấn át vốn tư nhân. Điểm này nối thẳng với tài liệu về thứ tự ưu tiên của chủ nợ và rủi ro quốc gia, và với tài liệu về hiểm hoạ của nợ chính phủ song phương.

### Với Việt Nam: đang ở nhánh đi lên, và ba con số nói thẳng nên làm gì

Việt Nam ở ngưỡng cận đầu tư với chênh lệch thấp hơn nhiều so với vùng 500 điểm, tức nằm ở **nhánh đi lên của đường cong chữ U** — vùng mà việc phát hành do nhu cầu tài trợ quyết định chứ không do nguồn cung vốn. Vị trí thuận lợi, nhưng cũng có nghĩa các bài học phải được đọc theo nhóm chênh lệch thấp, vì ba cặp biến quan trọng nhất **đảo dấu** giữa hai nhóm: nợ dài hạn đối ngoại có tác động dương ở nhóm thấp và âm ở nhóm cao, nên việc kéo dài kỳ hạn là tín hiệu uy tín với Việt Nam nhưng bị đọc là pha loãng nợ với một nước tiên phong đang ở 700 điểm. Đây là cảnh báo cụ thể về việc sao chép thực hành của nước khác mà không xét nhóm.

Ba con số đáng đưa vào thực tiễn. Thứ nhất, tác động biên của pháp quyền mạnh nhất **giữa phân vị 15 và 40** rồi giảm dần — lợi suất của cải cách thể chế cao nhất đúng ở dải mà Việt Nam đang đứng. Thứ hai, dự báo cán cân tài khoá ba năm tới tạo một **bước nhảy quanh ngưỡng không**: thị trường phân biệt giữa dự báo thặng dư và dự báo thâm hụt mạnh hơn nhiều so với phân biệt giữa thâm hụt 2% và 4%, tức dấu quan trọng hơn độ lớn. Thứ ba, biến dự báo mạnh nhất trong cả mô hình là **lượng nghĩa vụ quốc tế đang lưu hành**: người đã có mặt trên thị trường thì dễ quay lại. Với một thị trường trái phiếu quốc tế còn mỏng như của Việt Nam, duy trì một đường cong chuẩn và phát hành đều đặn là **một quyền chọn mua quyền tiếp cận trong tương lai**, và quyền chọn đó mất giá nếu không được duy trì.

Cuối cùng, hai biến quan trọng nhất ở nhóm chênh lệch cao là dự trữ ngoại hối và **chế độ tỷ giá**, với chế độ cứng nhắc bị đọc là dấu hiệu dễ tổn thương. Chế độ tỷ giá quản lý chặt của Việt Nam gần như không bị trừng phạt ở nhóm chênh lệch thấp, nhưng nó là một khoản nợ tiềm ẩn về mặt định giá, chỉ đáo hạn nếu Việt Nam rơi xuống nhóm rủi ro cao — đúng lúc không còn thời gian để sửa. Như tài liệu về lập kế hoạch vay nợ hằng năm nhấn mạnh: công việc phải làm xong trước khi cần đến nó.
