# Chương 8 — Diễn giải và thao túng thông tin (Interpreting and Manipulating Information)

**Nguồn:** Avinash K. Dixit và Barry J. Nalebuff, *The Art of Strategy: A Game Theorist's Guide to Success in Business and Life*, ấn bản đầu (W. W. Norton, 2008), Phần III, Chương 8.
**Tác giả:** Avinash K. Dixit (sinh 1944), nhà kinh tế Mỹ gốc Ấn, giáo sư danh dự Đại học Princeton; Barry J. Nalebuff (sinh 1958), giáo sư Trường Quản trị Yale. Sách kế thừa *Thinking Strategically* (1991) của cùng hai tác giả.
**Vị trí trong lập luận của cả cuốn sách:** Phần I dạy các công cụ cơ bản (suy luận ngược, thế lưỡng nan của người tù, cân bằng Nash). Phần II bàn cách thay đổi trò chơi: Chương 5 về chiến lược hỗn hợp (giữ cho đối thủ không đoán được), Chương 6 về nước đi chiến lược (cam kết, đe doạ, hứa hẹn), Chương 7 về cách làm cho các nước đi đó đáng tin. Chương 8 mở đầu Phần III (Chương 8–14, nơi các công cụ được áp dụng vào từng nhóm tình huống) và hỏi một câu yếu hơn câu của Chương 7: khi không thể buộc người khác giữ lời, làm sao ít nhất biết được điều họ nói có thật hay không? Câu trả lời là quan sát hành động có chi phí, qua hai công cụ: phát tín hiệu (signaling) và sàng lọc (screening). Chương 9 (hợp tác và phối hợp), Chương 10 (đấu giá, nơi "lời nguyền người thắng" được nhắc ở đây sẽ được giải quyết), Chương 13 (thiết kế khuyến khích khi không quan sát được nỗ lực) đều dùng lại các ý của chương này; Chương 14 có bốn tình huống tiếp nối, trong đó có lời giải cho thế khó của vua Solomon.
**Ý chính:** Hai tác giả muốn người đọc hiểu rằng **hành động nói to hơn lời nói**: lời nói của một người có lợi ích khác mình thì không đáng tin, còn một hành động chỉ đáng tin khi nó tốn kém với người nói dối hơn là với người nói thật. Ví dụ trung tâm mở đầu chương là chuyện cô Sue yêu cầu người yêu xăm tên mình lên người: hình xăm gần như không tốn gì nếu anh ta định gắn bó lâu dài, nhưng sẽ là vật chứng ngượng ngùng nếu anh ta không định cưới. Anh ta từ chối, và Sue có câu trả lời. Từ đó chương đi qua bảo hành xe cũ, thị trường "xe chanh" của Akerlof, bằng MBA như công cụ sàng lọc, thủ tục hành chính và trợ cấp bằng hiện vật, việc không phát tín hiệu cũng là tín hiệu, phản tín hiệu, gây nhiễu tín hiệu, điệp viên Ashraf Marwan, cách dùng quy tắc Bayes khi chơi poker, và kết thúc bằng phép tính chi tiết về cách hãng hàng không phân biệt giá giữa khách doanh nhân và khách du lịch.

> **Lưu ý:** Sách viết khoảng 2007–2008, nên các ví dụ thương mại mang dấu ấn thời đó: phần mềm bán qua đĩa CD gửi bưu điện, máy in laser IBM, đầu DVD Sharp với chuẩn PAL và NTSC, chương trình chuyển dư nợ của Capital One "suốt một thập kỷ từ khi lên sàn năm 1994", chế độ bảo hành của Hyundai năm 1999. Từ đó, phần mềm chủ yếu bán qua tải về và thuê bao, nhưng chiến lược tạo phiên bản (bản "lite", bản miễn phí, bản cao cấp) vẫn phổ biến hơn bao giờ hết. Về vụ Ashraf Marwan, sau khi sách in đã có thêm sách và phim nghiêng về giả thuyết ông là điệp viên thật cho Israel, nhưng câu hỏi vẫn chưa ngã ngũ. Chương có **8 chú thích chân trang** của tác giả (dấu `*` trong sách), đều đã đưa vào đúng chỗ và ghi "Chú thích của tác giả". Chương có ba hình (một công thức, một bảng xác suất trong poker, một bảng giá và chi phí của hãng hàng không); cả ba đã được dựng lại. Chương có một bài tập "Trip to the Gym" (số 5), đã đưa đáp án vào ngay sau đề. Các câu trích là bản dịch của người tổng hợp.

## Sơ đồ

### Tiểu mục "The Marrying Kind?" — người này có định kết hôn không?

```text
       Chuyện có thật: cô Sue, 37 tuổi, yêu một giám đốc điều hành rất thành
       đạt; anh ta độc thân, thông minh, nói yêu cô
                                │
                                ▼
       Sue muốn kết hôn và có con; anh ta đồng ý, nhưng bảo các con riêng
       từ cuộc hôn nhân trước chưa sẵn sàng để bố tái hôn, cần chờ
       · Sue sẵn lòng chờ nếu biết chắc "cuối đường hầm có ánh sáng"
       · không thể đòi một cam kết công khai, vì bọn trẻ sẽ biết
                                │
                                ▼
       Sue cần một TÍN HIỆU ĐÁNG TIN (credible signal)
       · đây là "họ hàng" của công cụ cam kết ở Chương 7, nhưng yếu hơn:
         không buộc anh ta giữ lời, chỉ giúp cô biết anh ta có nghiêm túc
                                │
                                ▼
       Sue đề nghị anh ta xăm tên cô, một hình xăm nhỏ, kín, không ai khác
       phải thấy
       · nếu anh ta gắn bó lâu dài: hình xăm là món quà tình yêu, gần như
         không tốn gì
       · nếu anh ta không định cưới: hình xăm là vật chứng ngượng ngùng mà
         người tình kế tiếp sẽ phát hiện
                                │
                                ▼
       Anh ta chần chừ, nên Sue ra đi. Cô gặp người khác, nay đã kết hôn và
       có con; còn anh ta thì, theo lời hai tác giả, vẫn "nằm trên đường
       băng, bị hoãn cất cánh vĩnh viễn"
```

### Tiểu mục "Tell It Like It Is?" — sao không cứ nói thật?

```text
       Vì sao không thể tin người khác nói thật? Vì nói thật có thể trái
       với lợi ích của họ
                                │
                                ▼
       Khi lợi ích trùng nhau, lời nói đáng tin
       · bạn gọi bít tết chín tái; người phục vụ muốn làm bạn vui, nên cứ
         tin rằng bạn thật sự muốn chín tái
       Khi lợi ích lệch nhau, lời nói kém tin hơn
       · bạn hỏi nên gọi món gì, rượu gì: người phục vụ có thể hướng bạn
         tới món đắt để có tiền boa cao hơn
                                │
                                ▼
       Câu của nhà toán học G. H. Hardy (theo C. P. Snow): nếu Tổng giám mục
       Canterbury nói tin có Chúa thì đó chỉ là công việc; nếu ông nói
       không tin thì có thể tin ông nói thật
       · tương tự: khi người phục vụ khuyên món bít tết rẻ hay chai rượu
         Chile giá hời, bạn có mọi lý do để tin
       · khi anh ta khuyên món đắt, có thể anh ta cũng đúng, nhưng khó biết
                                │
                                ▼
       Xung đột lợi ích càng lớn, lời nhắn càng kém tin
       · cầu thủ sút phạt đền (Chương 5) nói trước "tôi sẽ sút bên phải"
       · thủ môn không nên tin, nhưng cũng KHÔNG nên suy ra bên trái: cầu
         thủ có thể lừa ở tầng thứ hai, "nói dối bằng cách nói thật"
       → với người có lợi ích hoàn toàn đối nghịch: bỏ qua hẳn lời họ nói,
         không coi là đúng, cũng không coi điều ngược lại là đúng; hãy tìm
         cân bằng của trò chơi thật và chơi theo đó
                                │
                                ▼
       Chính trị gia, nhà quảng cáo, trẻ con đều là người chơi có lợi ích
       riêng. Hai câu hỏi của chương:
       · diễn giải thông tin từ những nguồn có lợi ích riêng thế nào?
       · làm sao để lời mình được tin khi biết người khác sẽ nghi ngờ?
```

### Tiểu mục "King Solomon's Dilemma" — thế khó của vua Solomon

```text
       Hai người phụ nữ cùng nhận là mẹ của một đứa bé (Kinh Thánh, Các Vua
       quyển 1, 3:24–28)
                                │
                                ▼
       Vua Solomon ra lệnh: mang gươm tới, chặt đứa bé làm đôi, mỗi người
       một nửa
       · người mẹ thật xin vua: hãy trao đứa bé cho bà kia, đừng giết nó
       · người kia nói: không ai được nó cả, cứ chặt đi
       · vua xử: trao đứa bé cho người thứ nhất, bà ấy là mẹ nó
                                │
                                ▼
       Hai tác giả hỏi: nếu người mẹ giả hiểu trò này thì sao? Mưu của vua
       sẽ thất bại
       · người mẹ giả mắc một lỗi chiến lược: chính câu "cứ chặt đi" làm
         bà khác người mẹ thật
       · lẽ ra bà chỉ cần nhắc lại đúng lời người kia; hai người nói giống
         nhau thì vua không phân biệt được
                                │
                                ▼
       → Vua may hơn là khôn; mưu chỉ thành nhờ lỗi của người mẹ giả.
         Câu hỏi vua lẽ ra nên làm gì được để dành làm tình huống ở
         Chương 14
```

### Tiểu mục "Devices for Manipulating Information" — các công cụ thao túng thông tin

```text
       Chuyện của Sue và Solomon có mặt trong hầu hết các tương tác chiến
       lược: có người biết nhiều hơn về điều ảnh hưởng tới kết quả của tất
       cả mọi người
       · có người biết mà muốn GIẤU (như người mẹ giả)
       · có người biết mà muốn LỘ sự thật (như người mẹ thật)
       · người biết ít (như vua) muốn KHAI THÁC được sự thật
                                │
                                ▼
       NGUYÊN TẮC CHUNG: hành động (kể cả hình xăm) nói to hơn lời nói
       · hãy nhìn người khác LÀM gì, không phải họ NÓI gì
       · biết người khác diễn giải hành động của mình như vậy, mỗi người
         sẽ chọn hành động theo lượng thông tin nó để lộ
       · hai tác giả mượn và bẻ một câu thơ của T. S. Eliot ("Bản tình ca
         của J. Alfred Prufrock"): phải luôn "chuẩn bị một gương mặt để gặp
         những gương mặt bạn gặp"
       · hai tác giả coi đây là một trong những bài học quan trọng nhất của
         lý thuyết trò chơi
                                │
                                ▼
       BA CÔNG CỤ
       ┌────────────────────┬──────────────────────────────────────────┐
       │ Phát tín hiệu      │ người biết nhiều chọn hành động làm lộ   │
       │ (signaling)        │ thông tin có lợi cho mình                │
       ├────────────────────┼──────────────────────────────────────────┤
       │ Gây nhiễu tín hiệu │ người biết nhiều hành động để giảm hay   │
       │ (signal jamming)   │ xoá thông tin bất lợi bị lộ, thường bằng │
       │                    │ cách bắt chước hành vi hợp với hoàn cảnh │
       │                    │ khác                                     │
       ├────────────────────┼──────────────────────────────────────────┤
       │ Sàng lọc           │ người biết ít đặt ra tình huống mà người │
       │ (screening)        │ kia sẽ chọn hành động khác nhau tuỳ thông│
       │                    │ tin họ có; hành động (hay không hành     │
       │                    │ động) làm lộ thông tin. Ví dụ: yêu cầu   │
       │                    │ hình xăm của Sue                         │
       └────────────────────┴──────────────────────────────────────────┘
       · Chú thích của tác giả: đôi khi chính hành động cũng khó quan sát;
         khó nhất là chất lượng nỗ lực làm việc, nên phải xét theo kết quả
         và thiết kế cơ chế khuyến khích (Chương 13)
                                │
                                ▼
       ĐIỀU KIỆN để một hành động là tín hiệu hiệu quả: người nói dối có
       lý trí không thể bắt chước được nó, tức nó phải lỗ khi sự thật khác
       với điều bạn muốn truyền đạt
       · poker (Chương 1): tỷ lệ pha trộn cược tối ưu khác nhau với bài
         mạnh và bài yếu, nên cược vẫn để lộ một phần thông tin
                                │
                                ▼
       Thông tin quan trọng nhất bạn có mà người khác không có: đặc điểm
       của chính bạn (năng lực, sở thích, ý định)
       · hãng luật chiêu đãi thực tập sinh mùa hè thật xa hoa: "chúng tôi
         coi trọng bạn; nếu không, chúng tôi đã chẳng chi nhiều thế". Điều
         quan trọng là cái GIÁ, không phải đồ ăn có ngon hay không
       · bằng tốt nghiệp đại học tốt: chủ lao động cần biết năng lực tư duy
         và học hỏi chung; người tốt nghiệp như nói "nếu tôi kém hơn, liệu
         tôi có tốt nghiệp loại ưu ở Princeton không?"
                                │
                                ▼
       NHƯNG phát tín hiệu có thể thành cuộc đua chuột (rat race)
       · người kém học thêm một chút để được nhầm là người giỏi
       · người giỏi phải học thêm nữa để tách mình ra
       · cuối cùng việc văn phòng đơn giản cũng đòi bằng thạc sĩ; năng lực
         thật không đổi, chỉ giáo sư đại học được lợi
       → cá nhân hay doanh nghiệp không tự dừng được; cần chính sách công
```

### Tiểu mục "Is the Quality Guaranteed?" — chất lượng có được bảo đảm không?

```text
       Bạn mua xe cũ, thấy hai chiếc có vẻ tốt như nhau; chiếc thứ nhất có
       bảo hành, chiếc thứ hai không. Bạn thích chiếc thứ nhất và sẵn lòng
       trả cao hơn, vì hai lý do:
       · nếu hỏng thì được sửa miễn phí (nhưng mất thời gian, phiền toái
         không được đền)
       · quan trọng hơn: bạn tin chiếc có bảo hành ít hỏng hơn ngay từ đầu
                                │
                                ▼
       Vì sao? Hãy nghĩ theo chiến lược của người bán
       · người bán biết rõ chất lượng xe hơn bạn
       · xe tốt: bảo hành gần như không tốn gì
       · xe tồi: bảo hành tốn kém nhiều
       → xe càng tồi, bảo hành càng dễ là món lỗ, kể cả khi đã tính giá
         cao hơn mà xe có bảo hành bán được
                                │
                                ▼
       Bảo hành là một lời tuyên bố ngầm: "tôi biết xe đủ tốt để có thể
       bảo hành". Người bán "đặt tiền vào chỗ lời nói của mình"
       · tách người chỉ "nói suông" khỏi người "nói được làm được"
                                │
                                ▼
       ĐỊNH NGHĨA: tín hiệu (signal) là hành động nhằm truyền thông tin
       riêng của một người chơi cho người khác. Muốn đáng tin, hành động
       phải là tối ưu với người chơi NẾU VÀ CHỈ NẾU họ có thông tin đó
                                │
                                ▼
       VÍ DỤ SỐ của hai tác giả
       · chi phí sửa chữa kỳ vọng: xe tốt 500 USD, xe tồi 2.000 USD
       · giá xe có bảo hành cao hơn xe không bảo hành 800 USD
       → người bán chịu bảo hành với mức chênh 800 USD hẳn biết xe mình tốt
       · bạn có thể chủ động: "tôi trả thêm 800 USD nếu anh bảo hành"
       · mọi mức giá bảo hành trên 500 và dưới 2.000 USD đều khiến người
         bán xe tốt và xe tồi chọn khác nhau; hai bên mặc cả trong khoảng
         đó (bạn đưa 600, người bán đòi 1.800)
                                │
                                ▼
       PHÁT TÍN HIỆU và SÀNG LỌC
       · người bán chủ động đưa bảo hành: phát tín hiệu
       · người mua chủ động đòi bảo hành: sàng lọc
       · hai cách có tác dụng tương tự, dù cân bằng có thể khác nhau về kỹ
         thuật; dùng cách nào tuỳ bối cảnh lịch sử, văn hoá, thể chế
                                │
                                ▼
       PHÉP THỬ: người bán mời bạn đưa xe cho thợ kiểm tra. Có phải tín
       hiệu đáng tin không? KHÔNG
       · nếu thợ thấy lỗi và bạn bỏ đi, người bán không mất gì so với
         trước, dù xe tốt hay tồi; người bán xe tồi cũng mời được
       · Chú thích của tác giả: người bán tự trả tiền kiểm tra và đưa giấy
         chứng nhận cũng đáng ngờ (thợ có thể thông đồng). Muốn đáng tin,
         người bán nên cam kết hoàn tiền kiểm tra cho bạn nếu thợ phát hiện
         lỗi; điều đó tốn kém hơn với người bán xe tồi
                                │
                                ▼
       Bảo hành phải thi hành được
       · người bán tư nhân có thể chuyển nhà, không có tiền, kiện thì tốn
       · đại lý ở lâu trong nghề, có danh tiếng cần giữ (dù cũng có thể
         chối là bạn bảo dưỡng kém hay lái ẩu)
       → tiết lộ chất lượng qua bảo hành khó hơn nhiều khi mua bán tư nhân
                                │
                                ▼
       HYUNDAI: cuối thập niên 1990 đã nâng chất lượng xe nhưng người tiêu
       dùng Mỹ chưa nhận ra. Năm 1999, hãng đưa ra bảo hành chưa từng có:
       10 năm hoặc 100.000 dặm cho hệ truyền động, 5 năm hoặc 50.000 dặm
       cho phần còn lại
```

### Tiểu mục "A Little History" — một chút lịch sử

```text
       George Akerlof dùng thị trường xe cũ trong bài báo kinh điển cho
       thấy thông tin bất cân xứng có thể làm thị trường thất bại
                                │
                                ▼
       Hai loại xe: "xe chanh" (lemon, xe tồi) và "xe đào" (peach, xe tốt)
       ┌──────────┬──────────────────────┬────────────────────────┐
       │ Loại xe  │ Người bán chịu bán   │ Người mua chịu trả     │
       │          │ với giá tối thiểu    │ tối đa                 │
       ├──────────┼──────────────────────┼────────────────────────┤
       │ Xe chanh │ 1.000 USD            │ 1.500 USD              │
       │ Xe đào   │ 3.000 USD            │ 4.000 USD              │
       └──────────┴──────────────────────┴────────────────────────┘
       · nếu ai cũng thấy chất lượng: mọi xe đều được bán, xe chanh giá từ
         1.000 tới 1.500, xe đào từ 3.000 tới 4.000
                                │
                                ▼
       Nếu chỉ người bán biết chất lượng, người mua chỉ biết một nửa là xe
       chanh, một nửa là xe đào:
       · người mua trả tối đa ½ × (1.500 + 4.000) = 2.750 USD
         (công thức dựng lại từ sách)
       · chủ xe đào không bán với giá 2.750 (dưới 3.000), nên chỉ còn xe
         chanh được rao bán; người mua biết vậy nên chỉ trả tối đa 1.500
       → thị trường xe đào sụp đổ hoàn toàn, dù có người mua sẵn lòng trả
         mức giá mà người bán xe đào chấp nhận
       · cách nhìn "Pangloss" (thị trường luôn là thể chế tốt nhất, hiệu
         quả nhất) đổ vỡ
       · Chú thích của tác giả: người mua ngây thơ trả 2.750 USD vì tưởng
         đó là giá trị trung bình sẽ mắc "lời nguyền người thắng": việc
         người bán chịu bán chứng tỏ xe kém hơn dự đoán (Chương 10 bàn cách
         tránh)
                                │
                                ▼
       Dixit là nghiên cứu sinh khi bài của Akerlof ra đời; ai cũng thấy
       đó là ý tưởng cách mạng. Chỉ có một vấn đề: hầu hết nghiên cứu sinh
       đều lái xe cũ mua của tư nhân, và phần lớn không phải xe chanh
                                │
                                ▼
       Thị trường có những cách tự đối phó:
       · người hiểu máy móc tự xem xe, hoặc nhờ bạn xem
       · hỏi lịch sử xe qua mạng lưới bạn bè chung
       · nhiều chủ xe tốt buộc phải bán với gần như bất kỳ giá nào: chuyển
         đi xa, ra nước ngoài, cần xe to hơn khi gia đình đông thêm
                                │
                                ▼
       Bước đột phá khái niệm tiếp theo:
       · Michael Spence: PHÁT TÍN HIỆU; tính chất then chốt là kết quả của
         cùng một hành động khác nhau với những người chơi có thông tin
         khác nhau
         Chú thích của tác giả: nên đọc nguyên bản "Market Signaling" của
         Spence (1974); ý tương tự trong tâm lý học có ở cuốn "The
         Presentation of Self in Everyday Life" của Erving Goffman (1959)
       · James Mirrlees, William Vickrey, rồi Michael Rothschild và Joseph
         Stiglitz (thị trường bảo hiểm): SÀNG LỌC. Người mua bảo hiểm biết
         rủi ro của mình rõ hơn công ty; công ty đưa ra một thực đơn gói có
         mức khấu trừ và đồng chi trả khác nhau; người rủi ro thấp chọn gói
         phí thấp nhưng tự chịu nhiều rủi ro hơn, nên lựa chọn làm lộ loại
         rủi ro. Ý này giải thích cả các điều kiện kèm vé giảm giá máy bay
                                │
                                ▼
       LỰA CHỌN NGƯỢC (adverse selection), tên gọi từ ngành bảo hiểm
       · hợp đồng bảo hiểm nhân thọ phí 5 xu cho mỗi đô la bảo hiểm đặc
         biệt hấp dẫn người có tỷ lệ tử vong trên 5%
       · người rủi ro cao mua nhiều hơn, mua hợp đồng lớn hơn
       · tăng giá còn tệ hơn: người rủi ro thấp bỏ đi, chỉ còn ca xấu
       → "hiệu ứng Groucho Marx": ai chịu mua bảo hiểm với giá đó thì
         chính là người bạn không muốn bảo hiểm
       · ở ví dụ của Akerlof: người mua không trả giá khác nhau cho từng
         xe được, nên việc bán hấp dẫn riêng chủ xe chanh
                                │
                                ▼
       LỰA CHỌN THUẬN LỢI (positive selection): CAPITAL ONE
       · lên sàn năm 1994; một thập kỷ tăng trưởng kép 40% mỗi năm, chưa
         kể sáp nhập và mua lại
       · sáng kiến: khách chuyển dư nợ từ thẻ khác sang được lãi suất thấp
         hơn (ít nhất trong một thời gian)
       · ba loại khách thẻ tín dụng:
         – trả đủ hằng tháng, không vay (maxpayer): công ty LỖ, vì phí thu
           từ người bán chỉ vừa đủ bù khoản vay miễn phí một tháng, không
           đủ bù chi phí lập hoá đơn, gian lận, rủi ro khách ly hôn hay mất
           việc rồi vỡ nợ
         – vay rồi trả dần (revolver): LÃI nhiều nhất
         – vay rồi không trả (deadbeat): LỖ
       · ai thấy ưu đãi chuyển dư nợ hấp dẫn? Không phải người không vay,
         không phải người định quỵt nợ, mà chính người đang nợ nhiều và
         định trả
       → ưu đãi tự lọc ra loại khách có lãi; ngược với hiệu ứng Groucho
         Marx: ai nhận lời mời chính là người bạn muốn
```

### Tiểu mục "Screening and Signaling" — sàng lọc và phát tín hiệu (kèm khung "One Reason to Get an MBA")

```text
       Bạn là trưởng phòng nhân sự, cần tuyển người có tài quản lý bẩm sinh
       · ứng viên biết mình có tài hay không, bạn thì không
       · người giỏi tạo vài triệu USD lợi nhuận; người kém gây lỗ lớn rất
         nhanh
       · quần áo, thái độ, thư giới thiệu của người thân: ai cũng bắt chước
         được, nên vô dụng
                                │
                                ▼
       Bằng MBA làm công cụ sàng lọc. Số liệu giả định của hai tác giả:
       · chi phí lấy bằng: khoảng 200.000 USD (học phí cộng lương bỏ lỡ)
       · lương của người không có MBA: 50.000 USD/năm
       · khấu hao chi phí MBA trong 5 năm: cần thêm 40.000 USD/năm
       → phải trả người có MBA ít nhất 90.000 USD/năm
                                │
                                ▼
       MBA chỉ phân loại được nếu người có tài lấy bằng DỄ hơn hoặc RẺ hơn
       · giả định: người có tài chắc chắn tốt nghiệp; người không có tài
         chỉ có 50% khả năng tốt nghiệp
       · bạn trả 100.000 USD cho người có MBA
       · người có tài: thêm 50.000 USD/năm, đủ bù chi phí, nên đi học
       · người không có tài: thêm kỳ vọng 50% × 50.000 = 25.000 USD/năm,
         không đủ bù 40.000 USD/năm, nên không đi học
       → ai có MBA thì có tài; nhóm sinh viên tốt nghiệp tự chia thành hai
         nhóm đúng như bạn muốn. Lý do: chi phí dùng công cụ THẤP HƠN với
         người bạn muốn thu hút so với người bạn muốn tránh
                                │
                                ▼
       Nghịch lý: lẽ ra công ty có thể tuyển sinh viên MBA ngay ngày đầu
       nhập học, vì chỉ người có tài mới đăng ký
       · nhưng nếu ai cũng làm thế, người không có tài sẽ đăng ký rồi bỏ
         học đầu tiên; sàng lọc chỉ hoạt động khi người ta học hết hai năm
                                │
                                ▼
       CHI PHÍ CỦA SÀNG LỌC: nếu nhận ra người có tài trực tiếp, bạn chỉ
       cần trả hơn 50.000 USD; nay phải trả hơn 90.000 USD
       · 40.000 USD/năm × 5 năm là cái giá của việc bạn thiếu thông tin
       · NGOẠI ỨNG THÔNG TIN: chính sự tồn tại của người không có tài gây
         ngoại ứng tiêu cực; người có tài trả trước, rồi công ty trả bằng
         lương cao hơn, nên cuối cùng công ty chịu
                                │
                                ▼
       Có đáng trả không? So với tuyển ngẫu nhiên với lương 50.000 USD:
       · giả sử 25% không có tài, mỗi người gây lỗ 1 triệu USD trước khi bị
         phát hiện, thì tuyển ngẫu nhiên lỗ kỳ vọng 250.000 USD mỗi người
       · sàng lọc bằng MBA tốn 200.000 USD (40.000 × 5 năm)
       → sàng lọc rẻ hơn; trên thực tế tỷ lệ có tài thấp hơn và thiệt hại
         lớn hơn, nên lý lẽ dùng sàng lọc còn mạnh hơn (hai tác giả đùa
         thêm: hy vọng MBA cũng dạy được vài kỹ năng hữu ích)
                                │
                                ▼
       KHUNG "MỘT LÝ DO ĐỂ HỌC MBA"
       · chủ lao động có thể e ngại tuyển và đào tạo một phụ nữ trẻ rồi cô
         nghỉ việc để sinh con (phân biệt đối xử dù hợp pháp hay không)
       · MBA là tín hiệu đáng tin rằng cô định đi làm vài năm: nếu định
         nghỉ sau một năm, cô đã đi làm ba năm thay vì bỏ hai năm đi học;
         cần ít nhất khoảng 5 năm mới thu hồi được chi phí MBA
                                │
                                ▼
       Các cách nhận ra tài năng khác (chọn cách rẻ nhất):
       · thử việc, giao dự án nhỏ có giám sát (tốn lương và vài khoản lỗ)
       · hợp đồng trả lương dồn về sau hoặc theo kết quả: người có tài tự
         tin sẽ nhận, người khác chọn việc chắc chắn 50.000 USD
       · quan sát người quản lý ở công ty khác rồi lôi kéo người giỏi
                                │
                                ▼
       Cạnh tranh giữa các công ty đẩy lương người có tài lên trên mức tối
       thiểu 90.000 USD, nhưng không thể vượt 130.000 USD
       · Chú thích của tác giả: ở mức 130.000 USD, người không có tài một
         nửa số lần lấy được bằng và thêm 80.000 USD, tức kỳ vọng 40.000
         USD, vừa đủ bù chi phí học trong 5 năm
       · vượt mức đó, nhóm MBA bị "nhiễm" người không có tài mà may mắn đỗ
                                │
                                ▼
       MBA CŨNG LÀ CÔNG CỤ PHÁT TÍN HIỆU, do ứng viên chủ động
       · bạn đang tuyển ngẫu nhiên với giá 50.000 USD và chịu lỗ do người
         kém; một ứng viên có MBA tới, giải thích bằng MBA chứng minh tài
         năng, và đề nghị làm việc nếu được trả trên 75.000 USD
       · nếu khả năng phân loại của trường kinh doanh là rõ, đây là đề nghị
         hấp dẫn với bạn
       → sàng lọc và phát tín hiệu do hai bên khác nhau khởi xướng, nhưng
         cùng một nguyên lý: hành động phân biệt các loại người chơi
```

### Tiểu mục "Signaling via Bureaucracy" — phát tín hiệu qua thủ tục hành chính

```text
       Workers' Compensation: hệ thống bảo hiểm ở Mỹ chi trả điều trị chấn
       thương, bệnh tật do công việc
       · người quản lý khó biết mức độ nặng (đôi khi cả việc có bị thương
         hay không) và chi phí điều trị
       · người lao động và bác sĩ biết rõ hơn nhưng có động cơ phóng đại
       · ước tính 20% hồ sơ trở lên có gian lận
       · Stan Long (CEO công ty bảo hiểm nhà nước của bang Oregon): "Nếu
         bạn phát tiền cho bất kỳ ai xin, sẽ có rất nhiều người xin tiền"
                                │
                                ▼
       Cách 1: giám sát bí mật (thấy người khai đau lưng nặng đang khuân đồ
       nặng thì bác hồ sơ và truy tố), nhưng cách này tốn kém
                                │
                                ▼
       Cách 2: SÀNG LỌC bằng thủ tục
       · bắt điền nhiều mẫu đơn, ngồi cả ngày chờ nói chuyện năm phút với
         một viên chức
       · người khoẻ, kiếm được tiền nếu đi làm cả ngày: chờ đợi quá tốn
       · người thật sự bị thương, không làm được: chờ được
       → sự chậm chạp, phiền hà của bộ máy hành chính, vốn bị coi là bằng
         chứng chính phủ kém hiệu quả, đôi khi là chiến lược hợp lý để đối
         phó với vấn đề thông tin
                                │
                                ▼
       TRỢ CẤP BẰNG HIỆN VẬT có tác dụng tương tự
       · phát tiền mua xe lăn: nhiều người giả tật
       · phát thẳng xe lăn: người không cần phải vất vả bán lại trên thị
         trường đồ cũ với giá thấp, nên ít người giả
       · nhà kinh tế thường cho rằng tiền mặt tốt hơn hiện vật (người nhận
         tự chọn cách tiêu tốt nhất); nhưng khi thông tin bất cân xứng,
         hiện vật có thể tốt hơn vì nó là công cụ sàng lọc
```

### Tiểu mục "Signaling by Not Signaling" — không phát tín hiệu cũng là tín hiệu

```text
       Sherlock Holmes trong truyện "Silver Blaze": điều kỳ lạ là con chó
       KHÔNG sủa trong đêm, nghĩa là kẻ đột nhập là người quen
                                │
                                ▼
       Nếu người khác biết bạn có cơ hội làm một việc thể hiện điểm tốt của
       mình mà bạn không làm, họ sẽ hiểu là bạn không có điểm tốt đó
       · bạn vô tình bỏ qua cũng không giúp gì cho bạn
       · thường là tin xấu, nhưng không phải luôn luôn
                                │
                                ▼
       ĐIỂM ĐẠT/KHÔNG ĐẠT (pass/fail) Ở ĐẠI HỌC MỸ
       · nhiều sinh viên tưởng điểm P sẽ được hiểu là điểm đạt trung bình
         của thang chữ; với tình trạng lạm phát điểm, ít nhất là B+, nhiều
         khả năng A–
       · trường sau đại học và chủ lao động đọc bảng điểm chiến lược hơn:
         – người chắc được A+ có động cơ học lấy điểm chữ để nổi bật
         – nhóm chọn pass/fail mất phần trên cùng; trung bình nhóm còn B+
         – người chắc được A lại có động cơ chọn điểm chữ; nhóm mất thêm
           phần trên
         – quá trình tiếp diễn tới khi chủ yếu chỉ người dự đoán được C hay
           tệ hơn mới chọn pass/fail
       → người đọc bảng điểm hiểu điểm P theo cách đó; sinh viên khá giỏi
         không nghĩ ra điều này sẽ chịu hậu quả
                                │
                                ▼
       JOHN, người bạn giỏi thương lượng mua bán doanh nghiệp, xây mạng
       lưới báo rao vặt toàn cầu qua không dưới 100 thương vụ mua lại
       · lần đầu bán công ty, ông được quyền cùng đầu tư vào mọi thương vụ
         mua lại mới mà ông mang tới cho bên mua
       · Chú thích của tác giả: chữ "lần đầu" có lý do. Bên mua là Cendant,
         nạn nhân của vụ gian lận kế toán ở CUC, một công ty nó mua lại; khi
         cổ phiếu Cendant sụp, John mua lại được công ty của mình với giá
         rẻ
       · John lập luận: quyền cùng đầu tư giúp bên mua yên tâm là không trả
         giá quá cao
       · bên mua đi thêm một bước: nếu John KHÔNG cùng đầu tư, họ sẽ coi
         đó là dấu hiệu xấu và có lẽ bỏ thương vụ
       → quyền được đầu tư thực chất thành nghĩa vụ phải đầu tư. Mọi việc
         bạn làm đều phát tín hiệu, kể cả việc không phát tín hiệu
```

### Tiểu mục "Countersignaling" — phản tín hiệu (kèm câu đố "A Trip to the Bar")

```text
       Tưởng rằng ai phát được tín hiệu thì nên phát. Nhưng nhiều người có
       khả năng phát nhất lại không làm. Feltovich, Harbaugh và To liệt kê:
       · người mới giàu khoe của; người giàu lâu đời chê việc khoe khoang
       · quan chức nhỏ khoe quyền vặt; người thật sự quyền lực tỏ ra rộng
         lượng
       · người học vấn trung bình viết chữ đều đặn; người học cao thường
         viết nguệch ngoạc
       · học sinh trung bình trả lời câu hỏi dễ; học sinh giỏi nhất ngại
         chứng tỏ mình biết chuyện vặt
       · người quen lịch sự lờ đi khuyết điểm của bạn; bạn thân trêu chọc
         chính khuyết điểm đó để tỏ sự thân thiết
       · người năng lực vừa phải tìm bằng cấp chính thức; người tài thường
         không nhắc tới bằng cấp dù đã có
       · người danh tiếng trung bình cãi lại lời buộc tội; người rất được
         kính trọng thấy trả lời là hạ mình
                                │
                                ▼
       Ý chính: có lúc cách tốt nhất để thể hiện mình là từ chối chơi trò
       phát tín hiệu
                                │
                                ▼
       VÍ DỤ HỢP ĐỒNG TIỀN HÔN NHÂN (prenup), ba loại bạn đời: kẻ đào mỏ,
       người khó đoán ("dấu hỏi"), người yêu thật lòng
       · một người đề nghị ký prenup: ký là rẻ nếu yêu thật, đắt nếu vì
         tiền
       · người kia đáp: "anh/em phân biệt được người yêu thật với kẻ đào
         mỏ; chỉ có loại dấu hỏi làm anh/em lẫn lộn (lúc nhầm kẻ đào mỏ với
         dấu hỏi, lúc nhầm dấu hỏi với người yêu thật). Nếu tôi ký, tức là
         tôi thấy cần tách mình khỏi kẻ đào mỏ, tức tôi là dấu hỏi. Vậy tôi
         không ký để anh/em thấy tôi là người yêu thật"
                                │
                                ▼
       Đó có phải cân bằng không?
       · nếu kẻ đào mỏ và người yêu thật không ký, dấu hỏi ký: ai ký bị coi
         là dấu hỏi; ai không ký chỉ có thể là đào mỏ hoặc yêu thật, và
         người kia phân biệt được hai loại này
       · nếu dấu hỏi cũng không ký: họ bị coi là đào mỏ hoặc yêu thật; tốt
         hay xấu tuỳ họ dễ bị nhầm với loại nào hơn; nếu dễ bị coi là đào
         mỏ hơn thì không ký là ý tồi
                                │
                                ▼
       Bài học lớn: ta có cách khác để biết loại người ngoài tín hiệu họ
       phát; chính việc phát tín hiệu cho thấy họ cần tách mình khỏi một
       loại khác. Có lúc tín hiệu mạnh nhất là cho thấy mình không cần phát
       tín hiệu
       · Chú thích của tác giả: duy nhất một lần, một ứng viên trợ lý giáo
         sư mặc quần jeans tới buổi thuyết trình xin việc. Hai tác giả nghĩ
         ngay: chỉ thiên tài mới dám không mặc com-lê. Sau mới biết hãng
         hàng không làm thất lạc hành lý của anh ta
       · Sylvia Nasar về John Nash: theo Fagi Levinson, người "mẹ" của khoa
         toán MIT, nhà toán học tầm thường phải tuân thủ khuôn phép, còn
         người giỏi thì làm gì cũng được
                                │
                                ▼
       NGHIÊN CỨU HỘP THƯ THOẠI (Harbaugh và To), ở 26 trường thuộc hệ
       thống University of California và California State University:
       · ở trường có chương trình tiến sĩ: dưới 4% nhà kinh tế xưng học vị
         trong lời chào hộp thư thoại
       · ở trường không có chương trình tiến sĩ: 27%
       · tất cả đều có bằng tiến sĩ; nhắc học vị cho thấy bạn cần bằng cấp
         để phân biệt mình. Hai tác giả đùa: cứ gọi chúng tôi là Avinash và
         Barry
                                │
                                ▼
       CÂU ĐỐ "A TRIP TO THE BAR" (không có đáp án, người đọc tự chấm)
       · buổi hẹn đầu với người bạn thấy hấp dẫn; không có cơ hội thứ hai
       · đối phương biết ấn tượng có thể làm giả, nên bạn cần tín hiệu đáng
         tin về phẩm chất của mình
       · đồng thời bạn muốn sàng lọc đối phương, xem sức hút ban đầu có nền
         tảng bền vững không
       → hãy nghĩ ra chiến lược phát tín hiệu và sàng lọc tốt
```

### Tiểu mục "Signal Jamming" — gây nhiễu tín hiệu

```text
       Mua xe cũ của chủ trước, bạn muốn biết họ giữ gìn xe thế nào
       · xe được rửa, đánh bóng, hút bụi thảm có vẻ là dấu hiệu chăm xe
       · nhưng chủ cẩu thả cũng làm được khi rao bán, và chi phí rửa xe với
         họ không cao hơn với chủ cẩn thận, nên tín hiệu không phân loại
         được
       · như ví dụ MBA: phải có CHÊNH LỆCH CHI PHÍ thì tín hiệu mới hiệu quả
                                │
                                ▼
       Có chênh lệch nhỏ: chủ cẩn thận tự hào và thích rửa xe; chủ cẩu thả
       bận rộn, khó dành thời gian. Chênh lệch nhỏ có đủ không? Tuỳ tỷ lệ
       hai loại chủ xe trong dân số
                                │
                                ▼
       ┌──────────────────────┬────────────────────────────────────────┐
       │ Tỷ lệ chủ cẩu thả    │ Kết quả                                │
       ├──────────────────────┼────────────────────────────────────────┤
       │ NHỎ                  │ xe sạch gây ấn tượng tốt (khả năng chủ │
       │                      │ cẩn thận cao) → cả chủ cẩu thả cũng rửa│
       │                      │ xe → CÂN BẰNG GỘP (pooling): mọi loại  │
       │                      │ làm như nhau, hành động không mang     │
       │                      │ thông tin; xe bẩn là dấu hiệu chắc chắn│
       │                      │ của chủ cẩu thả                        │
       ├──────────────────────┼────────────────────────────────────────┤
       │ LỚN                  │ không thể gộp: nếu ai cũng rửa, xe sạch│
       │                      │ không gây ấn tượng, chủ cẩu thả chẳng  │
       │                      │ rửa. Không thể tách: nếu không chủ cẩu │
       │                      │ thả nào rửa, một người rửa sẽ được coi │
       │                      │ là cẩn thận, nên đáng rửa. → mỗi chủ   │
       │                      │ cẩu thả dùng CHIẾN LƯỢC HỖN HỢP, rửa xe│
       │                      │ với một xác suất → BÁN TÁCH BIỆT       │
       │                      │ (semi-separating)                      │
       └──────────────────────┴────────────────────────────────────────┘
       · đối lập với cân bằng gộp là CÂN BẰNG TÁCH BIỆT (separating): một
         loại phát tín hiệu, loại kia không, hành động nhận diện đúng loại
                                │
                                ▼
       Ở trường hợp bán tách biệt:
       · người mua biết tỷ lệ pha trộn, suy ra xác suất chủ xe sạch là chủ
         cẩn thận, và trả giá theo xác suất đó
       · mức giá phải sao cho chủ cẩu thả bàng quan giữa tốn chút công rửa
         xe và để bẩn (bị nhận ra, bán giá thấp hơn)
       · cần công thức QUY TẮC BAYES (Bayes' Rule) để suy xác suất của các
         loại từ hành động quan sát được
```

### Tiểu mục "Bodyguard of Lies" — vệ sĩ bằng những lời nói dối

```text
       Churchill nói với Stalin tại Hội nghị Tehran 1943: thời chiến, sự
       thật quý giá đến mức luôn phải có một đoàn vệ sĩ bằng lời nói dối
                                │
                                ▼
       Chuyện hai thương gia đối thủ gặp nhau ở ga Warsaw
       · "Anh đi đâu?" — "Đi Minsk."
       · "Đi Minsk à? Anh trơ thật! Tôi biết anh nói đi Minsk vì muốn tôi
         tin anh đi Pinsk. Nhưng tôi biết anh THẬT SỰ đi Minsk. Vậy sao anh
         lại nói dối tôi?"
                                │
                                ▼
       Lời nói dối hay nhất: nói thật để không được tin
       · ASHRAF MARWAN, con rể Tổng thống Ai Cập Nasser, người liên lạc của
         ông với cơ quan tình báo; tự nguyện làm việc cho Mossad (Israel),
         được xác nhận là nguồn thật
       · tháng 4/1973: Marwan gửi mật mã "Củ cải" (Radish), nghĩa là chiến
         tranh sắp nổ ra; Israel gọi hàng nghìn quân dự bị, tốn hàng chục
         triệu, rồi hoá ra là báo động giả
       · ngày 5/10/1973: lại "Củ cải": Ai Cập và Syria sẽ đồng loạt tấn
         công ngày hôm sau, ngày lễ Yom Kippur, lúc hoàng hôn
       · lần này trưởng tình báo quân đội cho Marwan là điệp viên hai mang
         và coi tin này là bằng chứng chiến tranh CHƯA tới
       · cuộc tấn công nổ ra lúc 2 giờ chiều, suýt tràn ngập quân Israel;
         tướng Zeira, trưởng tình báo, mất chức
       · 27/6/2007: Marwan chết sau cú ngã đáng ngờ từ ban công căn hộ tầng
         bốn ở Mayfair, London. Ông là điệp viên tốt nhất của Israel hay
         điệp viên hai mang tài giỏi của Ai Cập: vẫn chưa rõ
                                │
                                ▼
       Bài học
       · với chiến lược hỗn hợp, không thể lừa đối thủ mọi lần, chỉ có thể
         giữ cho họ phải đoán và lừa được đôi lần
       · với người muốn đánh lừa mình: tốt nhất là bỏ qua lời họ nói, không
         tin nguyên văn, cũng không suy ra điều ngược lại
       · nhưng HÀNH ĐỘNG của họ vẫn mang thông tin: tỷ lệ pha trộn trong
         cân bằng phụ thuộc kết quả của họ, nên quan sát nước đi giúp suy
         ra lợi ích thật của đối thủ
                                │
                                ▼
       POKER. Lời khuyên của John McDonald: ván bài phải luôn được che sau
       "mặt nạ của sự thiếu nhất quán", người chơi giỏi phải hành động ngẫu
       nhiên, thậm chí đôi khi vi phạm nguyên tắc chơi đúng
       · người chơi "chặt" không bao giờ tố láo: hiếm khi thắng ván lớn, vì
         không ai tố theo; thắng nhiều ván nhỏ nhưng rốt cuộc thua
       · người chơi "lỏng" tố láo quá nhiều: luôn bị theo, cũng thua
       → chiến lược tốt nhất pha trộn hai cách
                                │
                                ▼
       Bảng xác suất hành động của đối thủ (dựng lại từ sách; ô là xác
       suất, không phải kết quả của người chơi):
       ┌──────────────┬────────────┬────────────┬────────────┐
       │ Bài          │ Tố (raise) │ Theo (call)│ Bỏ (fold)  │
       ├──────────────┼────────────┼────────────┼────────────┤
       │ Bài tốt      │ 2/3        │ 1/3        │ 0          │
       │ Bài xấu      │ 1/3        │ 0          │ 2/3        │
       └──────────────┴────────────┴────────────┴────────────┘
       · (đang tố láo thì theo là ý tồi, vì không mong thắng)
                                │
                                ▼
       Trước khi đối thủ cược, bạn tin bài tốt và bài xấu đều 1/2
       · thấy bỏ bài: chắc chắn bài xấu; thấy theo: chắc chắn bài tốt
         (nhưng khi đó cuộc cược đã kết thúc)
       · thấy tố: P(bài tốt và tố) = 1/2 × 2/3 = 1/3
                  P(bài xấu và tố, tức tố láo) = 1/2 × 1/3 = 1/6
                  P(tố) = 1/3 + 1/6 = 1/2
                  QUY TẮC BAYES: P(bài tốt | tố) = (1/3) / (1/2) = 2/3
       → sau khi nghe tố, khả năng bài tốt tăng từ 1/2 lên 2/3 (tỷ lệ 2:1)
```

### Tiểu mục "Price Discrimination by Screening" — phân biệt giá bằng sàng lọc (kèm bài "Trip to the Gym No. 5")

```text
       Ứng dụng của sàng lọc chạm tới đời sống bạn nhiều nhất: PHÂN BIỆT
       GIÁ (price discrimination)
       · người bán muốn phục vụ mọi khách sẵn lòng trả hơn chi phí, với giá
         cao nhất có thể, tức mỗi khách một giá
       · khó: người bán không biết ai sẵn lòng trả bao nhiêu (tạm bỏ qua
         vấn đề khách mua rẻ rồi bán lại)
                                │
                                ▼
       Mẹo: TẠO PHIÊN BẢN (versioning) của cùng một sản phẩm, định giá khác
       nhau; khách tự chọn, nên không có phân biệt công khai, nhưng mỗi
       loại khách chọn một phiên bản, nên lựa chọn làm lộ mức sẵn lòng trả
       · SÁCH: bản bìa cứng giá cao ra trước, bản bìa mềm giá thấp ra sau
         khoảng một năm; người trả cao cũng là người muốn đọc ngay; chênh
         lệch chi phí in nhỏ hơn nhiều chênh lệch giá (hai tác giả hỏi:
         bạn đang đọc bản nào?)
       · PHẦN MỀM: bản "lite" hay "sinh viên" ít tính năng, rẻ hơn nhiều;
         thường làm bằng cách lấy bản đầy đủ rồi tắt bớt tính năng, nên
         bản rẻ lại tốn chi phí làm hơn
       · MÁY IN IBM: bản E in 5 trang/phút, bản nhanh in 10 trang/phút đắt
         hơn 200 USD; khác biệt duy nhất là một con chip thêm vào bản E để
         chèn thời gian chờ, làm chậm máy
       · ĐẦU DVD SHARP: DVE611 và DV740U làm cùng một nhà máy ở Thượng Hải;
         DVE611 "không" phát được đĩa chuẩn châu Âu (PAL) trên tivi chuẩn
         Mỹ (NTSC), nhưng tính năng vẫn có, chỉ là Sharp mài bớt nút chuyển
         hệ và che bằng mặt nạ điều khiển; người dùng đục lỗ đúng chỗ là
         khôi phục được
       → doanh nghiệp tốn công làm hỏng sản phẩm, khách tốn công sửa lại
                                │
                                ▼
       VÍ DỤ SỐ: hãng hàng không Pie-In-The-Sky (PITS), tuyến Podunk – South
       Succotash; 30% khách doanh nhân, 70% khách du lịch; tính trên 100
       khách. Bảng dựng lại từ sách (USD):
       ┌──────────┬────────┬────────────────────┬─────────────────────┐
       │ Hạng     │ Chi phí│ Giá tối đa sẵn lòng│ Lợi nhuận tiềm năng │
       │          │ của    │ trả                │ của PITS            │
       │          │ PITS   ├─────────┬──────────┼──────────┬──────────┤
       │          │        │ Du lịch │ Doanh    │ Du lịch  │ Doanh    │
       │          │        │         │ nhân     │          │ nhân     │
       ├──────────┼────────┼─────────┼──────────┼──────────┼──────────┤
       │ Phổ thông│ 100    │ 140     │ 225      │ 40       │ 125      │
       │ Hạng nhất│ 150    │ 175     │ 300      │ 25       │ 150      │
       └──────────┴────────┴─────────┴──────────┴──────────┴──────────┘
                                │
                                ▼
       TRƯỜNG HỢP LÝ TƯỞNG: PHÂN BIỆT GIÁ HOÀN HẢO (biết loại từng khách,
       không cấm, không bán lại)
       · doanh nhân: hạng nhất 300 (lãi 150) tốt hơn phổ thông 225 (lãi 125)
       · du lịch: phổ thông 140 (lãi 40) tốt hơn hạng nhất 175 (lãi 25)
       · lợi nhuận = 40 × 70 + 150 × 30 = 2.800 + 4.500 = 7.300 USD
                                │
                                ▼
       TRƯỜNG HỢP THỰC TẾ: không nhận ra khách, phải sàng lọc
       · nếu hạng nhất giá 300, doanh nhân mua phổ thông 140 và được thặng
         dư tiêu dùng 225 – 140 = 85 USD (hạng nhất cho họ 0), nên họ chuyển
         sang phổ thông và sàng lọc thất bại
       · RÀNG BUỘC TƯƠNG THÍCH KHUYẾN KHÍCH của doanh nhân: hạng nhất phải
         cho họ ít nhất 85 USD thặng dư, nên giá tối đa là 300 – 85 = 215
         USD
       · lợi nhuận = 40 × 70 + 65 × 30 = 2.800 + 1.950 = 4.750 USD
       · mất 7.300 – 4.750 = 2.550 USD = 85 × 30: cái giá của việc phân
         biệt gián tiếp qua tự lựa chọn
                                │
                                ▼
       Muốn thu doanh nhân hơn 215 USD, phải tăng giá phổ thông
       · ví dụ hạng nhất 240, phổ thông 165: doanh nhân được 60 USD thặng
         dư ở cả hai hạng, vừa đủ chọn hạng nhất
       · nhưng giá phổ thông 140 đã chạm mức tối đa của khách du lịch; chỉ
         141 USD là mất hết họ; đó là RÀNG BUỘC THAM GIA của khách du lịch
       → chiến lược của PITS bị kẹp giữa ràng buộc tham gia của khách du
         lịch và ràng buộc tương thích khuyến khích của doanh nhân; cặp giá
         215 và 140 là tối ưu (hai tác giả khẳng định, không chứng minh)
                                │
                                ▼
       BÀI "TRIP TO THE GYM" SỐ 5: kiểm tra rằng ràng buộc tham gia của
       doanh nhân và ràng buộc tương thích khuyến khích của khách du lịch
       tự động thoả mãn ở mức giá trên
       · Đáp án của sách (phần Workouts): giá hạng nhất 215 thấp hơn hẳn
         mức 300 doanh nhân sẵn lòng trả, nên ràng buộc tham gia của họ
         được thoả. Khách du lịch được thặng dư 0 (140 – 140) ở hạng phổ
         thông, nhưng thặng dư âm (175 – 215 = –40) ở hạng nhất, nên họ
         không muốn đổi; ràng buộc tương thích khuyến khích của họ được
         thoả
                                │
                                ▼
       NẾU 50% LÀ DOANH NHÂN
       · sàng lọc: 40 × 50 + 65 × 50 = 2.000 + 3.250 = 5.250 USD
       · chỉ bán hạng nhất 300 USD cho doanh nhân, bỏ khách du lịch:
         150 × 50 = 7.500 USD
       → khi khách trả thấp chỉ là số ít, bỏ hẳn họ có thể lợi hơn là hạ
         giá cho số đông trả cao
       · ý cốt lõi của mọi chiến lược sàng lọc bằng tự lựa chọn: sự giằng
         co giữa ràng buộc tương thích khuyến khích và ràng buộc tham gia
```

### Tiểu mục "Case Study: Going Undercover" — tình huống: hoà nhập bí mật

```text
       Tanya, một nhà nhân học bạn của hai tác giả, làm điền dã ở London;
       đối tượng nghiên cứu là các phù thuỷ hiện đại (những người tụ họp
       trao đổi bùa phép, học phép thuật)
       · nhóm rất cởi mở với cô: khi cô nói mình là nhà nhân học, họ cho đó
         là vỏ bọc khéo của một phù thuỷ thật
       · đặc điểm lạ: các buổi họp diễn ra trong tình trạng khoả thân. Vì
         sao?
                                │
                                ▼
       Thảo luận của sách
       · mọi nhóm "ngoài lề" đều lo thành viên chỉ đứng xem và chế giễu
         chứ không thật sự tham gia
       · ngồi khoả thân thì khó nói mình chỉ đứng ngoài xem
       → khoả thân là công cụ SÀNG LỌC đáng tin: tin thật vào hội thì gần
         như không tốn gì; người hoài nghi thì khó giải thích với người
         khác và với chính mình
       · Chú thích của tác giả: trong phim "Gray's Anatomy", Spalding Gray
         kể một trải nghiệm tương tự trong lều xông hơi của người Mỹ bản địa
       · cùng lý do, nghi thức nhập băng đảng thường đòi xăm mình hay phạm
         tội: rẻ với người thật lòng muốn vào, rất đắt với cảnh sát chìm
                                │
                                ▼
       Các tình huống tiếp nối ở Chương 14: "The Other Person's Envelope Is
       Always Greener", "But One Life to Lay Down for Your Country", "King
       Solomon's Dilemma Redux", "The King Lear Problem"
```

## Ba câu hỏi chương này trả lời

1. **Khi nào nên tin điều người khác nói?** Khi lợi ích của họ trùng với lợi ích của bạn, hoặc khi điều họ nói đi ngược lợi ích của họ (người phục vụ khuyên món rẻ, Tổng giám mục nói không tin có Chúa). Với người có lợi ích hoàn toàn đối nghịch, như cầu thủ sút phạt đền nói trước hướng sút, cách hợp lý duy nhất là bỏ qua hẳn lời họ nói: không tin, cũng không suy ra điều ngược lại, mà chơi theo cân bằng của trò chơi thật.
2. **Điều gì làm một hành động thành tín hiệu đáng tin?** Hành động đó phải là lựa chọn tối ưu của người chơi nếu và chỉ nếu họ có thông tin mà họ muốn truyền đạt, tức nó phải tốn kém hơn với người nói dối. Bảo hành xe cũ đáng tin vì chi phí sửa chữa kỳ vọng của xe tốt (500 USD) thấp hơn hẳn xe tồi (2.000 USD), nên mức chênh giá 800 USD chỉ có lợi cho người bán xe tốt. Lời mời đưa xe đi kiểm tra không đáng tin, vì người bán xe tồi cũng không mất gì khi mời. Bằng MBA phân loại được ứng viên chỉ vì người có tài chắc chắn tốt nghiệp, còn người không có tài chỉ có 50% khả năng.
3. **Người biết ít hơn khai thác thông tin từ người biết nhiều hơn bằng cách nào, và tốn gì?** Bằng sàng lọc: đưa ra những lựa chọn mà mỗi loại người sẽ chọn khác nhau, như thực đơn gói bảo hiểm, thủ tục hành chính mất thời gian, trợ cấp bằng xe lăn thay vì tiền, các hạng vé máy bay. Sàng lọc có giá: công ty phải trả người có MBA thêm 40.000 USD/năm trong 5 năm, và hãng hàng không PITS phải hạ giá hạng nhất từ 300 xuống 215 USD để doanh nhân không chuyển sang hạng phổ thông, mất 2.550 USD trên mỗi 100 khách so với khi nhận ra từng khách.

## Khái niệm cần biết

**Thông tin bất cân xứng (information asymmetry).** Tình huống một bên biết nhiều hơn bên kia về điều ảnh hưởng tới kết quả của cả hai. Ví dụ trong chương: người bán xe cũ biết xe tốt hay tồi, người mua chỉ biết một nửa số xe là tồi. Đây là bối cảnh của toàn bộ chương; mọi công cụ khác đều nhằm xử lý nó.

**Tín hiệu đáng tin (credible signal) và phát tín hiệu (signaling).** Tín hiệu là hành động của người biết nhiều nhằm truyền thông tin riêng của mình cho người khác. Nó đáng tin khi hành động đó là tối ưu với người chơi nếu và chỉ nếu họ có thông tin ấy. Ví dụ: bảo hành xe cũ với mức chênh giá 800 USD, khi chi phí sửa chữa kỳ vọng là 500 USD với xe tốt và 2.000 USD với xe tồi. Hai tác giả gọi tín hiệu đáng tin là "họ hàng" của cam kết ở Chương 7: nó không buộc ai làm gì, chỉ giúp phân biệt ai là ai.

**Sàng lọc (screening).** Người biết ít chủ động đặt ra tình huống hay thực đơn lựa chọn để người biết nhiều tự lộ thông tin qua lựa chọn của mình. Ví dụ: công ty trả 100.000 USD cho người có MBA; người có tài đi học (thêm 50.000 USD/năm, đủ bù 40.000 USD chi phí khấu hao mỗi năm), người không có tài thì không (kỳ vọng chỉ thêm 25.000 USD/năm). Sàng lọc và phát tín hiệu dựa trên cùng một nguyên lý, chỉ khác bên khởi xướng.

**Gây nhiễu tín hiệu (signal jamming).** Hành động của người biết nhiều nhằm che bớt thông tin bất lợi, thường bằng cách bắt chước hành vi của loại người khác. Ví dụ: chủ xe cẩu thả vẫn rửa sạch xe trước khi bán, vì rửa xe không tốn với họ hơn với chủ cẩn thận. Quan trọng vì nó cho thấy một dấu hiệu bề ngoài (xe sạch) có thể chẳng mang thông tin gì.

**Cân bằng gộp, cân bằng tách biệt, cân bằng bán tách biệt (pooling, separating, semi-separating equilibrium).** Ba kết cục của trò chơi phát tín hiệu. Gộp: mọi loại người chơi làm như nhau, nên hành động không mang thông tin (khi chủ xe cẩu thả là số ít, ai cũng rửa xe). Tách biệt: một loại phát tín hiệu, loại kia không, nên hành động nhận diện đúng loại (chỉ người có tài học MBA). Bán tách biệt: một loại dùng chiến lược hỗn hợp, nên hành động chỉ mang một phần thông tin (khi chủ xe cẩu thả là số đông, mỗi người rửa xe với một xác suất).

**Lựa chọn ngược (adverse selection) và lựa chọn thuận lợi (positive selection).** Lựa chọn ngược: một giao dịch thu hút riêng những người "xấu" với bên kia, vì bên kia không phân biệt được. Ví dụ: hợp đồng nhân thọ phí 5 xu mỗi đô la bảo hiểm hấp dẫn riêng người có tỷ lệ tử vong trên 5%; tăng phí còn đuổi thêm người rủi ro thấp (hai tác giả gọi là "hiệu ứng Groucho Marx"). Lựa chọn thuận lợi là chiều ngược lại: ưu đãi chuyển dư nợ của Capital One chỉ hấp dẫn đúng loại khách có lãi (người đang nợ nhiều và định trả). Thuật ngữ này đặt tên cho cả một nhánh nghiên cứu về thông tin bất cân xứng.

**Xe chanh và xe đào (lemons and peaches), thị trường sụp đổ.** Ví dụ của George Akerlof: chủ xe chanh chịu bán 1.000 USD, người mua chịu trả 1.500; chủ xe đào chịu bán 3.000, người mua chịu trả 4.000. Khi người mua không phân biệt được, họ trả tối đa 2.750 USD; chủ xe đào rút lui, chỉ còn xe chanh. Quan trọng vì nó cho thấy thông tin bất cân xứng có thể làm biến mất cả những giao dịch mà hai bên đều muốn.

**Phản tín hiệu (countersignaling).** Người thuộc loại tốt nhất cố ý không phát tín hiệu mà loại trung bình hay dùng, vì việc phát tín hiệu cho thấy mình cần tách khỏi loại kém hơn. Ví dụ: dưới 4% nhà kinh tế ở trường có chương trình tiến sĩ xưng học vị trong lời chào hộp thư thoại, so với 27% ở trường không có chương trình tiến sĩ. Quan trọng vì nó cảnh báo rằng "tín hiệu càng nhiều càng tốt" không phải lúc nào cũng đúng.

**Quy tắc Bayes (Bayes' Rule).** Cách cập nhật xác suất về loại của đối phương sau khi quan sát hành động: xác suất bài tốt khi thấy tố bằng xác suất "vừa bài tốt vừa tố" chia cho xác suất "tố". Ví dụ: (1/3) / (1/2) = 2/3. Quan trọng vì nó biến nguyên tắc "hành động nói to hơn lời nói" thành phép tính cụ thể.

**Ngoại ứng thông tin (informational externality).** Chi phí mà sự tồn tại của một loại người gây ra cho người khác chỉ vì không ai phân biệt được họ. Ví dụ: vì có người không có tài quản lý, người có tài phải học MBA tốn 200.000 USD, và công ty phải trả họ thêm 40.000 USD/năm. Hai tác giả khuyên người đọc tìm ra ngoại ứng này trong mọi ví dụ của chương.

**Phân biệt giá bằng sàng lọc (price discrimination by screening), tạo phiên bản (versioning).** Người bán tạo nhiều phiên bản của cùng sản phẩm với giá khác nhau để mỗi loại khách tự chọn phiên bản dành cho mình. Ví dụ: máy in IBM bản E chậm hơn vì một con chip chèn thời gian chờ, rẻ hơn 200 USD. Quan trọng vì đây là ứng dụng của sàng lọc mà người đọc gặp hằng ngày.

**Ràng buộc tương thích khuyến khích và ràng buộc tham gia (incentive compatibility constraint, participation constraint).** Hai điều kiện mà mọi thực đơn sàng lọc phải thoả. Tương thích khuyến khích: mỗi loại khách phải thích phiên bản dành cho mình hơn phiên bản dành cho loại khác (giá hạng nhất tối đa 215 USD để doanh nhân không chuyển sang phổ thông). Tham gia: mỗi loại khách phải vẫn muốn mua (giá phổ thông tối đa 140 USD để khách du lịch còn đi). Đi kèm là khái niệm **giá tối đa sẵn lòng trả (reservation price)** và **thặng dư tiêu dùng (consumer surplus)**, phần chênh giữa giá tối đa sẵn lòng trả và giá thật phải trả.

## Nội dung chi tiết

### 1. Người này có định kết hôn không? (The Marrying Kind?)

Hai tác giả mở chương bằng một chuyện có thật về người bạn họ gọi là Sue. Ở tuổi 37, Sue yêu một giám đốc điều hành rất thành đạt, thông minh, độc thân, và anh ta nói yêu cô. Sue muốn kết hôn và có con; anh ta đồng ý với kế hoạch đó, nhưng giải thích rằng các con riêng từ cuộc hôn nhân trước chưa sẵn sàng để bố tái hôn, nên cần thời gian. Sue sẵn lòng chờ, miễn là biết chắc sự chờ đợi có kết quả. Vấn đề là làm sao biết lời anh ta có thật lòng, khi mọi cam kết công khai đều không thể, vì bọn trẻ sẽ biết.

Điều Sue cần là một tín hiệu đáng tin. Hai tác giả gọi nó là "họ hàng" của công cụ cam kết ở chương trước: Chương 7 bàn những chiến lược bảo đảm người ta làm đúng điều đã nói, còn ở đây chỉ cần một thứ yếu hơn, giúp Sue hiểu anh ta có nghiêm túc hay không. Sau nhiều suy nghĩ, Sue đề nghị anh ta xăm tên cô, một hình xăm nhỏ, kín đáo, không ai khác phải thấy. Nếu anh ta định gắn bó lâu dài, hình xăm là sự tôn vinh tình yêu và gần như không tốn gì; nếu không, nó sẽ là vật chứng ngượng ngùng cho người tình kế tiếp phát hiện. Anh ta chần chừ, nên Sue ra đi. Cô gặp người khác, nay đã kết hôn và có con; còn anh ta, theo cách nói đùa của hai tác giả, vẫn "nằm trên đường băng, bị hoãn cất cánh vĩnh viễn".

### 2. Sao không cứ nói thật? (Tell It Like It Is?)

Người ta không thể luôn tin lời nhau vì nói thật có thể trái lợi ích của người nói. Khi lợi ích trùng nhau, lời nói đáng tin: bạn gọi bít tết chín tái thì người phục vụ cứ tin là bạn muốn chín tái, vì anh ta muốn làm bạn hài lòng. Khi bạn hỏi nên gọi món gì hay rượu gì, lợi ích bắt đầu lệch: người phục vụ có thể hướng bạn tới món đắt để được tiền boa cao hơn. Nhà khoa học kiêm nhà văn Anh C. P. Snow kể rằng nhà toán học G. H. Hardy từng nói: nếu Tổng giám mục Canterbury nói ông tin có Chúa thì đó chỉ là chuyện nghề nghiệp, còn nếu ông nói không tin thì có thể tin ông nói thật. Cũng vậy, khi người phục vụ khuyên món bít tết thăn rẻ hay chai rượu Chile giá hời, bạn có mọi lý do để tin; khi anh ta khuyên món đắt, có thể anh ta vẫn đúng nhưng bạn khó biết.

Xung đột lợi ích càng lớn, lời nhắn càng kém tin. Hai tác giả nhắc lại cầu thủ sút phạt đền và thủ môn ở Chương 5: nếu ngay trước khi sút, cầu thủ nói "tôi sẽ sút bên phải", thủ môn không nên tin, vì lợi ích hai bên hoàn toàn đối nghịch. Nhưng thủ môn cũng không nên suy ra cầu thủ sẽ sút bên trái, vì cầu thủ có thể đang lừa ở tầng thứ hai, "nói dối bằng cách nói thật". Phản ứng hợp lý duy nhất trước lời khẳng định của người có lợi ích hoàn toàn đối nghịch là bỏ qua hẳn: không coi nó là đúng, cũng không coi điều ngược lại là đúng, mà tìm cân bằng của trò chơi thật và chơi theo đó (phần poker cuối chương chỉ cách làm).

Chính trị gia, nhà quảng cáo và trẻ con đều là người chơi có lợi ích riêng, và điều họ nói phục vụ mục đích của họ. Chương đặt ra hai câu hỏi: nên diễn giải thông tin từ những nguồn như vậy thế nào, và ngược lại, làm sao để lời mình được tin khi biết người khác sẽ nghi ngờ đúng mức.

### 3. Thế khó của vua Solomon (King Solomon's Dilemma)

Kinh Thánh (Các Vua quyển 1, chương 3) kể hai người phụ nữ tranh nhau một đứa bé. Vua Solomon sai mang gươm tới và ra lệnh chặt đứa bé làm đôi, mỗi người một nửa. Người mẹ thật xót con, xin vua trao đứa bé cho người kia và đừng giết nó; người kia nói không ai được nó cả, cứ chặt đi. Vua phán trao đứa bé cho người thứ nhất vì bà là mẹ nó, và cả Israel kính phục sự khôn ngoan của vua.

Hai tác giả "không thể để yên một câu chuyện hay": nếu người mẹ giả hiểu chuyện gì đang diễn ra, mưu của vua có hiệu quả không? Không. Người mẹ giả mắc một lỗi chiến lược: chính câu trả lời đồng ý chặt đứa bé làm bà khác người mẹ thật. Lẽ ra bà chỉ cần nhắc lại đúng lời người thứ nhất; khi hai người nói giống hệt nhau, vua không thể biết ai là mẹ thật. Như vậy vua may mắn hơn là khôn ngoan, vì mưu chỉ thành nhờ lỗi của người mẹ giả. Vua lẽ ra nên làm gì được để dành làm tình huống ở Chương 14.

### 4. Các công cụ thao túng thông tin (Devices for Manipulating Information)

Vấn đề của Sue và Solomon có mặt trong hầu hết tương tác chiến lược: một số người chơi biết nhiều hơn về điều ảnh hưởng tới kết quả của tất cả. Có người biết mà muốn giấu (như người mẹ giả), có người biết mà muốn lộ sự thật (như người mẹ thật), còn người biết ít (như vua) muốn khai thác được sự thật từ người biết.

Nguyên tắc chung cho mọi tình huống này là **hành động (kể cả hình xăm) nói to hơn lời nói**. Người chơi nên nhìn người khác làm gì chứ không phải nói gì; và vì biết người khác sẽ diễn giải hành động của mình như vậy, mỗi người chơi sẽ chọn hành động theo lượng thông tin nó để lộ. Mượn và bẻ một câu trong bài thơ "Bản tình ca của J. Alfred Prufrock" của T. S. Eliot, hai tác giả nói ta phải luôn "chuẩn bị một gương mặt để gặp những gương mặt mình gặp". Ai không nhận ra "gương mặt", tức hành động, của mình đang bị diễn giải sẽ dễ hành xử theo cách gây hại cho chính mình, nên hai tác giả coi bài học của chương là một trong những bài quan trọng nhất của lý thuyết trò chơi.

Người có thông tin riêng sẽ giấu nó nếu bị hại khi người khác biết sự thật, và sẽ chọn những hành động mà khi được diễn giải đúng sẽ lộ ra thông tin có lợi cho mình. Hai tác giả phân biệt ba công cụ:

| Công cụ | Ai khởi xướng | Nội dung |
|---|---|---|
| Phát tín hiệu (signaling) | Người biết nhiều | Chọn hành động làm lộ thông tin có lợi cho mình |
| Gây nhiễu tín hiệu (signal jamming) | Người biết nhiều | Hành động để giảm hay xoá thông tin bất lợi bị lộ, thường bằng cách bắt chước hành vi vốn hợp với một hoàn cảnh khác |
| Sàng lọc (screening) | Người biết ít | Đặt ra tình huống mà người kia sẽ chọn hành động này nếu thông tin thuộc loại này, hành động khác nếu thuộc loại khác; hành động hay không hành động làm lộ thông tin. Yêu cầu hình xăm của Sue là một phép sàng lọc |

> **Chú thích của tác giả:** đôi khi chính hành động cũng khó quan sát và diễn giải. Khó nhất là đánh giá chất lượng nỗ lực làm việc: lượng thời gian thì đo được, nhưng trừ những việc lặp lại đơn giản nhất, mọi việc đều cần suy nghĩ và sáng tạo, và người giám sát không thể biết chính xác nhân viên dùng thời gian tốt hay không. Khi đó phải đánh giá qua kết quả, và người chủ phải thiết kế cơ chế khuyến khích phù hợp để nhân viên bỏ ra nỗ lực chất lượng cao; đó là chủ đề của Chương 13.

Ở Chương 1, hai tác giả đã nói người chơi poker nên giấu độ mạnh của bài bằng cách cược hơi khó đoán. Nhưng tỷ lệ pha trộn tối ưu khác nhau với bài mạnh và bài yếu, nên cược vẫn để lộ một phần thông tin về khả năng bài mạnh. Cùng nguyên tắc đó áp dụng khi ai đó muốn truyền đạt chứ không phải che giấu thông tin. Để là tín hiệu hiệu quả, hành động phải không thể bị một kẻ nói dối có lý trí bắt chước: nó phải gây lỗ khi sự thật khác với điều bạn muốn truyền đạt.

Thông tin quan trọng nhất bạn có mà người khác không có là đặc điểm của chính bạn: năng lực, sở thích, ý định. Họ không quan sát được, nhưng bạn có thể làm những việc phát tín hiệu đáng tin về chúng, và họ sẽ cố suy ra đặc điểm của bạn từ hành động của bạn. Khi một hãng luật tuyển thực tập sinh mùa hè bằng những buổi chiêu đãi xa hoa, hãng đang nói: "Bạn sẽ được đối xử tốt ở đây vì chúng tôi rất coi trọng bạn; bạn tin được, vì nếu coi trọng bạn ít hơn, chúng tôi đã chẳng chi nhiều tiền như vậy." Thực tập sinh nên hiểu rằng đồ ăn dở hay chương trình giải trí nhàm chán cũng không sao; điều quan trọng là cái giá.

Nhiều trường đại học bị cựu sinh viên chê dạy những thứ vô dụng cho sự nghiệp sau này. Lời chê đó bỏ qua giá trị tín hiệu của giáo dục: kỹ năng cụ thể cho từng công ty, từng nghề thường học tốt nhất khi đi làm; điều chủ lao động khó quan sát mà rất cần biết là năng lực tư duy và học hỏi chung của ứng viên. Một tấm bằng tốt của một trường tốt là tín hiệu về năng lực đó; người tốt nghiệp như đang nói "nếu tôi kém hơn, liệu tôi có tốt nghiệp loại ưu ở Princeton không?".

Nhưng phát tín hiệu có thể thành một cuộc đua chuột. Nếu người giỏi chỉ học nhiều hơn một chút, người kém có thể thấy đáng học thêm tương tự để được nhầm là người giỏi và có việc, lương tốt hơn; khi đó người giỏi thật phải học thêm nữa để phân biệt mình. Chẳng bao lâu, việc văn phòng đơn giản cũng đòi bằng thạc sĩ. Năng lực thật không đổi; người duy nhất được lợi từ đầu tư quá mức vào giáo dục để phát tín hiệu là các giáo sư đại học như hai tác giả. Từng người lao động hay từng công ty không tự dừng được cuộc cạnh tranh lãng phí này; cần một giải pháp chính sách công.

### 5. Chất lượng có được bảo đảm không? (Is the Quality Guaranteed?)

Bạn đi mua xe cũ và tìm được hai chiếc có vẻ tốt như nhau, nhưng chiếc thứ nhất có bảo hành, chiếc thứ hai không. Bạn chắc chắn thích chiếc thứ nhất và sẵn lòng trả cao hơn. Một phần vì nếu hỏng, xe được sửa miễn phí, dù bạn vẫn mất thời gian và chịu phiền toái không được đền. Phần quan trọng hơn là bạn tin chiếc xe có bảo hành ít hỏng hơn ngay từ đầu. Muốn hiểu vì sao, phải nghĩ theo chiến lược của người bán. Người bán biết rõ chất lượng xe hơn bạn. Nếu xe tốt, ít khả năng phải sửa tốn kém, bảo hành gần như không tốn gì; nếu xe tồi, bảo hành sẽ tốn nhiều. Vì vậy, kể cả khi đã tính giá cao hơn mà xe có bảo hành bán được, xe càng tồi thì bảo hành càng dễ thành món lỗ cho người bán.

Bảo hành vì thế là một lời tuyên bố ngầm của người bán: "Tôi biết xe đủ tốt để có thể bảo hành." Bạn không thể tin lời tuyên bố suông "tôi biết xe này rất tốt", nhưng với bảo hành, người bán đặt tiền vào chỗ lời nói của mình. Việc đưa ra bảo hành dựa trên chính phép tính được mất của người bán, nên đáng tin theo cách lời nói không thể có. Người biết xe mình tồi sẽ không bảo hành, nên bảo hành tách người bán chỉ "nói suông" khỏi người bán "nói được làm được".

Hai tác giả định nghĩa: tín hiệu là hành động nhằm truyền thông tin riêng của một người chơi cho người chơi khác; muốn là phương tiện đáng tin của một thông tin cụ thể, **hành động phải là tối ưu với người chơi nếu, và chỉ nếu, họ có thông tin đó**. Bảo hành có đáng tin trong một trường hợp cụ thể hay không tuỳ loại hỏng hóc dễ xảy ra với loại xe đó, chi phí sửa và chênh lệch giá giữa xe có và không có bảo hành:

| Thông số (ví dụ của hai tác giả) | Giá trị |
|---|---|
| Chi phí sửa chữa kỳ vọng của xe tốt | 500 USD |
| Chi phí sửa chữa kỳ vọng của xe tồi | 2.000 USD |
| Chênh lệch giá giữa xe có và không có bảo hành | 800 USD |
| Kết luận | Người bán chịu bảo hành ở mức chênh 800 USD hẳn biết xe mình tốt |

Bạn không cần chờ người bán nghĩ ra điều này. Bạn có thể chủ động nói: "Tôi trả thêm 800 USD nếu anh bảo hành." Đề nghị này có lợi cho người bán nếu và chỉ nếu xe tốt. Thực ra bạn có thể đưa 600 USD và người bán đòi 1.800 USD: mọi mức giá bảo hành trên 500 và dưới 2.000 USD đều khiến người bán xe tốt và xe tồi chọn khác nhau và lộ thông tin riêng, và hai bên có thể mặc cả trong khoảng đó.

Sàng lọc xảy ra khi người biết ít yêu cầu người biết nhiều làm một hành động lộ thông tin như vậy. Người bán có thể chủ động phát tín hiệu bằng cách đưa bảo hành, hoặc người mua chủ động sàng lọc bằng cách đòi bảo hành. Hai chiến lược có tác dụng tương tự, dù về kỹ thuật lý thuyết trò chơi, cân bằng sinh ra có thể khác nhau; khi cả hai đều khả thi, cách nào được dùng có thể tuỳ bối cảnh lịch sử, văn hoá hay thể chế của giao dịch.

Một tín hiệu đáng tin phải đi ngược lợi ích của chủ xe tồi. Để nhấn mạnh, hai tác giả hỏi: nên hiểu thế nào khi người bán mời bạn đưa xe cho thợ kiểm tra? Đó không phải tín hiệu đáng tin. Nếu thợ tìm ra lỗi nghiêm trọng và bạn bỏ đi, người bán cũng không thiệt gì so với trước, dù xe tốt hay tồi; chủ xe tồi cũng mời như vậy được. Chú thích của tác giả: người bán có thể tự bỏ tiền đưa xe đi kiểm tra và trình giấy chứng nhận chất lượng, nhưng bạn có lý do để ngờ thợ thông đồng với người bán. Muốn tín hiệu đáng tin, người bán có thể cam kết hoàn tiền kiểm tra cho bạn nếu thợ tìm ra lỗi; cam kết đó tốn kém với người bán xe tồi hơn là với người bán xe tốt.

Bảo hành đáng tin vì có tính chất chênh lệch chi phí then chốt. Nhưng chính bảo hành cũng phải đáng tin theo nghĩa thi hành được khi cần. Ở đây có khác biệt lớn giữa người bán tư nhân và đại lý. Từ lúc bán tới lúc xe cần sửa, người bán tư nhân có thể chuyển nhà không để lại địa chỉ, hoặc không có tiền trả, và kiện ra toà rồi thi hành bản án có thể quá tốn với người mua. Đại lý có khả năng làm ăn lâu dài và có danh tiếng cần giữ, dù đại lý cũng có thể tìm cách chối bằng cách nói bạn bảo dưỡng kém hay lái ẩu. Nhìn chung, việc tiết lộ chất lượng xe (hay hàng tiêu dùng lâu bền khác) qua bảo hành hay cách khác khó khăn hơn nhiều trong giao dịch tư nhân so với khi mua của đại lý có tiếng.

Các hãng xe chưa có danh tiếng chất lượng cũng gặp vấn đề tương tự. Cuối thập niên 1990, Hyundai đã nâng chất lượng xe nhưng người tiêu dùng Mỹ chưa nhận ra. Để truyền đạt điều đó một cách ấn tượng và đáng tin, năm 1999 hãng phát tín hiệu bằng một chế độ bảo hành chưa từng có: 10 năm hoặc 100.000 dặm cho hệ truyền động, 5 năm hoặc 50.000 dặm cho phần còn lại.

### 6. Một chút lịch sử (A Little History)

George Akerlof chọn thị trường xe cũ làm ví dụ chính trong bài báo kinh điển chứng minh thông tin bất cân xứng có thể làm thị trường thất bại. Ở dạng đơn giản nhất, chỉ có hai loại xe cũ: "xe chanh" (xe tồi) và "xe đào" (xe tốt).

| Loại xe | Chủ xe chịu bán với giá tối thiểu | Người mua chịu trả tối đa | Khoảng giá nếu ai cũng thấy chất lượng |
|---|---|---|---|
| Xe chanh (lemon) | 1.000 USD | 1.500 USD | 1.000–1.500 USD |
| Xe đào (peach) | 3.000 USD | 4.000 USD | 3.000–4.000 USD |

Nếu chất lượng từng xe ai cũng thấy ngay, thị trường vận hành tốt và mọi xe đều được bán. Nhưng giả sử chỉ người bán biết chất lượng, còn người mua chỉ biết một nửa số xe là chanh, một nửa là đào. Nếu xe được rao bán theo đúng tỷ lệ đó, mỗi người mua chỉ chịu trả tối đa (công thức dựng lại từ sách):

½ × (1.500 USD + 4.000 USD) = 2.750 USD.

Chủ xe đào không chịu bán với giá này, nên chỉ xe chanh được rao bán; người mua biết vậy nên chỉ trả tối đa 1.500 USD. Thị trường xe đào sụp đổ hoàn toàn, dù người mua sẵn lòng trả cho một chiếc xe đào được chứng minh một mức giá mà người bán vui vẻ chấp nhận. Cách nhìn "Pangloss" (lấy tên nhân vật lạc quan mù quáng của Voltaire) rằng thị trường là thể chế tốt nhất, hiệu quả nhất để tổ chức hoạt động kinh tế đổ vỡ.

> **Chú thích của tác giả:** người mua ngây thơ trả 2.750 USD vì nghĩ đó là giá trị trung bình của một chiếc xe ngẫu nhiên sẽ là nạn nhân của **lời nguyền người thắng (winner's curse)**: mua được hàng rồi mới phát hiện nó không đáng giá như mình tưởng. Vấn đề này xảy ra khi chất lượng hàng không chắc chắn và thông tin của bạn chỉ là một mảnh ghép; chính việc người bán chịu nhận giá của bạn cho thấy phần thông tin còn thiếu không tốt như bạn đoán. Đôi khi lời nguyền người thắng làm thị trường sụp đổ hoàn toàn như ví dụ của Akerlof; lúc khác nó chỉ có nghĩa bạn phải trả thấp hơn để khỏi lỗ. Chương 10 sẽ chỉ cách tránh bẫy này.

Dixit là nghiên cứu sinh khi bài của Akerlof ra đời. Ông và các nghiên cứu sinh khác lập tức thấy đây là ý tưởng xuất sắc, gây sửng sốt, loại ý tưởng làm nên cách mạng khoa học. Chỉ có một vấn đề: gần như tất cả họ đều lái xe cũ, phần lớn mua qua giao dịch tư nhân, và phần lớn không phải xe chanh. Hẳn phải có cách để người tham gia thị trường đối phó với vấn đề thông tin mà Akerlof nêu. Có những cách hiển nhiên: một số sinh viên khá rành máy móc, những người khác nhờ bạn xem giúp; họ hỏi lịch sử xe qua mạng lưới bạn bè chung; và nhiều chủ xe tốt buộc phải bán với gần như bất kỳ giá nào vì chuyển đi xa, ra nước ngoài, hay cần xe to hơn khi gia đình đông thêm.

Bước đột phá khái niệm tiếp theo phải chờ công trình của Michael Spence về cách hành động chiến lược truyền đạt thông tin. Spence phát triển ý tưởng phát tín hiệu và làm rõ tính chất then chốt làm tín hiệu đáng tin: kết quả của cùng một hành động khác nhau với những người chơi có thông tin khác nhau. Chú thích của tác giả: đây là trường hợp rất đáng đọc nguyên bản, cuốn *Market Signaling* của A. Michael Spence (Harvard University Press, 1974); ý tưởng tương tự trong tâm lý học xuất hiện ở cuốn kinh điển *The Presentation of Self in Everyday Life* của Erving Goffman (1959).

Ý tưởng sàng lọc bắt nguồn từ công trình của James Mirrlees và William Vickrey, và được phát biểu rõ nhất trong công trình của Michael Rothschild và Joseph Stiglitz về thị trường bảo hiểm. Người mua bảo hiểm biết rủi ro của mình rõ hơn công ty bảo hiểm. Công ty có thể yêu cầu họ chọn giữa các gói có mức khấu trừ và tỷ lệ đồng chi trả khác nhau; người rủi ro thấp sẽ thích gói phí thấp nhưng tự chịu phần rủi ro lớn hơn, còn gói đó kém hấp dẫn với người biết mình rủi ro cao. Lựa chọn của người mua vì thế lộ ra loại rủi ro của họ. Ý tưởng sàng lọc bằng một thực đơn lựa chọn được thiết kế khéo nay là chìa khoá để hiểu nhiều hiện tượng thị trường, chẳng hạn các điều kiện hạn chế mà hãng hàng không gắn vào vé giảm giá.

Thị trường bảo hiểm còn góp thêm một ý. Các công ty bảo hiểm từ lâu biết hợp đồng của họ thu hút chọn lọc những rủi ro tệ nhất. Một hợp đồng nhân thọ thu phí 5 xu cho mỗi đô la bảo hiểm đặc biệt hấp dẫn người có tỷ lệ tử vong trên 5%. Nhiều người rủi ro thấp vẫn mua vì cần bảo vệ gia đình, nhưng người rủi ro cao nhất sẽ chiếm tỷ lệ quá lớn và mua hợp đồng lớn hơn. Tăng phí còn làm tình hình tệ hơn: người rủi ro thấp thấy quá đắt và bỏ đi, chỉ còn lại ca xấu. Đó lại là "hiệu ứng Groucho Marx" (theo câu đùa của danh hài Groucho Marx rằng ông không muốn vào câu lạc bộ nào chịu nhận người như ông): ai chịu mua bảo hiểm với giá đó thì chính là người bạn không muốn bảo hiểm. Trong ví dụ của Akerlof cũng vậy: người mua không biết chất lượng từng xe nên không trả giá khác nhau được, và việc bán xe hấp dẫn riêng chủ xe chanh. Vì những loại "xấu" bị giao dịch thu hút một cách chọn lọc, ngành bảo hiểm gọi hiện tượng này là **lựa chọn ngược (adverse selection)**, và cả nhánh nghiên cứu về thông tin bất cân xứng trong lý thuyết trò chơi và kinh tế học thừa hưởng tên gọi đó.

Hiệu ứng này có thể đảo ngược thành "lựa chọn thuận lợi". Từ khi lên sàn năm 1994, Capital One là một trong những công ty thành công nhất nước Mỹ, với một thập kỷ tăng trưởng kép 40% mỗi năm, chưa kể sáp nhập và mua lại. Là người mới trong ngành thẻ tín dụng, sáng kiến lớn của Capital One là cho khách chuyển dư nợ từ thẻ khác sang và hưởng lãi suất thấp hơn, ít nhất trong một thời gian. Ưu đãi này sinh lãi vì lựa chọn thuận lợi. Đại thể có ba loại khách thẻ tín dụng:

| Loại khách | Hành vi | Lãi hay lỗ cho công ty thẻ | Có thấy ưu đãi chuyển dư nợ hấp dẫn không |
|---|---|---|---|
| Người trả đủ (maxpayer) | Trả đủ hoá đơn mỗi tháng, không vay | Lỗ: phí thu từ người bán hàng chỉ vừa đủ bù khoản vay miễn phí một tháng; khoản lãi nhỏ không đủ bù chi phí lập hoá đơn, gian lận, và rủi ro nhỏ nhưng có thật là khách ly hôn hay mất việc rồi vỡ nợ | Không, vì không vay |
| Người vay quay vòng (revolver) | Vay trên thẻ và trả dần | Lãi nhiều nhất, nhất là với lãi suất thẻ cao | Có, nhất là người nợ nhiều và định trả |
| Người quỵt nợ (deadbeat) | Vay và sẽ không trả | Lỗ | Ít, vì không định trả |

Capital One có thể không nhận ra ai là khách có lãi, nhưng bản chất của ưu đãi khiến nó chỉ hấp dẫn đúng loại khách đó, và tự lọc bỏ các loại không có lãi. Đây là chiều ngược của hiệu ứng Groucho Marx: ai nhận lời mời của bạn chính là người bạn muốn.

### 7. Sàng lọc và phát tín hiệu (Screening and Signaling)

Hai tác giả đặt người đọc vào vai trưởng phòng nhân sự cần tuyển người trẻ có tài quản lý bẩm sinh. Mỗi ứng viên biết mình có tài hay không, còn bạn thì không. Cả người không có tài cũng nộp đơn, mong hưởng lương cao cho tới khi bị phát hiện. Một nhà quản lý giỏi tạo vài triệu USD lợi nhuận, một người kém có thể gây lỗ lớn rất nhanh. Quần áo phù hợp và thái độ đúng mực ai cũng bắt chước được; thư giới thiệu khen khả năng lãnh đạo thì nhờ bố mẹ, họ hàng, bạn bè viết là có. Bạn cần bằng chứng đáng tin và khó bắt chước.

Giả sử ứng viên có thể học MBA. Các con số giả định của hai tác giả:

| Thông số | Giá trị |
|---|---|
| Chi phí lấy bằng MBA (học phí và lương bỏ lỡ) | khoảng 200.000 USD |
| Lương của người tốt nghiệp đại học không có MBA, ở công việc không cần tài quản lý | 50.000 USD/năm |
| Thời gian khấu hao chi phí MBA | 5 năm |
| Khoản lương thêm cần để bù chi phí | ít nhất 40.000 USD/năm |
| Lương tối thiểu phải trả người có MBA | 90.000 USD/năm |
| Xác suất tốt nghiệp: người có tài / người không có tài | 100% / 50% |

Nếu người không có tài lấy bằng MBA dễ như người có tài, bằng MBA chẳng phân loại được gì: cả hai loại đều có bằng và mong kiếm đủ để bù chi phí. MBA chỉ phân biệt được hai loại khi người có tài lấy bằng dễ hơn hoặc rẻ hơn. Giả sử người có tài chắc chắn tốt nghiệp, còn người không có tài chỉ có 50% khả năng. Bạn trả hơn 90.000 USD một chút, chẳng hạn 100.000 USD, cho người có MBA. Người có tài thấy đáng đi học. Người không có tài có 50% khả năng đỗ và nhận 100.000 USD, 50% khả năng trượt và phải làm việc khác với mức 50.000 USD thông thường; với 50% cơ hội tăng gấp đôi lương, trung bình họ chỉ được thêm 25.000 USD/năm, không đủ khấu hao chi phí MBA trong 5 năm, nên họ không đi học. Khi đó ai có MBA đều có tài quản lý bạn cần: nhóm sinh viên tốt nghiệp tự chia thành hai nhóm đúng như bạn muốn. MBA là công cụ sàng lọc, và hai tác giả nhấn mạnh lần nữa: nó hoạt động vì chi phí dùng công cụ thấp hơn với người bạn muốn thu hút so với người bạn muốn tránh.

Nghịch lý là công ty có thể tuyển sinh viên MBA ngay ngày đầu nhập học: khi sàng lọc hoạt động, chỉ người có tài đăng ký, nên không cần chờ họ tốt nghiệp. Nhưng nếu cách này phổ biến, người không có tài sẽ bắt đầu đăng ký và là những người đầu tiên bỏ học; sàng lọc chỉ hoạt động chừng nào người ta còn phải học hết hai năm.

Sàng lọc này tốn kém đáng kể. Nếu nhận ra người có tài trực tiếp, bạn chỉ cần trả họ hơn 50.000 USD một chút, mức họ kiếm được ở nơi khác. Nay bạn phải trả hơn 90.000 USD để người có tài thấy đáng bỏ chi phí tự chứng minh mình. Khoản thêm 40.000 USD/năm trong 5 năm là cái giá để khắc phục bất lợi thông tin của bạn. Cái giá đó có được là do sự tồn tại của người không có tài: nếu ai cũng là nhà quản lý giỏi thì chẳng cần sàng lọc. Người không có tài, chỉ bằng việc tồn tại, gây một ngoại ứng tiêu cực lên những người khác. Ban đầu người có tài chịu chi phí, nhưng rồi công ty phải trả họ cao hơn, nên cuối cùng công ty chịu. Hai tác giả gọi đây là **ngoại ứng thông tin** và khuyên người đọc tìm ra nó trong mọi ví dụ phía sau.

Có đáng trả cái giá đó không, hay nên tuyển ngẫu nhiên với giá 50.000 USD mỗi người và chấp nhận rủi ro? Tuỳ tỷ lệ người có tài và mức thiệt hại mỗi người kém gây ra:

| Phương án | Chi phí kỳ vọng mỗi lần tuyển |
|---|---|
| Tuyển ngẫu nhiên, giả sử 25% không có tài, mỗi người gây lỗ 1 triệu USD trước khi bị phát hiện | 250.000 USD |
| Sàng lọc bằng MBA (40.000 USD lương thêm × 5 năm) | 200.000 USD |

Sàng lọc rẻ hơn. Trên thực tế, tỷ lệ người có tài quản lý có lẽ thấp hơn nhiều và thiệt hại do chiến lược kém lớn hơn nhiều, nên lý lẽ dùng công cụ sàng lọc tốn kém còn mạnh hơn. Hai tác giả đùa thêm rằng họ muốn tin MBA cũng dạy được vài kỹ năng hữu ích.

**Khung "Một lý do để học MBA" (One Reason to Get an MBA).** Một chủ lao động có thể e ngại tuyển và đào tạo một phụ nữ trẻ rồi cô rời lực lượng lao động để sinh con; dù hợp pháp hay không, kiểu phân biệt đối xử này vẫn xảy ra. Bằng MBA là tín hiệu đáng tin rằng cô định đi làm vài năm: nếu định nghỉ sau một năm, bỏ hai năm đi học MBA là vô lý, cô thà đi làm ba năm còn hơn. Trên thực tế, cần ít nhất khoảng 5 năm mới thu hồi được học phí và lương bỏ lỡ của MBA, nên có thể tin người có MBA khi cô nói sẽ gắn bó.

Thường có nhiều cách nhận ra tài năng, và bạn nên dùng cách rẻ nhất. Một là tuyển cho giai đoạn đào tạo nội bộ hay thử việc, giao dự án nhỏ có giám sát và quan sát kết quả; chi phí là lương trả trong thời gian đó và rủi ro người kém gây vài khoản lỗ nhỏ. Hai là đưa ra hợp đồng có thu nhập dồn về sau hoặc gắn với kết quả: người có tài, tự tin trụ được và tạo lợi nhuận, sẵn lòng nhận hơn, còn người khác thích việc chắc chắn 50.000 USD/năm ở nơi khác. Ba là quan sát kết quả của các nhà quản lý ở công ty khác rồi lôi kéo những người đã chứng tỏ năng lực.

Khi mọi công ty cùng làm vậy, mọi phép tính về chi phí tuyển người học việc, cơ cấu lương và thưởng đều thay đổi. Quan trọng nhất, cạnh tranh giữa các công ty đẩy lương người có tài lên trên mức tối thiểu cần để thu hút họ (90.000 USD với người có MBA). Trong ví dụ này, lương không thể vượt 130.000 USD; nếu vượt, người không có tài cũng thấy đáng đi học MBA, và nhóm người có MBA bị "nhiễm" những người không có tài nhưng may mắn đỗ. Chú thích của tác giả: một nửa số lần, người không có tài lấy được bằng và với lương 130.000 USD được thêm 80.000 USD, tức trung bình 40.000 USD, vừa đủ bù chi phí học trong 5 năm.

Đến đây MBA được xem như công cụ sàng lọc: công ty đặt nó làm điều kiện tuyển dụng và gắn lương khởi điểm với tấm bằng. Nhưng nó cũng có thể là công cụ phát tín hiệu do ứng viên khởi xướng. Giả sử bạn chưa nghĩ ra cách này, đang tuyển ngẫu nhiên với giá 50.000 USD và chịu lỗ do những người kém. Một ứng viên có MBA tới, giải thích tấm bằng chứng minh tài năng của anh ta, và nói: "Biết tôi là nhà quản lý giỏi làm lợi nhuận kỳ vọng công ty thu từ tôi tăng thêm một triệu. Tôi sẽ làm cho anh nếu được trả trên 75.000 USD/năm." Chừng nào khả năng phân loại tài quản lý của trường kinh doanh là rõ ràng, đây là đề nghị hấp dẫn với bạn. Sàng lọc và phát tín hiệu do hai bên khác nhau khởi xướng, nhưng cùng một nguyên lý: hành động phân biệt các loại người chơi hay cho thấy thông tin riêng mà một người chơi nắm giữ.

### 8. Phát tín hiệu qua thủ tục hành chính (Signaling via Bureaucracy)

Ở Mỹ, Workers' Compensation là hệ thống bảo hiểm do nhà nước vận hành, chi trả điều trị chấn thương và bệnh tật liên quan tới công việc. Mục tiêu đáng khen nhưng kết quả có vấn đề: người quản lý hệ thống khó biết mức độ nặng của chấn thương (có khi cả việc chấn thương có thật hay không) và chi phí điều trị. Người lao động và bác sĩ điều trị biết rõ hơn nhưng có cám dỗ mạnh để phóng đại và nhận nhiều tiền hơn mức xứng đáng. Ước tính có từ 20% hồ sơ trở lên liên quan tới gian lận. Stan Long, CEO công ty bảo hiểm Workers' Compensation thuộc sở hữu của bang Oregon, nói: nếu bạn vận hành một hệ thống phát tiền cho bất kỳ ai xin, bạn sẽ có rất nhiều người xin tiền.

Giám sát có thể giải quyết một phần: người khai, hay ít nhất người bị nghi khai gian, bị theo dõi bí mật; nếu bị bắt gặp làm việc không khớp với chấn thương đã khai (người khai đau lưng nặng đang khuân đồ nặng), hồ sơ bị bác và họ bị truy tố. Nhưng giám sát tốn kém. Phân tích về khai thác thông tin gợi ra các công cụ sàng lọc khác: bắt người khai dành nhiều thời gian điền mẫu đơn, ngồi cả ngày ở cơ quan để nói chuyện năm phút với một viên chức. Người thật ra khoẻ mạnh, có thể kiếm tiền tốt nếu đi làm cả ngày, phải bỏ khoản thu nhập đó nên thấy chờ đợi quá tốn; người thật sự bị thương, không làm việc được, thì có thời gian. Người ta thường coi sự chậm chạp và phiền hà của bộ máy hành chính là bằng chứng chính phủ kém hiệu quả, nhưng đôi khi chúng là chiến lược có giá trị để đối phó với vấn đề thông tin.

Trợ cấp bằng hiện vật có tác dụng tương tự. Nếu chính phủ hay công ty bảo hiểm phát tiền để người khuyết tật mua xe lăn, nhiều người có thể giả khuyết tật. Nếu phát thẳng xe lăn, động cơ giả vờ giảm hẳn, vì người không cần xe lăn phải mất nhiều công bán lại trên thị trường đồ cũ và chỉ được giá thấp. Nhà kinh tế thường cho rằng tiền mặt tốt hơn hiện vật, vì người nhận tự quyết định cách tiêu phù hợp nhất với sở thích của mình; nhưng khi thông tin bất cân xứng, trợ cấp hiện vật có thể tốt hơn vì nó là công cụ sàng lọc.

### 9. Không phát tín hiệu cũng là tín hiệu (Signaling by Not Signaling)

Trong truyện "Silver Blaze", Sherlock Holmes lưu ý "sự việc kỳ lạ của con chó trong đêm"; khi người kia nói con chó chẳng làm gì cả, Holmes đáp rằng đó chính là điều kỳ lạ. Con chó không sủa nghĩa là kẻ đột nhập là người quen. Cũng vậy, khi một người không phát tín hiệu, việc đó cũng mang thông tin, thường là tin xấu nhưng không phải luôn luôn. Nếu người khác biết bạn có cơ hội làm một việc thể hiện điểm tốt của mình mà bạn không làm, họ sẽ hiểu là bạn không có điểm tốt đó. Bạn có thể vô tình không để ý tới vai trò tín hiệu của việc làm hay không làm, nhưng điều đó chẳng giúp gì bạn.

Sinh viên đại học Mỹ có thể học nhiều môn lấy điểm chữ (A tới F) hoặc chỉ lấy đạt/không đạt (P hoặc F). Nhiều sinh viên nghĩ điểm P trên bảng điểm sẽ được hiểu là điểm đạt trung bình của thang chữ; với mức lạm phát điểm hiện nay ở Mỹ, đó ít nhất là B+, nhiều khả năng A–, nên lựa chọn pass/fail có vẻ hời. Nhưng trường sau đại học và chủ lao động đọc bảng điểm chiến lược hơn. Họ biết mỗi sinh viên tự đánh giá khá đúng năng lực mình. Người giỏi tới mức chắc được A+ có động cơ mạnh để học lấy điểm chữ, tách mình khỏi mức trung bình. Khi nhiều sinh viên A+ không còn chọn pass/fail, nhóm chọn pass/fail mất phần trên cùng; điểm trung bình của nhóm còn lại không còn là A– mà chỉ còn khoảng B+. Khi đó người biết mình sẽ được A cũng có thêm động cơ chọn điểm chữ để tách khỏi đám đông, và nhóm pass/fail mất thêm phần trên. Quá trình có thể tiếp diễn tới khi chủ yếu chỉ người biết mình sẽ được C hay tệ hơn mới chọn pass/fail, và người đọc bảng điểm có tư duy chiến lược sẽ hiểu điểm P đúng như vậy. Những sinh viên khá giỏi không nghĩ thấu điều này sẽ chịu hậu quả của sự thiếu hiểu biết chiến lược.

John, một người bạn của hai tác giả, rất giỏi thương lượng mua bán: ông xây một mạng lưới báo rao vặt toàn cầu qua không dưới 100 thương vụ mua lại. Khi lần đầu bán công ty, một điều khoản cho phép ông cùng đầu tư vào bất kỳ thương vụ mua lại mới nào ông mang tới cho bên mua. Chú thích của tác giả: chữ "lần đầu" có lý do; bên mua là Cendant, công ty sau đó thành nạn nhân của một vụ gian lận kế toán tại CUC, một đơn vị nó mua lại, và khi cổ phiếu Cendant lao dốc, John mua lại được công ty của mình với giá rẻ. John giải thích với bên mua rằng quyền cùng đầu tư giúp họ yên tâm thương vụ tốt và không trả giá quá cao. Bên mua hiểu lập luận và đi thêm một bước: John có hiểu rằng nếu ông không cùng đầu tư thì họ sẽ coi đó là dấu hiệu xấu và có lẽ không làm thương vụ không? Như vậy cơ hội được đầu tư thực chất thành yêu cầu phải đầu tư. Mọi việc bạn làm đều phát tín hiệu, kể cả việc không phát tín hiệu.

### 10. Phản tín hiệu (Countersignaling)

Từ phần trước, có vẻ ai có khả năng phát tín hiệu về loại của mình thì nên phát, để tách khỏi người không làm được. Thế nhưng một số người có khả năng nhất lại không làm. Feltovich, Harbaugh và To đưa ra một loạt ví dụ: người mới giàu phô trương của cải, còn người giàu lâu đời khinh kiểu phô trương thô thiển đó; quan chức nhỏ chứng tỏ địa vị bằng những màn thể hiện quyền lực vặt, còn người thật sự quyền lực thể hiện sức mạnh bằng cử chỉ rộng lượng; người học vấn trung bình khoe nét chữ đều đặn, còn người học cao thường viết nguệch ngoạc; học sinh trung bình trả lời câu hỏi dễ của thầy, còn học sinh giỏi nhất ngại chứng tỏ mình biết những điều vụn vặt; người quen tỏ thiện ý bằng cách lịch sự lờ đi khuyết điểm của ta, còn bạn thân tỏ sự gần gũi bằng cách trêu chính khuyết điểm đó; người năng lực vừa phải tìm bằng cấp chính thức để gây ấn tượng, còn người tài thường không nhắc tới bằng cấp dù đã có; người danh tiếng trung bình phản bác những lời buộc tội nhắm vào mình, còn người rất được kính trọng thấy trả lời là hạ thấp mình.

Nhận định của họ là trong một số hoàn cảnh, cách tốt nhất để thể hiện năng lực hay loại của mình là không phát tín hiệu, từ chối chơi trò phát tín hiệu. Hai tác giả minh hoạ bằng ba loại bạn đời tiềm năng: kẻ đào mỏ, người khó đoán (hai tác giả gọi là "dấu hỏi") và người yêu thật lòng. Một người đề nghị người kia ký hợp đồng tiền hôn nhân, lập luận rằng ký là rẻ nếu yêu thật và rất đắt nếu đến với nhau vì tiền. Điều đó đúng. Nhưng người kia có thể đáp: "Anh/em phân biệt được người yêu thật với kẻ đào mỏ; chính loại dấu hỏi mới làm anh/em bối rối, lúc nhầm kẻ đào mỏ với dấu hỏi, lúc nhầm dấu hỏi với người yêu thật. Nếu tôi ký, tức là tôi thấy cần tách mình khỏi kẻ đào mỏ, tức tôi là dấu hỏi. Nên tôi sẽ giúp anh/em thấy tôi là người yêu thật bằng cách không ký."

Đây có phải cân bằng không? Giả sử kẻ đào mỏ và người yêu thật không ký, còn dấu hỏi ký. Khi đó ai ký đều bị coi là dấu hỏi, vị trí kém hơn người yêu thật; còn với người không ký thì không có nhầm lẫn, vì họ chỉ có thể là kẻ đào mỏ hoặc người yêu thật, và người kia phân biệt được hai loại này. Nếu dấu hỏi cũng quyết định không ký, người kia sẽ hiểu họ là kẻ đào mỏ hoặc người yêu thật; việc đó tốt hay xấu cho dấu hỏi tuỳ họ dễ bị nhầm với loại nào hơn. Nếu dấu hỏi dễ bị coi là kẻ đào mỏ hơn, không ký là ý tồi.

Ý lớn rất đơn giản: ta có những cách khác để biết loại người ngoài tín hiệu họ phát; và chính việc họ phát tín hiệu cũng là một tín hiệu cho thấy họ đang cố tách mình khỏi một loại khác không đủ sức phát cùng tín hiệu. Trong một số hoàn cảnh, tín hiệu mạnh nhất bạn có thể phát là cho thấy mình không cần phát tín hiệu. Chú thích của tác giả: chỉ một lần trong kinh nghiệm của hai tác giả, một ứng viên trợ lý giáo sư mặc quần jeans tới buổi thuyết trình xin việc; ý nghĩ đầu tiên của họ là chỉ thiên tài mới dám không mặc com-lê, mãi sau mới biết hãng hàng không làm thất lạc hành lý của anh ta. Sylvia Nasar kể về John Nash: theo Fagi Levinson, người được coi như "mẹ" của khoa toán MIT, việc Nash đi ngược khuôn phép không gây sốc như người ta tưởng, vì ai ở đó cũng là ngôi sao kiêu kỳ; một nhà toán học tầm thường phải tuân thủ khuôn phép, còn người giỏi thì làm gì cũng được.

Rick Harbaugh và Ted To nghiên cứu thêm về phản tín hiệu (hai tác giả đùa bằng cách gọi ông là "Prof. Rick Harbaugh, Ph.D."). Họ nghe lời chào hộp thư thoại ở 26 trường thuộc hai hệ thống University of California và California State University:

| Nhóm trường | Tỷ lệ nhà kinh tế xưng học vị trong lời chào hộp thư thoại |
|---|---|
| Trường có chương trình tiến sĩ | dưới 4% |
| Trường không có chương trình tiến sĩ | 27% |

Tất cả đều có bằng tiến sĩ, nhưng nhắc học vị cho người gọi cho thấy bạn cần một chứng nhận để phân biệt mình. Những giảng viên thật sự xuất sắc có thể cho thấy họ nổi tiếng tới mức không cần phát tín hiệu. Hai tác giả kết: cứ gọi chúng tôi là Avinash và Barry.

**Câu đố "A Trip to the Bar".** Hai tác giả để lại một câu đố, không gọi là "Trip to the Gym" vì không cần tính toán, và không đưa đáp án vì câu trả lời đúng tuỳ hoàn cảnh từng người; người đọc tự chấm điểm. Bạn đang trong buổi hẹn đầu với một người bạn thấy hấp dẫn và muốn gây ấn tượng tốt vì sẽ không có cơ hội thứ hai. Nhưng bạn biết đối phương hiểu rằng ấn tượng có thể làm giả, nên phải nghĩ ra tín hiệu đáng tin về phẩm chất của mình. Đồng thời bạn muốn sàng lọc đối phương, xem sức hút ban đầu có nền tảng bền vững không, để quyết định có tiếp tục mối quan hệ. Hãy tìm những chiến lược phát tín hiệu và sàng lọc tốt.

### 11. Gây nhiễu tín hiệu (Signal Jamming)

Khi mua xe cũ trực tiếp của chủ trước, bạn muốn biết họ chăm xe thế nào. Bạn có thể nghĩ tình trạng hiện tại là tín hiệu: xe được rửa sạch, đánh bóng, nội thất sạch, thảm được hút bụi thì có lẽ được chăm tốt. Nhưng chủ xe cẩu thả cũng bắt chước được khi rao bán, và quan trọng nhất, chi phí làm sạch xe với chủ cẩu thả không cao hơn với chủ cẩn thận. Tín hiệu đó vì vậy không phân biệt được hai loại; như ví dụ MBA cho thấy, chênh lệch chi phí là điều kiện thiết yếu để tín hiệu làm được việc này.

Thực ra có vài chênh lệch chi phí nhỏ: người luôn chăm xe có thể tự hào và thậm chí thích tự rửa, đánh bóng xe; người cẩu thả có thể rất bận và khó dành thời gian. Chênh lệch nhỏ như vậy có đủ để tín hiệu hiệu quả không? Câu trả lời tuỳ tỷ lệ hai loại trong dân số. Hãy xét cách người mua diễn giải xe sạch hay bẩn. Nếu ai cũng làm sạch xe trước khi bán, người mua chẳng học được gì từ một chiếc xe sạch: anh ta coi nó như rút ngẫu nhiên từ tổng thể các chủ xe. Một chiếc xe bẩn thì chắc chắn là của chủ cẩu thả.

| Tỷ lệ chủ cẩu thả | Điều xảy ra | Loại cân bằng |
|---|---|---|
| Nhỏ | Xe sạch gây ấn tượng rất tốt, vì khả năng chủ cẩn thận cao; người mua dễ mua hơn hoặc trả cao hơn. Vì lợi ích đó, cả chủ cẩu thả cũng rửa xe | Cân bằng gộp (pooling): mọi loại cùng làm một việc, hành động hoàn toàn không mang thông tin |
| Lớn | Nếu ai cũng rửa xe, xe sạch không gây ấn tượng, chủ cẩu thả không đáng bỏ công rửa (chủ cẩn thận thì xe luôn sạch), nên không có cân bằng gộp. Nhưng nếu không chủ cẩu thả nào rửa, một người rửa sẽ được nhầm là chủ cẩn thận và thấy đáng bỏ chút công, nên cũng không có cân bằng tách biệt. Kết quả nằm giữa: mỗi chủ cẩu thả dùng chiến lược hỗn hợp, rửa xe với một xác suất dương nhưng không chắc chắn | Cân bằng bán tách biệt (semi-separating) |

Đối lập với cân bằng gộp là cân bằng tách biệt (separating): một loại phát tín hiệu, loại kia không, nên hành động nhận diện chính xác, tức tách các loại ra. Trong trường hợp bán tách biệt, các xe sạch trên thị trường là một hỗn hợp của chủ cẩn thận và chủ cẩu thả. Người mua biết tỷ lệ hỗn hợp và suy ngược ra xác suất chủ một chiếc xe sạch là người cẩn thận; mức họ sẵn lòng trả tuỳ xác suất đó. Ngược lại, mức sẵn lòng trả phải sao cho mỗi chủ cẩu thả bàng quan giữa bỏ chút công làm sạch xe và để bẩn (tiết kiệm công nhưng bị nhận ra là chủ cẩu thả và bán được giá thấp hơn). Phép tính khá phức tạp, cần công thức gọi là quy tắc Bayes để suy xác suất của các loại từ hành động quan sát được; phần poker phía sau minh hoạ cách dùng.

### 12. Vệ sĩ bằng những lời nói dối (Bodyguard of Lies)

Tình báo thời chiến cho những ví dụ đặc biệt hay về chiến lược làm rối tín hiệu của đối phương. Churchill từng nói với Stalin tại Hội nghị Tehran năm 1943 rằng thời chiến, sự thật quý giá đến mức luôn phải có một đoàn vệ sĩ bằng những lời nói dối đi kèm. Có chuyện hai thương gia đối thủ gặp nhau ở ga xe lửa Warsaw. Người thứ nhất hỏi: "Anh đi đâu?" Người kia đáp: "Đi Minsk." Người thứ nhất nói: "Đi Minsk à? Anh trơ thật! Tôi biết anh nói đi Minsk vì muốn tôi tin anh đi Pinsk. Nhưng tôi lại biết anh thật sự đi Minsk. Vậy sao anh nói dối tôi?"

Một số lời nói dối hay nhất là khi người ta nói thật để không được tin. Ngày 27/6/2007, Ashraf Marwan chết ở London sau một cú ngã đáng ngờ từ ban công căn hộ tầng bốn ở Mayfair, khép lại cuộc đời của một người hoặc là điệp viên có quan hệ tốt nhất của Israel, hoặc là điệp viên hai mang tài giỏi của Ai Cập. Marwan là con rể Tổng thống Ai Cập Abdel Nasser và là người liên lạc của ông với cơ quan tình báo. Ông tự nguyện làm việc cho Mossad của Israel, và Mossad xác định thông tin ông cung cấp là thật; Marwan trở thành người dẫn đường cho Israel hiểu cách nghĩ của giới lãnh đạo Ai Cập.

| Thời điểm | Sự kiện |
|---|---|
| Tháng 4/1973 | Marwan gửi mật mã "Củ cải" (Radish), nghĩa là chiến tranh sắp nổ ra. Israel gọi hàng nghìn quân dự bị và tốn hàng chục triệu cho một báo động hoá ra là giả |
| 5/10/1973 | Marwan lại gửi "Củ cải": Ai Cập và Syria sẽ đồng loạt tấn công ngày hôm sau, ngày lễ Yom Kippur, lúc hoàng hôn. Lần này trưởng tình báo quân đội cho rằng Marwan là điệp viên hai mang và coi tin này là bằng chứng chiến tranh chưa tới |
| 6/10/1973 | Cuộc tấn công nổ ra lúc 2 giờ chiều và suýt tràn ngập quân đội Israel. Tướng Zeira, trưởng tình báo Israel, mất chức vì thất bại này |
| 27/6/2007 | Marwan chết sau cú ngã ở London. Ông là điệp viên của Israel hay điệp viên hai mang vẫn chưa rõ; nếu cái chết không phải tai nạn, cũng không biết Israel hay Ai Cập phải chịu trách nhiệm |

Khi chơi chiến lược hỗn hợp, bạn không thể lừa đối phương mọi lần; tốt nhất chỉ có thể giữ cho họ phải đoán và lừa được đôi lần. Bạn biết khả năng thành công nhưng không nói trước được lần cụ thể nào sẽ thành. Vì thế, khi biết mình đang nói chuyện với người muốn đánh lừa mình, tốt nhất có thể là bỏ qua mọi lời họ nói, thay vì tin nguyên văn hay suy ra điều ngược lại là thật.

Nhưng hành động vẫn nói to hơn lời nói một chút. Nhìn đối thủ làm gì, bạn có thể đánh giá khả năng tương đối của những điều họ muốn giấu. Không thể tin nguyên văn lời đối thủ, nhưng điều đó không có nghĩa bỏ qua cả hành động của họ khi tìm hiểu lợi ích thật của họ. Tỷ lệ pha trộn đúng trong chiến lược cân bằng của một người phụ thuộc vào kết quả của người đó; quan sát nước đi của họ cho biết phần nào tỷ lệ đang dùng, và là bằng chứng quý để suy ra lợi ích của đối thủ. Chiến lược cược trong poker là ví dụ điển hình.

Người chơi poker quen với việc phải pha trộn lối chơi. John McDonald khuyên rằng ván bài phải luôn được che sau "mặt nạ của sự thiếu nhất quán": người chơi giỏi phải tránh lối mòn và hành động ngẫu nhiên, thậm chí đôi khi vi phạm cả nguyên tắc cơ bản của lối chơi đúng. Người chơi "chặt", không bao giờ tố láo, hiếm khi thắng ván lớn vì chẳng ai tố theo họ; họ có thể thắng nhiều ván nhỏ nhưng rốt cuộc vẫn thua. Người chơi "lỏng", tố láo quá nhiều, luôn bị theo, nên cũng thua. Chiến lược tốt nhất pha trộn cả hai.

Giả sử bạn biết một đối thủ quen thuộc, khi có bài tốt, tố hai phần ba số lần và theo một phần ba số lần; khi có bài xấu, bỏ bài hai phần ba số lần và tố (tức tố láo) một phần ba số lần. (Nói chung, đang tố láo thì theo là ý tồi, vì không mong có bài thắng.) Bảng dựng lại từ sách; hai tác giả lưu ý đây không phải bảng kết quả: các cột không phải chiến lược của người chơi nào mà là các khả năng do may rủi, và ô là xác suất chứ không phải kết quả.

| Chất lượng bài | Tố (raise) | Theo (call) | Bỏ (fold) |
|---|---|---|---|
| Tốt | 2/3 | 1/3 | 0 |
| Xấu | 1/3 | 0 | 2/3 |

Giả sử trước khi đối thủ cược, bạn tin bài tốt và bài xấu đều có khả năng như nhau. Vì tỷ lệ pha trộn của họ phụ thuộc bài, cược cho bạn thêm thông tin. Thấy họ bỏ bài, bạn chắc chắn bài xấu; thấy họ theo, bạn biết bài tốt; nhưng cả hai trường hợp này cuộc cược đã kết thúc. Nếu họ tố, khả năng bài tốt là 2:1. Cược không luôn lộ hoàn toàn bài, nhưng bạn biết nhiều hơn lúc đầu: sau khi thấy tố, khả năng bài tốt tăng từ một nửa lên hai phần ba.

Phép tính này dùng quy tắc Bayes: xác suất đối thủ có bài tốt khi đã thấy cược "X" bằng xác suất họ vừa có bài tốt vừa cược X chia cho xác suất họ cược X nói chung.

| Bước | Phép tính |
|---|---|
| Xác suất vừa bài tốt vừa tố | (1/2) × (2/3) = 1/3 |
| Xác suất vừa bài xấu vừa tố (tố láo) | (1/2) × (1/3) = 1/6 |
| Xác suất thấy tố | 1/3 + 1/6 = 1/2 |
| Xác suất bài tốt khi thấy tố | (1/3) / (1/2) = 2/3 |

### 13. Phân biệt giá bằng sàng lọc (Price Discrimination by Screening)

Ứng dụng của sàng lọc tác động tới đời sống của người đọc nhiều nhất là phân biệt giá. Với gần như mọi hàng hoá, dịch vụ, có người sẵn lòng trả nhiều hơn người khác, vì giàu hơn, sốt ruột hơn hay đơn giản là sở thích khác. Chừng nào chi phí sản xuất và bán cho một khách thấp hơn mức khách sẵn lòng trả, người bán muốn phục vụ khách đó với giá cao nhất có thể, tức mỗi khách một giá: giảm giá cho người không chịu trả nhiều mà không phải giảm cho người chịu trả nhiều. Điều này thường khó, vì người bán không biết chính xác mỗi khách sẵn lòng trả bao nhiêu, và kể cả biết thì còn phải ngăn khách mua giá thấp bán lại cho khách bị tính giá cao. Hai tác giả gác vấn đề bán lại, chỉ tập trung vào vấn đề thông tin.

Mẹo phổ biến là tạo ra nhiều phiên bản của cùng một sản phẩm với giá khác nhau. Mỗi khách tự do chọn bất kỳ phiên bản nào và trả giá người bán đặt cho phiên bản đó, nên không có phân biệt công khai; nhưng người bán đặt đặc tính và giá của từng phiên bản sao cho mỗi loại khách chọn một phiên bản khác nhau. Lựa chọn đó ngầm lộ thông tin riêng của khách, tức mức sẵn lòng trả: người bán đang sàng lọc người mua.

- **Sách bìa cứng và bìa mềm.** Người sẵn lòng trả nhiều cũng thường là người muốn có sách đọc ngay, vì cần thông tin gấp hay muốn gây ấn tượng với bạn bè, đồng nghiệp; người khác trả ít hơn và chịu chờ. Nhà xuất bản tận dụng quan hệ nghịch giữa mức sẵn lòng trả và mức sẵn lòng chờ bằng cách ra bản bìa cứng giá cao trước, rồi khoảng một năm sau ra bản bìa mềm giá thấp. Chênh lệch chi phí in nhỏ hơn nhiều so với chênh lệch giá; việc tạo phiên bản chỉ là mẹo sàng lọc người mua. (Hai tác giả hỏi người đọc đang đọc bản nào.)
- **Phần mềm bản "lite" hay "sinh viên".** Bản này ít tính năng hơn và rẻ hơn nhiều. Một số người dùng chịu trả giá cao, có thể vì công ty trả tiền, hoặc vì muốn đủ tính năng phòng khi cần; người khác chỉ cần tính năng cơ bản. Chi phí phục vụ thêm một khách rất nhỏ (ghi và gửi một đĩa CD, còn ít hơn nếu tải qua Internet), nên nhà sản xuất muốn bán cho cả người trả ít mà vẫn thu nhiều của người trả nhiều. Họ thường làm bản lite bằng cách lấy bản đầy đủ rồi tắt bớt tính năng, nên bản rẻ lại tốn chi phí làm hơn; điều nghe như nghịch lý này chỉ hiểu được qua mục đích phân biệt giá bằng sàng lọc.
- **Máy in laser IBM.** Bản E in 5 trang/phút; bản nhanh in 10 trang/phút, đắt hơn 200 USD. Khác biệt duy nhất là IBM gắn thêm vào phần sụn của bản E một con chip chèn các trạng thái chờ để làm chậm việc in. Không làm vậy, IBM phải bán mọi máy in cùng một giá; có bản chậm, hãng bán rẻ hơn được cho người dùng gia đình chịu chờ lâu hơn.
- **Đầu DVD Sharp.** Hai mẫu DVE611 và DV740U làm cùng một nhà máy ở Thượng Hải. Khác biệt chính là DVE611 không phát được đĩa định dạng chuẩn châu Âu (PAL) trên tivi chuẩn Mỹ (NTSC). Nhưng tính năng đó vẫn có sẵn, chỉ bị giấu: Sharp mài bớt nút chuyển hệ rồi che bằng mặt nạ điều khiển. Vài người dùng khéo léo phát hiện và chia sẻ trên mạng; chỉ cần đục một lỗ đúng chỗ trên mặt nạ là khôi phục đủ tính năng. Doanh nghiệp thường tốn nhiều công tạo ra phiên bản bị làm hỏng của sản phẩm, còn khách hàng thường tốn nhiều công để khôi phục nó.

**Ví dụ số: hãng hàng không PITS.** Định giá vé máy bay có lẽ là ví dụ phân biệt giá quen thuộc nhất, nên hai tác giả đi sâu để cho thấy mặt định lượng. Hãng giả định Pie-In-The-Sky (PITS) bay tuyến Podunk – South Succotash, chở khách doanh nhân (sẵn lòng trả cao hơn) và khách du lịch. Để phục vụ khách du lịch có lãi mà không phải bán giá thấp cho doanh nhân, PITS phải tạo các phiên bản của cùng chuyến bay và định giá sao cho mỗi loại khách chọn một phiên bản. Hai tác giả lấy ví dụ hạng nhất và hạng phổ thông (một cách phân biệt phổ biến khác là vé không điều kiện và vé có điều kiện). Giả sử 30% khách là doanh nhân, 70% là khách du lịch, tính trên 100 khách. Bảng dựng lại từ sách (USD):

| Hạng | Chi phí của PITS | Giá tối đa sẵn lòng trả: du lịch | Giá tối đa sẵn lòng trả: doanh nhân | Lợi nhuận tiềm năng: du lịch | Lợi nhuận tiềm năng: doanh nhân |
|---|---|---|---|---|---|
| Phổ thông | 100 | 140 | 225 | 40 | 125 |
| Hạng nhất | 150 | 175 | 300 | 25 | 150 |

Mức tối đa mỗi loại khách sẵn lòng trả được gọi là **giá tối đa sẵn lòng trả (reservation price)**.

*Trường hợp lý tưởng: phân biệt giá hoàn hảo.* Giả sử PITS biết loại từng khách (chẳng hạn nhìn cách ăn mặc khi họ đặt vé), không có luật cấm và không thể bán lại. Với mỗi doanh nhân, bán hạng nhất 300 USD lãi 150 USD, bán phổ thông 225 USD lãi 125 USD, nên hạng nhất tốt hơn. Với mỗi khách du lịch, bán hạng nhất 175 USD lãi 25 USD, bán phổ thông 140 USD lãi 40 USD, nên phổ thông tốt hơn. PITS lý tưởng nhất là chỉ bán hạng nhất cho doanh nhân, chỉ bán phổ thông cho khách du lịch, mỗi bên đúng bằng giá tối đa sẵn lòng trả. Lợi nhuận trên 100 khách: (140 – 100) × 70 + (300 – 150) × 30 = 2.800 + 4.500 = 7.300 USD.

*Trường hợp thực tế: sàng lọc.* Nếu PITS không nhận ra loại khách, hoặc không được dùng thông tin đó để phân biệt công khai, điều quan trọng nhất là hãng không thể thu doanh nhân đủ 300 USD cho hạng nhất. Doanh nhân có thể mua vé phổ thông 140 USD trong khi sẵn lòng trả 225 USD, được thêm một khoản lợi, gọi là **thặng dư tiêu dùng (consumer surplus)**, bằng 85 USD (có thể dùng cho ăn ở tốt hơn trong chuyến đi). Trả đủ 300 USD cho hạng nhất thì thặng dư bằng 0, nên họ sẽ chuyển sang phổ thông và sàng lọc thất bại. Giá hạng nhất tối đa phải cho doanh nhân ít nhất 85 USD thặng dư, tức 300 – 85 = 215 USD (có lẽ nên là 214 USD để doanh nhân có lý do rõ ràng chọn hạng nhất, nhưng hai tác giả bỏ qua chênh lệch nhỏ này). Lợi nhuận: (140 – 100) × 70 + (215 – 150) × 30 = 2.800 + 1.950 = 4.750 USD.

| Chiến lược (30% doanh nhân) | Giá phổ thông | Giá hạng nhất | Lợi nhuận trên 100 khách |
|---|---|---|---|
| Phân biệt giá hoàn hảo (biết loại từng khách) | 140 | 300 | 7.300 USD |
| Sàng lọc qua tự lựa chọn | 140 | 215 | 4.750 USD |
| Chênh lệch | | | 2.550 USD = 85 × 30 |

PITS sàng lọc thành công, nhưng phải hy sinh một phần lợi nhuận: chênh lệch 2.550 USD đúng bằng 85 (mức giảm giá hạng nhất so với giá tối đa doanh nhân sẵn lòng trả) nhân 30 (số doanh nhân). Hãng phải giữ giá hạng nhất đủ thấp để doanh nhân có đủ động cơ chọn nó chứ không "đào ngũ" sang lựa chọn dành cho khách du lịch. Yêu cầu này đối với chiến lược của người sàng lọc được gọi là **ràng buộc tương thích khuyến khích (incentive compatibility constraint)**.

Cách duy nhất để thu doanh nhân hơn 215 USD mà họ không đào ngũ là tăng giá phổ thông. Ví dụ hạng nhất 240 USD và phổ thông 165 USD: doanh nhân được thặng dư 300 – 240 = 60 USD ở hạng nhất và 225 – 165 = 60 USD ở phổ thông, nên vừa đủ chịu mua hạng nhất. Nhưng giá phổ thông 140 USD đã chạm mức tối đa khách du lịch sẵn lòng trả; chỉ cần 141 USD là PITS mất hết họ. Yêu cầu loại khách đó vẫn muốn mua được gọi là **ràng buộc tham gia (participation constraint)** của họ. Chiến lược định giá của PITS bị kẹp giữa ràng buộc tham gia của khách du lịch và ràng buộc tương thích khuyến khích của doanh nhân. Trong tình huống này, cặp giá 215 USD cho hạng nhất và 140 USD cho phổ thông thực sự là có lãi nhất; chứng minh chặt chẽ cần chút toán nên hai tác giả chỉ khẳng định.

**Bài "Trip to the Gym" số 5.** Đề: còn một ràng buộc tham gia cho doanh nhân và một ràng buộc tương thích khuyến khích cho khách du lịch; hãy kiểm tra rằng chúng tự động được thoả ở các mức giá đã nêu. *Đáp án của sách (phần Workouts):* giá hạng nhất 215 USD thấp hơn hẳn mức 300 USD doanh nhân sẵn lòng trả cho hạng này, nên ràng buộc tham gia của họ được thoả. Khách du lịch được thặng dư bằng 0 (140 – 140) khi mua phổ thông, nhưng thặng dư âm (175 – 215 = –40 USD) nếu mua hạng nhất, nên họ không muốn đổi; ràng buộc tương thích khuyến khích của họ được thoả.

Chiến lược này có tối ưu hay không tuỳ các con số cụ thể. Nếu tỷ lệ doanh nhân cao hơn nhiều, chẳng hạn 50%, khoản hy sinh 85 USD trên mỗi doanh nhân có thể quá lớn so với lợi ích giữ số ít khách du lịch. PITS có thể làm tốt hơn bằng cách không phục vụ họ, tức vi phạm ràng buộc tham gia của họ, và nâng giá hạng nhất cho doanh nhân:

| Chiến lược (50% doanh nhân) | Lợi nhuận trên 100 khách |
|---|---|
| Sàng lọc: phổ thông 140, hạng nhất 215 | (140 – 100) × 50 + (215 – 150) × 50 = 2.000 + 3.250 = 5.250 USD |
| Chỉ bán hạng nhất 300 USD cho doanh nhân | (300 – 150) × 50 = 7.500 USD |

Khi chỉ có ít khách trả thấp, người bán có thể thấy bỏ hẳn họ lợi hơn là phải hạ giá cho số đông khách trả cao để họ khỏi chuyển sang phiên bản giá rẻ. Hai tác giả kết rằng khi đã biết nhìn, người đọc sẽ thấy sàng lọc để phân biệt giá ở khắp nơi, và giới nghiên cứu phân tích các chiến lược sàng lọc bằng tự lựa chọn cũng thường xuyên như vậy. Một số chiến lược rất phức tạp và cần nhiều toán, nhưng ý cơ bản đằng sau tất cả là sự giằng co giữa hai yêu cầu song sinh: tương thích khuyến khích và tham gia.

### 14. Tình huống: hoà nhập bí mật (Case Study: Going Undercover)

Tanya, một người bạn khác của hai tác giả, là nhà nhân học. Trong khi phần lớn nhà nhân học tới tận cùng trái đất để nghiên cứu một bộ lạc lạ, Tanya làm điền dã ở London, và đối tượng của cô là các phù thuỷ. Ngay ở London hiện đại vẫn có số người đáng ngạc nhiên tụ họp trao đổi bùa phép và học phép thuật (dù làm phù thuỷ đi tàu điện ngầm cũng cần chút tự biện minh). Nhà nhân học thường khó lấy được lòng tin của đối tượng, nhưng nhóm của Tanya đặc biệt cởi mở: khi cô nói mình là nhà nhân học, họ coi đó là một mẹo khéo, rằng cô thực ra là phù thuỷ có vỏ bọc tuyệt vời. Một đặc điểm lạ là các buổi họp của họ diễn ra trong tình trạng khoả thân. Vì sao?

Thảo luận của sách: mọi nhóm "ngoài lề" đều phải lo thành viên chỉ là người quan sát chứ không thật sự tham gia, ngồi đó chế giễu cả quá trình. Khi đang ngồi khoả thân, khó mà nói mình chỉ đứng xem và cười người khác; bạn đã dấn thân hẳn. Vì vậy khoả thân là một công cụ sàng lọc đáng tin: nếu thật lòng tin vào hội, có mặt trong tình trạng khoả thân gần như không tốn gì; nếu là người hoài nghi, việc đó rất khó giải thích, với người khác lẫn với chính mình. Chú thích của tác giả: trong bộ phim *Gray's Anatomy*, nghệ sĩ độc thoại Spalding Gray kể một trải nghiệm thử thách tương tự trong lều xông hơi của người Mỹ bản địa. Cũng vì lý do đó, nghi thức nhập băng đảng thường đòi những việc tương đối rẻ với người thật lòng muốn sống đời băng đảng (xăm mình, phạm tội) nhưng rất đắt với một cảnh sát chìm muốn trà trộn.

Các tình huống khác về diễn giải và thao túng thông tin nằm ở Chương 14: "The Other Person's Envelope Is Always Greener" (phong bì của người khác bao giờ cũng xanh hơn), "But One Life to Lay Down for Your Country" (chỉ một mạng sống để hiến cho tổ quốc), "King Solomon's Dilemma Redux" (thế khó của vua Solomon, trở lại) và "The King Lear Problem" (bài toán vua Lear).

**Ví dụ hôm nay** (minh hoạ của người tổng hợp, con số giả định). Một người bán điện thoại cũ trên mạng rao hai mức giá cho cùng một mẫu máy: 6 triệu đồng không bảo hành, hoặc 6,7 triệu đồng kèm bảo hành 6 tháng, lỗi gì cũng sửa miễn phí. Giả sử với một chiếc máy tốt, chi phí sửa chữa kỳ vọng trong 6 tháng là 200.000 đồng; với một chiếc máy đã thay linh kiện kém, con số đó là 1,5 triệu đồng. Phần chênh 700.000 đồng nằm giữa hai mức này, nên người bán chỉ có lợi khi đưa ra lựa chọn có bảo hành nếu họ biết máy mình tốt. Người mua cũng có thể chủ động sàng lọc: "tôi trả thêm 700.000 đồng nếu anh bảo hành 6 tháng bằng văn bản". Ngược lại, lời mời "anh cứ mang máy ra tiệm kiểm tra" không nói lên gì, vì người bán máy kém cũng chẳng mất gì khi mời. Và như hai tác giả cảnh báo, bảo hành chỉ có giá trị nếu thi hành được: lời hứa của một tài khoản mạng xã hội vô danh kém tin hơn nhiều so với lời hứa của một cửa hàng có địa chỉ và danh tiếng cần giữ.

## Luận điểm kinh tế cốt lõi

### Mệnh đề

Khi một bên biết nhiều hơn bên kia, lời nói không đủ để truyền thông tin nếu lợi ích hai bên lệch nhau; chỉ những hành động có chi phí khác nhau với các loại người chơi khác nhau mới truyền thông tin đáng tin. Người biết nhiều dùng hành động đó để phát tín hiệu hoặc gây nhiễu; người biết ít thiết kế lựa chọn để sàng lọc. Việc khắc phục thông tin bất cân xứng luôn tốn một cái giá, và người chơi nào không nhận ra hành động (kể cả không hành động) của mình đang bị diễn giải sẽ tự làm hại mình.

### Giả định

- Người chơi có lý trí và theo đuổi lợi ích riêng; người nói dối sẽ bắt chước mọi tín hiệu rẻ.
- Mỗi người chơi biết loại của chính mình (năng lực, chất lượng hàng, rủi ro), còn người khác chỉ biết phân phối xác suất của các loại.
- Có ít nhất một hành động mà chi phí của nó khác nhau giữa các loại (tiêu chuẩn chênh lệch chi phí).
- Người quan sát hiểu cấu trúc trò chơi và cập nhật niềm tin theo quy tắc Bayes.
- Cam kết đi kèm tín hiệu (như bảo hành) có thể thi hành được.

### Cơ chế

1. Người biết nhiều có động cơ nói điều có lợi cho mình, nên lời nói của họ chỉ đáng tin khi lợi ích trùng với người nghe hoặc khi điều họ nói đi ngược lợi ích của chính họ.
2. Một hành động đáng tin khi nó tối ưu với người chơi nếu và chỉ nếu họ thuộc loại mà họ muốn chứng tỏ: bảo hành rẻ với xe tốt, đắt với xe tồi; MBA đáng học với người có tài, không đáng với người không có tài.
3. Người biết ít có thể chủ động đặt ra lựa chọn như vậy (sàng lọc): đòi bảo hành, thực đơn gói bảo hiểm, thủ tục mất thời gian, trợ cấp bằng hiện vật, các hạng vé.
4. Nếu chênh lệch chi phí quá nhỏ so với lợi ích của việc được nhầm là loại tốt, các loại sẽ làm như nhau (cân bằng gộp) hoặc pha trộn (bán tách biệt), và hành động chỉ mang một phần hay không mang thông tin.
5. Khi không có cách phân biệt, thị trường có thể bị lựa chọn ngược làm sụp đổ (xe chanh); thiết kế khéo có thể tạo lựa chọn thuận lợi (Capital One).
6. Sàng lọc có giá: người sàng lọc phải nhường một phần lợi ích cho loại tốt để thoả ràng buộc tương thích khuyến khích, đồng thời giữ ràng buộc tham gia của loại kia; đôi khi bỏ hẳn một loại khách lại lợi hơn.
7. Vì mọi hành động đều bị diễn giải, cả việc không phát tín hiệu cũng mang thông tin (điểm pass/fail, quyền cùng đầu tư của John), và loại tốt nhất đôi khi chứng tỏ mình bằng cách không phát tín hiệu (phản tín hiệu).

### Bằng chứng và ví dụ hai tác giả đưa ra

- Sue và yêu cầu hình xăm; vua Solomon và hai người mẹ.
- Người phục vụ nhà hàng; câu của G. H. Hardy về Tổng giám mục Canterbury; cầu thủ sút phạt đền.
- Hãng luật chiêu đãi thực tập sinh; bằng tốt nghiệp đại học và cuộc đua chuột bằng cấp.
- Bảo hành xe cũ (500 USD so với 2.000 USD, chênh giá 800 USD); lời mời kiểm tra xe; Hyundai năm 1999 (10 năm hoặc 100.000 dặm).
- Thị trường xe chanh của Akerlof (1.000/1.500 và 3.000/4.000 USD, giá trung bình 2.750 USD); kinh nghiệm xe cũ của Dixit thời nghiên cứu sinh.
- Spence, Mirrlees, Vickrey, Rothschild và Stiglitz; bảo hiểm nhân thọ 5 xu mỗi đô la và hiệu ứng Groucho Marx; Capital One tăng trưởng kép 40% trong một thập kỷ.
- MBA: chi phí 200.000 USD, lương 50.000 USD so với 90.000–130.000 USD, xác suất tốt nghiệp 100% so với 50%, so sánh với tuyển ngẫu nhiên lỗ kỳ vọng 250.000 USD.
- Workers' Compensation (từ 20% hồ sơ trở lên có gian lận); trợ cấp xe lăn bằng hiện vật.
- Con chó không sủa của Sherlock Holmes; điểm pass/fail; quyền cùng đầu tư của John.
- Danh sách phản tín hiệu của Feltovich, Harbaugh và To; prenup với ba loại bạn đời; hộp thư thoại (dưới 4% so với 27%); John Nash.
- Chủ xe rửa xe trước khi bán (gộp, tách biệt, bán tách biệt).
- Churchill ở Tehran; chuyện Minsk – Pinsk; Ashraf Marwan và chiến tranh Yom Kippur 1973.
- Poker và quy tắc Bayes (xác suất bài tốt tăng từ 1/2 lên 2/3 sau khi thấy tố).
- Sách bìa cứng/bìa mềm, phần mềm bản lite, máy in IBM, đầu DVD Sharp; hãng hàng không PITS (7.300, 4.750, 5.250, 7.500 USD).
- Các phù thuỷ khoả thân ở London; nghi thức nhập băng đảng.

### Kết luận và hàm ý chính sách

- Đừng tin lời của người có lợi ích đối nghịch, cũng đừng suy ra điều ngược lại; hãy nhìn hành động có chi phí.
- Muốn lời mình được tin, hãy "đặt tiền vào chỗ lời nói": chọn hành động mà người nói dối không đủ sức bắt chước, và bảo đảm cam kết đi kèm thi hành được.
- Cạnh tranh phát tín hiệu bằng bằng cấp có thể thành cuộc đua lãng phí mà cá nhân không tự dừng được; hai tác giả cho rằng cần giải pháp chính sách công.
- Thủ tục hành chính và trợ cấp bằng hiện vật, thường bị chê kém hiệu quả, có thể là công cụ sàng lọc hợp lý khi nhà nước không phân biệt được người thật sự cần hỗ trợ.
- Thiết kế sản phẩm, hợp đồng, chính sách nên tính tới lựa chọn ngược: tăng giá bảo hiểm có thể đuổi người rủi ro thấp; một ưu đãi khéo có thể tự lọc ra khách tốt.
- Người thiết kế thực đơn giá phải cân hai ràng buộc: tương thích khuyến khích và tham gia.

### Trong ngôn ngữ kinh tế học

- **Kinh tế học thông tin (economics of information).** Nhánh nghiên cứu hành vi và thị trường khi thông tin bất cân xứng; Akerlof, Spence và Stiglitz cùng nhận giải Nobel kinh tế năm 2001 cho các công trình được nhắc trong chương (Mirrlees và Vickrey nhận giải năm 1996).
- **Mô hình phát tín hiệu của Spence (job market signaling).** Giáo dục có thể có giá trị vì nó tách người giỏi khỏi người kém, kể cả khi không làm tăng năng suất; điều kiện then chốt là chi phí học khác nhau giữa các loại (điều kiện "single crossing" trong lý thuyết).
- **Cân bằng Bayes hoàn hảo (perfect Bayesian equilibrium).** Khái niệm cân bằng dùng cho trò chơi có thông tin không đầy đủ, trong đó niềm tin được cập nhật theo quy tắc Bayes; các cân bằng gộp, tách biệt, bán tách biệt trong chương là các loại của nó.
- **Thiết kế cơ chế và nguyên lý mặc khải (mechanism design, revelation principle).** Lý thuyết thiết kế luật chơi để người chơi tự nguyện lộ thông tin riêng; ràng buộc tương thích khuyến khích và ràng buộc tham gia là hai điều kiện trung tâm.
- **Phân biệt giá cấp một và cấp hai (first-degree and second-degree price discrimination).** Cấp một là mỗi khách một giá đúng bằng mức sẵn lòng trả (trường hợp lý tưởng 7.300 USD của PITS); cấp hai là phân biệt qua thực đơn phiên bản cho khách tự chọn (trường hợp 4.750 USD).
- **Rủi ro đạo đức (moral hazard).** Vấn đề thông tin về hành động không quan sát được (chú thích về chất lượng nỗ lực làm việc), khác với lựa chọn ngược là vấn đề thông tin về loại người; chương chỉ nhắc và để dành cho Chương 13.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong chương |
|---|---|
| Information asymmetry | Thông tin bất cân xứng: một bên biết nhiều hơn bên kia |
| Credible signal | Tín hiệu đáng tin: hành động chỉ có lợi với người thật sự thuộc loại mình muốn chứng tỏ |
| Signaling | Phát tín hiệu: người biết nhiều chủ động làm lộ thông tin có lợi |
| Screening | Sàng lọc: người biết ít đặt ra lựa chọn để người kia tự lộ thông tin |
| Signal jamming | Gây nhiễu tín hiệu: bắt chước hành vi của loại khác để che thông tin bất lợi |
| Countersignaling | Phản tín hiệu: loại tốt nhất cố ý không phát tín hiệu mà loại trung bình dùng |
| Pooling equilibrium | Cân bằng gộp: mọi loại làm như nhau, hành động không mang thông tin |
| Separating equilibrium | Cân bằng tách biệt: hành động nhận diện chính xác từng loại |
| Semi-separating equilibrium | Cân bằng bán tách biệt: một loại dùng chiến lược hỗn hợp, hành động mang một phần thông tin |
| Adverse selection | Lựa chọn ngược: giao dịch thu hút chọn lọc những loại "xấu" |
| Positive selection | Lựa chọn thuận lợi: ưu đãi chỉ hấp dẫn những loại "tốt" |
| Lemons / peaches | Xe chanh (xe cũ tồi) / xe đào (xe cũ tốt) trong ví dụ của Akerlof |
| Winner's curse | Lời nguyền người thắng: mua được rồi mới thấy hàng không đáng giá như tưởng |
| Groucho Marx effect | Hiệu ứng Groucho Marx: ai chịu nhận lời mời thì chính là người mình không muốn |
| Informational externality | Ngoại ứng thông tin: chi phí do sự tồn tại của loại kém gây ra cho người khác |
| Rat race | Cuộc đua chuột: cạnh tranh phát tín hiệu leo thang, lãng phí |
| Warranty | Bảo hành |
| Deductible / coinsurance | Mức khấu trừ / tỷ lệ đồng chi trả trong bảo hiểm |
| Benefits in kind | Trợ cấp bằng hiện vật |
| Bayes' Rule | Quy tắc Bayes: cập nhật xác suất sau khi quan sát hành động |
| Bluff | Tố láo (cược mạnh khi bài xấu) trong poker |
| Price discrimination | Phân biệt giá: bán cùng sản phẩm với giá khác nhau cho các khách khác nhau |
| Perfect price discrimination | Phân biệt giá hoàn hảo: mỗi khách trả đúng mức tối đa sẵn lòng trả |
| Versioning | Tạo phiên bản: làm nhiều bản của cùng sản phẩm để sàng lọc khách |
| Reservation price | Giá tối đa sẵn lòng trả của khách |
| Consumer surplus | Thặng dư tiêu dùng: chênh lệch giữa giá tối đa sẵn lòng trả và giá phải trả |
| Incentive compatibility constraint | Ràng buộc tương thích khuyến khích: mỗi loại phải thích phiên bản dành cho mình |
| Participation constraint | Ràng buộc tham gia: mỗi loại phải vẫn muốn mua |
| Prenuptial agreement (prenup) | Hợp đồng tiền hôn nhân |
| Coinvest | Cùng đầu tư |
| Pass/fail | Hình thức chấm đạt/không đạt thay cho điểm chữ |

## Câu nói đáng nhớ

> "Xung đột càng lớn, lời nhắn càng kém đáng tin."
*"The greater the conflict, the less the message can be trusted."*

> "Hành động (kể cả hình xăm) nói to hơn lời nói."
*"Actions (including tattoos) speak louder than words."*

> "Muốn là tín hiệu hiệu quả, một hành động phải không thể bị kẻ nói dối có lý trí bắt chước: nó phải gây lỗ khi sự thật khác với điều bạn muốn truyền đạt."
*"To be an effective signal, an action should be incapable of being mimicked by a rational liar: it must be unprofitable when the truth differs from what you want to convey."*

> "Mọi việc bạn làm đều phát tín hiệu, kể cả việc không phát tín hiệu."
*"Everything you do sends a signal, including not sending a signal."*

> "Trong một số hoàn cảnh, tín hiệu mạnh nhất bạn có thể phát là cho thấy mình không cần phát tín hiệu."
*"In some circumstances, the most powerful signal you can send is that you don't need to signal."*

> "Ở đây, bất kỳ khách hàng nào nhận lời mời của bạn đều là người bạn muốn có."
*"Here, any customer who accepts your offer is one you want to take."*

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương là gói cả một nhánh kinh tế học đoạt giải Nobel vào một tiêu chuẩn duy nhất: chênh lệch chi phí

Kinh tế học thông tin thường được dạy bằng mô hình toán, nhưng hai tác giả rút nó về một câu hỏi người đọc tự đặt được: hành động này có tốn kém với người nói dối hơn với người nói thật không? Cùng một tiêu chuẩn giải thích hình xăm của Sue, bảo hành xe, bằng MBA, thủ tục hành chính, hạng vé máy bay và các buổi họp khoả thân của phù thuỷ. Phép thử ngược (lời mời kiểm tra xe không phải tín hiệu, vì người bán xe tồi cũng không mất gì) dạy người đọc cách loại những "tín hiệu" rẻ tiền. Chương cũng không dừng ở định tính: ví dụ MBA và PITS cho thấy sàng lọc có giá cụ thể (40.000 USD mỗi năm; 2.550 USD trên 100 khách), và có lúc không đáng làm.

### Ví dụ MBA minh hoạ rõ nguyên lý, nhưng các con số chỉ là giả định để minh hoạ

Hai tác giả nói rõ các con số là giả định, nhưng người đọc dễ quên. Kết luận "người không có tài chỉ có 50% khả năng tốt nghiệp MBA" là điều kiện then chốt cho cả lập luận, và trên thực tế tỷ lệ tốt nghiệp MBA ở các trường hàng đầu rất cao với hầu hết người đã được nhận; phần sàng lọc thật có lẽ nằm ở khâu tuyển sinh hơn là khâu tốt nghiệp. Theo người tổng hợp, trong đoạn ứng viên tự phát tín hiệu, mức 75.000 USD ứng viên đòi thấp hơn mức 90.000 USD cần để bù chi phí MBA, điều chỉ hợp lý nếu coi chi phí học là đã bỏ ra rồi. (Còn câu "lợi nhuận kỳ vọng tăng thêm một triệu" thì không mâu thuẫn với số liệu: tuyển ngẫu nhiên có 25% khả năng gặp người kém, vừa chịu lỗ 1 triệu USD vừa mất phần lợi nhuận "vài triệu USD" mà một nhà quản lý giỏi lẽ ra tạo ra, nên biết chắc ứng viên giỏi có thể làm lợi nhuận kỳ vọng tăng khoảng một triệu USD.) Những chỗ này cho thấy ví dụ được dựng để minh hoạ nguyên lý, không phải để kiểm chứng.

### Quan điểm "giáo dục chủ yếu là tín hiệu" bị nhiều nhà kinh tế phản biện

Hai tác giả nghiêng về cách nhìn giáo dục là tín hiệu, thậm chí kết luận cuộc đua bằng cấp cần chính sách công can thiệp. Trường phái vốn con người cho rằng giáo dục thật sự làm tăng năng suất, và các nghiên cứu thực nghiệm thường thấy cả hai tác động cùng tồn tại, với tỷ trọng còn tranh cãi. Hai tác giả cũng không nói chính sách công cụ thể nên là gì. Người đọc nên giữ ý cốt lõi (bằng cấp có giá trị tín hiệu, và cạnh tranh tín hiệu có thể lãng phí) mà không coi đó là toàn bộ câu chuyện về giáo dục.

### Ví dụ thủ tục hành chính có lý, nhưng có mặt trái mà chương không nói tới

Lập luận rằng thời gian chờ đợi lọc được người khoẻ khỏi người bị thương là đúng về nguyên lý. Nhưng chi phí thời gian cũng đè nặng lên những người thật sự cần mà có ít nguồn lực nhất (người phải chăm con nhỏ, người ở xa, người kém hiểu biết thủ tục), nên một số người đủ điều kiện bỏ cuộc. Tương tự, trợ cấp hiện vật lọc được kẻ giả mạo nhưng có thể không đúng nhu cầu của người nhận thật. Đây là sự đánh đổi giữa loại sai lầm "trả nhầm cho người không cần" và "bỏ sót người cần", và chương chỉ nhìn một phía.

### Điều đã thay đổi từ 2008: tạo phiên bản và tín hiệu đã chuyển lên môi trường số

Theo nhận định của người tổng hợp, các ví dụ đĩa CD phần mềm, máy in IBM, đầu DVD Sharp đã lỗi thời, nhưng chiến lược tạo phiên bản phổ biến hơn bao giờ hết qua các gói thuê bao miễn phí, cơ bản, cao cấp và các tính năng phần mềm được "mở khoá" bằng phí trên cùng một thiết bị. Thị trường xe cũ có thêm các công cụ tra lịch sử xe và các nền tảng có chế độ kiểm định, bảo hành, đúng như dự đoán của hai tác giả rằng thị trường tìm cách đối phó với vấn đề xe chanh. Đánh giá, xếp hạng trực tuyến trở thành một kênh danh tiếng mới, nhưng cũng là đối tượng của gây nhiễu tín hiệu (đánh giá giả). Về chuyện điểm pass/fail, đợt chuyển sang học trực tuyến năm 2020 khiến nhiều trường đại học Mỹ cho phép hoặc bắt buộc chấm pass/fail trên diện rộng, làm thay đổi đúng cơ chế suy luận mà chương mô tả. Chế độ bảo hành dài hạn của Hyundai nay đã thành một phần thương hiệu, và danh tiếng chất lượng của hãng được cải thiện rõ, phù hợp với ý rằng đó là một tín hiệu thành công.

### Quan điểm trái chiều: tín hiệu tốn kém có thể là lãng phí xã hội, và phản tín hiệu dễ bị hiểu sai

Một tín hiệu tốn kém chỉ chuyển thông tin chứ không tạo ra giá trị; về mặt xã hội, chi phí đó là lãng phí nếu có cách rẻ hơn để truyền cùng thông tin (kiểm định độc lập, hệ thống đánh giá danh tiếng, thử việc). Vì vậy câu hỏi đúng không chỉ là "tín hiệu này có đáng tin không" mà "có cách nào rẻ hơn không"; hai tác giả có nhắc ý này trong phần các cách nhận ra tài năng nhưng không nhấn mạnh. Về phản tín hiệu, chính chú thích về ứng viên mặc quần jeans cho thấy rủi ro: người quan sát có thể đọc nhầm một sự cố thành dấu hiệu thiên tài, hoặc ngược lại. Phản tín hiệu chỉ có tác dụng khi người quan sát đã có sẵn thông tin khác để phân biệt bạn với loại kém nhất; người mới vào nghề, chưa có danh tiếng, mà bắt chước sẽ dễ bị xếp vào nhóm kém.

### Vận dụng: trước mỗi lời hứa hay lời quảng cáo, hãy hỏi điều gì sẽ xảy ra với người nói nếu họ nói sai

- **Trong doanh nghiệp.** Khi muốn khách tin chất lượng, hãy chọn cam kết tốn kém nếu bạn nói sai: bảo hành dài, hoàn tiền vô điều kiện, cho dùng thử, chia rủi ro theo kết quả. Khi thiết kế giá, hãy dùng thực đơn phiên bản thay vì một giá duy nhất, và kiểm tra hai điều kiện: khách trả cao không có lý do chuyển sang bản rẻ, và khách trả thấp vẫn muốn mua; nếu khách trả thấp chỉ là số ít, cân nhắc bỏ hẳn phân khúc đó. Khi thiết kế ưu đãi, hãy tự hỏi nó sẽ thu hút loại khách nào nhất: ưu đãi kiểu Capital One tự lọc ra khách tốt, còn một gói bảo hành hay bảo hiểm giá rẻ có thể chỉ thu hút người sắp dùng tới nó.
- **Trong đầu tư.** Coi lời của ban lãnh đạo là lời nói rẻ; coi hành động có chi phí là tín hiệu: lãnh đạo mua thêm cổ phiếu bằng tiền riêng, cổ đông lớn cam kết không bán trong thời gian dài, người sáng lập giữ lại phần vốn lớn khi bán công ty. Như chuyện của John, nếu một người có quyền cùng đầu tư mà không dùng, đó là tín hiệu xấu. Khi một tài sản được rao bán với giá "hời" mà bạn không rõ chất lượng, nhớ tới bài học xe chanh và lời nguyền người thắng: việc người bán chịu bán ở giá đó đã là thông tin.
- **Trong nghề nghiệp.** Bằng cấp và chứng chỉ là tín hiệu có giá trị chủ yếu ở đầu sự nghiệp, khi người tuyển chưa có thông tin nào khác; khi đã có thành tích, chính thành tích là tín hiệu mạnh hơn, và việc liên tục nhắc tới chức danh có thể phản tác dụng (bài học hộp thư thoại). Khi tuyển người, đừng dựa vào những thứ ai cũng làm giả được (trang phục, thư giới thiệu, lời tự giới thiệu), mà dùng thử việc, bài tập thực tế, hợp đồng có thưởng theo kết quả. Khi đàm phán lương, sẵn lòng nhận phần thưởng theo kết quả cũng là một tín hiệu về năng lực.
- **Trong đời sống.** Trong các mối quan hệ, câu đố "A Trip to the Bar" và chuyện của Sue cho thấy: lời hứa rẻ, hành động tốn kém mới đáng tin; và việc một người từ chối mọi hành động tốn kém nhỏ cũng là thông tin. Khi đọc bảng điểm, hồ sơ hay lời giới thiệu, hãy hỏi điều gì bị bỏ trống và vì sao.
- **Khi đọc tin chính sách.** Ở Việt Nam, các tranh luận về thủ tục xét duyệt trợ cấp, hỗ trợ bằng tiền mặt hay bằng hiện vật, hay yêu cầu bằng cấp, chứng chỉ trong tuyển dụng công chức đều có thể đọc bằng lăng kính của chương: thủ tục rườm rà có thể là công cụ sàng lọc nhưng cũng có thể đẩy người thật sự cần ra ngoài; yêu cầu bằng cấp ngày càng cao có thể là dấu hiệu của cuộc đua tín hiệu hơn là đòi hỏi thật của công việc. Với các cam kết của doanh nghiệp hay dự án (bảo hành, hoàn tiền, bảo lãnh), câu hỏi then chốt là cam kết đó có thi hành được không, và ai chịu thiệt nếu cam kết bị phá vỡ.
