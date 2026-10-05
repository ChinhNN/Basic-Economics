# Tokenized Finance — Tài chính token hoá

**Nguồn:** IMF Note NOTE/2026/001.
**Tác giả:** chưa xác định (bản PDF không có trang bìa và trang tác giả).
**Ý chính:** Token hoá không chỉ là số hoá chứng từ. Nó là việc gắn tài sản và nghĩa vụ vào sổ cái lập trình được, nơi việc chuyển giao và việc cập nhật sổ sách xảy ra đồng thời. Điều đó phân bổ lại niềm tin: từ chỗ tin vào tổ chức trung gian sang tin vào mã lệnh và quản trị mã lệnh. Bài lập luận rằng lợi ích thực sự đến từ việc rút ngắn quyết toán và giảm đối soát, nhưng lợi ích đó chỉ hiện thực hoá nếu tính chung quyết toán được bảo đảm về mặt pháp lý, và rủi ro lớn nhất đối với các nền kinh tế mới nổi là thay thế tiền trong nước bằng token ngoại tệ.

> **Lưu ý:** bản PDF không có trang bìa và trang tác giả. Tên bài và số hiệu lấy từ phần đầu văn bản và trang bìa sau.

## Sơ đồ

### Token hoá thay đổi điều gì

```text
       HỆ THỐNG HIỆN NAY — SỔ SÁCH TÁCH RỜI
       Bên mua ─┐                              ┌─ Bên bán
                │  lệnh                  lệnh  │
                ▼                              ▼
       Ngân hàng lưu ký ◂──┐          ┌──▸ Ngân hàng lưu ký
                │          │          │            │
                ▼          │          │            ▼
       Trung tâm lưu ký ◂──┤ ĐỐI SOÁT ├──▸ Trung tâm thanh toán
                │          │  nhiều   │            │
                ▼          │  vòng    │            ▼
       Sổ cái tiền ────────┘          └──────── Sổ cái chứng khoán
       · MỖI bên giữ SỔ RIÊNG, phải khớp với nhau
       · quyết toán T+1 hoặc T+2 → RỦI RO ĐỐI TÁC tồn tại giữa chừng
       · phải ký quỹ để bù rủi ro đó → VỐN BỊ GIAM
                                │
                                ▼
       HỆ THỐNG TOKEN HOÁ — SỔ CÁI CHUNG LẬP TRÌNH ĐƯỢC
       ┌──────────────────────────────────────────────────────┐
       │  MỘT SỔ CÁI: tiền token hoá ◂──atomic swap──▸ chứng   │
       │  khoán token hoá                                     │
       │  · chuyển giao và cập nhật sổ sách là CÙNG MỘT hành vi│
       │  · giao hàng đổi thanh toán (DvP) xảy ra NGUYÊN TỬ:   │
       │    hoặc CẢ HAI chân cùng xong, hoặc KHÔNG chân nào    │
       │  · hợp đồng thông minh tự động hoá trả lãi, ký quỹ,   │
       │    tuân thủ, sự kiện doanh nghiệp                     │
       └──────────────────────────────────────────────────────┘
       LỢI ÍCH: giảm rủi ro đối tác · giải phóng ký quỹ · bớt đối
       soát · 24/7 · khả năng "kết hợp" (composability) giữa các
       ứng dụng tài chính
       ĐÁNH ĐỔI: niềm tin chuyển từ TỔ CHỨC sang MÃ LỆNH → ai viết
       mã, ai sửa được, ai chịu trách nhiệm khi mã sai?
```

### Ba loại tiền token hoá và nơi sCBDC đứng

```text
       ❶ TIỀN GỬI TOKEN HOÁ (tokenized deposits)
         · nghĩa vụ của NGÂN HÀNG THƯƠNG MẠI, giữ nguyên cấu trúc
           hai tầng của hệ thống tiền tệ hiện hành
         · nằm trong khung quản lý ngân hàng, có bảo hiểm tiền gửi
         · CHUYỂN GIAO giữa các ngân hàng vẫn cần quyết toán bằng
           tiền ngân hàng trung ương → cần cầu nối
         → ÍT GÂY GIÁN ĐOẠN nhất
                                │
       ❷ STABLECOIN
         · nghĩa vụ của TỔ CHỨC PHI NGÂN HÀNG, neo vào tiền pháp
           định qua dự trữ
         · tính đơn nhất của tiền (singleness of money) KHÔNG được
           bảo đảm: giá có thể lệch mệnh giá
         · rủi ro: rút chạy hàng loạt, chất lượng dự trữ, minh bạch
         → linh hoạt nhất nhưng RỦI RO CAO nhất
                                │
       ❸ QUỸ THỊ TRƯỜNG TIỀN TỆ TOKEN HOÁ
         · yêu cầu trên một RỔ TÀI SẢN, không phải mệnh giá cố định
         · trả lợi tức nhưng KHÔNG phải phương tiện thanh toán tự
           nhiên; chuyển đổi cần bán tài sản
                                │
                                ▼
       ★ sCBDC — CBDC BÁN BUÔN TRÊN SỔ CÁI TOKEN HOÁ
         · NEO của toàn hệ thống: tài sản quyết toán KHÔNG RỦI RO
         · giữ tính đơn nhất của tiền vì mọi token tư nhân đều quy
           đổi về MỘT đơn vị tài khoản chung
         · cho phép quyết toán nguyên tử mà không cần tin vào bên
           phát hành tư nhân nào
         → LẬP LUẬN CỦA BÀI: không có tài sản quyết toán ngân hàng
           trung ương, tài chính token hoá sẽ TÁI TẠO lại đúng rủi
           ro tín dụng và rủi ro thanh khoản mà nó hứa loại bỏ
```

### Tính chung quyết toán: điểm yếu pháp lý cốt lõi

```text
       VẤN ĐỀ
       · "quyết toán nguyên tử" là thuộc tính KỸ THUẬT của sổ cái
       · "tính chung quyết toán" (settlement finality) là thuộc tính
         PHÁP LÝ: thời điểm mà việc chuyển giao KHÔNG THỂ đảo ngược,
         kể cả khi một bên PHÁ SẢN
       · HAI THỨ NÀY KHÔNG TỰ ĐỘNG TRÙNG NHAU
                                │
                                ▼
       CÁC CÂU HỎI CHƯA CÓ LỜI ĐÁP THỐNG NHẤT
       ① luật nào ÁP DỤNG cho một sổ cái phân tán qua nhiều nước?
       ② token là TÀI SẢN gì về mặt pháp lý — chứng khoán, hàng hoá,
         yêu cầu hợp đồng, hay một loại mới?
       ③ nếu mã lệnh thực hiện đúng nhưng kết quả TRÁI với ý định
         của các bên, cái nào thắng — MÃ hay HỢP ĐỒNG?
       ④ ai có quyền ĐẢO NGƯỢC khi có gian lận hoặc lệnh toà án?
       ⑤ cơ chế phá sản: token của khách hàng có TÁCH KHỎI khối tài
         sản của bên trung gian phá sản không?
                                │
                                ▼
       HỆ QUẢ: nếu không xử lý, token hoá KHÔNG loại bỏ rủi ro — nó
       chỉ DI CHUYỂN rủi ro từ nơi có khung pháp lý rõ sang nơi
       chưa có
```

### Ba kịch bản và lộ trình năm trụ cột

```text
       KỊCH BẢN A — "NGÕ CỤT"
       thí điểm không mở rộng được; chi phí chuyển đổi cao hơn lợi
       ích; hệ thống cũ vẫn đủ tốt → token hoá thành ngách nhỏ
       KỊCH BẢN B — "SONG SONG"
       hệ thống token hoá và hệ thống truyền thống cùng tồn tại,
       nối bằng cầu nối → hưởng một phần lợi ích, NHƯNG phân mảnh
       thanh khoản và chi phí vận hành KÉP
       KỊCH BẢN C — "CHUYỂN ĐỔI"
       tài chính bán buôn dịch chuyển lên hạ tầng token hoá chung
       với sCBDC làm neo → lợi ích đầy đủ, nhưng đòi hỏi PHỐI HỢP
       quốc tế ở mức chưa từng có
       ────────────────────────────────────────────────────────────
       LỘ TRÌNH NĂM TRỤ CỘT
       ❶ RÕ RÀNG PHÁP LÝ: định danh tài sản, tính chung quyết toán,
         luật áp dụng, quy tắc phá sản — LÀM TRƯỚC, không làm sau
       ❷ TÀI SẢN QUYẾT TOÁN: bảo đảm có tiền ngân hàng trung ương
         trên sổ cái token hoá, hoặc cơ chế tương đương
       ❸ KHẢ NĂNG LIÊN THÔNG: chuẩn chung để tránh phân mảnh thành
         các "hòn đảo" thanh khoản
       ❹ QUẢN TRỊ MÃ LỆNH: ai kiểm toán, ai nâng cấp, ai chịu trách
         nhiệm; áp dụng nguyên tắc "cùng hoạt động, cùng rủi ro,
         cùng quy định"
       ❺ BẢO VỆ EMDE: chống thay thế tiền tệ bằng token ngoại tệ,
         giữ hiệu lực của quản lý dòng vốn, xây năng lực giám sát
```

## Ba câu hỏi bài viết trả lời

1. Token hoá thay đổi điều gì về bản chất so với số hoá tài chính đã có?
2. Loại tiền nào sẽ làm chân tiền trong giao dịch token hoá, và vì sao lựa chọn đó quan trọng?
3. Rủi ro đặc thù với các nền kinh tế mới nổi là gì và nên làm gì trước?

## Khái niệm cần biết

**Token hoá (tokenization).** Thể hiện một tài sản hoặc một quyền (cổ phiếu, trái phiếu, tiền gửi, phần góp quỹ) dưới dạng bản ghi trên một sổ cái lập trình được, nơi việc chuyển quyền sở hữu và việc ghi sổ là cùng một hành vi. Ví dụ minh hoạ: khi một trái phiếu token hoá được chuyển từ A sang B, chính thao tác chuyển đó là việc cập nhật sổ; không có một sổ riêng ở trung tâm lưu ký phải sửa sau. Khác với số hoá thông thường, vốn chỉ biến giấy thành tệp điện tử nhưng vẫn để mỗi bên giữ một sổ riêng. Đây là khái niệm nền của toàn bài.

**Quyết toán (settlement) và chu kỳ T+1, T+2.** Quyết toán là bước hoàn tất giao dịch: tiền thật sự đến tay bên bán và tài sản thật sự đến tay bên mua. T+2 nghĩa là việc này xảy ra hai ngày làm việc sau ngày giao dịch (ngày T). Ví dụ minh hoạ: mua cổ phiếu thứ Hai theo chu kỳ T+2 thì tới thứ Tư mới quyết toán; trong hai ngày đó, nếu một bên phá sản, bên kia chịu rủi ro. Khoảng chờ này là thứ token hoá hứa rút ngắn.

**Rủi ro đối tác và ký quỹ.** Rủi ro đối tác là khả năng bên kia không thực hiện nghĩa vụ. Để phòng rủi ro này, các bên phải nộp ký quỹ, tức một khoản tiền hoặc tài sản đặt cọc. Ví dụ minh hoạ: một ngân hàng có giao dịch 100 triệu đô la đang chờ quyết toán có thể phải đặt vài triệu đô la ký quỹ; số tiền đó bị "giam", không dùng vào việc khác được. Rút ngắn quyết toán làm giảm rủi ro đối tác, nên giải phóng được ký quỹ.

**Quyết toán nguyên tử và giao hàng đổi thanh toán (atomic settlement, DvP).** Giao dịch có hai chân: chân tiền và chân tài sản. Quyết toán nguyên tử nghĩa là hai chân hoặc cùng xong, hoặc không chân nào xảy ra; không bao giờ có cảnh một bên đã giao mà bên kia chưa trả. Ví dụ minh hoạ: A đổi 1 triệu đô la token lấy trái phiếu token của B; nếu tài khoản B không có trái phiếu, tiền của A cũng không rời đi. Đây là lợi ích kỹ thuật cốt lõi của token hoá.

**Tính chung quyết toán (settlement finality).** Thời điểm mà, theo luật, việc chuyển giao không thể bị đảo ngược nữa, kể cả khi một bên phá sản sau đó. Ví dụ minh hoạ: giao dịch đã hoàn tất trên sổ cái lúc 10 giờ, nhưng nếu luật chưa công nhận đó là thời điểm chung thẩm, người quản lý tài sản phá sản của một bên vẫn có thể đòi huỷ giao dịch. Bài nhấn mạnh tính nguyên tử là thuộc tính kỹ thuật, còn tính chung quyết toán là thuộc tính pháp lý, và hai thứ không tự động trùng nhau.

**Tính đơn nhất của tiền (singleness of money).** Mọi hình thái tiền trong một hệ thống (tiền mặt, tiền gửi ở ngân hàng này hay ngân hàng kia) đều đổi ngang mệnh giá cho nhau. Ví dụ minh hoạ: 100 đô la gửi ở ngân hàng X và 100 đô la gửi ở ngân hàng Y đều là đúng 100 đô la; nếu một stablecoin chỉ đổi được 99,7 xu cho mỗi đô la danh nghĩa thì tính đơn nhất bị phá. Khái niệm này giải thích vì sao bài cần một tài sản quyết toán của ngân hàng trung ương làm neo.

**sCBDC (CBDC bán buôn trên sổ cái token hoá).** Tiền điện tử do ngân hàng trung ương phát hành, chỉ dành cho các tổ chức tài chính (bán buôn) chứ không cho người dân, và nằm trực tiếp trên sổ cái token hoá. Vì là nghĩa vụ của ngân hàng trung ương, nó không có rủi ro tín dụng. Ví dụ minh hoạ: hai ngân hàng quyết toán một giao dịch trái phiếu token bằng sCBDC thì không bên nào phải lo bên phát hành tiền vỡ nợ. Đây là "neo" của toàn hệ thống trong lập luận của bài.

**Thay thế tiền tệ (currency substitution).** Người dân bỏ dần đồng tiền trong nước để dùng đồng tiền khác cho tiết kiệm và thanh toán. Ví dụ minh hoạ: ở một nước có lạm phát cao, người dân giữ tiết kiệm bằng stablecoin neo đô la trên điện thoại thay vì tiền gửi nội tệ. Đây là rủi ro lớn nhất bài nêu cho các nền kinh tế mới nổi và đang phát triển (EMDE).

## Nội dung chi tiết

### 1. Token hoá là gì và không phải là gì

**Định nghĩa.** Token hoá là việc thể hiện tài sản hoặc quyền dưới dạng bản ghi trên sổ cái lập trình được, nơi việc chuyển giao quyền sở hữu và việc cập nhật sổ sách là cùng một hành vi. Đây là điểm khác biệt cốt lõi so với số hoá thông thường. Số hoá chỉ biến chứng từ giấy thành tệp điện tử, trong khi vẫn giữ nhiều sổ sách tách rời cần đối soát với nhau.

**Hệ thống hiện nay: sổ sách tách rời.** Trong một giao dịch chứng khoán thông thường, bên mua và bên bán gửi lệnh qua ngân hàng lưu ký của mình. Các ngân hàng lưu ký làm việc với trung tâm lưu ký chứng khoán và trung tâm thanh toán; tiền được ghi trên một sổ cái tiền, chứng khoán được ghi trên một sổ cái chứng khoán riêng. Mỗi bên giữ sổ riêng, và các sổ phải được đối soát nhiều vòng để khớp với nhau. Ba hệ quả:

- Quyết toán mất T+1 hoặc T+2, tức một đến hai ngày làm việc sau giao dịch.
- Trong khoảng chờ đó, rủi ro đối tác tồn tại: một bên có thể đã cam kết giao mà bên kia chưa trả.
- Để bù rủi ro này, các bên phải ký quỹ, nên một phần vốn bị giam lại.

**Hệ thống token hoá: một sổ cái chung lập trình được.** Tiền token hoá và chứng khoán token hoá nằm trên cùng một sổ cái và được đổi cho nhau bằng một giao dịch hoán đổi nguyên tử (*atomic swap*). Chuyển giao và cập nhật sổ sách là cùng một hành vi. Hệ quả trực tiếp là khả năng **quyết toán nguyên tử**: giao hàng đổi thanh toán (DvP) xảy ra sao cho hai chân của giao dịch, chân tiền và chân tài sản, hoặc cùng hoàn tất hoặc cùng không xảy ra. Điều này loại bỏ rủi ro một bên đã giao mà bên kia chưa trả.

**Khả năng lập trình và khả năng kết hợp.** Vì sổ cái chạy được mã lệnh, hợp đồng thông minh có thể tự động hoá các thao tác vốn tốn kém: trả lãi coupon trái phiếu, gọi ký quỹ, kiểm tra tuân thủ trước khi giao dịch, xử lý sự kiện doanh nghiệp (chia cổ tức, tách cổ phiếu). Khả năng kết hợp (*composability*) cho phép các ứng dụng tài chính khác nhau gọi lẫn nhau trên cùng một hạ tầng.

Tổng hợp lợi ích: giảm rủi ro đối tác, giải phóng ký quỹ, bớt đối soát, hoạt động 24/7 (24 giờ mỗi ngày, 7 ngày mỗi tuần), và khả năng kết hợp giữa các ứng dụng.

**Điều token hoá không làm: loại bỏ rủi ro.** Token hoá phân bổ lại niềm tin. Thay vì tin vào trung tâm lưu ký chứng khoán và các tổ chức trung gian được cấp phép, người tham gia phải tin vào tính đúng đắn của mã lệnh, và vào cơ chế quản trị quyết định ai được sửa mã lệnh đó. Từ đây nảy sinh ba câu hỏi: ai viết mã, ai sửa được mã, và ai chịu trách nhiệm khi mã sai.

### 2. Ba loại tiền token hoá

Giao dịch token hoá cần một "chân tiền". Bài phân biệt ba loại tiền tư nhân có thể đóng vai trò này, và một loại tiền ngân hàng trung ương làm neo:

| Loại | Là nghĩa vụ của ai | Ưu điểm | Hạn chế |
|---|---|---|---|
| Tiền gửi token hoá | Ngân hàng thương mại | Giữ cấu trúc hai tầng, nằm trong khung quản lý và có bảo hiểm tiền gửi; ít gây gián đoạn nhất | Chuyển giữa các ngân hàng khác nhau vẫn cần quyết toán bằng tiền ngân hàng trung ương, nên cần cầu nối |
| Stablecoin | Tổ chức phi ngân hàng, neo vào tiền pháp định qua dự trữ | Linh hoạt nhất | Rủi ro cao nhất: tính đơn nhất không được bảo đảm, có thể lệch mệnh giá, rủi ro rút chạy hàng loạt, chất lượng dự trữ, minh bạch |
| Quỹ thị trường tiền tệ token hoá | Quỹ, đại diện yêu cầu trên một rổ tài sản | Trả lợi tức | Không có mệnh giá cố định; không phải phương tiện thanh toán tự nhiên vì muốn chuyển đổi phải bán tài sản cơ sở |
| sCBDC (CBDC bán buôn trên sổ cái token hoá) | Ngân hàng trung ương | Tài sản quyết toán không rủi ro; neo của toàn hệ thống | Cần ngân hàng trung ương phát hành và vận hành |

**Tiền gửi token hoá** là nghĩa vụ của ngân hàng thương mại được thể hiện trên sổ cái. Chúng giữ nguyên cấu trúc hai tầng của hệ thống tiền tệ hiện hành (ngân hàng trung ương ở tầng trên, ngân hàng thương mại ở tầng dưới), nằm trong khung quản lý ngân hàng và bảo hiểm tiền gửi, nên ít gây gián đoạn nhất.

**Stablecoin** là nghĩa vụ của tổ chức phi ngân hàng, neo vào tiền pháp định qua tài sản dự trữ. Vấn đề cơ bản là tính đơn nhất của tiền không được bảo đảm: một stablecoin có thể giao dịch lệch mệnh giá, và người nắm giữ chịu rủi ro về chất lượng dự trữ cùng rủi ro rút chạy hàng loạt.

**Quỹ thị trường tiền tệ token hoá** trả lợi tức nhưng không phải phương tiện thanh toán tự nhiên, vì giá trị của nó phụ thuộc vào rổ tài sản và muốn dùng làm tiền thì phải bán tài sản.

**sCBDC đóng vai trò neo.** Vì là tài sản quyết toán không rủi ro, sCBDC giữ được tính đơn nhất của tiền: mọi token tư nhân đều quy đổi về một đơn vị tài khoản chung. Nó cũng cho phép quyết toán nguyên tử mà không cần tin vào bất kỳ bên phát hành tư nhân nào. Lập luận trung tâm của bài là: nếu không có tài sản quyết toán không rủi ro của ngân hàng trung ương hiện diện trực tiếp trên sổ cái, hệ thống token hoá sẽ tái tạo lại đúng các rủi ro tín dụng và rủi ro thanh khoản mà nó hứa loại bỏ, chỉ là dưới hình thức mới.

### 3. Tác động lên ba khu vực

**Ngân hàng.** Token hoá có thể rút ngắn chu kỳ quyết toán, giảm nhu cầu ký quỹ và giải phóng vốn. Nhưng nó cũng có thể đẩy nhanh tốc độ rút tiền gửi khi khủng hoảng, vì tiền token hoá di chuyển tức thời và liên tục, không dừng vào cuối tuần hay ban đêm. Câu hỏi quản lý thanh khoản trong môi trường hoạt động 24/7 chưa có lời giải đầy đủ.

**Thị trường vốn.** Lợi ích rõ nhất nằm ở các thị trường có chu kỳ quyết toán dài và nhiều khâu đối soát, như trái phiếu doanh nghiệp, quỹ đầu tư và giao dịch xuyên biên giới. Token hoá cũng có thể mở rộng khả năng chia nhỏ tài sản, giúp nhiều người tiếp cận được tài sản kém thanh khoản (ví dụ một phần nhỏ của một toà nhà). Tuy vậy bài lưu ý rằng chia nhỏ không tự động tạo ra thanh khoản: chia một tài sản thành nhiều phần không bảo đảm có người mua các phần đó.

**Hạ tầng thị trường tài chính.** Vai trò của trung tâm lưu ký chứng khoán (CSD), hệ thống quyết toán chứng khoán và đối tác bù trừ trung tâm (CCP) bị đặt lại câu hỏi. Một số chức năng của chúng, như ghi sổ và đối chiếu, có thể được mã hoá vào sổ cái. Nhưng các chức năng quản trị rủi ro, xử lý khi một thành viên vỡ nợ và quản lý khủng hoảng thì khó thay thế bằng mã lệnh, vì chúng đòi hỏi phán đoán trong tình huống chưa lường trước.

### 4. Tính chung quyết toán và quản trị mã lệnh

**Vấn đề cốt lõi.** Bài phân biệt rạch ròi hai khái niệm. Tính nguyên tử ("quyết toán nguyên tử") là thuộc tính kỹ thuật của sổ cái. Tính chung quyết toán là thuộc tính pháp lý, xác định thời điểm mà việc chuyển giao không thể bị đảo ngược, ngay cả khi một bên phá sản. Hai thứ này không tự động trùng nhau, và khoảng cách giữa chúng là nơi rủi ro ẩn nấp: một giao dịch có thể đã xong trên sổ cái nhưng về mặt pháp lý vẫn có thể bị huỷ.

**Năm câu hỏi pháp lý chưa có lời đáp thống nhất:**

1. Luật nào áp dụng cho một sổ cái phân tán qua nhiều quốc gia?
2. Token là loại tài sản gì về mặt pháp lý: chứng khoán, hàng hoá, yêu cầu theo hợp đồng, hay một loại mới?
3. Nếu mã lệnh thực hiện đúng nhưng kết quả trái với ý định của các bên, cái nào thắng: mã hay hợp đồng?
4. Ai có quyền đảo ngược giao dịch khi có gian lận hoặc lệnh toà án?
5. Khi một bên trung gian phá sản, token của khách hàng có được tách khỏi khối tài sản phá sản của bên trung gian đó không?

**Hệ quả.** Nếu không xử lý những câu hỏi này, token hoá không loại bỏ rủi ro. Nó chỉ di chuyển rủi ro từ nơi có khung pháp lý rõ ràng sang nơi chưa có.

**Quản trị mã lệnh.** Bài đặt các câu hỏi thực tiễn: ai kiểm toán mã trước khi triển khai, ai có quyền nâng cấp, quy trình nào áp dụng khi phát hiện lỗi, và ai chịu trách nhiệm tài chính cho tổn thất do lỗi mã. Nguyên tắc đề xuất là "cùng hoạt động, cùng rủi ro, cùng quy định": quản lý theo bản chất của hoạt động, bất kể nó được thực hiện bằng công nghệ nào.

### 5. Rủi ro đối với các nền kinh tế mới nổi và đang phát triển

**Thay thế tiền tệ là rủi ro nổi bật nhất.** Nếu token ngoại tệ, đặc biệt là stablecoin neo đô la, dễ tiếp cận qua điện thoại di động, người dân ở các nước có lạm phát cao hoặc đồng tiền biến động có thể chuyển sang dùng chúng nhanh hơn nhiều so với các đợt đô la hoá trước đây. Các đợt đô la hoá trước bị giới hạn bởi chi phí và ma sát vật lý: phải đến quầy đổi tiền, phải cất giữ tiền mặt. Với token trên điện thoại, những rào cản đó gần như biến mất.

Hệ quả của thay thế tiền tệ:

- chính sách tiền tệ trong nước mất hiệu lực, vì lãi suất nội tệ không còn tác động tới phần tài sản người dân giữ bằng token ngoại tệ;
- cơ sở tiền gửi của hệ thống ngân hàng bị bào mòn, ngân hàng có ít vốn hơn để cho vay;
- ngân hàng trung ương mất nguồn thu phát hành tiền.

**Lách quản lý dòng vốn.** Các biện pháp quản lý dòng vốn (CFM) có thể bị lách, vì token di chuyển qua biên giới mà không đi qua hệ thống ngân hàng đại lý truyền thống, nơi các biện pháp này vốn được thực thi.

**Rủi ro ngược chiều.** Bài cũng nêu một rủi ro theo hướng ngược lại: nếu các nước này bị loại khỏi hạ tầng token hoá đang hình thành, chi phí và thời gian cho thanh toán xuyên biên giới cùng kiều hối của họ có thể vẫn cao, trong khi các nước khác hưởng lợi.

### 6. Ba kịch bản và lộ trình

**Ba kịch bản phát triển:**

| Kịch bản | Mô tả | Kết quả |
|---|---|---|
| A. Ngõ cụt | Các thí điểm không mở rộng được vì chi phí chuyển đổi vượt lợi ích, hệ thống hiện hành vẫn đủ tốt | Token hoá thành một ngách nhỏ |
| B. Song song | Hệ thống token hoá và hệ thống truyền thống cùng tồn tại, nối với nhau bằng cầu nối | Hưởng một phần lợi ích, nhưng thanh khoản phân mảnh và chi phí vận hành kép |
| C. Chuyển đổi | Tài chính bán buôn dịch chuyển lên hạ tầng token hoá chung, có sCBDC làm neo | Lợi ích đầy đủ, nhưng đòi hỏi mức phối hợp quốc tế chưa từng có |

**Lộ trình năm trụ cột:**

1. **Rõ ràng pháp lý:** định danh tài sản, tính chung quyết toán, luật áp dụng, quy tắc phá sản. Bài nhấn mạnh việc này phải làm trước, không làm sau.
2. **Tài sản quyết toán:** bảo đảm có tiền ngân hàng trung ương trên sổ cái token hoá, hoặc một cơ chế tương đương.
3. **Khả năng liên thông:** xây chuẩn chung để tránh hệ thống bị phân mảnh thành các "hòn đảo" thanh khoản không nối với nhau.
4. **Quản trị mã lệnh:** xác định ai kiểm toán, ai nâng cấp, ai chịu trách nhiệm, theo nguyên tắc "cùng hoạt động, cùng rủi ro, cùng quy định".
5. **Bảo vệ EMDE:** chống thay thế tiền tệ bằng token ngoại tệ, giữ hiệu lực của quản lý dòng vốn, và xây năng lực giám sát.

**Các dự án minh hoạ trong phụ lục.** Bài minh hoạ bằng các dự án thực tế: Jura và Agorá về thanh toán xuyên biên giới bằng tiền token hoá; DTCC cùng Eurex và HQLAx về quản lý tài sản bảo đảm; nền tảng XC về kiến trúc liên thông; và một phép so sánh trực tiếp giữa stablecoin với sCBDC về đặc tính rủi ro.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Tokenization | Token hoá, thể hiện tài sản trên sổ cái lập trình được |
| Programmable ledger | Sổ cái lập trình được, cho phép gắn logic vào chính bản ghi tài sản |
| Atomic settlement | Quyết toán nguyên tử, hai chân giao dịch cùng xong hoặc cùng không xảy ra |
| DvP | Giao hàng đổi thanh toán, chuyển tài sản chỉ khi tiền được chuyển |
| Settlement finality | Tính chung quyết toán, thời điểm pháp lý mà chuyển giao không thể đảo ngược |
| Singleness of money | Tính đơn nhất của tiền, mọi hình thái tiền đều quy đổi ngang mệnh giá |
| Tokenized deposit | Tiền gửi token hoá, nghĩa vụ ngân hàng thương mại trên sổ cái |
| Stablecoin | Token neo giá trị vào tiền pháp định qua tài sản dự trữ |
| Tokenized MMF | Quỹ thị trường tiền tệ token hoá, yêu cầu trên rổ tài sản |
| sCBDC | CBDC bán buôn trên sổ cái token hoá, tài sản quyết toán không rủi ro |
| Settlement asset | Tài sản quyết toán, phương tiện dùng để hoàn tất nghĩa vụ thanh toán |
| Smart contract | Hợp đồng thông minh, mã lệnh tự thực thi khi điều kiện được thoả mãn |
| Composability | Khả năng kết hợp, các ứng dụng trên cùng sổ cái gọi lẫn nhau |
| Interoperability | Khả năng liên thông giữa các sổ cái và hệ thống khác nhau |
| Bridge | Cầu nối giữa hệ thống token hoá và hệ thống truyền thống |
| Liquidity fragmentation | Phân mảnh thanh khoản thành các hòn đảo không nối với nhau |
| CSD | Trung tâm lưu ký chứng khoán |
| CCP | Đối tác bù trừ trung tâm |
| Collateral mobility | Tính linh hoạt của tài sản bảo đảm, khả năng chuyển nhanh tới nơi cần |
| Code governance | Quản trị mã lệnh, quy trình kiểm toán, nâng cấp và quy trách nhiệm |
| Same activity same risk same regulation | Nguyên tắc quản lý theo bản chất hoạt động, không theo nhãn công nghệ |
| Currency substitution | Thay thế tiền tệ, người dân chuyển sang dùng đồng tiền khác |
| CFM | Biện pháp quản lý dòng vốn |
| Unified ledger | Sổ cái thống nhất, nơi tiền và tài sản cùng tồn tại và giao dịch |

## Câu nói đáng nhớ

> "Tokenization does not eliminate trust. It relocates it — from institutions to code, and to whoever governs that code."

> "Atomicity is a technical property. Finality is a legal one. They do not automatically coincide."

> "Without a central bank settlement asset on the ledger, tokenized finance risks recreating the very credit and liquidity exposures it promises to remove."

## Đánh giá và phát hiện đáng chú ý

### Khoảng cách giữa tính nguyên tử và tính chung quyết toán là một khoản rủi ro chưa được ai đặt tên

Phân biệt giữa nguyên tử — thuộc tính kỹ thuật của sổ cái — và chung quyết toán — thuộc tính pháp lý xác định thời điểm không thể đảo ngược kể cả khi một bên phá sản — là đóng góp khái niệm sắc nhất của bài. Nhưng hệ quả của nó lớn hơn chỗ bài dừng lại.

Hãy hình dung khoảng trống ấy một cách cụ thể. Giao dịch đã hoàn tất trên sổ cái: token đã chuyển, số dư đã cập nhật, cả hai bên đều thấy kết quả. Nhưng về mặt pháp lý, nếu một bên phá sản trong giai đoạn sau đó, quản tài viên có thể lập luận rằng việc chuyển giao là vô hiệu và đòi hoàn trả. Trong khoảng thời gian giữa hai thời điểm ấy, bên nhận **đang mang một khoản rủi ro mà không có bất kỳ ai đo, ai tính vốn, hay ai đặt hạn mức**.

Đây không phải một rủi ro mới trong lịch sử tài chính. Nó là bản sao hiện đại của loại rủi ro quyết toán mà toàn bộ hạ tầng thị trường tài chính đã được xây lên trong ba chục năm để tiêu diệt: tình huống một bên đã thực hiện nghĩa vụ của mình trong khi vế còn lại chưa chắc chắn về mặt pháp lý. Ngành tài chính đã tốn rất nhiều công sức và rất nhiều tiền để loại bỏ nó, thông qua luật quyết toán, hệ thống quyết toán tổng tức thời, và cơ chế thanh toán đổi thanh toán.

Điều đáng lo là loại rủi ro này có một đặc tính nguy hiểm: **nó vô hình cho tới đúng lúc nó hiện ra**. Trong điều kiện bình thường, không ai kiểm tra xem một bút toán có chung thẩm về mặt pháp lý hay không, vì không ai tranh chấp. Nó chỉ lộ ra trong vụ phá sản đầu tiên, tức là thời điểm tệ nhất và cũng là thời điểm mà lượng giao dịch đang treo lơ lửng là lớn nhất.

Vì vậy trật tự đúng không phải là xây hệ thống rồi làm rõ luật khi có vấn đề. Bài nói đúng ở trụ cột thứ nhất: **làm trước, không làm sau**. Điều bài chưa nói đủ mạnh là vì sao — không phải vì làm trước thì gọn gàng hơn, mà vì rủi ro này không thể phát hiện bằng cách vận hành thử.

### Tính đơn nhất của tiền là lập luận quyết định, và nó không phải một lập luận về rủi ro

Trong ba loại tiền token hoá, bài phân biệt chúng chủ yếu bằng hồ sơ rủi ro. Nhưng tiêu chí thực sự phân định chúng là một tiêu chí khác, và bài có nêu tên mà không khai thác: **tính đơn nhất của tiền**.

Một hệ thống thanh toán chỉ là một hệ thống khi mọi hình thái tiền trong đó đều quy đổi ngang mệnh giá. Nếu một stablecoin giao dịch ở chín mươi chín phẩy bảy xu, thì tồn tại hai mức giá cho cùng một đơn vị danh nghĩa, và mọi hợp đồng phải ghi rõ mình đang nói tới loại tiền nào. Đó không phải một rủi ro tài chính cần được tính vốn. Đó là **sự mất đi chức năng đơn vị tính toán**, tức là chức năng cơ bản nhất của tiền, và nó làm hỏng mọi thứ xây trên đó: kế toán, định giá, tính toán nghĩa vụ ròng, so sánh giữa các báo giá.

Đặt như vậy thì lập luận của bài về sự cần thiết của một tài sản quyết toán ngân hàng trung ương trên sổ cái trở nên mạnh hơn nhiều so với cách nó được trình bày. Nó không chỉ là câu chuyện loại bỏ rủi ro tín dụng của bên phát hành tư nhân. Nó là câu chuyện **có một điểm neo mà mọi token tư nhân quy về, để hệ thống còn là một hệ thống**.

Và ở đây, lịch sử lặp lại một cách khá chính xác. Thời kỳ tiền ngân hàng tư nhân thế kỷ mười chín kết thúc không phải vì thị trường chọn ra một loại giấy bạc tốt nhất, mà vì nhà nước tạo ra một đơn vị thống nhất mà mọi công cụ khác phải quy chiếu vào. Đề xuất của bài — một tài sản quyết toán ngân hàng trung ương làm neo cho các token tư nhân — chính là động tác đó, phát biểu bằng ngôn ngữ kỹ thuật của thế kỷ hai mươi mốt.

### Hai tài liệu IMF trong cùng thư mục, cùng thời điểm, nghiêng về hai hướng khác nhau

Bài này lập luận rằng nếu không có tiền ngân hàng trung ương **trên sổ cái**, tài chính token hoá sẽ tái tạo lại chính các rủi ro nó hứa loại bỏ. Báo cáo chính sách về CBDC trong cùng thư mục lại kết luận rằng lợi ích của token hoá **có thể đạt được mà không cần phát hành CBDC bán buôn**, thông qua cơ chế kích hoạt nối sang hệ thống quyết toán sẵn có hoặc thông qua tài khoản gộp.

Hai kết luận này không mâu thuẫn trực tiếp, nhưng chúng đặt trọng tâm ở hai nơi khác nhau, và điểm khác biệt nằm ở một câu hỏi kỹ thuật rất cụ thể: **tính nguyên tử một phần có đủ không**.

Cơ chế kích hoạt giữ được điểm neo — tiền quyết toán vẫn là tiền ngân hàng trung ương — nhưng đặt nó **ngoài sổ cái**. Giao dịch trên sổ cái token phải gọi sang hệ thống bên ngoài, chờ xác nhận, rồi mới hoàn tất. Trong khoảng chờ đó, tính nguyên tử bị phá vỡ: có một cửa sổ trong đó một chân đã thực hiện còn chân kia chưa. Cửa sổ ấy có thể rất ngắn, nhưng nó tồn tại, và nó chính là khoảng trống mà đoạn trên vừa mô tả.

Vậy câu hỏi thật là: cửa sổ ngắn tới mức nào thì coi như không có? Với giao dịch trong nước, trong giờ làm việc, giữa các bên đã biết nhau, câu trả lời có lẽ là "đủ ngắn". Với giao dịch xuyên biên giới, qua nhiều múi giờ, giữa các bên ở các tài phán khác nhau, câu trả lời có lẽ là "không". Cả hai tài liệu đều không đặt câu hỏi theo cách này, và đó là câu hỏi còn treo giữa chúng. Với một nước phải chọn hướng đi, đây là câu hỏi cần trả lời trước tiên, vì nó quyết định liệu phải phát hành một thứ mới hay chỉ cần nối thứ đã có.

### Ba kịch bản không có xác suất, và kịch bản có khả năng nhất lại là kịch bản nguy hiểm nhất

Bài đưa ra ba kịch bản — ngõ cụt, song song, chuyển đổi — rồi để chúng ngang hàng. Nhưng chính mô tả của bài đã ngầm xếp hạng chúng.

Kịch bản chuyển đổi được mô tả là đòi hỏi "phối hợp quốc tế ở mức chưa từng có". Trong ngôn ngữ của tài liệu chính sách đa phương, cụm từ đó gần như là một lời thừa nhận rằng điều đó sẽ không xảy ra. Kịch bản ngõ cụt thì đã bị thực tế bác bỏ một phần: các dự án đã vượt quy mô thí điểm ở một số mảng, đặc biệt là quản lý tài sản bảo đảm và thanh toán xuyên biên giới bán buôn.

Còn lại kịch bản song song, và đó cũng là kịch bản mà phân tích về hạ tầng thị trường tài chính trong cùng thư mục xác định là **giai đoạn nguy hiểm nhất**: thanh khoản phân mảnh, cầu nối trở thành điểm hỏng có tầm quan trọng hệ thống, chênh lệch quy định tạo arbitrage, và chi phí vận hành kép bào mòn chính các tổ chức đang chuyển đổi.

Nếu lộ trình khả dĩ nhất là lộ trình tệ nhất, thì thứ tự ưu tiên của năm trụ cột phải thay đổi. Trụ cột về **khả năng liên thông** — vốn được xếp thứ ba và thường bị coi là việc kỹ thuật buồn tẻ — trở thành trụ cột quan trọng thứ hai sau pháp lý, vì nó là thứ duy nhất làm dịu được chính rủi ro của kịch bản song song. Còn cuộc tranh luận về kiến trúc sổ cái lý tưởng, thứ chiếm phần lớn sự chú ý trong ngành, lại là cuộc tranh luận ít cấp thiết nhất, vì nó bàn về một đích đến có khả năng không bao giờ tới.

### Rủi ro duy nhất đẩy theo chiều ngược lại chỉ được cho một dòng, và nó làm hỏng lựa chọn "chờ xem"

Toàn bộ phần về các nền kinh tế mới nổi tập trung vào rủi ro của việc token hoá lan tới: thay thế tiền tệ, lách kiểm soát vốn, bào mòn cơ sở tiền gửi. Tất cả đều nói rằng hãy cẩn trọng, hãy phòng thủ, hãy chậm lại.

Rồi ở cuối phần đó, một câu nói ngược: nếu các nước này bị loại khỏi hạ tầng token hoá đang hình thành, chi phí và thời gian cho thanh toán xuyên biên giới và kiều hối có thể vẫn cao trong khi các nước khác hưởng lợi.

Câu này quan trọng hơn vị trí của nó, vì nó phá hỏng một giả định mà mọi lập luận phòng thủ đều dựa vào: rằng **không làm gì thì giữ nguyên hiện trạng**. Điều đó chỉ đúng khi phần còn lại của thế giới cũng đứng yên. Nếu hạ tầng bán buôn của thanh toán quốc tế dịch chuyển, một nước không kết nối không giữ được dịch vụ như cũ — nó nhận dịch vụ **xấu đi tương đối**, vì các ngân hàng đại lý sẽ tập trung nguồn lực vào hành lang mới và rút dần khỏi hành lang cũ, đúng theo xu hướng thu hẹp quan hệ đại lý đã diễn ra nhiều năm nay.

Nói cách khác, đây là một tình thế không có lựa chọn trung lập: tham gia mang rủi ro thay thế tiền tệ, không tham gia mang rủi ro bị cô lập về hạ tầng. Bài dựng ra tình thế này rồi không giải, và đó là câu hỏi chiến lược thật sự mà một nước như Việt Nam phải trả lời.

### Với Việt Nam: bốn trong năm trụ cột cần phối hợp quốc tế, trụ cột còn lại thì không

Chiếu lộ trình năm trụ cột vào hoàn cảnh một nước đi sau, một trật tự ưu tiên khá rõ hiện ra, và nó khác với trật tự trong bài.

Trụ cột thứ hai về tài sản quyết toán, thứ ba về liên thông và thứ tư về quản trị mã lệnh đều phụ thuộc vào chuẩn mực được định hình ở nơi khác, bởi những bên có quy mô lớn hơn nhiều. Trụ cột thứ năm về bảo vệ trước thay thế tiền tệ thì phụ thuộc vào việc điều chỉnh được hành vi của các bên phát hành đặt ở nước ngoài — khó, và như các tài liệu khác trong thư mục đã chỉ ra, lệnh cấm khó thực thi.

**Trụ cột thứ nhất thì hoàn toàn nằm trong tầm kiểm soát.** Năm câu hỏi pháp lý mà bài liệt kê — luật nào áp dụng, token là loại tài sản gì, mã hay hợp đồng thắng khi hai bên mâu thuẫn, ai có quyền đảo ngược, tài sản khách hàng có tách khỏi khối phá sản của trung gian không — đều là những câu hỏi mà một quốc hội có thể trả lời cho sổ cái trong phạm vi lãnh thổ mình mà không cần hỏi ai. Chúng không tốn ngoại tệ, không cần công nghệ, không cần đàm phán quốc tế, và chúng có giá trị ngay cả trong kịch bản ngõ cụt, vì khi đó chúng chỉ đơn giản là chưa được dùng tới.

Đây cũng là chỗ đáng ghi nhận một sự hội tụ: **ba tài liệu độc lập trong cùng thư mục** — bài này, phân tích về hạ tầng thị trường tài chính, và báo cáo chính sách về CBDC — đều chỉ ra luật về tính chung quyết toán là bước rẻ nhất, ít hào nhoáng nhất và có tỷ suất lợi ích cao nhất. Khi ba khung phân tích khác nhau cùng chỉ vào một việc, đó là lý do đủ để làm việc đó trước.

Về phần rủi ro, hồ sơ của Việt Nam làm thay đổi thứ tự so với bài. Rủi ro tiền gửi chạy nhanh hơn trong môi trường hoạt động liên tục chưa phải mối lo cấp bách, vì tiền gửi token hoá chưa tồn tại. Rủi ro thay thế tiền tệ và lách kiểm soát vốn thì đã đang diễn ra, nhưng qua kênh stablecoin bán lẻ chứ không qua tài chính token hoá bán buôn. Điều này gợi ý một cách chia việc rõ ràng: **phần bán buôn là cơ hội cần chuẩn bị về pháp lý; phần bán lẻ là rủi ro cần xử lý ngay**. Gộp hai thứ vào cùng một cuộc thảo luận, như cách chúng thường bị gộp, làm chậm cả hai.
