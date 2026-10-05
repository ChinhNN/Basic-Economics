# Artificial Intelligence's Promise and Peril — Hứa hẹn và hiểm hoạ của trí tuệ nhân tạo

**Nguồn:** IMF *Finance & Development*, Back to Basics, tháng 12/2023, tr. 8–9.
**Tác giả:** Hervé Tourpe, Trưởng Đơn vị Tư vấn Số của IMF.
**Ý chính:** AI tạo sinh (GenAI) là bước tiến lớn nhất của học máy, hứa hẹn làn sóng sáng tạo và năng suất, nhưng đặt ra câu hỏi hệ trọng về thao túng, việc làm và rủi ro tồn vong.

## Sơ đồ

### Con đường đến GenAI

```text
              TURING 1950: "trò chơi bắt chước"
                              │
                              ▼
       1960s: ELIZA — chatbot theo quy tắc, tiền thân
                              │
                              ▼
       1980s: MẠNG NEURON NHÂN TẠO — hiểu ngôn ngữ, nhận ảnh
            (bị kìm bởi thiếu dữ liệu và sức tính toán,
                    nhưng cả hai tăng gấp đôi mỗi năm)
                              │
                              ▼
       2000s: DEEP LEARNING — Google Translate, Alexa, Siri,
                           xe tự lái
       (máy hỗ trợ và dự đoán, nhưng chưa hiểu hội thoại,
                 tạo nội dung giống người còn kém)
                              │
            ┌─────────────────┴─────────────────┐
            │                                   │
            ▼                                   ▼
     2014: GANs                         2017: ATTENTION
  generator tạo giả ×               "Attention Is All You Need"
  discriminator phân biệt           máy "nắm được" bản chất input
  → hai mạng mài giũa nhau
            └─────────────────┬─────────────────┘
                              │
                  + dữ liệu và sức tính toán tăng
                              │
                              ▼
              ChatGPT (OpenAI, 11/2022) → big tech nối gót
```

### Hứa hẹn trong kinh tế và tài chính

```text
        AI TRUYỀN THỐNG                     GenAI
   (phân tích nâng cao, học máy,    (đào sâu, diễn giải dữ liệu
    deep learning dự đoán)           phức tạp một cách sáng tạo)
   tính toán, dự báo xu hướng,   → không chỉ dự báo mà còn kịch bản
   cá nhân hoá sản phẩm             thay thế, biểu đồ, mã lệnh
                                            │
        ┌───────────────┬───────────────────┼───────────────┐
        │               │                   │               │
        ▼               ▼                   ▼               ▼
   Chính phủ       Ngân hàng TW        Quỹ đầu tư        Bảo hiểm
 dịch vụ công    sàng dữ liệu NH,    phát hiện biến    hợp đồng cá
 dân, thiếu      dự báo, giám sát    động giá, tâm lý  nhân hoá
 nhân lực        rủi ro, gian lận    thị trường
```

### Hiểm hoạ

```text
                    HOÀI NGHI: "vẹt ngẫu nhiên"
       ảo giác (hallucination), không hiểu nghĩa, giới hạn
      ngày huấn luyện → nhưng tốc độ đổi mới xoá dần lập luận
                              │
                              ▼
                    LO NGẠI CŨ TRỞ NÊN CẤP BÁCH
            thiên kiến trong dữ liệu · thiếu minh bạch
                              │
            ┌─────────────────┼─────────────────┐
            │                 │                 │
            ▼                 ▼                 ▼
     VŨ KHÍ HOÁ          MẤT VIỆC          TỒN VONG
  kể chuyện hợp       tự động hoá       thư 2023: "giảm rủi
  niềm tin sẵn có     tác vụ người      ro tuyệt chủng từ AI"
  → echo chamber      → cần chiến       ngang đại dịch, hạt nhân
  deepfake Zelenskyy  lược việc làm,    (Turing đã cảnh báo:
  3/2022 → thao túng  đào tạo lại       máy sẽ kiểm soát
  chính trị, thị                        cuộc sống)
  trường, dư luận
  (kể cả vô ý do
  ảo giác)
            └─────────────────┬─────────────────┘
                              │
                              ▼
              KHÔNG THỂ "PHÁT MINH NGƯỢC" → cần giám sát,
        khung pháp lý mới, đổi mới đạo đức, minh bạch, kiểm soát
```

## Ba câu hỏi bài viết trả lời

1. GenAI là gì và ra đời qua những cột mốc nào?
2. GenAI thay đổi kinh tế và tài chính ra sao?
3. Những rủi ro mới nào xuất hiện và cần ứng phó thế nào?

## Khái niệm cần biết

**Học máy (machine learning).** Cách làm cho máy tính tự rút ra quy luật từ dữ liệu thay vì được lập trình từng quy tắc một. Ví dụ minh hoạ: thay vì viết sẵn quy tắc "email có chữ 'trúng thưởng' là thư rác", ta cho máy xem 100.000 email đã được đánh dấu thư rác hay không, và máy tự học cách phân biệt. Bài coi AI tạo sinh là bước tiến ấn tượng nhất của học máy.

**Mạng neuron nhân tạo và học sâu (artificial neural networks, deep learning).** Mạng neuron nhân tạo là mô hình toán học gồm nhiều "nút" nối với nhau, lấy cảm hứng từ cách các tế bào thần kinh trong não truyền tín hiệu. Học sâu là mạng neuron có rất nhiều lớp chồng lên nhau, nên học được các quy luật phức tạp. Ví dụ trong bài: Google Translate, trợ lý số Alexa, Siri và xe tự lái. Đây là bậc thang ngay trước AI tạo sinh.

**AI tạo sinh (generative AI, GenAI).** Loại AI không chỉ phân loại hay dự đoán mà còn **tạo ra nội dung mới**, như văn bản, hình ảnh, đoạn mã, trông giống do con người làm. Ví dụ: ChatGPT, do OpenAI ra mắt tháng 11/2022, viết được một bức thư hay một đoạn chương trình theo yêu cầu. Đây là đối tượng của cả bài.

**Mạng đối nghịch tạo sinh (GANs).** Hai mạng neuron cạnh tranh với nhau: mạng "tạo" (*generator*) làm ra dữ liệu giả, mạng "phân biệt" (*discriminator*) cố nhận ra đâu là thật, đâu là giả. Mỗi bên tiến bộ nhờ bên kia. Ví dụ minh hoạ: giống một người làm tranh giả và một chuyên gia giám định cùng luyện tập, cho tới khi tranh giả khó phân biệt với thật. Phương pháp này ra đời năm 2014.

**Cơ chế chú ý (attention mechanism).** Kỹ thuật giúp máy tập trung vào những phần liên quan nhất của đầu vào khi xử lý. Ví dụ minh hoạ: trong câu "Con mèo không ăn vì nó no", để hiểu chữ "nó", máy cần "chú ý" vào chữ "con mèo". Kỹ thuật này được công bố năm 2017 trong bài báo *Attention Is All You Need* và là nền tảng của các mô hình ngôn ngữ lớn như ChatGPT.

**Ảo giác (hallucination).** Khi AI tạo ra thông tin nghe rất thuyết phục nhưng sai hoặc vô nghĩa. Ví dụ minh hoạ: hỏi AI về một bài nghiên cứu, nó có thể đưa ra tên tác giả, năm xuất bản và tên tạp chí đầy đủ cho một bài báo không hề tồn tại. Khái niệm này quan trọng vì bài nêu rằng AI có thể lan tin sai cả khi không ai cố ý.

**Buồng vang (echo chamber).** Môi trường thông tin trong đó người ta chỉ nghe những gì củng cố niềm tin sẵn có của mình. Ví dụ minh hoạ: một người tin một tin đồn về thị trường được cung cấp liên tục các bài viết ủng hộ tin đồn đó, nên càng tin chắc hơn. Bài lo rằng AI tạo sinh, vì có thể viết nội dung hợp ý từng người, sẽ làm buồng vang mạnh hơn.

**Giả mạo sâu (deepfake).** Video, ảnh hoặc giọng nói do AI tổng hợp để giả làm người thật nói hay làm điều họ không hề nói, làm. Ví dụ trong bài: tháng 3/2022, một video giả mạo Tổng thống Ukraine Zelenskyy kêu gọi đầu hàng Nga. Đây là bằng chứng cụ thể cho rủi ro AI bị dùng làm vũ khí.

## Nội dung chi tiết

### 1. GenAI là gì

Năm 1950, nhà toán học Alan Turing hình dung một ngày máy móc sẽ đạt tới mức bắt chước được trí tuệ con người. Ông đề xuất một phép thử gọi là "trò chơi bắt chước": nếu người đối thoại không phân biệt được mình đang nói chuyện với máy hay với người, thì máy đã bắt chước thành công. Theo tác giả, với ChatGPT và các công cụ AI tạo sinh khác, trò chơi mà Turing dự đoán đã thành hiện thực.

AI tạo sinh (GenAI) là bước tiến ấn tượng nhất của công nghệ học máy tính tới nay. Nó là một bước nhảy trong khả năng của máy trong việc hiểu và tương tác với các mẫu dữ liệu phức tạp. Bước nhảy này có thể mở ra một làn sóng sáng tạo và năng suất mới, nhưng cũng đặt ra những câu hỏi hệ trọng cho nhân loại.

### 2. Các cột mốc

Bài kể lại con đường đi tới GenAI qua sáu chặng:

| Thời điểm | Cột mốc | Ý nghĩa |
|---|---|---|
| Thập niên 1960 | ELIZA | Chương trình tạo phản hồi giống người theo các quy tắc cố định và đơn giản; tiền thân của chatbot |
| Khoảng hai thập kỷ sau (thập niên 1980) | Mạng neuron nhân tạo | Lấy cảm hứng từ não người; cho máy hiểu sắc thái ngôn ngữ, nhận diện hình ảnh |
| Thập niên 2000 | Học sâu (deep learning) | Google Translate, Alexa, Siri, xe tự lái |
| 2014 | Mạng đối nghịch tạo sinh (GANs) | Hai mạng neuron cạnh tranh, mài giũa nhau |
| 2017 | Cơ chế chú ý ("Attention Is All You Need") | Máy dường như "nắm được" bản chất đầu vào |
| Tháng 11/2022 | ChatGPT (OpenAI) | GenAI đến tay công chúng; các hãng công nghệ lớn nhanh chóng nối gót |

Mỗi chặng giải quyết một giới hạn của chặng trước.

**ELIZA** chỉ làm theo quy tắc lập sẵn, nên không thật sự "hiểu" gì.

**Mạng neuron nhân tạo** cho máy học từ dữ liệu, nhưng tiến bộ bị kìm hãm vì thiếu dữ liệu để huấn luyện và thiếu sức mạnh tính toán. Điều đáng chú ý là cả hai nguồn lực này tăng gấp đôi mỗi năm, nên giới hạn đó dần được gỡ bỏ.

**Học sâu** giúp máy bắt đầu hiểu và tương tác với thế giới: dịch văn bản, trả lời câu hỏi bằng giọng nói, lái xe. Máy đã giỏi hỗ trợ con người và đưa ra dự đoán. Nhưng còn thiếu một mảnh ghép: máy chưa thật sự hiểu hội thoại, và khả năng tạo ra nội dung giống người còn kém.

**GANs** (năm 2014) lấp một phần chỗ trống đó. Hai mạng neuron đấu với nhau liên tục: mạng "tạo" (*generator*) làm ra dữ liệu, văn bản, hình ảnh giả; mạng "phân biệt" (*discriminator*) cố nhận ra đâu là thật, đâu là giả. Mỗi vòng, mạng tạo giỏi làm giả hơn và mạng phân biệt giỏi phát hiện hơn. Cách này cách mạng hoá khả năng AI hiểu và tái tạo các mẫu phức tạp.

**Cơ chế chú ý** (năm 2017, từ bài báo *Attention Is All You Need*) dạy AI tập trung vào những phần liên quan của đầu vào. Nhờ đó máy dường như bắt đầu "nắm được" bản chất của điều được hỏi, và tạo ra nội dung giống người đến kỳ lạ, ít nhất là trong phòng thí nghiệm.

GANs, cơ chế chú ý, cộng với lượng dữ liệu và sức mạnh tính toán ngày càng lớn, đã tạo nền móng cho ChatGPT, được OpenAI ra mắt tháng 11/2022.

### 3. Kinh tế và tài chính

AI không phải chuyện mới trong kinh tế và tài chính. Từ lâu, **AI truyền thống**, gồm phân tích nâng cao, học máy và học sâu dùng để dự đoán, đã được dùng để tính toán, đo xu hướng thị trường và cá nhân hoá sản phẩm tài chính.

Điểm khác của **GenAI** là nó đào sâu hơn và diễn giải dữ liệu phức tạp theo cách sáng tạo hơn. Khi phân tích quan hệ giữa các chỉ số kinh tế hay các biến tài chính, nó không chỉ đưa ra một dự báo, mà còn đề xuất các kịch bản thay thế, vẽ biểu đồ và viết sẵn đoạn mã để người dùng chạy tiếp.

Bài nêu bốn nhóm người dùng:

| Nhóm | Cách dùng GenAI |
|---|---|
| Chính phủ | Cải thiện dịch vụ cho người dân và bù đắp tình trạng thiếu nhân lực |
| Ngân hàng trung ương | Sàng lọc khối lượng lớn dữ liệu ngân hàng để tinh chỉnh dự báo, giám sát rủi ro, kể cả phát hiện gian lận |
| Quỹ đầu tư | Phát hiện những biến động tinh vi của giá cổ phiếu và tâm lý thị trường, đề xuất các lựa chọn đầu tư sáng tạo hơn |
| Công ty bảo hiểm | Dùng mô hình tạo sinh để soạn hợp đồng cá nhân hoá, sát với nhu cầu từng khách hàng |

**Quan điểm hoài nghi.** Không phải ai cũng tin vào GenAI. Những người hoài nghi gọi nó là "vẹt ngẫu nhiên": nó chỉ ghép lại các mẫu chữ đã thấy mà không hiểu nghĩa. Nó có thể tạo ra "sự thật" sai và vô nghĩa, hiện tượng gọi là **ảo giác**. Kiến thức của ChatGPT cũng chỉ dừng ở ngày nó được huấn luyện xong. Nhưng tác giả đặt câu hỏi: với tốc độ đổi mới chóng mặt hiện nay, những lập luận này còn đúng được bao lâu?

### 4. Lo ngại

Sự hào hứng ban đầu đã nhường chỗ cho những lo ngại thật sự. Một số thách thức cũ của AI nay trở nên cấp bách hơn: AI có thể **khuếch đại thiên kiến** có sẵn trong dữ liệu huấn luyện (ví dụ dữ liệu cho vay trong quá khứ vốn bất lợi cho một nhóm người thì AI học theo), và **thiếu minh bạch** trong cách nó ra quyết định (khó giải thích vì sao AI từ chối một hồ sơ). Bên cạnh đó, nhiều lo ngại mới cũng xuất hiện, được trình bày ở mục tiếp theo.

### 5. AI bị vũ khí hoá

**Thao túng thông tin.** Rủi ro đặc biệt đáng báo động là GenAI có thể kể những câu chuyện hợp với niềm tin và quan điểm sẵn có của từng người, từ đó củng cố các buồng vang và các "ốc đảo" tư tưởng tách biệt nhau.

Kẻ xấu không chỉ khai thác nó bằng chữ viết. Tháng 3/2022, một video do AI tạo ra giả mạo Tổng thống Ukraine Zelenskyy tuyên bố đầu hàng Nga. Sự việc cho thấy GenAI có thể bị biến thành vũ khí để thao túng chính trị, thị trường và dư luận.

Dù là câu chuyện bịa, ảnh chỉnh sửa hay video tổng hợp, sản phẩm của GenAI có thể thuyết phục tới mức tạo ra cảm giác thật giả lẫn lộn. Chúng có thể lan truyền tin sai, gây hoảng loạn, thậm chí làm bất ổn hệ thống kinh tế, tài chính, với hiệu quả và cường độ chưa từng có. Và điều này không phải lúc nào cũng do cố ý: máy có thể vô tình lan tin sai do ảo giác.

**Mất việc làm.** GenAI có thể tự động hoá những công việc trước đây do con người làm, khiến nhiều việc làm biến mất. Vì vậy cần có chiến lược việc làm và chương trình đào tạo lại người lao động.

**Rủi ro tồn vong.** Đầu năm 2023, các chuyên gia AI hàng đầu, trong đó có cả những người tạo ra ChatGPT, ký một bức thư cảnh báo rằng "giảm rủi ro tuyệt chủng do AI nên là một ưu tiên toàn cầu, ngang với đại dịch và chiến tranh hạt nhân". Họ nhắc lại đúng nỗi lo mà Turing đã nêu từ hàng chục năm trước: "có nguy cơ máy móc cuối cùng sẽ kiểm soát cuộc sống của chúng ta".

| Loại rủi ro | Biểu hiện | Ứng phó gợi ý trong bài |
|---|---|---|
| Vũ khí hoá | Buồng vang, giả mạo sâu, thao túng chính trị và thị trường, tin sai do ảo giác | Giám sát, minh bạch |
| Mất việc | Tự động hoá tác vụ của con người | Chiến lược việc làm, đào tạo lại |
| Tồn vong | Máy vượt khỏi tầm kiểm soát | Ưu tiên toàn cầu, kiểm soát được |

### 6. Ngã ba công nghệ và đạo đức

GenAI, với những hứa hẹn rộng lớn và những câu hỏi sâu sắc về sự tồn vong, không thể bị "phát minh ngược", tức không thể quay về thời chưa có nó.

Khi tận dụng sức mạnh chuyển đổi của GenAI, tác giả khuyên nên nhớ lời cảnh báo của Turing. GenAI là một bước chuyển lớn, đòi hỏi:

- giám sát cảnh giác;
- khung pháp lý mới;
- cam kết không lay chuyển với đổi mới có đạo đức;
- minh bạch và khả năng kiểm soát;
- sự hài hoà với các giá trị của con người.

## Thuật ngữ

| Thuật ngữ | Nghĩa trong bài |
|---|---|
| Generative AI (GenAI) | AI tạo sinh: tạo nội dung mới (văn bản, ảnh, mã) giống người |
| Imitation game | "Trò chơi bắt chước" Turing đề xuất năm 1950, tiền thân của ý tưởng máy giả người |
| ELIZA | Chatbot theo quy tắc thập niên 1960 |
| Artificial neural networks | Mạng neuron nhân tạo, lấy cảm hứng từ não người |
| Deep learning | Học sâu, làn sóng AI thứ ba những năm 2000 |
| GANs | Mạng đối nghịch tạo sinh (2014): generator tạo giả, discriminator phân biệt |
| Attention mechanism | Cơ chế chú ý (2017), nền tảng của các mô hình ngôn ngữ lớn |
| Hallucination | Ảo giác: AI tạo ra sự thật sai, vô nghĩa |
| Stochastic parrot | "Vẹt ngẫu nhiên": phê phán AI lặp lại mẫu mà không hiểu nghĩa |
| Echo chamber | Buồng vang: nội dung củng cố niềm tin sẵn có |
| Deepfake | Video, ảnh tổng hợp giả mạo người thật (ví dụ video Zelenskyy 3/2022) |

## Câu nói đáng nhớ

> "GenAI creations can be so convincing that they create a false sense of reality. This has the potential to spread misinformation, incite panic, and even destabilize economic or financial systems."

> "GenAI, with its vast promise and profound, existential questions, cannot be uninvented."

## Đánh giá và phát hiện đáng chú ý

### Bài kể lịch sử công nghệ như một chuỗi ý tưởng thông minh, và vì thế bỏ lỡ chỗ nằm của kinh tế học

Dòng thời gian mà bài dựng — từ trò chơi bắt chước của Turing, qua mạng neuron, học sâu, đến cơ chế chú ý — kể câu chuyện về những đột phá khái niệm nối tiếp nhau. Cách kể này rất phổ biến, và nó dẫn người đọc tới một kết luận ngầm: bước tiến lớn tiếp theo cũng sẽ đến từ một ý tưởng mới.

Nhưng yếu tố quyết định nhất trong giai đoạn 2019–2025 không phải ý tưởng mới mà là **quy mô**. Kiến trúc nền tảng được công bố năm 2017 hầu như không đổi; cái đã đổi là lượng dữ liệu, số lượng tham số và đặc biệt là lượng vốn đầu tư vào năng lực tính toán. Bài có nhắc tới việc dữ liệu và sức tính toán "tăng gấp đôi mỗi năm" nhưng xử lý điều đó như một điều kiện thuận lợi ở nền, chứ không phải là nguyên nhân chính.

Sự khác biệt trong cách kể này có hệ quả kinh tế rất lớn, và đó là lý do đáng nói ở một tạp chí về kinh tế và tài chính. Nếu tiến bộ đến từ ý tưởng, ngành sẽ phân tán: ai cũng có thể có ý tưởng hay, rào cản gia nhập thấp, lợi ích lan tỏa nhanh. Nếu tiến bộ đến từ quy mô vốn, ngành sẽ **tập trung cực độ**: chỉ một số rất ít tổ chức đủ sức chi hàng chục tỷ đô la cho một thế hệ mô hình, và cấu trúc thị trường trở thành độc quyền nhóm ở tầng mô hình nền, cộng với một nút thắt cổ chai duy nhất ở tầng chip.

Điều này đã diễn ra đúng như vậy trong ba năm qua, và nó kéo theo cả một loạt câu hỏi kinh tế mà bài không chạm tới: ai chiếm được phần giá trị tạo ra, một khoản chi vốn ở quy mô đó có tạo ra rủi ro tài chính hệ thống hay không, và điện năng cho trung tâm dữ liệu — nay đã trở thành một biến số vĩ mô ở nhiều nước — sẽ được cung cấp thế nào trong khi cùng lúc phải cắt phát thải. Câu hỏi cuối nối thẳng với các tài liệu về giảm nhẹ khí hậu và về định giá carbon trong cùng tập này, và nó là một mâu thuẫn chính sách rất thực mà cả hai phía đều chưa giải quyết.

### Phần kinh tế và tài chính là phần yếu nhất, và nó bỏ lỡ câu hỏi quan trọng nhất

Phần này chỉ gồm bốn gạch đầu dòng: chính phủ cải thiện dịch vụ công, ngân hàng trung ương sàng dữ liệu, quỹ đầu tư phát hiện biến động giá, bảo hiểm cá nhân hóa hợp đồng. Tất cả đều là **danh sách ứng dụng tiềm năng**, không phải phân tích kinh tế.

Câu hỏi kinh tế trung tâm của trí tuệ nhân tạo không phải "ai sẽ dùng nó" mà là: **đây có phải một công nghệ đa dụng theo nghĩa của máy hơi nước và điện khí hóa không, và nếu có thì năng suất tổng hợp sẽ tăng bao nhiêu, sau bao lâu, và phần thu nhập tăng thêm sẽ chia cho ai?**

Đây không phải câu hỏi quá chuyên sâu cho một chuyên mục nhập môn. Chính tập Back to Basics này có một bài về năng suất tổng hợp các nhân tố, và khung phân tích ở đó là công cụ đúng để đặt câu hỏi này. Lịch sử cũng có sẵn một bài học cảnh báo: nghịch lý được phát biểu vào cuối thập niên 1980 rằng có thể thấy kỷ nguyên máy tính ở khắp nơi trừ trong số liệu năng suất, và phải mất khoảng mười lăm năm hiệu ứng mới hiện ra trong thống kê, vì phần lớn công việc thật sự nằm ở đầu tư bổ trợ — tổ chức lại quy trình, đào tạo lại người, viết lại phần mềm nội bộ.

Ba năm sau khi bài này ra đời, tình hình khớp gần như hoàn hảo với giai đoạn đầu của đường cong đó: chi đầu tư khổng lồ, ứng dụng lan rộng ở cấp cá nhân, nhưng chưa có dấu hiệu rõ ràng và không thể chối cãi trong số liệu năng suất tổng hợp ở cấp quốc gia. Điều quan trọng là **hai cách giải thích trái ngược nhau đều phù hợp với dữ liệu hiện có**: hoặc đây là phần lõm của đường cong chữ J trước khi hiệu ứng bùng lên, hoặc đây là một chu kỳ đầu tư vượt mức sẽ kết thúc bằng điều chỉnh. Ai nói chắc chắn theo một trong hai hướng đều đang nói vượt quá bằng chứng.

### Rủi ro được bài xếp hạng ngược với mức độ cụ thể của bằng chứng

Bài dành phần dài nhất và giọng cấp bách nhất cho hai rủi ro ở hai đầu: vũ khí hóa thông tin và rủi ro tồn vong. Trong khi đó rủi ro việc làm — thứ chắc chắn xảy ra và đo lường được — chỉ được hai câu.

Cách phân bổ này phản ánh không khí tranh luận cuối năm 2023, khi bức thư về rủi ro tuyệt chủng còn rất mới. Nhưng nhìn lại, việc đóng khung vấn đề theo trục tồn vong đã gây ra một tác hại phụ: nó **chiếm hết không gian của phần giữa**, tức là những tác hại cụ thể, đã xảy ra và có thể quản lý được bằng công cụ chính sách thông thường.

Đáng chú ý là chính bài đã nêu đúng một rủi ro ở phần giữa với lập luận rất sắc: nội dung tổng hợp thuyết phục tới mức có thể "lan tin sai, gây hoảng loạn, thậm chí gây bất ổn hệ thống kinh tế, tài chính". Rủi ro này cụ thể hơn nhiều so với rủi ro tuyệt chủng, có cơ chế truyền dẫn rõ ràng, và có thể phòng ngừa bằng những biện pháp rất đời thường. Kịch bản đáng sợ nhất không phải một siêu trí tuệ mà một video giả về một ngân hàng mất thanh khoản, lan trong vài giờ qua mạng xã hội, kích hoạt rút tiền hàng loạt — và chuyện rút tiền hàng loạt với tốc độ mạng xã hội đã được chứng minh là có thật trong các vụ đổ vỡ ngân hàng khu vực ở Hoa Kỳ năm 2023, ngay trước khi bài này được viết, mà chưa cần đến nội dung giả mạo nào.

Nói cách khác, mắt xích nguy hiểm nhất không phải công nghệ tạo nội dung mà là **tốc độ mà thông tin biến thành hành vi tài chính đồng loạt**. Đây là một vấn đề thuộc về thiết kế cơ chế — ngưỡng dừng giao dịch, quy trình xác minh, kênh truyền thông có thẩm quyền của ngân hàng trung ương — chứ không thuộc về quản lý mô hình, và nó có thể triển khai được ngay. Bài có đủ chất liệu để đi tới đó nhưng lại rẽ sang hướng tồn vong.

### Khuyến nghị "minh bạch và kiểm soát được" mâu thuẫn với chính cấu trúc ngành mà bài mô tả

Đoạn kết kêu gọi giám sát cảnh giác, khung pháp lý mới, cam kết với đổi mới có đạo đức, minh bạch và kiểm soát được. Không ai phản đối những từ này, và đó là vấn đề.

Có ít nhất ba mâu thuẫn cụ thể khiến chúng khó thực hiện, và cả ba đều có thể nhận ra từ nội dung của chính bài.

**Thứ nhất, minh bạch về dữ liệu huấn luyện đụng thẳng vào rủi ro pháp lý.** Các mô hình được huấn luyện trên lượng lớn nội dung có bản quyền. Công bố đầy đủ nguồn dữ liệu đồng nghĩa với việc tự cung cấp bằng chứng cho hàng loạt vụ kiện. Không doanh nghiệp nào tự nguyện làm điều đó, và đây là lý do thực chất khiến các cam kết minh bạch dừng ở mức mô tả chung.

**Thứ hai, minh bạch về kỹ thuật đụng vào cạnh tranh và an ninh quốc gia.** Khi năng lực mô hình được coi là tài sản chiến lược quốc gia, chính phủ vừa muốn quản lý vừa muốn doanh nghiệp trong nước dẫn đầu. Hai mong muốn này kéo ngược nhau, và trong ba năm qua, mong muốn thứ hai gần như luôn thắng.

**Thứ ba, "kiểm soát được" là một yêu cầu kỹ thuật chưa có lời giải.** Không phải vì thiếu ý chí mà vì bản chất của các mô hình này là hành vi nổi lên từ dữ liệu chứ không phải từ quy tắc được viết ra. Chính hiện tượng ảo giác mà bài nêu là minh chứng: đó không phải một lỗi có thể vá mà là hệ quả của cách mô hình hoạt động.

Kết luận thực tiễn: khung pháp lý khả thi trong ngắn hạn sẽ không nhắm vào bản thân mô hình mà nhắm vào **ứng dụng trong các lĩnh vực rủi ro cao** — tín dụng, tuyển dụng, y tế, tư pháp, bầu cử — với nghĩa vụ đặt lên người triển khai chứ không phải người tạo mô hình. Đó cũng là cấu trúc mà khung pháp lý đầu tiên của châu Âu đã chọn, và là cấu trúc mà các nước đi sau nhiều khả năng sẽ sao chép vì nó khả thi, chứ không phải vì nó tối ưu.

### Với Việt Nam: mức độ phơi nhiễm thấp là một tin xấu được ngụy trang thành tin tốt

Bài viết ở tầm toàn cầu và không phân biệt theo trình độ phát triển. Nhưng đó chính là chỗ có phát hiện quan trọng nhất cho người đọc Việt Nam, và nó nằm trong các nghiên cứu mà chính IMF công bố ngay sau bài này.

Mức độ phơi nhiễm của việc làm với trí tuệ nhân tạo tạo sinh ở các nền kinh tế tiên tiến vào khoảng sáu phần mười tổng việc làm, trong khi ở các nước thu nhập thấp chỉ khoảng một phần tư. Lý do là công nghệ này tác động mạnh nhất vào **công việc nhận thức ở văn phòng** — soạn thảo, phân tích, lập trình, dịch thuật, dịch vụ khách hàng — chứ không phải vào lao động chân tay hay nông nghiệp. Đây là điểm đảo ngược so với mọi làn sóng tự động hóa trước đó, vốn nhắm vào lao động phổ thông ở nhà máy.

Với cơ cấu việc làm của Việt Nam — tỷ trọng lớn trong nông nghiệp, gia công chế biến và dịch vụ phi chính thức — mức phơi nhiễm thuộc nhóm thấp. Điều này thường được đọc như một tin tốt: ít xáo trộn hơn, ít người mất việc hơn.

Nhưng đọc kỹ thì đây là tin xấu. Phơi nhiễm thấp có nghĩa là **cơ hội tăng năng suất nhờ công nghệ này cũng thấp**. Nếu các nền kinh tế tiên tiến nâng được năng suất khu vực dịch vụ tri thức trong khi Việt Nam không có nhiều dư địa để nâng, thì khoảng cách thu nhập giữa hai bên sẽ giãn ra chứ không thu hẹp — ngược với xu hướng hội tụ mà toàn cầu hóa sản xuất đã tạo ra suốt ba thập niên.

Có một rủi ro thứ hai còn cụ thể hơn. Mô hình tăng trưởng của Việt Nam dựa vào lợi thế chi phí lao động trong gia công. Nếu trí tuệ nhân tạo kết hợp với tự động hóa làm giảm đáng kể tỷ trọng chi phí lao động trong tổng chi phí sản xuất, thì lý do để đặt nhà máy ở nơi lao động rẻ yếu đi, và các yếu tố khác — gần thị trường tiêu thụ, ổn định chính trị, chất lượng điện và hạ tầng số — trở nên quyết định hơn. Đây là kịch bản mà chính sách có thể chuẩn bị được, nhưng chỉ nếu nhận ra sớm.

Hàm ý cuối cùng, và là điều hiếm khi được nói: với một nước ở vị trí của Việt Nam, chính sách đúng không phải là cố xây mô hình nền — cuộc đua đó cần quy mô vốn ngoài tầm — mà là **tối đa hóa tốc độ hấp thụ**: hạ tầng điện toán và điện năng đủ tin cậy, dữ liệu số hóa trong hành chính công và y tế đủ sạch để dùng được, và đào tạo diện rộng ở tầng ứng dụng thay vì tầng nghiên cứu. Phần lớn lợi ích của điện khí hóa không rơi vào tay nước phát minh ra máy phát điện, mà vào tay những nước triển khai nó nhanh nhất vào sản xuất.
