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

## Dàn ý chi tiết

### 1. Token hoá là gì và không phải là gì

- Token hoá là việc thể hiện tài sản hoặc quyền dưới dạng bản ghi trên sổ cái lập trình được, nơi việc chuyển giao quyền sở hữu và việc cập nhật sổ sách là cùng một hành vi. Đây là điểm khác biệt cốt lõi so với số hoá thông thường, vốn chỉ biến chứng từ giấy thành tệp điện tử trong khi vẫn giữ nhiều sổ sách tách rời cần đối soát.
- Hệ quả trực tiếp là khả năng quyết toán nguyên tử: hai chân của một giao dịch, chân tiền và chân tài sản, hoặc cùng hoàn tất hoặc cùng không xảy ra. Điều này loại bỏ rủi ro một bên đã giao mà bên kia chưa trả.
- Khả năng lập trình mở ra việc tự động hoá các thao tác vốn tốn kém: trả lãi coupon, gọi ký quỹ, kiểm tra tuân thủ trước giao dịch, xử lý sự kiện doanh nghiệp. Khả năng kết hợp cho phép các ứng dụng tài chính khác nhau gọi lẫn nhau trên cùng một hạ tầng.
- Điều token hoá không làm là loại bỏ rủi ro. Nó phân bổ lại niềm tin. Thay vì tin vào trung tâm lưu ký chứng khoán và các tổ chức trung gian được cấp phép, người tham gia phải tin vào tính đúng đắn của mã lệnh và vào cơ chế quản trị quyết định ai được sửa mã lệnh đó.

### 2. Ba loại tiền token hoá

- **Tiền gửi token hoá** là nghĩa vụ của ngân hàng thương mại được thể hiện trên sổ cái. Chúng giữ nguyên cấu trúc hai tầng của hệ thống tiền tệ, nằm trong khung quản lý và bảo hiểm tiền gửi hiện hành, nên ít gây gián đoạn nhất. Hạn chế là việc chuyển giữa các ngân hàng khác nhau vẫn cần quyết toán bằng tiền ngân hàng trung ương.
- **Stablecoin** là nghĩa vụ của tổ chức phi ngân hàng, neo vào tiền pháp định qua tài sản dự trữ. Vấn đề cơ bản là tính đơn nhất của tiền không được bảo đảm: một stablecoin có thể giao dịch lệch mệnh giá, và người nắm giữ chịu rủi ro về chất lượng dự trữ cùng rủi ro rút chạy hàng loạt.
- **Quỹ thị trường tiền tệ token hoá** đại diện cho yêu cầu trên một rổ tài sản chứ không phải một mệnh giá cố định. Chúng trả lợi tức nhưng không phải phương tiện thanh toán tự nhiên vì việc chuyển đổi đòi hỏi bán tài sản cơ sở.
- **CBDC bán buôn trên sổ cái token hoá** đóng vai trò neo. Lập luận trung tâm của bài là nếu không có tài sản quyết toán không rủi ro của ngân hàng trung ương hiện diện trực tiếp trên sổ cái, hệ thống token hoá sẽ tái tạo lại đúng các rủi ro tín dụng và thanh khoản mà nó hứa loại bỏ, chỉ là dưới hình thức mới.

### 3. Tác động lên ba khu vực

- **Ngân hàng.** Token hoá có thể rút ngắn chu kỳ quyết toán, giảm nhu cầu ký quỹ và giải phóng vốn. Nhưng nó cũng có thể đẩy nhanh tốc độ rút tiền gửi khi khủng hoảng, vì tiền có thể di chuyển tức thời và liên tục. Câu hỏi về việc quản lý thanh khoản trong môi trường hoạt động 24/7 chưa có lời giải đầy đủ.
- **Thị trường vốn.** Lợi ích rõ nhất nằm ở các thị trường có chu kỳ quyết toán dài và nhiều khâu đối soát, như trái phiếu doanh nghiệp, quỹ và các giao dịch xuyên biên giới. Token hoá cũng có thể mở rộng khả năng chia nhỏ tài sản, tăng tính tiếp cận với tài sản kém thanh khoản, tuy bài lưu ý rằng chia nhỏ không tự động tạo ra thanh khoản.
- **Hạ tầng thị trường tài chính.** Vai trò của trung tâm lưu ký, hệ thống quyết toán chứng khoán và đối tác bù trừ trung tâm bị đặt lại câu hỏi. Một số chức năng có thể được mã hoá vào sổ cái, nhưng các chức năng quản trị rủi ro, xử lý vỡ nợ và quản lý khủng hoảng thì khó thay thế bằng mã lệnh.

### 4. Tính chung quyết toán và quản trị mã lệnh

- Bài phân biệt rạch ròi giữa tính nguyên tử, một thuộc tính kỹ thuật của sổ cái, và tính chung quyết toán, một thuộc tính pháp lý xác định thời điểm mà việc chuyển giao không thể bị đảo ngược ngay cả khi một bên phá sản. Hai thứ này không tự động trùng nhau, và khoảng cách giữa chúng là nơi rủi ro ẩn nấp.
- Các câu hỏi pháp lý chưa được giải quyết thống nhất gồm: luật nào áp dụng cho một sổ cái phân tán qua nhiều quốc gia; token thuộc loại tài sản pháp lý nào; khi mã lệnh thực hiện đúng nhưng kết quả trái ý định các bên thì mã hay hợp đồng thắng; ai có quyền đảo ngược khi có gian lận hoặc lệnh toà án; và token của khách hàng có được tách khỏi khối tài sản phá sản của trung gian hay không.
- Về quản trị mã lệnh, bài đặt các câu hỏi thực tiễn: ai kiểm toán mã trước khi triển khai, ai có quyền nâng cấp, quy trình nào áp dụng khi phát hiện lỗi, và ai chịu trách nhiệm tài chính cho tổn thất do lỗi mã. Nguyên tắc đề xuất là cùng hoạt động thì cùng rủi ro và cùng quy định, bất kể hình thức công nghệ.

### 5. Rủi ro đối với các nền kinh tế mới nổi và đang phát triển

- Rủi ro nổi bật nhất là thay thế tiền tệ. Nếu token ngoại tệ, đặc biệt là stablecoin neo đô la, dễ tiếp cận qua điện thoại di động, người dân ở các nước có lạm phát cao hoặc đồng tiền biến động có thể chuyển sang dùng chúng nhanh hơn nhiều so với các đợt đô la hoá trước đây, vốn bị giới hạn bởi chi phí và ma sát vật lý.
- Hệ quả là chính sách tiền tệ trong nước mất hiệu lực, cơ sở tiền gửi của hệ thống ngân hàng bị bào mòn, và ngân hàng trung ương mất nguồn thu phát hành tiền.
- Các biện pháp quản lý dòng vốn có thể bị lách vì token di chuyển qua biên giới mà không đi qua hệ thống ngân hàng đại lý truyền thống, nơi các biện pháp này vốn được thực thi.
- Bài cũng nêu rủi ro ngược: nếu các nước này bị loại khỏi hạ tầng token hoá đang hình thành, chi phí và thời gian cho thanh toán xuyên biên giới cùng kiều hối có thể vẫn cao trong khi các nước khác hưởng lợi.

### 6. Ba kịch bản và lộ trình

- **Ngõ cụt:** các thí điểm không mở rộng được vì chi phí chuyển đổi vượt lợi ích và hệ thống hiện hành vẫn đủ tốt; token hoá thành một ngách.
- **Song song:** hai hệ thống cùng tồn tại được nối bằng cầu nối; hưởng một phần lợi ích nhưng chịu chi phí vận hành kép và thanh khoản phân mảnh.
- **Chuyển đổi:** tài chính bán buôn dịch chuyển lên hạ tầng token hoá chung có sCBDC làm neo; đạt lợi ích đầy đủ nhưng đòi hỏi mức độ phối hợp quốc tế chưa từng có.
- Lộ trình năm trụ cột: làm rõ khung pháp lý trước chứ không phải sau; bảo đảm có tài sản quyết toán của ngân hàng trung ương trên sổ cái; xây chuẩn liên thông để tránh phân mảnh; thiết lập quản trị mã lệnh có trách nhiệm giải trình; và bảo vệ các nền kinh tế mới nổi khỏi thay thế tiền tệ đồng thời xây năng lực giám sát.
- Các phụ lục minh hoạ bằng các dự án thực tế: Jura và Agorá về thanh toán xuyên biên giới bằng tiền token hoá, DTCC cùng Eurex và HQLAx về quản lý tài sản bảo đảm, nền tảng XC về kiến trúc liên thông, và so sánh trực tiếp giữa stablecoin với sCBDC về đặc tính rủi ro.

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
