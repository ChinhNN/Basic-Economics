# Chương 11 — Mặc cả (Bargaining)

**Nguồn:** Avinash K. Dixit và Barry J. Nalebuff, *The Art of Strategy: A Game Theorist's Guide to Success in Business and Life*, ấn bản đầu (W. W. Norton, 2008), Chương 11, kèm phụ lục "Rubinstein Bargaining" ở cuối chương.
**Tác giả:** Avinash K. Dixit (sinh 1944), nhà kinh tế Mỹ gốc Ấn, giáo sư danh dự Đại học Princeton; Barry J. Nalebuff (sinh 1958), giáo sư Trường Quản trị Yale. Sách kế thừa *Thinking Strategically* (1991) của cùng hai tác giả.
**Vị trí trong lập luận của cả cuốn sách:** Chương 11 thuộc Phần III, phần áp dụng công cụ lý thuyết trò chơi vào những tình huống cụ thể. Nó dùng lại ba công cụ của các chương trước: suy luận ngược và trò chơi tối hậu thư (ultimatum game) ở Chương 2; chiến lược bên bờ vực (brinkmanship) và nước đi chiến lược ở Chương 6; phát tín hiệu (signaling) ở Chương 8. Chương 10 vừa bàn về đấu giá, nơi người bán tạo cạnh tranh giữa nhiều người mua; Chương 11 chuyển sang tình huống chỉ có hai bên phải chia nhau phần giá trị chung. Chương kế tiếp, Chương 12, chuyển sang bỏ phiếu, tức cách một tập thể đông người ra quyết định chung.
**Ý chính:** Hai tác giả muốn người đọc hiểu rằng mặc cả không phải cuộc so tài ăn nói mà là một trò chơi có thể giải được. Ví dụ trung tâm là cuộc mặc cả lương giữa công đoàn và ban quản lý một khách sạn nghỉ dưỡng mùa hè: mùa kéo dài 101 ngày, mỗi ngày mở cửa lãi 1.000 USD. Suy luận ngược từ ngày cuối cho thấy (1) khi hai bên kiên nhẫn như nhau và có nhiều vòng mặc cả, phần lãi gần như được chia đôi; (2) thoả thuận phải đạt ngay ngày đầu; (3) bên nào có phương án dự phòng tốt hơn khi không thoả thuận được (BATNA) thì được chia nhiều hơn. Từ đó chương rút ra quy tắc "đo đúng chiếc bánh": chỉ phần giá trị tăng thêm so với tổng BATNA của hai bên mới là thứ đang được mặc cả (ví dụ chia tiền vé máy bay của một luật sư). Chương giải thích vì sao vẫn có đình công (thông tin không đối xứng, chiến lược bên bờ vực), đề xuất "đình công ảo" để hai bên chịu thiệt mà người ngoài không bị vạ lây, và kết bằng mô hình mặc cả Rubinstein: bên kiên nhẫn hơn được phần lớn hơn.

> **Lưu ý:** Sách viết khoảng 2007–2008, nên các ví dụ thực tế dừng ở thời điểm đó: cuộc đình công bóng chày nhà nghề năm 1980, vụ đóng cửa cảng năm 2002, mùa giải khúc côn cầu NHL 2004–05 bị huỷ, các cuộc đình công ảo ở Ý năm 1999–2000 (khi Ý còn dùng đồng lire). Từ đó tới nay: NHL và giải bóng chày nhà nghề Mỹ (MLB) đều có thêm những lần chủ đội đóng cửa không cho cầu thủ thi đấu; đàm phán khí hậu toàn cầu đã có Thoả thuận Paris (2015); đình công ảo vẫn là ý tưởng hiếm khi được áp dụng. Câu đùa về Enron trong một chú thích gợi lại vụ phá sản gian lận năm 2001 của tập đoàn năng lượng này. Chương có **7 chú thích chân trang** của tác giả, đã đưa vào đúng chỗ trong phần Nội dung chi tiết và ghi "Chú thích của tác giả". Có một lỗi nhỏ của sách: ví dụ chia vé máy bay mở đầu bằng "một công ty ở Dallas", nhưng toàn bộ phần sau (bảng giá vé, các phép tính) nói về Houston; bản tổng hợp dùng Houston. Các bảng và công thức trong sách là hình ảnh, đã được dựng lại bằng bảng markdown. Chương không có bài tập "Trip to the Gym". Các câu trích là bản dịch của người tổng hợp.

## Sơ đồ

### Phần mở đầu chương — câu chuyện thủ lĩnh công đoàn và bài toán khách sạn 101 ngày

```text
       Chuyện cười mở đầu: một thủ lĩnh công đoàn mới được bầu, lần đầu ngồi
       vào phòng họp hội đồng quản trị, buột miệng: "Chúng tôi muốn 10 USD
       một giờ, nếu không thì..." Ông chủ hỏi: "Nếu không thì sao?"
       Thủ lĩnh công đoàn đáp: "Thì 9,50 USD."
                                │
                                ▼
       Câu chuyện đặt ra các câu hỏi của mọi cuộc mặc cả:
       · có đạt thoả thuận không?
       · đạt êm thấm hay chỉ sau một cuộc đình công?
       · ai nhượng bộ, nhượng bộ khi nào?
       · ai được bao nhiêu trong "chiếc bánh" (phần giá trị đang tranh cãi)?
                                │
                                ▼
       Chương 2 đã dùng trò chơi tối hậu thư để minh hoạ suy luận ngược;
       chương này dùng cùng nguyên tắc nhưng sát thực tế hơn
                                │
                                ▼
       BÀI TOÁN KHÁCH SẠN NGHỈ DƯỠNG MÙA HÈ
       · mùa kéo dài 101 ngày; mỗi ngày mở cửa, khách sạn lãi 1.000 USD
       · khách sạn chỉ mở cửa khi công đoàn và ban quản lý đã thoả thuận
       · công đoàn đưa yêu cầu; ban quản lý chấp nhận, hoặc từ chối và hôm
         sau đưa đề nghị ngược lại; hai bên luân phiên mỗi ngày một lần
                                │
                                ▼
       SUY LUẬN NGƯỢC TỪ NGÀY CUỐI MÙA
       · chỉ còn 1 ngày, đến lượt công đoàn: ban quản lý nhận gì cũng hơn
         không, nên công đoàn lấy cả 1.000 USD (Chú thích của tác giả:
         thực tế phải chừa cho bên kia một phần nhỏ, ví dụ 100 USD)
       · còn 2 ngày, đến lượt ban quản lý: công đoàn có thể chờ để lấy
         1.000 USD vào ngày cuối, nên ban quản lý trả đúng 1.000 USD và
         giữ 1.000 USD; mỗi bên 500 USD mỗi ngày
       · còn 3 ngày, đến lượt công đoàn: đưa ban quản lý 1.000 USD, giữ
         2.000 USD; công đoàn 667 USD/ngày, ban quản lý 333 USD/ngày
       · cứ thế lùi về ngày đầu mùa (bảng đầy đủ ở Nội dung chi tiết, mục 1)
                                │
                                ▼
       KẾT QUẢ Ở NGÀY ĐẦU MÙA (còn 101 ngày, công đoàn đề nghị):
       công đoàn 505 USD/ngày, ban quản lý 495 USD/ngày
       · bên đề nghị cuối cùng có lợi thế, nhưng lợi thế nhỏ dần khi số
         vòng tăng lên
                                │
                                ▼
       HAI DỰ ĐOÁN CỦA LÝ THUYẾT
       1. khi khoảng cách giữa các lượt đề nghị ngắn và thời gian mặc cả
          dài, quy tắc thứ tự đề nghị không còn quan trọng: CHIA ĐÔI
       2. thoả thuận đạt ngay ngày đầu, vì hai bên cùng nhìn trước thấy một
          kết quả, chẳng có lý do gì để cùng mất 1.000 USD mỗi ngày
                                │
                                ▼
       Nhưng thực tế vẫn có đổ vỡ, đình công, thoả thuận lệch về một phía;
       phần còn lại của chương sửa giả định để giải thích các điều đó
```

### Tiểu mục "The Handicap System in Negotiations" — hệ thống điểm chấp trong đàm phán

```text
       Yếu tố quyết định cách chia bánh: CHI PHÍ CHỜ ĐỢI của mỗi bên
       · hai bên cùng mất lãi khi chưa thoả thuận, nhưng một bên có thể có
         nguồn thu khác bù lại một phần
                                │
                                ▼
       TRƯỜNG HỢP 1: đoàn viên công đoàn kiếm được 300 USD/ngày bên ngoài
       trong lúc mặc cả
       · mỗi lượt của ban quản lý, họ phải trả công đoàn phần công đoàn sẽ
         có vào hôm sau CỘNG thêm ít nhất 300 USD cho hôm nay
       · kết quả: vẫn thoả thuận ngay ngày đầu, không đình công, nhưng công
         đoàn được 653 USD/ngày, ban quản lý 347 USD/ngày
                                │
                                ▼
       Cách hiểu như "điểm chấp" trong golf:
       · công đoàn xuất phát với 300 USD đã chắc chắn có
       · còn 700 USD để mặc cả, chia đôi mỗi bên 350 USD
       · công đoàn 650 USD, ban quản lý 350 USD
                                │
                                ▼
       TRƯỜNG HỢP 2: ban quản lý vận hành khách sạn bằng lao động thay thế
       người đình công, lãi 500 USD/ngày (lao động kém hiệu quả hoặc
       phải trả cao hơn, khách ngại đi qua hàng rào người đình công);
       đoàn viên không có thu nhập ngoài
       · ban quản lý 750 USD, công đoàn 250 USD, vẫn thoả thuận ngay
                                │
                                ▼
       TRƯỜNG HỢP 3: công đoàn có 300 USD bên ngoài VÀ ban quản lý lãi 500
       USD khi dùng lao động thay thế
       · chỉ còn 200 USD để mặc cả, chia đôi
       · ban quản lý 600 USD, công đoàn 400 USD
                                │
                                ▼
       NGUYÊN TẮC: bên nào tự mình làm được càng tốt khi không có thoả
       thuận thì phần bánh của bên đó càng lớn
```

### Tiểu mục "Measuring the Pie" — đo chiếc bánh

```text
       Bước đầu tiên của mọi cuộc đàm phán: đo đúng chiếc bánh
       · trong trường hợp 3, hai bên KHÔNG mặc cả 1.000 USD
       · không thoả thuận: công đoàn có 300 USD, ban quản lý có 500 USD
       · thoả thuận chỉ tạo thêm 200 USD; đó mới là chiếc bánh
                                │
                                ▼
       BATNA (Best Alternative to a Negotiated Agreement), thuật ngữ của
       Roger Fisher và William Ury: phương án thay thế tốt nhất khi không
       đạt thoả thuận, tức điều tốt nhất bạn có nếu không thoả thuận được
       với bên này
       · ai cũng có BATNA của mình mà không cần đàm phán
       · nên chiếc bánh là phần giá trị tạo ra VƯỢT TRÊN tổng các BATNA
                                │
                                ▼
       VÍ DỤ VÉ MÁY BAY CỦA LUẬT SƯ (phỏng theo một vụ thật)
       · hai công ty, ở Houston và San Francisco (SF), thuê chung một luật
         sư ở New York (NY)
       · luật sư bay vòng tam giác NY–Houston–SF–NY thay vì hai chuyến
       · giá vé một chiều: NY–Houston 666 USD; Houston–SF 909 USD;
         SF–NY 1.243 USD; tổng chuyến tam giác 2.818 USD
       · nếu đi riêng, vé khứ hồi đúng bằng hai lần vé một chiều
                                │
                                ▼
       CÁC CÁCH CHIA "TÙY HỨNG" (ad hoc)
       · chia đôi: mỗi bên 1.409 USD; Houston từ chối, vì tự đi khứ hồi
         chỉ tốn 2 × 666 = 1.332 USD
       · mỗi bên trả chặng của mình, chia đôi chặng Houston–SF: SF trả
         1.697,50 USD, Houston trả 1.120,50 USD
       · chia theo tỷ lệ vé khứ hồi: SF trả 1.835 USD, Houston trả 983 USD
                                │
                                ▼
       CÁCH CỦA HAI TÁC GIẢ: bắt đầu từ BATNA
       · không thoả thuận: luật sư đi hai chuyến riêng, Houston tốn 1.332
         USD, SF tốn 2.486 USD, tổng 3.818 USD
       · chuyến tam giác tốn 2.818 USD; khoản tiết kiệm 1.000 USD là
         chiếc bánh
       · mỗi công ty cần thiết như nhau để có khoản tiết kiệm này; nếu
         kiên nhẫn như nhau thì chia đôi, mỗi bên tiết kiệm 500 USD
       · Houston trả 832 USD, SF trả 1.986 USD
                                │
                                ▼
       Bài học: không chia theo số dặm hay giá vé tương đối; vé đi Houston
       rẻ hơn không có nghĩa Houston được hưởng ít tiền tiết kiệm hơn
       · cách chia này có gốc từ nguyên tắc "chia tấm vải" trong Talmud
                                │
                                ▼
       Ở các ví dụ trên BATNA là cố định; khi BATNA thay đổi được, mở ra
       chiến lược tác động lên BATNA: nâng BATNA của mình, hạ BATNA của
       đối phương (hai mục tiêu đôi khi mâu thuẫn nhau)
```

### Tiểu mục "This Will Hurt You More Than It Hurts Me" — việc này làm anh đau hơn tôi

```text
       Điều quan trọng là phương án bên ngoài của mình SO VỚI của đối thủ
       · có thể có lợi khi đưa ra cam kết hay đe doạ làm giảm phương án
         bên ngoài của CẢ HAI, miễn là đối thủ bị thiệt nặng hơn
                                │
                                ▼
       VÍ DỤ KHÁCH SẠN (tiếp trường hợp 3: công đoàn 400, ban quản lý 600)
       · công đoàn bỏ 100 USD/ngày thu nhập ngoài để tăng cường biểu tình
         chặn cửa, làm lãi của ban quản lý giảm 200 USD/ngày
       · điểm xuất phát mới: công đoàn 200 USD, ban quản lý 300 USD
       · còn 500 USD chia đôi: công đoàn 450 USD, ban quản lý 550 USD
       · công đoàn được thêm 50 USD nhờ đe doạ làm cả hai đau, nhưng làm
         ban quản lý đau hơn
                                │
                                ▼
       VÍ DỤ BÓNG CHÀY NHÀ NGHỀ MỸ NĂM 1980
       · cầu thủ đình công trong mùa thi đấu giao hữu, quay lại khi mùa
         chính thức bắt đầu, đe doạ đình công tiếp từ dịp lễ Chiến sĩ trận
         vong (Memorial Day, cuối tháng 5)
       · mùa giao hữu: cầu thủ không có lương, chủ đội vẫn có doanh thu
         từ khách du lịch và dân địa phương
       · mùa chính thức: lương cầu thủ đều mỗi tuần; doanh thu vé và
         truyền hình của chủ đội thấp lúc đầu, tăng mạnh từ Memorial Day
       · thiệt hại của chủ đội SO VỚI cầu thủ lớn nhất đúng ở hai giai đoạn
         cầu thủ chọn để đình công
       · chủ đội nhượng bộ ngay trước nửa sau của cuộc đình công
                                │
                                ▼
       Nhưng nửa đầu cuộc đình công đã thật sự xảy ra: lý thuyết suy luận
       ngược chưa đủ; vì sao có đình công?
```

### Tiểu mục "Brinkmanship and Strikes" — chiến lược bên bờ vực và đình công

```text
       Trước khi hợp đồng cũ hết hạn, chưa có gì cấp bách: công việc vẫn
       chạy, không mất sản lượng; tưởng như mỗi bên nên chờ tới phút chót
       · nhưng thực tế nhiều khi thoả thuận đạt sớm hơn nhiều
                                │
                                ▼
       Lý do: chính quá trình đàm phán có rủi ro
       · hiểu sai mức kiên nhẫn hay phương án bên ngoài của bên kia
       · căng thẳng, va chạm cá nhân, nghi ngờ bên kia không thiện chí
       → đàm phán có thể đổ vỡ dù cả hai bên đều muốn thành công
                                │
                                ▼
       Hai bên không cùng nhìn thấy một điểm kết thúc
       · thông tin và góc nhìn khác nhau; mỗi bên phải đoán chi phí chờ
         đợi của bên kia
       · bên có chi phí chờ thấp được lợi, nên ai cũng TUYÊN BỐ chi phí của
         mình thấp; lời nói suông không được tin
       · cách chứng minh: bắt đầu chịu chi phí và cho thấy mình trụ lâu
         hơn, hoặc chấp nhận rủi ro lớn hơn
       → thiếu một cái nhìn chung về kết cục là nguyên nhân khởi đầu đình
         công
                                │
                                ▼
       ĐÌNH CÔNG LÀ MỘT DẠNG PHÁT TÍN HIỆU
       · ai cũng nói được "tôi chịu đình công được"; dám đình công thật là
         bằng chứng tốt nhất
       · như mọi tín hiệu, nó tốn kém và làm mất hiệu quả
                                │
                                ▼
       CHIẾN LƯỢC BÊN BỜ VỰC
       · đe doạ cắt đứt đàm phán và đình công ngay thì không đáng tin, vì
         đình công cũng tốn kém cho đoàn viên
       · đe doạ nhỏ hơn thì đáng tin: căng thẳng tăng dần, đổ vỡ có thể
         xảy ra dù công đoàn không muốn
       · chiến lược này là vũ khí của bên MẠNH hơn, tức bên ít sợ đổ vỡ
         hơn
                                │
                                ▼
       LÀM VIỆC THEO HỢP ĐỒNG ĐÃ HẾT HẠN
       · bên muốn đổi điều khoản (thường là công đoàn) chịu thiệt nặng:
         ban quản lý cứ để đàm phán kéo dài mãi trong khi hợp đồng cũ vẫn
         chạy (Chú thích của tác giả: có thể công đoàn đang chờ thời điểm
         đình công gây thiệt hại nhất, như đình công ở UPS ngay trước
         Giáng sinh thay vì giữa tháng 8)
       · cần có một xác suất đình công thì doanh nghiệp mới chịu đáp ứng;
         tiếp tục làm theo hợp đồng hết hạn bị coi là dấu hiệu công đoàn
         yếu
                                │
                                ▼
       ĐIỀU GÌ GIỮ CUỘC ĐÌNH CÔNG KÉO DÀI?
       · đe doạ "không bao giờ quay lại làm" không đáng tin
       · đe doạ "chờ thêm một ngày, một tuần" thì đáng tin: thiệt hại nhỏ
         hơn lợi ích kỳ vọng
       · nếu công nhân đúng, ban quản lý nên nhượng bộ ngay; nhưng nếu ban
         quản lý tin công nhân sắp chịu thua, họ cũng chờ thêm
       → cả hai cùng cầm cự, đình công kéo dài
                                │
                                ▼
       SO SÁNH VỚI CHIẾN LƯỢC BÊN BỜ VỰC Ở CHƯƠNG 6
       · dạng ở Chương 6: xác suất NHỎ nhưng tăng dần của một thiệt hại LỚN
       · đình công: xác suất LỚN (gần chắc chắn) của một thiệt hại NHỎ
         nhưng thiệt hại lớn dần theo thời gian
       · một bên chỉ lùi khi phát hiện bên kia thật sự mạnh hơn
       · sức mạnh có nhiều dạng: ít thiệt khi chờ (có phương án tốt), rất
         cần thắng (vì còn đàm phán với công đoàn khác), thua rất đắt
                                │
                                ▼
       ÁP DỤNG GIỮA CÁC QUỐC GIA: Mỹ muốn đồng minh gánh thêm chi phí quốc
       phòng, nhưng ở thế "làm việc theo hợp đồng hết hạn": thoả thuận cũ
       (Mỹ gánh phần lớn) vẫn chạy, đồng minh vui lòng kéo dài đàm phán
       · hai tác giả để ngỏ câu hỏi: Mỹ có thể, và có nên, dùng chiến lược
         bên bờ vực không?
                                │
                                ▼
       Rủi ro thay đổi bản chất mặc cả: với chiến lược bên bờ vực, đôi khi
       hai bên rơi xuống vực thật; đổ vỡ và đình công có thể tự có đà và
       kéo dài lâu bất ngờ
```

### Tiểu mục "Simultaneous Bargaining over Many Issues" — mặc cả đồng thời nhiều vấn đề

```text
       Thực tế có nhiều khía cạnh: lương, bảo hiểm y tế, lương hưu, điều
       kiện làm việc; tổng lượng phát thải CO2 và cách phân bổ giữa các
       nước
       · về nguyên tắc quy được ra tiền, nhưng MỖI BÊN ĐỊNH GIÁ KHÁC NHAU
                                │
                                ▼
       VÍ DỤ BẢO HIỂM Y TẾ
       · công ty mua bảo hiểm nhóm 1.000 USD/năm cho gia đình bốn người;
         công nhân tự mua mất 2.000 USD/năm
       · công nhân thích bảo hiểm hơn 1.500 USD lương thêm; công ty cũng
         thích trả bảo hiểm hơn trả 1.500 USD lương thêm
       → gộp các vấn đề vào một "nồi" chung, tận dụng khác biệt định giá
       · bằng chứng: đàm phán tự do hoá thương mại rộng trong GATT và WTO
         thành công hơn đàm phán hẹp theo từng ngành, từng mặt hàng
                                │
                                ▼
       MẶT TRÁI: gộp vấn đề cho phép dùng trò chơi này để tạo đe doạ trong
       trò chơi khác
       · Mỹ có thể đòi Nhật mở cửa thị trường bằng cách đe doạ phá vỡ quan
         hệ quân sự, để Nhật đối mặt rủi ro bị Triều Tiên hay Trung Quốc
         gây hấn
       · Mỹ không muốn điều đó xảy ra; chỉ là đe doạ
       → vì vậy Nhật sẽ đòi đàm phán kinh tế và quân sự TÁCH RIÊNG
```

### Tiểu mục "The Virtues of a Virtual Strike" — ưu điểm của đình công ảo

```text
       Đình công làm hại cả những người không ngồi vào bàn đàm phán
       · UPS đình công: khách hàng không nhận được bưu kiện
       · nhân viên hành lý Air France đình công: kỳ nghỉ bị phá hỏng
       · không thoả thuận về phát thải CO2: các thế hệ tương lai (không có
         ghế ở bàn đàm phán) chịu hậu quả
                                │
                                ▼
       Thiệt hại phụ có thể lớn hơn nhiều so với khoản tranh chấp
       · cuộc đóng cửa cảng 10 ngày năm 2002 (tới khi Tổng thống Bush can
         thiệp ngày 3/10/2002 theo Luật Taft-Hartley) gây thiệt hại cho
         kinh tế Mỹ hơn 10 tỷ USD
       · khoản tranh chấp: 20 triệu USD cải thiện năng suất
       · thiệt hại phụ gấp 500 lần khoản tranh chấp
                                │
                                ▼
       Ý TƯỞNG ĐÌNH CÔNG ẢO (đã có hơn 50 năm)
       · công nhân vẫn làm việc bình thường, doanh nghiệp vẫn sản xuất
       · trong thời gian đình công ảo, KHÔNG BÊN NÀO được trả tiền: công
         nhân làm không lương; doanh nghiệp nộp TOÀN BỘ DOANH THU (không
         chỉ lợi nhuận, vì lợi nhuận khó đo và có thể đánh giá thấp
         thiệt hại thật)
       · doanh thu chuyển cho nhà nước, cho từ thiện, hoặc sản phẩm được
         phát miễn phí cho khách
       · hai bên vẫn chịu đau nên vẫn có động lực thoả thuận; người ngoài
         không bị vạ lây, thậm chí được lợi
                                │
                                ▼
       So sánh với đình công thật: NHL đóng cửa mùa 2004–05, cả mùa bị
       huỷ, không có Cúp Stanley, lượng khán giả rất lâu mới hồi phục
                                │
                                ▼
       ĐÃ ĐƯỢC ÁP DỤNG
       · Thế chiến II: hải quân Mỹ dùng đình công ảo ở nhà máy van Jenkins
         Company, Bridgeport, Connecticut
       · 1960: đình công xe buýt ở Miami, khách được đi miễn phí
       · 1999: phi công và tiếp viên hãng Meridiana, cuộc đình công ảo đầu
         tiên ở Ý; hãng tặng doanh thu chuyến bay cho từ thiện, chuyến bay
         không bị gián đoạn
       · 2000: 300 phi công của Công đoàn Vận tải Ý nộp 100 triệu lire; tiền
         mua thiết bị y tế cho một bệnh viện nhi
                                │
                                ▼
       NGHỊCH LÝ: lợi ích quan hệ công chúng của đình công ảo có thể làm nó
       khó áp dụng
       · đình công thật thường nhằm làm khách hàng khó chịu để họ ép ban
         quản lý; nộp lợi nhuận có thể chưa tái tạo đủ thiệt hại thật
       · trong cả bốn ví dụ lịch sử, doanh nghiệp đều nộp toàn bộ doanh thu
                                │
                                ▼
       Vì sao công nhân chịu làm không lương? Cùng lý do họ đình công: gây
       đau cho ban quản lý và chứng minh chi phí chờ của mình thấp
       · thậm chí họ có thể làm CHĂM hơn, vì mỗi đơn hàng thêm là thêm một
         khoản doanh thu doanh nghiệp phải nộp
                                │
                                ▼
       Miễn là BATNA của hai bên trong đình công ảo bằng trong đình công
       thật, không bên nào có lợi khi chọn đình công thật
       · thời điểm đúng để thoả thuận dùng đình công ảo là khi hai bên còn
         đang nói chuyện, trước lần đàm phán hợp đồng kế tiếp
```

### Tiểu mục "Case Study: 'Tis Better to Give Than to Receive?" — cho thì có phúc hơn nhận?

```text
       Khách sạn 101 ngày, lãi 1.000 USD/ngày, nhưng CHỈ ban quản lý được
       đưa đề nghị; công nhân chỉ chấp nhận hoặc từ chối
                                │
                                ▼
       SUY LUẬN NGƯỢC
       · ngày cuối: công nhân nhận bất kỳ khoản dương nào, ví dụ 1 USD
       · ngày áp chót: từ chối chỉ được 1 USD ngày mai, nên nhận 2 USD hôm
         nay
       · ngày đầu mùa: ban quản lý đề nghị 101 USD trên tổng 101.000 USD,
         công nhân chấp nhận
       → khi đưa đề nghị, "cho" có lợi hơn "nhận" (chơi chữ câu Kinh Thánh)
                                │
                                ▼
       Phân tích này phóng đại sức mạnh của ban quản lý
       · hoãn một ngày, ban quản lý mất 999 USD, công nhân mất 1 USD
       · nếu công nhân quan tâm cả việc so sánh với ban quản lý, chia lệch
         cực đoan như vậy không thể xảy ra
       · nhưng cũng không quay về chia đôi: nếu ngày cuối công nhân chấp
         nhận 200 USD so với 800 USD, ban quản lý duy trì tỷ lệ 4:1 suốt
         101 ngày và giữ 80% tổng lãi
                                │
                                ▼
       TRÒ CHƠI LẶP KHÁC TRÒ CHƠI MỘT LẦN
       · một lần (chia 100 USD): đề nghị 80:20 bị từ chối thì đã quá muộn
       · lặp 101 lần: bên nhận có động cơ tỏ ra cứng rắn lúc đầu, như thể
         phi lý hoặc chỉ chấp nhận chia 50:50 (Chú thích của tác giả: điều
         này đưa vào sự bất định về sở thích của đối phương)
                                │
                                ▼
       TRƯỜNG HỢP CHỈ CÒN 2 NGÀY
       · đề nghị 80:20 bị từ chối: nếu nhận, bên kia được 200 + 200 = 400;
         từ chối rồi được chia đôi ngày cuối thì được 500, nên từ chối có
         thể chỉ là lừa; bạn có thể giữ 80:20 ở ngày cuối
       · đề nghị 67:33 bị từ chối: nếu nhận, bên kia được 333 + 333 = 666;
         từ chối thì tốt nhất chỉ được 500; tự làm mình thiệt là bằng chứng
         không phải lừa, nên chia 50:50 ở ngày cuối có thể hợp lý
                                │
                                ▼
       NGHỊCH LÝ: bên kia thường được lợi khi TỎ RA phi lý, nên đừng tin
       ngay; nhưng nếu họ tự gây thiệt quá lớn mà lừa không có lợi, hãy
       đánh giá lại mục tiêu của họ
```

### Phụ lục "Appendix: Rubinstein Bargaining" — mô hình mặc cả Rubinstein

```text
       Không có ngày kết thúc thì có giải được không? Ariel Rubinstein tìm
       ra cách giải
       · hai bên luân phiên đề nghị chia chiếc bánh có kích thước 1, ví dụ
         (3/4 cho tôi, 1/4 cho anh)
       · trò chơi kết thúc khi một bên chấp nhận; từ chối làm chậm thoả
         thuận, mà thoả thuận hôm nay đáng giá hơn ngày mai
                                │
                                ▼
       ĐO SỰ SỐT RUỘT BẰNG δ: phần giá trị còn lại nếu thoả thuận ở vòng sau
       thay vì hôm nay
       · tiền: lãi suất 10%/năm thì 1 USD hôm nay bằng 1,10 USD năm sau
       · rủi ro: khách quen bỏ sang nhà cung cấp khác, doanh nghiệp đóng
         cửa, công nhân phải tìm việc lương thấp hơn, uy tín thủ lĩnh công
         đoàn và quyền chọn cổ phiếu của ban quản lý mất giá
       · δ = 0,99: kiên nhẫn; δ = 1/3: mất hai phần ba giá trị mỗi tuần
       · vòng đề nghị cách một tuần: δ khoảng 0,99; cách một phút: δ khoảng
         0,999999
                                │
                                ▼
       LẬP LUẬN: tìm mức thấp nhất L bạn từng chấp nhận
       · bên kia biết bạn không nhận dưới L, nên ở lượt của họ, họ được tối
         đa 1 − L; vậy hôm nay ở lượt của bạn họ sẽ nhận δ(1 − L)
       · bạn từ chối hôm nay, mai đề nghị họ δ(1 − L) và giữ 1 − δ(1 − L)
       · nên hôm nay không nhận dưới δ(1 − δ(1 − L)), suy ra
         L ≥ δ(1 − δ)/(1 − δ²) = δ/(1 + δ)
                                │
                                ▼
       Tương tự, mức cao nhất M bạn có thể mong: bên kia không nhận dưới
       δ/(1 + δ), nên vòng sau bạn được tối đa 1/(1 + δ); hôm nay bạn nhận
       mọi mức từ δ/(1 + δ) trở lên, tức M ≤ δ/(1 + δ)
       → L và M trùng nhau: bên trả lời được δ/(1 + δ), bên đề nghị được
         1/(1 + δ)
                                │
                                ▼
       BA TRƯỜNG HỢP
       · δ = 1 (chờ không tốn gì): bên trả lời được 1/2, chia đôi
       · δ = 0 (bánh mất hết nếu từ chối): (0, 1), đúng trò chơi tối hậu thư
       · δ = 1/2: bên trả lời được 1/3, bên đề nghị 2/3, tỷ lệ 2:1
                                │
                                ▼
       KIÊN NHẪN KHÁC NHAU: bên kiên nhẫn hơn được phần lớn hơn; khi khoảng
       cách giữa các vòng ngắn lại, bánh chia theo tỷ lệ nghịch với chi phí
       chờ (Chú thích của tác giả: công đoàn δ = 0,99, ban quản lý δ = 0,98;
       ban quản lý sốt ruột gấp đôi nên được một phần ba, công đoàn hai phần
       ba)
                                │
                                ▼
       HÀM Ý CHO NƯỚC MỸ: hệ thống chính trị và truyền thông Mỹ nuôi dưỡng
       sự sốt ruột; nhóm vận động hành lang, nghị sĩ, báo chí ép chính quyền
       đòi kết quả nhanh, và đối thủ biết điều đó nên đòi được nhượng bộ lớn
```

## Ba câu hỏi chương này trả lời

1. **Khi hai bên phải chia một phần giá trị chung, ai được bao nhiêu?** Suy luận ngược cho thấy bên được đưa đề nghị cuối cùng có lợi thế, nhưng lợi thế đó nhỏ dần khi có nhiều vòng: ở khách sạn 101 ngày, công đoàn (bên đề nghị cuối) chỉ được 505 USD mỗi ngày so với 495 USD của ban quản lý. Khi hai bên kiên nhẫn như nhau và các vòng đề nghị cách nhau ngắn, kết quả là chia đôi phần giá trị vượt trên BATNA của hai bên. Bên nào có BATNA cao hơn (công đoàn kiếm được 300 USD bên ngoài, ban quản lý lãi 500 USD với lao động thay thế) hoặc kiên nhẫn hơn (δ cao hơn) thì được phần lớn hơn.
2. **Nếu lý thuyết dự đoán thoả thuận đạt ngay ngày đầu, tại sao vẫn có đình công?** Vì hai bên không cùng thông tin: mỗi bên phải đoán chi phí chờ của bên kia, và ai cũng có lợi khi tuyên bố chi phí của mình thấp. Lời nói không đủ, nên phải chứng minh bằng cách chịu chi phí thật, tức đình công như một tín hiệu. Chiến lược bên bờ vực làm đình công kéo dài từng ngày, cho tới khi một bên nhận ra bên kia thật sự mạnh hơn.
3. **Có cách nào giữ nguyên sức ép của đình công mà không làm hại người ngoài cuộc không?** Có: đình công ảo. Công nhân làm không lương, doanh nghiệp nộp toàn bộ doanh thu cho từ thiện, nhà nước hoặc khách hàng. Sức mạnh mặc cả (BATNA) của hai bên không đổi, nhưng người ngoài không mất gì; trong vụ đóng cửa cảng năm 2002, thiệt hại phụ (hơn 10 tỷ USD) gấp 500 lần khoản tranh chấp (20 triệu USD).

## Khái niệm cần biết

**Mặc cả (bargaining) và "chiếc bánh" (the pie).** Tình huống hai bên cùng tạo ra một phần giá trị nếu thoả thuận được và phải quyết định chia phần đó. "Chiếc bánh" là ẩn dụ của chính hai tác giả cho phần giá trị đang được chia. Ví dụ: khách sạn lãi 1.000 USD mỗi ngày mở cửa, và chỉ mở cửa khi công đoàn và ban quản lý đã thoả thuận về lương. Đây là đối tượng của cả chương.

**Suy luận ngược trong mặc cả luân phiên (backward reasoning in alternating offers).** Bắt đầu từ vòng cuối cùng, xác định ai được gì, rồi lùi dần từng vòng. Ví dụ: còn 1 ngày, công đoàn lấy cả 1.000 USD; còn 2 ngày, ban quản lý chia 500 USD/500 USD mỗi ngày; còn 101 ngày, 505 USD/495 USD. Quan trọng vì nó cho ra hai dự đoán chính của chương: gần chia đôi và thoả thuận ngay.

**BATNA (Best Alternative to a Negotiated Agreement), phương án thay thế tốt nhất khi không đạt thoả thuận.** Thuật ngữ của Roger Fisher và William Ury: điều tốt nhất một bên có được nếu không thoả thuận với bên kia. Ví dụ: trong lúc mặc cả, công đoàn có 300 USD/ngày từ việc làm bên ngoài, ban quản lý có 500 USD/ngày nhờ lao động thay thế. Hai tác giả gọi nó là ý tưởng "vừa sâu sắc vừa đơn giản một cách đánh lừa": nó quyết định cả kích thước chiếc bánh lẫn phần của mỗi bên.

**Đo chiếc bánh (measuring the pie).** Chiếc bánh không phải tổng giá trị mà là phần giá trị thoả thuận tạo thêm so với tổng BATNA. Ví dụ: khách sạn lãi 1.000 USD nhưng tổng BATNA là 800 USD, nên chỉ có 200 USD được mặc cả; vé máy bay của luật sư thì chiếc bánh là 3.818 − 2.818 = 1.000 USD tiết kiệm. Quan trọng vì đo sai bánh dẫn tới những cách chia nghe hợp lý nhưng một bên sẽ từ chối.

**Điểm chấp (handicap).** Ẩn dụ của hai tác giả lấy từ golf: mỗi bên xuất phát với BATNA của mình như một điểm chấp, rồi chia đôi phần còn lại. Ví dụ: công đoàn chấp 300 USD, còn 700 USD chia đôi, công đoàn được 650 USD, ban quản lý 350 USD. Quan trọng vì nó là cách tính nhanh kết quả mặc cả khi hai bên kiên nhẫn như nhau.

**Chi phí chờ đợi và hệ số kiên nhẫn δ (cost of waiting, discount factor).** δ là phần giá trị còn lại nếu thoả thuận chậm một vòng. Ví dụ: 1 USD tuần sau đáng 99 xu hôm nay thì δ = 0,99; δ = 1/3 nghĩa là mỗi tuần mất hai phần ba giá trị. Trong mô hình Rubinstein, bên trả lời được δ/(1 + δ), bên đề nghị được 1/(1 + δ). Quan trọng vì bên kiên nhẫn hơn được phần lớn hơn, nên ai cũng muốn tỏ ra ít sốt ruột.

**Chiến lược bên bờ vực (brinkmanship).** Cố ý tạo ra một rủi ro mà cả hai bên không kiểm soát hết, để bên kia nhượng bộ (đã giới thiệu ở Chương 6). Ví dụ: công đoàn không đe doạ đình công ngay (không đáng tin) mà để căng thẳng tăng dần, đổ vỡ có thể xảy ra dù không ai muốn; khi đình công đã nổ ra thì đe doạ "thêm một ngày nữa". Quan trọng vì nó giải thích vì sao đôi khi hai bên thật sự "rơi xuống vực": đình công xảy ra và kéo dài.

**Đình công như tín hiệu (strike as signaling).** Hành động tốn kém để chứng minh điều mà lời nói không chứng minh được, ở đây là chi phí chờ thấp. Ví dụ: ai cũng nói được "chúng tôi chịu được đình công", nhưng chỉ bên thật sự chịu được mới dám đình công. Quan trọng vì nó cho thấy đình công là cái giá của thông tin không đối xứng.

**Đình công ảo (virtual strike).** Công nhân vẫn làm, doanh nghiệp vẫn sản xuất, nhưng công nhân không nhận lương và doanh nghiệp nộp toàn bộ doanh thu cho bên thứ ba. Ví dụ: năm 1999 hãng Meridiana ở Ý tặng doanh thu chuyến bay cho từ thiện trong khi phi công và tiếp viên làm không lương. Quan trọng vì nó giữ nguyên BATNA của hai bên mà loại bỏ thiệt hại cho người ngoài cuộc.

**Mặc cả nhiều vấn đề (multi-issue bargaining).** Đàm phán đồng thời nhiều hạng mục mà mỗi bên định giá khác nhau. Ví dụ: bảo hiểm y tế công ty mua nhóm hết 1.000 USD, công nhân tự mua hết 2.000 USD; cả hai đều thích bảo hiểm hơn 1.500 USD lương. Quan trọng vì nó tạo thêm giá trị, nhưng cũng cho phép dùng vấn đề này để đe doạ ở vấn đề khác.

## Nội dung chi tiết

### 1. Mở đầu chương: chuyện thủ lĩnh công đoàn và bài toán khách sạn 101 ngày

Chương mở bằng một chuyện cười. Một thủ lĩnh công đoàn mới được bầu tới phiên mặc cả gay go đầu tiên trong phòng họp hội đồng quản trị. Lo lắng và choáng ngợp, ông buột miệng: "Chúng tôi muốn 10 USD một giờ, nếu không thì...". Ông chủ hỏi vặn: "Nếu không thì sao?". Thủ lĩnh công đoàn đáp: "Thì 9,50 USD". Hai tác giả nhận xét ít thủ lĩnh công đoàn lùi nhanh như vậy, và các ông chủ ngày nay thường cần tới mối đe doạ cạnh tranh từ Trung Quốc, chứ không phải quyền lực của chính mình, để buộc công nhân chấp nhận giảm lương. Nhưng câu chuyện đặt ra mọi câu hỏi của mặc cả: có thoả thuận không, thoả thuận êm thấm hay sau đình công, ai nhượng bộ và khi nào, ai được bao nhiêu trong chiếc bánh.

Chương 2 đã dùng trò chơi tối hậu thư để minh hoạ nguyên tắc nhìn trước và suy luận ngược, và đã hy sinh nhiều chi tiết thực tế để nguyên tắc nổi bật. Chương này dùng lại nguyên tắc đó nhưng chú ý hơn tới các vấn đề nảy sinh trong mặc cả ở kinh doanh, chính trị và đời sống.

Để suy luận ngược, cần một điểm kết thúc cố định trong tương lai, nên hai tác giả chọn một doanh nghiệp có điểm kết thúc tự nhiên: một khách sạn ở khu nghỉ dưỡng mùa hè. Mùa kéo dài 101 ngày; mỗi ngày mở cửa khách sạn lãi 1.000 USD. Đầu mùa, công đoàn và ban quản lý mặc cả về lương. Công đoàn đưa yêu cầu; ban quản lý chấp nhận, hoặc từ chối và hôm sau đưa đề nghị ngược lại. Khách sạn chỉ mở cửa sau khi đã có thoả thuận.

Hãy bắt đầu từ tình huống cực đoan: mặc cả kéo dài tới mức dù vòng tới có thoả thuận thì khách sạn cũng chỉ mở được ngày cuối. Thực tế mặc cả không kéo dài như thế, nhưng chính suy nghĩ về điểm cực đoan này quyết định điều xảy ra. Nếu đến lượt công đoàn, ban quản lý nhận gì cũng hơn không, nên công đoàn lấy cả 1.000 USD. (Chú thích của tác giả: có thể giả định thực tế hơn rằng ban quản lý cần một phần tối thiểu, ví dụ 100 USD, nhưng điều đó chỉ làm phép tính rắc rối hơn mà không đổi ý chính. Đây là vấn đề đã bàn trong trò chơi tối hậu thư gốc: phải cho bên kia đủ để họ không từ chối vì tức tối.) Lùi lại một ngày, đến lượt ban quản lý: họ biết công đoàn có thể từ chối và lấy 1.000 USD vào ngày cuối, nên không thể đề nghị ít hơn; công đoàn cũng không thể được hơn 1.000 USD, nên ban quản lý không cần đề nghị nhiều hơn. (Chú thích của tác giả: lại có vấn đề một chút "đường ngọt" thêm cho bên kia, hai tác giả bỏ qua để trình bày cho gọn.) Vậy trong 2.000 USD lãi của hai ngày cuối, ban quản lý giữ một nửa: mỗi bên 500 USD mỗi ngày. Lùi thêm một ngày, công đoàn đề nghị ban quản lý 1.000 USD và giữ 2.000 USD, tức công đoàn 667 USD/ngày và ban quản lý 333 USD/ngày.

**Các vòng mặc cả lương liên tiếp (Bảng dựng lại từ sách)**

| Số ngày còn lại | Bên đề nghị | Công đoàn: tổng | Công đoàn: mỗi ngày | Ban quản lý: tổng | Ban quản lý: mỗi ngày |
|---|---|---|---|---|---|
| 1 | Công đoàn | 1.000 USD | 1.000 USD | 0 USD | 0 USD |
| 2 | Ban quản lý | 1.000 USD | 500 USD | 1.000 USD | 500 USD |
| 3 | Công đoàn | 2.000 USD | 667 USD | 1.000 USD | 333 USD |
| 4 | Ban quản lý | 2.000 USD | 500 USD | 2.000 USD | 500 USD |
| 5 | Công đoàn | 3.000 USD | 600 USD | 2.000 USD | 400 USD |
| ... | ... | ... | ... | ... | ... |
| 100 | Ban quản lý | 50.000 USD | 500 USD | 50.000 USD | 500 USD |
| 101 | Công đoàn | 51.000 USD | 505 USD | 50.000 USD | 495 USD |

Mỗi lần công đoàn đề nghị, họ có lợi thế nhờ được đưa đề nghị "được ăn cả, ngã về không" cuối cùng. Nhưng lợi thế đó nhỏ dần khi số vòng tăng: đầu mùa 101 ngày, vị thế hai bên gần như ngang nhau, 505 USD so với 495 USD. Kết quả gần giống hệt nếu ban quản lý là bên đề nghị cuối, hoặc nếu không có quy tắc cứng như mỗi ngày một đề nghị hay luân phiên đề nghị. Phụ lục cuối chương cho thấy khung phân tích này mở rộng được cho trường hợp không có ngày kết thúc định trước. Giả định luân phiên đề nghị và có ngày kết thúc chỉ là công cụ giúp nhìn trước; chúng trở nên vô hại khi khoảng cách giữa các đề nghị ngắn và thời gian mặc cả dài. Khi đó suy luận ngược dẫn tới một quy tắc đơn giản: **chia đôi tổng giá trị**.

Dự đoán thứ hai của lý thuyết là thoả thuận đạt ngay ngày đầu. Vì hai bên cùng nhìn trước và thấy cùng một kết quả, không có lý do gì để không thoả thuận rồi cùng mất 1.000 USD mỗi ngày. Nhưng không phải cuộc mặc cả nào cũng khởi đầu tốt đẹp như vậy: đàm phán đổ vỡ, đình công hay đóng cửa không cho công nhân làm (lockout) xảy ra, và thoả thuận lệch về một bên. Hai tác giả sửa dần các giả định để giải thích những điều này.

### 2. Hệ thống điểm chấp trong đàm phán (The Handicap System in Negotiations)

Yếu tố quan trọng quyết định cách chia bánh là chi phí chờ đợi của mỗi bên. Hai bên có thể mất lượng lãi như nhau, nhưng một bên có thể có phương án khác giúp lấy lại một phần.

**Trường hợp công đoàn có thu nhập bên ngoài.** Giả sử trong lúc mặc cả, đoàn viên kiếm được 300 USD mỗi ngày ở nơi khác. Khi đó mỗi lượt của mình, ban quản lý phải đề nghị công đoàn không chỉ phần công đoàn sẽ có vào ngày hôm sau mà còn ít nhất 300 USD cho hôm nay. Bảng dịch chuyển có lợi cho công đoàn:

**Các vòng mặc cả lương liên tiếp, khi đoàn viên có thu nhập bên ngoài 300 USD/ngày (Bảng dựng lại từ sách)**

| Số ngày còn lại | Bên đề nghị | Công đoàn: tổng | Công đoàn: mỗi ngày | Ban quản lý: tổng | Ban quản lý: mỗi ngày |
|---|---|---|---|---|---|
| 1 | Công đoàn | 1.000 USD | 1.000 USD | 0 USD | 0 USD |
| 2 | Ban quản lý | 1.300 USD | 650 USD | 700 USD | 350 USD |
| 3 | Công đoàn | 2.300 USD | 767 USD | 700 USD | 233 USD |
| 4 | Ban quản lý | 2.600 USD | 650 USD | 1.400 USD | 350 USD |
| 5 | Công đoàn | 3.600 USD | 720 USD | 1.400 USD | 280 USD |
| ... | ... | ... | ... | ... | ... |
| 100 | Ban quản lý | 65.000 USD | 650 USD | 35.000 USD | 350 USD |
| 101 | Công đoàn | 66.000 USD | 653 USD | 35.000 USD | 347 USD |

Thoả thuận vẫn đạt ngay đầu mùa, không có đình công, nhưng công đoàn được nhiều hơn hẳn. Hai tác giả giải thích kết quả này như một điều chỉnh tự nhiên của nguyên tắc chia đôi, khi hai bên xuất phát với "điểm chấp" khác nhau như trong golf. Công đoàn xuất phát với 300 USD, số tiền đoàn viên kiếm được bên ngoài; còn lại 700 USD để mặc cả, chia đôi mỗi bên 350 USD; công đoàn được 650 USD, ban quản lý chỉ 350 USD.

**Trường hợp ban quản lý có lao động thay thế.** Trong hoàn cảnh khác, ban quản lý có thể có lợi thế, chẳng hạn vận hành khách sạn bằng lao động thay thế người đình công trong lúc mặc cả. Vì những lao động này kém hiệu quả hơn hoặc phải trả lương cao hơn, hoặc vì một số khách ngại đi qua hàng người biểu tình của công đoàn, lãi khi đó chỉ 500 USD mỗi ngày. Nếu đoàn viên không có thu nhập bên ngoài, hai bên vẫn thoả thuận ngay mà không có đình công thật, nhưng khả năng dùng lao động thay thế cho ban quản lý lợi thế: ban quản lý được 750 USD mỗi ngày, công đoàn 250 USD.

**Khi cả hai bên có phương án bên ngoài.** Nếu đoàn viên kiếm được 300 USD bên ngoài và ban quản lý lãi 500 USD khi dùng lao động thay thế, chỉ còn 200 USD để mặc cả. Chia đôi số đó, ban quản lý được 600 USD, công đoàn 400 USD.

| Tình huống | BATNA công đoàn | BATNA ban quản lý | Phần còn để chia | Công đoàn được | Ban quản lý được |
|---|---|---|---|---|---|
| Không bên nào có phương án ngoài | 0 USD | 0 USD | 1.000 USD | khoảng 500 USD | khoảng 500 USD |
| Đoàn viên có việc ngoài | 300 USD | 0 USD | 700 USD | 650 USD | 350 USD |
| Ban quản lý dùng lao động thay thế | 0 USD | 500 USD | 500 USD | 250 USD | 750 USD |
| Cả hai | 300 USD | 500 USD | 200 USD | 400 USD | 600 USD |

Ý chung: bên nào tự mình làm được càng tốt khi không có thoả thuận thì phần bánh của bên đó càng lớn.

### 3. Đo chiếc bánh (Measuring the Pie)

Bước đầu tiên trong mọi cuộc đàm phán là đo đúng chiếc bánh. Trong trường hợp cuối ở trên, hai bên không thật sự mặc cả 1.000 USD. Nếu thoả thuận, họ chia nhau 1.000 USD mỗi ngày; nếu không, công đoàn có 300 USD và ban quản lý có 500 USD. Vậy thoả thuận chỉ mang lại thêm 200 USD, và cách đúng là coi chiếc bánh có kích thước 200 USD. Tổng quát: kích thước chiếc bánh đo bằng lượng giá trị được tạo ra khi hai bên thoả thuận so với khi không thoả thuận.

Trong ngôn ngữ đàm phán, các con số dự phòng 300 USD của công đoàn và 500 USD của ban quản lý gọi là BATNA, thuật ngữ do Roger Fisher và William Ury đặt ra, viết tắt của *Best Alternative to a Negotiated Agreement* (phương án thay thế tốt nhất khi không đạt thoả thuận; hai tác giả nói thêm rằng cũng có thể hiểu là *Best Alternative to No Agreement*). Đó là điều tốt nhất bạn có được nếu không thoả thuận được với bên này. Vì ai cũng có BATNA của mình mà không cần đàm phán, toàn bộ ý nghĩa của đàm phán là tạo thêm được bao nhiêu giá trị vượt trên tổng các BATNA. Hai tác giả gọi ý này là vừa sâu sắc vừa đơn giản một cách đánh lừa, và đưa ra một ví dụ phỏng theo một vụ thật để cho thấy người ta dễ quên BATNA thế nào.

**Ví dụ vé máy bay của luật sư.** Hai công ty, một ở Houston và một ở San Francisco, cùng thuê một luật sư ở New York. Nhờ phối hợp lịch, luật sư bay một vòng tam giác New York–Houston–San Francisco–New York thay vì hai chuyến riêng. Vì không kịp đặt vé sớm, vé khứ hồi đúng bằng hai lần vé một chiều.

**Giá vé một chiều (Bảng dựng lại từ sách)**

| Chặng | Giá vé |
|---|---|
| New York–Houston | 666 USD |
| Houston–San Francisco | 909 USD |
| San Francisco–New York | 1.243 USD |
| Tổng chuyến tam giác | 2.818 USD |

Hai công ty nên chia tiền vé thế nào? Hai tác giả thừa nhận số tiền nhỏ, nhưng điều họ tìm là nguyên tắc. Các cách chia người ta hay nghĩ ra:

| Cách chia | Houston trả | San Francisco trả | Nhận xét |
|---|---|---|---|
| Chia đôi tổng tiền | 1.409 USD | 1.409 USD | Houston từ chối: tự đi khứ hồi chỉ tốn 2 × 666 = 1.332 USD |
| Mỗi bên trả chặng nối với New York của mình, chia đôi chặng Houston–San Francisco | 1.120,50 USD | 1.697,50 USD | Hai tác giả xếp vào loại cách chia "tùy hứng" (ad hoc); theo người tổng hợp, cách này chia theo hành trình chứ không theo giá trị thoả thuận tạo ra |
| Chia theo tỷ lệ giá vé khứ hồi (San Francisco trả khoảng gấp đôi Houston) | 983 USD | 1.835 USD | Cũng là cách chia "tùy hứng" |
| Chia đôi khoản tiết kiệm so với BATNA (cách của hai tác giả) | 832 USD | 1.986 USD | Cách hai tác giả cho là công bằng nhất |

> **Chú thích của tác giả** (ở cách chia đôi): nếu bạn nghĩ luật sư có thể tính cho khách Houston 1.332 USD và khách San Francisco 2.486 USD theo giá vé khứ hồi rồi bỏ túi phần chênh lệch, có lẽ bạn đã có thể làm sự nghiệp ở Enron. Tiếc là đã quá muộn.
Hai tác giả gọi ba cách đầu là cách chia "tùy hứng" (ad hoc), có cách hợp lý hơn cách khác. Cách họ ưa là bắt đầu từ BATNA để đo chiếc bánh. Nếu hai công ty không thoả thuận được, luật sư sẽ đi hai chuyến riêng: Houston tốn 1.332 USD, San Francisco tốn 2.486 USD, tổng 3.818 USD. Chuyến tam giác chỉ tốn 2.818 USD. Điểm then chốt: chi phí thêm của hai chuyến khứ hồi so với chuyến tam giác là 1.000 USD, và đó là chiếc bánh. Thoả thuận tạo ra khoản tiết kiệm 1.000 USD vốn sẽ mất nếu không thoả thuận, và mỗi công ty cần thiết như nhau để có khoản đó. Nếu hai bên kiên nhẫn như nhau trong đàm phán, họ nên chia đôi: mỗi bên tiết kiệm 500 USD so với giá vé khứ hồi, tức Houston trả 832 USD và San Francisco trả 1.986 USD.

Con số của Houston thấp hơn hẳn mọi cách khác. Điều đó cho thấy cách chia giữa hai bên không nên dựa trên số dặm bay hay giá vé tương đối: vé đi Houston rẻ hơn không có nghĩa Houston được hưởng ít phần tiết kiệm hơn, vì nếu Houston không đồng ý, toàn bộ 1.000 USD sẽ mất. Hai tác giả hy vọng người đọc ban đầu nghĩ tới một trong các cách khác, rồi sau khi áp dụng BATNA để đo đúng chiếc bánh thì bị thuyết phục rằng cách mới là công bằng nhất; ai nghĩ ra ngay 832 USD và 1.986 USD thì đáng được ngả mũ. Cách chia chi phí này có thể truy về nguyên tắc "chia tấm vải" trong sách Talmud của Do Thái giáo.

Trong các ví dụ trên, BATNA là cố định: công đoàn có 300 USD, ban quản lý 500 USD, giá vé khứ hồi do bên ngoài quyết định. Ở những trường hợp khác, BATNA không cố định, và điều này mở ra chiến lược tác động lên BATNA. Nói chung bạn muốn nâng BATNA của mình và hạ BATNA của bên kia; đôi khi hai mục tiêu này mâu thuẫn nhau.

### 4. Việc này làm anh đau hơn tôi (This Will Hurt You More Than It Hurts Me)

Người mặc cả có tư duy chiến lược, khi thấy phương án bên ngoài tốt hơn mang lại phần chia tốt hơn, sẽ tìm các nước đi chiến lược để cải thiện phương án bên ngoài. Hơn nữa, anh ta sẽ nhận ra điều quan trọng là phương án bên ngoài của mình *so với* của đối thủ. Anh ta sẽ được lợi kể cả khi đưa ra một cam kết hay đe doạ làm giảm phương án bên ngoài của cả hai bên, miễn là phương án của đối thủ bị tổn hại nặng hơn.

Trở lại khách sạn: khi đoàn viên kiếm được 300 USD bên ngoài và ban quản lý lãi 500 USD với lao động thay thế, kết quả là công đoàn 400 USD, ban quản lý 600 USD. Giả sử đoàn viên bỏ 100 USD thu nhập ngoài mỗi ngày để tăng cường biểu tình chặn cửa, làm lãi của ban quản lý giảm 200 USD mỗi ngày. Điểm xuất phát mới của công đoàn là 200 USD (300 trừ 100), của ban quản lý là 300 USD (500 trừ 200). Tổng hai điểm xuất phát là 500 USD; 500 USD lãi còn lại của khách sạn được chia đôi. Công đoàn được 450 USD, ban quản lý 550 USD. Đe doạ làm cả hai bên đau, nhưng làm ban quản lý đau hơn, đã mang về cho công đoàn thêm 50 USD.

| | BATNA công đoàn | BATNA ban quản lý | Phần chia đôi | Công đoàn được | Ban quản lý được |
|---|---|---|---|---|---|
| Trước khi tăng cường biểu tình | 300 USD | 500 USD | 200 USD | 400 USD | 600 USD |
| Sau khi tăng cường biểu tình | 200 USD | 300 USD | 500 USD | 450 USD | 550 USD |

Các cầu thủ bóng chày nhà nghề Mỹ (Major League Baseball) đã dùng đúng chiến thuật này trong đàm phán lương năm 1980. Họ đình công trong mùa thi đấu giao hữu, quay lại thi đấu khi mùa chính thức bắt đầu, và đe doạ đình công tiếp từ dịp nghỉ lễ Chiến sĩ trận vong (Memorial Day, cuối tháng 5). Lý do chiến thuật này "làm chủ đội đau hơn": trong mùa giao hữu, cầu thủ không có lương nhưng chủ đội vẫn có doanh thu từ khách du lịch và dân địa phương; trong mùa chính thức, cầu thủ nhận lương như nhau mỗi tuần, còn doanh thu vé và truyền hình của chủ đội thấp lúc đầu rồi tăng mạnh trong và sau dịp Memorial Day. Vì vậy thiệt hại của chủ đội so với cầu thủ lớn nhất trong mùa giao hữu và từ Memorial Day trở đi, đúng hai giai đoạn cầu thủ chọn. Chủ đội nhượng bộ ngay trước nửa sau của cuộc đình công bị đe doạ. Nhưng nửa đầu đã thật sự xảy ra, nên lý thuyết suy luận ngược rõ ràng chưa đầy đủ: vì sao không phải lúc nào cũng thoả thuận được trước khi thiệt hại xảy ra, vì sao có đình công?

### 5. Chiến lược bên bờ vực và đình công (Brinkmanship and Strikes)

Trước khi hợp đồng cũ hết hạn, công đoàn và doanh nghiệp bắt đầu đàm phán hợp đồng mới, nhưng không có gì cấp bách: công việc vẫn chạy, không mất sản lượng, chẳng có lợi gì rõ ràng khi thoả thuận sớm. Tưởng như mỗi bên nên chờ tới phút cuối, khi hợp đồng cũ sắp hết và đình công cận kề, mới đưa yêu cầu. Điều đó đôi khi xảy ra, nhưng thường thoả thuận đạt sớm hơn nhiều.

Lý do là trì hoãn thoả thuận có thể tốn kém ngay trong giai đoạn yên bình: bản thân quá trình đàm phán có rủi ro. Có thể hiểu sai mức kiên nhẫn hay phương án bên ngoài của bên kia; có căng thẳng, va chạm cá nhân, nghi ngờ bên kia không mặc cả thiện chí. Đàm phán có thể đổ vỡ dù cả hai bên muốn nó thành công.

Hai bên có thể cùng muốn thành công nhưng hiểu "thành công" khác nhau. Họ không phải lúc nào cũng nhìn trước thấy cùng một điểm kết thúc, vì không có cùng thông tin hay cùng góc nhìn. Mỗi bên phải đoán chi phí chờ của bên kia. Vì bên có chi phí chờ thấp được lợi, ai cũng muốn tuyên bố chi phí của mình thấp; nhưng lời tuyên bố không được tin ngay mà phải được chứng minh. Cách chứng minh là bắt đầu chịu chi phí và cho thấy mình trụ được lâu hơn, hoặc chấp nhận rủi ro chịu chi phí lớn hơn (chi phí thấp thì rủi ro cao mới chấp nhận được). Chính việc thiếu một cái nhìn chung về kết cục của đàm phán là điều khởi đầu một cuộc đình công.

Hai tác giả đề nghị coi đình công là một ví dụ của phát tín hiệu. Ai cũng nói được rằng mình chịu được chi phí đình công (hay chi phí đối phó với đình công), nhưng dám làm thật là bằng chứng tốt nhất: hành động có sức nặng hơn lời nói. Và như mọi tín hiệu, truyền thông tin bằng tín hiệu đòi hỏi một chi phí, tức hy sinh hiệu quả. Cả doanh nghiệp lẫn công nhân đều muốn chứng minh chi phí thấp của mình mà không phải gây ra mọi thiệt hại của việc ngừng sản xuất.

Tình huống này sinh ra để dùng chiến lược bên bờ vực. Công đoàn có thể đe doạ cắt đứt đàm phán ngay và đình công, nhưng đình công cũng tốn kém cho đoàn viên, nên khi còn thời gian đàm phán, đe doạ nặng như vậy không đáng tin. Một đe doạ nhỏ hơn thì vẫn đáng tin: căng thẳng tăng dần và đổ vỡ có thể xảy ra dù công đoàn không thật sự muốn. Nếu điều đó làm ban quản lý lo hơn công đoàn, đây là chiến lược tốt cho công đoàn. Lập luận đúng cả theo chiều ngược lại: chiến lược bên bờ vực là vũ khí của bên mạnh hơn, tức bên ít sợ đổ vỡ hơn.

Đôi khi đàm phán tiếp tục sau khi hợp đồng cũ hết hạn mà không có đình công, công việc chạy theo điều khoản cũ. Có vẻ đây là cách tốt hơn, vì máy móc và công nhân không nhàn rỗi, sản lượng không mất. Nhưng một bên, thường là công đoàn, đang đòi sửa điều khoản có lợi cho mình, và với bên đó cách này đặc biệt bất lợi. (Chú thích của tác giả: một cách giải thích là công nhân đang chờ thời điểm thích hợp để đình công; nhân viên UPS đình công ngay trước Giáng sinh sẽ gây thiệt hại lớn hơn nhiều so với đình công giữa những ngày hè oi ả tháng 8.) Ban quản lý việc gì phải nhượng bộ, sao không để đàm phán kéo dài mãi trong khi hợp đồng cũ trên thực tế vẫn có hiệu lực? Mối đe doạ ở đây lại là xác suất quá trình đổ vỡ và đình công nổ ra. Công đoàn dùng chiến lược bên bờ vực, nhưng lần này sau khi hợp đồng cũ đã hết hạn và thời gian đàm phán thường lệ đã qua. Tiếp tục làm việc theo hợp đồng hết hạn trong khi đàm phán bị coi rộng rãi là dấu hiệu công đoàn yếu; phải có một xác suất đình công nào đó thì doanh nghiệp mới chịu đáp ứng yêu cầu.

Khi đình công đã nổ ra, điều gì giữ nó kéo dài? Chìa khoá của cam kết là thu nhỏ đe doạ để nó đáng tin. Chiến lược bên bờ vực giữ cuộc đình công theo từng ngày. Đe doạ không bao giờ quay lại làm việc không đáng tin, nhất là khi ban quản lý đã gần đáp ứng yêu cầu; nhưng chờ thêm một ngày hay một tuần là đe doạ đáng tin, vì thiệt hại của công nhân nhỏ hơn lợi ích tiềm năng. Miễn là họ tin mình sẽ thắng (và sớm), chờ là đáng. Nếu công nhân tin đúng, ban quản lý nên thấy nhượng bộ rẻ hơn và nhượng bộ ngay, nên đe doạ của công nhân thực ra không tốn gì. Vấn đề là doanh nghiệp có thể không nhìn tình hình như vậy: nếu họ tin công nhân sắp chịu thua, thì mất thêm một ngày hay một tuần lãi là đáng để có hợp đồng có lợi hơn. Thế là cả hai bên cùng cầm cự và đình công tiếp diễn.

Ở Chương 6, hai tác giả mô tả rủi ro của chiến lược bên bờ vực là khả năng cả hai bên cùng trượt xuống dốc trơn. Khi xung đột kéo dài, hai bên đối mặt một thiệt hại lớn với xác suất nhỏ nhưng tăng dần, và chính mức phơi nhiễm rủi ro tăng dần buộc một bên lùi bước. Chiến lược bên bờ vực dưới dạng đình công gây chi phí theo cách khác nhưng hiệu quả giống nhau: thay vì xác suất nhỏ của một thiệt hại lớn, đình công là xác suất lớn, thậm chí chắc chắn, của một thiệt hại nhỏ; khi đình công kéo dài, thiệt hại nhỏ đó lớn dần, giống như xác suất rơi xuống vực tăng dần. Cách chứng minh quyết tâm là chấp nhận thêm rủi ro hoặc nhìn thiệt hại đình công leo thang. Chỉ khi một bên phát hiện bên kia thật sự mạnh hơn, bên đó mới lùi. Sức mạnh có nhiều dạng: một bên có thể ít thiệt khi chờ, có lẽ vì có phương án thay thế giá trị; có thể thắng rất quan trọng với họ, có lẽ vì họ còn đàm phán với các công đoàn khác; hoặc thua rất đắt, khiến thiệt hại đình công trông nhỏ đi.

Chiến lược bên bờ vực áp dụng cả cho mặc cả giữa các quốc gia, không chỉ giữa các doanh nghiệp. Khi Mỹ muốn đồng minh gánh phần lớn hơn chi phí quốc phòng, Mỹ chịu cái yếu của bên đàm phán trong khi vẫn làm việc theo hợp đồng đã hết hạn: thoả thuận cũ, trong đó Mỹ gánh phần lớn gánh nặng, vẫn tiếp tục, và đồng minh vui lòng để đàm phán kéo dài. Hai tác giả để ngỏ câu hỏi: Mỹ có thể, và có nên, dùng chiến lược bên bờ vực không?

Rủi ro và chiến lược bên bờ vực thay đổi quá trình mặc cả một cách căn bản. Trong các phân tích chuỗi đề nghị trước đó, triển vọng của những vòng sau khiến hai bên thoả thuận ngay vòng đầu. Một phần không tách rời của chiến lược bên bờ vực là đôi khi hai bên rơi xuống thật. Đổ vỡ và đình công có thể xảy ra; cả hai bên có thể thật lòng hối tiếc, nhưng chúng có thể tự có đà và kéo dài lâu đến bất ngờ.

### 6. Mặc cả đồng thời nhiều vấn đề (Simultaneous Bargaining over Many Issues)

Tới đây chương chỉ xét một chiều: tổng số tiền và cách chia giữa hai bên. Thực tế mặc cả có nhiều chiều: công đoàn và ban quản lý quan tâm không chỉ lương mà cả bảo hiểm y tế, lương hưu, điều kiện làm việc; Mỹ và các đối tác thương mại quan tâm không chỉ tổng lượng phát thải CO2 mà cả cách phân bổ. Về nguyên tắc nhiều hạng mục quy đổi được ra tiền, nhưng với một khác biệt quan trọng: mỗi bên có thể định giá chúng khác nhau.

Khác biệt đó mở ra những thoả thuận mà cả hai bên chấp nhận được. Giả sử công ty mua được bảo hiểm y tế nhóm với giá tốt hơn công nhân tự mua: 1.000 USD mỗi năm thay vì 2.000 USD cho một gia đình bốn người. Công nhân thích có bảo hiểm hơn là thêm 1.500 USD lương mỗi năm, và công ty cũng thích cung cấp bảo hiểm hơn là trả thêm 1.500 USD lương. Có vẻ người đàm phán nên đưa mọi vấn đề cùng quan tâm vào một "nồi" mặc cả chung và khai thác khác biệt trong cách định giá để đạt kết quả tốt hơn cho mọi người. Cách này có hiệu quả trong một số trường hợp: các vòng đàm phán rộng về tự do hoá thương mại trong Hiệp định chung về Thuế quan và Thương mại (GATT) và tổ chức kế nhiệm là Tổ chức Thương mại Thế giới (WTO) đã thành công hơn các cuộc đàm phán hẹp theo từng ngành hay mặt hàng.

Nhưng gộp vấn đề cũng mở ra khả năng dùng một trò chơi mặc cả để tạo đe doạ trong trò chơi khác. Chẳng hạn Mỹ có thể đòi được nhiều nhượng bộ hơn trong đàm phán mở cửa thị trường Nhật cho hàng xuất khẩu của mình nếu đe doạ phá vỡ quan hệ quân sự, khiến Nhật đối mặt rủi ro bị Triều Tiên hoặc Trung Quốc gây hấn. Mỹ không hề muốn điều đó xảy ra; đó chỉ là đe doạ để Nhật nhượng bộ về kinh tế. Chính vì vậy, Nhật sẽ đòi đàm phán vấn đề kinh tế và vấn đề quân sự tách riêng.

### 7. Ưu điểm của đình công ảo (The Virtues of a Virtual Strike)

Phân tích tới đây bỏ qua tác động lên những người không tham gia thoả thuận. Khi công nhân UPS đình công, khách hàng không nhận được bưu kiện; khi nhân viên hành lý Air France đình công, các kỳ nghỉ bị phá hỏng. Đình công làm hại nhiều người hơn hai bên đàm phán. Việc không đạt thoả thuận về ấm lên toàn cầu và phát thải CO2 có thể gây tai hoạ cho mọi thế hệ tương lai, những người không có ghế ở bàn đàm phán.

Nhưng các bên đàm phán phải sẵn sàng bỏ đi để chứng tỏ sức mạnh BATNA của mình hoặc để làm bên kia đau hơn. Ngay cả với một cuộc đình công bình thường, thiệt hại phụ có thể dễ dàng vượt xa quy mô tranh chấp. Cuộc đóng cửa không cho công nhân bốc xếp làm việc kéo dài mười ngày ở các cảng, cho tới khi Tổng thống Bush can thiệp ngày 3/10/2002 bằng cách viện dẫn Luật Taft-Hartley, đã gây thiệt hại cho kinh tế Mỹ hơn 10 tỷ USD. Tranh chấp xoay quanh 20 triệu USD cải thiện năng suất. Thiệt hại phụ lớn gấp 500 lần số tiền công nhân và ban quản lý cãi nhau.

| | Số tiền |
|---|---|
| Khoản tranh chấp (cải thiện năng suất) | 20 triệu USD |
| Thiệt hại cho kinh tế Mỹ sau 10 ngày đóng cửa cảng | Hơn 10 tỷ USD |
| Tỷ lệ | Khoảng 500 lần |

Có cách nào để hai bên giải quyết bất đồng mà không gây chi phí lớn như vậy cho phần còn lại của xã hội? Đã hơn 50 năm nay có một ý tưởng khéo léo để loại bỏ gần như toàn bộ lãng phí của đình công và đóng cửa mà không làm thay đổi sức mạnh mặc cả tương đối của công nhân và chủ: thay đình công truyền thống bằng đình công ảo (hay đóng cửa ảo). Công nhân vẫn làm việc bình thường, doanh nghiệp vẫn sản xuất bình thường; mấu chốt là trong thời gian đình công ảo, không bên nào được trả tiền.

Trong đình công thật, công nhân mất lương và chủ mất lợi nhuận. Vậy trong đình công ảo, công nhân làm không lương và chủ bỏ ra toàn bộ lợi nhuận. Vì lợi nhuận có thể khó đo và lợi nhuận ngắn hạn có thể đánh giá thấp chi phí thật của doanh nghiệp, hai tác giả đề nghị doanh nghiệp bỏ ra toàn bộ doanh thu. Số tiền đó có thể chuyển cho nhà nước ("chú Sam") hay một tổ chức từ thiện, hoặc sản phẩm được phát miễn phí để doanh thu thực chất về tay khách hàng. Trong đình công ảo, phần còn lại của nền kinh tế không bị gián đoạn, khách hàng không bị bỏ rơi. Ban quản lý và công nhân chịu đau nên có động lực thoả thuận, còn nhà nước, tổ chức từ thiện hay khách hàng được hưởng một khoản bất ngờ.

Đình công thật (hay việc ban quản lý chủ động đóng cửa để đi trước một cuộc đình công) có thể huỷ hoại vĩnh viễn nhu cầu của khách hàng và đe doạ tương lai của cả doanh nghiệp. Giải khúc côn cầu nhà nghề Bắc Mỹ (NHL) đóng cửa không cho cầu thủ thi đấu để đối phó với đe doạ đình công trong mùa 2004–05: cả mùa giải bị huỷ, không có Cúp Stanley, và phải rất lâu sau khi tranh chấp được giải quyết lượng khán giả mới hồi phục.

Đình công ảo không chỉ là ý tưởng viển vông chờ thử nghiệm:

| Thời gian | Nơi | Diễn biến |
|---|---|---|
| Thế chiến II | Nhà máy van của Jenkins Company, Bridgeport, Connecticut | Hải quân Mỹ dùng đình công ảo để giải quyết tranh chấp lao động |
| 1960 | Đình công xe buýt ở Miami | Áp dụng đình công ảo; hành khách được đi xe miễn phí theo đúng nghĩa đen |
| 1999 | Hãng hàng không Meridiana, Ý | Cuộc đình công ảo đầu tiên ở Ý: phi công và tiếp viên làm không lương, hãng tặng doanh thu chuyến bay cho từ thiện; các chuyến bay không bị gián đoạn. Các cuộc đình công giao thông khác ở Ý làm theo |
| 2000 | Công đoàn Vận tải Ý | 300 phi công đình công ảo, công đoàn nộp 100 triệu lire; tiền dùng mua một thiết bị y tế đắt tiền cho một bệnh viện nhi, tạo cơ hội quảng bá hình ảnh |

Thay vì huỷ hoại nhu cầu như vụ đóng cửa NHL, khoản tiền bất ngờ từ đình công ảo tạo cơ hội nâng uy tín thương hiệu. Có phần trớ trêu là chính lợi ích quan hệ công chúng này có thể làm đình công ảo khó áp dụng hơn. Đình công thật thường được thiết kế để gây phiền cho khách hàng, khiến họ ép ban quản lý thoả thuận; vì vậy yêu cầu chủ chỉ nộp lợi nhuận có thể không tái tạo đủ chi phí thật của một cuộc đình công truyền thống. Đáng chú ý là trong cả bốn ví dụ lịch sử, ban quản lý đều đồng ý nộp nhiều hơn lợi nhuận, tức toàn bộ doanh thu gộp của mọi giao dịch trong thời gian đình công.

Vì sao công nhân lại đồng ý làm không lương? Cùng lý do họ sẵn sàng đình công: để gây đau cho ban quản lý và chứng minh chi phí chờ của mình thấp. Thậm chí trong đình công ảo, có thể thấy công nhân làm chăm hơn, vì mỗi giao dịch thêm là thêm nỗi đau cho doanh nghiệp, bên phải nộp toàn bộ doanh thu của giao dịch đó.

Mục đích của hai tác giả là tái tạo chi phí và lợi ích của đàm phán cho các bên trong cuộc, đồng thời để mọi người khác không bị hại. Miễn là hai bên có BATNA trong đình công ảo bằng trong đình công thật, không bên nào có lợi khi chọn đình công thật. Thời điểm đúng để chuyển sang đình công ảo là khi hai bên còn đang nói chuyện: thay vì chờ tới khi đình công thật, công nhân và ban quản lý có thể thoả thuận trước rằng sẽ dùng đình công ảo nếu lần đàm phán hợp đồng tới thất bại. Lợi ích tiềm năng từ việc loại bỏ toàn bộ phi hiệu quả của đình công và đóng cửa truyền thống đáng để thử nghiệm cách quản lý xung đột lao động mới này.

### 8. Tình huống: cho thì có phúc hơn nhận? (Case Study: 'Tis Better to Give Than to Receive?)

Tên tình huống chơi chữ câu Kinh Thánh "cho thì có phúc hơn nhận". Trở lại khách sạn, nhưng lần này chỉ ban quản lý được đưa đề nghị, công nhân chỉ được chấp nhận hoặc từ chối. Mùa vẫn 101 ngày, lãi 1.000 USD mỗi ngày mở cửa, mặc cả bắt đầu từ đầu mùa. Mỗi ngày ban quản lý đưa một đề nghị; nếu được chấp nhận, khách sạn mở cửa và phần lãi còn lại được chia theo thoả thuận; nếu bị từ chối, mặc cả tiếp tục cho tới khi có đề nghị được chấp nhận hoặc hết mùa và mất toàn bộ lãi. Câu hỏi: nếu mỗi bên chỉ quan tâm tối đa hoá phần của mình, điều gì xảy ra và khi nào? Nếu là công nhân, bạn làm gì để cải thiện vị thế?

Phần thảo luận của sách: kết quả sẽ khác xa 50:50. Vì chỉ ban quản lý được đề nghị, họ ở thế mặc cả mạnh hơn và có thể lấy gần hết, với thoả thuận ngay ngày đầu. Suy luận ngược: ngày cuối, tiếp tục chẳng được gì, nên công nhân nhận bất kỳ khoản dương nào, chẳng hạn 1 USD. Ngày áp chót, công nhân biết từ chối thì mai chỉ được 1 USD, nên thà nhận 2 USD hôm nay. Lập luận tiếp tục tới ngày đầu mùa: ban quản lý đề nghị công nhân 101 USD, và công nhân, không thấy tương lai có gì tốt hơn, chấp nhận. Trong việc đưa đề nghị, "cho" có lợi hơn "nhận".

**Mặc cả lương khi chỉ ban quản lý được đưa đề nghị (Bảng dựng lại từ sách; trong đề bài cột cuối để dấu hỏi, phần thảo luận điền số)**

| Số ngày còn lại | Bên đề nghị | Tổng lãi còn để chia | Khoản đề nghị cho công nhân |
|---|---|---|---|
| 1 | Ban quản lý | 1.000 USD | 1 USD |
| 2 | Ban quản lý | 2.000 USD | 2 USD |
| 3 | Ban quản lý | 3.000 USD | 3 USD |
| 4 | Ban quản lý | 4.000 USD | 4 USD |
| 5 | Ban quản lý | 5.000 USD | 5 USD |
| ... | ... | ... | ... |
| 100 | Ban quản lý | 100.000 USD | 100 USD |
| 101 | Ban quản lý | 101.000 USD | 101 USD |

Phân tích này rõ ràng phóng đại sức mạnh thật của ban quản lý. Hoãn thoả thuận dù chỉ một ngày làm ban quản lý mất 999 USD và công nhân chỉ mất 1 USD. Nếu công nhân quan tâm không chỉ tiền mình nhận mà cả việc so sánh với phần của ban quản lý, cách chia lệch cực đoan như vậy không thể xảy ra. Nhưng không có nghĩa phải quay về chia đôi: ban quản lý vẫn mạnh hơn. Mục tiêu của họ là tìm khoản tối thiểu công nhân chấp nhận, khoản mà công nhân thích hơn là không có gì, dù ban quản lý được nhiều hơn. Chẳng hạn, ở ngày cuối, công nhân có thể chấp nhận 200 USD so với 800 USD của ban quản lý nếu phương án thay thế là không có gì. Khi đó ban quản lý duy trì tỷ lệ 4:1 suốt 101 ngày và giữ 80% tổng lãi.

Giá trị của kỹ thuật này là nó chỉ ra nhiều nguồn sức mạnh mặc cả khác nhau. Chia đôi hay chia đều là lời giải phổ biến nhưng không phổ quát; suy luận ngược cho biết vì sao có thể gặp cách chia không đều. Nhưng cũng có lý do để nghi ngờ kết luận của suy luận ngược: nếu bạn thử mà nó không hiệu quả thì sao?

Khả năng bên kia chứng minh phân tích của bạn sai khiến phiên bản lặp lại khác phiên bản một lần. Trong trò chơi chia 100 USD một lần, bạn có thể giả định bên nhận thấy 20 USD đủ có lợi để chấp nhận, để bạn giữ 80 USD; nếu giả định sai thì trò chơi đã kết thúc, quá muộn để đổi chiến lược, nên bên kia không có cơ hội dạy bạn một bài học nhằm thay đổi chiến lược tương lai của bạn. Ngược lại, khi chơi trò chơi tối hậu thư 101 lần, bên nhận đề nghị có thể có động cơ chơi cứng lúc đầu để tạo ấn tượng rằng mình có lẽ phi lý, hoặc ít nhất tin chắc vào chuẩn mực chia 50:50. (Chú thích của tác giả: khi đưa ra khả năng này, hai tác giả đã ngầm đổi trò chơi bằng cách thêm sự bất định về sở thích của người chơi kia. Nhiều khả năng người đó sẽ nhận bất kỳ đề nghị nào tối đa hoá phần của mình, nhưng nay có một xác suất nhỏ rằng họ chỉ chấp nhận chia 50:50, một dạng chuẩn mực công bằng. Dù khả năng đó thấp, nhiều người chơi chỉ lo tối đa hoá cũng muốn thuyết phục bạn rằng họ thuộc loại "50:50" để được chia nhiều hơn.)

Nếu bạn đề nghị chia 80:20 ngày đầu và bên kia từ chối thì sao? Dễ trả lời nhất khi tổng cộng chỉ có hai ngày, tức vòng sau là vòng cuối. Bạn có nghĩ người đó thật sự thuộc loại từ chối mọi thứ trừ 50:50, hay đó chỉ là mẹo để bạn chia 50:50 ở vòng cuối?

| Đề nghị ngày 1 bị từ chối | Bên kia được nếu chấp nhận cả hai ngày | Bên kia được nếu từ chối rồi được chia đôi ngày 2 | Cách hiểu |
|---|---|---|---|
| 80:20 | 200 + 200 = 400 | 500 | Ngay cả một cỗ máy tính toán lạnh lùng cũng từ chối nếu nghĩ làm vậy sẽ được chia đôi ở vòng cuối. Có thể chỉ là lừa: bạn có thể giữ 80:20 ở vòng cuối và tin rằng nó sẽ được chấp nhận |
| 67:33 | 333 + 333 = 666 | 500 | Kể cả được như ý, họ vẫn thiệt hơn so với chấp nhận. Đây là bằng chứng họ không lừa; lúc này đề nghị 50:50 ở vòng cuối có thể hợp lý |

Tóm lại, điều làm trò chơi nhiều vòng khác trò chơi một lần, kể cả khi chỉ một bên đưa đề nghị, là bên nhận có cơ hội cho bạn thấy lý thuyết của bạn không vận hành như dự đoán. Khi đó bạn giữ lý thuyết hay đổi chiến lược? Nghịch lý là bên kia thường được lợi khi tỏ ra phi lý, nên bạn không thể tin ngay sự phi lý đó. Nhưng họ có thể tự gây thiệt hại lớn tới mức (và gây thiệt cho bạn trên đường đi) mà việc lừa không còn giúp được họ; trong trường hợp đó, bạn rất nên đánh giá lại mục tiêu của bên kia.

### 9. Phụ lục: mô hình mặc cả Rubinstein (Appendix: Rubinstein Bargaining)

Có thể tưởng không giải được bài toán mặc cả khi trò chơi không có ngày kết thúc. Nhưng nhờ một cách tiếp cận tài tình của Ariel Rubinstein, vẫn tìm được lời giải. Trong trò chơi của Rubinstein, hai bên luân phiên đưa đề nghị về cách chia chiếc bánh, để đơn giản có kích thước 1. Một đề nghị có dạng (X, 1 − X): nếu X = 3/4 thì 3/4 cho tôi, 1/4 cho anh. Trò chơi kết thúc ngay khi một bên chấp nhận đề nghị của bên kia; trước đó các đề nghị qua lại luân phiên. Từ chối là tốn kém vì làm chậm thoả thuận: thoả thuận đạt ngày mai sẽ có giá trị hơn nếu đạt hôm nay, nên thoả thuận ngay là lợi ích chung của hai bên.

**Thời gian là tiền theo nhiều cách.** Đơn giản nhất, một đô la nhận sớm đáng giá hơn một đô la nhận muộn vì có thể đem đầu tư để có lãi hay cổ tức: với lợi suất 10% một năm, 1 USD nhận ngay bằng 1,10 USD nhận sau một năm. Với công đoàn và ban quản lý còn có thêm những yếu tố làm tăng sự sốt ruột. Mỗi tuần thoả thuận bị hoãn, có rủi ro khách quen trung thành gắn bó lâu dài với nhà cung cấp khác, và doanh nghiệp có nguy cơ phải đóng cửa vĩnh viễn; công nhân và quản lý khi đó phải chuyển sang việc lương thấp hơn, uy tín của thủ lĩnh công đoàn bị tổn hại, quyền chọn cổ phiếu của ban quản lý mất giá trị. Mức độ thoả thuận ngay tốt hơn thoả thuận tuần sau chính là xác suất những điều đó xảy ra trong tuần.

Giống trò chơi tối hậu thư, bên đến lượt đưa đề nghị có lợi thế, và độ lớn của lợi thế phụ thuộc mức sốt ruột. Hai tác giả đo sự sốt ruột bằng phần giá trị còn lại nếu thoả thuận ở vòng sau thay vì hôm nay, ký hiệu δ. Nếu mỗi tuần có một đề nghị và 1 USD tuần sau đáng 99 xu hôm nay thì 99% giá trị còn lại, δ = 0,99 (hai tác giả chơi chữ câu tục ngữ "một con chim trong tay hơn hai con trong bụi": 99 xu trong tay bằng 1 USD trong bụi tuần sau). Khi δ gần 1, như 0,99, người ta kiên nhẫn; khi δ nhỏ, chẳng hạn 1/3, chờ đợi tốn kém và người mặc cả sốt ruột; với δ = 1/3, mỗi tuần mất hai phần ba giá trị. Mức sốt ruột thường phụ thuộc khoảng thời gian giữa các vòng: nếu mất một tuần để đưa đề nghị ngược lại thì có thể δ = 0,99; nếu chỉ mất một phút thì δ = 0,999999 và gần như không mất gì.

**Mức thấp nhất bạn chấp nhận.** Khi biết mức sốt ruột, có thể tìm cách chia bằng cách xét mức thấp nhất một người có thể chấp nhận và mức cao nhất người đó có thể được đề nghị. Có thể nào mức thấp nhất bạn chấp nhận là 0? Không. Giả sử bên kia đề nghị bạn 0. Bạn biết nếu từ chối hôm nay và mai tới lượt bạn đề nghị, bạn có thể đề nghị bên kia δ và họ sẽ nhận, vì họ thà có δ ngày mai còn hơn chờ thêm một vòng để được 1 (và 1 chỉ là trường hợp tốt nhất của họ, khi bạn chấp nhận 0 sau hai vòng). Biết chắc họ nhận δ ngày mai, bạn có thể trông vào 1 − δ ngày mai, nên hôm nay không bao giờ nên nhận dưới δ(1 − δ). Vậy cả hôm nay lẫn sau hai vòng, bạn đều không nên nhận 0. (Chú thích của tác giả: trừ khi δ = 0, tức bạn hoàn toàn sốt ruột và tương lai không có giá trị gì.)

Lập luận đó chưa nhất quán hoàn toàn, vì nó tìm mức tối thiểu bạn chấp nhận với giả định bạn sẽ nhận 0 sau hai vòng. Điều cần tìm là một mức tối thiểu đứng vững theo thời gian: một con số mà khi mọi người hiểu đó là mức thấp nhất bạn từng chấp nhận, nó đặt bạn vào vị thế không nên nhận ít hơn. Cách giải vòng lập luận này: gọi L (lowest) là mức chia tệ nhất bạn từng chấp nhận. Giả sử bạn tính từ chối đề nghị hôm nay để đưa đề nghị ngược lại. Bên kia không bao giờ có thể mong hơn 1 − L khi tới lượt họ lần nữa, vì họ biết bạn không nhận dưới L. Vì đó là điều tốt nhất họ có sau hai vòng, ngày mai họ nên nhận δ(1 − L). Vậy hôm nay, khi cân nhắc nhận đề nghị của họ, bạn có thể tin rằng nếu từ chối và ngày mai đề nghị lại δ(1 − L), họ sẽ nhận, để lại cho bạn chắc chắn 1 − δ(1 − L) ngày mai. Do đó hôm nay bạn không bao giờ nên nhận ít hơn δ(1 − δ(1 − L)). Từ đó có điều kiện cho L (công thức dựng lại từ sách):

- L ≥ δ(1 − δ(1 − L)), hay L ≥ δ(1 − δ)/(1 − δ²) = δ/(1 + δ).

Bạn không bao giờ nên nhận dưới δ/(1 + δ), vì chờ và đưa đề nghị ngược lại mà bên kia chắc chắn nhận sẽ cho bạn nhiều hơn. Điều đúng với bạn cũng đúng với bên kia: họ cũng không bao giờ nhận dưới δ/(1 + δ).

**Mức cao nhất bạn có thể mong.** Gọi M (most) là con số lớn tới mức bạn không bao giờ nên từ chối. Vì bên kia không bao giờ nhận dưới δ/(1 + δ) ở vòng sau, trong trường hợp tốt nhất vòng sau bạn được tối đa 1 − δ/(1 + δ) = 1/(1 + δ). Nếu đó là điều tốt nhất bạn làm được vòng sau, thì hôm nay bạn luôn nên nhận δ × 1/(1 + δ) = δ/(1 + δ). Vậy (công thức dựng lại từ sách):

- L ≥ δ/(1 + δ) và M ≤ δ/(1 + δ).

Mức thấp nhất bạn từng chấp nhận là δ/(1 + δ), và bạn luôn chấp nhận mọi mức từ δ/(1 + δ) trở lên. Vì hai mức trùng nhau, đó chính là phần bạn được: bên kia không đề nghị ít hơn vì bạn sẽ từ chối, và không đề nghị nhiều hơn vì bạn chắc chắn nhận δ/(1 + δ). Bên đề nghị giữ 1/(1 + δ).

**Ba trường hợp (công thức dựng lại từ sách).**

| Giá trị δ | Ý nghĩa | Phần bên trả lời δ/(1 + δ) | Phần bên đề nghị | Cách chia |
|---|---|---|---|---|
| δ = 1 | Chờ một lượt gần như không tốn gì (khoảng cách giữa các đề nghị rất ngắn) | 1/2 | 1/2 | 50:50; người đi trước không có lợi thế |
| δ = 1/2 | Thời gian quý giá, mỗi lần hoãn mất nửa chiếc bánh | (1/2)/(1 + 1/2) = 1/3 | 2/3 | 2:1 |
| δ = 0 | Bánh mất hết nếu đề nghị bị từ chối | 0 | 1 | (0, 1), đúng như trò chơi tối hậu thư, kèm mọi lưu ý của trò chơi đó |

Hai tác giả giải thích trường hợp δ = 1/2 bằng lời: người đang đề nghị với tôi có quyền đòi toàn bộ phần bánh sẽ mất nếu tôi từ chối, tức ngay lập tức được 1/2. Trong nửa còn lại, tôi được một nửa, tức 1/4 tổng, vì phần đó sẽ mất nếu anh ta không nhận đề nghị của tôi. Sau hai vòng, anh ta đã thu 1/2, tôi thu 1/4, và ta quay về điểm xuất phát. Vậy trong mỗi cặp đề nghị anh ta thu gấp đôi tôi, dẫn tới cách chia 2:1.

**Khi hai bên kiên nhẫn khác nhau.** Lời giải trên giả định hai bên kiên nhẫn như nhau. Có thể dùng cùng cách để giải khi chi phí chờ khác nhau, và như dự đoán, bên kiên nhẫn hơn được phần lớn hơn. Khi khoảng thời gian giữa các đề nghị ngắn lại, chiếc bánh được chia theo tỷ lệ chi phí chờ của hai bên, theo chiều ngược lại (bên chờ tốn kém hơn được ít hơn): nếu một bên sốt ruột gấp đôi bên kia, bên đó được một phần ba chiếc bánh, tức một nửa phần của bên kia. (Chú thích của tác giả: chẳng hạn công đoàn và ban quản lý đánh giá rủi ro của trì hoãn và hậu quả của nó khác nhau. Cụ thể, công đoàn coi 1,00 USD ngay bây giờ tương đương 1,01 USD một tuần sau (δ = 0,99), còn với ban quản lý con số là 1,02 USD (δ = 0,98). Nói cách khác, "lãi suất" theo tuần của công đoàn là 1%, của ban quản lý là 2%. Ban quản lý sốt ruột gấp đôi công đoàn nên sẽ được một nửa phần của công đoàn.)

| Bên | δ mỗi tuần | "Lãi suất" chờ mỗi tuần | Phần bánh khi các vòng rất ngắn |
|---|---|---|---|
| Công đoàn | 0,99 | 1% | 2/3 |
| Ban quản lý | 0,98 | 2% | 1/3 |

Hai tác giả kết phụ lục bằng một hàm ý chính sách: việc phần lớn hơn thuộc về bên kiên nhẫn hơn là điều không may cho nước Mỹ. Hệ thống chính quyền Mỹ và cách truyền thông đưa tin nuôi dưỡng sự sốt ruột. Khi đàm phán quân sự và kinh tế với các nước khác tiến triển chậm, các nhóm vận động hành lang có lợi ích liên quan tìm sự ủng hộ của hạ nghị sĩ, thượng nghị sĩ và báo chí, những người ép chính quyền phải có kết quả nhanh hơn. Các nước đối thủ trong đàm phán biết rõ điều này và đòi được những nhượng bộ lớn hơn từ Mỹ.

**Ví dụ hôm nay** (minh hoạ của người tổng hợp, con số giả định). Hai công ty khởi nghiệp, A và B, cùng thuê một văn phòng chia sẻ. Nếu mỗi bên thuê riêng, A trả 30 triệu đồng/tháng cho một văn phòng nhỏ, B trả 50 triệu đồng/tháng cho một văn phòng lớn hơn; tổng BATNA là 80 triệu đồng. Thuê chung một tầng hết 60 triệu đồng/tháng, tức thoả thuận tạo ra chiếc bánh 20 triệu đồng tiết kiệm. Chia theo diện tích (giả sử A dùng 40%, B dùng 60%) thì A trả 24 triệu, B trả 36 triệu. Chia đôi khoản tiết kiệm theo cách của Dixit và Nalebuff thì mỗi bên tiết kiệm 10 triệu: A trả 20 triệu, B trả 40 triệu. Giả sử B đang có một phương án dự phòng khác: một toà nhà mời B thuê với giá 42 triệu đồng/tháng. BATNA của B khi đó là 42 triệu thay vì 50 triệu, tổng BATNA là 72 triệu, chiếc bánh chỉ còn 12 triệu; chia đôi thì mỗi bên tiết kiệm 6 triệu, A trả 24 triệu, B trả 36 triệu. Phương án dự phòng tốt hơn của B chuyển 4 triệu đồng mỗi tháng từ A sang B, đúng như trong ví dụ khách sạn.

## Luận điểm kinh tế cốt lõi

### Mệnh đề

Mặc cả giữa hai bên có thể phân tích bằng suy luận ngược. Khi hai bên kiên nhẫn như nhau và các vòng đề nghị cách nhau ngắn, họ chia đôi phần giá trị mà thoả thuận tạo thêm so với tổng BATNA của hai bên, và thoả thuận đạt ngay. Phần của mỗi bên tăng theo BATNA và mức kiên nhẫn của bên đó. Đổ vỡ và đình công xảy ra khi hai bên không cùng thông tin về chi phí chờ của nhau, và đình công là cách tốn kém để phát tín hiệu; đình công ảo có thể giữ nguyên sức ép mặc cả mà loại bỏ thiệt hại cho người ngoài cuộc.

### Giả định

- Mỗi bên lý trí, nhìn trước và suy luận ngược, quan tâm tới phần của mình (chương nới giả định này khi bàn tới chuẩn mực công bằng 50:50).
- Trì hoãn thoả thuận tốn kém: chiếc bánh nhỏ đi theo thời gian (khách sạn mất 1.000 USD mỗi ngày; δ nhỏ hơn 1).
- Trong mô hình cơ bản, hai bên có cùng thông tin và nhìn thấy cùng một kết cục; khi bỏ giả định này, đình công xuất hiện.
- Hai bên kiên nhẫn như nhau thì chia đôi phần dư; kiên nhẫn khác nhau thì phần của mỗi bên tỷ lệ nghịch với chi phí chờ của bên đó.
- BATNA của mỗi bên là điều họ chắc chắn có được nếu không thoả thuận, và có thể bị tác động bằng nước đi chiến lược.

### Cơ chế

1. Xác định điểm kết thúc (ngày cuối mùa) và bên có quyền đề nghị ở vòng cuối; bên đó lấy gần hết phần còn lại.
2. Lùi từng vòng: bên đề nghị phải trả cho bên kia đúng bằng những gì bên kia có được nếu chờ thêm một vòng; khi có nhiều vòng, lợi thế đề nghị cuối nhỏ dần và kết quả tiến về chia đôi.
3. Thêm BATNA: mỗi bên xuất phát với "điểm chấp" bằng BATNA của mình; chỉ phần dư được chia đôi.
4. Nước đi chiến lược: một bên có thể chấp nhận hạ BATNA của chính mình nếu làm BATNA đối thủ giảm nhiều hơn (công đoàn hy sinh 100 USD để làm ban quản lý mất 200 USD, được thêm 50 USD).
5. Khi thông tin không đối xứng, mỗi bên tuyên bố chi phí chờ thấp; tuyên bố chỉ được tin khi được chứng minh bằng hành động tốn kém (đình công), và chiến lược bên bờ vực giữ đình công kéo dài từng ngày cho tới khi một bên nhận ra bên kia mạnh hơn.
6. Đình công ảo tách sức ép mặc cả (hai bên vẫn mất tiền) khỏi thiệt hại cho bên thứ ba (sản xuất vẫn chạy).

### Bằng chứng và ví dụ hai tác giả đưa ra

- Bài toán khách sạn 101 ngày: 505 USD/495 USD khi không có phương án ngoài; 650 USD/350 USD khi công đoàn có việc ngoài 300 USD; 250 USD/750 USD khi ban quản lý có lao động thay thế lãi 500 USD; 400 USD/600 USD khi có cả hai; 450 USD/550 USD sau khi công đoàn tăng cường biểu tình.
- Vé máy bay luật sư: chiếc bánh 1.000 USD; Houston trả 832 USD, San Francisco trả 1.986 USD; gốc từ nguyên tắc "chia tấm vải" trong Talmud.
- Đình công của cầu thủ bóng chày nhà nghề Mỹ năm 1980, chọn đúng thời điểm chủ đội thiệt nặng nhất.
- Đình công ở UPS (thời điểm trước Giáng sinh); Mỹ và đồng minh về chi phí quốc phòng; Mỹ và Nhật về thương mại và an ninh.
- GATT và WTO: đàm phán rộng thành công hơn đàm phán hẹp theo ngành.
- Đóng cửa cảng năm 2002: thiệt hại hơn 10 tỷ USD cho khoản tranh chấp 20 triệu USD; NHL huỷ mùa 2004–05.
- Đình công ảo ở Jenkins Company (Thế chiến II), xe buýt Miami (1960), Meridiana (1999), Công đoàn Vận tải Ý (2000).
- Mô hình Rubinstein: bên trả lời được δ/(1 + δ); ví dụ công đoàn δ = 0,99 và ban quản lý δ = 0,98 chia 2/3 và 1/3.

### Kết luận và hàm ý chính sách

- Bước đầu tiên của mọi cuộc đàm phán là đo đúng chiếc bánh: phần giá trị vượt trên tổng BATNA, không phải tổng giá trị.
- Muốn được phần lớn hơn, hãy cải thiện BATNA của mình (hoặc hạ BATNA của đối phương) và giảm chi phí chờ của mình; tranh cãi về "công bằng" theo số dặm hay tỷ lệ giá vé ít có sức thuyết phục bằng lập luận BATNA.
- Đình công và đổ vỡ không phải thất bại của lý trí mà là hệ quả của thông tin không đối xứng; giảm bất đồng về thông tin giúp giảm đình công.
- Nên thiết kế trước cơ chế giải quyết tranh chấp (như đình công ảo) để hai bên chịu sức ép mà xã hội không chịu thiệt hại phụ.
- Gộp nhiều vấn đề vào một cuộc đàm phán tạo thêm giá trị, nhưng bên yếu nên cảnh giác khi bên mạnh dùng vấn đề này để đe doạ ở vấn đề khác.
- Với nhà nước, một hệ thống chính trị và truyền thông khiến nhà đàm phán sốt ruột là bất lợi trong đàm phán quốc tế.

### Trong ngôn ngữ kinh tế học

- **Mặc cả luân phiên có kỳ hạn hữu hạn (finite-horizon alternating-offers bargaining).** Mô hình khách sạn 101 ngày, giải bằng quy nạp ngược (backward induction) để tìm cân bằng Nash hoàn hảo trong trò chơi con (subgame perfect equilibrium).
- **Mô hình mặc cả Rubinstein (1982).** Mặc cả luân phiên vô hạn với chiết khấu; cân bằng duy nhất cho bên đề nghị 1/(1 + δ). Khi δ tiến tới 1, kết quả tiến tới lời giải mặc cả Nash (Nash bargaining solution): chia đôi phần dư vượt trên điểm bất đồng (disagreement point), tức BATNA trong ngôn ngữ của chương.
- **Thặng dư hợp tác (surplus from cooperation).** "Chiếc bánh" của hai tác giả: tổng giá trị khi hợp tác trừ tổng giá trị khi không hợp tác.
- **Giá trị Shapley và chia chi phí (cost allocation).** Ví dụ vé máy bay là một bài toán chia chi phí chung; với hai bên, chia đôi khoản tiết kiệm trùng với giá trị Shapley. Nguyên tắc "chia tấm vải" trong Talmud là một bài toán chia tài sản có tranh chấp đã được lý thuyết trò chơi hiện đại phân tích.
- **Đình công như hệ quả của thông tin bất cân xứng (asymmetric information and strikes).** Cách giải thích đình công bằng phát tín hiệu và sàng lọc về chi phí chờ, thay vì bằng sự phi lý.
- **Ngoại ứng tiêu cực (negative externality).** Thiệt hại của đình công lên khách hàng và nền kinh tế là chi phí mà hai bên mặc cả không tính tới; đình công ảo nội hoá chi phí này.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong chương |
|---|---|
| Bargaining | Mặc cả: hai bên quyết định cách chia phần giá trị chung |
| The pie | "Chiếc bánh": phần giá trị đang được mặc cả, tức giá trị vượt trên tổng BATNA |
| Ultimatum game | Trò chơi tối hậu thư: một bên đề nghị một lần, bên kia nhận hoặc từ chối, từ chối thì cả hai mất hết |
| Look forward and reason backward | Nhìn trước và suy luận ngược |
| Alternating offers | Luân phiên đề nghị |
| Handicap | Điểm chấp (ẩn dụ golf): BATNA mà mỗi bên mang vào mặc cả |
| Cost of waiting | Chi phí chờ đợi |
| BATNA (Best Alternative to a Negotiated Agreement) | Phương án thay thế tốt nhất khi không đạt thoả thuận |
| Fallback | Phương án dự phòng (cách nói khác của BATNA) |
| Scab labor | Lao động thay thế người đình công |
| Picket line / picketing | Hàng người biểu tình chặn cửa / biểu tình chặn cửa |
| Lockout | Chủ đóng cửa không cho công nhân làm việc |
| Brinkmanship | Chiến lược bên bờ vực: cố ý tạo rủi ro đổ vỡ mà không bên nào kiểm soát hết |
| Signaling | Phát tín hiệu: hành động tốn kém để chứng minh điều lời nói không chứng minh được |
| Expired contract | Hợp đồng lao động đã hết hạn nhưng vẫn được áp dụng trên thực tế |
| Multi-issue bargaining | Mặc cả đồng thời nhiều vấn đề |
| Virtual strike | Đình công ảo: vẫn làm việc nhưng công nhân không nhận lương, doanh nghiệp nộp toàn bộ doanh thu |
| Collateral damage | Thiệt hại phụ cho người ngoài cuộc |
| Taft-Hartley Act | Luật Taft-Hartley (1947), cho phép tổng thống Mỹ can thiệp chấm dứt tạm thời tranh chấp lao động đe doạ lợi ích quốc gia |
| Rubinstein bargaining | Mô hình mặc cả Rubinstein: luân phiên đề nghị, không có ngày kết thúc |
| δ (delta) | Hệ số kiên nhẫn: phần giá trị còn lại nếu thoả thuận chậm một vòng |
| Divided cloth (Talmud) | Nguyên tắc "chia tấm vải" trong Talmud |

## Câu nói đáng nhớ

> "Bên nào tự mình làm được càng tốt khi không có thoả thuận thì phần bánh mặc cả của bên đó càng lớn."
*"The better a party can do by itself in the absence of an agreement, the larger its share of the bargaining pie will be."*

> "Bước đầu tiên trong mọi cuộc đàm phán là đo đúng chiếc bánh."
*"The first step in any negotiation is to measure the pie correctly."*

> "Như mọi khi, hành động có sức nặng hơn lời nói."
*"As always, actions speak louder than words."*

> "Chiến lược bên bờ vực là vũ khí của bên mạnh hơn trong hai bên, tức bên ít sợ đổ vỡ hơn."
*"The strategy of brinkmanship is a weapon for the stronger of the two parties—namely, the one that fears a breakdown less."*

> "Nghịch lý là bên kia thường sẽ được lợi khi tỏ ra phi lý, nên bạn không thể cứ thế tin sự phi lý đó."
*"The paradox is that the other side will often gain by appearing to be irrational, so you can't simply accept irrationality at face value."*

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương là biến "công bằng" từ cảm tính thành phép tính dựa trên BATNA

Ví dụ vé máy bay là phần thuyết phục nhất. Ba cách chia đầu tiên (chia đôi, chia theo chặng, chia theo tỷ lệ giá vé) đều nghe hợp lý, và nhiều người đọc sẽ chọn một trong số đó. Hai tác giả cho thấy cách chia đôi bị Houston từ chối ngay (1.409 USD đắt hơn 1.332 USD tự đi), còn hai cách kia không trả lời được câu hỏi: vì sao Houston phải chấp nhận ít phần tiết kiệm hơn, khi không có Houston thì khoản tiết kiệm 1.000 USD cũng không tồn tại? Lập luận "đo chiếc bánh" cho ra một con số (832 USD và 1.986 USD) mà mỗi bên đều có thể bảo vệ. Đây là công cụ dùng được ngay trong mọi tình huống chia chi phí hay lợi ích chung.

### Mô hình khách sạn đơn giản hoá nhiều điều mà chính chương sau đó thừa nhận

Kết quả "thoả thuận ngay, chia gần đôi" dựa trên giả định hai bên cùng thông tin, lý trí và chỉ quan tâm tới tiền. Hai tác giả tự chỉ ra giới hạn: chuẩn mực công bằng khiến công nhân không nhận 101 USD trên 101.000 USD; thông tin không đối xứng sinh ra đình công. Điểm cần lưu ý là quy tắc "chia đôi phần dư" chỉ là điểm xuất phát; trong thực tế, phần của mỗi bên còn phụ thuộc vào khả năng chứng minh BATNA, uy tín, và những bên thứ ba tác động lên đàm phán. Lời giải thích đình công bằng thông tin không đối xứng cũng chỉ là một trong nhiều giải thích; các nghiên cứu khác nhấn mạnh yếu tố chính trị nội bộ công đoàn (thủ lĩnh cần cho đoàn viên thấy mình đã chiến đấu) mà chương không bàn.

### Ý tưởng đình công ảo hấp dẫn về lý thuyết nhưng gặp trở ngại thực tế mà chính hai tác giả nhận ra

Đình công ảo giữ nguyên sức ép giữa hai bên và loại bỏ thiệt hại cho người ngoài. Nhưng như hai tác giả thừa nhận, đình công thật thường cố ý gây phiền cho khách hàng để họ ép ban quản lý, và đình công ảo lại mang về cho doanh nghiệp tiếng tốt (tặng tiền cho bệnh viện nhi), nên sức ép lên ban quản lý có thể yếu hơn đình công thật. Ngoài ra, cam kết nộp toàn bộ doanh thu đòi hỏi một bên thứ ba đáng tin để giám sát, và cả hai bên phải thoả thuận về đình công ảo từ trước, khi quan hệ còn tốt. Gần hai thập kỷ sau khi sách ra đời, đình công ảo vẫn hiếm, cho thấy những trở ngại này là có thật.

### Từ 2008, đàm phán khí hậu và thương mại minh hoạ đúng các cảnh báo của chương

Nói định tính: các cuộc đàm phán khí hậu toàn cầu sau 2008 cho thấy chính vấn đề hai tác giả nêu, các thế hệ tương lai không có ghế ở bàn đàm phán, và cách chia "chiếc bánh" phát thải giữa nước giàu và nước nghèo là điểm vướng mắc chính. Các vòng đàm phán thương mại đa phương rộng trong WTO sau đó lại bế tắc, khiến nhiều nước chuyển sang hiệp định khu vực và song phương; điều này cho thấy gộp nhiều vấn đề không phải lúc nào cũng thành công khi số bên quá đông. Việc dùng quan hệ an ninh để gây sức ép thương mại, đúng như ví dụ Mỹ và Nhật trong chương, vẫn là chủ đề nóng trong quan hệ quốc tế.

### Quan điểm trái chiều: sốt ruột không phải lúc nào cũng là điểm yếu

Hai tác giả kết luận hệ thống chính trị Mỹ bất lợi vì khiến nhà đàm phán sốt ruột. Nhưng theo chính logic về cam kết mà cuốn sách trình bày ở Chương 6 và 7, một nhà đàm phán bị trói tay bởi Quốc hội hay dư luận có thể lại có lợi: "tôi không thể chấp nhận ít hơn, Quốc hội sẽ không phê chuẩn" là một cam kết đáng tin. Sốt ruột về thời gian và bị ràng buộc về điều khoản là hai chuyện khác nhau; một hệ thống chính trị có thể đồng thời khiến nhà đàm phán vội vàng và cho họ một lý do đáng tin để giữ yêu cầu cao.

### Vận dụng: trước mỗi cuộc đàm phán, hãy tính BATNA của cả hai bên và đo chiếc bánh

- **Trong doanh nghiệp.** Trước khi đàm phán với nhà cung cấp, khách hàng hay đối tác liên doanh, hãy viết ra BATNA của mình và ước tính BATNA của bên kia; phần đáng mặc cả là chênh lệch giữa giá trị khi hợp tác và tổng hai BATNA. Đầu tư vào phương án thay thế (thêm một nhà cung cấp dự phòng, một kênh phân phối khác) là cách trực tiếp nhất để tăng phần của mình, kể cả khi không bao giờ dùng tới nó. Khi chia chi phí chung (văn phòng, kho bãi, chiến dịch quảng cáo chung), hãy đề xuất chia đôi khoản tiết kiệm thay vì chia theo diện tích hay doanh thu.
- **Trong đầu tư.** Khi đánh giá một doanh nghiệp có nguy cơ tranh chấp lao động hay đàm phán hợp đồng lớn, hãy hỏi bên nào có chi phí chờ thấp hơn và thời điểm nào doanh nghiệp dễ bị tổn thương nhất (như mùa cao điểm với chủ đội bóng chày, hay dịp Giáng sinh với UPS). Trong thương vụ mua bán doanh nghiệp, bên có nhiều người mua hay người bán thay thế, hoặc ít áp lực thời gian hơn, thường giành được phần lớn hơn của giá trị cộng hưởng.
- **Trong nghề nghiệp.** Khi đàm phán lương, BATNA là lời mời làm việc khác thật sự trong tay, không phải lời tuyên bố "tôi có thể đi". Ứng viên đang có việc ổn định có chi phí chờ thấp hơn người đang thất nghiệp và vì vậy mạnh hơn. Khi đàm phán gói đãi ngộ, hãy tìm những hạng mục công ty định giá thấp mà bạn định giá cao (thời gian làm việc linh hoạt, ngân sách đào tạo, bảo hiểm nhóm), như ví dụ bảo hiểm y tế trong chương.
- **Khi đọc tin chính sách.** Ở Việt Nam, khi đọc tin về đàm phán hiệp định thương mại, về tranh chấp lao động hay ngừng việc tập thể ở các khu công nghiệp, hoặc về thương lượng tiền lương tối thiểu giữa đại diện người lao động và người sử dụng lao động, có thể hỏi: BATNA của mỗi bên là gì, bên nào có chi phí chờ thấp hơn, và ai ngoài bàn đàm phán đang chịu thiệt hại phụ. Một bên tuyên bố cứng rắn chưa chắc là bên mạnh; bên mạnh là bên ít sợ đổ vỡ hơn.
