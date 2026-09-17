# What Drives Crypto Mining? Evidence from Hardware Imports — Điều gì thúc đẩy hoạt động đào tiền mã hoá? Bằng chứng từ nhập khẩu phần cứng

**Nguồn:** IMF Working Paper.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Hoạt động đào tiền mã hoá gần như không thể đo được vì nó cố tình ẩn danh và phân tán qua biên giới. Bài giải bài toán này bằng một mẹo đo lường: máy đào là phần cứng vật lý phải qua hải quan, nên dữ liệu nhập khẩu theo mã HS cho ta một thước đo hoạt động đào theo từng nước và từng quý. Kết quả thực nghiệm trên 45 nước từ quý 1/2019 đến quý 1/2023 cho thấy giá bitcoin và giá điện là hai yếu tố quyết định, và điều bất ngờ nhất là chi phí kiểm soát vốn có hệ số âm rất lớn: nhập khẩu máy đào không phải kênh lách kiểm soát vốn mà bị chính kiểm soát vốn cản trở.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Thông tin nguồn lấy từ phần đầu văn bản.

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

### Kết quả hồi quy chính (Bảng 2)

```text
       BIẾN PHỤ THUỘC: log khối lượng nhập khẩu máy đào
       ┌────────────────────────────┬──────────┬─────────────────┐
       │ BIẾN GIẢI THÍCH            │ HỆ SỐ    │ DIỄN GIẢI       │
       ├────────────────────────────┼──────────┼─────────────────┤
       │ ln Pb — giá bitcoin        │ +0,837***│ giá tăng 10% →  │
       │                            │          │ nhập khẩu +8,4% │
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
       PHÂN RÃ (Bảng 3) — độ co giãn theo giá bitcoin
       · trong chuỗi thời gian TOÀN CẦU ······ 0,75
       · trong biến thiên GIỮA CÁC NƯỚC ······ 1,60
       → phản ứng giữa các nước MẠNH GẤP ĐÔI, tức là khi giá tăng,
         hoạt động không chỉ MỞ RỘNG mà còn DỊCH CHUYỂN địa lý về
         nơi có điện rẻ
       ────────────────────────────────────────────────────────────
       MẪU: 45 nước, quý 1/2019 – quý 1/2023
```

## Ba câu hỏi bài viết trả lời

1. Làm sao đo được hoạt động đào tiền mã hoá theo từng nước khi nó cố tình ẩn danh?
2. Yếu tố nào thực sự quyết định nơi và thời điểm hoạt động đào diễn ra?
3. Đào tiền mã hoá có phải là kênh lách kiểm soát vốn không?

## Dàn ý chi tiết

### 1. Vấn đề đo lường

- Hoạt động đào tiền mã hoá là một trong những hiện tượng kinh tế lớn khó đo nhất. Thợ đào không có nghĩa vụ khai báo, địa chỉ ví không gắn với quốc gia, và hoạt động có thể di chuyển nhanh qua biên giới.
- Thước đo phổ biến hiện nay dựa trên địa chỉ IP mà thợ đào dùng khi kết nối vào bể đào. Cách này bị sai lệch nghiêm trọng bởi mạng riêng ảo. Sau lệnh cấm của Trung Quốc năm 2021, số liệu dựa trên IP cho thấy hoạt động chuyển ra khỏi Trung Quốc rồi quay lại theo cách khó tin về mặt vật lý, cho thấy đó chủ yếu là thay đổi trong việc che giấu chứ không phải thay đổi trong hoạt động thật.
- Cách tiếp cận của bài dựa trên một quan sát đơn giản: máy đào là phần cứng vật lý, phải được sản xuất, vận chuyển và thông quan. Dữ liệu hải quan là bắt buộc khai báo, có theo từng nước và từng quý, và ghi cả giá trị lẫn khối lượng.
- Hai mã hải quan được dùng là HS 8471.41.90 và HS 8471.50.40, chứa phần lớn lượng nhập khẩu máy đào chuyên dụng. Một đặc điểm thuận lợi là máy đào có vòng đời kinh tế rất ngắn, khoảng một năm rưỡi đến ba năm, nên lượng nhập khẩu phản ánh hoạt động hiện tại chứ không phải tồn kho tích luỹ từ quá khứ.
- Bài thừa nhận hạn chế: các mã này cũng chứa thiết bị không phải máy đào. Chiến lược xử lý là dựa vào biến động theo thời gian trong từng nước thay vì mức tuyệt đối, cùng với một loạt kiểm định độ vững.

### 2. Ba công cụ đo lường được xây dựng

- **Chỉ số khối lượng Laspeyres** tách phần tăng do số lượng khỏi phần tăng do giá, dùng trọng số kỳ gốc. Điều này quan trọng vì giá máy đào biến động rất mạnh theo chu kỳ giá bitcoin, nên giá trị nhập khẩu tính bằng đô la có thể tăng trong khi số máy thực tế giảm.
- **Chỉ số giá ASIC hiệu dụng** chuẩn hoá giá theo năng lực băm chứ không theo số máy, đo bằng đô la trên mỗi terahash mỗi giây. Đây là cách duy nhất so sánh được các thế hệ máy có hiệu năng chênh nhau nhiều lần.
- **Thuật toán phát hiện đột biến** nhận diện các quý mà lượng nhập khẩu vọt lên bất thường so với xu hướng riêng của nước đó, dùng để nghiên cứu các đợt di cư của hoạt động đào.

### 3. Mô hình lý thuyết

- Bài xây dựng một mô hình phân bổ danh mục trong đó nhà đầu tư chọn giữa tài sản trong nước có lợi suất an toàn, đầu tư vào máy đào, và tài sản nước ngoài chịu chi phí kiểm soát vốn.
- Lợi suất kỳ vọng của việc đào phụ thuộc vào giá bitcoin kỳ vọng, độ biến động của giá đó, giá máy đào hiệu dụng, độ khó của mạng lưới, và giá điện.
- Mô hình sinh ra hai giả thuyết cạnh tranh về vai trò của kiểm soát vốn. Giả thuyết kênh lách cho rằng ở nước có kiểm soát vốn chặt, đào tiền mã hoá là cách chuyển giá trị ra ngoài, nên kiểm soát càng chặt thì nhập khẩu máy đào càng nhiều. Giả thuyết ma sát cho rằng kiểm soát vốn làm khó việc nhập thiết bị, thanh toán cho nhà cung cấp nước ngoài và hồi hương lợi nhuận, nên tác động ngược lại.

### 4. Kết quả thực nghiệm

- Giá bitcoin có hệ số dương 0,837 và có ý nghĩa thống kê cao: giá tăng 10% làm khối lượng nhập khẩu máy đào tăng khoảng 8,4%.
- Độ biến động giá bitcoin có hệ số âm 0,977, phù hợp với lý thuyết quyền chọn thực: khi bất định cao, giá trị của việc chờ đợi tăng lên, nên nhà đầu tư hoãn cam kết vốn không thể thu hồi.
- Giá máy đào hiệu dụng có hệ số âm 0,467, cho thấy cầu co giãn đáng kể theo giá thiết bị.
- Độ khó mạng có hệ số âm rất lớn, 1,846. Điều này phản ánh bản chất cạnh tranh của việc đào: khi tổng năng lực băm toàn cầu tăng, phần thưởng cho mỗi đơn vị năng lực giảm tương ứng, bào mòn lợi nhuận rất nhanh.
- Giá điện có hệ số âm lớn nhất, 3,393, khẳng định điện là chi phí vận hành chi phối và là yếu tố quyết định địa điểm.
- Phân rã độ co giãn theo giá bitcoin cho kết quả đáng chú ý: trong chuỗi thời gian toàn cầu, độ co giãn là 0,75; trong biến thiên giữa các nước, là 1,60. Phản ứng giữa các nước mạnh gấp đôi, nghĩa là khi giá tăng, hoạt động không chỉ mở rộng về tổng quy mô mà còn dịch chuyển địa lý mạnh về phía những nơi có điện rẻ.

### 5. Kiểm soát vốn: kết quả bất ngờ

- Hệ số của biến chi phí kiểm soát vốn mang dấu âm và lớn, bác bỏ giả thuyết kênh lách và ủng hộ giả thuyết ma sát.
- Diễn giải là việc đào tiền mã hoá ở quy mô thương mại không phải hoạt động có thể làm lén lút. Nó đòi hỏi nhập khẩu thiết bị hợp pháp, hợp đồng điện năng lớn, mặt bằng công nghiệp và các khoản thanh toán quốc tế đáng kể. Chính những yêu cầu này khiến nó bị cản trở bởi kiểm soát vốn thay vì được hưởng lợi từ chúng.
- Kết quả này có hàm ý chính sách trực tiếp: lo ngại rằng đào tiền mã hoá sẽ trở thành lỗ hổng lớn trong chế độ quản lý dòng vốn không được dữ liệu ủng hộ, ít nhất ở giai đoạn mẫu. Các kênh lách vốn qua tiền mã hoá, nếu có, nhiều khả năng nằm ở giao dịch trên thị trường thứ cấp và ở stablecoin, chứ không ở việc đào.

### 6. Hàm ý chính sách

- Về năng lượng: độ co giãn cao theo giá điện có nghĩa là chính sách giá điện là công cụ hiệu quả nhất để điều tiết hoạt động đào. Các nước trợ giá điện đang vô tình trợ cấp cho hoạt động này và nên nhận thức rõ chi phí tài khoá đó.
- Về đo lường: dữ liệu hải quan nên được đưa vào bộ công cụ giám sát chuẩn cho hoạt động tiền mã hoá, vì nó khách quan, có sẵn và khó bị che giấu hơn các thước đo dựa trên hoạt động trên chuỗi.
- Về quản lý dòng vốn: bằng chứng không ủng hộ việc coi nhập khẩu máy đào là kênh rò rỉ vốn cần siết chặt thêm.
- Về ổn định vĩ mô: tính biến động cực cao của hoạt động này, gắn chặt với giá một tài sản đầu cơ, có nghĩa là các nước để hoạt động đào phát triển thành một phần đáng kể của nhu cầu điện hoặc của nhập khẩu đang tiếp nhận một nguồn biến động vĩ mô mới.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Crypto mining | Đào tiền mã hoá, dùng năng lực tính toán để xác thực giao dịch lấy phần thưởng |
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
