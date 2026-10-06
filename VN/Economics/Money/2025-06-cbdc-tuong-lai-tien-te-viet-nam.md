# Tiền pháp định kỹ thuật số: CBDC và tương lai tiền tệ ở Việt Nam

**Nguồn:** AI WikiMoney (wikimoney.ai.vn), chuyên mục Kinh tế › Tiền tệ, đăng ngày 11/6/2025. https://wikimoney.ai.vn/tien-phap-dinh-ky-thuat-so-cbdc-va-tuong-lai-tien-te-o-viet-nam-3716.html
**Tác giả:** WikiMoney Team (bài dẫn nhận định của TS. Đặng Minh Tuấn).
**Ý chính:** CBDC là dạng kỹ thuật số của tiền pháp định do ngân hàng trung ương phát hành và bảo đảm, khác tiền mã hóa ở chỗ quản lý tập trung và giá trị ổn định. Việt Nam bắt đầu quan tâm từ Quyết định 1255/QĐ-TTg (2017), được giao nghiên cứu thí điểm theo Quyết định 942/QĐ-TTg (2021), nhưng tiến độ chậm hơn Trung Quốc, Campuchia, Bahamas. CBDC hứa hẹn thanh toán hiệu quả, tài chính toàn diện, giảm chi phí tiền mặt và minh bạch hơn, nhưng vướng thói quen tiền mặt ở nông thôn, hạ tầng, an ninh mạng, quyền riêng tư và khung pháp lý.

> **Lưu ý:** Bài có một số nhầm lẫn khái niệm và sự kiện: (1) "NHNN có thể phát hành CBDC dưới dạng stablecoin" là lẫn lộn hai khái niệm; stablecoin là token do tư nhân phát hành neo giá vào tiền pháp định, còn CBDC là nợ trực tiếp của ngân hàng trung ương; (2) xếp Mỹ vào nhóm "thực nghiệm CBDC" không còn đúng ở thời điểm bài đăng: tháng 1/2025 Tổng thống Mỹ đã ký sắc lệnh cấm các cơ quan liên bang xây dựng CBDC; (3) Bakong của Campuchia là hệ thống thanh toán dựa trên blockchain, thường được gọi là "gần CBDC" hơn là một CBDC đúng nghĩa; (4) bảng so sánh tiến độ trong bản gốc bị vỡ định dạng (tiêu đề cột nằm lẫn giữa đoạn văn), và có ký tự lạ "鼓励" (tiếng Trung, nghĩa là "khuyến khích") lọt vào câu giải pháp "đẩy mạnh thanh toán không tiền mặt" (chỗ khuyến khích dùng ví điện tử và QR). Câu "17 tỷ giao dịch, 280 triệu tỷ đồng, tăng 120% so với 2023" không ghi rõ tăng 120% về số lượng hay giá trị.

## Sơ đồ

### CBDC đứng ở đâu giữa các loại tiền

```text
                        Ai phát hành?
              ┌──────────────┴───────────────┐
              ▼                              ▼
     Ngân hàng trung ương                Tư nhân
       │            │                 │            │
       ▼            ▼                 ▼            ▼
   Tiền mặt       CBDC          Tiền gửi NHTM,   Tiền mã hóa
   (vật chất)   (kỹ thuật số)   ví điện tử       (Bitcoin,
                  │              (kỹ thuật số)    stablecoin)
          ┌───────┴───────┐
          ▼               ▼
      Bán lẻ           Bán buôn
   (người dân)     (liên ngân hàng)
```

### Lộ trình CBDC của Việt Nam

```text
2017  QĐ 1255/QĐ-TTg: đề án khung pháp lý tài sản ảo, tiền điện tử
  │
2021  QĐ 942/QĐ-TTg (15/6): giao NHNN nghiên cứu, thí điểm tiền
  │   kỹ thuật số dựa trên blockchain giai đoạn 2021–2023
  │
2023  Kết thúc giai đoạn thí điểm ban đầu, chưa công bố kết quả
  │
2024  NHNN tiếp tục nghiên cứu với tổ chức nghiên cứu, fintech;
  │   9,13 triệu tài khoản Mobile Money (72% nông thôn)
  ▼
Tương lai: CBDC bán lẻ ở đô thị? Tham gia mBridge xuyên biên giới?
```

## Ba câu hỏi bài viết trả lời

1. CBDC là gì, khác tiền mã hóa ở đâu và có vai trò gì?
2. Việt Nam đã làm gì với CBDC, đang ở đâu so với các nước, và CBDC có thể mang lại lợi ích gì?
3. Việt Nam gặp thách thức nào khi triển khai CBDC và cần giải pháp gì?

## Khái niệm cần biết

**Tiền pháp định (fiat money).** Tiền có giá trị vì nhà nước quy định nó là phương tiện thanh toán hợp pháp, chứ không vì nó được đổi ra vàng hay hàng hoá. Tờ 100.000 đồng không chứa giá trị tự thân tương ứng, nhưng mọi người chấp nhận vì luật buộc phải chấp nhận và vì Ngân hàng Nhà nước (NHNN) đứng sau bảo đảm. CBDC chính là phiên bản kỹ thuật số của loại tiền này.

**CBDC (Central Bank Digital Currency, tiền kỹ thuật số của ngân hàng trung ương).** Dạng kỹ thuật số của tiền pháp định, do ngân hàng trung ương trực tiếp phát hành và bảo đảm. Khác với số dư trong tài khoản ngân hàng thương mại (là khoản ngân hàng đó nợ bạn), một đơn vị CBDC là khoản ngân hàng trung ương nợ trực tiếp người giữ, giống tiền mặt nhưng ở dạng số. Ví dụ minh hoạ: 1 triệu đồng CBDC trong ví điện tử của NHNN có giá trị đúng bằng 1 triệu đồng tiền giấy, chỉ khác là không cầm được. Đây là đối tượng của toàn bài.

**CBDC bán lẻ và CBDC bán buôn (retail, wholesale CBDC).** CBDC bán lẻ dành cho người dân và doanh nghiệp dùng thanh toán hằng ngày, như mua hàng, trả tiền điện. CBDC bán buôn chỉ dùng trong giao dịch giữa các ngân hàng và tổ chức tài chính, thường là các khoản rất lớn, ví dụ hai ngân hàng thanh toán cho nhau hàng nghìn tỷ đồng mỗi ngày. Việc phân biệt hai dạng này giúp hiểu bài đang nói CBDC sẽ phục vụ ai.

**Tiền mã hoá (cryptocurrency) và stablecoin.** Tiền mã hoá như Bitcoin do một mạng lưới tư nhân tạo ra, không có ngân hàng trung ương bảo đảm, giá biến động mạnh. Stablecoin là token do công ty tư nhân phát hành và neo giá vào một đồng tiền pháp định, ví dụ 1 token đổi 1 USD. Cả hai đều do tư nhân phát hành; đây là điểm cốt lõi khiến chúng khác CBDC, và vì vậy câu "NHNN phát hành CBDC dưới dạng stablecoin" trong bài là lẫn lộn khái niệm.

**Blockchain và sổ cái phân tán (DLT).** Cách lưu sổ giao dịch trong đó nhiều máy tính cùng giữ một bản sao và cùng xác nhận mỗi giao dịch mới, nên khó sửa lén. Blockchain là một dạng sổ cái phân tán, trong đó các giao dịch được gom thành khối nối tiếp nhau. Bài coi blockchain là công nghệ thường dùng cho CBDC và Quyết định 942/QĐ-TTg giao NHNN thí điểm tiền kỹ thuật số dựa trên blockchain.

**Mobile Money.** Dịch vụ thanh toán qua tài khoản gắn với số điện thoại, do nhà mạng cung cấp, không cần tài khoản ngân hàng. Ví dụ trong bài: đến tháng 6/2024 Việt Nam có 9,13 triệu tài khoản Mobile Money, 72% ở nông thôn. Bài dùng con số này để chỉ ra nhóm người dân mà CBDC có thể phục vụ.

**Tài chính toàn diện (financial inclusion).** Mục tiêu để mọi người dân, kể cả người ở vùng sâu, vùng xa và người chưa có tài khoản ngân hàng, tiếp cận được dịch vụ tài chính cơ bản như thanh toán, tiết kiệm. Đây là một trong bốn vai trò mà bài kỳ vọng ở CBDC.

## Nội dung chi tiết

### 1. Khái niệm và vai trò

CBDC (Central Bank Digital Currency) là dạng kỹ thuật số của tiền pháp định, do ngân hàng trung ương phát hành và bảo đảm. Để thấy CBDC đứng ở đâu, có thể chia các loại tiền theo hai câu hỏi: ai phát hành, và tiền ở dạng vật chất hay kỹ thuật số.

| | Dạng vật chất | Dạng kỹ thuật số |
|---|---|---|
| Ngân hàng trung ương phát hành | Tiền mặt | CBDC |
| Tư nhân phát hành | | Tiền gửi ở ngân hàng thương mại, số dư ví điện tử; tiền mã hoá (Bitcoin, stablecoin) |

Theo bài, CBDC khác Bitcoin ở ba điểm: được quản lý tập trung bởi ngân hàng trung ương; có giá trị ổn định, tương đương tiền giấy; và được pháp luật công nhận là phương tiện thanh toán hợp pháp.

CBDC có hai dạng: **bán lẻ**, dành cho người dân, và **bán buôn**, dùng trong giao dịch liên ngân hàng. Bài cho rằng CBDC thường dùng công nghệ blockchain hoặc sổ cái phân tán (DLT) để bảo đảm minh bạch và bảo mật.

Bài nêu bốn vai trò mà CBDC được kỳ vọng đảm nhận:

1. **Tăng hiệu quả thanh toán:** rút ngắn thời gian và giảm chi phí giao dịch, nhất là thanh toán xuyên biên giới vốn chậm và đắt.
2. **Tài chính toàn diện:** phục vụ những người chưa có tài khoản ngân hàng ở vùng sâu, vùng xa.
3. **Giảm chi phí tiền mặt:** bỏ bớt chi phí in tiền, vận chuyển và lưu trữ tiền mặt.
4. **Minh bạch:** blockchain cho phép truy vết giao dịch, hỗ trợ chống rửa tiền và gian lận.

### 2. Thử nghiệm CBDC của NHNN

**Các mốc chính sách.** Lộ trình của Việt Nam theo bài như sau:

| Năm | Mốc |
|---|---|
| 2017 | Quyết định 1255/QĐ-TTg phê duyệt đề án hoàn thiện khung pháp lý để quản lý tài sản ảo, tiền điện tử |
| 2021 (ngày 15/6) | Quyết định 942/QĐ-TTg giao NHNN nghiên cứu, thí điểm tiền kỹ thuật số dựa trên blockchain trong giai đoạn 2021–2023 |
| 2023 | Kết thúc giai đoạn thí điểm ban đầu; chưa công bố kết quả |
| 2024 | NHNN chưa công bố kết quả cụ thể, đang hợp tác với các tổ chức nghiên cứu và công ty fintech để đánh giá tính khả thi |
| Tương lai | Có thể triển khai CBDC bán lẻ ở đô thị và tham gia dự án thanh toán xuyên biên giới mBridge |

Bài cho rằng Việt Nam nằm trong nhóm 32 quốc gia đang thực nghiệm CBDC, cùng Mỹ, EU, Indonesia, Philippines. Như phần lưu ý đã ghi, việc xếp Mỹ vào nhóm này không còn đúng: tháng 1/2025, Tổng thống Mỹ đã ký sắc lệnh cấm các cơ quan liên bang xây dựng CBDC.

**Các khía cạnh có thể thử nghiệm.** Dựa trên định hướng chính sách và kinh nghiệm quốc tế, bài nêu bốn hướng:

- **Công nghệ:** dùng blockchain, học hỏi từ Bahamas hoặc Trung Quốc.
- **Thanh toán bán lẻ:** bắt đầu ở các đô thị lớn, nơi mã QR và ví điện tử đã phổ biến.
- **Thanh toán xuyên biên giới:** có thể tham gia các dự án như mBridge, nơi ngân hàng trung ương Trung Quốc, Hồng Kông, Thái Lan và UAE thử thanh toán quốc tế bằng CBDC.
- **Tài chính toàn diện:** tận dụng nền tảng Mobile Money, với 9,13 triệu tài khoản (72% ở nông thôn) tính đến tháng 6/2024.

**Tiến độ so với các nước.** Việt Nam đi chậm hơn các nước tiên phong là Trung Quốc (e-CNY), Campuchia (Bakong) và Bahamas (Sand Dollar). Theo TS. Đặng Minh Tuấn, nguyên nhân là Việt Nam cần xây dựng khung pháp lý, hạ tầng công nghệ và thay đổi thói quen của người dân. NHNN đang học hỏi Campuchia, nơi Bakong vận hành thành công từ năm 2020 (dù Bakong thường được coi là hệ thống thanh toán "gần CBDC" hơn là một CBDC đúng nghĩa).

Bảng so sánh tiến độ mà bài dẫn từ Atlantic Council và NHNN:

| Quốc gia | Giai đoạn | Thời gian bắt đầu | Trạng thái |
|---|---|---|---|
| Trung Quốc | Triển khai diện rộng | 2014 | Thử nghiệm e-CNY tại nhiều thành phố |
| Campuchia | Hoạt động chính thức | 2018 | Dự án Bakong vận hành từ 2020 |
| Việt Nam | Thực nghiệm | 2021 | Nghiên cứu và thử nghiệm giai đoạn đầu |
| Nhật Bản | Thử nghiệm | 2021 | Thử nghiệm đồng yên kỹ thuật số |

### 3. Lợi ích tiềm năng tại Việt Nam

Bài nêu bốn nhóm lợi ích nếu Việt Nam triển khai CBDC:

- **Thúc đẩy thanh toán không tiền mặt.** Nền tảng đã có sẵn: năm 2024 Việt Nam có 17 tỷ giao dịch không dùng tiền mặt, giá trị 280 triệu tỷ đồng, tăng 120% so với 2023 (theo Báo Điện tử VTV; bài không ghi rõ 120% là về số lượng hay giá trị). CBDC có thể được tích hợp với mã QR, ví điện tử và Mobile Money.
- **Tài chính toàn diện.** Vì 72% tài khoản Mobile Money nằm ở nông thôn, CBDC có thể đi theo cùng kênh để phục vụ người chưa có tài khoản ngân hàng.
- **Hỗ trợ kinh tế số.** CBDC có thể dùng trong các mô hình như Chợ 4.0 (chợ Đồng Xa, Hà Nội), các tuyến phố thương mại 4.0 ở Hà Nội, Đà Nẵng, TP.HCM, và được tích hợp vào dịch vụ công trực tuyến.
- **Giảm chi phí và tăng minh bạch.** Giảm chi phí in và vận chuyển tiền mặt; truy vết giao dịch để chống rửa tiền, gian lận.

### 4. Thách thức

Bài liệt kê năm thách thức:

| Thách thức | Nội dung |
|---|---|
| Thói quen tiền mặt | Hơn 90% giao dịch ở nông thôn vẫn dùng tiền mặt (theo Advertising Vietnam), nhất là ở người lớn tuổi |
| Hạ tầng | Internet ở vùng sâu không ổn định, thiếu thiết bị thanh toán; blockchain đòi hỏi đầu tư lớn vào hạ tầng và nhân lực |
| An ninh mạng | Nguy cơ lừa đảo, đánh cắp dữ liệu; cần xác thực sinh trắc học và mã hoá |
| Quyền riêng tư | CBDC quản lý tập trung có thể cho phép NHNN theo dõi mọi giao dịch; bài đề xuất thiết kế cơ chế bảo vệ dữ liệu, học hỏi Trung Quốc (e-CNY) |
| Khung pháp lý | Cần quy định mới về giao dịch số, chống rửa tiền và bảo mật dữ liệu |

Thách thức về quyền riêng tư là mặt trái của chính lợi ích "minh bạch" ở mục 3: một hệ thống cho phép truy vết mọi giao dịch để chống rửa tiền cũng là hệ thống cho phép nhìn thấy chi tiêu của mỗi người.

### 5. Triển vọng và giải pháp

**Triển vọng.** Bài kỳ vọng CBDC góp phần đưa Việt Nam tới một xã hội ít tiền mặt, nhất là ở đô thị; mở đường cho thanh toán xuyên biên giới qua mBridge; và hỗ trợ nhóm dân cư chưa tiếp cận ngân hàng thông qua Mobile Money và Chợ 4.0. Bài còn cho rằng NHNN có thể phát hành CBDC "dưới dạng stablecoin"; đây là cách nói lẫn lộn hai khái niệm, vì stablecoin do tư nhân phát hành còn CBDC là nợ trực tiếp của ngân hàng trung ương.

**Giải pháp.** Bài đề xuất năm nhóm:

1. **Đẩy mạnh thanh toán không tiền mặt,** chẳng hạn qua "Ngày không tiền mặt" (16/6), khuyến khích dùng ví điện tử và QR, để người dân quen với tiền số trước khi có CBDC.
2. **Đầu tư hạ tầng,** mở rộng internet và hạ tầng blockchain ở nông thôn, học theo Bakong.
3. **Tăng bảo mật:** mã hoá, sinh trắc học, phối hợp với cơ quan an ninh mạng.
4. **Hoàn thiện khung pháp lý** về phát hành, quản lý và sử dụng CBDC, tham khảo Trung Quốc và Bahamas.
5. **Học hỏi quốc tế:** Bakong, e-CNY, và tham gia mBridge.

### 6. Lợi ích cho người tiêu dùng

Theo bài, người tiêu dùng sẽ được:

- **Thanh toán nhanh, an toàn,** bài nói là "không cần trung gian", tiết kiệm chi phí và thời gian. Cần lưu ý rằng ở hầu hết các nước, CBDC được thiết kế theo mô hình hai tầng: ngân hàng trung ương phát hành, còn ngân hàng thương mại vẫn là bên phân phối tới người dân.
- **Quản lý tài chính dễ hơn** qua ví điện tử, ứng dụng di động, và hưởng ưu đãi từ ngân hàng, fintech.
- **Người vùng sâu, vùng xa tiếp cận được dịch vụ tài chính.**

Bài kèm ba mẹo: tìm hiểu cách dùng tiền số an toàn, cập nhật thông tin chính thức từ NHNN, và tham gia các chương trình khuyến khích thanh toán không dùng tiền mặt.

### 7. Kết luận của bài

Bài kết luận rằng CBDC là một bước ngoặt cho tương lai tiền tệ Việt Nam. Thử nghiệm của NHNN mới ở giai đoạn đầu nhưng mang tính chiến lược. Để đi tiếp, Việt Nam cần vượt qua thói quen dùng tiền mặt, yếu kém về hạ tầng và rủi ro an ninh mạng, đồng thời học hỏi kinh nghiệm của các nước đi trước như Trung Quốc, Campuchia và Bahamas.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| CBDC (Central Bank Digital Currency) | Tiền pháp định dạng số do ngân hàng trung ương phát hành và bảo đảm |
| CBDC bán lẻ (retail CBDC) | CBDC cho người dân, doanh nghiệp dùng thanh toán hằng ngày |
| CBDC bán buôn (wholesale CBDC) | CBDC dùng trong thanh toán giữa các ngân hàng, tổ chức tài chính |
| Sổ cái phân tán (Distributed Ledger Technology, DLT) | Cơ sở dữ liệu giao dịch được nhiều nút cùng lưu giữ, blockchain là một dạng |
| Stablecoin | Token do tư nhân phát hành, neo giá vào tiền pháp định hoặc tài sản |
| e-CNY | Nhân dân tệ kỹ thuật số của Trung Quốc |
| Bakong | Hệ thống thanh toán dựa trên blockchain của Ngân hàng Quốc gia Campuchia |
| Sand Dollar | CBDC của Bahamas, ra mắt năm 2020 |
| mBridge | Dự án thanh toán xuyên biên giới bằng CBDC nhiều ngân hàng trung ương |
| Mobile Money | Dịch vụ thanh toán qua tài khoản viễn thông, không cần tài khoản ngân hàng |
| Tài chính toàn diện (financial inclusion) | Mọi người dân tiếp cận được dịch vụ tài chính cơ bản |

## Câu nói đáng nhớ

> "Khác với các loại tiền mã hóa như Bitcoin, CBDC được quản lý tập trung, có giá trị ổn định tương đương tiền giấy và được công nhận là phương tiện thanh toán hợp pháp."

> "CBDC tập trung có thể cho phép NHNN theo dõi mọi giao dịch, gây lo ngại về quyền riêng tư."

> "Tiến độ triển khai CBDC tại Việt Nam chậm hơn các nước tiên phong như Trung Quốc (e-CNY), Campuchia (Bakong), hay Bahamas (Sand Dollar)."

## Đánh giá và phát hiện đáng chú ý

### Câu hỏi bị bỏ qua: Việt Nam có thực sự cần CBDC bán lẻ không?
Bài coi CBDC là "xu hướng tất yếu", nhưng chính số liệu của bài cho thấy Việt Nam đã có hệ thống chuyển tiền nhanh 24/7 miễn phí và mã QR liên thông giữa ngân hàng (VietQR), với hàng tỷ giao dịch mỗi năm. Phần lớn lợi ích được kỳ vọng của CBDC bán lẻ (thanh toán nhanh, rẻ, tức thời) đã đạt được bằng hệ thống này. Kinh nghiệm quốc tế cũng cho thấy CBDC bán lẻ khó cạnh tranh với thanh toán nhanh sẵn có: e-CNY có mức sử dụng thấp so với Alipay, WeChat Pay; eNaira của Nigeria gần như không được dùng. Giá trị thực của CBDC có lẽ nằm ở mảng bán buôn và xuyên biên giới hơn.

### Blockchain không phải điều kiện của CBDC
Bài gắn CBDC với blockchain như mặc định, theo đúng tinh thần Quyết định 942. Thực tế nhiều thiết kế CBDC (kể cả e-CNY ở tầng lõi) dùng cơ sở dữ liệu tập trung, vì một bên phát hành duy nhất không cần cơ chế đồng thuận phân tán. Đặt nặng blockchain có thể khiến chi phí và độ phức tạp tăng mà không thêm lợi ích. Tương tự, khẳng định "không cần trung gian" không đúng với mô hình hai tầng mà hầu hết các nước chọn, trong đó ngân hàng thương mại vẫn phân phối CBDC tới người dân.

### Rủi ro hệ thống ngân hàng bị bỏ sót
Thách thức kinh tế lớn nhất của CBDC bán lẻ không phải là thói quen hay hạ tầng mà là nguy cơ "rút tiền gửi khỏi ngân hàng": khi có biến cố, người dân có thể chuyển tức thì tiền gửi sang CBDC (tài sản phi rủi ro), làm ngân hàng mất nguồn vốn. Vì vậy các thiết kế như đồng euro số đề xuất hạn mức nắm giữ mỗi người và không trả lãi. Với Việt Nam, nơi ngân hàng là kênh dẫn vốn chủ đạo, đây là cân nhắc quan trọng hơn hầu hết các điểm bài liệt kê.

### Quyền riêng tư: "học từ e-CNY" là một lựa chọn gây tranh luận
Mô hình "ẩn danh có kiểm soát" của e-CNY cho phép ngân hàng trung ương thấy dữ liệu giao dịch ở mức nhất định, và đây chính là lý do một số nước phương Tây do dự với CBDC. Đề xuất học Trung Quốc về bảo vệ quyền riêng tư cần được đặt cạnh các mô hình khác (như thiết kế bảo vệ dữ liệu của đồng euro số) để người đọc thấy các đánh đổi.

### Bối cảnh bổ sung: thế giới đã thay đổi từ 2024
Ngoài sắc lệnh của Mỹ năm 2025, Ngân hàng Thanh toán Quốc tế (BIS) đã rút khỏi dự án mBridge vào cuối năm 2024, và dự án này hiện do các ngân hàng trung ương thành viên vận hành. Đồng thời, Việt Nam đang tập trung vào khung pháp lý cho tài sản số (Luật Công nghiệp công nghệ số), nhiều khả năng sẽ có tác động sớm hơn tới người dùng so với CBDC. Người đọc nên theo dõi các thông báo chính thức của NHNN thay vì kỳ vọng một đồng tiền số quốc gia trong ngắn hạn.
