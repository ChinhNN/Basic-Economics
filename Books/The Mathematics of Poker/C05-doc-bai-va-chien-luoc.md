# Chương 5 — "Bói bài Tarot một cách khoa học": đọc bài và đọc chiến lược (Scientific Tarot: Reading Hands and Strategies)

**Nguồn:** Bill Chen và Jerrod Ankenman, *The Mathematics of Poker*, ConJelCo 2006 (ấn bản đầu tiên), Chương 5 "Scientific Tarot: Reading Hands and Strategies", trang 62–72.
**Tác giả:** Bill Chen (tiến sĩ toán, Đại học California tại Berkeley, 1999; làm ở Susquehanna International Group; vô địch hai giải World Series of Poker 2006) và Jerrod Ankenman (cử nhân quản trị kinh doanh, Pepperdine 2004; người chơi poker chuyên nghiệp; á quân một giải WSOP 2006).
**Vị trí trong lập luận của cả cuốn sách:** Chương 3 ([C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md)) đã giới thiệu định lý Bayes và khẳng định suy luận Bayes là "trái tim của việc đọc bài và chơi khai thác". Chương 4 ([C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md)) mở Phần II, định nghĩa chơi khai thác là tối đa hoá kỳ vọng trước chiến lược của đối thủ, và mô tả nó là quy trình hai bước: (1) thu thập thông tin về bài và chiến lược đối thủ, (2) chọn hành động. Chương 5 là bước (1): đọc bài là suy luận Bayes về **phân phối tay bài** của đối thủ; đọc chiến lược là ước lượng đối thủ chơi từng tay trong phân phối đó ra sao; đọc tell là thêm một lớp Bayes. Chương 6 ([C06-poker-truc-tuyen.md](C06-poker-truc-tuyen.md)) bàn thông tin có được khi chơi online. Chương 7–9 ([C07-choi-chinh-xac-bai-lat-ngua.md](C07-choi-chinh-xac-bai-lat-ngua.md), [C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md), [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md)) là bước (2): chơi chính xác trước bài lật ngửa, trước một phân phối, rồi thích nghi; Chương 8 quay lại đúng ván stud của Ví dụ 5.1 để quyết định bet hay check ở sixth street.
**Ý chính:** **"Đọc" đối thủ không phải là phép màu đoán đúng một lá bài, mà chủ yếu là suy luận Bayes dựa trên cách cược (cộng một điều chỉnh, thường nhỏ, cho tell): ta không bao giờ gán cho đối thủ một tay bài duy nhất mà duy trì một phân phối xác suất trên mọi tay họ có thể cầm, rồi thu hẹp nó theo từng lá bài lộ ra và từng hành động; còn việc đọc chiến lược của đối thủ khó hơn nhiều so với người chơi thường nghĩ, vì dữ liệu quan sát được rất ít.** Phần mở đầu kể ván satellite no-limit: tác giả call all-in 2.100 chip với A♥8♥ không phải vì "đoán" đối thủ cầm bài gì, mà vì trước phân phối "mọi lá A, mọi đôi, vài lá K tốt, T9 cùng chất…" A♥8♥ có gần 50% equity (người tổng hợp mô phỏng: 48–50%, trong khi chỉ cần khoảng 41%), dù đối thủ thực ra cầm AK khác chất. Mục "Advanced Hand Reading" nêu phương pháp: bắt đầu từ phân phối đều trên mọi cặp lá kín (đã trừ các lá ta thấy), cập nhật theo lá lộ ra và theo xác suất đối thủ hành động như vậy với từng tay, giữ một xác suất nhỏ "mất trí" cho hành động bất thường, và thêm tell như một lớp Bayes nữa. Ví dụ 5.1 (stud tám-hoặc-tốt-hơn, 30–60 USD) dựng phân phối của đối thủ qua từng vòng, từ danh sách bài raise ở third street tới 16 tổ hợp lá kín ở sixth street (AA 1, Q♣Qx 3, QxQy 3, J♣Jx 2, JxJy 1, hai lá chuồn nhỏ 6). Mục "Reading Strategies" liệt kê bốn nguồn thông tin (bằng chứng trực tiếp ở showdown, bài đối thủ tự lật, tần suất hành động, phân loại người chơi) và chỉ ra giới hạn: sau 1.000 tay chỉ khoảng 100 tay được lật; 121 tay ở vị trí under the gun với tỷ lệ raise 10% cho khoảng tin cậy 95% từ 4% tới 16%; người chơi đổi chiến lược; não người thấy mẫu hình ở cả dữ liệu ngẫu nhiên; thấy người chơi chặt lật AA không chứng minh họ chặt. Mục "Reading Tells" coi đọc tell như chẩn đoán bệnh: giá trị của tell phụ thuộc vào xác suất dương tính giả. Cuối chương mô tả ba kiểu người chơi yếu dễ nhận ra và cách khai thác: maniac, rock, calling station.

> **Lưu ý:**
> - **Ví dụ 5.1, lá A trong tay bị đổi chất:** ở third street và fifth street, lá kín của ta là (5♣ A♥); ở bảng tóm tắt sixth street sách ghi (5♣ A♠) trong khi lá ngửa mới cũng là A♠, nên A♠ xuất hiện hai lần. Đúng là (5♣ A♥) 4♥ 8♠ J♥ A♠. Phép đếm "AA của đối thủ chỉ còn một tổ hợp A♣A♦" khớp với cách đọc này.
> - **Ví dụ 5.1, ký hiệu "-1", "-3"… trong bảng tổ hợp:** dấu gạch là dấu phân cách, không phải dấu âm; các số là số tổ hợp lá kín (AA: 1; Q♣Qx: 3; …).
> - **Câu "All AA hands contain the ace of clubs, of course — we have the other aces in our hand!":** ta chỉ giữ hai lá A (A♥ kín và A♠ ngửa); ý đúng là hai lá A còn lại là A♣ và A♦, nên đôi AA duy nhất có thể là A♣A♦ và tất nhiên chứa A♣.
> - **Các công thức ở mục "Reading Tells" bị viết rối (đã đối chiếu ảnh trang 70–71):** sách viết "p(T | A) = p(A ∩ T) / p(A)" gọi là định lý Bayes (phương trình 3.1), rồi "p(A ∩ T) = p(T) p(A ∨ T)" — ký hiệu "∨" ở đây là cách dựng chữ của dấu "|" nên vế phải là p(T) p(A | T). Câu then chốt "We also know that p(A | T) = p(A ∩ T) + p(Ā + T)" sai hai chỗ: vế trái phải là **p(T)** (chính lời giải thích ngay sau nói "xác suất T xảy ra"), và "Ā + T" phải là **Ā ∩ T** (A không xảy ra nhưng T xảy ra). Công thức đúng: p(T) = p(A ∩ T) + p(Ā ∩ T), nên p(A | T) = p(A ∩ T) / [p(A ∩ T) + p(Ā ∩ T)]. Lỗi "p(Ā + T)" lặp lại ở trang 71. Sách cũng dùng lẫn ký hiệu τ và T cho cùng một tell.
> - **Satellite: số liệu do người tổng hợp tính:** sách chỉ nói A♥8♥ có "gần 50% equity" trước phân phối đối thủ. Người tổng hợp mô phỏng (8.000 ván mỗi phân phối): trước "mọi lá A, mọi đôi, KQ, KJ" A♥8♥ có khoảng 48%; thêm KT và T9s, 98s, 87s, JTs thì khoảng 50%; trước riêng AK khác chất (9 tổ hợp) chỉ khoảng 30%. Ngưỡng hoà vốn theo chip: call 1.800 (đã có 300 big blind) vào pot cuối 2.100 + 2.100 + 150 = 4.350, tức cần 41,4%. Sách không bàn yếu tố đặc thù của satellite (giá trị chip không tuyến tính), sẽ được bàn ở Phần V.
> - **Khoảng tin cậy cho tỷ lệ raise 10% trên 121 tay:** sai số chuẩn √(0,1 × 0,9 / 121) ≈ 2,7%, nên khoảng ±2 sai số chuẩn là 4,5%–15,5%, sách làm tròn thành 4%–16%. Phân phối {TT+, AK, AQs} có 50 tổ hợp, tức 3,8% của 1.326 tổ hợp; {66+, AT+, KJ+, QJ, JT, T9} có 198 tổ hợp, tức 14,9% — sách ghi 16% "hoặc biến thể nào đó" (người tổng hợp tính).
> - **Pot 345 USD ở sixth street:** sách không nói số người chơi; người tổng hợp kiểm tra rằng con số khớp với bàn bảy người (năm người fold cộng ta và đối thủ): ante 7 × 5 = 35; third street 10 (bring-in) + 60 + 60 = 130; fourth street 2 × 30 = 60; fifth street 2 × 60 = 120; tổng 345 USD.
> - **Lớp chữ:** "mat" là "that"; "theft" là "their"; "-elated" là "related"; "'normally small)" là "(normally small)"; "single -and that" là "single hand that"; "litde" là "little"; "send-automatically" là "semi-automatically"; "dearly" là "clearly"; "ran firming" là "confirming"; "mates for" là "makes for"; "Hushes" là "flushes"; "imitations" là "limitations"; "horn" là "from"; "ethers" là "others". Bản tổng hợp đọc lại các danh sách tay bài và công thức từ ảnh trang.
> - **Quy ước:** trong stud, lá trong ngoặc là lá kín (úp), lá ngoài ngoặc là lá ngửa; "X♣Y♣" là hai lá chuồn nhỏ bất kỳ; "Qx", "Qy" là lá Q không phải chuồn. "Range" (phạm vi bài) được dịch là "phân phối tay bài" theo cách sách dùng "distribution".

## Sơ đồ

### Phần mở đầu Chương 5 — đọc đối thủ là suy luận Bayes, không phải đoán một tay bài (trang 62)

```text
       Quan niệm phổ biến (truyền hình, phỏng vấn): "đọc" đối thủ là khả
       năng không định lượng được; "dân toán" thiếu khả năng này
                                │
                                ▼
       Quan điểm của tác giả: đọc đối thủ phần lớn là SUY LUẬN BAYES dựa
       trên cách cược, cộng điều chỉnh (thường nhỏ) cho tell; đúng cả
       khi suy luận có ý thức hay tiềm thức
                                │
                                ▼
       Cách đọc sai: đoán một tay bài cụ thể ("cho đối thủ cầm AK"), chơi
       như thể đúng vậy
       · ví dụ: reraise người raise sớm bằng đôi nhỏ vì "đối thủ cầm AX";
         AK là tay đơn lẻ khả dĩ nhất, nhưng phân phối còn có các đôi lớn
         → mất equity cả trước và sau flop
                                │
                                ▼
       Ván satellite no-limit: 5 người còn lại, blind 150–300
       · người hay đẩy all-in stack ngắn đẩy khoảng 2.100 từ under the gun
       · tác giả ở big blind, khoảng 3.200 chip, cầm A♥ 8♥: CALL
       · đối thủ cầm AK khác chất; tác giả ra lá 8 và thắng
                                │
                                ▼
       Đối thủ hỏi: "Anh nghĩ tôi cầm gì mà anh hơn?"
       Trả lời: phân phối "mọi lá A, mọi đôi, vài lá K tốt, T9 cùng
       chất…" → A♥ 8♥ có gần 50% equity: call dễ dàng
       · không hề có bước "đoán một tay bài"; call vẫn đúng về cơ bản
         dù đối thủ cầm một trong các tay mạnh của phân phối
```

### Mục "Advanced Hand Reading" — phương pháp đọc bài theo phân phối (trang 62–63)

```text
       Người đọc bài giỏi hơn dùng suy luận logic và tell, loại dần các
       khả năng; lỗi thường gặp: loại tay bài khỏi phân phối quá mạnh
       tay, thu hẹp phân phối sai
                                │
                                ▼
       Phương pháp của tác giả:
       1. Không gán MỘT tay bài; mỗi đối thủ có một PHÂN PHỐI XÁC SUẤT
          trên mọi tay bài
       2. Đầu ván: phân phối đều trên mọi cặp lá kín, đã trừ các lá trong
          tay ta (hiệu ứng loại lá bài)
       3. Mỗi hành động: cập nhật theo lá mới lộ ra và theo ước lượng đối
          thủ sẽ làm gì với từng tay
       4. Giữ xác suất "MẤT TRÍ": khả năng (nhỏ) ta hiểu sai đối thủ hoặc
          đối thủ lệch khỏi lối chơi thường ngày
       5. Tell: thêm một lớp Bayes — "với mỗi tay trong phân phối, khả
          năng đối thủ để lộ tell này là bao nhiêu?"
                                │
                                ▼
       Mục tiêu: dùng mọi thông tin để có phân phối tay bài của đối thủ
       · quá trình chủ yếu là GIẢM và LOẠI: tay bài mà đối thủ sẽ chơi
         khác hẳn thì giảm xác suất
       · lý tưởng: còn một tay; thực tế: hầu như không thể
       · tại bàn không nhớ hết xác suất; dựng lại phân phối khi gặp
         quyết định quan trọng
```

### Ví dụ 5.1 (phần 1) — stud tám-hoặc-tốt-hơn: phân phối raise ở third street (Example 5.1, trang 63–64)

```text
       Seven-card stud tám-hoặc-tốt-hơn (hi-lo); ante 5 USD; 30–60 USD
       · người bên phải mở bắt buộc (bring-in) 10 USD với 2♣
       · ta nâng lên 30 USD với (5♣ A♥) 4♥
       · hai lá 10, lá 7♦ và một lá K fold
       · đối thủ ngửa 6♣ raise lên 60 USD; bring-in fold; ta call
       Lá đã fold: T♣ T♠ 7♦ K♠ 2♣
                                │
                                ▼
       Phân phối raise của đối thủ (lá kín trong ngoặc, 6♣ ngửa):
       ┌──────────────────────────┬─────────────────────────────────┐
       │ hầu như ai cũng reraise  │ (AA)6, (KK)6, (66)6; ba lá chuồn│
       │                          │ nhỏ có lá A                     │
       │ hơi hung hãn thêm        │ (QQ–TT)6; ba lá chuồn nhỏ bất   │
       │                          │ kỳ; (A2)6; (A3)6                │
       │ rất hung hãn thêm        │ (99–55)6; (A4)6; (A5)6; (54)6;  │
       │                          │ (57)6; ba lá chuồn có A, ví dụ  │
       │                          │ (A♣ J♣)6♣                       │
       │ tác giả từng thấy        │ (QJ)6                           │
       └──────────────────────────┴─────────────────────────────────┘
                                │
                                ▼
       Đã có thể giảm trọng số: chỉ còn hai lá 10, nên (TT)6 có khả năng
       bằng 1/6 so với khi không có lá nào bị fold; người cầm (TT)6 thấy
       hai lá 10 đã chết thì thường fold chứ không reraise
```

### Ví dụ 5.1 (phần 2) — fourth street và fifth street: ít thông tin, rồi nhiều thông tin (trang 64–65)

```text
       Fourth street: ta 8♠, đối thủ T♦; đối thủ check, ta bet, đối thủ
       call
       · ÍT THÔNG TIN: diễn biến dễ đoán; pot đủ lớn để call; mức cược
         sắp gấp đôi nên đối thủ có thể hoãn raise sang vòng sau
                                │
                                ▼
       Fifth street: ta J♥ (ba lá cơ + bốn lá thấp); đối thủ K♣, check;
       ta bet
       (5♣ A♥) 4♥ 8♠ J♥     đấu     (??) 6♣ T♦ K♣
       ┌──────────────────────┬──────────────────────────────────┐
       │ có lẽ CALL           │ (AA), (X♣Y♣), (QQ), (JJ)         │
       │ có lẽ RAISE          │ (66) — bộ ba 6; (KK) — bộ ba K   │
       │ có lẽ FOLD           │ (A2), (A3) — draw thấp đã hỏng   │
       └──────────────────────┴──────────────────────────────────┘
       · "có lẽ" vì không biết chắc; lệch thường gặp nhất: raise
         semi-bluff với bốn lá chuồn
       · loại hẳn một tay bài có thể trả giá đắt nếu ta raise "an toàn"
         rồi bị reraise
                                │
                                ▼
       Đối thủ CALL → phân phối còn: đôi lớn và bốn lá chuồn
```

### Ví dụ 5.1 (phần 3) — sixth street: đếm tổ hợp lá kín (trang 65–67)

```text
       Sixth street: ta A♠ (có đôi A); đối thủ 3♣; pot 345 USD
       (5♣ A♥) 4♥ 8♠ J♥ A♠     đấu     (??) 6♣ T♦ K♣ 3♣
       Câu hỏi: có nên bet? Quyết định sát đến đâu? (giải ở Chương 8)
                                │
                                ▼
       Đếm tổ hợp lá kín (tạm bỏ qua nhóm "mất trí"):
       ┌──────────────┬────────┬─────────────────────────────────────┐
       │ lá kín       │ số tổ  │ lý do                               │
       │              │ hợp    │                                     │
       ├──────────────┼────────┼─────────────────────────────────────┤
       │ AA           │ 1      │ chỉ còn A♣, A♦                      │
       │ Q♣ Qx        │ 3      │ không lá Q nào chết; 6 đôi, 3 có Q♣ │
       │ Qx Qy        │ 3      │                                     │
       │ J♣ Jx        │ 2      │ J♥ trong tay ta; còn 3 đôi, 2 có J♣ │
       │ Jx Jy        │ 1      │                                     │
       │ X♣ Y♣        │ 6      │ chuồn thấp còn A♣ 4♣ 7♣ 8♣: C(4,2)  │
       └──────────────┴────────┴─────────────────────────────────────┘
                                │
                                ▼
       Bốn nhóm: đôi A; đôi lớn có flush draw; đôi lớn không flush draw;
       flush thấp đã thành
       Tell có thể dịch chuyển phân phối: đối thủ khó chịu khi lá A ra
       (nếu chỉ lộ khi cầm đôi lớn) → nên bet; đối thủ vui khi thấy 3♣
       → có thể tiết kiệm ít nhất một bet nếu họ đã có flush
```

### Phần chuyển tiếp — tóm tắt quá trình đọc bài trong Ví dụ 5.1 (trang 66–67)

```text
       Đầu ván: phân phối đều trên mọi cặp lá kín
       Third street (raise): còn chủ yếu đôi lớn, bài thấp mạnh, ba lá
       chuồn thấp
       Fourth street: ta có thêm equity, nhưng ít thông tin
       Fifth street: NHIỀU thông tin — tiếp tục sau lá cao thứ hai, nên
       loại các draw thấp không có hai lá chuồn kín; nếu đối thủ vẫn call
       với ba lá thấp, ta đã lời ngay từ sai lầm đó
       Sixth street: ta có bài cao; đối thủ cũng mạnh lên nhờ lá chuồn
       nhỏ → bốn nhóm tay bài
                                │
                                ▼
       Chơi khai thác = tìm phân phối tay bài VÀ chiến lược của đối thủ
       (hoặc phân phối có trọng số của nhiều chiến lược) để tối đa hoá
       EV; đọc bài phụ thuộc vào ước lượng đối thủ chơi từng tay ra sao
```

### Mục "Reading Strategies" — bốn nguồn thông tin và giới hạn của chúng (trang 67–69)

```text
       Đọc chiến lược: ước lượng đối thủ sẽ chơi từng tay trong phân phối
       ra sao
       · giả định đối thủ chơi tốt phần còn lại → khai thác HÌNH DẠNG phân
         phối; nếu họ tiếp tục mắc lỗi → lời thêm
                                │
                                ▼
       Bốn nguồn thông tin:
       1. Bằng chứng trực tiếp: bài phải lật ở showdown — chắc chắn đúng
       2. Bằng chứng trực tiếp do đối thủ chủ động lật — đúng, nhưng có
          thể nhằm tác động tâm lý
       3. Bằng chứng gián tiếp: tần suất hành động, kể cả với tay không
          lật
       4. Tương quan theo phân loại người chơi (chặt–lỏng, thụ động–hung
          hãn, hình mẫu con vật…): xếp đúng nhóm thì suy ra được cả tình
          huống chưa từng thấy
                                │
                                ▼
       Giới hạn:
       · 1.000 tay limit đủ bàn (khoảng 30 giờ ở casino, 10–15 giờ
         online): chỉ khoảng 100 tay được lật, chia lệch cho 9 vị trí
       · 121 tay under the gun, raise 10%: khoảng tin cậy 95% là 4%–16%
         ({TT+, AK, AQs} tới {66+, AT+, KJ+, QJ, JT, T9})
       · đối thủ có thể đang khai thác ta; đối thủ thay đổi theo thời
         gian; ít cơ hội xác nhận một nhận định lệch khỏi lối chơi thông
         thường
       · não người thấy mẫu hình ở cả dữ liệu ngẫu nhiên
       · fold 30 tay rồi lật AA: chỉ 30 tay fold là bằng chứng "chặt";
         lá AA chỉ chứng minh họ được chia AA
                                │
                                ▼
       Kết luận: đọc chiến lược có giá trị nhưng tốn công, thông tin mơ
       hồ hơn nhiều người tưởng
```

### Mục "Reading Tells" — tell, dương tính giả và ba kiểu người chơi yếu (trang 69–72)

```text
       Người chơi đánh giá quá cao khả năng đọc bài và đọc tell vì trí nhớ
       chọn lọc
       · "trò chơi đọc bài": ở showdown của ván mình không tham gia, đoán
         đúng tay bài là "thắng", sai là "thua" → biết mình sai nhiều
                                │
                                ▼
       Đọc tell giống chẩn đoán bệnh: thấy triệu chứng, suy ra nguyên nhân
       · mệt mỏi ít khi là ung thư vì có nhiều nguyên nhân khả dĩ hơn
       · p(A | T) = p(A ∩ T) / [p(A ∩ T) + p(Ā ∩ T)]
       · p(Ā ∩ T) là DƯƠNG TÍNH GIẢ: tell xuất hiện mà không mang nghĩa
         ta gán cho nó
               ┌────────────────┴────────────────┐
               ▼                                 ▼
       Tell hiếm khi dương tính giả:     Tell có nhiều nghĩa trái ngược:
       người chưa hành động không giữ    đẩy chip nhanh (bài yếu giả mạnh,
       bài, quay đi chỗ khác → hầu như   hoặc bài mạnh nhưng dễ bị vượt…)
       chắc bài yếu                      → p(A | T) không gần 0 hay 1
               └────────────────┬────────────────┘
                                ▼
       Ba kiểu người chơi yếu dễ nhận ra:
       · MANIAC (rất lỏng, rất hung hãn): nếu lùi khi bị raise thì chỉ
         call với bài khá mạnh để họ bluff; nếu không lùi thì đẩy mạnh
         bài mạnh
       · ROCK (rất chặt, thụ động): cướp blind, cướp pot trên flop khi cả
         hai trượt
       · CALLING STATION (lỏng, thụ động, hay call): value bet cả những
         bài yếu hơn hẳn bình thường
                                │
                                ▼
       Thận trọng khi kết luận ai đó chơi tệ từ một hai ví dụ (lỗi nhất
       thời, đã tiến bộ, hoặc lối chơi lỏng–hung hãn thật ra rất mạnh)
       Game càng yếu càng đáng đọc chiến lược; trước người chơi tốt, dành
       công sửa lỗ hổng của chính mình
```

### Phần "Key Concepts" — các ý then chốt cuối chương (trang 72)

```text
       · Tối đa hoá EV bằng chơi khai thác cần thông tin chính xác về
         phân phối tay bài và chiến lược chơi các tay đó của đối thủ
       · Bằng chứng trực tiếp (bài lật ở showdown) rất giá trị vì chắc
         chắn đúng
       · Bằng chứng gián tiếp (tần suất hành động) cũng là cơ sở suy luận
       · Đọc tell là quá trình Bayes: giá trị của tell phụ thuộc tần suất
         và độ tin cậy; dương tính giả làm giảm mạnh giá trị
       · Chơi khai thác hiệu quả nhất trước người chơi rất tệ
       · Mục tiêu cuối cùng: dùng mọi thông tin để có phân phối xác suất
         tay bài của đối thủ
```

## Ba câu hỏi chương này trả lời

1. **"Đọc bài" thực chất là gì?** Là suy luận Bayes về một phân phối xác suất trên mọi tay bài đối thủ có thể cầm, không phải đoán một tay cụ thể. Bắt đầu từ phân phối đều trên các cặp lá kín (trừ các lá ta thấy), mỗi hành động và mỗi lá lộ ra làm giảm trọng số các tay mà đối thủ đáng lẽ đã chơi khác; giữ một xác suất nhỏ cho hành động bất thường. Trong ván satellite, A♥8♥ call đúng vì có gần 50% equity trước cả phân phối (cần khoảng 41%), dù thua tay AK cụ thể mà đối thủ cầm. Trong Ví dụ 5.1, phân phối của đối thủ được thu hẹp từ một danh sách bài raise ở third street xuống 16 tổ hợp lá kín ở sixth street.
2. **Ta biết được bao nhiêu về chiến lược của đối thủ?** Ít hơn nhiều người tưởng. Nguồn tin gồm bài lật ở showdown, bài đối thủ tự lật, tần suất hành động và việc xếp đối thủ vào một nhóm người chơi; nhưng sau 1.000 tay chỉ khoảng 100 tay được lật, 121 tay ở một vị trí với tỷ lệ raise 10% vẫn để khoảng tin cậy 95% từ 4% tới 16%, người chơi thay đổi theo thời gian và theo đối thủ, và não người dễ thấy mẫu hình không có thật. Vì vậy cách dùng dữ liệu hiệu quả nhất là phân loại đúng người chơi rồi suy ra lối chơi của họ.
3. **Tell có giá trị đến đâu, và đối thủ nào dễ khai thác nhất?** Giá trị của tell tính bằng định lý Bayes: p(A | T) = p(A ∩ T) / [p(A ∩ T) + p(Ā ∩ T)]; tell hiếm khi dương tính giả (như quay đi khi chưa hành động) rất giá trị, tell có nhiều cách hiểu (đẩy chip nhanh) giá trị thấp dù quan sát rõ. Ba kiểu người chơi yếu — maniac, rock, calling station — lộ ra rất nhanh trong dữ liệu và có cách khai thác rõ; trước người chơi tốt, công sức nên dành cho việc sửa lỗi của chính mình.

## Khái niệm cần biết

- **Đọc bài (hand reading):** quá trình suy luận Bayes để có phân phối xác suất tay bài của đối thủ. Ví dụ: đối thủ raise với 6♣ ngửa ở third street, call ở fourth và fifth street; ở sixth street còn 16 tổ hợp lá kín. Quan trọng vì mọi quyết định khai thác đều tính trên phân phối này.
- **Phân phối tay bài (hand distribution, range):** tập các tay đối thủ có thể cầm, mỗi tay có một xác suất. Ví dụ: "mọi lá A, mọi đôi, vài lá K tốt, T9 cùng chất" của người đẩy all-in. Quan trọng vì equity phải tính trước cả phân phối, không trước một tay.
- **"Cho đối thủ cầm một tay" (putting a player on a hand):** cách đọc sai, đoán một tay cụ thể rồi chơi như thể chắc chắn. Ví dụ: reraise bằng đôi nhỏ vì "đối thủ cầm AX", bỏ qua các đôi lớn trong phân phối. Quan trọng vì nó làm mất equity một cách có hệ thống.
- **Hiệu ứng loại lá bài (card-removal effect):** lá bài ta thấy (trong tay ta, ngửa, đã fold) làm giảm số tổ hợp đối thủ có thể có. Ví dụ: hai lá 10 bị fold nên (TT) chỉ còn 1 tổ hợp thay vì 6. Quan trọng vì nó là bước cập nhật Bayes đầu tiên, miễn phí.
- **Xác suất "mất trí" (lost his mind probability):** xác suất nhỏ dành cho khả năng ta hiểu sai đối thủ hoặc đối thủ chơi lệch hẳn thói quen. Ví dụ: đối thủ raise semi-bluff với bốn lá chuồn thay vì call. Quan trọng vì gán xác suất 0 cho hành động bất thường dẫn tới fold sai hoặc raise "an toàn" rồi bị reraise.
- **Stud tám-hoặc-tốt-hơn (seven-card stud eight-or-better):** stud chia pot giữa bài cao nhất và bài thấp nhất đủ điều kiện (năm lá khác nhau từ 8 trở xuống). Ví dụ: (5♣ A♥) 4♥ có ba lá thấp. Quan trọng vì Ví dụ 5.1 diễn ra trong trò này.
- **Bring-in, complete:** bring-in là cược mở bắt buộc của người có lá ngửa thấp nhất ở stud; complete là nâng lên mức cược đầy đủ. Ví dụ: bring-in 10 USD với 2♣, ta complete lên 30 USD. Quan trọng để hiểu diễn biến ví dụ.
- **Đọc chiến lược (strategy reading):** ước lượng đối thủ sẽ chơi từng tay trong phân phối ra sao. Ví dụ: đối thủ cầm (KK)6 sẽ raise ở fifth street khi ra K♣. Quan trọng vì đọc bài phụ thuộc vào nó.
- **Bằng chứng trực tiếp và gián tiếp (direct, indirect hand evidence):** trực tiếp là bài thấy được ở showdown; gián tiếp là tần suất hành động. Ví dụ: raise 12 lần trong 121 tay ở under the gun. Quan trọng vì chúng có độ tin cậy và cỡ mẫu rất khác nhau.
- **Tương quan theo phân loại người chơi (player classification correlation):** xếp đối thủ vào một nhóm (chặt–lỏng, thụ động–hung hãn) rồi suy ra lối chơi của họ. Ví dụ: thấy một người lỏng–thụ động, đoán họ hay call với draw yếu. Quan trọng vì đây là cách dùng dữ liệu ít ỏi hiệu quả nhất.
- **Tell:** dấu hiệu cơ thể vô tình để lộ sức mạnh bài. Ví dụ: người chưa hành động quay đi khỏi bàn. Quan trọng vì nó là một lớp bằng chứng Bayes thêm vào phân phối.
- **Dương tính giả của tell (false positive):** tell xuất hiện mà không mang nghĩa ta gán cho nó; đo bằng p(Ā ∩ T). Ví dụ: đẩy chip nhanh có thể là bài yếu giả mạnh hoặc bài mạnh sợ bị vượt. Quan trọng vì nó quyết định giá trị của tell.
- **Maniac, rock, calling station:** maniac chơi rất lỏng và rất hung hãn; rock chơi rất chặt và thụ động; calling station chơi lỏng, thụ động, hay call. Ví dụ: calling station call nhiều vòng với draw yếu. Quan trọng vì ba kiểu này dễ nhận ra nhanh và có cách khai thác rõ.

## Nội dung chi tiết

### 1. Phần mở đầu: đọc đối thủ là suy luận Bayes (trang 62)

Người chơi, nhất là trên truyền hình và trong phỏng vấn, thích nói về việc "đọc" đối thủ và cho rằng mình làm việc đó giỏi hơn đối thủ. Nhiều cách mô tả ngầm định rằng một "nhận định" (read) không thể định lượng, và "dân toán" thiếu óc tưởng tượng thì không có khả năng này. Tác giả không đồng ý. Khả năng chỉ ra chính xác tay bài đối thủ bằng "phép màu" thì đúng là mạnh, nhưng theo tác giả, đọc đối thủ phần lớn là quá trình suy luận Bayes liên quan tới cách cược (betting pattern), cộng vài điều chỉnh (thường nhỏ) cho tell cơ thể — dù quá trình suy luận diễn ra có ý thức hay tiềm thức. Dùng một mô hình toán học có thể nâng cao trực giác, làm kim chỉ nam cho cách chơi đúng.

**Cách đọc bằng cách đoán một tay.** Một cách "đọc" phổ biến là đoán tay bài của đối thủ, chơi như thể họ cầm tay đó, và mong là đúng. Đôi khi cách này dẫn tới nước chơi đúng. Ví dụ: người chơi limit hold'em reraise người raise sớm bằng đôi nhỏ hoặc vừa khi có vị trí, vì "cho đối thủ cầm AX". Đúng là AK (giả sử đối thủ luôn raise tay này) là tay đơn lẻ khả dĩ nhất mà người raise sớm có thể cầm, nên nhận định này thường đúng. Nhưng những người chơi đó có thể đang mất equity cả trước lẫn sau flop vì giả định đối thủ cầm một tay cụ thể, trong khi phân phối của đối thủ không chỉ có các lá lớn không thành đôi mà còn có các đôi lớn hơn.

**Ván satellite.** Một tác giả gần đây chơi một ván trong satellite no-limit (giải vòng loại, phần thưởng là vé vào giải lớn hơn) minh hoạ điểm này. Còn năm người, blind 150–300; một người đã đẩy stack ngắn all-in nhiều lần trong khoảng mười tay gần nhất raise all-in khoảng 2.100 từ vị trí under the gun (người hành động đầu tiên trước flop). Mọi người fold tới tác giả ở big blind, có khoảng 3.200 chip, cầm A♥ 8♥. Tác giả call. Người raise cầm AK khác chất (AKo); tác giả ra lá 8 và thắng.

Sau satellite, người cầm AKo hỏi: "Anh nghĩ tôi cầm gì mà anh hơn?" Tác giả trả lời: "Tôi đoán anh đẩy với mọi lá A, mọi đôi, vài lá K tốt. Thêm nữa, anh càng là người chơi giỏi thì càng có khả năng raise với các tay như T9 cùng chất. Trước phân phối đó, tôi có gần 50% equity, nên call dễ dàng."

Ý của câu chuyện: người hỏi cố hình dung suy nghĩ của tác giả là "đoán một tay bài" rồi đánh giá cơ hội trước tay đó. Nhưng không có bước nào như vậy. Tác giả dựng một phân phối các tay mà người kia có thể raise và hành động theo đó. Tình cờ đối thủ cầm một trong các tay mạnh của phân phối và tác giả may mắn thắng. Câu hỏi "hơn" một tay cụ thể không bao giờ là một phần của quá trình ra quyết định, và quyết định call vẫn đúng về cơ bản.

Người tổng hợp tính lại bằng mô phỏng (8.000 ván cho mỗi phân phối):

| Phân phối của người đẩy all-in | Số tổ hợp | Equity của A♥ 8♥ (ước lượng) |
|---|---:|---:|
| mọi lá A, mọi đôi, KQ, KJ | 245 | khoảng 48% |
| thêm KT, T9s, 98s, 87s, JTs | 275 | khoảng 50% |
| chỉ AK khác chất | 9 | khoảng 30% |

Ngưỡng hoà vốn theo chip: tác giả đã có 300 trong pot (big blind), phải bỏ thêm 1.800 để call 2.100; pot cuối là 2.100 + 2.100 + 150 (small blind) = 4.350, nên cần 1.800 / 4.350 ≈ 41,4% equity. Trước phân phối, call có lợi rõ (khoảng +6 tới +8 điểm phần trăm trên ngưỡng); trước riêng AKo thì thua lỗ — nhưng quyết định phải dựa trên phân phối.

### 2. Đọc bài nâng cao (Advanced Hand Reading, trang 62–63)

Những người chơi khác "đọc" đối thủ bằng kết hợp suy luận logic và tell. Họ loại dần các khả năng dựa trên giả định rằng đối thủ chơi hợp lý, hoặc dựa trên hiểu biết của họ về cách đối thủ chơi. Lỗi thường gặp của kiểu đọc bài này là loại tay bài khỏi phân phối của đối thủ quá mạnh tay, thu hẹp sai phân phối. Dù vậy, cách làm này gần với quá trình đọc bài mà tác giả chủ trương hơn nhiều; ở dạng tinh vi nhất thì nó giống hệt.

**Phương pháp, về lý thuyết:**

1. Nói chung không bao giờ gán một tay bài duy nhất cho đối thủ; mỗi đối thủ có một **phân phối xác suất** trên các tay bài có thể.
2. Đầu ván, mỗi đối thủ có phân phối đầy đủ các tay ngẫu nhiên, đã điều chỉnh theo hiệu ứng loại lá bài (Bayes) do các lá trong tay ta.
3. Khi mỗi người hành động, ta điều chỉnh xác suất theo thông tin mới: cả lá mới lộ ra lẫn ước lượng tốt nhất về hành động mà người chơi sẽ chọn với từng tay.
4. Thường thêm một xác suất phụ, có thể gọi là xác suất **"mất trí"**, phản ánh khả năng (đôi khi nhỏ) rằng hiểu biết của ta về phong cách của đối thủ chưa đầy đủ, hoặc họ đơn giản là đang lệch khỏi chiến lược thường ngày. Người chơi, kể cả người khá giỏi, thỉnh thoảng làm những việc rất bất thường; coi các việc đó có xác suất 0 là sai và có thể dẫn tới "fold lớn" sai hoặc call, raise tồi.

Thực tế, ta không giữ trong đầu xác suất chính xác của từng tay; việc đó quá tải và tốn công hơn giá trị nó mang lại. Nhưng thường ta có thể dựng lại diễn biến cược và các lá đã lộ để tạo phân phối cho đối thủ ở thời điểm cần ra quyết định quan trọng. Đưa tell cơ thể vào khuôn khổ này cũng không khó: chỉ cần áp thêm một lớp định lý Bayes lên phân phối hiện có. Tức là hỏi: "Với phân phối tay bài mà người này đang có, xác suất họ để lộ tell tôi vừa thấy với mỗi tay là bao nhiêu?" rồi cân lại phân phối theo thông tin bổ sung.

Mục tiêu cuối cùng là đưa mọi thông tin thu được vào để tìm phân phối xác suất tay bài của đối thủ. Đây nói chung là quá trình giảm và loại: các tay mà đối thủ đáng lẽ đã chơi khác hẳn thì giảm xác suất tương đối trong phân phối. Lý tưởng là thu đủ thông tin để phân phối chỉ còn một tay; thực tế điều đó thường không thể.

### 3. Ví dụ 5.1 — đọc bài trong seven-card stud tám-hoặc-tốt-hơn (Example 5.1, trang 63–67)

Ví dụ chi tiết này đưa ra nhiều giả định về ý nghĩa của cách chơi ở từng vòng; nhiều giả định có thể tranh luận. Mục đích không phải tranh cãi cách chơi đúng của tay bài mà minh hoạ quá trình đọc bài. Chương này xét khía cạnh đọc bài; quyết định then chốt của ván được xét ở Chương 8.

#### Third street

Trò chơi là seven-card stud tám-hoặc-tốt-hơn (eight-or-better: pot chia đôi giữa bài cao nhất và bài thấp nhất đủ điều kiện, tức năm lá khác nhau đều từ 8 trở xuống). Ante 5 USD, mức cược 30–60 USD. Người ngồi bên phải ta mở bắt buộc (bring-in) với 2♣, 10 USD. Ta nâng lên mức đầy đủ (complete) 30 USD với (5♣ A♥) 4♥. Hai người có lá 10 ngửa, người có 7♦ và người có một lá K fold. Người tiếp theo, ngửa 6♣, raise lên 60 USD. Người bring-in fold; ta call.

- Ta: (5♣ A♥) 4♥
- Đối thủ: (??) 6♣
- Lá đã fold: T♣ T♠ 7♦ K♠ 2♣

Ở third street, ta bắt đầu dựng hình ảnh về tay bài của đối thủ. Dù không biết gì về người chơi này, vẫn dựng được một phân phối thô:

| Mức hung hãn của đối thủ | Các tay bài reraise (lá kín trong ngoặc, 6♣ ngửa) |
|---|---|
| Hầu như mọi người chơi | (AA)6, (KK)6, (66)6; ba lá chuồn nhỏ có lá A |
| Đối thủ hơi hung hãn hơn thêm | (QQ–TT)6; ba lá chuồn nhỏ bất kỳ; (A2)6; (A3)6 |
| Đối thủ khá hung hãn thêm | (99–55)6; (A4)6; (A5)6; (54)6; (57)6; ba lá chuồn có lá A, ví dụ (A♣ J♣)6♣ |
| Tác giả từng thấy | (QJ)6 |

Về nhóm cuối, tác giả bình luận: không may cho phương pháp đọc bài nhưng may cho bankroll (vốn chơi) của tác giả, những người chơi kiểu này thường mất tiền quá nhanh nên không kịp có nhận định chính xác về phân phối raise của họ.

Ở giai đoạn sớm này chỉ có thể xấp xỉ phân phối. Nhưng một số tay đã khá khó xảy ra. Chẳng hạn chỉ còn hai lá 10 trong bộ bài (T♣ và T♠ đã fold), nên (TT)6 có khả năng chỉ bằng 1/6 so với khi không có lá nào bị fold (C(2, 2) = 1 tổ hợp so với C(4, 2) = 6). Hơn nữa, người cầm (TT)6 thấy hai lá 10 đã chết có lẽ sẽ fold chứ không reraise.

Người tổng hợp đếm thêm số tổ hợp lá kín của nhóm "hầu như mọi người chơi" ở thời điểm này: (AA) có 3 tổ hợp (ta giữ A♥); (KK) có 3 (K♠ đã fold); (66) có 3 (6♣ đang ngửa); ba lá chuồn nhỏ có lá A: A♣ đi với một trong 3♣, 4♣, 7♣, 8♣, tức 4 tổ hợp (2♣ đã fold, 5♣ trong tay ta).

#### Fourth street

Ta rút 8♠, đối thủ rút T♦ — diễn biến thuận lợi. Đối thủ check, ta bet, mong đôi khi thắng pot ngay. Nhưng đối thủ call.

Ở vòng này ta thu được rất ít thông tin, vì hai lý do. Thứ nhất, diễn biến cược theo khuôn mẫu dễ đoán: ta rút lá khá tốt, đối thủ rút lá khá tệ; nhưng cỡ pot và sức mạnh tương đối của hai phân phối (chủ đề sẽ quay lại sau) làm cho việc đối thủ chỉ call chờ fifth street là hợp lý. Thứ hai, mức cược tăng gấp đôi ở vòng sau; người chơi thường nên hoãn raise ở vòng cược nhỏ khi raise làm lộ thông tin và họ có khả năng raise ở vòng sau.

#### Fifth street

Ta rút J♥ — lá khá tệ, dù cho ta ba lá cơ (A♥ 4♥ J♥) bên cạnh bốn lá thấp (A, 4, 5, 8). Đối thủ rút K♣ và lại check. Ta bet, mong thắng pot khá thường xuyên.

- Ta: (5♣ A♥) 4♥ 8♠ J♥
- Đối thủ: (??) 6♣ T♦ K♣

Xét ý nghĩa các hành động có thể của đối thủ, nhìn lại các tay ứng viên, nhất là hai nhóm đầu:

| Hành động có lẽ chọn | Các tay bài |
|---|---|
| Có lẽ call | (AA) 6♣ T♦ K♣; (X♣Y♣) 6♣ T♦ K♣ (bốn lá chuồn); (QQ) 6♣ T♦ K♣; (JJ) 6♣ T♦ K♣ |
| Có lẽ raise | (66) 6♣ T♦ K♣ (bộ ba 6); (KK) 6♣ T♦ K♣ (bộ ba K) |
| Có lẽ fold | (A2) 6♣ T♦ K♣; (A3) 6♣ T♦ K♣ (draw thấp đã có hai lá cao) |

Mỗi nhóm chỉ là "có lẽ": hoàn toàn không rõ đối thủ thực sự chơi các tay này ra sao hay chọn mỗi hành động bao nhiêu phần trăm số lần. Có vẻ lệch khỏi các chiến lược này thường gặp nhất là raise semi-bluff với bốn lá chuồn; nhưng không loại trừ được các kiểu lệch khác. Khi dựng phân phối, rất quan trọng là không bỏ qua việc đối thủ sẽ chơi bài theo những cách ta không lường trước. Loại hẳn một tay dựa trên hành động trước đó có thể trả giá đắt nếu nó khiến ta raise "an toàn" ở cuối ván rồi bị reraise và thấy bài mạnh hơn.

Giả sử đối thủ call. Ta tạm thu hẹp tay của họ xuống các đôi lớn và bốn lá chuồn.

#### Sixth street

Ta rút A♠, đối thủ rút 3♣. Ta có một quyết định.

- Ta: (5♣ A♥) 4♥ 8♠ J♥ A♠ (sách in nhầm lá kín thành A♠; xem khối Lưu ý)
- Đối thủ: (??) 6♣ T♦ K♣ 3♣

Pot có 345 USD (người tổng hợp kiểm tra: khớp với bàn bảy người, xem khối Lưu ý). Câu hỏi: có nên bet? Nhiều người sẽ gần như tự động bet với đôi A và draw thấp. Nhưng với các giả định trên, tay này mạnh đến đâu? Và quan trọng không kém, quyết định sát đến đâu — nếu đổi giả định một chút, toàn bộ phân tích có đổi không? Để trả lời, phải xét phân phối giả định của đối thủ và EV của ta trước toàn bộ phân phối đó (Chương 8).

Trước hết, xác định các tay đối thủ có thể cầm, tạm bỏ qua nhóm "mất trí" (sẽ kiểm tra lại kết quả với các phân phối có thêm tay thuộc nhóm này). Dựa trên cách đối thủ chơi suốt ván, có bốn nhóm: (AA), (X♣Y♣), (QQ), (JJ), cùng với 6♣ T♦ K♣ 3♣ ngửa. Giờ phải chia nhỏ QQ và JJ thành tay có lá chuồn tương ứng và tay không có:

- Không lá Q nào chết; trong sáu đôi Q, ba đôi chứa Q♣.
- J♥ đã chết (trong tay ta), nên chỉ còn ba đôi J (từ J♠, J♦, J♣), hai đôi chứa J♣.
- Mọi đôi AA đều chứa A♣: ta giữ A♥ và A♠, nên đôi AA duy nhất có thể là A♣ A♦.
- Số tay "ba lá chuồn thấp": 2♣ đã fold ở third street, 3♣ và 6♣ ngửa trước mặt đối thủ, 5♣ trong tay ta, nên các lá này không thể là lá kín của đối thủ. Còn bốn lá chuồn thấp: A♣, 4♣, 7♣, 8♣, cho C(4, 2) = 6 cặp lá kín hai lá chuồn.

| Lá kín của đối thủ | Số tổ hợp | Ý nghĩa ở sixth street | Tỷ lệ nếu mọi tổ hợp đồng khả năng (người tổng hợp tính) |
|---|---:|---|---:|
| AA (A♣ A♦) | 1 | đôi A, có bốn lá chuồn | 6,25% |
| Q♣ Qx | 3 | đôi Q, có flush draw | 18,75% |
| Qx Qy | 3 | đôi Q, không flush draw | 18,75% |
| J♣ Jx | 2 | đôi J, có flush draw | 12,5% |
| Jx Jy | 1 | đôi J, không flush draw | 6,25% |
| X♣ Y♣ | 6 | đã có flush (năm lá chuồn) với các lá thấp | 37,5% |
| Cộng | 16 | | 100% |

(Cột tỷ lệ giả định mọi tổ hợp được đối thủ chơi theo cùng một cách; sách chưa gán trọng số theo tần suất hành động.)

**Tell bổ sung.** Có thể có thêm thông tin. Chẳng hạn, một tell cho thấy đối thủ không thích bài của mình khi lá A ra rõ ràng ủng hộ việc bet — nếu ta nghĩ họ chỉ để lộ tell đó khi có đôi lớn kín. Ngược lại, một tell cho thấy họ rất vui khi thấy 3♣ có thể cực kỳ giá trị, và có thể giúp ta tiết kiệm ít nhất một bet đầy đủ nếu họ đã có flush.

#### Tóm tắt quá trình đọc bài

Ta bắt đầu với phân phối gán xác suất như nhau cho mọi cặp lá kín đối thủ có thể cầm. Khi họ raise ở third street, ta thu hẹp được xuống tập con chủ yếu gồm các đôi lớn, bài thấp mạnh và ba lá chuồn thấp. Ở fourth street, ta có thêm equity trong pot nhờ rút lá khá trong khi đối thủ rút lá tệ, nhưng thu được rất ít thông tin.

Ở fifth street, ta thu được rất nhiều thông tin khi đối thủ tiếp tục dù đã rút lá cao thứ hai. Hoàn toàn hợp lý khi đối thủ theo thêm một lá ở fourth street với ba lá thấp khác chất sau khi đã reraise vòng trước. Nhưng khi K♣ ra ở fifth, ta gần như loại được mọi draw thấp không có hai lá chuồn kín. Nếu đối thủ vẫn call ở fifth chỉ với ba lá thấp, ta lời ngay từ sai lầm đó; dù quá trình khai thác của ta có làm mất chút kỳ vọng ở các vòng sau, phần lời từ sai lầm của họ đã bù dư.

Ở sixth street, bài ta mạnh lên đáng kể vì có bài cao (đôi A); đồng thời phân phối của đối thủ cũng mạnh lên đáng kể nhờ lá chuồn nhỏ, nhiều khả năng cho họ flush draw hoặc flush. Ta thu hẹp phân phối của họ xuống khoảng bốn nhóm: đôi A, đôi lớn có flush draw, đôi lớn không có flush draw, và flush thấp đã thành.

Ví dụ này chủ yếu dùng cách cược để đọc bài. Yếu tố quan trọng thứ hai là khả năng phát hiện và diễn giải đúng tell. Sách không bàn cách nhận ra tell (ngoài phạm vi), nhưng việc diễn giải đúng tell thì có nhiều chỗ cho toán học (mục 5). Ván này sẽ trở lại ở Chương 8 với quyết định bet hay check ở sixth street.

Khi chơi khai thác, ta tìm một phân phối tay bài và một chiến lược của đối thủ (hoặc một phân phối có trọng số của nhiều chiến lược) để tối đa hoá EV trước đó. Tới đây, chương đã bàn "đọc bài", với tác giả về bản chất là suy luận Bayes về phân phối tay bài. Quá trình đó lại phụ thuộc vào ước lượng đối thủ chơi từng tay ra sao; trong các ví dụ trước, ta hoặc giả định đối thủ chơi thẳng thắn, hoặc giả định đã biết chiến lược của họ để tiện phân tích.

### 4. Đọc chiến lược (Reading Strategies, trang 67–69)

Một phần quan trọng và cực kỳ khó của chơi khai thác là đánh giá chính xác cách đối thủ sẽ chơi các tay khác nhau trong phân phối của họ. Một giả định có thể là đối thủ sẽ chơi rất tốt mọi tay còn lại. Nếu giả định vậy và tìm chiến lược khai thác tương ứng, chiến lược đó sẽ khai thác **hình dạng** phân phối của họ. Khi đối thủ đã mắc lỗi nghiêm trọng để đi tới một điểm trong ván (như call ở fifth street với ba lá thấp), khai thác hình dạng phân phối sẽ rất có lời. Ta còn lời thêm nếu đối thủ tiếp tục mắc lỗi khi chơi phân phối của họ ở các điểm quyết định sau. Có nhiều nguồn thông tin để ước lượng chiến lược, quá trình sách gọi là "đọc chiến lược":

1. **Bằng chứng trực tiếp về tay bài.** Đôi khi ta có thông tin chắc chắn đúng về tay đã chơi, vì người chơi buộc phải lật bài ở showdown để thắng pot. Khi có, đây có lẽ là loại bằng chứng giá trị nhất, vì nhiều loại khác có thể bị làm giả.
2. **Bằng chứng trực tiếp do đối thủ kiểm soát.** Là nhóm con của loại trên: đối thủ đôi khi cố ý lật bài. Đây là con dao hai lưỡi: bằng chứng là thật, nhưng việc đối thủ tự nguyện cho xem làm nó kém giá trị hơn, vì có lẽ nhằm tạo hiệu ứng tâm lý. Dù vậy, nếu cân trọng số hợp lý, ta thường vẫn dùng được thông tin này.
3. **Bằng chứng gián tiếp.** Ngoài giá trị bài phải lộ ở showdown, ta có thể ghi tần suất các hành động, kể cả với các tay không được lật. Thông tin này hữu ích cho cả đọc bài lẫn đọc chiến lược, nhưng phải kết hợp với thông tin về loại tay bài đang được chơi.
4. **Tương quan theo phân loại người chơi.** Có lẽ là cách đọc chiến lược phổ biến nhất, cả với người chơi ta chưa thu được nhiều thông tin lẫn với các tình huống ít gặp. Về cơ bản là xếp người chơi vào các nhóm hoặc tổ hợp nhóm. Một số tác giả đề xuất các trục như lỏng–chặt (loose–tight) và thụ động–hung hãn (passive–aggressive); số khác dùng hình mẫu con vật. Cốt lõi của mọi cách này: nếu mô tả chính xác được lối chơi của một nhóm người chơi và xếp đúng một người vào nhóm đó, ta có thể suy luận về lối chơi của họ ngay cả trong tình huống chưa từng thấy họ chơi.

Phần tiếp theo chủ yếu xét người chơi hợp lý: không dễ bị khai thác một cách rõ ràng, dù mắc lỗi thường xuyên. Cuối mục sẽ bàn các kiểu người chơi rất yếu, có chiến lược dễ đọc hơn nhiều.

#### Giới hạn của việc đọc chiến lược

Dù có các nguồn tin trên, cần nhận ra giới hạn của khả năng đọc chiến lược. Theo tác giả, nhiều người chơi, nhất là người giỏi thu thập và ghi nhớ thông tin, đánh giá quá cao độ chắc chắn của nhận định về chiến lược đối thủ, và do đó đánh giá quá cao giá trị dự báo của việc phân loại. Ngay cả qua nhiều tay, ta thu được tương đối ít bằng chứng trực tiếp về cách một người chơi.

**Bằng chứng trực tiếp ít.** Xét mẫu 1.000 tay limit hold'em bàn đủ người (tương đương khoảng ba mươi giờ chơi ở sòng bài thật, có lẽ mười tới mười lăm giờ online). Có vẻ là mẫu khá lớn để "nắm được" lối chơi của đối thủ. Nhưng một đối thủ điển hình có lẽ chỉ lật bài khoảng một trăm tay trong số đó. Các tay này chia không đều cho chín vị trí, với blind và button chiếm phần lớn bất cân xứng. Hơn nữa, các tay lật bài được chơi trên các kiểu flop rất khác nhau, trước các đối thủ khác nhau, trong các tình huống khác nhau.

**Bằng chứng gián tiếp cũng không giúp nhiều**, vì cỡ mẫu cho hành động trước flop chỉ chậm chạp đạt mức tin cậy. Ví dụ, xét 121 tay chơi ở vị trí under the gun. Nếu người chơi raise 10% số tay quan sát được ở vị trí này, thì khoảng tin cậy 95% cho tỷ lệ thật trên toàn bộ là khoảng 4% tới 16% số tay (người tổng hợp tính: sai số chuẩn √(0,1 × 0,9 / 121) ≈ 2,7%, khoảng ±2 sai số chuẩn là 4,5%–15,5%).

| Tỷ lệ raise | Phân phối ví dụ | Số tổ hợp (người tổng hợp đếm) |
|---:|---|---:|
| khoảng 4% | {TT+, AK, AQs} | 50 (3,8%) |
| khoảng 16% | {66+, AT+, KJ+, QJ, JT, T9} hoặc biến thể | 198 (14,9%) |

Ngay cả thấy vài tay mạnh người này raise ở vị trí này cũng không thu hẹp được phân phối nhiều, vì các tay như QQ có mặt trong mọi phân phối đó. Thêm nữa, các tay mạnh dễ đi tới showdown hơn nhờ sức mạnh của chúng (thiên lệch chọn mẫu). Vì vậy khó suy ra nhiều điều giá trị từ bằng chứng gián tiếp.

Do đó, có vẻ nguồn thông tin chính về lối chơi của đối thủ đến từ việc dùng bằng chứng trực tiếp không phải để ước lượng thẳng họ sẽ chơi thế nào trong từng tình huống, mà để **phân loại chính xác** người chơi rồi kết luận về lối chơi dựa trên phân loại đó. Một số mối đe doạ đến giá trị của phương pháp này:

- **Người chơi không dùng một chiến lược cố định trong ngắn hạn:** họ có thể đang chơi khai thác trong tay quan sát được. Dùng một tay quan sát được để phân loại đối thủ dựa trên giả định tay đó đặc trưng cho chiến lược tổng thể của họ. Điều thường quan trọng với chơi khai thác không phải người đó chơi thế nào nói chung, mà chơi thế nào *trước bạn*. Một chương sau sẽ bàn việc phản khai thác (counter-exploitation) và cách đối thủ thích nghi gây khó cho chơi khai thác, dẫn ta tới tìm giải pháp khác.
- **Người chơi không dùng một chiến lược cố định trong thời gian dài:** họ đọc sách, nói chuyện với người chơi khác, tự rút ra bài học. Vì vậy ngay cả một nhận định được mài giũa kỹ cũng có thể mất hiệu lực khá nhanh. Ngay cả việc thắng một thời gian ở mức cược cao hơn thường lệ cũng có thể khiến một người tự tin hơn và thay đổi mạnh chiến lược.
- **Rất ít cơ hội kiểm chứng giả thuyết.** Nhiều tay được chơi giống nhau theo nhiều chiến lược khác nhau. Nếu người chơi chơi một tay như vậy theo cách thông thường, điều đó chỉ xác nhận rất nhẹ nhận định của ta. Hiếm khi một nhận định dự báo lệch khỏi lối chơi thông thường được xác nhận: muốn vậy, nhận định phải dự báo lệch với một tay cụ thể, đối thủ phải cầm đúng tay đó, và ta phải có thông tin trực tiếp về tay họ cầm (thường qua showdown). Nếu xảy ra, đó là bằng chứng xác nhận mạnh — nhưng hiếm.

**Não người thấy mẫu hình không có thật.** Bộ óc con người rất giỏi thấy mẫu hình, kể cả trong chuỗi ngẫu nhiên. Nhiều nghiên cứu tâm lý học xác nhận rằng người ta thường mô tả mẫu hình nền trong dữ liệu được đưa cho họ, ngay cả khi dữ liệu được sinh ngẫu nhiên và không có mẫu hình nào. Vì vậy ta nên chủ động tìm thông tin xác nhận hoặc bác bỏ giả thuyết của mình; nhưng như đã thấy, thông tin đó thường khó có vì ít cơ hội quan sát.

**Đừng coi bằng chứng không xác nhận là bằng chứng xác nhận.** Ví dụ: một người chơi hold'em fold mọi tay trong vài vòng đầu, rồi chơi một tay và ở showdown lật AA. Nhiều người sẽ coi đó là bằng chứng xác nhận người này chơi chặt trước flop. Nhưng việc họ chơi AA không phải bằng chứng họ chặt — chỉ là bằng chứng họ được chia AA, vì mọi chiến lược hợp lý đều chơi AA trước flop. Ba mươi tay họ fold trước đó mới là bằng chứng về sự chặt; việc lật AA không thêm gì vào bằng chứng có sẵn, dù nó tạo nên một câu chuyện hay ("Gã này fold ba mươi tay liền. Rồi chơi một tay, và đó là đôi A"). Người tổng hợp diễn giải bằng ngôn ngữ Bayes: tỷ số hợp lý p(chơi AA | chặt) / p(chơi AA | lỏng) xấp xỉ 1, nên quan sát này không làm dịch chuyển xác suất hậu nghiệm.

Đoạn này có thể tạo ấn tượng tác giả rất bi quan về việc đọc chiến lược. Không phải vậy: tác giả cho rằng công sức đòi hỏi cao và giá trị đôi khi đáng ngờ của thông tin trái ngược hẳn với nhận thức của nhiều người chơi, những người tin rằng có thể đánh giá nhanh và chính xác chiến lược của một người chơi hợp lý chỉ sau vài giờ ngồi cùng bàn. Việc mô tả lối chơi của một người từ dữ liệu rất hạn chế thường chỉ cho một cảm nhận mơ hồ về cách họ có thể chơi, thiếu các chi tiết làm cho việc khai thác thật sự có lời.

### 5. Đọc tell (Reading Tells, trang 69–72)

#### Trò chơi đọc bài

Nhiều người chơi đánh giá quá cao khả năng đọc bài hay phát hiện tell. Lý do thường là trí nhớ chọn lọc: ta nhớ những lần đọc trúng phóc, nhưng quên những lần hơi bất ngờ ở showdown. Tác giả rèn trực giác để đánh giá đúng giá trị của tell bằng một phương pháp gọi là **"trò chơi đọc bài"**: ở showdown của một ván mình không tham gia, ngay sau khi cược ở river kết thúc, thử gọi tên tay bài của một người trong ván. Gọi đúng chính xác là "thắng", sai là "thua". Nhờ đó ta biết rõ hơn nhận định của mình đúng bao nhiêu lần và sai bao nhiêu lần. Sau một buổi chơi trò này, nhiều người ngạc nhiên vì họ gọi đúng bài đối thủ ít đến thế và sai thường đến thế.

#### Giá trị và khó khăn của tell

Thông tin thêm từ tell cơ thể, cho đọc bài hay đọc chiến lược, có giá trị đáng kể. Nhưng có khó khăn tương tự các khó khăn đã bàn: giống thông tin lịch sử, khó quan sát được nhiều lần xác nhận; cần cùng lúc có tay phù hợp, tell xuất hiện, rồi bằng chứng xác nhận qua showdown. Tuy vậy, khi có một tell đã được xác nhận, bằng chứng này có thể cực kỳ giá trị. Tell cũng thường áp dụng được (ở dạng yếu hơn chút) qua phân loại người chơi: thấy một tell ở một nhóm rộng người chơi, ta suy ra một người lạ có tell đó đang ở tình huống tương tự những người khác.

#### Tell như chẩn đoán bệnh

Đọc tell cơ thể có nhiều điểm chung với chẩn đoán bệnh, một quá trình Bayes về bản chất: quan sát các hiệu ứng rồi suy ra nguyên nhân. Cảm lạnh gây nghẹt mũi và mệt mỏi; bệnh xơ cứng teo cơ một bên (ALS) gây mất dần chức năng vận động. Ta quan sát triệu chứng và cố xác định nguyên nhân. Tương tự, có quan hệ nhân quả giữa sức mạnh tay bài và tell: người chơi đẩy chip nhanh vì phấn khích với bài mạnh; người chơi nín thở khi bluff, v.v.

Kỹ năng nằm ở chỗ đảo ngược mạng Bayes và đánh giá chính xác phân phối tiên nghiệm để diễn giải đúng thông tin mới. Bệnh nhân ung thư có báo mệt mỏi, nhưng bác sĩ bình thường không chẩn đoán ung thư cho một người khoẻ mạnh chỉ vì triệu chứng đó, cũng không nghĩ ngay tới nó trong danh sách nguyên nhân khả dĩ, vì có nhiều nguyên nhân khả dĩ hơn nhiều.

**Công thức.** Gọi A là một sự kiện, chẳng hạn "đang bluff", và T là tell đã quan sát. Thứ ta cần là p(A | T), xác suất A đúng khi thấy T. Theo định nghĩa xác suất có điều kiện (phương trình 3.1) và quy tắc nhân (phương trình 1.5):

- p(A | T) = p(A ∩ T) / p(T);
- p(T) = p(A ∩ T) + p(Ā ∩ T): xác suất T xảy ra bằng xác suất A và T cùng xảy ra cộng xác suất A không xảy ra nhưng T xảy ra.

Vậy p(A | T) = p(A ∩ T) / [p(A ∩ T) + p(Ā ∩ T)] = p(T | A)p(A) / [p(T | A)p(A) + p(T | Ā)p(Ā)]. (Sách viết các công thức này với vài ký hiệu sai; xem khối Lưu ý.)

Số hạng thứ hai, p(Ā ∩ T), rất quan trọng: nó là xác suất **dương tính giả** — tần suất ta thấy tell mà nó không mang nghĩa ta gán cho nó. Tell rất hiếm khi dương tính giả thì rất giá trị, vì p(A | T) tiến tới 100%. Ví dụ: một người chưa hành động không giữ bài và, chẳng hạn, quay đi khỏi bàn. Tell này hầu như không bao giờ dương tính giả, vì người có bài mạnh sẽ không làm vậy.

Ngược lại, điều này chỉ ra lỗi của cách đọc tell thông thường: gán nghĩa cho các tell có nghĩa khác mâu thuẫn với nghĩa được gán. Chẳng hạn, vì sao một người đẩy chip vào nhanh? Có thể lập luận cả hai phía: người đó có thể có bài yếu và cố tỏ ra mạnh; có thể nóng lòng đẩy chip vì bài mạnh nhưng dễ bị vượt; v.v. Dù việc quan sát tell rất rõ ràng (ta chắc chắn đã thấy), tell vẫn có giá trị thấp vì số hạng p(Ā ∩ T) lớn đến mức xác suất có điều kiện không gần 1 hay 0.

Minh hoạ của người tổng hợp: giả sử tiên nghiệm đối thủ bluff là 20%. Một tell xuất hiện 50% số lần khi bluff. Nếu nó chỉ xuất hiện 5% số lần khi không bluff: p(bluff | T) = 0,1 / (0,1 + 0,8 × 0,05) = 0,1 / 0,14 ≈ 71%. Nếu nó xuất hiện 30% số lần khi không bluff: p(bluff | T) = 0,1 / (0,1 + 0,8 × 0,3) = 0,1 / 0,34 ≈ 29%, gần như không đổi so với 20%.

Bài toán thật phức tạp hơn nhiều: ta muốn xác suất của một sự kiện A khi có một chuỗi quan sát gồm các tell T_n ở các ván trước, các tay bài quan sát được A_n, các tay không quan sát được, và một tell T ở ván hiện tại. Nhưng ta thiếu quan sát để làm việc này. Bộ óc một số người có vẻ xử lý các xác suất có điều kiện này tốt hơn người khác; có lẽ chính hiệu ứng đó khiến ta nhận ra những người có khả năng "đọc" mạnh hơn.

#### Ba kiểu người chơi yếu dễ nhận ra

Tin tốt hơn cho chơi khai thác: có những kiểu người chơi phổ biến chơi khá tệ, về họ ta có thông tin dễ dàng và ngay lập tức.

- **Maniac:** người chơi cực kỳ lỏng và hung hãn trong mọi tình huống, thường chơi bài rất yếu một cách rất hung hãn và bỏ thêm bet, raise khi rõ ràng là sai. Lưu ý: người chơi rất giỏi thường bị nhầm là maniac, nhất là ở bàn ít người (short-handed) hoặc bàn rất chặt, vì họ cũng chơi bài yếu hung hãn và bền bỉ. Khai thác maniac thường cần biết họ phản ứng thế nào trước sự hung hãn ngược lại. Nếu họ lùi khi bị raise, thường đúng là chỉ call với bài khá mạnh, để họ bluff nhiều lần nhất có thể. Nếu họ phớt lờ sự hung hãn hoặc tiếp tục lao vào, thì đẩy mạnh bài mạnh là đáp trả khai thác đúng.
- **Rock:** người chơi cực kỳ chặt và thường khá thụ động, chỉ vào pot với bài rất mạnh và thường không lấy được giá trị từ các bài đó. Rock hiếm khi bluff, thích sự an toàn của bài mạnh. Khai thác rock về cơ bản là cướp blind của họ và cướp pot trên flop khi cả hai cùng trượt.
- **Calling station:** người chơi lỏng nhưng thụ động, thường call nhiều hoặc mọi vòng với bài yếu hoặc draw yếu. Họ có sự bền bỉ của người chơi giỏi nhưng không lấy giá trị từ bài của mình đúng cách. Khai thác thường là value bet thêm những bài yếu hơn hẳn phạm vi bet bình thường, vì các bet này nay có giá trị trước phạm vi call rộng của calling station.

Các chiến lược này dễ nhận ra và mô tả vì chúng thể hiện khá nhanh trong các nguồn thông tin chính đã bàn. Sau 100 tay, người raise 8% số tay ở một vị trí gần như không phân biệt được với người raise 12% (người tổng hợp tính: sai số chuẩn khoảng 2,7% và 3,2%, nên khoảng ±2 sai số chuẩn của hai người chồng lên nhau gần hết); nhưng dễ nhận ra người raise, chẳng hạn, 50% số tay. Còn với người chỉ raise một tay trong một trăm, đi tới showdown và tay đó tình cờ là đôi A kín, ta dùng được định lý Bayes để kết luận về xu hướng của họ. Dĩ nhiên người chơi theo các chiến lược này ở các mức độ khác nhau: maniac cực đoan có thể là "raise-bot", raise nhiều chip nhất có thể ở mọi cơ hội — tương đối dễ thắng. Maniac càng tiết chế sự hung hãn ở những chỗ rõ ràng là cửa dưới, càng tiến gần tới chơi tốt, càng khó khai thác, và việc khai thác càng kém giá trị.

#### Thận trọng khi kết luận đối thủ chơi tệ

Cần thận trọng khi kết luận một người chơi tệ từ một hai ví dụ. Có nhiều nguy cơ:

1. Người đó có thể chỉ mắc một lỗi tệ không đặc trưng. Poker phức tạp, ai cũng mắc lỗi kiểu này hay kiểu khác.
2. Người đó có thể đã tiến bộ kể từ lần ta thấy nước chơi yếu. Việc này hay xảy ra, nhất là online, nơi ta có thể "ghi chú" về một nước chơi; vài tháng sau cố khai thác một người có thể đã tiến bộ nhiều là nguy hiểm.
3. Nước chơi có thể không yếu như ta tưởng. Điều này hay xảy ra khi gặp lối chơi lỏng–hung hãn thật ra khá mạnh nhưng không theo quan niệm thông thường về sự "chặt" trước flop. Tự động coi người chơi lỏng–hung hãn là yếu, nhiều người bỏ qua một mối nguy lớn làm họ mất nhiều tiền, và tự chuốc lấy bực bội vì không thắng được những người chơi "yếu" này.

Game càng yếu, người chơi càng rơi vào các nhóm dễ khai thác. Theo tác giả, chủ yếu ở game yếu, việc đọc chiến lược đối thủ mới mang lại nhiều nhất, nhờ nhanh chóng nhận ra và khai thác người chơi rất tệ. Với người chơi khá tốt, không có lỗ hổng lớn, tác giả thường cho rằng hiệu quả và có lời hơn khi dành công sức tìm lỗ hổng trong lối chơi của chính mình và ngăn người khác khai thác mình.

### 6. Các ý then chốt (Key Concepts, trang 72)

- Tối đa hoá EV bằng chơi khai thác đòi hỏi xây dựng thông tin chính xác và hữu ích về phân phối tay bài của đối thủ và chiến lược họ chơi các tay đó.
- Một số bằng chứng thu được là bằng chứng trực tiếp, chẳng hạn tay bài lật ở showdown. Bằng chứng này cực kỳ giá trị vì biết chắc là đúng.
- Bằng chứng gián tiếp, như tần suất hành động, cũng có thể làm cơ sở suy luận về lối chơi và chiến lược.
- Đọc tell về bản chất là quá trình Bayes: giá trị của một tell liên quan trực tiếp tới cả tần suất lẫn độ tin cậy của nó. Dương tính giả làm giảm đáng kể giá trị của tell.
- Chơi khai thác đạt hiệu quả tối đa trước người chơi rất tệ.
- Mục tiêu cuối cùng của đọc bài là đưa mọi thông tin thu được vào để tìm phân phối xác suất tay bài của đối thủ.

## Luận điểm cốt lõi

### Mệnh đề

Đọc đối thủ là suy luận Bayes có thể định lượng: duy trì một phân phối xác suất trên mọi tay bài đối thủ có thể cầm, cập nhật nó theo lá lộ ra, hành động và tell, rồi quyết định trước cả phân phối. Đọc chiến lược của đối thủ có giá trị nhưng bị giới hạn nghiêm trọng bởi dữ liệu ít, đối thủ thay đổi, và thiên kiến của não người; vì vậy nó đem lại nhiều nhất trước những người chơi rất tệ.

### Giả định

- Đối thủ chơi theo một chiến lược ổn định đủ để ước lượng (ít nhất trong một ván).
- Có thể gán xác suất cho hành động của đối thủ với từng tay; mọi tổ hợp lá kín ban đầu đồng khả năng.
- Tell có quan hệ nhân quả ổn định với sức mạnh tay bài (cho từng người hoặc từng nhóm người).

### Cơ chế

1. Phân phối tiên nghiệm: mọi cặp lá kín, trừ lá đã thấy.
2. Hàm hợp lý: với mỗi tay, xác suất đối thủ có hành động quan sát được (raise, call, check) và xác suất để lộ tell.
3. Cập nhật: nhân và chuẩn hoá; giữ xác suất "mất trí" để không loại hẳn tay nào.
4. Giá trị thông tin của một quan sát phụ thuộc vào việc các tay khác nhau có hành động khác nhau không: fourth street và việc lật AA gần như không mang thông tin; fifth street và tell ít dương tính giả mang nhiều thông tin.
5. Chiến lược của đối thủ ước lượng qua phân loại, vì dữ liệu trực tiếp quá ít.

### Bằng chứng và ví dụ tác giả đưa ra

- Ván satellite: A♥8♥ call all-in vì có gần 50% equity trước phân phối, dù thua AK.
- Ví dụ 5.1: từ danh sách bài raise ở third street tới 16 tổ hợp lá kín ở sixth street.
- 1.000 tay chỉ khoảng 100 tay showdown; 121 tay, 10% raise, khoảng tin cậy 4%–16%.
- Ví dụ lật AA sau 30 tay fold; ví dụ bác sĩ không chẩn đoán ung thư từ mệt mỏi.
- Ba kiểu người chơi yếu và cách khai thác.

### Kết luận và hàm ý cho người chơi

- Đừng hỏi "tôi có hơn tay X không?", hãy hỏi "equity của tôi trước cả phân phối là bao nhiêu?".
- Đừng loại hẳn tay bài nào; giữ xác suất nhỏ cho bất ngờ.
- Đánh giá mỗi quan sát theo câu hỏi: các tay khác nhau có hành động khác nhau không? Nếu không, quan sát gần như vô giá trị.
- Tự kiểm tra khả năng đọc bằng "trò chơi đọc bài" để tránh tự tin quá mức.
- Tell có nhiều cách hiểu thì giá trị thấp; tell gần như không bao giờ sai mới đáng tin.
- Ở game yếu, nhận diện và khai thác người chơi tệ; ở game mạnh, sửa lỗi của mình.

### Trong ngôn ngữ xác suất

Đọc bài là lọc Bayes (Bayesian filtering) trên không gian các tổ hợp lá kín: π_t(h) ∝ π_{t−1}(h) · p(a_t | h, s), trong đó a_t là hành động ở vòng t và s là chiến lược của đối thủ. Đọc chiến lược là ước lượng s — một bài toán suy luận thống kê với cỡ mẫu nhỏ, nên phân loại người chơi đóng vai trò của phân phối tiên nghiệm phân cấp (hierarchical prior), tức "mượn sức mạnh" từ dữ liệu của những người cùng nhóm (theo hiểu biết của người tổng hợp). Giá trị của tell đo bằng tỷ số hợp lý p(T | A) / p(T | Ā): tỷ số gần 1 thì tell vô giá trị dù quan sát rõ đến đâu.

## Thuật ngữ

| Tiếng Anh | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| hand reading | đọc bài | suy luận phân phối tay bài của đối thủ |
| strategy reading | đọc chiến lược | ước lượng cách đối thủ chơi từng tay |
| read | nhận định | kết luận về bài hoặc lối chơi của đối thủ |
| putting someone on a hand | đoán một tay cụ thể | gán cho đối thủ đúng một tay bài |
| hand distribution, range | phân phối tay bài | tập tay bài có thể kèm xác suất |
| card removal | loại lá bài | lá đã thấy làm giảm tổ hợp của đối thủ |
| lost his mind probability | xác suất "mất trí" | xác suất nhỏ cho hành động bất thường |
| betting pattern | cách cược | chuỗi hành động cược của đối thủ |
| tell | tell | dấu hiệu cơ thể để lộ sức mạnh bài |
| false positive | dương tính giả | tell xuất hiện mà không mang nghĩa được gán |
| direct / indirect hand evidence | bằng chứng trực tiếp / gián tiếp | bài thấy ở showdown / tần suất hành động |
| player classification | phân loại người chơi | xếp đối thủ vào nhóm để suy ra lối chơi |
| loose–tight, passive–aggressive | lỏng–chặt, thụ động–hung hãn | hai trục phân loại phổ biến |
| maniac | maniac | cực kỳ lỏng và hung hãn |
| rock | rock | cực kỳ chặt và thụ động |
| calling station | calling station | lỏng, thụ động, hay call |
| raise-bot | raise-bot | maniac cực đoan, raise ở mọi cơ hội |
| counter-exploitation | phản khai thác | khai thác lại người đang khai thác mình |
| leak | lỗ hổng | điểm yếu lặp lại trong lối chơi |
| satellite | satellite | giải vòng loại, thưởng vé vào giải lớn hơn |
| all-in, jam, push | all-in | đặt toàn bộ chip |
| under the gun | under the gun | vị trí hành động đầu tiên trước flop |
| big blind, small blind, button | big blind, small blind, button | cược bắt buộc lớn, nhỏ; vị trí người chia |
| short stack | stack ngắn | lượng chip ít |
| AKo, T9s | AK khác chất, T9 cùng chất | ký hiệu o = offsuit, s = suited |
| seven-card stud eight-or-better | stud tám-hoặc-tốt-hơn | stud chia pot cao–thấp, bài thấp phải từ 8 trở xuống |
| ante | ante | tiền góp bắt buộc của mọi người trước khi chia |
| bring-in | bring-in | cược mở bắt buộc của người có lá ngửa thấp nhất |
| complete | complete | nâng bring-in lên mức cược đầy đủ |
| third/fourth/fifth/sixth street | third/fourth/fifth/sixth street | các vòng cược của stud (lá thứ 3 tới thứ 6) |
| hole cards, upcards | lá kín, lá ngửa | lá úp chỉ người cầm thấy / lá lật cho mọi người |
| three-flush, four-flush | ba lá, bốn lá cùng chất | draw thùng ở các mức |
| low draw | draw thấp | đang chờ bài thấp đủ điều kiện |
| flat call | call (không raise) | chỉ theo cược |
| showdown | showdown | lật bài so ở cuối ván |
| full ring | bàn đủ người | 9–10 người |
| brick and mortar | sòng bài thật | chơi trực tiếp, không online |
| short-handed | bàn ít người | khoảng 6 người trở xuống |
| big laydown | fold lớn | bỏ một bài mạnh vì tin đối thủ mạnh hơn |
| bankroll | bankroll | vốn dành cho chơi poker |
| Bayesian inference | suy luận Bayes | cập nhật xác suất theo bằng chứng |
| prior distribution | phân phối tiên nghiệm | phân phối trước khi có bằng chứng mới |
| confidence interval | khoảng tin cậy | khoảng giá trị hợp lý cho một tỷ lệ chưa biết |

## Câu nói đáng nhớ

> "It is our view that reading opponents is largely a process of Bayesian inference related to betting patterns, with some (normally small) adjustments made for physical tells." — mở đầu chương
>
> *Dịch: Theo chúng tôi, đọc đối thủ phần lớn là quá trình suy luận Bayes dựa trên cách cược, với vài điều chỉnh (thường nhỏ) cho tell cơ thể.*
>
> Ý nghĩa: luận điểm trung tâm của chương; "đọc" là toán, không phải phép màu.

> "Against that range, I had almost 50% equity, so I think it's an easy call." — câu chuyện satellite
>
> *Dịch: Trước phân phối đó, tôi có gần 50% equity, nên đó là một call dễ dàng.*
>
> Ý nghĩa: quyết định dựa trên phân phối, không dựa trên việc "hơn" một tay cụ thể.

> "We generally never assign one single hand to an opponent; instead, each opponent has a probability distribution of different possible hands." — mục Advanced Hand Reading
>
> *Dịch: Nói chung chúng tôi không bao giờ gán một tay bài duy nhất cho đối thủ; mỗi đối thủ có một phân phối xác suất của các tay có thể.*
>
> Ý nghĩa: nguyên tắc nền của đọc bài hiện đại.

> "Pretending that these things are probability zero is simply incorrect and can lead to making incorrect 'big laydowns' or bad calls and raises." — mục Advanced Hand Reading
>
> *Dịch: Coi những việc này có xác suất bằng 0 đơn giản là sai, và có thể dẫn tới những lần fold lớn sai, hoặc call và raise tồi.*
>
> Ý nghĩa: luôn để chỗ cho bất ngờ trong phân phối.

> "Even over the course of many hands, we gain relatively little direct evidence of how a player plays." — mục Reading Strategies
>
> *Dịch: Ngay cả qua nhiều tay, ta thu được tương đối ít bằng chứng trực tiếp về cách một người chơi.*
>
> Ý nghĩa: cảnh báo về sự tự tin quá mức khi "đọc" đối thủ.

> "The fact that the player played AA is not confirming evidence of his tightness — in fact, it is only evidence that he was dealt AA." — mục Reading Strategies
>
> *Dịch: Việc người chơi chơi AA không phải bằng chứng xác nhận họ chặt — thực ra chỉ là bằng chứng họ được chia AA.*
>
> Ý nghĩa: một quan sát mà mọi giả thuyết đều dự báo như nhau thì không mang thông tin.

> "Tells that are very seldom false positives are very valuable." — mục Reading Tells
>
> *Dịch: Những tell rất hiếm khi là dương tính giả thì rất giá trị.*
>
> Ý nghĩa: giá trị của tell nằm ở độ tin cậy, không ở độ rõ ràng khi quan sát.

> "In the case of players who play fairly well, without any very large leaks, we often consider it to be more efficient and profitable to spend energy on identifying leaks in our own play." — cuối chương
>
> *Dịch: Với những người chơi khá tốt, không có lỗ hổng lớn, chúng tôi thường cho rằng hiệu quả và có lời hơn khi dành công sức tìm lỗ hổng trong lối chơi của chính mình.*
>
> Ý nghĩa: chuyển dần từ khai thác sang chiến lược khó bị khai thác — dẫn tới Phần III.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương biến khái niệm mơ hồ "đọc đối thủ" thành một quy trình cụ thể: phân phối tiên nghiệm, cập nhật theo hành động và lá bài, xác suất cho bất ngờ. Câu chuyện satellite là minh hoạ tốt cho sự khác biệt giữa "đoán một tay" và "tính trước phân phối", và mô phỏng của người tổng hợp xác nhận nhận định "gần 50%" của tác giả. Phần về giới hạn của việc đọc chiến lược đặc biệt có giá trị vì nó đi ngược niềm tin phổ biến của người chơi, dựa trên các lập luận thống kê đúng: cỡ mẫu nhỏ, thiên lệch chọn mẫu ở showdown, giá trị thông tin bằng không của quan sát mà mọi giả thuyết đều dự báo. Ví dụ "lật AA sau 30 tay fold" là một bài học về tỷ số hợp lý rất dễ nhớ.

### Những chỗ đơn giản hoá

- **Ví dụ 5.1 dừng ở đếm tổ hợp:** mọi tổ hợp được coi là như nhau, trong khi thực tế xác suất mỗi tay đi tới sixth street khác nhau (một người chơi có thể raise ba lá chuồn với tần suất khác với đôi Q). Sách tự thừa nhận các nhóm chỉ là "có lẽ".
- **Satellite:** quyết định được đánh giá theo equity chip; trong satellite, giá trị chip không tuyến tính (mất hết chip khác với nhân đôi chip), nên ngưỡng thật có thể cao hơn 41,4%. Sách bàn chủ đề này ở Phần V.
- **Tell:** sách chỉ đưa khuôn khổ, không có số liệu thực nghiệm về tần suất tell; các con số minh hoạ trong bản tổng hợp là giả định của người tổng hợp.
- **Phân loại người chơi** được trình bày như công cụ chính, nhưng sách không nói cách đánh giá độ chính xác của phân loại.

### Những gì đã thay đổi từ 2006 (theo hiểu biết của người tổng hợp)

- Phần mềm theo dõi và HUD làm cho "bằng chứng gián tiếp" có hàng chục nghìn tay cho mỗi đối thủ online, nên vấn đề cỡ mẫu của tác giả giảm nhiều với các chỉ số trước flop, nhưng vẫn còn với các tình huống hiếm (river, check-raise). Nhiều phòng chơi sau đó cấm hoặc hạn chế HUD, đưa vấn đề trở lại.
- Tư duy "phạm vi bài" (range) thay cho "đoán một tay" nay là mặc định trong cộng đồng poker, phần lớn nhờ các sách như cuốn này và nhờ solver.
- Bot poker dùng đúng khuôn khổ của chương: Libratus và Pluribus duy trì phân phối niềm tin về bài đối thủ và cập nhật theo hành động; đồng thời các AI này không dựa vào đọc chiến lược đối thủ mà chơi gần tối ưu, đúng với lời khuyên cuối chương khi gặp đối thủ mạnh.
- Poker online và trực tuyến không có tell cơ thể; "timing tell" (thời gian ra quyết định) thay thế một phần (Chương 6).

### Liên hệ các chương khác

- [C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md](C03-dung-het-thong-tin-uoc-luong-tham-so-va-dinh-ly-bayes.md): định lý Bayes, ví dụ xét nghiệm và ví dụ maniac — nền của đọc bài và đọc tell; khoảng tin cậy dùng cho tỷ lệ raise.
- [C04-pot-odds-va-implied-odds.md](C04-pot-odds-va-implied-odds.md): định nghĩa chơi khai thác và quy trình hai bước; chương này là bước một.
- [C06-poker-truc-tuyen.md](C06-poker-truc-tuyen.md): thông tin và tell trong poker online.
- [C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md](C08-choi-chinh-xac-tay-bai-dau-phan-phoi.md): quyết định bet hay check ở sixth street của Ví dụ 5.1, tính EV trước phân phối 16 tổ hợp.
- [C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md](C09-choi-thich-nghi-phan-phoi-dau-phan-phoi.md): thích nghi khi đối thủ cũng điều chỉnh, phản khai thác.
- [C10-ly-thuyet-tro-choi.md](C10-ly-thuyet-tro-choi.md): chiến lược tối ưu — câu trả lời khi không đọc được đối thủ đủ chắc.
- [C27-giai-dau-phan-2-chip-khong-phai-tien.md](C27-giai-dau-phan-2-chip-khong-phai-tien.md): giá trị chip không tuyến tính trong giải đấu, liên quan quyết định call ở satellite.

### Vận dụng

- **Người chơi poker:** trước mỗi quyết định lớn, viết ra (trong đầu) phân phối của đối thủ theo nhóm và đếm tổ hợp như Ví dụ 5.1; hỏi equity trước cả phân phối. Chơi "trò chơi đọc bài" để hiệu chỉnh sự tự tin. Ghi chú về đối thủ kèm ngày, và nghi ngờ các ghi chú cũ.
- **Người làm tài chính và đầu tư:** đọc thị trường cũng là đọc phân phối: thay vì "đoán" một kịch bản (lãi suất sẽ giảm), hãy gán xác suất cho nhiều kịch bản và chọn vị thế tốt trước cả phân phối. Bài học "lật AA" áp dụng cho đánh giá nhà quản lý quỹ: một thương vụ thành công mà mọi nhà quản lý đều làm (mua cổ phiếu lớn trong thị trường tăng) không phải bằng chứng về kỹ năng; bằng chứng là những quyết định khác biệt so với số đông và được kiểm chứng. Thiên lệch chọn mẫu ở showdown giống thiên lệch người sống sót (survivorship bias) trong dữ liệu quỹ.
- **Người ra quyết định nói chung:** một tín hiệu chỉ có giá trị khi tỷ lệ dương tính giả của nó thấp (như chương trước về xét nghiệm); hãy hỏi "tín hiệu này có xuất hiện ngay cả khi điều tôi nghi ngờ là sai không?". Và đừng loại hẳn khả năng nào — luôn để một xác suất nhỏ cho "đối phương mất trí".
