# The Evolution of Financial Market Infrastructures in a Tokenized Economy — Sự tiến hoá của hạ tầng thị trường tài chính trong nền kinh tế token hoá

**Nguồn:** IMF Working Paper No. WP/2026/136.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Hạ tầng thị trường tài chính tồn tại vì sổ sách của các bên tách rời nhau và cần được đối chiếu. Token hoá hứa hẹn xoá bỏ nhu cầu đó, nên câu hỏi tự nhiên là liệu trung tâm lưu ký, hệ thống quyết toán và đối tác bù trừ trung tâm có còn cần thiết. Bài trả lời rằng chức năng ghi sổ và quyết toán có thể được mã hoá vào sổ cái, nhưng chức năng quản trị rủi ro, xử lý vỡ nợ và quản lý khủng hoảng thì không. Kết quả nhiều khả năng là các hạ tầng lai, nơi phần kỹ thuật tự động hoá còn phần chịu trách nhiệm vẫn thuộc về một pháp nhân được giám sát.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Số hiệu working paper lấy từ trang bìa sau.

## Sơ đồ

### Vòng đời giao dịch và nơi rủi ro nảy sinh

```text
       ① GIAO DỊCH (trading) — khớp lệnh mua và bán
          RỦI RO: thao túng giá, truy cập không công bằng, sai lệch
          thông tin trước giao dịch
                                │
                                ▼
       ② XÁC NHẬN (confirmation) — hai bên thống nhất điều khoản
          RỦI RO: sai lệch dữ liệu giữa hai sổ sách, tranh chấp về
          nội dung đã thoả thuận
                                │
                                ▼
       ③ BÙ TRỪ (clearing) — tính nghĩa vụ ròng, quản lý rủi ro
          giữa lúc khớp lệnh và lúc quyết toán
          RỦI RO: ★ RỦI RO ĐỐI TÁC — bên kia có thể vỡ nợ trong
          khoảng thời gian này · rủi ro thay thế (phải mua lại ở
          giá khác) · rủi ro tài sản bảo đảm không đủ
          → đây là lý do TỒN TẠI của CCP
                                │
                                ▼
       ④ QUYẾT TOÁN (settlement) — chuyển tài sản và tiền
          RỦI RO: rủi ro gốc (một bên giao mà bên kia không trả) ·
          rủi ro thanh khoản trong ngày · rủi ro vận hành
                                │
                                ▼
       ⑤ LƯU KÝ (custody) — giữ và ghi nhận quyền sở hữu
          RỦI RO: mất tài sản, tài sản bị lẫn vào khối phá sản của
          bên lưu ký, sai sót ghi sổ
                                │
                                ▼
       ⑥ HẬU QUYẾT TOÁN — sự kiện doanh nghiệp, báo cáo, đối soát
          RỦI RO: xử lý sai sự kiện, thông tin thị trường thiếu
       ────────────────────────────────────────────────────────────
       LUẬN ĐIỂM: token hoá tấn công mạnh nhất vào ②, ③ và ④ bằng
       cách làm cho sổ sách CHUNG và quyết toán NGUYÊN TỬ. Nó tác
       động ÍT hơn tới ① và ⑥, và gần như KHÔNG giải quyết được
       phần QUẢN TRỊ RỦI RO trong ③.
```

### Bốn hạ tầng truyền thống và số phận của chúng

```text
       ┌────────┬────────────────────────┬───────────────────────┐
       │ HẠ TẦNG│ CHỨC NĂNG HIỆN NAY     │ TRONG THẾ GIỚI TOKEN  │
       ├────────┼────────────────────────┼───────────────────────┤
       │ CSD    │ ghi nhận quyền sở hữu  │ chức năng GHI SỔ có   │
       │ trung  │ chứng khoán, bảo đảm   │ thể chuyển lên sổ cái │
       │ tâm lưu│ tính toàn vẹn của đợt  │ NHƯNG ai bảo đảm token│
       │ ký     │ phát hành (không tạo   │ ứng đúng 1:1 với tài  │
       │        │ hoặc mất chứng khoán)  │ sản pháp lý? → vẫn cần│
       │        │                        │ MỘT bên chịu trách    │
       │        │                        │ nhiệm pháp lý         │
       ├────────┼────────────────────────┼───────────────────────┤
       │ SSS    │ quyết toán giao dịch   │ ★ BỊ THAY THẾ RÕ NHẤT:│
       │ hệ     │ chứng khoán, thường    │ quyết toán nguyên tử  │
       │ thống  │ T+1/T+2, cần DvP       │ trên sổ cái chung làm │
       │ quyết  │                        │ đúng việc này, tốt    │
       │ toán   │                        │ hơn và nhanh hơn      │
       ├────────┼────────────────────────┼───────────────────────┤
       │ CCP    │ xen vào giữa hai bên,  │ ★ KHÓ THAY THẾ NHẤT:  │
       │ đối tác│ trở thành người mua    │ quyết toán tức thời   │
       │ bù trừ │ của mọi người bán và   │ LOẠI BỎ rủi ro đối    │
       │ trung  │ ngược lại · bù trừ đa  │ tác trong giao dịch   │
       │ tâm    │ phương · quỹ vỡ nợ ·   │ GIAO NGAY, nhưng KHÔNG│
       │        │ quản lý khủng hoảng    │ giúp gì cho HỢP ĐỒNG  │
       │        │                        │ PHÁI SINH dài hạn ·   │
       │        │                        │ và mất bù trừ đa      │
       │        │                        │ phương nghĩa là NHU   │
       │        │                        │ CẦU THANH KHOẢN TĂNG  │
       ├────────┼────────────────────────┼───────────────────────┤
       │ TR     │ lưu trữ dữ liệu giao   │ về nguyên tắc DƯ THỪA │
       │ kho dữ │ dịch cho cơ quan quản  │ nếu cơ quan quản lý   │
       │ liệu   │ lý giám sát            │ đọc trực tiếp sổ cái ·│
       │ giao   │                        │ nhưng cần quyền truy  │
       │ dịch   │                        │ cập và khả năng diễn  │
       │        │                        │ giải dữ liệu thô      │
       └────────┴────────────────────────┴───────────────────────┘
       ★ NGHỊCH LÝ THANH KHOẢN: bù trừ đa phương của CCP giảm nhu
       cầu thanh khoản tới 90% ở một số thị trường. Quyết toán
       nguyên tử từng giao dịch loại bỏ lợi ích đó → cần NHIỀU tiền
       và tài sản sẵn sàng hơn, đúng lúc đòi hỏi phải có NGAY.
```

### Ba kiến trúc sổ cái

```text
       ❶ SỔ CÁI ĐƠN NHẤT (single ledger)
         mọi tài sản và mọi loại tiền trên MỘT sổ cái duy nhất
         ✔ nguyên tử hoàn hảo, không cần cầu nối, thanh khoản tập
           trung, khả năng kết hợp tối đa
         ✘ điểm hỏng đơn lẻ · rủi ro độc quyền · câu hỏi ai VẬN
           HÀNH và ai QUẢN TRỊ nó · khó đạt được về mặt chính trị
           ở cấp quốc tế
                                │
       ❷ SỔ CÁI CHUNG CÓ PHÂN VÙNG (common ledger, partitioned)
         một hạ tầng chung nhưng chia vùng theo loại tài sản, theo
         nhóm người tham gia hoặc theo tài phán
         ✔ giữ được phần lớn lợi ích nguyên tử trong vùng, đồng
           thời cho phép quy tắc khác nhau giữa các vùng
         ✘ giao dịch LIÊN VÙNG lại cần cơ chế điều phối
                                │
       ❸ SỔ CÁI TƯƠNG THÍCH (compatible ledgers)
         nhiều sổ cái độc lập, nối với nhau bằng CHUẨN CHUNG và
         GIAO THỨC LIÊN THÔNG
         ✔ thực tế nhất về chính trị, cho phép cạnh tranh và đổi
           mới, không có điểm hỏng đơn lẻ
         ✘ nguyên tử qua các chuỗi RẤT KHÓ · cầu nối là điểm yếu
           an ninh đã bị khai thác nhiều lần · thanh khoản PHÂN MẢNH
       ────────────────────────────────────────────────────────────
       ĐÁNH GIÁ CỦA BÀI: ❸ là con đường KHẢ THI trước mắt, ❷ là
       đích đến hợp lý ở cấp khu vực, ❶ khó xảy ra ở quy mô toàn cầu
```

### Rủi ro theo giai đoạn chuyển đổi

```text
       GIAI ĐOẠN 1 — THÍ ĐIỂM song song
       rủi ro: quy mô nhỏ nên rủi ro hệ thống thấp, NHƯNG rủi ro
       PHÁP LÝ cao vì khung chưa rõ · thí điểm thành công có thể
       tạo cảm giác an toàn giả về khả năng mở rộng
       giảm thiểu: hộp cát quản lý có giới hạn rõ, yêu cầu báo cáo
                                │
       GIAI ĐOẠN 2 — SONG SONG Ở QUY MÔ ĐÁNG KỂ
       rủi ro: ★ NGUY HIỂM NHẤT — thanh khoản PHÂN MẢNH giữa hai hệ
       thống · cầu nối trở thành điểm hỏng có tầm quan trọng hệ
       thống · arbitrage giữa hai chế độ quản lý · chi phí vận hành
       KÉP làm suy yếu chính các tổ chức đang chuyển đổi
       giảm thiểu: giám sát cầu nối như hạ tầng quan trọng, áp cùng
       chuẩn quản lý rủi ro cho cả hai bên
                                │
       GIAI ĐOẠN 3 — TOKEN HOÁ CHIẾM ƯU THẾ
       rủi ro: tập trung vào ít nhà vận hành sổ cái · rủi ro MÃ
       LỆNH trở thành rủi ro hệ thống · tốc độ lan truyền tăng vì
       mọi thứ tức thời và 24/7 · mất khả năng "bấm dừng" mà các
       hệ thống hiện tại vẫn có
       giảm thiểu: cơ chế ngắt mạch được thiết kế SẴN trong giao
       thức · yêu cầu kiểm toán mã bắt buộc · kế hoạch xử lý đổ vỡ
       cho nhà vận hành sổ cái
```

## Ba câu hỏi bài viết trả lời

1. Hạ tầng thị trường tài chính thực sự làm những chức năng gì, và token hoá thay thế được chức năng nào?
2. Ba kiến trúc sổ cái khả dĩ khác nhau ra sao về lợi ích và rủi ro?
3. Rủi ro nào lớn nhất trong quá trình chuyển đổi và nên xử lý thế nào?

## Dàn ý chi tiết

### 1. Vì sao hạ tầng thị trường tài chính tồn tại

- Câu trả lời lịch sử rất đơn giản: vì sổ sách của các bên tách rời nhau. Mỗi ngân hàng, mỗi nhà môi giới, mỗi nhà đầu tư giữ bản ghi riêng, và các bản ghi đó phải được đối chiếu. Hạ tầng thị trường tài chính ra đời để làm việc đối chiếu đó một cách tập trung, đáng tin cậy và có trách nhiệm pháp lý.
- Từ nhu cầu ban đầu ấy, các hạ tầng tích tụ thêm những chức năng khác không liên quan trực tiếp tới việc ghi sổ: quản lý rủi ro đối tác, xử lý tình huống thành viên vỡ nợ, cung cấp dữ liệu cho cơ quan giám sát, và đóng vai trò điểm can thiệp khi khủng hoảng.
- Bài lập luận rằng việc phân biệt hai nhóm chức năng này là chìa khoá để trả lời câu hỏi về tương lai. Token hoá tấn công trực diện vào nhóm thứ nhất, nhưng gần như không đụng tới nhóm thứ hai.

### 2. Vòng đời giao dịch và bản đồ rủi ro

- Bài đi qua sáu giai đoạn của vòng đời một giao dịch: giao dịch, xác nhận, bù trừ, quyết toán, lưu ký và hậu quyết toán, xác định rủi ro đặc trưng ở từng giai đoạn.
- Rủi ro nghiêm trọng nhất tập trung ở khoảng giữa khớp lệnh và quyết toán, nơi rủi ro đối tác tồn tại. Đây chính là lý do tồn tại của đối tác bù trừ trung tâm và của các yêu cầu ký quỹ.
- Token hoá với quyết toán nguyên tử loại bỏ hoàn toàn khoảng trống này đối với giao dịch giao ngay. Đó là lợi ích thật và lớn. Nhưng bài lưu ý rằng khoảng trống này chỉ là một trong các nguồn rủi ro, và với hợp đồng phái sinh có thời hạn dài, rủi ro đối tác tồn tại suốt vòng đời hợp đồng chứ không chỉ trong vài ngày quyết toán.

### 3. Số phận của bốn loại hạ tầng

- **Trung tâm lưu ký chứng khoán.** Chức năng ghi nhận quyền sở hữu có thể chuyển lên sổ cái. Nhưng chức năng bảo đảm tính toàn vẹn của đợt phát hành, tức là bảo đảm số token đang lưu hành khớp đúng với số chứng khoán được phát hành hợp pháp, vẫn cần một bên chịu trách nhiệm pháp lý. Mã lệnh có thể thực thi quy tắc nhưng không thể chịu trách nhiệm.
- **Hệ thống quyết toán chứng khoán.** Đây là nơi token hoá thay thế rõ nhất. Quyết toán nguyên tử trên sổ cái chung làm đúng việc mà hệ thống quyết toán làm, nhanh hơn và không cần khoảng chờ.
- **Đối tác bù trừ trung tâm.** Đây là trường hợp khó nhất và bài dành nhiều chỗ nhất cho nó. Quyết toán tức thời loại bỏ rủi ro đối tác trong giao dịch giao ngay nhưng không giúp gì cho hợp đồng phái sinh dài hạn. Quan trọng hơn, bù trừ đa phương của đối tác bù trừ trung tâm giảm nhu cầu thanh khoản tới khoảng 90% ở một số thị trường. Quyết toán nguyên tử từng giao dịch một loại bỏ lợi ích đó, đòi hỏi người tham gia phải có nhiều tiền và tài sản sẵn sàng hơn, và phải có ngay lập tức. Bài gọi đây là nghịch lý thanh khoản của quyết toán nguyên tử.
- **Kho dữ liệu giao dịch.** Về nguyên tắc trở nên dư thừa nếu cơ quan quản lý đọc trực tiếp sổ cái. Nhưng điều đó đòi hỏi quyền truy cập được bảo đảm về pháp lý và năng lực diễn giải dữ liệu thô, hai điều không tự động có.

### 4. Quản trị blockchain theo bốn chiều

- **Ai được tham gia:** hệ thống có phép hay không phép, và ai quyết định việc cấp phép.
- **Ai xác thực giao dịch:** cơ chế đồng thuận, và mức độ tập trung của quyền xác thực trong thực tế.
- **Ai được thay đổi quy tắc:** quy trình nâng cấp giao thức, ngưỡng phê duyệt, và cơ chế xử lý bất đồng.
- **Ai chịu trách nhiệm khi có sự cố:** đây là chiều mà bài cho là yếu nhất trong các thiết kế hiện có. Trong hệ thống truyền thống, luôn có một pháp nhân được cấp phép, chịu giám sát và có vốn để bù đắp tổn thất. Trong nhiều thiết kế phi tập trung, không có ai như vậy.
- Bài nhấn mạnh rằng mức độ phi tập trung trong thực tế thường thấp hơn nhiều so với trong thiết kế, và cơ quan quản lý nên đánh giá theo thực tế vận hành chứ không theo mô tả kỹ thuật.

### 5. Ba kiến trúc sổ cái

- **Sổ cái đơn nhất** cho lợi ích tối đa về nguyên tử và thanh khoản tập trung, nhưng tạo điểm hỏng đơn lẻ, rủi ro độc quyền và câu hỏi khó về việc ai vận hành và quản trị nó. Bài đánh giá phương án này khó đạt được ở quy mô toàn cầu vì lý do chính trị hơn là kỹ thuật.
- **Sổ cái chung có phân vùng** giữ được phần lớn lợi ích trong từng vùng đồng thời cho phép quy tắc khác nhau giữa các vùng, phù hợp với thực tế là các tài phán có luật khác nhau. Giao dịch liên vùng vẫn cần cơ chế điều phối.
- **Sổ cái tương thích** là nhiều sổ cái độc lập nối với nhau bằng chuẩn chung. Đây là con đường thực tế nhất về chính trị và cho phép cạnh tranh, nhưng nguyên tử qua các chuỗi rất khó đạt được, cầu nối là điểm yếu an ninh đã bị khai thác nhiều lần, và thanh khoản bị phân mảnh.
- Đánh giá của bài là sổ cái tương thích là con đường khả thi trước mắt, sổ cái chung có phân vùng là đích đến hợp lý ở cấp khu vực, và sổ cái đơn nhất khó xảy ra ở quy mô toàn cầu.

### 6. Rủi ro chuyển đổi và khái niệm hạ tầng lai

- Giai đoạn nguy hiểm nhất không phải là điểm khởi đầu hay điểm kết thúc mà là giai đoạn giữa, khi hai hệ thống cùng tồn tại ở quy mô đáng kể. Thanh khoản bị phân mảnh, cầu nối trở thành điểm hỏng có tầm quan trọng hệ thống, chênh lệch quy định tạo cơ hội arbitrage, và chi phí vận hành kép làm suy yếu chính các tổ chức đang chuyển đổi.
- Ở giai đoạn token hoá chiếm ưu thế, rủi ro chuyển sang tập trung vào ít nhà vận hành sổ cái, rủi ro mã lệnh trở thành rủi ro hệ thống, và tốc độ lan truyền tăng vì mọi thứ diễn ra tức thời và liên tục. Bài đặc biệt lưu ý việc mất khả năng bấm dừng mà các hệ thống hiện tại vẫn có, và đề xuất thiết kế sẵn cơ chế ngắt mạch vào chính giao thức.
- Kết luận là khái niệm hạ tầng lai: các tổ chức trong đó phần kỹ thuật được tự động hoá trên sổ cái, còn phần chịu trách nhiệm pháp lý, quản trị rủi ro và xử lý khủng hoảng vẫn thuộc về một pháp nhân được cấp phép và giám sát. Nguyên tắc chỉ đạo là cùng hoạt động thì cùng rủi ro và cùng quy định, và các Nguyên tắc dành cho Hạ tầng Thị trường Tài chính vẫn áp dụng được, tuy cần diễn giải lại cho môi trường mới.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| FMI | Hạ tầng thị trường tài chính |
| CSD | Trung tâm lưu ký chứng khoán, ghi nhận quyền sở hữu và bảo đảm toàn vẹn phát hành |
| SSS | Hệ thống quyết toán chứng khoán |
| CCP | Đối tác bù trừ trung tâm, xen vào giữa người mua và người bán |
| TR | Kho dữ liệu giao dịch, lưu trữ dữ liệu cho cơ quan giám sát |
| PFMI | Nguyên tắc dành cho Hạ tầng Thị trường Tài chính của CPMI-IOSCO |
| Clearing | Bù trừ, tính nghĩa vụ ròng và quản lý rủi ro trước khi quyết toán |
| Settlement | Quyết toán, chuyển giao tài sản và tiền để hoàn tất nghĩa vụ |
| Novation | Thế quyền, CCP thay thế hợp đồng gốc bằng hai hợp đồng với chính nó |
| Multilateral netting | Bù trừ đa phương, gộp nghĩa vụ nhiều bên để giảm nhu cầu thanh khoản |
| Atomic settlement | Quyết toán nguyên tử, hai chân giao dịch cùng xong hoặc cùng không |
| Liquidity paradox | Nghịch lý thanh khoản, quyết toán nguyên tử làm mất lợi ích bù trừ đa phương |
| Counterparty risk | Rủi ro đối tác không thực hiện nghĩa vụ |
| Principal risk | Rủi ro gốc, một bên giao tài sản mà không nhận được thanh toán |
| Default fund | Quỹ vỡ nợ do thành viên CCP đóng góp để bù tổn thất |
| Default management | Quản lý vỡ nợ, quy trình xử lý khi một thành viên không thực hiện nghĩa vụ |
| Issuance integrity | Tính toàn vẹn phát hành, số token khớp đúng số chứng khoán hợp pháp |
| Single ledger | Sổ cái đơn nhất, mọi tài sản trên một hạ tầng duy nhất |
| Partitioned ledger | Sổ cái chung có phân vùng theo tài sản, người tham gia hoặc tài phán |
| Compatible ledgers | Sổ cái tương thích, nhiều sổ cái độc lập nối bằng chuẩn chung |
| Cross-chain bridge | Cầu nối giữa các chuỗi, điểm yếu an ninh trọng yếu |
| Hybrid FMI | Hạ tầng lai, tự động hoá phần kỹ thuật nhưng giữ pháp nhân chịu trách nhiệm |
| Circuit breaker | Cơ chế ngắt mạch, dừng giao dịch khi có biến động bất thường |
| Consensus mechanism | Cơ chế đồng thuận xác định giao dịch nào được ghi vào sổ cái |
| Recovery and resolution | Khôi phục và xử lý đổ vỡ của một hạ tầng có tầm quan trọng hệ thống |

## Câu nói đáng nhớ

> "Financial market infrastructures exist because ledgers are separate. Tokenization attacks that premise directly."

> "Code can enforce a rule. It cannot bear responsibility for the rule being wrong."

> "Atomic settlement removes counterparty risk and, with it, the netting that made the system liquid."
