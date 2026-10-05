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

## Khái niệm cần biết

**Hạ tầng thị trường tài chính (financial market infrastructure, FMI).** Các hệ thống dùng chung mà mọi ngân hàng, nhà môi giới và nhà đầu tư dựa vào để hoàn tất giao dịch: trung tâm lưu ký chứng khoán (CSD), hệ thống quyết toán chứng khoán (SSS), đối tác bù trừ trung tâm (CCP) và kho dữ liệu giao dịch (TR). Chúng giống "đường ray" của thị trường: người dùng ít khi thấy, nhưng nếu một hạ tầng ngừng chạy thì cả thị trường đứng lại. Bài hỏi liệu token hoá có làm các đường ray này trở nên thừa hay không.

**Token hoá và sổ cái chung (tokenization, shared ledger).** Token hoá là biểu diễn một tài sản (cổ phiếu, trái phiếu, tiền) dưới dạng một mục ghi trên sổ cái số dùng chung, thường là công nghệ chuỗi khối. Hiện nay mỗi tổ chức giữ sổ riêng và phải đối chiếu với nhau; trên sổ cái chung, mọi bên nhìn cùng một bản ghi. Ví dụ minh hoạ: khi nhà đầu tư A bán 100 trái phiếu cho B, thay vì ngân hàng của A, ngân hàng của B và trung tâm lưu ký cùng cập nhật ba sổ khác nhau rồi đối chiếu, chỉ có một dòng ghi chuyển 100 token từ ví A sang ví B. Đây là lý do token hoá "tấn công" vào lý do tồn tại của FMI.

**Bù trừ và quyết toán (clearing, settlement).** Bù trừ là bước tính xem sau khi khớp lệnh, ai nợ ai bao nhiêu, và quản lý rủi ro trong khoảng thời gian chờ. Quyết toán là bước thực sự chuyển chứng khoán và tiền để hoàn tất nghĩa vụ. Ví dụ: với chu kỳ T+2, lệnh khớp hôm thứ Hai thì tới thứ Tư mới quyết toán; trong hai ngày đó, các bên còn nợ nhau. Phân biệt hai bước này giúp hiểu bước nào token hoá thay thế được và bước nào không.

**Rủi ro đối tác và rủi ro gốc (counterparty risk, principal risk).** Rủi ro đối tác là khả năng bên kia vỡ nợ trước khi giao dịch hoàn tất; khi đó bạn phải mua hoặc bán lại ở giá khác (rủi ro thay thế). Rủi ro gốc nặng hơn: bạn đã giao tài sản nhưng bên kia không trả tiền, bạn mất toàn bộ giá trị. Ví dụ minh hoạ: bạn bán 1 tỷ đồng cổ phiếu, giao cổ phiếu trước, rồi người mua phá sản trước khi trả tiền; bạn mất 1 tỷ đồng. Hai rủi ro này là lý do có các hạ tầng như CCP và cơ chế giao chứng khoán đồng thời với thanh toán (DvP).

**Quyết toán nguyên tử (atomic settlement).** Hai chân của giao dịch (giao tài sản và trả tiền) cùng xảy ra trong một bước không thể tách rời: hoặc cả hai cùng xong, hoặc không chân nào xảy ra. Từ "nguyên tử" ở đây nghĩa là không chia nhỏ được. Trên sổ cái chung có cả token tài sản và token tiền, điều này làm được tự động. Nó loại bỏ hẳn rủi ro gốc và rủi ro đối tác trong giao dịch giao ngay, nhưng như bài chỉ ra, nó cũng loại bỏ lợi ích của bù trừ đa phương.

**Đối tác bù trừ trung tâm và bù trừ đa phương (central counterparty, multilateral netting).** CCP xen vào giữa mọi giao dịch, trở thành người mua của mọi người bán và người bán của mọi người mua (gọi là thế quyền, novation). Nhờ đứng giữa tất cả, CCP gộp được nghĩa vụ của mọi bên lại và chỉ yêu cầu mỗi bên thanh toán phần ròng. Ví dụ minh hoạ: ngân hàng X mua 100 tỷ đồng trái phiếu từ Y, và bán 90 tỷ đồng trái phiếu cho Z trong cùng ngày; nếu quyết toán từng giao dịch, X phải có sẵn 100 tỷ để trả; qua CCP, X chỉ cần thanh toán phần ròng 10 tỷ. Theo bài, bù trừ đa phương giảm nhu cầu thanh khoản tới 90% ở một số thị trường.

**Cầu nối giữa các chuỗi (cross-chain bridge).** Phần mềm chuyển tài sản từ sổ cái này sang sổ cái khác, thường bằng cách khoá tài sản ở chuỗi gốc và phát hành bản tương ứng ở chuỗi đích. Cầu nối giữ một lượng tài sản lớn nên là mục tiêu tấn công hấp dẫn; bài lưu ý đây là điểm yếu an ninh đã bị khai thác nhiều lần. Khái niệm này quan trọng vì kiến trúc mà bài cho là khả thi nhất, nhiều sổ cái tương thích, phụ thuộc vào cầu nối.

**Hạ tầng lai (hybrid FMI).** Một tổ chức trong đó phần kỹ thuật (ghi sổ, quyết toán) được tự động hoá trên sổ cái, còn phần chịu trách nhiệm (quản trị rủi ro, xử lý vỡ nợ, quản lý khủng hoảng) vẫn thuộc về một pháp nhân được cấp phép và giám sát. Đây là kết luận của bài về hình dạng tương lai của FMI.

## Nội dung chi tiết

### 1. Vì sao hạ tầng thị trường tài chính tồn tại

Câu trả lời lịch sử rất đơn giản: vì sổ sách của các bên tách rời nhau. Mỗi ngân hàng, mỗi nhà môi giới, mỗi nhà đầu tư giữ bản ghi riêng, và các bản ghi đó phải được đối chiếu để bảo đảm khớp nhau. Hạ tầng thị trường tài chính ra đời để làm việc đối chiếu đó một cách tập trung, đáng tin cậy và có trách nhiệm pháp lý: khi có sai lệch, có một bên đứng ra chịu trách nhiệm.

Từ nhu cầu ban đầu ấy, các hạ tầng tích tụ thêm những chức năng không liên quan trực tiếp tới việc ghi sổ:

- quản lý rủi ro đối tác;
- xử lý tình huống một thành viên vỡ nợ;
- cung cấp dữ liệu cho cơ quan giám sát;
- đóng vai trò điểm can thiệp khi có khủng hoảng.

Bài lập luận rằng phân biệt hai nhóm chức năng này là chìa khoá để trả lời câu hỏi về tương lai. Nhóm thứ nhất là **ghi sổ và quyết toán**, những việc thuần kỹ thuật. Nhóm thứ hai là **quản trị rủi ro, xử lý vỡ nợ và quản lý khủng hoảng**, những việc đòi hỏi một bên có trách nhiệm, có vốn và có quyền ra quyết định. Token hoá tấn công trực diện vào nhóm thứ nhất, vì khi mọi bên dùng chung một sổ cái thì không còn gì để đối chiếu. Nhưng nó gần như không đụng tới nhóm thứ hai.

### 2. Vòng đời giao dịch và bản đồ rủi ro

Bài đi qua sáu giai đoạn của vòng đời một giao dịch và chỉ ra rủi ro đặc trưng ở từng giai đoạn:

| Giai đoạn | Việc diễn ra | Rủi ro chính |
|---|---|---|
| Thứ nhất: Giao dịch (trading) | khớp lệnh mua và bán | thao túng giá, truy cập không công bằng, sai lệch thông tin trước giao dịch |
| Thứ hai: Xác nhận (confirmation) | hai bên thống nhất điều khoản | sai lệch dữ liệu giữa hai sổ sách, tranh chấp về nội dung đã thoả thuận |
| Thứ ba: Bù trừ (clearing) | tính nghĩa vụ ròng, quản lý rủi ro giữa lúc khớp lệnh và lúc quyết toán | rủi ro đối tác (bên kia có thể vỡ nợ trong khoảng thời gian này), rủi ro thay thế (phải mua lại ở giá khác), rủi ro tài sản bảo đảm không đủ |
| Thứ tư: Quyết toán (settlement) | chuyển tài sản và tiền | rủi ro gốc (một bên giao mà bên kia không trả), rủi ro thanh khoản trong ngày, rủi ro vận hành |
| Thứ năm: Lưu ký (custody) | giữ và ghi nhận quyền sở hữu | mất tài sản, tài sản bị lẫn vào khối tài sản phá sản của bên lưu ký, sai sót ghi sổ |
| Thứ sáu: Hậu quyết toán | sự kiện doanh nghiệp (trả cổ tức, chia tách cổ phiếu), báo cáo, đối soát | xử lý sai sự kiện, thông tin thị trường thiếu |

Rủi ro nghiêm trọng nhất tập trung ở khoảng giữa khớp lệnh và quyết toán, nơi rủi ro đối tác tồn tại. Đây chính là lý do tồn tại của đối tác bù trừ trung tâm và của các yêu cầu ký quỹ: CCP đứng giữa để nếu một bên vỡ nợ thì bên kia vẫn được bảo đảm, và ký quỹ là khoản tiền đặt trước để bù tổn thất khi điều đó xảy ra.

Luận điểm của bài về tác động của token hoá lên sáu giai đoạn:

- Token hoá tấn công mạnh nhất vào giai đoạn xác nhận, bù trừ và quyết toán, bằng cách làm cho sổ sách **chung** (không còn sai lệch giữa hai sổ) và quyết toán **nguyên tử** (không còn khoảng chờ).
- Nó tác động ít hơn tới giai đoạn giao dịch và hậu quyết toán.
- Nó gần như không giải quyết được phần **quản trị rủi ro** trong giai đoạn bù trừ.

Quyết toán nguyên tử loại bỏ hoàn toàn khoảng trống giữa khớp lệnh và quyết toán đối với giao dịch **giao ngay**. Đó là lợi ích thật và lớn. Nhưng bài lưu ý khoảng trống này chỉ là một trong các nguồn rủi ro. Với hợp đồng phái sinh có thời hạn dài, ví dụ một hợp đồng hoán đổi lãi suất kéo dài nhiều năm, rủi ro đối tác tồn tại suốt vòng đời hợp đồng, vì hai bên còn nợ nhau các khoản thanh toán trong tương lai, chứ không chỉ trong vài ngày chờ quyết toán. Quyết toán tức thời không làm thay đổi điều đó.

### 3. Số phận của bốn loại hạ tầng

| Hạ tầng | Chức năng hiện nay | Trong thế giới token hoá |
|---|---|---|
| CSD, trung tâm lưu ký chứng khoán | ghi nhận quyền sở hữu chứng khoán; bảo đảm tính toàn vẹn của đợt phát hành (không tự sinh ra hoặc mất đi chứng khoán) | chức năng ghi sổ chuyển được lên sổ cái, nhưng vẫn cần một bên chịu trách nhiệm pháp lý bảo đảm token ứng đúng 1:1 với tài sản pháp lý |
| SSS, hệ thống quyết toán chứng khoán | quyết toán giao dịch chứng khoán, thường theo chu kỳ T+1 hoặc T+2, cần cơ chế DvP | bị thay thế rõ nhất |
| CCP, đối tác bù trừ trung tâm | xen vào giữa hai bên, trở thành người mua của mọi người bán và ngược lại; bù trừ đa phương; quỹ vỡ nợ; quản lý khủng hoảng | khó thay thế nhất |
| TR, kho dữ liệu giao dịch | lưu trữ dữ liệu giao dịch cho cơ quan quản lý giám sát | về nguyên tắc dư thừa, nhưng cần điều kiện |

**Trung tâm lưu ký chứng khoán.** Chức năng ghi nhận ai sở hữu bao nhiêu có thể chuyển lên sổ cái. Nhưng chức năng bảo đảm tính toàn vẹn của đợt phát hành, tức là bảo đảm số token đang lưu hành khớp đúng với số chứng khoán được phát hành hợp pháp theo tỷ lệ 1:1, vẫn cần một bên chịu trách nhiệm pháp lý. Ví dụ minh hoạ: nếu một lỗi phần mềm tạo thêm 1.000 token trái phiếu không có trái phiếu thật đứng sau, ai bồi thường cho người đang nắm giữ? Mã lệnh có thể thực thi quy tắc nhưng không thể chịu trách nhiệm khi quy tắc sai.

**Hệ thống quyết toán chứng khoán.** Đây là nơi token hoá thay thế rõ nhất. Hiện nay giao dịch được quyết toán sau một hoặc hai ngày làm việc (T+1, T+2) và cần cơ chế giao chứng khoán đồng thời với thanh toán (DvP) để tránh rủi ro gốc. Quyết toán nguyên tử trên sổ cái chung làm đúng việc đó, nhanh hơn và không cần khoảng chờ.

**Đối tác bù trừ trung tâm.** Đây là trường hợp khó nhất và bài dành nhiều chỗ nhất cho nó, vì hai lý do.

- Quyết toán tức thời loại bỏ rủi ro đối tác trong giao dịch giao ngay, nhưng không giúp gì cho hợp đồng phái sinh dài hạn, vốn là mảng hoạt động lớn của CCP.
- Quan trọng hơn là **nghịch lý thanh khoản**. Bù trừ đa phương của CCP giảm nhu cầu thanh khoản tới khoảng 90% ở một số thị trường: thay vì mỗi giao dịch phải có đủ tiền, các bên chỉ thanh toán phần chênh lệch ròng sau khi gộp mọi giao dịch. Quyết toán nguyên tử từng giao dịch một làm mất lợi ích đó. Người tham gia phải có nhiều tiền và tài sản sẵn sàng hơn hẳn, và phải có ngay tại thời điểm giao dịch chứ không phải sau một hai ngày.

Ví dụ minh hoạ nghịch lý: một ngân hàng mua và bán xen kẽ trong ngày, tổng giá trị mua 1.000 tỷ đồng, tổng giá trị bán 950 tỷ đồng. Qua CCP, cuối ngày ngân hàng chỉ cần trả phần ròng 50 tỷ. Với quyết toán nguyên tử, mỗi lệnh mua phải có tiền ngay lúc khớp, nên ngân hàng có thể cần sẵn hàng trăm tỷ đồng trong suốt ngày. Công nghệ loại bỏ được rủi ro, nhưng cũng loại bỏ cơ chế đã giúp hệ thống tiết kiệm thanh khoản.

**Kho dữ liệu giao dịch.** Về nguyên tắc, kho này trở nên dư thừa nếu cơ quan quản lý đọc trực tiếp sổ cái. Nhưng điều đó đòi hỏi hai thứ không tự động có: quyền truy cập được bảo đảm về mặt pháp lý, và năng lực diễn giải dữ liệu thô (một sổ cái ghi hàng triệu dòng chuyển token không tự nó cho biết rủi ro tập trung ở đâu).

### 4. Quản trị blockchain theo bốn chiều

Vì token hoá chuyển phần ghi sổ lên sổ cái, câu hỏi "ai quản trị sổ cái" trở thành trung tâm. Bài phân tích quản trị theo bốn chiều:

| Chiều | Câu hỏi cụ thể |
|---|---|
| Ai được tham gia | hệ thống có phép (chỉ thành viên được duyệt) hay không phép (ai cũng vào được), và ai quyết định việc cấp phép |
| Ai xác thực giao dịch | cơ chế đồng thuận nào quyết định giao dịch được ghi vào sổ, và trên thực tế quyền xác thực tập trung tới mức nào |
| Ai được thay đổi quy tắc | quy trình nâng cấp giao thức, ngưỡng phê duyệt, cơ chế xử lý bất đồng |
| Ai chịu trách nhiệm khi có sự cố | ai bồi thường, ai xử lý, ai bị xử phạt |

Chiều thứ tư là chiều mà bài cho là yếu nhất trong các thiết kế hiện có. Trong hệ thống truyền thống, luôn có một pháp nhân được cấp phép, chịu giám sát và có vốn để bù đắp tổn thất. Trong nhiều thiết kế phi tập trung, không có ai như vậy: khi có lỗi, không có địa chỉ để khiếu nại.

Bài cũng nhấn mạnh rằng mức độ phi tập trung trong thực tế thường thấp hơn nhiều so với trong thiết kế. Ví dụ minh hoạ: một mạng lưới có hàng trăm nút xác thực trên giấy, nhưng nếu ba nhà vận hành kiểm soát phần lớn quyền xác thực thì thực chất nó tập trung. Vì vậy cơ quan quản lý nên đánh giá một hệ thống theo thực tế vận hành chứ không theo mô tả kỹ thuật.

### 5. Ba kiến trúc sổ cái

Bài so sánh ba cách tổ chức sổ cái cho một nền kinh tế token hoá:

| Kiến trúc | Mô tả | Ưu điểm | Nhược điểm |
|---|---|---|---|
| Thứ nhất: Sổ cái đơn nhất (single ledger) | mọi tài sản và mọi loại tiền trên một sổ cái duy nhất | nguyên tử hoàn hảo, không cần cầu nối, thanh khoản tập trung, khả năng kết hợp các tài sản và dịch vụ tối đa | điểm hỏng đơn lẻ; rủi ro độc quyền; câu hỏi ai vận hành và ai quản trị; khó đạt được về chính trị ở cấp quốc tế |
| Thứ hai: Sổ cái chung có phân vùng (common ledger, partitioned) | một hạ tầng chung nhưng chia vùng theo loại tài sản, nhóm người tham gia hoặc tài phán | giữ được phần lớn lợi ích nguyên tử trong vùng; cho phép quy tắc khác nhau giữa các vùng | giao dịch liên vùng vẫn cần cơ chế điều phối |
| Thứ ba: Sổ cái tương thích (compatible ledgers) | nhiều sổ cái độc lập nối với nhau bằng chuẩn chung và giao thức liên thông | thực tế nhất về chính trị; cho phép cạnh tranh và đổi mới; không có điểm hỏng đơn lẻ | nguyên tử qua các chuỗi rất khó; cầu nối là điểm yếu an ninh đã bị khai thác nhiều lần; thanh khoản phân mảnh |

**Sổ cái đơn nhất** cho lợi ích tối đa về nguyên tử và thanh khoản tập trung, nhưng tạo điểm hỏng đơn lẻ: nếu sổ cái đó gặp sự cố, mọi thứ dừng lại. Nó cũng đặt ra câu hỏi khó về việc ai vận hành và quản trị nó. Bài đánh giá phương án này khó đạt được ở quy mô toàn cầu vì lý do chính trị hơn là kỹ thuật: các nước khó chấp nhận đặt toàn bộ tài sản tài chính của mình lên một hạ tầng do một bên kiểm soát.

**Sổ cái chung có phân vùng** giữ được phần lớn lợi ích trong từng vùng, đồng thời cho phép quy tắc khác nhau giữa các vùng. Điều này phù hợp với thực tế là các tài phán có luật khác nhau. Giao dịch liên vùng vẫn cần cơ chế điều phối.

**Sổ cái tương thích** là nhiều sổ cái độc lập nối với nhau bằng chuẩn chung. Đây là con đường thực tế nhất về chính trị và cho phép cạnh tranh, nhưng có ba điểm yếu: quyết toán nguyên tử qua các chuỗi rất khó đạt được; cầu nối giữa các chuỗi là điểm yếu an ninh đã bị khai thác nhiều lần; và thanh khoản bị chia nhỏ giữa các sổ cái.

**Đánh giá của bài:** sổ cái tương thích là con đường khả thi trước mắt; sổ cái chung có phân vùng là đích đến hợp lý ở cấp khu vực; sổ cái đơn nhất khó xảy ra ở quy mô toàn cầu.

### 6. Rủi ro chuyển đổi và khái niệm hạ tầng lai

Bài chia quá trình chuyển đổi thành ba giai đoạn, mỗi giai đoạn có rủi ro và biện pháp giảm thiểu riêng:

| Giai đoạn | Rủi ro | Biện pháp giảm thiểu |
|---|---|---|
| Giai đoạn 1: Thí điểm song song | quy mô nhỏ nên rủi ro hệ thống thấp, nhưng rủi ro pháp lý cao vì khung pháp lý chưa rõ; thí điểm thành công có thể tạo cảm giác an toàn giả về khả năng mở rộng | hộp cát quản lý có giới hạn rõ ràng, yêu cầu báo cáo |
| Giai đoạn 2: Song song ở quy mô đáng kể | nguy hiểm nhất: thanh khoản phân mảnh giữa hai hệ thống; cầu nối trở thành điểm hỏng có tầm quan trọng hệ thống; arbitrage giữa hai chế độ quản lý; chi phí vận hành kép làm suy yếu chính các tổ chức đang chuyển đổi | giám sát cầu nối như hạ tầng quan trọng; áp cùng chuẩn quản lý rủi ro cho cả hai bên |
| Giai đoạn 3: Token hoá chiếm ưu thế | tập trung vào ít nhà vận hành sổ cái; rủi ro mã lệnh trở thành rủi ro hệ thống; tốc độ lan truyền tăng vì mọi thứ tức thời và chạy 24/7; mất khả năng "bấm dừng" mà các hệ thống hiện tại vẫn có | cơ chế ngắt mạch được thiết kế sẵn trong giao thức; kiểm toán mã bắt buộc; kế hoạch xử lý đổ vỡ cho nhà vận hành sổ cái |

**Giai đoạn giữa là nguy hiểm nhất.** Rủi ro lớn nhất không nằm ở điểm khởi đầu hay điểm kết thúc, mà ở giai đoạn hai hệ thống cùng tồn tại ở quy mô đáng kể. Thanh khoản bị chia giữa hệ thống cũ và hệ thống token, nên mỗi bên đều mỏng hơn. Cầu nối giữa hai hệ thống trở thành điểm hỏng có tầm quan trọng hệ thống. Chênh lệch quy định giữa hai chế độ tạo cơ hội arbitrage: hoạt động sẽ dồn sang nơi quy định lỏng hơn. Và các tổ chức phải vận hành cùng lúc hai hệ thống, chịu chi phí kép, nên bị suy yếu đúng lúc cần vững nhất.

**Giai đoạn token hoá chiếm ưu thế** đem lại loại rủi ro khác. Rủi ro tập trung vào số ít nhà vận hành sổ cái. Một lỗi trong mã lệnh, vốn trước đây chỉ ảnh hưởng một tổ chức, nay có thể ảnh hưởng cả hệ thống. Tốc độ lan truyền tăng vì mọi thứ diễn ra tức thời và liên tục 24/7, không còn đêm hay cuối tuần để các bên kịp phản ứng. Bài đặc biệt lưu ý việc mất khả năng "bấm dừng": hệ thống hiện nay có thể tạm ngừng giao dịch hay hoãn quyết toán khi có sự cố, còn hệ thống quyết toán nguyên tử tự động thì không, trừ khi được thiết kế từ đầu. Vì vậy bài đề xuất cài sẵn cơ chế ngắt mạch vào chính giao thức.

**Kết luận: hạ tầng lai.** Kết quả nhiều khả năng của quá trình này là các hạ tầng lai: phần kỹ thuật (ghi sổ, quyết toán) được tự động hoá trên sổ cái, còn phần chịu trách nhiệm pháp lý, quản trị rủi ro và xử lý khủng hoảng vẫn thuộc về một pháp nhân được cấp phép và giám sát. Nguyên tắc chỉ đạo là **cùng hoạt động, cùng rủi ro, cùng quy định**: một hoạt động quyết toán chịu cùng chuẩn mực dù chạy trên hệ thống cũ hay trên sổ cái token. Các Nguyên tắc dành cho Hạ tầng Thị trường Tài chính (PFMI) của CPMI-IOSCO vẫn áp dụng được, tuy cần được diễn giải lại cho môi trường mới.

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

## Đánh giá và phát hiện đáng chú ý

### Nghịch lý thanh khoản không phải một chi tiết, nó là kết luận thật của bài

Trong toàn bộ cuộc thảo luận toàn cầu về token hoá, quyết toán nguyên tử luôn được trình bày như một sự cải thiện thuần tuý: rủi ro đối tác biến mất, không ai mất gì. Bài này đưa ra con số phá vỡ cách kể đó — bù trừ đa phương của đối tác bù trừ trung tâm giảm nhu cầu thanh khoản tới khoảng chín mươi phần trăm ở một số thị trường — rồi đặt nó vào một hộp và đi tiếp.

Hãy nhìn kỹ vào phép đánh đổi. Bù trừ đa phương hoạt động được **chính vì** có một khoảng chờ giữa khớp lệnh và quyết toán: trong khoảng đó, các nghĩa vụ chồng chéo được gộp lại, và chỉ phần ròng mới cần tiền thật. Quyết toán nguyên tử loại bỏ khoảng chờ đó theo định nghĩa. Không thể vừa quyết toán tức thời từng giao dịch vừa bù trừ chúng với nhau — hai điều này loại trừ nhau về mặt logic, không phải về mặt kỹ thuật.

Nghĩa là token hoá không loại bỏ rủi ro. Nó **đổi một loại rủi ro lấy một loại khác**: đổi rủi ro đối tác lấy rủi ro thanh khoản. Và hai loại này có tính chất rất khác nhau. Rủi ro đối tác mang tính riêng lẻ, xảy ra hiếm, thường chỉ liên quan một bên, và đã có bộ công cụ trưởng thành để xử lý là ký quỹ và quỹ vỡ nợ. Rủi ro thanh khoản thì mang tính hệ thống, và nó bùng lên **đúng vào lúc căng thẳng, khi mọi người cùng cần tiền mặt một lúc**.

Đặt như vậy thì phép đổi có vẻ đi sai hướng đối với ổn định tài chính. Một hệ thống cần gấp mười lần lượng thanh khoản sẵn sàng, và cần nó ngay lập tức, là một hệ thống mong manh hơn trước cú sốc chung dù nó bền hơn trước cú sốc riêng lẻ. Nếu phải chọn một câu để mang ra khỏi tài liệu này, nên là câu đó, chứ không phải câu về việc hạ tầng nào sẽ biến mất.

### Bảng tổng kết bốn hạ tầng cho một tỷ số khiêm tốn hơn nhiều so với giọng điệu chung của ngành

Đọc bảng như một bảng điểm: trong bốn loại hạ tầng, chỉ **một** bị thay thế rõ ràng. Trung tâm lưu ký giữ lại chức năng bảo đảm tính toàn vẹn phát hành vì cần một pháp nhân chịu trách nhiệm. Đối tác bù trừ trung tâm giữ lại phái sinh dài hạn, bù trừ đa phương và quản lý vỡ nợ. Kho dữ liệu giao dịch chỉ dư thừa nếu cơ quan quản lý vừa có quyền truy cập được bảo đảm về pháp lý vừa có năng lực diễn giải dữ liệu thô — hai điều kiện không tự nhiên mà có. Chỉ hệ thống quyết toán chứng khoán là bị thay thế thật.

Điều làm tỷ số này còn khiêm tốn hơn là **chức năng bị thay thế cũng chính là chức năng đã được cải thiện gần hết bằng cách thông thường**. Chu kỳ quyết toán đã rút từ ba ngày xuống hai ngày rồi xuống một ngày ở các thị trường lớn, bằng quy trình và tự động hoá, không cần sổ cái phân tán nào. Phần lợi ích còn lại — đi từ một ngày xuống tức thời — là phần nhỏ nhất và khó nhất của con đường, đồng thời là phần phải trả giá bằng toàn bộ lợi ích bù trừ.

Nói cách khác, lập luận kinh tế cho việc token hoá quyết toán chứng khoán ở một thị trường đã đạt chu kỳ ngắn là yếu hơn nhiều so với mức mà cuộc thảo luận công khai gợi ý. Lập luận mạnh hơn nằm ở chỗ khác — ở khả năng kết hợp các tài sản chưa từng được số hoá, ở việc đưa tài sản không có thị trường thứ cấp vào một hạ tầng có thị trường — nhưng đó là lập luận về **mở rộng phạm vi tài sản**, không phải về hiệu quả quyết toán, và bài không đi theo hướng này.

### "Mã lệnh không thể chịu trách nhiệm" là nguyên lý bền nhất, và nó có một hệ quả tài khoá

Câu "mã lệnh có thể thực thi một quy tắc, nhưng không thể chịu trách nhiệm về việc quy tắc đó sai" là phát biểu gọn nhất về giới hạn của tự động hoá trong tài chính, và nó sẽ còn đúng bất kể công nghệ nào xuất hiện tiếp theo.

Lý do nó đúng không phải là triết học mà là kế toán. Chịu trách nhiệm nghĩa là **có vốn để mất**. Một pháp nhân được cấp phép chịu trách nhiệm vì nó có vốn chủ sở hữu, có quỹ vỡ nợ, có bảo hiểm, và những thứ đó có thể bị lấy đi để bù tổn thất. Một đoạn mã không có bảng cân đối kế toán.

Hệ quả mà bài không rút ra: khi một hệ thống tự động hoá việc thực thi mà không chỉ định một pháp nhân có vốn chịu trách nhiệm, rủi ro không biến mất — nó trở thành **rủi ro chưa được phân bổ**. Và rủi ro chưa được phân bổ trong một hệ thống có tầm quan trọng hệ thống luôn rơi về một nơi duy nhất khi sự cố xảy ra: khu vực công. Nói cách khác, một hạ tầng token hoá không có pháp nhân chịu trách nhiệm thì ngân sách nhà nước là đối tác bù trừ trung tâm mặc định của nó, chỉ là không ai ký hợp đồng và không ai thu phí.

Đây là lý do khái niệm hạ tầng lai mà bài đề xuất không phải một thoả hiệp nửa vời mà là kết luận đúng: phần kỹ thuật tự động hoá được thì nên tự động hoá, nhưng phần chịu trách nhiệm phải có tên và có vốn. Nó cũng giải thích vì sao chiều thứ tư trong khung quản trị — ai chịu trách nhiệm khi có sự cố — là chiều yếu nhất trong mọi thiết kế phi tập trung: đó không phải sơ suất thiết kế mà là hệ quả trực tiếp của việc phi tập trung hoá.

### Nút bấm dừng là một mâu thuẫn tự thân mà bài nêu ra nhưng không giải

Bài ghi nhận rằng hệ thống token hoá mất khả năng bấm dừng mà hệ thống hiện tại vẫn có, và đề xuất thiết kế sẵn cơ chế ngắt mạch vào giao thức. Đề xuất này đúng hướng nhưng va vào hai vấn đề mà bài không xử lý.

Vấn đề thứ nhất là **cơ chế ngắt mạch tự động phải được kích hoạt bởi một quy tắc**, mà tình huống cần bấm dừng nhất lại thường là tình huống nằm ngoài mọi quy tắc đã viết. Ngắt mạch theo biến động giá bắt được đợt bán tháo nhưng không bắt được một lỗi lập trình đang âm thầm tạo ra các bút toán sai vẫn nằm trong biên độ bình thường. Chính khả năng phán đoán ngoài quy tắc mới là giá trị của nút dừng thủ công.

Vấn đề thứ hai nghiêm trọng hơn: **ai giữ chìa khoá dừng thì người đó nắm quyền lực lớn nhất trong hệ thống**. Quyền dừng là quyền quyết định giao dịch nào hoàn tất và giao dịch nào không, tại thời điểm giá trị của quyết định đó cao nhất. Một hệ thống được quảng bá là phi tập trung nhưng có một chìa khoá dừng thì trên thực tế đã tập trung, chỉ là tập trung ở một điểm ít ai nhìn vào.

Hai vấn đề này gộp lại cho một kết luận thực tiễn: nút dừng nên được coi là một **thẩm quyền công**, giao cho cơ quan quản lý với quy trình và điều kiện được luật hoá, chứ không phải một tính năng kỹ thuật do bên vận hành sổ cái tự thiết kế. Bài đi rất gần kết luận này khi nói rằng các Nguyên tắc dành cho Hạ tầng Thị trường Tài chính vẫn áp dụng được nhưng cần diễn giải lại, mà không nói cụ thể phần nào cần diễn giải lại nhất. Phần đó chính là phần này.

### Phân tích rủi ro theo giai đoạn là phần hữu dụng nhất, và nó ngầm phê phán chiến lược mà mọi thị trường đang theo

Nhận định rằng giai đoạn nguy hiểm nhất không phải điểm đầu hay điểm cuối mà là giai đoạn giữa — khi hai hệ thống cùng tồn tại ở quy mô đáng kể — là phần có giá trị vận hành cao nhất của bài, và nó dẫn tới một hệ quả mà bài không nói ra.

Nếu giai đoạn song song là giai đoạn nguy hiểm, thì **chiến lược tệ nhất là một cuộc di chuyển chậm rãi, từng phần và tự nguyện** — vì nó kéo dài đúng giai đoạn nguy hiểm đó, có thể là hàng chục năm. Một cuộc chuyển đổi nhanh và bắt buộc an toàn hơn về lý thuyết. Nhưng không thị trường nào sẽ làm vậy, vì chi phí chính trị và chi phí chuyển đổi của các tổ chức hiện hữu quá lớn, và vì không ai muốn bắt buộc một công nghệ chưa được chứng minh ở quy mô.

Nên dự báo thực tế là: giai đoạn hai sẽ rất dài. Và nếu vậy, ưu tiên quản lý trong một thập kỷ tới không phải là chọn kiến trúc sổ cái nào — câu hỏi mà phần lớn cuộc thảo luận đang xoay quanh — mà là **giám sát cầu nối như hạ tầng có tầm quan trọng hệ thống**. Cầu nối giữa các sổ cái là nơi thanh khoản phân mảnh gặp nhau, là nơi lịch sử đã cho thấy các vụ tấn công lớn nhất xảy ra, và là nơi không có khung giám sát nào đang áp dụng. Nó không hấp dẫn bằng việc tranh luận về sổ cái đơn nhất, nhưng nó là nơi rủi ro thật sẽ nằm trong suốt thời gian đó.

### Với Việt Nam: bài này nói rằng đừng bỏ qua bước đang xây dở

Với một thị trường đang xây dựng cơ chế đối tác bù trừ trung tâm cho thị trường chứng khoán, tài liệu này đưa ra một thông điệp cụ thể hơn nhiều so với vẻ ngoài lý thuyết của nó.

Thông điệp đó là: **đối tác bù trừ trung tâm là hạ tầng mà token hoá không thay thế được**, và nó cũng là hạ tầng tạo ra lợi ích thanh khoản lớn nhất. Trong một thị trường có quy mô vốn hạn chế và nơi yêu cầu ký quỹ trước giao dịch là rào cản thực sự với nhà đầu tư tổ chức nước ngoài, lợi ích bù trừ đa phương không phải một tiện ích kỹ thuật mà là **chính thứ giải phóng vốn đang bị giam**. Bài này nói rằng nếu chọn quyết toán nguyên tử thay cho bù trừ, lợi ích đó sẽ mất đi. Với một thị trường thiếu thanh khoản, đó là phép đổi sai hướng nhất có thể.

Hệ quả thứ tự ưu tiên: hoàn thành cơ chế bù trừ trung tâm trước, và coi token hoá là lớp có thể thêm vào sau, chứ không phải con đường tắt để nhảy qua bước đó. Lập luận rằng có thể bỏ qua thế hệ hạ tầng cũ để đi thẳng lên công nghệ mới — vốn đúng trong nhiều trường hợp khác, như việc bỏ qua điện thoại cố định để đi thẳng lên di động — **không đúng ở đây**, vì thứ bị bỏ qua không phải một công nghệ lỗi thời mà là một cơ chế quản trị rủi ro không có thứ thay thế.

Hai điều kiện tiên quyết khác, cả hai đều thuộc về pháp lý chứ không phải công nghệ, cũng hiện ra từ bài. Một là **luật về tính chung thẩm của quyết toán**, phải trả lời được thời điểm nào một bút toán trên sổ cái trở thành không thể đảo ngược, và điều đó phải rõ trước khi có giá trị thật chạy trên đó. Hai là **xác định pháp nhân chịu trách nhiệm** cho tính toàn vẹn phát hành: ai bảo đảm rằng số token đang lưu hành khớp đúng với số chứng khoán được phát hành hợp pháp, và bên đó có vốn bao nhiêu để bù nếu sai. Cả hai đều rẻ để làm và cả hai đều trở nên rất đắt nếu bị bỏ qua cho tới khi có tranh chấp đầu tiên.
