# Chương 10 — Đấu giá, đấu thầu và các cuộc đọ sức (Auctions, Bidding, and Contests)

**Nguồn:** Avinash K. Dixit và Barry J. Nalebuff, *The Art of Strategy: A Game Theorist's Guide to Success in Business and Life*, ấn bản đầu (W. W. Norton, 2008), Phần III, Chương 10.
**Tác giả:** Avinash K. Dixit (sinh 1944), nhà kinh tế Mỹ gốc Ấn, giáo sư danh dự Đại học Princeton; Barry J. Nalebuff (sinh 1958), giáo sư Trường Quản trị Yale. Sách kế thừa *Thinking Strategically* (1991) của cùng hai tác giả.
**Vị trí trong lập luận của cả cuốn sách:** Phần I và II xây dựng bộ công cụ: suy luận ngược, thế lưỡng nan của người tù, cân bằng Nash, chiến lược hỗn hợp, nước đi chiến lược và độ tin cậy. Phần III đem bộ công cụ đó vào từng loại tình huống cụ thể. Chương 8 bàn về thông tin bất cân xứng và đã nêu hiện tượng "lời nguyền của người thắng" (winner's curse), hứa sẽ chỉ cách tránh nó ở Chương 10; Chương 1 cũng đã nhắc tới hiện tượng này. Chương 9 bàn về hợp tác và phối hợp. Chương 10 áp dụng các khái niệm chiến lược trội, cân bằng Nash và tư duy "nhìn trước hệ quả" vào đấu giá, rồi mở rộng sang hai loại cuộc đọ sức trông không giống đấu giá: trò chơi chiếm trước (preemption game) và cuộc chiến tiêu hao (war of attrition). Chương 11 tiếp theo bàn về mặc cả (bargaining), một dạng tương tác mua bán khác mà ở đó không có luật đấu giá cố định.
**Ý chính:** Hai tác giả muốn người đọc hiểu rằng bỏ giá là một quyết định chiến lược, không phải chuyện cảm xúc. Có ba ý trung tâm. Thứ nhất, trong đấu giá Vickrey (người trả giá cao nhất thắng nhưng chỉ trả mức giá cao thứ hai), bỏ đúng giá trị thật của mình là chiến lược trội. Thứ hai, người chơi sẽ điều chỉnh chiến lược để bù trừ cho thay đổi của luật chơi, nên với giá trị riêng và người chơi đối xứng, đấu giá kiểu Anh, Vickrey, Hà Lan và đấu giá kín đều đem lại cho người bán cùng một doanh thu trung bình (định lý tương đương doanh thu); phí người mua ở Sotheby's thực ra do người bán gánh, và việc Bộ Tài chính Mỹ chuyển sang đấu giá giá thống nhất cho tín phiếu không làm họ mất tiền. Thứ ba, hãy luôn bỏ giá "như thể mình đã thắng": ví dụ mua công ty ACME cho thấy người tính theo giá trị trung bình sẽ trả 10,5 triệu USD cho một thứ chỉ đáng trung bình 9,375 triệu USD khi lời đề nghị được nhận. Chương kết bằng tình huống đấu giá giấy phép phổ tần, nơi AT&T có giá trị cao hơn MCI ở cả hai giấy phép nhưng nên chỉ lấy một giấy phép với giá 1 thay vì cả hai với tổng giá 17.

> **Lưu ý:** Sách viết khoảng 2007–2008, nên các con số mang dấu ấn thời điểm đó: đấu giá quảng cáo của Google và Yahoo! thu "hơn 10 tỷ USD", FCC thu hơn 40 tỷ USD từ đấu giá phổ tần giai đoạn 1994–2005, cuộc đấu giá 3G ở Anh (năm 2000) thu 22,5 tỷ bảng. Từ đó, Yahoo! không còn là đối thủ đáng kể trong quảng cáo tìm kiếm, và quy mô đấu giá quảng cáo trực tuyến đã lớn hơn nhiều; một phần đấu giá quảng cáo hiển thị đã chuyển từ dạng giá thứ hai sang dạng giá thứ nhất vào cuối thập niên 2010. Năm 2020, Paul Milgrom và Robert Wilson nhận giải Nobel kinh tế cho các đóng góp vào lý thuyết đấu giá và thiết kế thể thức đấu giá mới, gồm thể thức đấu giá đồng thời nhiều vòng mà FCC dùng (chính thể thức trong tình huống cuối chương). Chương có **12 chú thích chân trang** của tác giả (đánh dấu từ {FN81} đến {FN92} trong text gốc); tất cả đã được đưa vào phần Nội dung chi tiết ngay tại chỗ chúng xuất hiện, ghi rõ "Chú thích của tác giả". Chương có ba bài tập "Trip to the Gym" (số 6, 7 và 8); đề bài và đáp án của sách đã được đưa vào ngay sau chỗ bài tập xuất hiện. Sáu hình trong chương (bảng so sánh hai cách bỏ giá, bảng các giá bỏ trong đấu giá tín phiếu, tranh biếm hoạ Doonesbury về máy Newton, ba bảng giá trong tình huống phổ tần) đã được dựng lại. Text gốc có hai chỗ lệch nhỏ: ví dụ tín phiếu nói có "mười" mức bỏ giá rồi sau đó gọi là "tám mức bỏ giá như trên", trong khi bảng của sách có chín dòng; sản phẩm của Apple được gọi là "Original Newton Message", tên thương mại thường dùng là Newton MessagePad. Các câu trích là bản dịch của người tổng hợp.

## Sơ đồ

### Phần mở đầu chương (không có tiêu đề riêng) — đấu giá bán, đấu thầu mua và các câu hỏi chiến lược

```text
       Hình ảnh cũ về đấu giá: người điều hành giọng Anh kiểu cách, phòng
       đầy nhà sưu tầm đeo trang sức ra hiệu bằng cách kéo tai
       · eBay đã khiến đấu giá trở nên đại chúng hơn
                                │
                                ▼
       Dạng quen thuộc nhất: MỘT người bán, NHIỀU người mua, ai trả cao
       nhất thì thắng
       · Sotheby's: tranh, đồ cổ
       · eBay: hộp kẹo Pez, bộ trống cũ, gần như mọi thứ (trừ quả thận)
       · Google, Yahoo!: đấu giá vị trí quảng cáo bên cạnh kết quả tìm
         kiếm theo từ khoá, thu hơn 10 tỷ USD
       · Úc: ngay cả nhà ở cũng bán bằng đấu giá
                                │
                                ▼
       Đấu giá cũng dùng để MUA: ĐẤU THẦU MUA SẮM (procurement auction)
       · chính quyền địa phương muốn làm đường, mời các nhà thầu bỏ giá
       · người bỏ giá THẤP NHẤT thắng; một người mua, nhiều người bán
       · Chú thích của tác giả: đấu thầu phức tạp hơn vì các mức giá
         không cùng "đơn vị" (chất lượng công trình khác nhau), nên chương
         tập trung vào đấu giá bán thông thường
                                │
                                ▼
       Bỏ giá cần chiến lược, không chỉ cần một tấm thẻ giơ lên; bỏ giá
       theo cảm xúc dễ dẫn tới hối hận
       · nên bỏ sớm hay chờ tới phút chót?
       · nếu món đồ đáng 100 USD với bạn, nên bỏ tới đâu?
       · làm sao tránh thắng rồi mới thấy mình trả quá đắt (LỜI NGUYỀN
         CỦA NGƯỜI THẮNG, winner's curse)?
       · có nên tham gia không: nhà ở Úc đấu giá ngày 1/7, căn bạn thích
         hơn đấu giá một tuần sau; chờ căn sau thì có thể mất cả hai
```

### Tiểu mục "English and Japanese Auctions" — đấu giá kiểu Anh và kiểu Nhật

```text
       ĐẤU GIÁ KIỂU ANH (English auction, đấu giá tăng dần): người điều
       hành hô giá tăng dần ("30 từ quý bà mũ hồng... 40... có ai 50
       không?... 40 lần một, lần hai, bán")
                                │
                                ▼
       Chiến lược tối ưu đơn giản: tiếp tục bỏ giá cho tới khi giá vượt
       giá trị của mình thì rút
       · bước giá 10, giá trị 95: bạn dừng ở 90 (rắc rối nhỏ ở cuối cuộc
         đấu); hai tác giả giả định bước giá rất nhỏ, ví dụ 1 xu
                                │
                                ▼
       "GIÁ TRỊ" (value) là MỨC GIÁ BỎ ĐI (walkaway number): mức giá cao
       nhất mà bạn vẫn muốn thắng; tại đúng mức đó, thắng hay thua với bạn
       là như nhau
       · có thể gồm: phần bù để món đồ không rơi vào tay đối thủ, niềm vui
         chiến thắng, giá bán lại dự kiến
                                │
                                ▼
       Hai loại giá trị
       · GIÁ TRỊ RIÊNG (private value): không phụ thuộc người khác nghĩ
         gì; ví dụ cuốn The Art of Strategy có chữ ký tặng riêng bạn
       · GIÁ TRỊ CHUNG (common value): như nhau với mọi người nhưng mỗi
         người ước lượng khác nhau; ví dụ lô dầu ngoài khơi, lượng dầu
         như nhau dù Exxon hay Shell thắng
       · thực tế thường lẫn cả hai (hãng khai thác giỏi hơn có thêm phần
         giá trị riêng)
                                │
                                ▼
       Với giá trị chung, biết ai còn bỏ giá và ai rút lúc nào là thông
       tin quý; đấu giá kiểu Anh GIẤU thông tin đó (người im lặng vẫn có
       thể nhảy vào phút chót)
                                │
                                ▼
       ĐẤU GIÁ KIỂU NHẬT (Japanese auction): mọi người giơ tay từ đầu, giá
       tăng theo đồng hồ (30, 31, 32...); hạ tay là rút và KHÔNG được giơ
       lại; còn một người thì kết thúc
       · luôn biết bao nhiêu người còn chơi và mỗi người rút ở giá nào
       · giống đấu giá kiểu Anh nhưng mọi người buộc phải lộ bài
                                │
                                ▼
       Kết quả dễ đoán: người có giá trị CAO NHẤT thắng và trả đúng giá
       trị CAO THỨ HAI (giá lúc người áp chót rút lui)
```

### Tiểu mục "Vickrey Auction" — đấu giá Vickrey (kèm bài tập Trip to the Gym số 6)

```text
       1961: William Vickrey (Đại học Columbia, sau này đoạt Nobel) đề
       xuất đấu giá giá thứ hai, nay gọi là ĐẤU GIÁ VICKREY
       · Chú thích của tác giả: bài gốc đăng Journal of Finance 1961; dân
         sưu tầm tem đã dùng từ thế kỷ 19; Goethe dùng năm 1797 khi bán
         bản thảo cho nhà xuất bản
                                │
                                ▼
       Luật: mọi người bỏ giá trong phong bì kín; giá cao nhất thắng
       NHƯNG người thắng chỉ trả mức giá cao THỨ HAI
                                │
                                ▼
       Điều "kỳ diệu": mọi người đều có CHIẾN LƯỢC TRỘI là bỏ đúng giá trị
       thật của mình
       · so với đấu giá kín thường (trả theo giá mình bỏ): phải đoán số
         người chơi, giá trị của họ, cả việc họ nghĩ gì về bạn
       · hai tác giả: mục tiêu của họ là tính toán chiến lược khi THIẾT KẾ
         trò chơi để người chơi không phải tính toán khi CHƠI nó
                                │
                                ▼
       Chứng minh: giá trị thật 60 USD; so sánh bỏ 60 với bỏ 50
       ┌─────────────────────────┬───────────────┬───────────────┐
       │ Giá cao nhất của người  │ Nếu bỏ 50     │ Nếu bỏ 60     │
       │ khác                    │               │               │
       ├─────────────────────────┼───────────────┼───────────────┤
       │ Trên 60 (ví dụ 63, 70)  │ thua          │ thua          │
       │ Dưới 50 (ví dụ 43)      │ thắng, trả 43 │ thắng, trả 43 │
       │ Giữa 50 và 60 (ví dụ 53)│ THUA          │ thắng, trả 53,│
       │                         │               │ lãi 7         │
       └─────────────────────────┴───────────────┴───────────────┘
       → bỏ thấp hơn giá trị chỉ tạo khác biệt khi bạn thua mà lẽ ra muốn
         thắng; lập luận tương tự cho thấy không nên bỏ cao hơn giá trị
                                │
                                ▼
       TRIP TO THE GYM SỐ 6: biết trước giá của người khác trong đấu giá
       Vickrey đáng bao nhiêu? Đáp án của sách: KHÔNG đáng gì (với giá trị
       riêng), vì bạn vẫn bỏ đúng giá trị dù biết gì; ngoại lệ là giá trị
       chung, khi thông tin làm bạn đổi ước lượng giá trị
```

### Tiểu mục "Revenue Equivalence" và "Buyer's Premium" — tương đương doanh thu và phí người mua

```text
       Đấu giá Vickrey đi tới CÙNG kết quả với đấu giá kiểu Anh/Nhật chỉ
       trong một bước: cùng người thắng (giá trị cao nhất), cùng giá phải
       trả (giá trị cao thứ hai)
                                │
                                ▼
       Khác biệt nhỏ: trong đấu giá kiểu Anh/Nhật người chơi thấy được một
       phần giá của người khác; trong Vickrey không thấy gì tới khi kết
       thúc; nhưng với GIÁ TRỊ RIÊNG, thông tin đó vô dụng, nên người bán
       thu như nhau
                                │
                                ▼
       Đây là một phần của kết quả tổng quát: nhiều thay đổi luật chơi
       không làm người bán thu nhiều hơn hay ít hơn
                                │
                                ▼
       PHÍ NGƯỜI MUA (buyer's premium) ở Sotheby's, Christie's: cộng thêm
       20%; thắng với 1.000 USD thì viết séc 1.200 USD
       · ai thực sự trả? Hai tác giả trả lời: NGƯỜI BÁN
       · nhà sưu tầm sẵn sàng trả 600 USD sẽ chỉ bỏ tối đa 500 USD
       · phí giống như quy đổi tiền tệ: nói 100 nghĩa là 120
       · Chú thích của tác giả: như đấu giá ở New York nhưng hô giá bằng
         euro; đổi đơn vị hô giá không làm nhà đấu giá thu thêm
       → người thắng vẫn trả tổng như cũ; nhà đấu giá lấy một phần,
         phần đó trừ vào tiền người bán
                                │
                                ▼
       Bài học lớn: đổi luật chơi thì người chơi đổi chiến lược, và nhiều
       khi bù trừ chính xác điều bạn vừa thay đổi
```

### Tiểu mục "Online Auctions" và "Sniping" — đấu giá trực tuyến và đặt giá phút chót

```text
       eBay: bạn không bỏ giá trực tiếp mà đặt GIÁ ỦY NHIỆM (proxy bid);
       eBay bỏ giá thay bạn tới mức đó
       · ủy nhiệm 100 USD, giá hiện tại 12: eBay bỏ 13 cho bạn; nếu người
         khác ủy nhiệm 26, eBay đẩy họ tới 26 và bạn lên 27
                                │
                                ▼
       Trông giống đấu giá Vickrey: ủy nhiệm A 26, B 33, C 100 → C thắng,
       trả 34 (giá ủy nhiệm cao thứ hai cộng một bước)
       · nếu mọi người nộp ủy nhiệm một lần, cùng lúc, thì đúng là Vickrey
         và bỏ đúng giá trị là chiến lược trội
                                │
                                ▼
       Nhưng có những "trục trặc nhỏ" khiến người ta bỏ giá cầu kỳ:
       · nhiều món tương tự cùng bán (khoảng mười bộ trống Pearl Export);
         sẵn sàng trả 400 USD cho một bộ, nhưng không bỏ 300 cho bộ này khi
         bộ kia có thể mua được với 250
       · thích cuộc đấu kết thúc sớm hơn để biết ngay mình thắng hay chưa
       → giá trị phụ thuộc vào những gì khác đang và sẽ được bán
                                │
                                ▼
       ĐẶT GIÁ PHÚT CHÓT (sniping): người ta chờ tới phút, thậm chí giây
       cuối mới đặt ủy nhiệm; có dịch vụ như Bidnapper làm thay
                                │
                                ▼
       Giải thích 1: giá ủy nhiệm sớm làm lộ thông tin
       · nhà buôn đồ nội thất bỏ giá cho một ghế Bauhaus: người khác suy
         ra ghế thật và có giá trị lịch sử; nhà buôn chịu 1.000 USD thì
         bạn sẵn lòng trả 1.200 USD
       · nhưng điều này chỉ đúng khi danh tính nhà buôn bị người khác biết
         và nhà buôn không dùng được tên giả (Chú thích của tác giả: tên
         giả dễ tạo, nhưng tài khoản không có lịch sử giao dịch có thể bị
         người bán ngại nhận)
       · vì đặt giá phút chót quá phổ biến, phải còn lý do khác
                                │
                                ▼
       Giải thích 2 (hai tác giả cho là tốt nhất): nhiều người KHÔNG BIẾT
       giá trị của chính mình, vì tìm ra nó tốn công
       · chiếc Porsche 911 đời cũ, giá khởi điểm 1 USD; người lười đặt ủy
         nhiệm 1.000 USD vì chắc chắn dưới mức đó là món hời
       · người mua am hiểu định giá 19.000 USD; nếu đặt ủy nhiệm ngay từ
         đầu, giá lập tức lên 1.000, người lười giật mình, đi tìm hiểu,
         được vợ/chồng cho bỏ tới 9.000 → giá cuối có thể lên 9.000 hoặc
         hơn
       · nếu chờ tới phút chót, giá có thể ở dưới 1.000 tới tận cuối
       → đặt giá phút chót để người khác không kịp nhận ra giá lười của
         họ không có cơ hội thắng, không kịp "làm bài tập về nhà"
```

### Tiểu mục "Bidding as If You've Won" và "ACME" — bỏ giá như thể mình đã thắng

```text
       Tư duy theo hệ quả (consequentialist): nhìn trước xem hành động của
       mình tạo khác biệt ở tình huống nào, rồi coi tình huống đó là tình
       huống thật ngay khi ra quyết định → công cụ chính để tránh lời
       nguyền của người thắng
                                │
                                ▼
       Ví dụ cầu hôn: hãy giả định câu trả lời là "đồng ý" khi ngỏ lời;
       nếu nghe "đồng ý" mà bạn lại muốn nghĩ lại, thì lẽ ra không nên hỏi
                                │
                                ▼
       TRÒ CHƠI ACME
       · bạn làm tăng giá trị ACME thêm 50%, dù giá trị hiện tại là bao
         nhiêu
       · giá trị hiện tại từ 2 đến 12 triệu USD, mọi mức đều khả năng như
         nhau, trung bình 7 triệu
       · bạn ra MỘT lời đề nghị, chủ sở hữu nhận nếu giá cao hơn giá trị
         hiện tại
       · ví dụ: trả 10 triệu, công ty đáng 8 triệu → bạn nâng lên 12, lãi
         2; công ty đáng 4 triệu → nâng lên 6, lỗ 4
                                │
                                ▼
       Lối nghĩ phổ biến: trung bình 7 triệu × 1,5 = 10,5 triệu, nên trả
       tới 10,5 triệu vẫn hoà vốn → SAI
                                │
                                ▼
       Nếu chủ nhận 10,5 triệu, bạn biết ngay công ty KHÔNG đáng 11 hay 12
       triệu: giá trị nằm trong 2–10,5, trung bình 6,25; × 1,5 = 9,375,
       thấp hơn 10,5 đã trả
       · trả 8 triệu: khi được nhận, trung bình 5, × 1,5 = 7,5 < 8
       · trả 6 triệu: khi được nhận, trung bình 4, × 1,5 = 6 → HOÀ VỐN
       · Chú thích của tác giả: trả X thì giá trị trung bình khi được nhận
         là (2 + X)/2; hoà vốn khi X = 1,5 × (2 + X)/2, tức X = 6
                                │
                                ▼
       Việc người bán nói "đồng ý" là TIN XẤU nhưng không làm hỏng giao
       dịch nếu bạn đã tính trước; khi bị từ chối, bạn ước lượng thấp
       nhưng không mua nên sai lầm không gây hại
       · 6 triệu là MỨC TRẦN hoà vốn; hai tác giả khuyên trả thấp hơn
```

### Tiểu mục "Sealed-Bid Auctions" — đấu giá kín trả theo giá mình bỏ

```text
       Luật: bỏ giá trong phong bì kín; giá cao nhất thắng và trả ĐÚNG giá
       mình bỏ
                                │
                                ▼
       Không bao giờ bỏ bằng giá trị (hay cao hơn): tốt nhất chỉ hoà vốn;
       chiến lược đó bị trội bởi việc HẠ GIÁ BỎ (shading) xuống dưới giá
       trị
       · Chú thích của tác giả: trong đấu thầu thì ngược lại; chi phí làm
         đường 10 triệu USD thì không bao giờ bỏ thầu dưới 10 triệu, vì
         nếu thắng ở 9 triệu bạn đang "trải đường" tới phá sản
                                │
                                ▼
       Hạ bao nhiêu phụ thuộc vào người khác bỏ bao nhiêu, mà họ lại phụ
       thuộc vào bạn → vòng lặp vô tận; cách cắt vòng lặp: luôn bỏ giá
       NHƯ THỂ MÌNH ĐÃ THẮNG (giả định mọi người khác thấp hơn mình)
       · giả định sai thì không sao, vì khi đó bạn thua và không phải trả
                                │
                                ▼
       Chứng minh bằng "người đồng loã" trong nhà đấu giá, chỉ hạ được giá
       của bạn KHI bạn đang cao nhất (Bảng dựng lại từ sách):
       ┌──────────────────────────────┬──────────────────────┐
       │ Trường hợp A                 │ Trường hợp B         │
       ├──────────────────────────────┼──────────────────────┤
       │ Bỏ 100 USD; hạ xuống 80 USD  │ Bỏ 80 USD ngay từ đầu│
       │ nếu 100 là giá cao nhất      │                      │
       └──────────────────────────────┴──────────────────────┘
       · nếu 100 thua thì 80 cũng thua; nếu 100 thắng thì kết quả như bỏ
         80 → hai trường hợp như nhau, nên cứ bỏ 80 từ đầu
       → khi tính giá bỏ, hãy giả định mọi người khác thấp hơn mình
```

### Tiểu mục "Dutch Auctions" — đấu giá kiểu Hà Lan (kèm bài tập Trip to the Gym số 7)

```text
       Chợ đấu giá hoa Aalsmeer (Hà Lan): rộng khoảng 160 mẫu Anh (acre),
       mỗi ngày khoảng 14 triệu bông hoa và 1 triệu chậu cây đổi chủ
                                │
                                ▼
       ĐẤU GIÁ KIỂU HÀ LAN (Dutch auction): giá bắt đầu CAO rồi GIẢM dần
       theo đồng hồ (100, 99, 98...); người đầu tiên dừng đồng hồ thắng và
       trả đúng giá lúc dừng → ngược với đấu giá kiểu Nhật
                                │
                                ▼
       Dặn người đại diện "chờ giá hoa dạ yên thảo xuống 86,3 euro thì
       bỏ": nếu giá xuống tới đó, bạn biết mình thắng và mọi người khác
       còn chưa ra tay
       · chờ thêm thì lãi nhiều hơn nhưng rủi ro bị giành mất tăng lên;
         giá tối ưu là lúc phần tiết kiệm không còn bù được rủi ro đó
                                │
                                ▼
       Đấu giá Hà Lan TƯƠNG ĐƯƠNG đấu giá kín: lời dặn người đại diện
       giống con số viết vào phong bì; người ghi số cao nhất cũng là người
       giơ tay đầu tiên
       · khác biệt duy nhất: ở đấu giá Hà Lan, lúc bỏ giá bạn BIẾT mình
         thắng; ở đấu giá kín bạn phải GIẢ ĐỊNH mình thắng, đúng như lời
         khuyên ở trên
                                │
                                ▼
       TRIP TO THE GYM SỐ 7: hai người, giá trị của người kia phân bố đều
       từ 0 đến 100, người kia cũng nghĩ vậy về bạn; nên bỏ bao nhiêu?
       Đáp án của sách: bỏ MỘT NỬA giá trị
       · trong Vickrey, giá trị 60 mà thắng thì trung bình trả 30
       · đổi luật thành "bỏ X, thắng thì trả X/2": kết quả trung bình như
         Vickrey, nên không ai đổi giá bỏ
       · đổi tiếp thành "trả đúng giá bỏ": mọi người chia đôi giá bỏ
       · kiểm tra: người kia bỏ nửa giá trị; bạn bỏ X thì thắng với xác
         suất 2X/100; lợi ích (V − X) × 2X/100 lớn nhất khi X = V/2
```

### Tiểu mục "Dutch Auctions" (tiếp) — định lý tương đương doanh thu và cách tính giá bỏ

```text
       Đấu giá kiểu Anh và Vickrey cho cùng kết quả; đấu giá kín và Hà Lan
       cũng cho cùng kết quả, nhưng vẫn chưa biết nên bỏ bao nhiêu; hai tác
       giả gọi đây là "hai bí ẩn có cùng đáp án"
                                │
                                ▼
       ĐỊNH LÝ TƯƠNG ĐƯƠNG DOANH THU (revenue equivalence theorem): với
       giá trị riêng và trò chơi đối xứng, người bán thu trung bình như
       nhau dù dùng đấu giá kiểu Anh, Vickrey, Hà Lan hay đấu giá kín
       · Chú thích của tác giả: Roger Myerson chứng minh đầu tiên; người
         bỏ giá chỉ quan tâm trung bình phải trả bao nhiêu và khả năng
         thắng là bao nhiêu; góp phần mang lại giải Nobel 2007 cho ông
                                │
                                ▼
       Cân bằng Nash đối xứng của đấu giá kín và Hà Lan: bỏ đúng mức giá
       trị bạn đoán cho người cao thứ hai, VỚI GIẢ ĐỊNH bạn là người cao
       nhất
       · giá trị phân bố đều 0–100, giá trị của bạn là 60:
         1 đối thủ → bỏ 30; 2 đối thủ → bỏ 40; 3 đối thủ → bỏ 45
       · Chú thích của tác giả: các đối thủ được đoán là cách đều nhau
         giữa 0 và giá trị của bạn (2 người: 20 và 40; 3 người: 15, 30,
         45); càng đông người, giá bỏ càng sát giá trị, thị trường tiến
         tới cạnh tranh hoàn hảo và toàn bộ thặng dư về tay người bán
                                │
                                ▼
       Bài học lớn: luật chơi đặt ra thế nào, người chơi cũng có thể
       "hoá giải" bằng cách đổi con số mình bỏ
       · bắt trả gấp đôi giá bỏ → người ta bỏ một nửa
       · bắt trả bình phương giá bỏ → người ta lấy căn bậc hai
       · bắt trả giá của mình thay vì giá thứ hai → người ta hạ giá bỏ
         xuống mức giá trị cao thứ hai dự kiến
```

### Tiểu mục "T-Bills" — đấu giá tín phiếu Kho bạc Mỹ

```text
       Mỗi tuần Bộ Tài chính Mỹ đấu giá để định lãi suất phần nợ quốc gia
       đáo hạn tuần đó (cuộc đấu giá lớn nhất thế giới)
       · tới đầu thập niên 1990: người thắng nhận đúng lãi suất mình bỏ
       · sau khi Milton Friedman và các nhà kinh tế khác thúc đẩy: thử
         nghiệm GIÁ THỐNG NHẤT (uniform pricing) năm 1992, áp dụng hẳn năm
         1998 (Bộ trưởng khi đó là nhà kinh tế Larry Summers)
                                │
                                ▼
       Ví dụ: bán 100 triệu USD; Bộ Tài chính nhận lãi suất thấp nhất
       trước (Bảng dựng lại từ sách)
       ┌──────────────────────────────┬──────────────────────┐
       │ Số tiền bỏ, ở lãi suất       │ Cộng dồn             │
       ├──────────────────────────────┼──────────────────────┤
       │ 10 triệu USD ở 3,1%          │ 10 triệu USD         │
       │ 20 triệu USD ở 3,25%         │ 30 triệu USD         │
       │ 20 triệu USD ở 3,33%         │ 50 triệu USD         │
       │ 15 triệu USD ở 3,5%          │ 65 triệu USD         │
       │ 25 triệu USD ở 3,6%          │ 90 triệu USD         │
       │ 20 triệu USD ở 3,72%         │ 110 triệu USD        │
       │ 25 triệu USD ở 3,75%         │ 135 triệu USD        │
       │ 30 triệu USD ở 3,80%         │ 165 triệu USD        │
       │ 25 triệu USD ở 3,82%         │ 190 triệu USD        │
       └──────────────────────────────┴──────────────────────┘
       · thắng: mọi mức từ 3,1% tới 3,6% (90 triệu) và một nửa mức 3,72%
       · LUẬT CŨ: ai nhận đúng lãi suất người đó bỏ (3,1%, 3,25%...)
       · LUẬT MỚI: mọi người thắng nhận lãi suất cao nhất được chấp nhận,
         ở đây là 3,72%
       · Chú thích của tác giả: nhà đầu tư nhỏ có thể chỉ ghi số tiền,
         không ghi lãi suất, chắc chắn thắng và nhận lãi suất bình quân
         của những người thắng; ngân hàng đầu tư lớn không được dùng cách
         này
                                │
                                ▼
       Thoạt nhìn luật mới tốn hơn cho chính phủ; nhưng người chơi sẽ KHÔNG
       bỏ giống nhau dưới hai luật (định luật 3 Newton của lý thuyết trò
       chơi: có tác động thì có phản ứng)
       · nếu Bộ Tài chính trả bớt 1% so với mức bỏ, ai định bỏ 3,1% sẽ bỏ
         4,1%, và mọi thứ như cũ → phản ứng "bằng và ngược chiều"
                                │
                                ▼
       Kết luận: sau khi người bỏ giá điều chỉnh, Bộ Tài chính trả lãi như
       cũ, nhưng việc bỏ giá dễ hơn hẳn: người chấp nhận 3,33% cứ bỏ 3,33%
       và biết nếu thắng sẽ nhận ít nhất 3,33%
       · Chú thích của tác giả: đây chưa hẳn là đấu giá Vickrey nhiều đơn
         vị, vì mua thêm đơn vị có thể kéo lãi suất mình nhận trên mọi đơn
         vị xuống; muốn là Vickrey thật, mỗi người phải nhận lãi suất
         thắng cao nhất tính như thể mình không tham gia
```

### Tiểu mục "The Preemption Game" — trò chơi chiếm trước (kèm bài tập Trip to the Gym số 8)

```text
       Nhiều trò chơi không giống đấu giá nhưng thực chất là đấu giá
                                │
                                ▼
       Apple Newton (ra mắt 3/8/1993): phần mềm nhận dạng chữ viết tay do
       lập trình viên Liên Xô phát triển "không hiểu tiếng Anh"
       · phim The Simpsons: "Beat up Martin" thành "Eat up Martha"
       · tranh Doonesbury chế giễu (dựng lại ở dưới); Newton bị khai tử
         27/2/1998
       · tháng 3/1996 Jeff Hawkins tung Palm Pilot 1000, nhanh chóng đạt
         doanh số 1 tỷ USD/năm
       → nghịch lý: chờ sẵn sàng thì lỡ cơ hội, nhảy vào sớm thì thất bại
                                │
                                ▼
       USA Today: nước nào cũng có báo ngày toàn quốc (Le Monde, The
       Times, Asahi Shimbun, Nhân dân Nhật báo, Pravda...), riêng Mỹ chưa
       · 1982 Al Neuharth thuyết phục hội đồng quản trị Gannett ra báo
       · phải in ở nhiều nhà máy khắp nước, truyền trang màu qua vệ tinh,
         công nghệ mới tinh và đắt
       · mất 12 năm mới hoà vốn, lỗ hơn 1 tỷ USD
       · chờ vài năm thì công nghệ dễ hơn, nhưng thị trường chỉ đủ cho
         MỘT tờ, và Neuharth sợ Knight Ridder ra trước
                                │
                                ▼
       TRÒ CHƠI CHIẾM TRƯỚC: ai ra trước có cơ hội chiếm thị trường nếu
       thành công; giống một cuộc ĐẤU SÚNG
       · bắn sớm mà trượt, đối thủ tiến lên bắn chắc chắn trúng
       · chờ quá lâu, chết khi chưa bắn phát nào
       · Chú thích của tác giả: Ben Polak (Yale) minh hoạ bằng cuộc đấu
         với miếng bọt biển ướt: hai người đi dần lại gần, khi nào ném?
                                │
                                ▼
       Coi như đấu giá: "giá bỏ" là thời điểm bắn; ai bỏ thấp nhất được
       bắn trước, nhưng bỏ thấp thì xác suất trúng thấp
       · hai bên sẽ bắn CÙNG LÚC, kể cả khi tài bắn khác nhau
       · nếu bạn định bắn lúc 10, đối thủ lúc 8: đối thủ nên chờ tới 9,99
         để tăng xác suất trúng mà không bị bắn trước
                                │
                                ▼
       Thời điểm bắn: khi xác suất thành công của bạn bằng xác suất thất
       bại của đối thủ, tức lúc HAI XÁC SUẤT THÀNH CÔNG CỘNG LẠI BẰNG 1
       TRIP TO THE GYM SỐ 8 (đáp án của sách): xác suất trúng p(t) của
       bạn, q(t) của đối thủ; không ai muốn bắn trước khi p(t) ≤ 1 − q(t)
       và q(t) ≤ 1 − p(t), tức p(t) + q(t) ≤ 1; cả hai bắn khi tổng bằng 1
                                │
                                ▼
       Giới hạn của mô hình: giả định hai bên biết đúng xác suất của nhau,
       và thử rồi thất bại tệ ngang với để đối thủ đi trước rồi thắng
```

```text
       Tranh Doonesbury (dựng lại từ sách): một người viết lên máy Newton
       Ô 1: viết "I am writing a test sentence"
            máy đọc thành "Siam fighting atomic sentry"
       Ô 2: viết lại câu đó; máy đọc thành "Ian is riding a taste
            sensation"
       Ô 3: viết mạnh tay "I am writing a test sentence!!"; lần này máy
            đọc đúng "I am writing a test sentence!"
       Ô 4: hỏi "Catching on?" (Hiểu ra chưa?); máy đọc thành
            "Egg freckles?"
```

### Tiểu mục "The War of Attrition" — cuộc chiến tiêu hao

```text
       Ngược với chiếm trước: mục tiêu là TRỤ LÂU HƠN đối thủ; câu hỏi là
       ai bỏ cuộc trước
       · coi như đấu giá: giá bỏ là thời gian chịu lỗ; người cao nhất thắng
         nhưng MỌI NGƯỜI đều trả giá mình bỏ; có thể hợp lý khi bỏ cao hơn
         giá trị
                                │
                                ▼
       1986: British Satellite Broadcasting (BSB) giành giấy phép truyền
       hình vệ tinh chính thức ở Anh
       · khi đó chỉ có 4 kênh (hai kênh BBC, ITV, Channel 4)
       · 21 triệu hộ, thu nhập cao, mưa nhiều, gần như không có truyền
         hình cáp (Chú thích của tác giả: dưới 1% hộ thuê bao cáp; luật chỉ
         cho phép cáp ở nơi không thu được sóng phát thanh truyền hình)
       · kỳ vọng doanh thu 2 tỷ bảng/năm
                                │
                                ▼
       6/1988: Rupert Murdoch dùng vệ tinh Astra đặt trên Hà Lan phát bốn
       kênh vào Anh (Dallas, rồi Baywatch)
       · tranh nhau mua phim Hollywood, đua giảm giá quảng cáo
       · công nghệ hai bên không tương thích, nhiều người chờ xem ai thắng
         rồi mới mua chảo thu
       · sau một năm, hai hãng lỗ tổng cộng 1,5 tỷ bảng
                                │
                                ▼
       Vì sao chịu lỗ? Giải thưởng cho người trụ lại rất lớn; khoản đã lỗ
       (ví dụ 600 triệu bảng) không liên quan, vì bỏ hay tiếp thì cũng đã
       mất; chỉ hỏi chi phí trụ thêm có đáng với "hũ vàng" không
                                │
                                ▼
       Không có chiến lược bỏ giá tốt nhất duy nhất: nếu nghĩ đối thủ sắp
       bỏ thì nên trụ thêm, mà họ sắp bỏ vì họ nghĩ bạn sẽ trụ...
       · không có cơ chế kiểm tra sự nhất quán → cả hai có thể quá tự tin,
         dẫn tới bỏ giá quá cao và lỗ lớn cho cả hai
                                │
                                ▼
       Lời khuyên: trò chơi nguy hiểm; nước đi tốt nhất là thoả thuận
       · Murdoch sáp nhập với BSB vào phút chót; khả năng chịu lỗ quyết
         định tỷ lệ chia trong liên doanh; cả hai cùng nguy cơ sụp đổ nên
         chính phủ buộc phải cho phép hai hãng duy nhất sáp nhập
       · bài học thứ hai: đừng bao giờ đặt cược chống lại Murdoch
```

### Tiểu mục "Case Study: Spectrum Auctions" — tình huống: đấu giá phổ tần

```text
       "Mẹ của mọi cuộc đấu giá": bán phổ tần cho điện thoại di động
       · FCC (Mỹ) thu hơn 40 tỷ USD giai đoạn 1994–2005
       · Anh: đấu giá phổ tần 3G thu 22,5 tỷ bảng, cuộc đấu giá đơn lẻ lớn
         nhất mọi thời
                                │
                                ▼
       Phiên bản đơn giản hoá của cuộc đấu giá phổ tần đầu tiên ở Mỹ: hai
       người chơi AT&T và MCI, hai giấy phép NY và LA
       · bán lần lượt thì khó: bán NY trước, AT&T thích LA hơn nhưng vẫn
         phải tranh NY vì sợ trắng tay, rồi có thể hết ngân sách cho LA
       · FCC (với các nhà lý thuyết trò chơi) chọn ĐẤU GIÁ ĐỒNG THỜI: cả
         hai giấy phép cùng lên sàn, chia thành nhiều vòng
       · mỗi vòng, ai không đang giữ giá cao nhất ở một giấy phép thì có
         thể nâng giá ở đó; cuộc đấu chỉ kết thúc khi có một vòng không ai
         bỏ giá
                                │
                                ▼
       Minh hoạ luật (Bảng dựng lại từ sách), giá đã bỏ sau vòng 4:
                         NY     LA
              AT&T        6      7
              MCI         5      8
       · AT&T cao nhất ở NY, MCI cao nhất ở LA; vòng 5 chỉ AT&T bỏ giá:
                         NY     LA
              AT&T        6      9
              MCI         5      8
       · AT&T cao nhất ở cả hai nên không được bỏ; cuộc đấu chưa hết vì
         vòng trước có người bỏ; MCI không bỏ thì kết thúc, MCI bỏ 7 cho
         NY thì tiếp tục
                                │
                                ▼
       Giá trị (Bảng dựng lại từ sách), hai bên đều biết của nhau:
                         NY     LA
              AT&T       10      9
              MCI         9      8
       Người đọc chơi AT&T; hai tác giả chơi MCI
```

### Tiểu mục "Case Discussion" — thảo luận tình huống

```text
       Bỏ 10 cho NY và 9 cho LA: thắng cả hai nhưng lãi 0, giống bỏ 10 USD
       để thắng tờ 10 USD; là chiến lược bị trội (yếu)
       · "giá trị 10" nghĩa là ở giá 10 bạn thắng hay thua đều như nhau
                                │
                                ▼
       Bỏ 9 và 8: thắng cả hai (MCI không bỏ quá giá trị), lãi 1 + 1 = 2
                                │
                                ▼
       Thử bỏ 5 và 5; MCI mở đầu 0 cho NY, 1 cho LA
       · MCI không thể về tay trắng trừ khi giá đã lên 9 và 8, nên bỏ 6
         cho LA; bạn nâng LA lên 7, MCI chuyển sang NY với 6...
       · cuối cùng bạn thắng cả hai ở 9 hoặc 10 (NY), 8 hoặc 9 (LA):
         không hơn gì bỏ 9 và 8
                                │
                                ▼
       Chơi lại: khi MCI bỏ 6 cho LA, bạn (đang giữ NY ở 5) DỪNG lại
       → cuộc đấu kết thúc; bạn được NY ở giá 5, lãi 10 − 5 = 5, hơn 2
                                │
                                ▼
       Lần chơi cuối: bạn bỏ 1 cho NY, 0 cho LA; MCI bỏ 0 cho NY, 1 cho
       LA; vòng sau không ai bỏ → bạn được NY ở giá 1, LÃI 9
                                │
                                ▼
       Vì sao không tranh nốt LA? MCI sẽ đẩy giá tới 9 và 8 trước khi chịu
       về tay trắng; muốn lấy cả hai, bạn phải trả tổng 17; đang giữ NY ở
       giá 1, nên CHI PHÍ THẬT của giấy phép thứ hai là 16, vượt xa giá
       trị 9 của LA → thắng được cả hai không có nghĩa là nên làm vậy
                                │
                                ▼
       Có phải thông đồng? Nói chặt chẽ thì KHÔNG: không ai thoả thuận gì,
       mỗi bên hành động vì lợi ích riêng → HỢP TÁC NGẦM (tacit
       cooperation); người bán là bên thua lớn
       · người bán muốn tránh thì bán lần lượt: MCI không thể bỏ NY cho
         AT&T ở giá 1, vì AT&T vẫn sẽ tranh LA ở cuộc sau mà không sợ mất
         gì ở NY
                                │
                                ▼
       Bài học lớn: gộp hai trò chơi làm một tạo cơ hội dùng chiến lược
       xuyên qua cả hai
       · Fuji vào thị trường phim chụp ảnh Mỹ: Kodak có thể đáp trả ở Mỹ
         (tốn kém cho Kodak) hoặc ở Nhật (tốn kém cho Fuji, gần như không
         tốn gì cho Kodak vốn có thị phần nhỏ ở Nhật)
       → NGUYÊN TẮC: nếu không thích trò chơi đang chơi, hãy tìm trò chơi
         lớn hơn
       · Các tình huống đấu giá khác nằm ở Chương 14: "The Safer Duel",
         "The Risk of Winning", "What Price a Dollar?"
```

## Ba câu hỏi chương này trả lời

1. **Nên bỏ giá bao nhiêu trong từng loại đấu giá?** Trong đấu giá kiểu Anh, Nhật và Vickrey, cứ bỏ (hoặc theo) tới đúng giá trị thật, vì đó là chiến lược trội. Trong đấu giá kín trả theo giá mình bỏ và đấu giá kiểu Hà Lan, phải hạ giá bỏ xuống mức giá trị mà bạn đoán cho người cao thứ hai, với giả định mình là người cao nhất. Với hai người và giá trị phân bố đều từ 0 đến 100, người có giá trị 60 nên bỏ 30; có hai đối thủ thì bỏ 40; ba đối thủ thì bỏ 45.
2. **Làm sao tránh lời nguyền của người thắng?** Bỏ giá như thể mình đã thắng: hỏi xem nếu lời đề nghị được nhận thì điều đó cho biết gì về giá trị món đồ. Trong ví dụ ACME, công ty đáng từ 2 đến 12 triệu USD và người mua nâng được giá trị thêm 50%; trả theo trung bình (10,5 triệu) sẽ lỗ, vì khi được nhận thì công ty trung bình chỉ đáng 6,25 triệu, tức 9,375 triệu sau khi nâng cấp. Mức trần hoà vốn là 6 triệu.
3. **Thay đổi luật đấu giá có làm người bán thu nhiều hơn không?** Thường là không, vì người chơi điều chỉnh để bù trừ. Phí người mua 20% của Sotheby's thực ra trừ vào tiền người bán; Bộ Tài chính Mỹ chuyển từ trả theo lãi suất mỗi người bỏ sang lãi suất thống nhất mà không phải trả lãi cao hơn; với giá trị riêng và người chơi đối xứng, bốn thể thức đấu giá chính cho cùng doanh thu trung bình. Ngoại lệ quan trọng là khi luật mở ra cơ hội chiến lược mới, như đấu giá đồng thời nhiều giấy phép phổ tần cho phép AT&T và MCI hợp tác ngầm để mỗi bên lấy một giấy phép với giá 1.

## Khái niệm cần biết

**Đấu thầu mua sắm (procurement auction).** Đấu giá mà một người mua mời nhiều người bán cạnh tranh, người bỏ giá thấp nhất thắng. Ví dụ: chính quyền mời thầu làm một đoạn đường; nhà thầu có chi phí 10 triệu USD (đã gồm lợi nhuận bình thường) không bao giờ nên bỏ dưới 10 triệu. Hai tác giả gác loại này sang bên vì chất lượng của các nhà thầu khác nhau khiến giá thấp nhất chưa chắc là tốt nhất; trong chú thích, họ chỉ ra rằng lời khuyên hạ giá bỏ của đấu giá kín phải đảo ngược khi áp dụng cho đấu thầu.

**Giá trị, hay mức giá bỏ đi (value, walkaway number).** Mức giá cao nhất mà bạn vẫn muốn thắng; tại đúng mức đó, thắng hay thua với bạn là như nhau. Ví dụ: AT&T định giá giấy phép NY là 10, nghĩa là ở giá 9,99 hơi muốn thắng, ở 10,01 hơi muốn thua. Khái niệm này quan trọng vì mọi chiến lược trong chương được tính từ giá trị, và hai tác giả nhấn mạnh rằng thắng ở đúng giá trị là không lãi gì.

**Giá trị riêng và giá trị chung (private value, common value).** Giá trị riêng không phụ thuộc người khác nghĩ gì (cuốn sách có chữ ký tặng riêng bạn); giá trị chung là như nhau với mọi người nhưng mỗi người ước lượng khác nhau (lượng dầu dưới một lô khai thác ngoài khơi). Với giá trị chung, giá bỏ của người khác mang thông tin, nên thể thức đấu giá nào làm lộ thông tin sẽ tạo khác biệt; với giá trị riêng thì không. Định lý tương đương doanh thu trong chương dựa trên giả định giá trị riêng.

**Lời nguyền của người thắng (winner's curse).** Hiện tượng thắng đấu giá rồi phát hiện mình trả quá giá trị, vì chính việc thắng cho thấy người khác đánh giá món đồ thấp hơn mình. Ví dụ ACME: người trả 10,5 triệu USD theo giá trị trung bình sẽ lỗ, vì lời đề nghị chỉ được nhận khi công ty đáng dưới 10,5 triệu. Đây là cái bẫy mà Chương 1 và Chương 8 đã hứa sẽ chỉ cách tránh ở chương này.

**Bỏ giá như thể mình đã thắng (bidding as if you've won).** Nguyên tắc tư duy theo hệ quả: khi ra giá, hãy giả định tình huống mà giá của mình có tác dụng (mình thắng, đối phương nói "đồng ý") rồi hỏi giá đó có còn đúng không. Ví dụ: trả 6 triệu USD cho ACME thì khi được nhận, công ty trung bình đáng 4 triệu, nâng lên 6 triệu, vừa hoà vốn. Nguyên tắc này vừa tránh được lời nguyền của người thắng vừa cắt được vòng lặp "tôi đoán anh đoán tôi" trong đấu giá kín.

**Đấu giá kiểu Anh và kiểu Nhật (English auction, Japanese auction).** Hai dạng đấu giá tăng dần: kiểu Anh thì người điều hành hô giá và người chơi có thể im lặng rồi nhảy vào muộn; kiểu Nhật thì mọi người giơ tay từ đầu, giá tăng theo đồng hồ, hạ tay là rút hẳn. Ví dụ: bước giá 10 và giá trị 95 thì người chơi dừng ở 90. Cả hai cho kết quả người có giá trị cao nhất thắng và trả giá trị cao thứ hai.

**Đấu giá Vickrey (Vickrey auction, second-price auction).** Đấu giá phong bì kín, giá cao nhất thắng nhưng chỉ trả mức giá cao thứ hai. Ví dụ: giá trị của bạn 60, người khác bỏ 53; bỏ 60 thì thắng và trả 53, bỏ 50 thì thua. Bỏ đúng giá trị là chiến lược trội, nên người chơi không cần đoán gì về người khác; eBay với giá ủy nhiệm gần giống đấu giá này.

**Đấu giá kín trả theo giá mình bỏ (sealed-bid auction, first-price).** Phong bì kín, giá cao nhất thắng và trả đúng giá mình bỏ. Ví dụ: hai người, giá trị phân bố đều từ 0 đến 100, cân bằng là mỗi người bỏ một nửa giá trị. Người chơi phải hạ giá bỏ (bid shading) xuống dưới giá trị, nếu không thì tốt nhất chỉ hoà vốn.

**Đấu giá kiểu Hà Lan (Dutch auction).** Giá bắt đầu cao và giảm dần theo đồng hồ; người đầu tiên dừng đồng hồ thắng và trả giá lúc đó. Ví dụ: chợ hoa Aalsmeer, mỗi ngày khoảng 14 triệu bông hoa đổi chủ. Nó tương đương đấu giá kín, vì người dừng đồng hồ biết chắc mình đang cao nhất, đúng như giả định "đã thắng" mà người bỏ giá kín phải tự đặt ra.

**Định lý tương đương doanh thu (revenue equivalence theorem).** Kết quả do Roger Myerson chứng minh: với giá trị riêng và người chơi đối xứng, người bán thu trung bình như nhau dù dùng đấu giá kiểu Anh, Vickrey, Hà Lan hay đấu giá kín. Ví dụ: trong Vickrey, người giá trị 60 thắng (với một đối thủ) trả trung bình 30; trong đấu giá kín, người đó bỏ đúng 30. Ý nghĩa rộng hơn: người chơi điều chỉnh chiến lược để bù trừ cho thay đổi của luật.

**Phí người mua (buyer's premium).** Khoản nhà đấu giá cộng thêm vào giá thắng, ở Sotheby's và Christie's là 20%. Ví dụ: người sẵn sàng trả 600 USD sẽ chỉ bỏ 500 USD. Hai tác giả dùng nó để minh hoạ rằng gánh nặng thật của một khoản phí không nhất thiết rơi vào người được ghi tên phải trả.

**Giá ủy nhiệm và đặt giá phút chót (proxy bid, sniping).** Giá ủy nhiệm là mức tối đa bạn ủy quyền cho eBay bỏ thay; đặt giá phút chót là chờ tới những giây cuối mới đặt ủy nhiệm. Ví dụ: người định giá chiếc Porsche 19.000 USD chờ tới phút chót để những người đặt "giá lười" 1.000 USD không kịp tìm hiểu và nâng giá lên 9.000. Hiện tượng đặt giá phút chót cho thấy eBay không hoàn toàn là đấu giá Vickrey, vì giá ủy nhiệm đặt sớm làm lộ thông tin.

**Đấu giá giá thống nhất và trả theo giá bỏ (uniform-price auction, pay-your-bid auction).** Hai cách trả lãi trong đấu giá tín phiếu: mỗi người thắng nhận đúng lãi suất mình bỏ, hoặc mọi người thắng nhận lãi suất cao nhất được chấp nhận. Ví dụ: với cùng các mức bỏ, luật cũ trả từ 3,1% tới 3,72%, luật mới trả tất cả 3,72%; nhưng người chơi sẽ bỏ khác đi nên chính phủ không thiệt. Đây là ứng dụng thực tế lớn nhất của ý tưởng tương đương doanh thu trong chương.

**Trò chơi chiếm trước (preemption game).** Cuộc đọ sức mà người hành động trước có thể chiếm cả thị trường nếu thành công, nhưng hành động càng sớm thì xác suất thành công càng thấp. Ví dụ: Apple Newton ra quá sớm và thất bại; USA Today ra sớm, lỗ hơn 1 tỷ USD trong 12 năm nhưng giữ được thị trường chỉ đủ cho một tờ. Trong cân bằng, hai bên hành động cùng lúc, vào thời điểm tổng xác suất thành công của hai bên bằng 1.

**Cuộc chiến tiêu hao (war of attrition).** Cuộc đọ sức xem ai trụ lâu hơn; giống đấu giá mà mọi người đều trả giá mình bỏ (thời gian chịu lỗ) còn chỉ người cao nhất được giải. Ví dụ: BSB và Murdoch lỗ tổng cộng 1,5 tỷ bảng trong một năm. Không có chiến lược tốt nhất duy nhất, cả hai dễ quá tự tin, nên hai tác giả khuyên tìm thoả thuận.

**Hợp tác ngầm (tacit cooperation).** Kết quả mà các bên cùng có lợi (thường gây thiệt cho bên thứ ba, ở đây là người bán) mà không cần thoả thuận, vì mỗi bên tự thấy đó là lợi ích của mình. Ví dụ: AT&T lấy NY ở giá 1, MCI lấy LA ở giá 1, vì AT&T thấy giành thêm LA có chi phí thật là 16. Quan trọng vì nó giải thích tại sao người thiết kế đấu giá phải lường trước các chiến lược xuyên qua nhiều trò chơi cùng lúc.

## Nội dung chi tiết

### 1. Mở đầu: đấu giá để bán, đấu thầu để mua

Hai tác giả bắt đầu bằng hình ảnh quen thuộc của đấu giá trước đây: người điều hành nói giọng Anh kiểu cách trước một căn phòng yên lặng đầy nhà sưu tầm đeo trang sức, ngồi ghế kiểu Louis XIV và kéo tai để ra hiệu. eBay đã làm đấu giá trở nên đại chúng hơn một chút. Dạng quen thuộc nhất là một món đồ được đem bán và người trả cao nhất thắng: ở Sotheby's là tranh hay đồ cổ; trên eBay là hộp kẹo Pez, bộ trống cũ hay gần như mọi thứ (trừ quả thận); ở Google và Yahoo!, các cuộc đấu giá vị trí quảng cáo bên cạnh kết quả tìm kiếm theo từ khoá thu về hơn 10 tỷ USD; ở Úc, ngay cả nhà ở cũng bán bằng đấu giá. Điểm chung là một người bán, nhiều người mua cạnh tranh với nhau.

Nhưng đấu giá cũng dùng để mua. Khi chính quyền địa phương muốn làm đường, họ mời các nhà thầu bỏ giá, và người bỏ giá thấp nhất thắng vì chính quyền muốn mua dịch vụ trải đường rẻ nhất. Đó là đấu thầu mua sắm: một người mua, nhiều người bán.

> **Chú thích của tác giả:** Đấu thầu mua sắm phức tạp hơn vì các mức giá không cùng một "đơn vị". Trong đấu giá thường, nếu Avinash bỏ 20 USD và Barry bỏ 25 USD thì người bán biết 25 là tốt hơn. Nhưng trong đấu thầu, Avinash nhận làm đường với giá 20 USD chưa chắc tốt hơn Barry nhận 25 USD, vì chất lượng công trình có thể khác nhau. Điều này giải thích vì sao đấu giá ngược khó vận hành trên eBay. Giả sử bạn muốn mua một bộ trống Pearl Export, loại khá phổ biến trên eBay, lúc nào cũng có khoảng chục bộ đang bán. Muốn tổ chức đấu thầu, bạn phải cho tất cả người bán bỏ giá cạnh tranh, rồi mua bộ có giá thấp nhất (nếu thấp hơn mức giá tối đa của bạn). Vấn đề là bạn có thể quan tâm tới màu sắc, tuổi của bộ trống, hay uy tín giao hàng đúng hẹn của người bán, nên giá thấp nhất chưa chắc là tốt nhất. Nhưng nếu bạn không luôn chọn giá thấp nhất thì người bán không biết phải bỏ thấp tới đâu mới thắng. Một giải pháp, thường hay trên lý thuyết hơn thực tế, là đặt tiêu chuẩn chất lượng tối thiểu; nhưng khi đó nhà thầu làm tốt hơn mức tối thiểu thường không được thưởng trong giá bỏ của họ. Vì những phức tạp này, chương tập trung vào đấu giá bán thông thường.

Hai tác giả nhấn mạnh rằng bỏ giá cần chiến lược, dù nhiều người nghĩ chỉ cần một tấm thẻ để giơ lên; người bỏ giá theo cảm xúc hay sự hào hứng thường hối hận. Các câu hỏi chiến lược gồm: nên bỏ sớm hay chờ tới gần cuối mới nhảy vào; nếu món đồ đáng 100 USD với bạn thì nên bỏ tới đâu; làm sao tránh thắng rồi mới thấy mình trả quá đắt, hiện tượng gọi là lời nguyền của người thắng. Thậm chí có nên tham gia không: thị trường nhà đấu giá ở Úc cho thấy thế khó của người mua. Giả sử bạn quan tâm một căn nhà sẽ đấu giá ngày 1/7, nhưng có một căn bạn thích hơn sẽ đấu giá một tuần sau; nếu chờ căn thứ hai, bạn có thể mất cả hai.

### 2. Đấu giá kiểu Anh và kiểu Nhật (English and Japanese Auctions)

Dạng nổi tiếng nhất là đấu giá kiểu Anh, hay đấu giá tăng dần: người điều hành đứng trước phòng và hô giá ngày càng cao ("Có ai 30 không? 30 từ quý bà đội mũ hồng. 40? Vâng, 40 từ quý ông bên trái tôi. Có ai 50 không? 40 lần một, lần hai, bán"). Chiến lược tối ưu đơn giản tới mức khó gọi là chiến lược: cứ bỏ giá cho tới khi giá vượt giá trị của mình thì rút. Có một chút rắc rối với bước giá: nếu giá tăng theo bậc 10 và giá trị của bạn là 95, bạn sẽ dừng ở 90; biết vậy, bạn có thể phải tính xem nên là người giữ giá cao nhất ở 70 hay ở 80. Trong phần còn lại, hai tác giả giả định bước giá rất nhỏ (ví dụ 1 xu) để bỏ qua những chuyện cuối cuộc đấu này.

Phần khó duy nhất là hiểu "giá trị" nghĩa là gì. Đó là mức giá bỏ đi: mức cao nhất mà bạn vẫn muốn thắng. Cao hơn một đô la thì bạn thà bỏ qua; thấp hơn một đô la thì bạn sẵn lòng trả, nhưng chỉ vừa đủ. Giá trị có thể gồm phần bù để món đồ không rơi vào tay đối thủ, niềm vui chiến thắng, hay giá bán lại dự kiến. Gộp tất cả lại, đó là con số mà nếu phải trả đúng bằng nó thì bạn không còn quan tâm mình thắng hay thua.

Giá trị có hai loại. Với giá trị riêng, giá trị của bạn hoàn toàn không phụ thuộc người khác nghĩ gì: giá trị của một cuốn *The Art of Strategy* có chữ ký tặng riêng bạn không phụ thuộc vào việc hàng xóm định giá nó ra sao. Với giá trị chung, mọi người hiểu món đồ có cùng giá trị với tất cả, dù mỗi người có ước lượng khác nhau về giá trị chung đó; ví dụ chuẩn là đấu giá quyền khai thác một lô dầu ngoài khơi, nơi lượng dầu dưới đất là như nhau dù Exxon hay Shell thắng. Thực tế thường lẫn cả hai: một hãng khai thác giỏi hơn hãng kia sẽ thêm phần giá trị riêng vào một món chủ yếu mang giá trị chung.

Khi có giá trị chung, ước lượng tốt nhất của bạn có thể phụ thuộc vào ai khác đang bỏ giá, bao nhiêu người, và họ rút lúc nào. Đấu giá kiểu Anh giấu những thông tin đó: bạn không biết ai sẵn lòng bỏ mà chưa lên tiếng, cũng không chắc khi nào ai đó đã rút; bạn biết giá cuối của họ nhưng không biết họ sẵn sàng lên tới đâu.

Đấu giá kiểu Nhật minh bạch hơn. Mọi người bắt đầu với tay giơ lên (hoặc nút bấm đang nhấn), giá tăng theo đồng hồ, ví dụ từ 30 lên 31, 32 và cao hơn. Còn giơ tay là còn tham gia; hạ tay là rút, và đã hạ thì không được giơ lại. Cuộc đấu kết thúc khi chỉ còn một người. Ưu điểm là luôn biết rõ còn bao nhiêu người chơi và từng người rút ở giá nào, không ai có thể im lặng rồi bất ngờ nhảy vào muộn. Đấu giá kiểu Nhật giống đấu giá kiểu Anh trong đó ai cũng buộc phải lộ bài.

Kết quả của đấu giá kiểu Nhật dễ đoán. Vì mọi người rút khi giá chạm giá trị của mình, người còn lại cuối cùng là người có giá trị cao nhất, và giá phải trả bằng giá trị cao thứ hai, vì cuộc đấu kết thúc đúng lúc người áp chót rút. Món đồ về tay người coi trọng nó nhất, còn người bán nhận số tiền bằng giá trị cao thứ hai.

### 3. Đấu giá Vickrey (Vickrey Auction)

Năm 1961, William Vickrey, nhà kinh tế Đại học Columbia và sau này đoạt giải Nobel, đề xuất một loại đấu giá khác mà ông gọi là đấu giá giá thứ hai; nay người ta gọi là đấu giá Vickrey để vinh danh ông.

> **Chú thích của tác giả:** Bài báo nền tảng của Vickrey là "Counterspeculation, Auctions, and Competitive Sealed Tenders", *Journal of Finance* 16 (1961). Vickrey là người đầu tiên nghiên cứu đấu giá giá thứ hai, nhưng việc sử dụng nó có từ ít nhất thế kỷ 19, khi giới sưu tầm tem dùng nó. Thậm chí có bằng chứng Goethe đã dùng đấu giá giá thứ hai năm 1797 khi bán bản thảo cho một nhà xuất bản (theo bài "Goethe's Second-Price Auction" của Benny Moldovanu và Manfred Tietzel, *Journal of Political Economy*, 1998).

Trong đấu giá Vickrey, mọi người bỏ giá vào phong bì kín; khi mở, giá cao nhất thắng, nhưng người thắng không trả giá mình bỏ mà chỉ trả mức giá cao thứ hai. Điều đáng chú ý, gần như kỳ diệu, là mọi người chơi đều có chiến lược trội: bỏ đúng giá trị thật. Trong đấu giá kín thông thường (người thắng trả đúng giá mình bỏ), bỏ giá là bài toán phức tạp: phải tính có bao nhiêu người chơi, họ định giá món đồ ra sao, thậm chí họ nghĩ bạn định giá ra sao. Trong đấu giá Vickrey, bạn chỉ cần biết món đồ đáng bao nhiêu với mình rồi ghi đúng con số đó; hai tác giả đùa rằng, tiếc cho họ, bạn không cần thuê nhà lý thuyết trò chơi giúp mình bỏ giá. Hai tác giả nói họ thích kết quả này, vì mục tiêu của họ là tính toán chiến lược khi thiết kế trò chơi để người chơi không phải tính toán chiến lược khi chơi. Chiến lược trội là nước đi tốt nhất bất kể người khác làm gì, nên bạn không cần biết có bao nhiêu người hay họ nghĩ gì.

Để chứng minh, hai tác giả lấy ví dụ: giá trị thật của bạn là 60 USD nhưng bạn bỏ 50 USD. Theo cách tư duy theo hệ quả, câu hỏi cần đặt ra là: khi nào bỏ 50 thay vì 60 dẫn tới kết quả khác? Hai tác giả đảo câu hỏi lại cho dễ trả lời: khi nào bỏ 50 hay 60 cho cùng một kết quả?

| Giá cao nhất của những người khác | Bỏ 50 USD | Bỏ 60 USD | Có khác biệt không |
|---|---|---|---|
| Trên 60 (ví dụ 63 hoặc 70) | Thua, ra về tay trắng | Thua, ra về tay trắng | Không |
| Dưới 50 (ví dụ 43) | Thắng, trả 43 | Thắng, trả 43 | Không; bỏ 50 không tiết kiệm được đồng nào |
| Giữa 50 và 60 (ví dụ 53) | Thua | Thắng, trả 53, lãi 7 | Có; bỏ 50 làm bạn mất món hời |

Trường hợp duy nhất mà bỏ 50 cho kết quả khác bỏ 60 là khi bạn thua trong lúc lẽ ra muốn thắng. Vậy không bao giờ nên bỏ thấp hơn giá trị thật. Lập luận tương tự cho thấy cũng không bao giờ nên bỏ cao hơn giá trị thật (bỏ cao hơn chỉ tạo khác biệt khi bạn thắng mà phải trả quá giá trị).

**Bài tập Trip to the Gym số 6.** Giả sử trước khi bỏ giá trong đấu giá Vickrey, bạn có thể biết những người khác bỏ bao nhiêu. Tạm gác chuyện đạo đức, thông tin đó đáng bao nhiêu với bạn?

**Đáp án của sách (phần Workouts):** Bạn không sẵn lòng trả gì cả để biết giá của người khác, vì bỏ đúng giá trị là chiến lược trội trong đấu giá Vickrey, nên bạn sẽ bỏ cùng một mức dù biết người khác làm gì. Có một lưu ý: lập luận này giả định giá trị là riêng của bạn, không bị ảnh hưởng bởi việc người khác định giá ra sao. Trong đấu giá Vickrey giá trị chung, bạn có thể muốn đổi giá bỏ theo hành động của người khác, nhưng chỉ vì thông tin đó làm thay đổi ước lượng của bạn về giá trị món đồ.

### 4. Tương đương doanh thu (Revenue Equivalence) và phí người mua (Buyer's Premium)

Đấu giá Vickrey đưa tới cùng kết quả như đấu giá kiểu Anh (hoặc Nhật), chỉ trong một bước. Trong đấu giá kiểu Anh, mọi người bỏ tới giá trị của mình, nên cuộc đấu dừng khi giá lên tới giá trị cao thứ hai; người còn lại có giá trị cao nhất và (trừ sai lệch do bước giá) trả đúng mức giá mà người áp chót rút, tức giá trị cao thứ hai. Trong đấu giá Vickrey, mọi người bỏ đúng giá trị, nên người có giá trị cao nhất thắng và theo luật chỉ trả giá cao thứ hai, cũng chính là giá trị cao thứ hai. Cùng người thắng, cùng giá phải trả. Vẫn có chuyện bước giá: người có giá trị 95 có thể rút ở 90 nếu giá tăng theo bậc 10, nhưng với bước giá đủ nhỏ thì người đó rút đúng tại giá trị của mình.

Có một khác biệt tinh tế. Trong đấu giá kiểu Anh, người chơi biết được phần nào người khác định giá món đồ bao nhiêu qua các giá họ bỏ (dù có nhiều giá tiềm năng không được bỏ ra). Trong đấu giá kiểu Nhật, người chơi biết còn nhiều hơn: ai rút ở đâu đều được thấy. Trong đấu giá Vickrey, người thắng không biết gì về giá của người khác cho tới khi kết thúc. Nhưng với giá trị riêng, người chơi không quan tâm người khác định giá ra sao, nên thông tin thêm là vô dụng. Vì vậy, với giá trị riêng, người bán thu cùng một số tiền dù dùng đấu giá Vickrey hay đấu giá kiểu Anh (hoặc Nhật). Đây là một phần của một kết quả tổng quát hơn nhiều: trong nhiều trường hợp, đổi luật không làm người bán thu nhiều hơn hay ít hơn.

**Phí người mua.** Nếu bạn thắng ở Sotheby's hay Christie's, bạn có thể ngạc nhiên khi phải trả nhiều hơn giá đã bỏ, và không chỉ vì thuế bán hàng: nhà đấu giá cộng thêm 20% phí người mua. Thắng với giá 1.000 USD thì phải viết séc 1.200 USD. Ai trả khoản phí này? Câu trả lời hiển nhiên là người mua, nhưng hai tác giả nói nếu hiển nhiên vậy thì họ đã không hỏi. Người trả thật là người bán. Điều kiện duy nhất là người mua biết luật này và tính tới nó khi bỏ giá. Một nhà sưu tầm sẵn lòng trả 600 USD sẽ chỉ bỏ tối đa 500 USD, vì biết nói 500 nghĩa là phải trả 600 sau phí. Phí người mua giống như quy đổi tiền tệ hay một mật mã: nói 100 nghĩa là 120, và ai cũng thu nhỏ giá bỏ tương ứng.

> **Chú thích của tác giả:** Có thể hình dung trò chơi này như cuộc đấu giá tổ chức ở New York nhưng hô giá bằng euro: người nói "500 euro" biết mình sẽ trả 600 USD. Rõ ràng đổi đơn vị tiền tệ để hô giá không thể làm nhà đấu giá thu thêm tiền. Nếu Sotheby's tuyên bố phiên đấu giá thứ Hai sẽ tiến hành bằng euro, ai cũng tự quy đổi giá bỏ sang đô la (hay yên). Họ hiểu chi phí thật của việc hô "100", bất kể đơn vị là gì.

Nếu giá thắng là 100 USD, bạn viết séc 120 USD. Bạn không quan tâm 120 được chia thành 100 cho người bán và 20 cho nhà đấu giá; bạn chỉ quan tâm bức tranh tốn 120. Có thể hình dung người bán nhận đủ 120 rồi chuyển 20 cho nhà đấu giá. Người thắng vẫn trả cùng tổng số tiền; khác biệt duy nhất là nhà đấu giá lấy một phần trong tổng đó, nên chi phí rơi hoàn toàn vào người bán. Bài học rộng hơn: bạn có thể đổi luật chơi, nhưng người chơi sẽ điều chỉnh chiến lược theo luật mới, và trong nhiều trường hợp họ bù trừ chính xác điều bạn đã làm.

### 5. Đấu giá trực tuyến (Online Auctions) và đặt giá phút chót (Sniping)

Đấu giá Vickrey có thể có từ thời Goethe nhưng đến gần đây vẫn hiếm; nay nó thành chuẩn cho đấu giá trực tuyến. Trên eBay, bạn không bỏ giá trực tiếp mà đặt giá ủy nhiệm, tức ủy quyền cho eBay bỏ giá thay bạn tới mức đó. Nếu bạn ủy nhiệm 100 USD và giá cao nhất hiện tại là 12, eBay bỏ 13 cho bạn; nếu thế là đủ thắng thì dừng. Nếu người khác đã ủy nhiệm 26, eBay bỏ tới 26 cho người đó và đẩy giá của bạn lên 27.

Trông giống hệt đấu giá Vickrey: giá ủy nhiệm như giá trong phong bì, người ủy nhiệm cao nhất thắng và trả bằng giá ủy nhiệm cao thứ hai. Ví dụ có ba giá ủy nhiệm:

| Người | Giá ủy nhiệm |
|---|---|
| A | 26 USD |
| B | 33 USD |
| C | 100 USD |

A rút khi giá lên 26; B đẩy giá lên mức đó; C đẩy tiếp lên 34. C thắng và trả theo giá ủy nhiệm cao thứ hai. Nếu mọi người phải nộp giá ủy nhiệm cùng lúc và chỉ một lần, trò chơi sẽ đúng là đấu giá Vickrey và lời khuyên là bỏ đúng giá trị; nói thật là chiến lược trội.

Nhưng trò chơi thực tế không diễn ra như vậy, và những "trục trặc nhỏ" khiến người ta bỏ giá cầu kỳ. Một là eBay thường có nhiều món tương tự bán cùng lúc: muốn mua một bộ trống Pearl Export cũ, bạn có khoảng mười bộ để chọn. Bạn có thể muốn mua bộ nào rẻ nhất với giá tối đa 400 USD; dù sẵn lòng trả 400 cho bất kỳ bộ nào, bạn sẽ không bỏ 300 cho bộ này khi bộ kia có thể mua được với 250. Bạn cũng có thể thích cuộc đấu kết thúc sớm hơn cuộc đấu kéo dài một tuần, để biết ngay mình thắng hay chưa. Rốt cuộc, giá trị của bạn phụ thuộc vào những gì khác đang và sẽ được bán, nên không thể định giá độc lập với cuộc đấu.

**Đặt giá phút chót.** Xét trường hợp không có chuyện nhiều món hay thời điểm: một món đồ độc nhất. Có lý do gì để không đặt đúng giá trị làm giá ủy nhiệm? Thực tế là người ta không làm vậy. Họ thường chờ tới phút cuối, thậm chí giây cuối, mới đặt giá ủy nhiệm tốt nhất; việc này gọi là sniping. Có cả dịch vụ trên mạng như Bidnapper làm thay để bạn khỏi phải ngồi chờ tới lúc kết thúc.

Vì bỏ đúng giá trị là chiến lược trội trong đấu giá Vickrey, việc đặt giá phút chót phải bắt nguồn từ khác biệt tinh tế giữa ủy nhiệm và Vickrey. Khác biệt then chốt là người khác có thể biết điều gì đó từ giá ủy nhiệm của bạn trước khi cuộc đấu kết thúc. Nếu điều họ biết ảnh hưởng tới cách họ bỏ giá, bạn có lý do giấu giá của mình, kể cả giá ủy nhiệm. Ví dụ: nếu một nhà buôn đồ nội thất bỏ giá cho một chiếc ghế Bauhaus cụ thể, bạn có thể (khá hợp lý) suy ra chiếc ghế là đồ thật và có giá trị lịch sử. Nếu nhà buôn sẵn lòng mua ở 1.000 USD thì bạn vui lòng trả 1.200, vẫn rẻ hơn mức bạn có thể mua lại từ chính nhà buôn đó. Vì vậy nhà buôn không muốn người khác biết mình sẵn lòng lên tới đâu, và chờ tới tận cuối mới bỏ giá; lúc đó bạn và người khác không kịp phản ứng. Tất nhiên điều này đòi hỏi danh tính người bỏ giá bị người khác biết và người đó không dùng được tên giả.

> **Chú thích của tác giả:** Tạo tên giả thì dễ, nhưng nếu người bỏ giá không có lịch sử giao dịch, người bán có thể ngần ngại chấp nhận giá của họ.

Vì đặt giá phút chót quá phổ biến, hẳn phải còn lời giải thích khác. Theo hai tác giả, lời giải thích tốt nhất là nhiều người không biết giá trị của chính mình. Lấy ví dụ một chiếc Porsche 911 đời cũ, giá khởi điểm 1 USD. Hai tác giả tất nhiên không định giá nó 1 USD; họ định giá nó 100, thậm chí 1.000 USD. Chừng nào giá còn dưới 1.000 thì họ chắc chắn đó là món hời, không cần tra giá tham khảo trong sổ Blue Book hay bàn với vợ về nhu cầu có thêm xe. Ý là người ta lười: tìm ra giá trị thật tốn công, và nếu thắng được mà không phải bỏ công thì họ chọn đường tắt.

Đây là chỗ đặt giá phút chót phát huy tác dụng. Giả sử một người mua am hiểu định giá chiếc Porsche 19.000 USD. Người này muốn giữ giá thấp càng lâu càng tốt. Nếu đặt ủy nhiệm 19.000 ngay từ đầu, giá ủy nhiệm "vô tâm" 1.000 USD của hai tác giả sẽ đẩy giá lên ngay 1.000. Khi đó họ biết mình cần tìm hiểu thêm, và trong quá trình đó, vợ có thể đồng ý cho bỏ tới 9.000; giá cuối có thể lên 9.000 hoặc cao hơn nếu những người khác cũng kịp tìm hiểu. Nhưng nếu người định giá 19.000 "giữ thuốc súng khô" (chờ thời), giá có thể không vượt 1.000 cho tới những giây cuối, khi đã quá muộn để người khác đặt giá cao hơn, giả sử họ còn đang để ý và kịp xin vợ đồng ý. Lý do để đặt giá phút chót là giữ người khác trong bóng tối về giá trị của chính họ: bạn không muốn họ biết giá lười của họ không có cơ hội thắng. Nếu họ biết sớm, họ sẽ tìm hiểu, và điều đó chỉ khiến bạn phải trả nhiều hơn, nếu bạn vẫn thắng.

### 6. Bỏ giá như thể mình đã thắng (Bidding as If You've Won) và trò chơi ACME

Một ý tưởng mạnh của lý thuyết trò chơi là hành động theo kiểu người tư duy theo hệ quả (consequentialist): nhìn trước xem hành động của mình tạo ra hệ quả ở tình huống nào, rồi coi tình huống đó là tình huống liên quan ngay từ lúc ra quyết định. Quan điểm này rất quan trọng trong đấu giá và trong đời, và là công cụ chính để tránh lời nguyền của người thắng.

Hai tác giả minh hoạ bằng lời cầu hôn. Người được hỏi có thể nói đồng ý hoặc không. Nếu không, chẳng có gì phải làm tiếp; nếu đồng ý, bạn sắp kết hôn. Vì vậy khi ngỏ lời, bạn nên giả định câu trả lời là đồng ý. Đây là cách nhìn lạc quan, và người kia có thể từ chối làm bạn rất thất vọng; nhưng lý do giả định "đồng ý" là để chuẩn bị cho kết quả đó, và khi ấy bạn cũng phải đang nói đồng ý. Nếu nghe người kia đồng ý mà bạn lại muốn nghĩ lại, thì lẽ ra bạn không nên hỏi. Trong cầu hôn, giả định câu trả lời là đồng ý khá tự nhiên; trong đàm phán và đấu giá, đây là cách nghĩ phải học.

**Trò chơi ACME.** Bạn là người có thể mua công ty ACME. Nhờ hiểu biết sâu về lý thuyết trò chơi, bạn sẽ làm tăng giá trị ACME thêm 50%, dù giá trị hiện tại là bao nhiêu. Vấn đề là bạn không chắc giá trị hiện tại. Sau khi thẩm định, bạn ước lượng nó nằm trong khoảng từ 2 đến 12 triệu USD, mọi mức trong khoảng đó đều có khả năng như nhau, trung bình 7 triệu. Bạn chỉ được đưa một lời đề nghị "nhận hoặc thôi"; chủ sở hữu sẽ nhận bất kỳ giá nào cao hơn giá trị hiện tại và từ chối nếu không. Ví dụ, bạn trả 10 triệu: nếu công ty hiện đáng 8 triệu, bạn nâng lên 12 triệu và lãi 2 triệu; nếu công ty chỉ đáng 4 triệu, bạn nâng lên 6 triệu nhưng đã trả 10 triệu, lỗ 4 triệu. Câu hỏi: mức cao nhất bạn có thể đề nghị mà vẫn hoà vốn trung bình (không phải lãi trong mọi trường hợp, mà trung bình không lãi không lỗ) là bao nhiêu? Hai tác giả lưu ý họ không khuyên bỏ đúng mức này, bạn luôn nên bỏ thấp hơn; đây chỉ là cách tìm mức trần.

Phần lớn người ta lập luận: trung bình công ty đáng 7 triệu, tôi nâng thêm 50% thành 10,5 triệu, vậy trả tới 10,5 triệu vẫn không lỗ. Hai tác giả hy vọng bạn không ra con số đó. Hãy nghĩ lại chuyện cầu hôn: nếu họ đồng ý thì sao? Nếu bạn trả 10,5 triệu và chủ đồng ý, bạn vừa biết một tin xấu: công ty hiện không đáng 11 hay 12 triệu.

| Lời đề nghị | Giá trị hiện tại khi được nhận | Trung bình | Sau khi tăng 50% | So với giá trả |
|---|---|---|---|---|
| 10,5 triệu USD | 2 đến 10,5 triệu | 6,25 triệu | 9,375 triệu | Lỗ 1,125 triệu |
| 8 triệu USD | 2 đến 8 triệu | 5 triệu | 7,5 triệu | Lỗ 0,5 triệu |
| 6 triệu USD | 2 đến 6 triệu | 4 triệu | 6 triệu | Hoà vốn |

Có vẻ như nếu họ đồng ý thì bạn lại không còn muốn mua. Cách giải quyết là giả định lời đề nghị của mình sẽ được nhận. Việc người bán nói đồng ý là tin xấu nhưng không làm hỏng giao dịch; bạn chỉ cần hạ giá đề nghị để tính tới hoàn cảnh mà người bán chịu nói đồng ý. Nếu trả 6 triệu và giả định được nhận, bạn dự đoán công ty chỉ đáng 4 triệu và sẽ không thất vọng khi được nhận.

> **Chú thích của tác giả:** Cách tính ra 6 triệu: nếu lời đề nghị X được nhận thì giá trị của người bán nằm trong khoảng từ 2 tới X, trung bình (2 + X)/2. Bạn làm công ty đáng thêm 50%, tức gấp 1,5 lần giá trị ban đầu. Hoà vốn nghĩa là giá X bằng (3/2) × (2 + X)/2, tức 4X = 3(2 + X), hay X = 6. Kiểm tra rằng 6 là đáp án thì dễ hơn tự tìm ra con số.

Thường thì lời đề nghị sẽ bị từ chối, khi đó bạn đã đánh giá thấp giá trị công ty, nhưng vì bạn không mua nên sai lầm đó không quan trọng. Ý tưởng giả định mình đã thắng là thành phần then chốt để bỏ giá đúng trong đấu giá kín.

### 7. Đấu giá kín (Sealed-Bid Auctions)

Luật đấu giá kín rất đơn giản: mọi người bỏ giá vào phong bì kín, mở ra, giá cao nhất thắng và trả đúng giá mình bỏ. Phần khó là quyết định bỏ bao nhiêu. Trước hết, không bao giờ bỏ bằng giá trị của mình (càng không bỏ cao hơn): làm vậy thì tốt nhất chỉ hoà vốn. Chiến lược đó bị trội bởi việc hạ giá bỏ xuống dưới giá trị, vì ít nhất bạn còn có cơ hội có lãi.

> **Chú thích của tác giả:** Trong đấu thầu mua sắm, lời khuyên này đảo ngược. Giả sử bạn bỏ thầu một hợp đồng xây một đoạn đường cao tốc, chi phí của bạn (đã gồm lợi nhuận bình thường bạn đòi hỏi trên vốn đầu tư) là 10 triệu USD. Bạn không bao giờ nên bỏ thầu thấp hơn chi phí. Chẳng hạn bỏ 9 triệu: nếu không thắng thì không khác gì, nhưng nếu thắng thì bạn được trả thấp hơn chi phí, và bạn đang "trải đường" tới phá sản của chính mình.

Hạ giá bao nhiêu phụ thuộc vào có bao nhiêu người cạnh tranh và bạn đoán họ bỏ bao nhiêu; nhưng họ bỏ bao nhiêu lại phụ thuộc vào họ đoán bạn bỏ bao nhiêu. Bước then chốt để cắt vòng lặp kỳ vọng vô tận đó là luôn bỏ giá như thể mình đã thắng: khi ghi giá, hãy giả định mọi người khác đều thấp hơn mình, rồi với giả định đó hỏi đây có phải giá tốt nhất không. Bạn sẽ thường sai khi giả định vậy, nhưng khi sai thì không sao, vì người khác đã bỏ cao hơn và bạn không thắng; còn khi đúng, bạn là người thắng và giả định của bạn chính xác.

Hai tác giả chứng minh bằng một thí nghiệm tưởng tượng. Bạn có một người đồng loã trong nhà đấu giá, người này có thể hạ giá của bạn nếu bạn đang có giá cao nhất. Tiếc là anh ta không biết giá của người khác nên không thể bảo bạn hạ chính xác bao nhiêu, và nếu bạn không có giá cao nhất thì anh ta không giúp được gì. Bạn có thể không muốn dùng dịch vụ này vì nó phi đạo đức, hoặc vì sợ biến giá thắng thành giá thua. Nhưng cứ giả sử bạn dùng: giá ban đầu của bạn là 100 USD, và khi biết đó là giá thắng, bạn bảo anh ta hạ xuống 80.

Bảng dựng lại từ sách:

| Trường hợp A | Trường hợp B |
|---|---|
| Bỏ 100 USD; hạ xuống 80 USD nếu 100 là giá cao nhất | Bỏ 80 USD ngay từ đầu |

Nếu 100 lẽ ra thua thì 100 hay 80 đều là giá thua. Nếu 100 lẽ ra thắng thì người đồng loã hạ xuống 80, và bạn ở đúng vị trí như khi bỏ 80 từ đầu. Bỏ 100 rồi hạ xuống 80 khi thắng không có lợi gì hơn bỏ 80 từ đầu; vì có thể đạt cùng kết quả mà không cần người đồng loã và không phi đạo đức, bạn cứ bỏ 80 từ đầu. Tóm lại, khi tính bỏ bao nhiêu, hãy giả định mọi người khác ở đâu đó dưới giá của bạn, rồi với giả định đó tìm giá tốt nhất. Hai tác giả hẹn quay lại cách tính cụ thể sau một "đường vòng" qua Hà Lan.

### 8. Đấu giá kiểu Hà Lan (Dutch Auctions) và định lý tương đương doanh thu

Cổ phiếu giao dịch ở Sở Giao dịch Chứng khoán New York, đồ điện tử bán ở khu Akihabara (Tokyo), còn hoa thì cả thế giới tới Hà Lan để mua. Chợ đấu giá hoa Aalsmeer rộng khoảng 160 mẫu Anh (acre); một ngày bình thường có khoảng 14 triệu bông hoa và một triệu chậu cây đổi chủ. Điều làm Aalsmeer và các cuộc đấu giá kiểu Hà Lan khác Sotheby's là giá đi ngược: thay vì bắt đầu thấp rồi tăng dần, cuộc đấu bắt đầu ở giá cao rồi giảm. Hãy hình dung một đồng hồ bắt đầu ở 100 rồi chạy xuống 99, 98 và tiếp tục; người đầu tiên dừng đồng hồ thắng và trả đúng giá lúc dừng. Đây là đảo ngược của đấu giá kiểu Nhật: ở kiểu Nhật, mọi người báo tham gia và giá tăng cho tới khi còn một người; ở kiểu Hà Lan, giá bắt đầu cao và giảm cho tới khi người đầu tiên báo tham gia. Giơ tay trong đấu giá Hà Lan là cuộc đấu dừng và bạn thắng.

Bạn không cần tới Hà Lan; bạn có thể cử người đại diện. Hãy nghĩ về lời dặn: chờ tới khi giá hoa dạ yên thảo (petunia) xuống 86,3 euro thì bỏ giá. Khi cân nhắc lời dặn đó, bạn phải dự đoán rằng nếu giá xuống tới 86,3 euro thì bạn sẽ thắng; nếu có mặt ở đó, bạn biết mọi người khác còn chưa ra tay. Biết vậy, bạn không muốn đổi giá: chờ thêm một chút, người khác có thể nhảy vào thế chỗ bạn. Điều đó đúng suốt cuộc đấu, chờ lúc nào cũng có rủi ro bị giành; vấn đề là chờ càng lâu thì phần lãi có thể mất càng lớn và rủi ro người khác sắp nhảy vào càng cao. Ở giá tối ưu, khoản tiết kiệm nhờ trả thấp hơn không còn đáng với rủi ro mất giải tăng thêm.

Theo nhiều nghĩa, việc này giống đấu giá kín. Lời dặn người đại diện tương đương con số bạn ghi vào phong bì; ai cũng làm vậy; người ghi số cao nhất cũng là người giơ tay đầu tiên. Khác biệt duy nhất là khi bạn bỏ giá trong đấu giá Hà Lan, bạn biết mình đã thắng, còn khi ghi giá trong đấu giá kín, bạn chỉ biết sau. Nhưng lời khuyên cho đấu giá kín là bỏ giá như thể mình đã thắng, giả định mọi người khác thấp hơn mình, và đó chính xác là tình huống của bạn trong đấu giá Hà Lan.

**Bài tập Trip to the Gym số 7.** Nên bỏ bao nhiêu trong đấu giá kín? Để đơn giản, giả sử chỉ có hai người; bạn tin giá trị của người kia có khả năng như nhau ở mọi mức từ 0 đến 100, và người kia cũng tin như vậy về bạn.

**Đáp án của sách (phần Workouts):** Hai tác giả biến đấu giá Vickrey thành đấu giá kín qua từng bước. Trong đấu giá Vickrey, giá trị của bạn là 60 nên bạn bỏ 60. Nếu được báo là đã thắng, bạn chỉ biết giá phải trả là một mức nào đó dưới 60; mọi mức dưới 60 có khả năng như nhau, nên trung bình bạn trả 30. Nếu được chọn giữa trả 30 và trả giá cao thứ hai, bạn thấy như nhau. Tương tự, giá trị 80 thì khi thắng trong Vickrey bạn trả trung bình 40; tổng quát, giá trị X thì trả trung bình X/2. Bước một: đổi luật thành "bỏ X, thắng thì trả X/2". Vì trung bình kết quả như Vickrey, giá bỏ tối ưu không đổi, và nếu mọi người cùng theo luật này thì giá của họ cũng không đổi. Đến đây đã gần giống đấu giá kín, chỉ khác là bạn trả một nửa con số mình ghi, như thể trả bằng đô la thay vì bảng Anh. Người chơi không bị lừa: nếu nói 80 nghĩa là trả 40 thì "80" thực chất là 40. Bước hai: đổi luật thành trả đúng giá mình bỏ; mọi người chỉ việc chia đôi giá bỏ, người sẵn lòng trả 40 sẽ nói 40 thay vì 80. Đó là đấu giá kín, và một cân bằng là cả hai bỏ một nửa giá trị. Kiểm tra: giả sử người kia bỏ một nửa giá trị; nếu bạn bỏ X, bạn thắng khi người kia có giá trị dưới 2X (tức bỏ dưới X), xác suất là 2X/100; lợi ích của bạn khi giá trị thật là V bằng (V − X) × 2X/100, lớn nhất tại X = V/2. Nếu người kia bỏ một nửa thì bạn cũng muốn bỏ một nửa, và ngược lại, nên đó là cân bằng Nash. Hai tác giả nhận xét: kiểm tra một cân bằng dễ hơn nhiều so với tìm ra nó.

Như vậy cách bỏ giá trong hai loại đấu giá là như nhau. Giống như đấu giá kiểu Anh và Vickrey đi tới cùng chỗ, đấu giá kín và đấu giá Hà Lan cũng vậy; người chơi bỏ cùng mức nên người bán thu như nhau. Nhưng điều đó chưa cho biết phải bỏ bao nhiêu, chỉ cho biết có "hai bí ẩn cùng một đáp án".

Đáp án đến từ một trong những kết quả đáng chú ý nhất của lý thuyết đấu giá, định lý tương đương doanh thu: khi giá trị là riêng và trò chơi đối xứng, người bán thu trung bình như nhau dù thể thức là kiểu Anh, Vickrey, Hà Lan hay đấu giá kín.

> **Chú thích của tác giả:** Kết quả này được Roger Myerson chứng minh đầu tiên. Về bản chất, nó đến từ việc người bỏ giá chỉ quan tâm tới mục đích chứ không tới phương tiện: anh ta chỉ quan tâm mình kỳ vọng trả bao nhiêu và khả năng thắng món đồ là bao nhiêu. Anh ta có thể trả nhiều hơn để tăng khả năng thắng, và những người coi trọng món đồ hơn sẽ làm vậy. Nhận thức này là một trong những đóng góp vào lý thuyết đấu giá giúp Myerson nhận giải Nobel năm 2007 (bài nền tảng "Optimal Auction Design", *Mathematics of Operations Research*, 1981).

Điều đó có nghĩa là đấu giá Hà Lan và đấu giá kín có một cân bằng đối xứng trong đó chiến lược tối ưu là bỏ đúng mức mà bạn nghĩ là giá trị của người cao kế tiếp, với niềm tin rằng mình có giá trị cao nhất. Trong đấu giá đối xứng, mọi người có cùng niềm tin về nhau, chẳng hạn ai cũng nghĩ giá trị của mỗi người có khả năng như nhau ở mọi mức từ 0 đến 100. Khi đó, dù là đấu giá Hà Lan hay đấu giá kín, bạn nên bỏ mức bạn kỳ vọng cho người cao kế tiếp, với giả định mọi giá trị khác đều dưới giá trị của bạn:

| Giá trị của bạn | Số đối thủ | Vị trí dự kiến của các đối thủ | Giá nên bỏ |
|---|---|---|---|
| 60 | 1 | 30 | 30 |
| 60 | 2 | 20 và 40 | 40 |
| 60 | 3 | 15, 30 và 45 | 45 |

> **Chú thích của tác giả:** Nói chung, bạn đoán các đối thủ cách đều nhau trong khoảng từ 0 tới giá trị của bạn. Một đối thủ thì người đó ở giữa; hai đối thủ thì dự kiến ở 20 và 40; ba đối thủ thì ở 15, 30 và 45. Bạn bỏ giá bằng giá trị kỳ vọng của đối thủ cao nhất. Khi số người bỏ giá tăng, giá bỏ hội tụ về giá trị; thị trường tiến tới cạnh tranh hoàn hảo và toàn bộ thặng dư về tay người bán.

Từ đây thấy ngay vì sao có tương đương doanh thu. Trong đấu giá Vickrey, người có giá trị cao nhất thắng nhưng chỉ trả giá cao thứ hai, tức giá trị cao thứ hai. Trong đấu giá kín, mọi người bỏ đúng mức họ nghĩ là giá trị cao thứ hai (với giả định mình cao nhất); người thực sự có giá trị cao nhất sẽ thắng và giá bỏ của họ trung bình bằng kết quả trong Vickrey.

Bài học rộng hơn: bạn có thể viết luật cho một trò chơi, nhưng người chơi có thể hoá giải luật đó. Bắt mọi người trả gấp đôi giá bỏ thì họ sẽ bỏ một nửa; bắt trả bình phương giá bỏ thì họ sẽ lấy căn bậc hai của mức lẽ ra họ bỏ. Đó chính là điều xảy ra trong đấu giá kín: khi bắt người ta trả giá của mình thay vì giá cao thứ hai, họ đổi con số ghi ra, hạ xuống tới mức bằng giá trị cao thứ hai mà họ kỳ vọng.

### 9. Tín phiếu Kho bạc (T-Bills)

Hai tác giả mời người đọc thử trực giác mới với cuộc đấu giá lớn nhất thế giới: thị trường tín phiếu Kho bạc Mỹ. Mỗi tuần, Bộ Tài chính Mỹ tổ chức đấu giá để định lãi suất cho phần nợ quốc gia đáo hạn tuần đó. Tới đầu thập niên 1990, người thắng nhận đúng lãi suất mình bỏ. Sau khi Milton Friedman và các nhà kinh tế khác thúc đẩy, Bộ Tài chính thử nghiệm đấu giá giá thống nhất năm 1992 và áp dụng hẳn từ năm 1998 (Bộ trưởng Tài chính khi đó là Larry Summers, một nhà kinh tế nổi tiếng).

Ví dụ: tuần đó Bộ Tài chính cần bán 100 triệu USD trái phiếu và nhận được các mức bỏ sau (Bảng dựng lại từ sách):

| Số tiền bỏ, ở lãi suất | Cộng dồn |
|---|---|
| 10 triệu USD ở 3,1% | 10 triệu USD |
| 20 triệu USD ở 3,25% | 30 triệu USD |
| 20 triệu USD ở 3,33% | 50 triệu USD |
| 15 triệu USD ở 3,5% | 65 triệu USD |
| 25 triệu USD ở 3,6% | 90 triệu USD |
| 20 triệu USD ở 3,72% | 110 triệu USD |
| 25 triệu USD ở 3,75% | 135 triệu USD |
| 30 triệu USD ở 3,80% | 165 triệu USD |
| 25 triệu USD ở 3,82% | 190 triệu USD |

Bộ Tài chính muốn trả lãi thấp nhất nên nhận các mức thấp nhất trước: mọi người chấp nhận từ 3,6% trở xuống đều thắng (cộng dồn 90 triệu), cùng một nửa số người chấp nhận 3,72% (vì 20 triệu ở mức này vượt 10 triệu còn lại). Theo luật cũ, 10 triệu bỏ ở 3,1% thắng và chỉ nhận lãi 3,1%; 20 triệu ở 3,25% nhận 3,25%; cứ thế cho tới 20 triệu ở 3,72%, trong đó chỉ một nửa được bán và nửa kia ra về tay trắng.

> **Chú thích của tác giả:** Còn có một điều khoản hay cho phép nhà đầu tư nhỏ nhận lãi suất bình quân của mọi người thắng. Nếu muốn mua mà không muốn đấu trí với Goldman Sachs và các nhà đầu tư sành sỏi khác, bạn chỉ cần ghi số tiền muốn mua mà không ghi lãi suất; bạn chắc chắn thắng và nhận lãi suất bình quân của những người thắng. Các ngân hàng đầu tư lớn không được dùng điều khoản này, chỉ nhà đầu tư nhỏ.

Theo luật mới, mọi mức từ 3,1% tới 3,6% thắng, cùng một nửa mức 3,72%, và tất cả nhận lãi suất cao nhất trong các mức thắng, ở đây là 3,72%. Phản xạ đầu tiên là nghĩ luật giá thống nhất tệ hơn nhiều cho chính phủ (và tốt hơn cho nhà đầu tư): thay vì trả từ 3,1% tới 3,72%, Bộ Tài chính trả mọi người 3,72%. Với các con số trong ví dụ thì đúng vậy. Nhưng vấn đề là người ta sẽ không bỏ giá giống nhau dưới hai luật; hai tác giả dùng cùng các con số chỉ để minh hoạ cơ chế. Đây là phiên bản lý thuyết trò chơi của định luật 3 Newton: có tác động thì có phản ứng. Đổi luật chơi thì phải dự đoán người chơi bỏ giá khác đi.

Một ví dụ đơn giản: giả sử Bộ Tài chính tuyên bố người thắng nhận lãi suất thấp hơn mức mình bỏ 1 điểm phần trăm, bỏ 3,1% chỉ được 2,1%. Với cùng các mức bỏ như trên thì đúng là lãi phải trả giảm (3,1% thành 2,1%, 3,25% thành 2,25%...). Nhưng dưới luật mới đó, ai định bỏ 3,1% sẽ bỏ 4,1%; mọi người bỏ cao hơn 1 điểm, và sau khi trừ đi thì mọi thứ y như trước. Điều này đưa tới vế thứ hai của định luật Newton: phản ứng bằng và ngược chiều với tác động. Ít nhất trong các trường hợp vừa xét, phản ứng của người bỏ giá bù trừ đúng thay đổi của luật.

Sau khi người bỏ giá điều chỉnh, Bộ Tài chính nên kỳ vọng trả cùng mức lãi dưới luật giá thống nhất như dưới luật trả theo giá bỏ. Nhưng việc của người bỏ giá dễ hơn nhiều: người sẵn lòng nhận 3,33% không còn phải tính có nên bỏ 3,6% hay 3,72%; họ cứ bỏ 3,33% và biết rằng nếu thắng sẽ nhận ít nhất 3,33%, nhiều khả năng cao hơn. Bộ Tài chính không mất tiền, người bỏ giá đỡ việc.

> **Chú thích của tác giả:** Đấu giá tín phiếu giá thống nhất chưa hẳn là đấu giá Vickrey. Vấn đề là khi bỏ giá mua thêm đơn vị, người bỏ giá có thể làm giảm lãi suất mình nhận trên mọi đơn vị đã thắng, nên vẫn còn một phần bỏ giá chiến lược. Muốn biến nó thành đấu giá Vickrey nhiều đơn vị, mỗi người phải nhận lãi suất thắng cao nhất tính trong thí nghiệm tưởng tượng mà người đó không tham gia.

### 10. Trò chơi chiếm trước (The Preemption Game)

Nhiều trò chơi thoạt nhìn không giống đấu giá nhưng hoá ra là đấu giá. Hai tác giả xét hai cuộc đọ ý chí: trò chơi chiếm trước và cuộc chiến tiêu hao.

Ngày 3/8/1993, Apple tung ra máy Newton (sách ghi "Original Newton Message"). Newton không chỉ thất bại mà còn là nỗi xấu hổ: phần mềm nhận dạng chữ viết tay do các lập trình viên Liên Xô phát triển dường như không hiểu tiếng Anh. Trong một tập phim *The Simpsons*, Newton đọc "Beat up Martin" (đánh Martin) thành "Eat up Martha" (ăn Martha). Tranh biếm hoạ *Doonesbury* chế giễu lỗi nhận dạng của nó.

Hình dựng lại từ sách (tranh Doonesbury bốn ô):

| Ô | Người dùng viết | Máy Newton đọc thành |
|---|---|---|
| 1 | "I am writing a test sentence" (Tôi đang viết một câu thử) | "Siam fighting atomic sentry" |
| 2 | Viết lại câu đó | "Ian is riding a taste sensation" |
| 3 | Viết mạnh tay "I am writing a test sentence!!" | "I am writing a test sentence!" (lần này đúng) |
| 4 | "Catching on?" (Hiểu ra chưa?) | "Egg freckles?" |

Newton bị khai tử năm năm sau, ngày 27/2/1998. Trong lúc Apple bận thất bại, tháng 3/1996 Jeff Hawkins giới thiệu máy tổ chức cá nhân cầm tay Palm Pilot 1000, nhanh chóng đạt doanh số 1 tỷ USD mỗi năm. Newton là ý tưởng hay nhưng chưa sẵn sàng. Đó là nghịch lý: chờ tới khi hoàn toàn sẵn sàng thì lỡ cơ hội; nhảy vào quá sớm thì thất bại.

Việc ra đời của *USA Today* gặp đúng vấn đề này. Hầu hết các nước có báo ngày toàn quốc lâu đời: Pháp có *Le Monde* và *Le Figaro*; Anh có *The Times*, *Observer* và *Guardian*; Nhật có *Asahi Shimbun* và *Yomiuri Shimbun*; Trung Quốc có *Nhân dân Nhật báo*; Nga có *Pravda*; Ấn Độ có *The Times*, *Hindu*, *Dainik Jagran* và khoảng sáu mươi tờ khác. Riêng người Mỹ không có báo ngày toàn quốc: họ có tạp chí toàn quốc (*Time*, *Newsweek*) và tuần báo *Christian Science Monitor*. Mãi tới năm 1982, Al Neuharth mới thuyết phục hội đồng quản trị Gannett ra *USA Today*. Làm báo toàn quốc ở Mỹ là cơn ác mộng hậu cần: phát hành báo vốn là việc địa phương, nên tờ báo phải in ở nhiều nhà máy khắp nước. Với Internet thì việc này đơn giản, nhưng năm 1982 cách khả thi duy nhất là truyền qua vệ tinh, và với các trang màu, *USA Today* là công nghệ mới tinh, rủi ro cao. Vì ngày nay thấy các hộp báo xanh của nó ở khắp nơi, người ta dễ nghĩ đó hẳn là ý tưởng hay; nhưng thành công hôm nay không có nghĩa là đáng với chi phí. Gannett mất 12 năm mới hoà vốn với tờ báo và lỗ hơn 1 tỷ USD trên đường đi, "vào thời một tỷ còn là tiền thật". Giá Gannett chờ thêm vài năm thì công nghệ đã làm hành trình dễ hơn nhiều. Vấn đề là thị trường báo toàn quốc ở Mỹ chỉ đủ chỗ cho nhiều nhất một tờ, và Neuharth lo Knight Ridder sẽ ra trước và cánh cửa đóng lại vĩnh viễn.

Cả Apple và *USA Today* đều đang chơi trò chơi chiếm trước: người ra mắt đầu tiên có cơ hội chiếm thị trường, với điều kiện thành công. Câu hỏi là khi nào bóp cò: bóp sớm quá thì trượt, chờ lâu quá thì bị đánh bại. Cách mô tả này gợi tới một cuộc đấu súng, và phép so sánh là xác đáng: nếu bạn bắn sớm và trượt, đối thủ có thể tiến lên và bắn trúng chắc chắn; nếu chờ quá lâu, bạn có thể chết mà chưa bắn phát nào.

> **Chú thích của tác giả:** Đồng nghiệp ở Yale của hai tác giả, Ben Polak, minh hoạ trò chơi chiếm trước bằng một cuộc đấu với hai miếng bọt biển ướt. Bạn có thể thử ở nhà (hoặc trong lớp): bắt đầu ở xa nhau, đi chậm lại gần nhau. Khi nào bạn ném?

Có thể mô hình cuộc đấu súng như một cuộc đấu giá: thời điểm bắn là giá bỏ; ai bỏ thấp nhất được bắn trước, nhưng bỏ thấp thì xác suất thành công cũng thấp. Có thể bất ngờ, nhưng cả hai người chơi sẽ muốn bắn cùng lúc. Điều này dễ hiểu khi hai người tài ngang nhau, nhưng kết quả vẫn đúng khi tài khác nhau. Giả sử ngược lại: bạn định chờ tới thời điểm 10 mới bắn, còn đối thủ định bắn lúc 8. Cặp chiến lược đó không thể là cân bằng, vì đối thủ nên chờ tới 9,99, tăng xác suất trúng mà không có nguy cơ bị bắn trước. Ai định đi trước cũng nên chờ tới khoảnh khắc ngay trước khi đối thủ sắp bắn.

Nếu chờ tới thời điểm 10 thật sự hợp lý, bạn phải sẵn lòng để bị bắn và hy vọng đối thủ trượt, và điều đó phải tốt ngang với việc bắn trước. Thời điểm đúng để bắn là khi xác suất thành công của bạn bằng xác suất thất bại của đối thủ. Vì xác suất thất bại bằng 1 trừ xác suất thành công, bạn bắn ở khoảnh khắc đầu tiên mà hai xác suất thành công cộng lại bằng 1. Nếu tổng đó bằng 1 với bạn thì cũng bằng 1 với đối thủ, nên thời điểm bắn là như nhau cho cả hai.

**Bài tập Trip to the Gym số 8.** Bạn và đối thủ cùng ghi thời điểm sẽ bắn. Xác suất trúng tại thời điểm t là p(t) với bạn và q(t) với đối thủ. Nếu phát đầu trúng thì trò chơi kết thúc; nếu trượt, người kia chờ tới cuối và bắn trúng chắc chắn. Khi nào bạn nên bắn?

**Đáp án của sách (phần Workouts):** Giả sử bạn biết đối thủ sẽ bắn lúc t = 10. Bạn có thể bắn lúc 9,99, khi đó khả năng thắng gần bằng p(10); hoặc chờ để đối thủ thử, khi đó bạn thắng nếu đối thủ trượt, với xác suất 1 − q(10). Vậy bạn nên bắn trước nếu p(10) > 1 − q(10). Đối thủ cũng tính như vậy: nếu nghĩ bạn sẽ bắn lúc 9,99, cô ấy muốn bắn lúc 9,98 nếu q(9,98) > 1 − p(9,98). Điều kiện để không bên nào muốn bắn trước là p(t) ≤ 1 − q(t) và q(t) ≤ 1 − p(t); hai điều kiện này là một: p(t) + q(t) ≤ 1. Vậy cả hai sẵn lòng chờ tới khi p(t) + q(t) = 1 rồi cùng bắn.

Hai tác giả lưu ý giới hạn của mô hình: nó giả định hai bên hiểu đúng xác suất thành công của nhau, điều không phải lúc nào cũng đúng; và giả định kết quả của việc thử rồi thất bại bằng kết quả của việc để đối thủ đi trước rồi thắng. Như người ta nói, đôi khi thử rồi thua còn hơn chưa bao giờ thử.

### 11. Cuộc chiến tiêu hao (The War of Attrition)

Ngược với trò chơi chiếm trước là cuộc chiến tiêu hao. Thay vì xem ai nhảy vào trước, mục tiêu là trụ lâu hơn đối thủ; câu hỏi không phải ai vào trước mà ai chịu thua trước. Đây cũng có thể coi là một cuộc đấu giá: giá bỏ là thời gian bạn sẵn lòng ở lại và chịu lỗ. Đó là một cuộc đấu giá lạ, vì mọi người tham gia đều phải trả giá mình bỏ, trong khi chỉ người cao nhất thắng; ở đây thậm chí có thể hợp lý khi bỏ cao hơn giá trị.

Năm 1986, British Satellite Broadcasting (BSB) giành giấy phép chính thức cung cấp truyền hình vệ tinh cho thị trường Anh, một trong những nhượng quyền có tiềm năng giá trị nhất lịch sử. Trong nhiều năm, khán giả Anh chỉ có hai kênh BBC và ITV; Channel 4 nâng tổng số lên, như bạn đoán, bốn kênh. Đây là nước có 21 triệu hộ gia đình, thu nhập cao, mưa nhiều, và khác với Mỹ, gần như không có truyền hình cáp.

> **Chú thích của tác giả:** Dưới 1% hộ gia đình thuê bao truyền hình cáp, và luật chỉ cho phép cáp ở những vùng không thu được sóng truyền hình phát qua không trung.

Vì vậy hoàn toàn có lý khi hình dung truyền hình vệ tinh ở Anh có thể đem lại 2 tỷ bảng doanh thu mỗi năm; những thị trường chưa khai thác như vậy rất hiếm. Mọi thứ đều thuận lợi cho BSB cho tới tháng 6/1988, khi Rupert Murdoch quyết định phá đám. Dùng một vệ tinh Astra kiểu cũ đặt trên Hà Lan, Murdoch phát bốn kênh của mình vào Anh; người Anh rốt cuộc được xem *Dallas* (và sớm sau đó là *Baywatch*). Thị trường có vẻ đủ lớn cho cả hai, nhưng cạnh tranh khốc liệt đã xoá sạch hy vọng lợi nhuận: hai bên đấu giá tranh nhau phim Hollywood và đua giảm giá quảng cáo. Vì công nghệ phát sóng không tương thích, nhiều người quyết định chờ xem ai thắng rồi mới mua chảo thu. Sau một năm cạnh tranh, hai hãng lỗ tổng cộng 1,5 tỷ bảng.

Điều này hoàn toàn đoán trước được. Murdoch hiểu rõ BSB sẽ không bỏ cuộc, còn chiến lược của BSB là xem có đẩy được Murdoch tới phá sản không. Cả hai sẵn lòng chịu lỗ lớn vì giải thưởng cho người thắng quá lớn: ai trụ lâu hơn sẽ có toàn bộ lợi nhuận. Việc bạn có thể đã lỗ 600 triệu bảng là không liên quan, vì dù tiếp tục hay bỏ cuộc bạn cũng đã mất khoản đó. Câu hỏi duy nhất là chi phí trụ thêm có đáng với "hũ vàng" của người thắng không.

Có thể mô hình đây là cuộc đấu giá mà giá bỏ của mỗi bên là thời gian ở lại, đo bằng khoản lỗ tài chính; hãng trụ lâu nhất thắng. Điều làm loại đấu giá này đặc biệt khó là không có một chiến lược bỏ giá tốt nhất duy nhất. Nếu nghĩ đối thủ sắp bỏ, bạn luôn nên trụ thêm một kỳ; và bạn nghĩ họ sắp bỏ vì bạn nghĩ họ nghĩ bạn sẽ trụ. Chiến lược của bạn phụ thuộc vào điều bạn nghĩ họ đang làm, và điều đó lại phụ thuộc vào điều họ nghĩ bạn đang làm. Bạn không thực sự biết họ làm gì, nên phải tự hình dung trong đầu họ nghĩ gì về bạn. Vì không có gì kiểm tra sự nhất quán, cả hai đều có thể quá tự tin vào khả năng trụ lâu hơn đối thủ, dẫn tới bỏ giá quá cao hoặc lỗ khổng lồ cho cả hai.

Hai tác giả cho rằng đây là trò chơi nguy hiểm, và nước đi tốt nhất là thoả thuận với người chơi kia. Murdoch đã làm đúng như vậy: vào phút chót, ông sáp nhập với BSB. Khả năng chịu lỗ quyết định tỷ lệ chia trong liên doanh, và việc cả hai hãng cùng có nguy cơ sụp đổ buộc chính phủ phải cho phép hai người chơi duy nhất sáp nhập. Bài học thứ hai: đừng bao giờ đặt cược chống lại Murdoch.

### 12. Tình huống: đấu giá phổ tần (Case Study: Spectrum Auctions)

"Mẹ của mọi cuộc đấu giá" là việc bán phổ tần cho giấy phép điện thoại di động. Từ 1994 đến 2005, Uỷ ban Truyền thông Liên bang Mỹ (FCC) thu hơn 40 tỷ USD. Ở Anh, một cuộc đấu giá phổ tần 3G (thế hệ thứ ba) thu được con số choáng váng 22,5 tỷ bảng, cuộc đấu giá đơn lẻ lớn nhất mọi thời. Khác với đấu giá tăng dần truyền thống, một số cuộc đấu này phức tạp hơn vì cho phép người tham gia bỏ giá đồng thời cho nhiều giấy phép.

Hai tác giả đưa ra phiên bản đơn giản hoá của cuộc đấu giá phổ tần đầu tiên ở Mỹ và mời người đọc tự xây chiến lược: chỉ có hai người chơi, AT&T và MCI, và hai giấy phép, NY và LA, mỗi giấy phép chỉ có một; cả hai hãng đều muốn cả hai giấy phép. Một cách là bán lần lượt, NY trước rồi LA, hoặc ngược lại; không có câu trả lời hiển nhiên, và cách nào cũng có vấn đề. Nếu bán NY trước, AT&T có thể thích LA hơn nhưng cảm thấy buộc phải tranh NY vì chưa chắc giành được LA, mà có còn hơn không; nhưng thắng NY rồi thì có thể không còn ngân sách cho LA. Với sự giúp đỡ của một số nhà lý thuyết trò chơi, FCC nghĩ ra giải pháp khéo léo: đấu giá đồng thời. Cả NY và LA cùng lên sàn; người tham gia có thể bỏ giá cho bất kỳ giấy phép nào; nếu AT&T bị vượt giá ở LA, họ có thể nâng giá LA hoặc chuyển sang tranh NY. Cuộc đấu chỉ kết thúc khi không ai muốn nâng giá cho bất kỳ giấy phép nào. Trong thực tế, việc bỏ giá chia thành các vòng; mỗi vòng, người chơi có thể nâng giá hoặc đứng yên.

Minh hoạ luật (Bảng dựng lại từ sách). Cuối vòng 4, các giá đã bỏ như sau, AT&T đang cao nhất ở NY, MCI cao nhất ở LA:

| | NY | LA |
|---|---|---|
| AT&T | 6 | 7 |
| MCI | 5 | 8 |

Ở vòng 5, AT&T có thể bỏ giá cho LA và MCI có thể bỏ cho NY; không có lý do để AT&T bỏ thêm cho NY vì đã cao nhất ở đó, MCI và LA cũng vậy. Giả sử chỉ AT&T bỏ giá, kết quả mới có thể là:

| | NY | LA |
|---|---|---|
| AT&T | 6 | 9 |
| MCI | 5 | 8 |

Giờ AT&T cao nhất ở cả hai nên không được bỏ giá. Nhưng cuộc đấu chưa kết thúc, vì nó chỉ kết thúc khi có một vòng không ai bỏ giá; AT&T vừa bỏ giá ở vòng trước nên phải có ít nhất một vòng nữa, và MCI có cơ hội bỏ. Nếu MCI không bỏ, cuộc đấu kết thúc (nhớ rằng AT&T không được bỏ). Nếu MCI bỏ, chẳng hạn 7 cho NY, cuộc đấu tiếp tục; vòng sau AT&T có thể bỏ cho NY và MCI lại có cơ hội vượt giá ở LA.

Sau phần giải thích luật, hai tác giả mời người đọc chơi từ đầu, và chia sẻ "thông tin thị trường": hai hãng đã chi hàng triệu USD để chuẩn bị, tính ra giá trị của chính mình cho từng giấy phép và giá trị mà họ nghĩ đối thủ có (Bảng dựng lại từ sách):

| | NY | LA |
|---|---|---|
| AT&T | 10 | 9 |
| MCI | 9 | 8 |

AT&T coi trọng cả hai giấy phép hơn MCI. Hai tác giả yêu cầu coi đây là dữ kiện, và giả định các giá trị này là hiểu biết chung: AT&T biết giá trị của mình, biết của MCI, biết MCI biết của AT&T, biết MCI biết AT&T biết của MCI, và cứ thế. Giả định này cực đoan, nhưng các hãng đã chi rất nhiều tiền cho cái gọi là tình báo cạnh tranh, nên việc họ hiểu rõ nhau là khá sát thực tế. Hai tác giả "lịch sự" để người đọc chọn phe, và cho rằng chọn AT&T là đúng vì có giá trị cao hơn nên có lợi thế; họ chơi MCI và ghi giá của mình mà không nhìn giá của người đọc.

### 13. Thảo luận tình huống (Case Discussion)

**Bỏ 10 cho NY và 9 cho LA.** Bạn chắc chắn thắng cả hai nhưng không lãi gì. Đây là một điểm tinh tế: nếu phải trả đúng giá mình bỏ, như ở đây, thì bỏ đúng giá trị chẳng có nghĩa gì, giống như bỏ 10 USD để thắng tờ 10 USD. Có thể nhầm lẫn nếu nghĩ việc thắng tự nó là một phần thưởng thêm, hoặc nếu coi các con số giá trị là mức bỏ tối đa chứ không phải giá trị thật. Hai tác giả không muốn người đọc hiểu theo cả hai cách đó. Giá trị 10 cho NY nghĩa là ở giá 10, bạn vui vẻ ra về mà không than vãn cũng không thắng; ở giá 9,99 bạn thích thắng hơn, nhưng chỉ một chút; ở 10,01 bạn thích không thắng hơn, dù thiệt hại nhỏ. Với cách hiểu này, bỏ 10 và 9 là chiến lược bị trội (yếu): bạn chắc chắn được 0, dù thắng hay thua. Bất kỳ chiến lược nào cho cơ hội được hơn 0 mà không bao giờ lỗ đều trội yếu so với việc bỏ ngay 10 và 9.

**Bỏ 9 cho NY và 8 cho LA.** Tốt hơn. Với giá của hai tác giả (họ không bỏ quá giá trị của MCI), bạn thắng cả hai, lãi 1 ở mỗi thành phố, tổng 2. Câu hỏi then chốt là có thể làm tốt hơn không.

**Bỏ 5 và 5.** (Các mức khác diễn ra tương tự.) Hai tác giả tiết lộ giá của mình: 0 (không bỏ) cho NY và 1 cho LA. Sau vòng đầu, bạn cao nhất ở cả hai nên không được bỏ ở vòng này; vì đang thua ở cả hai, MCI bỏ tiếp. Đứng ở vị trí MCI: họ không thể về báo với tổng giám đốc rằng đã rút khi giá mới ở mức 5; họ chỉ có thể về tay trắng khi giá đã lên 9 và 8, khi không còn đáng để bỏ tiếp. Vì vậy họ nâng giá LA lên 6, và vì có người bỏ giá nên cuộc đấu kéo thêm một vòng. Giả sử bạn nâng LA lên 7; vòng sau MCI sẽ bỏ cho NY với giá 6, vì họ thà thắng NY ở 6 hơn LA ở 8; rồi bạn lại có thể vượt giá ở NY. Tuỳ ai bỏ khi nào, bạn sẽ thắng cả hai giấy phép với giá 9 hoặc 10 ở NY, 8 hoặc 9 ở LA, không hơn gì bỏ ngay 9 và 8.

**Chơi lại ván đó.** Khi MCI bỏ 6 cho LA, bạn đang giữ NY ở giá 5. Bạn có thể không làm gì cả, dừng bỏ giá. MCI không có ý định vượt giá bạn ở NY; họ hài lòng với LA ở giá 6, và chỉ bỏ tiếp vì không thể về tay trắng (trừ khi giá đã lên 9 và 8). Nếu bạn dừng, cuộc đấu kết thúc ngay: bạn chỉ có một giấy phép, NY ở giá 5, nhưng vì định giá nó 10, bạn lãi 5, hơn hẳn mức lãi 2 khi bỏ 9 và 8. Từ phía MCI: họ biết không thể thắng bạn ở cả hai vì giá trị của bạn cao hơn, nên rất vui lòng ra về với một giấy phép ở bất kỳ giá nào dưới 9 và 8.

**Lần chơi cuối.** Hai tác giả hy vọng lần này bạn bỏ 1 cho NY và 0 cho LA, vì họ bỏ 0 cho NY và 1 cho LA. Vì vòng trước có người bỏ giá nên mỗi bên có thêm một lượt. Bạn không thể bỏ cho NY vì đang cao nhất; còn LA, bạn có bỏ không? Hai tác giả hy vọng là không; họ cũng không bỏ. Nếu bạn không bỏ, cuộc đấu kết thúc vì có một vòng không ai bỏ giá. Bạn ra về với một giấy phép ở giá hời 1, lãi 9.

Có thể bực mình khi thấy MCI lấy giấy phép thứ hai với giá 1 trong khi bạn coi trọng nó hơn nhiều, thậm chí hơn cả MCI. Hai tác giả đưa ra cách nhìn để an ủi: trước khi chịu về tay trắng, MCI sẽ bỏ tới 9 và 8. Muốn không cho họ giấy phép nào, bạn phải sẵn sàng trả tổng cộng 17. Bạn đang có một giấy phép ở giá 1, nên chi phí thật của giấy phép thứ hai là 16, vượt xa giá trị của nó với bạn.

| Lựa chọn của AT&T | Giấy phép có được | Tổng giá | Tổng giá trị | Lãi |
|---|---|---|---|---|
| Dừng lại | NY | 1 | 10 | 9 |
| Tranh cả hai (MCI đẩy giá tới 9 và 8) | NY và LA | 17 | 19 | 2 |

Thắng một giấy phép là lựa chọn tốt hơn. Bạn có thể đánh bại MCI ở cả hai cuộc đấu, nhưng điều đó không có nghĩa là nên làm vậy.

Hai tác giả đoán người đọc còn thắc mắc. Làm sao bạn biết MCI sẽ bỏ giá cho LA và để NY lại cho bạn? Thực ra bạn không biết; ván này may mắn diễn ra như vậy. Nhưng kể cả nếu cả hai cùng bỏ cho NY ở vòng đầu, cũng không mất nhiều thời gian để phân chia lại. Có phải là thông đồng không? Nói chặt chẽ thì không. Dù cả hai hãng đều có lợi hơn (và người bán là bên thua lớn), không bên nào cần thoả thuận với bên kia; mỗi bên hành động vì lợi ích của chính mình. MCI tự hiểu rằng mình không thể thắng cả hai giấy phép, điều không có gì lạ vì AT&T có giá trị cao hơn ở cả hai, nên MCI vui lòng thắng bất kỳ giấy phép nào. Còn AT&T thấy rằng chi phí thật của giấy phép thứ hai là phần phải trả thêm trên cả hai: vượt giá MCI ở LA có thể đẩy giá lên ở cả LA lẫn NY, và chi phí thật đó là 16, cao hơn giá trị.

Hiện tượng này thường gọi là hợp tác ngầm: mỗi người chơi hiểu chi phí dài hạn của việc tranh cả hai giấy phép và vì vậy thấy lợi của việc lấy một giấy phép với giá rẻ. Nếu là người bán, bạn muốn tránh kết quả này. Một cách là bán hai giấy phép lần lượt. Khi đó, MCI để AT&T lấy NY với giá 1 sẽ không còn hiệu quả, vì AT&T vẫn có mọi động cơ để tranh LA ở cuộc đấu sau; khác biệt then chốt là MCI không thể quay lại bỏ giá ở cuộc đấu NY, nên AT&T không mất gì khi tranh LA.

Bài học lớn hơn: khi hai trò chơi được gộp làm một, người chơi có cơ hội dùng các chiến lược xuyên qua cả hai. Khi Fuji vào thị trường phim chụp ảnh Mỹ, Kodak có thể đáp trả ở Mỹ hoặc ở Nhật. Khởi động chiến tranh giá ở Mỹ sẽ tốn kém cho Kodak, nhưng ở Nhật thì tốn kém cho Fuji (và không tốn gì cho Kodak, vốn có thị phần nhỏ ở Nhật). Tương tác giữa nhiều trò chơi diễn ra đồng thời tạo cơ hội trừng phạt và hợp tác mà nếu không thì không thể có, ít nhất là nếu không thông đồng công khai. Nguyên tắc rút ra: nếu không thích trò chơi đang chơi, hãy tìm trò chơi lớn hơn. Hai tác giả giới thiệu thêm các tình huống về đấu giá ở Chương 14: "The Safer Duel" (cuộc đấu súng an toàn hơn), "The Risk of Winning" (rủi ro của việc thắng) và "What Price a Dollar?" (một đô la đáng giá bao nhiêu?).

**Ví dụ hôm nay** (minh hoạ của người tổng hợp, con số giả định). Một doanh nghiệp tham gia đấu giá quyền khai thác một mỏ cát, kiểu đấu giá kín trả theo giá mình bỏ, có ba đối thủ khác. Bộ phận kỹ thuật ước tính mỏ đem lại lợi nhuận 100 tỷ đồng nếu trữ lượng đúng như hồ sơ. Áp dụng ba bài học của chương. Thứ nhất, không bỏ 100 tỷ: thắng ở giá đó thì chỉ hoà vốn. Thứ hai, với giá trị riêng, giả sử các đối thủ được đoán là định giá phân bố đều từ 0 tới 100 tỷ, công thức trong chương cho mức bỏ khoảng 75 tỷ (giá trị × 3/4 khi có ba đối thủ). Thứ ba, trữ lượng cát thực ra là giá trị chung: nếu doanh nghiệp thắng, rất có thể vì ước tính trữ lượng của mình lạc quan hơn của ba đối thủ. Bỏ giá như thể mình đã thắng nghĩa là phải hỏi: "nếu tôi là người trả cao nhất, điều đó nói gì về trữ lượng?" Nếu câu trả lời là trữ lượng thật có thể chỉ khoảng 80% hồ sơ, giá trị khi thắng còn khoảng 80 tỷ, và mức bỏ hợp lý giảm tương ứng xuống khoảng 60 tỷ. Bỏ theo ước tính trung bình ban đầu chính là rơi vào lời nguyền của người thắng.

## Luận điểm kinh tế cốt lõi

### Mệnh đề

Đấu giá là một trò chơi chiến lược mà người chơi điều chỉnh hành vi theo luật. Vì vậy, với giá trị riêng và người chơi đối xứng, các thể thức khác nhau đem lại cùng kết quả: người coi trọng món đồ nhất thắng, và người bán thu trung bình bằng giá trị cao thứ hai. Người bỏ giá phải luôn giả định mình đã thắng để tránh lời nguyền của người thắng, và người thiết kế đấu giá phải lường trước các chiến lược mà luật mở ra, đặc biệt khi nhiều trò chơi được gộp làm một.

### Giả định

- Người bỏ giá biết (hoặc có thể tìm ra) giá trị của mình, hiểu luật và tính tới luật khi bỏ giá.
- Trong định lý tương đương doanh thu: giá trị là riêng, người chơi đối xứng (cùng niềm tin về nhau), không có ràng buộc ngân sách hay nhiều món liên quan.
- Trong ví dụ ACME và đấu giá kín: phân bố giá trị đều và được biết.
- Trong trò chơi chiếm trước: hai bên biết đúng xác suất thành công của nhau; thử rồi thất bại tệ ngang với để đối thủ thắng.
- Trong tình huống phổ tần: giá trị của hai bên là hiểu biết chung.

### Cơ chế

1. Trong đấu giá kiểu Anh, Nhật và Vickrey, bỏ tới đúng giá trị là chiến lược trội, nên người có giá trị cao nhất thắng và trả giá trị cao thứ hai.
2. Trong đấu giá kín và Hà Lan, người chơi hạ giá bỏ xuống mức giá trị cao thứ hai mà họ kỳ vọng với giả định mình cao nhất, nên trung bình người bán vẫn thu giá trị cao thứ hai.
3. Mọi quy tắc "trả khác đi" (phí người mua 20%, trừ 1 điểm lãi suất, trả gấp đôi, giá thống nhất) đều bị người chơi bù trừ bằng cách đổi con số họ bỏ.
4. Khi giá trị là chung, việc thắng mang thông tin xấu về giá trị; bỏ giá như thể đã thắng là cách đưa thông tin đó vào giá trước khi bỏ.
5. Khi luật để lộ thông tin (giá ủy nhiệm sớm trên eBay), người chơi có lý do giấu giá tới phút chót.
6. Khi thời điểm là giá bỏ, người chơi chiếm trước sẽ hành động cùng lúc tại điểm p(t) + q(t) = 1; người chơi tiêu hao không có điểm dừng tự nhiên và dễ cùng thua lỗ.
7. Khi nhiều món được bán đồng thời, người chơi có thể chia thị trường bằng hợp tác ngầm, làm người bán thiệt.

### Bằng chứng và ví dụ hai tác giả đưa ra

- Đấu giá vị trí quảng cáo của Google và Yahoo! (hơn 10 tỷ USD); nhà ở Úc; Sotheby's và eBay.
- Phép so sánh bỏ 50 với bỏ 60 khi giá trị là 60 trong đấu giá Vickrey.
- Phí người mua 20% ở Sotheby's và Christie's: người sẵn lòng trả 600 USD chỉ bỏ 500.
- Giá ủy nhiệm trên eBay (A 26, B 33, C 100, C trả 34); bộ trống Pearl Export; ghế Bauhaus; Porsche 911 định giá 19.000 USD.
- Trò chơi ACME: trần hoà vốn 6 triệu USD, không phải 10,5 triệu.
- Chợ hoa Aalsmeer: 160 mẫu Anh, 14 triệu bông hoa mỗi ngày.
- Giá bỏ tối ưu 30, 40, 45 cho giá trị 60 với 1, 2, 3 đối thủ.
- Đấu giá tín phiếu Mỹ chuyển sang giá thống nhất (thử năm 1992, chính thức năm 1998).
- Apple Newton (1993–1998), Palm Pilot (1996), USA Today (ra năm 1982, lỗ hơn 1 tỷ USD, 12 năm mới hoà vốn).
- BSB và Murdoch: lỗ 1,5 tỷ bảng trong một năm, rồi sáp nhập.
- Đấu giá phổ tần: FCC thu hơn 40 tỷ USD (1994–2005), Anh thu 22,5 tỷ bảng; tình huống AT&T và MCI; Kodak và Fuji.

### Kết luận và hàm ý chính sách

- Người bán và cơ quan nhà nước nên thiết kế đấu giá sao cho người chơi không cần chiến lược phức tạp (như Vickrey hay giá thống nhất), vì làm vậy không làm giảm doanh thu mà giảm chi phí và sai sót cho người bỏ giá.
- Đánh thuế hay thu phí vào một phía của giao dịch không có nghĩa phía đó gánh chịu; cần hỏi ai thực sự trả sau khi các bên điều chỉnh.
- Khi bán nhiều tài sản liên quan cùng lúc (phổ tần, lô đất, mỏ), người thiết kế phải lường trước khả năng các bên chia thị trường bằng hợp tác ngầm; bán đồng thời giúp người mua ghép gói hợp lý nhưng cũng mở đường cho chiến lược xuyên giấy phép.
- Cơ quan quản lý cạnh tranh phải cân nhắc rằng một cuộc chiến tiêu hao có thể kết thúc bằng sáp nhập, như BSB và hãng truyền hình vệ tinh của Murdoch.
- Với doanh nghiệp: tránh cuộc chiến tiêu hao, tìm thoả thuận; trong trò chơi chiếm trước, hành động khi tổng xác suất thành công của hai bên chạm 1.

### Trong ngôn ngữ kinh tế học

- **Lý thuyết đấu giá (auction theory) và thiết kế cơ chế (mechanism design).** Nhánh của lý thuyết trò chơi nghiên cứu cách luật chơi ảnh hưởng tới hành vi và kết quả. Câu "chiến lược khi thiết kế để người chơi không phải chiến lược khi chơi" của hai tác giả chính là ý tưởng về cơ chế "tương thích động cơ" (incentive compatible), nơi nói thật là chiến lược tối ưu.
- **Định lý tương đương doanh thu (revenue equivalence theorem).** Kết quả của Vickrey (1961) và Myerson (1981), cùng Riley và Samuelson (1981): mọi thể thức đấu giá trao món đồ cho người có giá trị cao nhất và để người có giá trị thấp nhất có lợi ích 0 đều cho cùng doanh thu kỳ vọng, khi giá trị riêng, độc lập và người chơi trung lập với rủi ro.
- **Hạ giá bỏ (bid shading).** Trong đấu giá giá thứ nhất, người chơi bỏ dưới giá trị; với giá trị phân bố đều và n người chơi, giá bỏ cân bằng là giá trị × (n − 1)/n, khớp với ví dụ 30, 40, 45 của chương.
- **Ước lượng có điều kiện khi thắng.** Trong đấu giá giá trị chung, người bỏ giá hợp lý tính giá trị kỳ vọng với điều kiện mình có tín hiệu cao nhất; bỏ qua điều kiện đó là nguồn gốc của lời nguyền của người thắng. Ví dụ ACME là một dạng của bài toán lựa chọn ngược (adverse selection) đã gặp ở Chương 8.
- **Cuộc chiến tiêu hao và trò chơi thời điểm (war of attrition, games of timing).** Các mô hình mà biến chiến lược là thời điểm hành động; cuộc chiến tiêu hao tương đương "đấu giá mọi người đều trả" (all-pay auction).
- **Tiếp xúc đa thị trường (multimarket contact).** Ví dụ Kodak và Fuji minh hoạ ý tưởng rằng các hãng gặp nhau ở nhiều thị trường dễ duy trì hợp tác ngầm hơn, vì có thể trừng phạt nhau ở thị trường mà đối thủ dễ tổn thương nhất.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong chương |
|---|---|
| Auction | Đấu giá |
| Procurement auction / reverse auction | Đấu thầu mua sắm / đấu giá ngược: người bỏ giá thấp nhất thắng |
| Winner's curse | Lời nguyền của người thắng |
| Value / walkaway number | Giá trị / mức giá bỏ đi: mức giá mà thắng hay thua với mình là như nhau |
| Private value / common value | Giá trị riêng / giá trị chung |
| English (ascending) auction | Đấu giá kiểu Anh (tăng dần) |
| Japanese auction | Đấu giá kiểu Nhật: giá tăng theo đồng hồ, hạ tay là rút hẳn |
| Bidding increment | Bước giá |
| Vickrey (second-price) auction | Đấu giá Vickrey (giá thứ hai) |
| Sealed-bid auction | Đấu giá kín, người thắng trả đúng giá mình bỏ |
| Dutch auction | Đấu giá kiểu Hà Lan (giá giảm dần) |
| Revenue equivalence theorem | Định lý tương đương doanh thu |
| Buyer's premium | Phí người mua |
| Proxy bid | Giá ủy nhiệm |
| Sniping | Đặt giá phút chót |
| Shading (a bid) | Hạ giá bỏ xuống dưới giá trị |
| Consequentialist | Người tư duy theo hệ quả |
| Bidding as if you've won | Bỏ giá như thể mình đã thắng |
| Take-it-or-leave-it offer | Lời đề nghị "nhận hoặc thôi" |
| Uniform pricing | Giá thống nhất: mọi người thắng nhận cùng mức lãi suất cao nhất được chấp nhận |
| T-bills | Tín phiếu Kho bạc Mỹ |
| Preemption game | Trò chơi chiếm trước |
| War of attrition | Cuộc chiến tiêu hao |
| Spectrum auction | Đấu giá phổ tần |
| Simultaneous auction | Đấu giá đồng thời nhiều giấy phép, chia vòng |
| Competitive intelligence | Tình báo cạnh tranh |
| Weakly dominated strategy | Chiến lược bị trội yếu |
| Tacit cooperation | Hợp tác ngầm |
| Collusion | Thông đồng |

## Câu nói đáng nhớ

> "Mục tiêu của hai tác giả là tính toán chiến lược khi thiết kế một trò chơi để người chơi không phải tính toán chiến lược khi chơi nó."
*"Our goal is to be strategic when designing a game so that the players don't have to be strategic when they play it."*

> "Bạn có thể thay đổi luật chơi, nhưng người chơi sẽ điều chỉnh chiến lược để tính tới luật mới."
*"You may change the rules of the game, but the players will adapt their strategies to take those new rules into account."*

> "Nếu nghe người ấy nói đồng ý mà bạn lại muốn nghĩ lại, thì lẽ ra bạn không nên hỏi."
*"If upon hearing that your intended says yes, you then want to reconsider, you shouldn't have asked in the first place."*

> "Chỉ vì bạn có thể thắng phía chúng tôi (MCI, phe do hai tác giả đóng) ở cả hai cuộc đấu giá không có nghĩa là bạn nên làm vậy."
*"Just because you can beat us in both auctions doesn't mean that you should."*

> "Nếu bạn không thích trò chơi đang chơi, hãy tìm trò chơi lớn hơn."
*"If you don't like the game you are playing, look for the larger game."*

## Đánh giá và phát hiện đáng chú ý

### Chương biến lý thuyết đấu giá vốn nặng toán thành những lập luận so sánh từng trường hợp mà ai cũng theo được

Lý thuyết đấu giá thường được dạy bằng tích phân và hàm phân phối. Hai tác giả thay bằng một kỹ thuật duy nhất dùng lại nhiều lần: so sánh hai lựa chọn, tìm những trường hợp chúng cho cùng kết quả, rồi chỉ xét trường hợp chúng khác nhau. Kỹ thuật này chứng minh được chiến lược trội trong Vickrey (bỏ 50 hay 60), lời khuyên bỏ giá như thể đã thắng (người đồng loã hạ 100 xuống 80), và cả đáp án của bài tập Trip to the Gym số 6 (biết trước giá của người khác trong đấu giá Vickrey chẳng đáng đồng nào). Người đọc ra khỏi chương với một công cụ tư duy dùng được ngoài đấu giá: khi cân nhắc hai phương án, hãy hỏi chúng khác nhau ở tình huống nào.

### Ví dụ ACME là phần giá trị nhất cho người làm thương vụ

Lỗi tính theo giá trị trung bình rồi nhân với mức cộng hưởng là lỗi rất phổ biến trong mua bán và sáp nhập. Ví dụ ACME cho thấy bằng con số cụ thể rằng việc người bán chấp nhận là tin xấu, và mức trần hợp lý (6 triệu USD) thấp hơn gần một nửa mức trực giác (10,5 triệu). Bài học tổng quát "hãy hỏi điều gì đúng trong thế giới mà đề nghị của tôi được nhận" áp dụng cho tuyển dụng, đàm phán lương, mua nhà, đầu tư vào công ty chưa niêm yết.

### Định lý tương đương doanh thu được trình bày gọn nhưng các giả định của nó rất dễ bị vi phạm

Hai tác giả có nói rõ điều kiện "giá trị riêng và trò chơi đối xứng", nhưng phần ứng dụng (phí người mua, tín phiếu) dễ khiến người đọc nghĩ luật chơi hầu như không quan trọng. Trên thực tế, khi người bỏ giá sợ rủi ro, có giá trị chung, giá trị phụ thuộc lẫn nhau hay bị giới hạn ngân sách, các thể thức cho doanh thu khác nhau. Ví dụ, với giá trị chung, đấu giá tăng dần thường đem lại doanh thu cao hơn đấu giá kín vì thông tin lộ ra trong quá trình đấu làm giảm nỗi sợ lời nguyền của người thắng. Chính chương này cũng đưa ra phản ví dụ mạnh nhất: trong tình huống phổ tần, nếu hai hãng tranh nhau tới cùng thì người bán thu 17, còn khi luật bán đồng thời cho phép hợp tác ngầm thì người bán chỉ thu 2; hai tác giả cũng nói bán lần lượt sẽ ngăn được kết quả này. Lời khẳng định về phí người mua cũng cần dè dặt hơn: nó đúng khi người mua tính đủ phí vào giá, nhưng nhà đấu giá cạnh tranh với nhau để giành người bán, và người mua có thể không hoàn toàn tính đúng.

### Ví dụ đấu giá tín phiếu đơn giản hoá, và hai tác giả tự thừa nhận điều đó

Lập luận "trừ 1 điểm lãi suất thì mọi người bỏ cao hơn 1 điểm" là minh hoạ hay cho sự bù trừ, nhưng chuyển từ trả theo giá bỏ sang giá thống nhất không phải là phép dịch chuyển đơn giản như vậy, vì nó đổi cấu trúc động cơ khuyến khích. Chú thích của tác giả nói rõ đấu giá giá thống nhất nhiều đơn vị vẫn còn chỗ cho bỏ giá chiến lược (người mua lớn có thể làm giảm lãi suất trên toàn bộ phần mình mua). Các nghiên cứu thực nghiệm về thử nghiệm của Bộ Tài chính Mỹ cho kết quả khá khiêm tốn, không cho thấy khác biệt lớn về chi phí vay, phù hợp với kết luận "không mất tiền mà đơn giản hơn" của hai tác giả. Ngoài ra bảng số trong sách có chín dòng trong khi text nói "mười" rồi "tám" mức bỏ giá, một lỗi biên tập nhỏ không ảnh hưởng tới lập luận.

### Giải thích về đặt giá phút chót là giả thuyết của hai tác giả, và còn các giải thích cạnh tranh khác

Hai tác giả cho rằng lý do tốt nhất là nhiều người không biết giá trị của mình. Các nghiên cứu thực nghiệm về eBay còn nêu những lý do khác: tránh "cuộc chiến bỏ giá" với những người bỏ tăng dần theo cảm xúc, và việc giá cuối có thể không kịp được ghi nhận khi nhiều người cùng đặt giá phút chót. So sánh giữa eBay (kết thúc ở giờ cố định, đặt giá phút chót phổ biến) và các sàn tự động kéo dài thời gian khi có giá mới (đặt giá phút chót ít hơn) cho thấy luật kết thúc là yếu tố quan trọng, một điểm khớp với tinh thần "luật chơi định hình chiến lược" của chương.

### Từ 2008, lý thuyết đấu giá đã đi xa và được ghi nhận bằng giải Nobel

Năm 2020, Paul Milgrom và Robert Wilson nhận giải Nobel kinh tế cho các đóng góp vào lý thuyết đấu giá và thiết kế thể thức mới, trong đó có đấu giá đồng thời nhiều vòng mà FCC dùng. Các cuộc đấu giá phổ tần về sau dùng những thể thức phức tạp hơn, như đấu giá theo gói (combinatorial) cho phép bỏ giá cho cả gói giấy phép, và "đấu giá khuyến khích" mà FCC dùng để mua lại phổ tần từ các đài truyền hình rồi bán lại cho các nhà mạng. Trong quảng cáo trực tuyến, một phần thị trường đã chuyển từ dạng giá thứ hai sang dạng giá thứ nhất, cho thấy các nền tảng thấy lợi ích của tính minh bạch và đơn giản quan trọng hơn tính chất "nói thật là chiến lược trội". Câu chuyện Apple cũng có phần kết đáng chú ý: Palm, người thắng trò chơi chiếm trước năm 1996, về sau lụi tàn, còn Apple quay lại thị trường thiết bị cầm tay bằng iPhone năm 2007, cho thấy thắng trò chơi chiếm trước không bảo đảm giữ được thị trường mãi.

### Quan điểm trái chiều: "hợp tác ngầm" trong đấu giá phổ tần có thể bị coi là thông đồng

Hai tác giả nói chặt chẽ thì kết quả AT&T và MCI mỗi bên lấy một giấy phép giá 1 không phải là thông đồng, vì không có thoả thuận. Nhưng trong thực tế các cuộc đấu giá phổ tần ở Mỹ, đã có trường hợp người tham gia dùng các chữ số cuối của giá bỏ như tín hiệu để "nhắn" đối thủ tránh xa một giấy phép, và cơ quan quản lý coi đó là hành vi phản cạnh tranh. Ranh giới giữa hợp tác ngầm hợp pháp và thông đồng ngầm có thể bị xử phạt là vùng xám; người thiết kế đấu giá ngày nay thường dùng giá bỏ được làm tròn, giấu danh tính người bỏ giá và giới hạn số vòng để thu hẹp chỗ cho các tín hiệu như vậy.

### Vận dụng: trước mỗi lần bỏ giá, đấu thầu hay đưa ra lời đề nghị, hãy hỏi "nếu đối phương nói đồng ý thì điều đó cho tôi biết gì?"

- **Trong doanh nghiệp.** Khi dự thầu, hãy xác định đây là đấu thầu theo giá thấp nhất, chấm điểm tổng hợp hay đàm phán, rồi chọn chiến lược tương ứng: không bao giờ bỏ thầu dưới chi phí (đã gồm lợi nhuận bình thường), và nếu đối thủ đông, biên lợi nhuận sẽ bị ép về gần 0, đúng như chú thích của hai tác giả rằng khi số người bỏ giá tăng, giá bỏ hội tụ về giá trị và toàn bộ thặng dư về tay bên tổ chức đấu giá. Khi tranh một thị trường mới với đối thủ ngang sức, hãy nhận ra mình đang ở trò chơi chiếm trước hay cuộc chiến tiêu hao: với chiếm trước, đừng chờ tới khi hoàn hảo nhưng cũng đừng ra quá sớm như Apple Newton; với tiêu hao, khoản lỗ đã chịu là chi phí chìm, và lối ra tốt nhất thường là thoả thuận như Murdoch với BSB. Khi bán tài sản, hãy chọn thể thức giúp người mua bỏ giá thẳng thắn và đề phòng các bên chia nhau các lô hàng.
- **Trong đầu tư.** Khi tham gia mua tài sản có giá trị chung (cổ phần trong đợt chào bán, bất động sản đấu giá, công ty mục tiêu), chiến thắng trong một cuộc đấu đông người là tín hiệu rằng mình có thể đã quá lạc quan; hãy hạ giá bỏ theo số người cạnh tranh và theo mức không chắc chắn của định giá. Áp dụng phép tính ACME: giá trị trung bình sau cộng hưởng không phải mức trần; mức trần phải tính trên điều kiện người bán đã chấp nhận.
- **Trong nghề nghiệp.** Khi đàm phán lương hay nhận lời mời làm việc, hãy hỏi trước: nếu công ty đồng ý ngay mức tôi đưa ra, điều đó nói gì về giá trị của tôi với họ hay về vị trí đó? Khi tham gia các cuộc thi tuyển hay xét thưởng mà "mọi người đều trả giá" (thời gian làm thêm, công sức đầu tư), hãy cân nhắc đó có phải cuộc chiến tiêu hao không, và giải thưởng có đáng với tổng chi phí không.
- **Khi đọc tin chính sách.** Ở Việt Nam, đấu giá quyền sử dụng đất, đấu giá quyền khai thác khoáng sản, đấu giá biển số xe hay đấu giá tần số viễn thông đều là các ứng dụng trực tiếp của chương. Khi có tin về những phiên đấu giá đất với giá trúng cao bất thường rồi người trúng bỏ cọc, đó có thể vừa là lời nguyền của người thắng vừa là dấu hiệu luật đấu giá để hở chỗ cho chiến lược ngoài dự kiến; khi đọc về thiết kế một phiên đấu giá tần số, câu hỏi đáng đặt ra là bán lần lượt hay đồng thời, và luật có đề phòng các doanh nghiệp chia nhau các khối tần số hay không. Khi một khoản phí hay thuế được quy định "người mua chịu", hãy nhớ ví dụ phí người mua 20%: ai thực sự gánh còn tuỳ vào việc các bên điều chỉnh giá ra sao.
