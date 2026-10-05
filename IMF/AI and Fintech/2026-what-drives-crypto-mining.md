# What Drives Crypto Mining? Evidence from Hardware Imports — Điều gì thúc đẩy hoạt động đào tiền mã hoá? Bằng chứng từ nhập khẩu phần cứng

**Nguồn:** IMF Working Paper.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Không ai biết chính xác mỗi nước đang đào bao nhiêu tiền mã hoá, vì hoạt động này được thiết kế để ẩn danh. Bài giải bài toán đo lường bằng một mẹo đơn giản: máy đào là phần cứng vật lý, phải đi qua hải quan, nên dữ liệu nhập khẩu cho ta biết mỗi nước đang lắp thêm bao nhiêu máy đào trong từng quý. Trên mẫu 45 nước từ quý 1/2019 đến quý 1/2023, hai yếu tố quyết định nơi và lúc đào là **giá bitcoin** và **giá điện**. Kết quả bất ngờ nhất: kiểm soát vốn càng chặt thì nhập khẩu máy đào càng **ít**. Tức là đào tiền mã hoá không phải kênh để lách kiểm soát vốn, mà bị chính kiểm soát vốn cản trở.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Thông tin nguồn lấy từ phần đầu văn bản. Không có bản PDF gốc để đối chiếu lại các câu trích tiếng Anh ở mục "Câu nói đáng nhớ". Số liệu và mốc chính sách Việt Nam, cùng các ví dụ ngoài bài (Trung Quốc, Kazakhstan), là bổ sung của người tổng hợp.

## Sơ đồ

### Vấn đề đo lường và cách giải

```text
       VÌ SAO KHÓ ĐO HOẠT ĐỘNG ĐÀO?
       · thợ đào KHÔNG phải khai báo với ai
       · địa chỉ ví không gắn với QUỐC GIA
       · "hashrate theo nước" hiện có đều dựa vào ĐỊA CHỈ IP mà thợ
         đào kết nối vào bể đào → VPN làm sai lệch NGHIÊM TRỌNG
       · sau lệnh cấm của Trung Quốc 2021, số liệu IP cho thấy hoạt
         động "chuyển" đi rồi "quay lại" một cách khó tin
                                │
                                ▼
       MẸO ĐO LƯỜNG CỦA BÀI
       máy đào ASIC là HÀNG HOÁ VẬT LÝ → phải qua HẢI QUAN
       · HS 8471.41.90 và HS 8471.50.40 — mã hải quan chứa phần lớn
         lượng nhập khẩu máy đào
       · dữ liệu hải quan là BẮT BUỘC KHAI BÁO, có từng nước, từng
         quý, có cả GIÁ TRỊ và KHỐI LƯỢNG
       · máy đào có VÒNG ĐỜI NGẮN (1,5–3 năm) → nhập khẩu phản ánh
         hoạt động HIỆN TẠI, không phải tồn kho quá khứ
                                │
                                ▼
       BA BƯỚC XỬ LÝ SỐ LIỆU
       ① CHỈ SỐ KHỐI LƯỢNG LASPEYRES: tách phần tăng do SỐ LƯỢNG
         khỏi phần tăng do GIÁ, dùng trọng số kỳ gốc
       ② CHỈ SỐ GIÁ ASIC HIỆU DỤNG: chuẩn hoá theo NĂNG LỰC BĂM
         (đô la trên terahash) chứ không theo số MÁY, vì thế hệ máy
         mới mạnh hơn nhiều lần
       ③ THUẬT TOÁN PHÁT HIỆN ĐỘT BIẾN: nhận diện các quý mà nhập
         khẩu vọt lên bất thường so với xu hướng riêng của nước đó
       ────────────────────────────────────────────────────────────
       ⚠ HẠN CHẾ được bài thừa nhận: mã HS cũng chứa thiết bị KHÔNG
       phải máy đào; bài xử lý bằng cách dựa vào BIẾN ĐỘNG theo thời
       gian và kiểm định độ vững
```

### Mô hình danh mục có chi phí kiểm soát vốn

```text
       NHÀ ĐẦU TƯ chọn phân bổ giữa:
              ┌─ TÀI SẢN TRONG NƯỚC (lợi suất an toàn)
              │
              ├─ ĐÀO TIỀN MÃ HOÁ (đầu tư vào ASIC)
              │    lợi suất kỳ vọng phụ thuộc:
              │    · giá bitcoin kỳ vọng Pb
              │    · độ biến động giá bitcoin σb
              │    · giá máy đào hiệu dụng Pa
              │    · độ khó mạng T (tổng hashrate toàn cầu)
              │    · giá điện Pe
              │
              └─ TÀI SẢN NƯỚC NGOÀI (chịu CHI PHÍ KIỂM SOÁT VỐN)
       ────────────────────────────────────────────────────────────
       GIẢ THUYẾT CẠNH TRANH về vai trò của kiểm soát vốn
       ❶ "KÊNH LÁCH": ở nước kiểm soát vốn chặt, đào tiền mã hoá là
         cách chuyển giá trị ra ngoài → kiểm soát càng chặt, nhập
         khẩu máy đào càng NHIỀU (hệ số DƯƠNG)
       ❷ "MA SÁT": kiểm soát vốn làm khó việc nhập khẩu thiết bị,
         chuyển tiền trả nhà cung cấp và hồi hương lợi nhuận →
         kiểm soát càng chặt, nhập khẩu càng ÍT (hệ số ÂM)
       → BÀI KIỂM ĐỊNH TRỰC TIẾP hai giả thuyết này
```

### Kết quả hồi quy chính

```text
       BIẾN PHỤ THUỘC: log khối lượng nhập khẩu máy đào
       ┌────────────────────────────┬──────────┬─────────────────┐
       │ BIẾN GIẢI THÍCH            │ HỆ SỐ    │ DIỄN GIẢI       │
       ├────────────────────────────┼──────────┼─────────────────┤
       │ ln Pb — giá bitcoin        │ +0,837***│ giá tăng 10% →  │
       │                            │          │ nhập khẩu ≈ +8% │
       ├────────────────────────────┼──────────┼─────────────────┤
       │ σb — biến động giá bitcoin │ −0,977***│ bất định làm    │
       │                            │          │ HOÃN đầu tư     │
       ├────────────────────────────┼──────────┼─────────────────┤
       │ ln Pa — giá máy đào        │ −0,467***│ cầu co giãn     │
       │                            │          │ theo giá thiết bị│
       ├────────────────────────────┼──────────┼─────────────────┤
       │ ln T — độ khó mạng         │ −1,846***│ ★ hệ số LỚN:    │
       │                            │          │ cạnh tranh toàn │
       │                            │          │ cầu bào mòn lợi │
       │                            │          │ nhuận rất nhanh │
       ├────────────────────────────┼──────────┼─────────────────┤
       │ ln Pe — giá điện           │ −3,393*  │ ★ hệ số LỚN     │
       │                            │          │ NHẤT: điện là   │
       │                            │          │ chi phí vận hành│
       │                            │          │ chi phối        │
       └────────────────────────────┴──────────┴─────────────────┘
       *** p<0,01 · * p<0,1
       ────────────────────────────────────────────────────────────
       PHÂN RÃ — độ co giãn theo giá bitcoin
       · trong chuỗi thời gian TOÀN CẦU ······ 0,75
       · trong biến thiên GIỮA CÁC NƯỚC ······ 1,60
       → phản ứng giữa các nước MẠNH GẤP ĐÔI, tức là khi giá tăng,
         hoạt động không chỉ MỞ RỘNG mà còn DỊCH CHUYỂN địa lý về
         nơi có điện rẻ
       ────────────────────────────────────────────────────────────
       MẪU: 45 nước, quý 1/2019 – quý 1/2023
```

## Ba câu hỏi bài viết trả lời

1. **Làm sao đo được hoạt động đào tiền mã hoá theo từng nước khi nó cố tình ẩn danh?** Đo đầu vào vật lý mà nó không thể thiếu: máy đào nhập khẩu qua hải quan.
2. **Yếu tố nào quyết định nơi và lúc đào?** Giá bitcoin (càng cao càng đào nhiều) và giá điện (càng cao càng đào ít, với tác động lớn nhất trong mô hình); thêm độ khó của mạng lưới và mức biến động của giá bitcoin.
3. **Đào tiền mã hoá có phải là cách lách kiểm soát vốn không?** Không, ít nhất trong giai đoạn mẫu. Nơi kiểm soát vốn chặt hơn thì nhập khẩu máy đào ít hơn.

## Khái niệm cần biết

**Đào tiền mã hoá (crypto mining).** Bitcoin không có ngân hàng trung tâm xác nhận giao dịch. Thay vào đó, hàng triệu máy tính trên thế giới thi nhau giải một bài toán tính toán; máy nào giải được trước sẽ được ghi một "khối" giao dịch mới vào sổ cái chung và nhận phần thưởng bằng bitcoin mới. Cơ chế này gọi là bằng chứng công việc (*proof of work*). Muốn thắng nhiều thì phải thử được nhiều phép tính mỗi giây, tức là cần máy mạnh và tốn nhiều điện. Vì vậy đào bitcoin về bản chất là **biến điện thành tiền mã hoá**.

**Năng lực băm (hashrate).** Số phép thử mà một máy hay cả mạng lưới làm được mỗi giây. Một máy đào phổ biến giai đoạn 2021–2022 đạt khoảng 100 terahash mỗi giây (TH/s), tức 100 nghìn tỷ phép thử mỗi giây.

**Độ khó mạng (network difficulty).** Mạng bitcoin tự điều chỉnh độ khó của bài toán khoảng hai tuần một lần để giữ nhịp trung bình 10 phút một khối. Khi có thêm nhiều máy tham gia, độ khó tăng lên, và mỗi máy nhận được ít bitcoin hơn. Ví dụ: nếu tổng năng lực băm toàn cầu tăng gấp đôi trong khi máy của bạn giữ nguyên, phần thưởng của bạn giảm khoảng một nửa. Đây là lý do lợi nhuận đào bị cạnh tranh bào mòn rất nhanh.

**Máy ASIC.** Mạch tích hợp chuyên dụng (*application-specific integrated circuit*), loại chip chỉ làm được một việc là tính hàm băm của bitcoin. Nó nhanh hơn máy tính thường hàng nghìn lần nhưng không dùng vào việc gì khác được. Vòng đời kinh tế chỉ khoảng một năm rưỡi đến ba năm, vì thế hệ máy mới hiệu quả hơn liên tục ra đời.

**Mã HS.** Hệ thống hài hoà mô tả và mã hoá hàng hoá (*Harmonized System*), bộ mã mà hải quan mọi nước dùng để phân loại hàng xuất nhập khẩu. Bài dùng hai mã HS 8471.41.90 và HS 8471.50.40, nhóm "máy xử lý dữ liệu", nơi phần lớn máy đào được khai báo.

**Chỉ số khối lượng Laspeyres.** Cách tách phần tăng do *số lượng* khỏi phần tăng do *giá*, bằng cách giữ giá cố định ở kỳ gốc. Ví dụ: quý 1 nhập 100 máy, giá 2.000 USD/máy, tổng 200.000 USD. Quý 2 nhập 100 máy, giá 4.000 USD/máy, tổng 400.000 USD. Nhìn giá trị thì nhập khẩu "tăng gấp đôi", nhưng tính theo giá kỳ gốc thì khối lượng không đổi (100 × 2.000 = 200.000). Điều này quan trọng vì giá máy đào nhảy theo giá bitcoin.

**Độ co giãn.** Phần trăm thay đổi của một biến khi biến kia thay đổi 1%. Trong mô hình mà cả hai vế đều lấy logarit, hệ số hồi quy chính là độ co giãn. Ví dụ: hệ số 0,837 của giá bitcoin nghĩa là giá bitcoin tăng 10% thì nhập khẩu máy đào tăng khoảng 8%.

**Kiểm soát vốn.** Các biện pháp nhà nước hạn chế tiền đi ra hoặc vào qua biên giới: giới hạn mua ngoại tệ, yêu cầu giấy phép chuyển tiền, thuế giao dịch vốn. Trong mô hình, kiểm soát vốn là một "chi phí" mà nhà đầu tư phải trả nếu muốn giữ tài sản ở nước ngoài.

**Giá trị quyền chọn thực (real option value).** Khi một khoản đầu tư không thể lấy lại (máy ASIC không bán lại được giá nếu ngừng đào) và tương lai bất định, việc *chờ thêm* có giá trị. Bất định càng cao, giá trị của việc chờ càng lớn, nên người ta hoãn đầu tư. Đây là lý do mức biến động của giá bitcoin làm giảm nhập khẩu máy đào.

**Ý nghĩa thống kê.** Ký hiệu \*\*\* (p < 0,01) nghĩa là: nếu yếu tố đó thật ra không có tác động gì, thì xác suất dữ liệu cho ra một hệ số mạnh như vậy chỉ dưới 1%; vì thế ta khá tin tác động là có thật. Ký hiệu \* (p < 0,1) nghĩa là xác suất đó dưới 10%, tức bằng chứng yếu hơn nhiều. Một hệ số lớn nhưng chỉ có một dấu sao thì đáng tin về chiều (âm hay dương), nhưng con số cụ thể chưa chắc.

## Nội dung chi tiết

### 1. Vấn đề đo lường

Hoạt động đào là một trong những hiện tượng kinh tế lớn khó đo nhất. Thợ đào không phải khai báo với ai, địa chỉ ví không gắn với quốc gia, và máy móc có thể chuyển sang nước khác trong vài tháng.

Thước đo phổ biến nhất hiện nay là "năng lực băm theo quốc gia", ước tính từ địa chỉ IP mà thợ đào dùng khi kết nối vào bể đào (*mining pool*, nơi nhiều thợ đào gộp năng lực và chia phần thưởng). Cách này bị sai lệch nghiêm trọng vì thợ đào dùng mạng riêng ảo (VPN) để che vị trí. Ví dụ rõ nhất: sau khi Trung Quốc cấm đào năm 2021, số liệu theo IP cho thấy năng lực băm của Trung Quốc rơi về gần 0 rồi vài tháng sau "quay lại" khoảng 21% toàn cầu (dữ liệu đến tháng 1/2022). Máy móc không thể di chuyển nhanh và lặng lẽ như vậy; cái thay đổi chủ yếu là cách che giấu.

### 2. Mẹo đo lường: theo dấu máy đào qua hải quan

Ý tưởng của bài là đo **đầu vào vật lý** mà hoạt động đào không thể thiếu. Máy ASIC phải được sản xuất (chủ yếu ở Trung Quốc), vận chuyển và thông quan. Dữ liệu hải quan có ba ưu điểm:

- **Bắt buộc khai báo**, nên khó che giấu hơn số liệu trên chuỗi khối hay địa chỉ IP.
- **Có theo từng nước và từng quý**, ghi cả giá trị và khối lượng.
- **Phản ánh hoạt động hiện tại**, vì máy đào hết đời sau một năm rưỡi đến ba năm. Nếu máy dùng được 20 năm như máy phát điện, lượng nhập khẩu một quý gần như không nói gì về số máy đang chạy. Với máy hao mòn nhanh như ASIC, nhập khẩu gần như bằng mức đầu tư mới để duy trì và mở rộng hoạt động.

Bài dùng hai mã HS 8471.41.90 và HS 8471.50.40, nơi phần lớn máy đào được khai báo. Hạn chế mà bài thừa nhận: hai mã này cũng chứa máy chủ và thiết bị tính toán khác. Bài xử lý bằng cách dựa vào **biến động theo thời gian trong từng nước** (máy chủ thông thường không tăng giảm theo giá bitcoin) thay vì mức tuyệt đối, cộng thêm các kiểm định độ vững.

### 3. Ba công cụ đo lường được xây dựng

1. **Chỉ số khối lượng Laspeyres** tách số lượng khỏi giá (xem ví dụ ở phần Khái niệm). Không có bước này, một quý giá máy tăng gấp đôi sẽ trông như nhập khẩu tăng gấp đôi.
2. **Chỉ số giá máy đào hiệu dụng** tính giá theo năng lực băm, bằng đô la trên mỗi TH/s, chứ không theo số máy. Ví dụ: máy cũ 14 TH/s giá 1.400 USD và máy mới 100 TH/s giá 5.000 USD. Tính theo máy thì máy mới đắt gấp 3,6 lần; tính theo năng lực thì máy mới chỉ 50 USD/TH/s so với 100 USD/TH/s, tức **rẻ bằng một nửa**. Chỉ cách tính này mới so được các thế hệ máy.
3. **Thuật toán phát hiện đột biến** đánh dấu những quý mà nhập khẩu của một nước vọt lên bất thường so với xu hướng riêng của nước đó. Công cụ này dùng để theo dõi các đợt "di cư" của hoạt động đào, ví dụ sau lệnh cấm của Trung Quốc năm 2021.

### 4. Mô hình lý thuyết: nhà đầu tư chia tiền vào đâu

Bài xây một mô hình phân bổ danh mục. Một nhà đầu tư có ba lựa chọn:

- **Tài sản trong nước**, lợi suất an toàn.
- **Mua máy đào**, lợi suất kỳ vọng phụ thuộc năm yếu tố: giá bitcoin kỳ vọng, mức biến động của giá đó, giá máy đào hiệu dụng, độ khó mạng, và giá điện.
- **Tài sản nước ngoài**, phải trả chi phí kiểm soát vốn.

Mô hình sinh ra hai giả thuyết đối lập về vai trò của kiểm soát vốn:

| Giả thuyết | Lập luận | Dự đoán |
|---|---|---|
| **Kênh lách** | Ở nước kiểm soát vốn chặt, đào bitcoin là cách biến điện trong nước thành tài sản dễ chuyển ra nước ngoài | Kiểm soát càng chặt, nhập máy đào càng **nhiều** (hệ số dương) |
| **Ma sát** | Kiểm soát vốn làm khó việc nhập máy, trả tiền cho nhà cung cấp nước ngoài và đưa lợi nhuận về | Kiểm soát càng chặt, nhập máy đào càng **ít** (hệ số âm) |

Bài kiểm định trực tiếp xem dữ liệu ủng hộ giả thuyết nào.

### 5. Kết quả thực nghiệm: cái gì quyết định lượng máy đào nhập khẩu

Biến phụ thuộc là logarit của khối lượng nhập khẩu máy đào. Kết quả chính:

| Yếu tố | Hệ số | Mức chắc chắn | Ý nghĩa thực tế |
|---|---|---|---|
| Giá bitcoin (log) | +0,837 | \*\*\* | Giá bitcoin tăng 10% → nhập máy đào tăng khoảng 8% |
| Biến động giá bitcoin | −0,977 | \*\*\* | Bất định cao → nhà đầu tư hoãn mua máy (giá trị của việc chờ tăng) |
| Giá máy đào hiệu dụng (log) | −0,467 | \*\*\* | Máy đắt hơn 10% → nhập ít đi khoảng 4% |
| Độ khó mạng (log) | −1,846 | \*\*\* | Độ khó tăng 10% → nhập ít đi khoảng 16%; cạnh tranh toàn cầu bào mòn lợi nhuận rất nhanh |
| Giá điện (log) | −3,393 | \* | Giá điện tăng 10% → nhập ít đi khoảng 28%; tác động lớn nhất nhưng ước lượng kém chắc nhất |

Ví dụ để cảm nhận độ lớn: giá điện là yếu tố có hệ số lớn gấp khoảng bốn lần giá bitcoin. Nếu một nước tăng giá điện cho nhóm khách hàng này thêm 10%, tác động lên hoạt động đào (khoảng −28%) gần tương đương với việc giá bitcoin giảm một phần ba.

**Phân rã độ co giãn theo giá bitcoin.** Bài tách độ co giãn 0,837 thành hai phần:

- Khi nhìn **toàn cầu theo thời gian** (giá bitcoin lên thì cả thế giới nhập bao nhiêu máy), độ co giãn là **0,75**.
- Khi nhìn **giữa các nước** (giá lên thì nước nào nhận thêm máy), độ co giãn là **1,60**, gấp đôi.

Nghĩa là khi giá bitcoin tăng, hoạt động đào không chỉ mở rộng về tổng quy mô mà chủ yếu **di chuyển** về những nơi có điện rẻ. Đây là ngành đi tìm chênh lệch giá điện nhiều hơn là ngành công nghiệp gắn với một chỗ.

### 6. Kiểm soát vốn: kết quả bất ngờ

Hệ số của chi phí kiểm soát vốn mang **dấu âm và lớn**. Dữ liệu bác bỏ giả thuyết kênh lách và ủng hộ giả thuyết ma sát.

Lý do: đào ở quy mô thương mại không làm lén được. Một trại đào 1.000 máy cần nhập khẩu thiết bị chính ngạch trị giá vài triệu đô la, hợp đồng điện công nghiệp vài megawatt, nhà xưởng, chuyển tiền quốc tế cho nhà cung cấp, và đường đưa lợi nhuận về. Mỗi bước đều đi qua đúng những điểm mà kiểm soát vốn được đặt vào.

Bài lưu ý phạm vi của kết luận: nó **không** nói tiền mã hoá không phải kênh rò rỉ vốn. Nó chỉ nói **việc đào** không phải kênh đó. Kênh rò rỉ, nếu có, nhiều khả năng nằm ở mua bán tiền mã hoá trên thị trường thứ cấp và ở stablecoin.

### 7. Hàm ý chính sách

- **Năng lượng:** vì độ nhạy với giá điện rất cao, chính sách giá điện là công cụ mạnh nhất để điều tiết hoạt động đào. Nước nào trợ giá điện là đang vô tình trợ cấp cho thợ đào, và nên tính đến khoản chi phí ngân sách đó.
- **Đo lường:** dữ liệu hải quan nên vào bộ công cụ giám sát chuẩn cho hoạt động tiền mã hoá, vì nó có sẵn, khách quan và khó che giấu.
- **Quản lý dòng vốn:** không có bằng chứng để coi nhập khẩu máy đào là lỗ hổng cần siết thêm.
- **Ổn định vĩ mô:** hoạt động đào gắn với giá một tài sản đầu cơ, nên nước nào để nó thành phần đáng kể của nhu cầu điện hoặc nhập khẩu là đang nhận thêm một nguồn biến động.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Crypto mining | Đào tiền mã hoá, dùng năng lực tính toán để xác thực giao dịch lấy phần thưởng |
| Proof of work | Bằng chứng công việc, cơ chế buộc máy phải tính toán (tốn điện) mới được ghi khối và nhận thưởng |
| ASIC | Mạch tích hợp chuyên dụng, phần cứng chuyên để đào, không dùng được việc khác |
| Hashrate | Năng lực băm, tổng tốc độ tính toán của mạng, đo bằng hash mỗi giây |
| Network difficulty | Độ khó mạng, tự điều chỉnh theo tổng hashrate để giữ nhịp tạo khối |
| HS code | Mã Hệ thống Hài hoà, phân loại hàng hoá trong dữ liệu hải quan |
| Laspeyres volume index | Chỉ số khối lượng dùng trọng số kỳ gốc để tách lượng khỏi giá |
| Effective ASIC price | Giá máy đào chuẩn hoá theo năng lực băm, đô la trên terahash mỗi giây |
| Mining pool | Bể đào, nơi nhiều thợ đào gộp năng lực và chia phần thưởng |
| IP-based estimate | Ước tính dựa trên địa chỉ IP, bị sai lệch bởi mạng riêng ảo |
| Surge detection | Thuật toán phát hiện quý có nhập khẩu vọt lên bất thường |
| Portfolio model | Mô hình phân bổ danh mục giữa các loại tài sản có rủi ro khác nhau |
| Capital control cost | Chi phí do biện pháp quản lý dòng vốn áp lên giao dịch xuyên biên giới |
| Real option value | Giá trị quyền chọn thực, giá trị của việc chờ đợi khi bất định cao |
| Sunk cost | Chi phí chìm, khoản đầu tư vào ASIC không thể thu hồi nếu ngừng đào |
| Elasticity | Độ co giãn, phần trăm thay đổi của biến này khi biến kia đổi một phần trăm |
| Within-country variation | Biến thiên trong cùng một nước theo thời gian |
| Cross-country variation | Biến thiên giữa các nước, phản ánh dịch chuyển địa lý của hoạt động |
| Energy arbitrage | Arbitrage năng lượng, di chuyển tới nơi có điện rẻ nhất |
| Circumvention channel | Kênh lách, giả thuyết cho rằng đào giúp chuyển giá trị qua biên giới |
| Stranded energy | Năng lượng mắc kẹt, nguồn điện không nối được vào lưới nên rất rẻ |

## Câu nói đáng nhớ

> "Mining rigs are physical goods. They must clear customs. That makes them visible."

> "Electricity prices carry the largest coefficient in the model: location follows power."

> "Capital controls do not channel activity into mining. They obstruct it."

## Đánh giá và phát hiện đáng chú ý

### Đóng góp lớn nhất là một nguyên lý nghiên cứu, không phải một hệ số

Bài giải một bài toán đo lường mà ngành đã loay hoay nhiều năm, và cách giải đáng học hơn kết quả. Nguyên lý có thể phát biểu tổng quát: **khi một hoạt động cố tình vô hình trong lĩnh vực của chính nó, hãy tìm đầu vào vật lý mà nó không thể thiếu, và đo cái đó**.

Hoạt động đào giấu được dấu vết trên chuỗi, giấu được địa chỉ IP bằng mạng riêng ảo, giấu được quyền sở hữu qua nhiều lớp pháp nhân. Nhưng nó không giấu được một container máy ASIC đi qua cửa khẩu. Và điều khiến phép đo này đặc biệt sạch là một đặc tính kinh tế mà bài khai thác rất khéo: máy đào có **vòng đời rất ngắn**, một năm rưỡi tới ba năm. Với một tài sản khấu hao chậm, lượng nhập khẩu trong một quý nói rất ít về trữ lượng đang vận hành. Với một tài sản hao mòn nhanh, nhập khẩu gần như là một thước đo trực tiếp của hoạt động hiện hành. Đây là một sự trùng hợp may mắn được nhận ra và dùng đúng chỗ.

Nguyên lý này chuyển giao được sang nhiều bài toán khác đang cấp bách hơn. Năng lực tính toán cho AI của một nước đo được qua nhập khẩu chip gia tốc. Quy mô trung tâm dữ liệu đo được qua hợp đồng đấu nối công suất điện. Và đáng chú ý là chính hai mã hải quan mà bài dùng hiện đang chứa ngày càng nhiều thiết bị tính toán cho AI chứ không chỉ máy đào — điều đó vừa làm phép đo cho bài toán cũ nhiễu đi, vừa biến cùng bộ dữ liệu ấy thành công cụ cho một bài toán mới và quan trọng hơn.

Có một hệ quả mỉa mai đáng ghi nhận. Chính tính vật lý khiến hoạt động đào đo được cũng là tính vật lý khiến nó **đánh thuế được, quản lý được và định vị được**. Cái gọi là tính phi biên giới của tiền mã hoá dừng lại đúng ở chỗ có điện.

### Kết quả về kiểm soát vốn bác bỏ một định kiến phổ biến, nhưng phạm vi của nó hẹp hơn cách nó thường được trích

Hệ số âm và lớn của chi phí kiểm soát vốn là kết quả có giá trị chính sách cao nhất trong bài, vì nó đảo ngược một niềm tin được lặp lại rất nhiều: rằng ở nước kiểm soát vốn chặt, đào tiền mã hoá trở thành cửa thoát cho dòng vốn.

Cơ chế mà bài đưa ra thuyết phục và đáng nhớ: đào ở quy mô thương mại **không phải hoạt động làm lén được**. Nó cần nhập khẩu thiết bị chính ngạch, cần hợp đồng điện công nghiệp lớn, cần mặt bằng nhà xưởng, cần chuyển tiền quốc tế cho nhà cung cấp và cần hồi hương lợi nhuận. Mỗi bước đều đi qua đúng những điểm nghẽn mà kiểm soát vốn được cài vào. Tức là nó không hưởng lợi từ kiểm soát vốn mà bị kiểm soát vốn cản trở.

Nhưng cần rất cẩn trọng với phạm vi của kết luận này, và bài có nói nhưng nói hơi khẽ. Nó không nói rằng tiền mã hoá không phải kênh rò rỉ vốn. Nó chỉ nói rằng **việc đào không phải kênh đó**. Và bài còn chỉ đúng chỗ mà kênh đó nhiều khả năng nằm: giao dịch trên thị trường thứ cấp và stablecoin.

Ghép với phân tích về stablecoin trong cùng thư mục, nơi việc lách quản lý dòng vốn được xếp là rủi ro thứ năm và với lý do rất cụ thể — token chuyển qua biên giới không đi qua hệ thống ngân hàng đại lý, nơi các biện pháp này vốn được thực thi — ta có một sự phân công nhiệm vụ rõ ràng giữa hai tài liệu. Dòng chảy bị rò không nằm ở phần cứng, nó nằm ở token. Với một cơ quan giám sát có nguồn lực hữu hạn, đây là một chỉ dẫn phân bổ nguồn lực có giá trị thật: **đừng dồn năng lực kiểm tra vào cửa khẩu, hãy dồn vào các cửa ngõ chuyển đổi giữa nội tệ và token**.

### Phân rã độ co giãn là kết quả sâu nhất và nó được giải thích sơ sài nhất

Con số 0,75 trong biến thiên theo thời gian so với 1,60 trong biến thiên giữa các nước được trình bày như một chi tiết kỹ thuật, kèm một câu diễn giải ngắn. Nhưng đó là kết quả nói nhiều nhất về bản chất kinh tế của ngành này.

Nó nói rằng hoạt động đào **dễ di chuyển hơn là dễ mở rộng**. Khi giá bitcoin tăng, phản ứng chủ đạo không phải là tổng công suất toàn cầu tăng theo cùng tỷ lệ, mà là công suất **dịch chuyển** về phía nơi có điện rẻ nhất. Nói cách khác, đây không phải một ngành công nghiệp mà là một dòng chảy đi tìm chênh lệch giá năng lượng.

Hệ quả thực tiễn nghiêm trọng hơn nhiều so với cách bài trình bày. Một nước đón nhận hoạt động đào đang tiếp nhận một nhu cầu điện rất lớn, rất tập trung, và có thể **biến mất trong một chu kỳ giá**. Trong khi đó, phần hạ tầng cần thiết để phục vụ nhu cầu ấy — trạm biến áp, đường dây, công suất phát — có tuổi thọ kinh tế ba tới bốn chục năm và thời gian xây dựng nhiều năm.

Sự lệch pha giữa tuổi thọ của tài sản và tuổi thọ của nhu cầu là một cái bẫy quy hoạch cổ điển. Nếu ngành điện đầu tư mở rộng để phục vụ các cụm đào, và các cụm ấy rời đi sau một chu kỳ giá, phần chi phí cố định ở lại và sẽ được phân bổ vào giá điện của mọi người tiêu dùng khác. Đây không phải một rủi ro giả thuyết mà là kết cục đã xảy ra ở một số vùng trên thế giới, và độ co giãn 1,60 của bài chính là con số nói rằng nó có xác suất cao. Kazakhstan là ví dụ rõ: sau lệnh cấm của Trung Quốc năm 2021, thợ đào đổ sang, tỷ trọng năng lực băm toàn cầu của Kazakhstan tăng từ 8,2% (tháng 4/2021) lên 18,1% (tháng 8/2021); lưới điện quá tải, chính phủ chuyển từ chào đón sang giới hạn điện năng cấp cho thợ đào và phải mua thêm điện từ Nga.

### Hệ số lớn nhất lại là hệ số kém chắc chắn nhất, và nó có vấn đề nội sinh

Cần công bằng với số liệu: hệ số của giá điện là âm 3,393, lớn nhất trong mô hình, nhưng nó chỉ có ý nghĩa ở mức mười phần trăm, trong khi mọi hệ số khác đều có ý nghĩa ở mức một phần trăm. Câu kết luận "địa điểm đi theo nguồn điện" đúng về chiều và đúng về cơ chế, nhưng **độ lớn của nó thì không được ước lượng chính xác**.

Có thêm một vấn đề mà bài không bàn tới: giá điện ở đây gần như chắc chắn là biến nội sinh. Hoạt động đào làm tăng nhu cầu điện tại chỗ, và ở những thị trường mà giá phản ánh cung cầu, điều đó đẩy giá lên. Tức là chiều nhân quả chạy cả hai hướng, và điều này làm hệ số ước lượng bị chệch — nhiều khả năng là chệch về phía ước lượng thấp độ nhạy thật, vì phần tăng giá do chính hoạt động đào gây ra làm suy yếu tương quan âm quan sát được.

Điều này không làm hỏng kết luận chính sách, mà ngược lại. Nếu độ nhạy thật còn lớn hơn con số ước lượng, thì công cụ giá điện còn mạnh hơn mức bài nói. Nhưng nó có nghĩa là không nên dùng con số 3,393 để làm phép tính định lượng cụ thể kiểu "tăng giá điện x phần trăm sẽ giảm hoạt động đào y phần trăm". Con số đó chưa đủ chắc để làm việc đó.

### Nước trợ giá điện tự chọn mình vào vị trí chịu thiệt, và đó là một kết quả tự chọn mẫu mà bài không phát biểu

Bài có nêu rằng các nước trợ giá điện đang vô tình trợ cấp cho hoạt động đào và nên nhận thức rõ chi phí tài khoá đó. Nhưng chính các con số của bài hàm chứa một kết luận mạnh hơn nhiều.

Vì độ co giãn theo giá điện là rất lớn và vì hoạt động đào dịch chuyển dễ hơn mở rộng, dòng chảy này **tự tìm tới nơi giá điện thấp nhất**. Mà nơi có giá điện thấp nhất, trong nhiều trường hợp, không phải nơi có chi phí sản xuất điện thấp nhất mà là nơi **trợ giá nhiều nhất**.

Ghép lại thì đây là một cơ chế tự chọn mẫu khá tàn nhẫn: những nước có ngân sách yếu nhất, đang phải trợ giá điện vì lý do xã hội, lại chính là những nước thu hút hoạt động đào mạnh nhất. Và điều họ thực sự đang làm là **xuất khẩu năng lượng được trợ giá dưới dạng một hàng hoá số**, với phần trợ giá chảy vào lợi nhuận của thợ đào còn chi phí tài khoá ở lại với nhà nước. Đây là một hình thức rò rỉ ngân sách không xuất hiện trong bất kỳ dòng nào của bảng cân đối ngân sách, vì nó đi qua giá chứ không qua chi.

Điều này cũng giải thích vì sao lệnh cấm thường kém hiệu quả hơn chính sách giá. Lệnh cấm đẩy hoạt động vào chỗ khuất nhưng không thay đổi động cơ kinh tế, trong khi một biểu giá điện riêng cho phụ tải tính toán mật độ cao — không trợ giá, tính theo công suất đăng ký, có điều khoản cắt tải khi hệ thống căng — loại bỏ chính khoản lợi nhuận đã kéo hoạt động tới.

### Với Việt Nam: đây là bài có công cụ dùng được ngay nhất trong cả thư mục

Phần lớn tài liệu trong thư mục này đưa ra khung phân tích hoặc khuyến nghị dài hạn. Bài này đưa ra một **phương pháp mà một cơ quan nhà nước có thể triển khai trong quý tới với chi phí gần bằng không**: dữ liệu hải quan theo mã hàng đã có sẵn, đã được khai báo bắt buộc, và chỉ cần xử lý theo ba bước mà bài mô tả để cho ra một thước đo khách quan về quy mô hoạt động đào trong nước theo từng quý.

Giá trị của việc đó không chỉ nằm ở con số. Nó nằm ở chỗ hiện nay các cuộc thảo luận về quy mô hoạt động tiền mã hoá ở Việt Nam gần như hoàn toàn dựa vào ước tính của bên thứ ba dùng phương pháp không kiểm chứng được. Một thước đo nội bộ, khách quan và có chuỗi thời gian sẽ thay đổi chất lượng của mọi cuộc thảo luận chính sách tiếp theo.

Việt Nam cũng đã có sẵn chuỗi số liệu đúng loại mà bài dùng, và từng dùng nó để quản lý. Theo Tổng cục Hải quan, từ năm 2017 đến tháng 4/2018 có khoảng 15.600 máy đào tiền mã hoá được nhập khẩu: hơn 9.300 máy trong năm 2017 và hơn 6.300 máy chỉ trong bốn tháng đầu năm 2018, tập trung ở TP. Hồ Chí Minh, Hà Nội và Đà Nẵng. Ngày 11/4/2018, Thủ tướng ban hành Chỉ thị 10/CT-TTg về tăng cường quản lý hoạt động liên quan tiền ảo. Sau đó Bộ Tài chính đề xuất tạm ngừng nhập khẩu máy đào; Bộ Công an đồng tình, nhưng Bộ Công Thương đề xuất không cấm. Điều còn thiếu là xử lý số liệu ấy một cách hệ thống theo ba bước của bài để có chuỗi theo quý.

Nhu cầu về một thước đo như vậy đang tăng vì khung pháp lý đã đổi. Luật Công nghiệp công nghệ số, được Quốc hội thông qua ngày 14/6/2025 và có hiệu lực từ 1/1/2026, lần đầu đưa ra khung pháp lý cho tài sản số, trong đó có tài sản mã hoá; Nghị quyết 05/2025/NQ-CP ngày 9/9/2025 cho thí điểm thị trường tài sản mã hoá trong 5 năm. Khi tài sản mã hoá được hợp pháp hoá một phần, câu hỏi "trong nước đang đào bao nhiêu, tiêu thụ bao nhiêu điện" chuyển từ chuyện quản lý sang chuyện thuế và quy hoạch điện.

Ba kết luận khác áp dụng trực tiếp.

**Công cụ hiệu quả là biểu giá điện, không phải lệnh cấm.** Với một hệ thống điện mà giá bán lẻ ở nhiều nhóm khách hàng chưa phản ánh đủ chi phí và công suất dự phòng từng căng trong mùa cao điểm, việc để một phụ tải chạy hai bốn trên bảy với hệ số sử dụng gần một trăm phần trăm đấu vào lưới ở mức giá chung là một khoản trợ cấp ẩn đáng kể. Bài cho thấy chính khoản đó là thứ quyết định, nên rút nó đi là biện pháp trúng đích nhất. Để hình dung quy mô: từ ngày 10/5/2025, giá bán lẻ điện bình quân là 2.204,07 đồng/kWh (chưa VAT), khoảng 8–9 cent Mỹ. Theo phép tính minh hoạ của người tổng hợp, một máy ASIC thế hệ mới tiêu thụ khoảng 3 kW, chạy liên tục là khoảng 26.000 kWh mỗi năm, tức gần 60 triệu đồng tiền điện; một trại 1.000 máy dùng khoảng 26 triệu kWh mỗi năm, tương đương hơn mười nghìn hộ gia đình dùng khoảng 200 kWh mỗi tháng. Đợt thiếu điện ở miền Bắc tháng 5–6/2023, khi nhiều hồ thuỷ điện lớn về mực nước chết, cho thấy vì sao biểu giá cho loại phụ tải này cần có điều khoản cắt tải khi hệ thống căng.

**Tính biến động là rủi ro quy hoạch, không chỉ là rủi ro tài chính.** Kết quả về độ co giãn giữa các nước nói rằng phụ tải này có thể đến rất nhanh và đi cũng rất nhanh. Bất kỳ quyết định đầu tư lưới điện nào được biện minh bằng nhu cầu từ nhóm khách hàng này đều nên được xem xét như một khoản đầu tư có rủi ro mắc kẹt cao.

**Và tin tốt: nguồn lực giám sát nên được chuyển hướng.** Kết quả về kiểm soát vốn nói rằng nhập khẩu máy đào không phải lỗ hổng của chế độ quản lý ngoại hối. Với một cơ quan có nguồn lực hữu hạn, điều đó cho phép ngừng tiêu tốn sự chú ý vào một kênh không rò rỉ và dồn nó sang kênh thực sự rò rỉ, là các cửa ngõ chuyển đổi giữa nội tệ và stablecoin. Đây là loại kết luận phủ định ít khi được công bố nhưng lại tiết kiệm được nhiều nhất.
