# Chương 3 — Phương pháp đánh giá (Evaluation Methodology)

**Nguồn:** Chip Huyen, *AI Engineering: Building Applications with Foundation Models*, O'Reilly Media, ấn bản đầu tiên (12/2024), Chương 3 "Evaluation Methodology", trang PDF 232–314.
**Tác giả:** Chip Huyen — nhà văn và nhà khoa học máy tính chuyên về hệ thống học máy; từng làm ở NVIDIA, Snorkel AI, sáng lập một startup hạ tầng AI (sau được mua lại), dạy hệ thống học máy ở Đại học Stanford; tác giả *Designing Machine Learning Systems* (O'Reilly 2022) và bốn sách tiếng Việt bán chạy, trong đó có bộ *Xách ba lô lên và đi*.
**Vị trí trong lập luận của cả cuốn sách:** Chương 1 ([C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md)) đặt khung cho kỹ thuật AI (AI engineering) và nhấn mạnh rằng đánh giá là một trong những khác biệt lớn nhất so với học máy truyền thống; Chương 2 ([C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md)) giải thích dữ liệu huấn luyện, kiến trúc, post-training và cách lấy mẫu (sampling) làm cho đầu ra của mô hình nền tảng mang tính xác suất và mở. Chương 3 là chương thứ nhất trong hai chương về đánh giá: nó trình bày *các phương pháp* đánh giá mô hình có đầu ra mở — độ đo mô hình hoá ngôn ngữ (cross entropy, perplexity), đánh giá chính xác (functional correctness, độ tương đồng với dữ liệu tham chiếu, embedding), AI làm giám khảo (AI as a judge) và xếp hạng bằng đánh giá so sánh — cùng giới hạn của từng phương pháp. Chương 4 ([C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md)) dùng các phương pháp này để chọn mô hình và dựng quy trình đánh giá cho ứng dụng. Embedding và độ tương đồng cosine được dùng lại cho tìm kiếm vector trong RAG ở Chương 6 ([C06-rag-va-agent.md](C06-rag-va-agent.md)) và khử trùng lặp dữ liệu ở Chương 8 ([C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md)); perplexity xuất hiện lại khi bàn về lượng tử hoá ở Chương 7 ([C07-finetuning.md](C07-finetuning.md)); phản hồi so sánh từ người dùng được bàn tiếp ở Chương 10 ([C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md)).
**Ý chính:** **Đánh giá là trở ngại lớn nhất khi đưa ứng dụng AI vào thực tế, vì mô hình nền tảng càng giỏi thì càng khó chấm, đầu ra mở không có một đáp án đúng duy nhất, mô hình là hộp đen và benchmark công khai bão hoà nhanh; do đó cần đầu tư vào đánh giá tự động có hệ thống, kết hợp đánh giá chính xác (exact) với đánh giá chủ quan (AI làm giám khảo, so sánh theo cặp) và hiểu rõ giới hạn của từng loại.** Chương mở bằng các thất bại có thật (người tự tử sau khi chatbot khuyến khích, luật sư nộp chứng cứ do AI bịa, Air Canada bị buộc bồi thường vì chatbot trả lời sai) và các con số cho thấy đánh giá bị đầu tư thiếu: số bài báo về đánh giá LLM tăng từ khoảng 2 lên 33 bài mỗi tháng trong nửa đầu 2023, nhưng trong 1.000 kho mã AI nổi tiếng nhất trên GitHub chỉ có khoảng 40 kho công cụ đánh giá, so với khoảng 120 kho cho mô hình hoá và huấn luyện. Phần độ đo ngôn ngữ giải thích entropy (số bit trung bình mỗi token mang), cross entropy H(P, Q) = H(P) + D_KL(P‖Q), bits-per-character (ví dụ 6 bit/token chia 2 ký tự mỗi token bằng 3 BPC), bits-per-byte (3 chia 7/8 bằng 3,43 BPB, tức nén văn bản còn dưới một nửa) và perplexity = 2^H (cross entropy 2 bit cho perplexity 4); mô hình GPT-2 lớn hơn có perplexity thấp hơn (LAMBADA: 35,13 ở 117 triệu tham số xuống 8,63 ở 1,5 tỷ). Perplexity dùng được để phát hiện nhiễm dữ liệu benchmark, khử trùng lặp và phát hiện văn bản bất thường, nhưng kém tin cậy sau post-training và lượng tử hoá. Đánh giá chính xác gồm functional correctness (pass@k: 10 bài, giải được 5 với k = 3 thì pass@3 bằng 50%) và độ tương đồng với dữ liệu tham chiếu (khớp chính xác, tương đồng từ vựng như edit distance, BLEU, ROUGE, và tương đồng ngữ nghĩa bằng cosine giữa các embedding có 100–10.000 chiều). AI làm giám khảo nhanh, rẻ, không cần tham chiếu (58% đánh giá trên nền tảng LangChain năm 2023; GPT-4 đồng ý với người 85%, cao hơn mức người đồng ý với nhau 81%), nhưng không nhất quán (65% lên 77,5% khi thêm ví dụ, chi phí GPT-4 tăng gấp bốn), tiêu chí không chuẩn hoá (cùng "faithfulness" mà MLflow chấm 1–5, Ragas chấm 0/1, LlamaIndex trả lời YES/NO), tốn chi phí và độ trễ, và có thiên lệch (tự thiên vị: GPT-4 tự ưu tiên thêm 10%, Claude-v1 25%; thiên vị vị trí đầu; thiên vị câu dài). Đánh giá so sánh xếp hạng mô hình từ các trận đấu cặp bằng thuật toán như Elo, Bradley–Terry, TrueSkill; nó khó bị gian lận và không bão hoà, nhưng tốn dữ liệu (57 mô hình tạo 1.596 cặp, 244.000 lượt so sánh chỉ được trung bình 153 lượt mỗi cặp), khó chuẩn hoá (180 trong 33.000 prompt của Chatbot Arena chỉ là "hello"/"hi") và chỉ cho biết mô hình nào tốt hơn chứ không cho biết tốt đến đâu.

> **Lưu ý:**
> - **"greatest common denominator" (trang PDF 254):** hàm `gcd` tính *ước chung lớn nhất* (greatest common divisor), không phải "mẫu số chung lớn nhất". gcd(15, 20) = 5 đúng với ước chung lớn nhất.
> - **Công thức cosine bị vỡ ngay trong sách (trang PDF 266):** sách in "fracA ⋅ B ||A||||B||" — lệnh LaTeX `\frac` không được dựng. Công thức đúng là (A · B) / (‖A‖ · ‖B‖).
> - **Hình 3-6 (kiến trúc CLIP) ghi nhãn sai:** vector đầu ra của bộ mã hoá ảnh được ghi "Text embedding (D_v)"; đúng ra là "Image embedding (D_v)".
> - **Chú thích Bảng 3-4:** "Different tools can have very difficult default prompts" — "difficult" là lỗi in của "different" (các công cụ có prompt mặc định *khác nhau*).
> - **Hình 3-2 và lời văn không khớp:** lời văn nói "hơn 50 kho" mã chuyên về đánh giá trong 1.000 kho AI phổ biến nhất (tính đến 5/2024), nhưng đường tích luỹ trên Hình 3-2 dừng ở khoảng 40 kho vào đầu 2024; Hình 3-3 cũng cho cột "Evals" khoảng 40. Có thể hình được vẽ trước khi bổ sung các kho tìm qua lời kêu gọi cộng đồng (chú thích 5); sách không giải thích.
> - **Chú thích 4:** tên nhà toán học là Terence Tao (sách viết "Terrence"); mô hình ra tháng 9/2024 có tên chính thức là "o1" (o1-preview), không phải "GPT-o1".
> - **Trích dẫn "Valmeekamet et al., 2023" (trang PDF 292):** lỗi dính chữ của "Valmeekam et al.".
> - **Lớp chữ hỏng phải đọc từ ảnh:** công thức perplexity của một chuỗi (trang PDF 252) bị vỡ ký tự ("x2,â ¦,xn" là "x₂, …, xₙ"); câu "it has to choose among 2 = 4 possible options" (trang PDF 247) mất số mũ, đúng là 2² = 4; Bảng 3-1 bị cắt bên phải trong bản PDF, chỉ còn đọc được bốn cột (LAMBADA PPL, LAMBADA ACC, CBT-CN ACC, CBT-NE ACC); đoạn code HumanEval (trang PDF 255–256) và Bảng 3-6 cũng bị cắt mép phải (cột tỷ lệ thắng "A >> B" chỉ còn tiêu đề "A >>"). Bản tổng hợp dựng lại các dòng assert của HumanEval theo hiểu biết của người tổng hợp về bài HumanEval/0 và đã chạy thử để kiểm tra mọi kết quả kỳ vọng đều đúng.
> - **Bảng 3-1 không hoàn toàn đơn điệu:** chú thích bảng nói mô hình lớn hơn "luôn" cho perplexity thấp hơn — đúng với cột perplexity LAMBADA, nhưng ở cột độ chính xác CBT-CN, mô hình 1542M (93,30) thấp hơn mô hình 762M (93,45) một chút.
> - **Ví dụ tương đồng từ vựng (trang PDF 261):** con số "3 trên 5 từ" của câu B là tỷ lệ từ của *câu tham chiếu* xuất hiện trong câu sinh ra (kiểu *recall*, như ROUGE-1). Nếu tính theo tỷ lệ từ của câu sinh ra có trong tham chiếu (kiểu *precision*, như BLEU) thì câu B chỉ được 3/7 ≈ 43% (người tổng hợp tính). Sách gọi bigram là "a set of two tokens"; chính xác hơn là một *dãy* hai token liên tiếp (thứ tự có ý nghĩa).
> - **Công thức BLEU, ROUGE, Elo và Bradley–Terry không có trong sách:** sách chỉ nêu tên các độ đo và thuật toán này. Công thức, cách tính và các ví dụ số trong bản tổng hợp (BLEU-2, ROUGE, Elo, Bradley–Terry cho Bảng 3-6, ước lượng pass@k không chệch) là phần bổ sung của người tổng hợp, được ghi rõ ở từng chỗ.
> - **Bảng 3-6 có vòng lặp không bắc cầu (nhận xét của người tổng hợp):** mô hình 1 thắng mô hình 2 (90%), mô hình 2 thắng mô hình 5 (80%), nhưng mô hình 5 thắng mô hình 1 (90%); tương tự 1 thắng 2, 2 thắng 3 (60%), 3 thắng 1 (60%). Vì thế không thứ hạng nào khớp hết dữ liệu; đây có lẽ chính là ý của tác giả khi nói "không rõ nên xếp hạng năm mô hình này thế nào".
> - **Thuật ngữ:** "AI as a judge" dịch là "AI làm giám khảo", "AI judge" là "giám khảo AI"; "exact evaluation" là "đánh giá chính xác" (theo nghĩa *không mơ hồ*, chứ không phải *đúng*), "subjective evaluation" là "đánh giá chủ quan"; "pointwise evaluation" là "đánh giá từng điểm (độc lập)", "comparative evaluation" là "đánh giá so sánh"; "reference data / ground truth" là "dữ liệu tham chiếu / đáp án chuẩn"; "win rate" là "tỷ lệ thắng". Các thuật ngữ phổ biến (token, embedding, prompt, benchmark, perplexity, cross entropy, pass@k, guardrail, logprob, finetuning, post-training) giữ tiếng Anh.
> - **Những gì đã thay đổi sau 2024 (theo hiểu biết của người tổng hợp):** LMSYS Chatbot Arena đổi tên thành LMArena và tách thành công ty riêng (2025); một nghiên cứu năm 2025 ("The Leaderboard Illusion") chỉ ra các nhà cung cấp lớn được thử nhiều biến thể riêng trước khi công bố điểm, xác nhận lo ngại về gian lận bảng xếp hạng mà sách nêu ở chú thích 24. HumanEval và MMLU đã gần bão hoà với các mô hình hàng đầu; các benchmark khó hơn như GPQA, SWE-bench Verified, Humanity's Last Exam được dùng thay. Cohere đã ra Embed v4 sau các mô hình Embed v3 trong Bảng 3-2.

## Sơ đồ

### Phần mở đầu Chương 3 — vì sao phải đánh giá (Chapter 3 introduction, trang PDF 232–234)

```text
       AI được dùng càng nhiều thì càng nhiều cơ hội thất bại nghiêm trọng
       · một người tự tử sau khi được chatbot khuyến khích
       · luật sư nộp chứng cứ giả do AI bịa ra (hallucination)
       · Air Canada bị buộc bồi thường vì chatbot cho khách thông tin sai
                                │
                                ▼
       Trở ngại lớn nhất khi đưa ứng dụng AI vào thực tế là ĐÁNH GIÁ
       · với một số ứng dụng, đánh giá chiếm phần lớn công sức phát triển
       · Greg Brockman (12/2023): "evals are surprisingly often all you need"
                                │
                                ▼
       Đánh giá phải gắn với cả hệ thống: tìm chỗ hệ thống dễ hỏng rồi
       thiết kế đánh giá quanh các chỗ đó (có khi phải sửa hệ thống để
       nhìn thấy lỗi)
                                │
                                ▼
       Nhiều người chỉ dựa vào truyền miệng (6/70 người ra quyết định trong
       khảo sát a16z 2023) hay "nhìn qua kết quả" (vibe check)
       khiến rủi ro cao hơn, lặp chậm hơn; cần đánh giá có hệ thống
                                │
                                ▼
       Nội dung chương: độ đo mô hình ngôn ngữ → đánh giá chính xác →
       AI làm giám khảo (đánh giá chủ quan) → xếp hạng bằng so sánh
       · trọng tâm: đánh giá TỰ ĐỘNG; Chương 4 dùng các phương pháp này
         để chọn mô hình và dựng quy trình đánh giá
```

### Mục "Challenges of Evaluating Foundation Models" — năm lý do mô hình nền tảng khó đánh giá (trang PDF 234–240)

```text
  ┌──────────────────────────────────────────────────────────────────┐
  │ 1. Mô hình càng thông minh càng khó chấm                         │
  │    · ai cũng thấy bài toán lớp 1 sai; ít người chấm được lời     │
  │      giải toán cấp tiến sĩ                                       │
  │    · tóm tắt mạch lạc mà sai: phải đọc cả cuốn sách mới biết     │
  │    · phải kiểm chứng sự thật, suy luận, cần chuyên môn           │
  ├──────────────────────────────────────────────────────────────────┤
  │ 2. Đầu ra MỞ: không thể liệt kê hết các đáp án đúng để so        │
  │    (khác với phân loại: chỉ có các lớp định trước)               │
  ├──────────────────────────────────────────────────────────────────┤
  │ 3. Mô hình là HỘP ĐEN: không biết kiến trúc, dữ liệu, cách huấn  │
  │    luyện; chỉ quan sát được đầu ra                               │
  ├──────────────────────────────────────────────────────────────────┤
  │ 4. Benchmark công khai BÃO HOÀ nhanh                             │
  │    · GLUE (2018) bão hoà sau 1 năm, thay bằng SuperGLUE (2019)   │
  │    · NaturalInstructions (2021) thay bằng                        │
  │      Super-NaturalInstructions (2022)                            │
  │    · MMLU (2020) phần lớn thay bằng MMLU-Pro (2024)              │
  ├──────────────────────────────────────────────────────────────────┤
  │ 5. Phạm vi mở rộng: không chỉ đo việc đã biết mà còn phải KHÁM   │
  │    PHÁ việc mới mô hình làm được, kể cả việc vượt khả năng người │
  └──────────────────────────────────────────────────────────────────┘
                                │
                                ▼
       Tin tốt: nhiều phương pháp mới
       · số bài báo về đánh giá LLM: 0 (2020), 3 (2021), 3 (2022), rồi
         theo tháng năm 2023: 2 → 7 → 12 → 15 → 22 → 33 (6/2023 trở đi)
       · kho mã đánh giá trong top 1.000 kho AI trên GitHub tăng theo
         hàm mũ: khoảng 1 (2017) → 5 (2020) → 10 (2021) → khoảng 40 (2024)
                                │
                                ▼
       Tin xấu: đánh giá vẫn bị đầu tư thiếu
       · Balduzzi và cộng sự (DeepMind): kết quả thí nghiệm hầu như chỉ
         dùng để cải thiện thuật toán, hiếm khi để cải thiện đánh giá
       · Anthropic kêu gọi chính phủ tài trợ cho phương pháp đánh giá
       · số kho công cụ theo hạng mục: mô hình hoá & huấn luyện ~120,
         điều phối AI ~78, tối ưu suy luận ~49, prompt engineering ~47,
         giao diện AI ~45, agent ~44, đánh giá ~40 (ít nhất)
       · hạ tầng thiếu nên nhiều người chỉ nhìn qua kết quả hoặc dùng
         vài prompt "ruột" chọn theo kinh nghiệm cá nhân
```

### Mục "Understanding Language Modeling Metrics" — bốn độ đo liên quan nhau (trang PDF 240–242)

```text
       Mô hình nền tảng tiến hoá từ mô hình ngôn ngữ; hiệu năng của
       thành phần mô hình ngôn ngữ tương quan tốt với hiệu năng ứng dụng
       (Liu và cộng sự, 2023) — tương quan mạnh nhưng không giải thích hết
                                │
                                ▼
       Từ Shannon (1951, "Prediction and Entropy of Printed English"),
       độ đo dùng để phát triển mô hình ngôn ngữ ít thay đổi
       ┌───────────────┬───────────────┬────────────────┬──────────────┐
       │ cross entropy │ perplexity    │ bits-per-      │ bits-per-    │
       │               │ (PPL)         │ character (BPC)│ byte (BPB)   │
       └───────────────┴───────────────┴────────────────┴──────────────┘
       · biết một độ đo (và vài thông tin phụ) thì tính được ba độ đo kia
       · dùng được cho mọi mô hình sinh chuỗi token, kể cả token không
         phải chữ
                                │
                                ▼
       Mô hình ngôn ngữ học PHÂN PHỐI của dữ liệu huấn luyện: "I like
       drinking __" thì "tea" có xác suất cao hơn "charcoal"
       · học càng tốt, dự đoán token kế tiếp càng tốt, cross entropy
         huấn luyện càng thấp
       · dữ liệu của bạn càng gần dữ liệu huấn luyện, mô hình càng tốt
```

### Mục "Entropy" — thông tin trung bình mỗi token (trang PDF 242–243)

```text
       ENTROPY: lượng thông tin trung bình một token mang; entropy càng
       cao, mỗi token mang càng nhiều thông tin và cần càng nhiều bit
                                │
       ┌────────────────────────┴────────────────────────┐
       ▼                                                 ▼
  Ngôn ngữ (a): 2 token                         Ngôn ngữ (b): 4 token
  "nửa trên" / "nửa dưới"                       trên-trái, trên-phải,
  của một hình vuông                            dưới-trái, dưới-phải
  cần 1 bit; entropy = 1                        cần 2 bit; entropy = 2
       └────────────────────────┬────────────────────────┘
                                ▼
       Trực giác: entropy đo độ khó đoán điều tiếp theo
       · entropy thấp: ngôn ngữ dễ đoán (chỉ phải chọn giữa 2 thay vì 4)
       · nếu đoán trúng hoàn toàn điều tôi sắp nói, lời tôi không mang
         thông tin mới
       · công thức (người tổng hợp bổ sung): H(P) = −Σ P(x)·log₂P(x)
```

### Mục "Cross Entropy" — độ khó dự đoán của mô hình trên một tập dữ liệu (trang PDF 244–245)

```text
       Cross entropy của mô hình trên tập dữ liệu phụ thuộc hai yếu tố:
       1. độ dễ đoán của dữ liệu: entropy H(P) của phân phối thật P
       2. độ lệch giữa phân phối mô hình học được Q và P: D_KL(P‖Q)
                                │
                                ▼
       ┌──────────────────────────────────────────────┐
       │   H(P, Q) = H(P) + D_KL(P‖Q)                 │
       └──────────────────────────────────────────────┘
       · không đối xứng: H(P, Q) khác H(Q, P)
       · huấn luyện nhằm cực tiểu hoá H(P, Q)
       · học hoàn hảo: D_KL = 0 và H(P, Q) = H(P)
       · cross entropy của mô hình là ước lượng của nó cho entropy của
         dữ liệu huấn luyện
       · ví dụ của người tổng hợp: P = (1/2, 1/4, 1/8, 1/8), Q đều 1/4:
         H(P) = 1,75; H(P, Q) = 2,00; D_KL = 0,25; H(Q, P) = 2,25 bit
```

### Mục "Bits-per-Character and Bits-per-Byte" — so sánh mô hình có tokenizer khác nhau (trang PDF 245–246)

```text
       Đơn vị của entropy/cross entropy là BIT: cross entropy 6 bit
       nghĩa là mô hình cần 6 bit cho mỗi token
                                │
                                ▼
       Số bit/token không so được giữa các mô hình (token có thể là từ,
       có thể là ký tự), nên dùng BITS-PER-CHARACTER
       · 6 bit/token, mỗi token trung bình 2 ký tự: BPC = 6 / 2 = 3
                                │
                                ▼
       BPC lại phụ thuộc bảng mã ký tự (ASCII 7 bit; UTF-8 từ 8 đến 32
       bit), nên dùng BITS-PER-BYTE (số bit biểu diễn 1 byte dữ liệu gốc)
       · BPC = 3, mỗi ký tự 7 bit (bằng 7/8 byte): BPB = 3 / (7/8) = 3,43
                                │
                                ▼
       Cross entropy cho biết khả năng NÉN: BPB 3,43 nghĩa là 8 bit gốc
       được biểu diễn bằng 3,43 bit (42,9%), nén văn bản còn dưới một nửa
```

### Mục "Perplexity" — hàm mũ của cross entropy (trang PDF 246–247)

```text
       PPL(P) = 2^H(P)          PPL(P, Q) = 2^H(P, Q)     (đơn vị bit)
       PPL(P, Q) = e^H(P, Q)                               (đơn vị nat)
                                │
                                ▼
       Cross entropy đo độ KHÓ dự đoán; perplexity đo mức KHÔNG CHẮC
       chắn: số lựa chọn "hiệu dụng" cho token kế tiếp
       · mô hình học hoàn hảo 4 token vị trí: cross entropy 2 bit,
         perplexity 2² = 4 (phải chọn giữa 4 khả năng)
                                │
                                ▼
       TensorFlow, PyTorch dùng NAT (logarit tự nhiên, cơ số e) vì đạo
       hàm của ln x là 1/x, toán gọn hơn
       · 2 bit = 2 × ln 2 = 1,386 nat; e^1,386 = 4: perplexity không đổi
       · vì lẫn lộn bit và nat, nhiều người báo cáo perplexity thay cho
         cross entropy
```

### Mục "Perplexity Interpretation and Use Cases" — đọc và dùng perplexity (trang PDF 248–252)

```text
       Cả bốn độ đo càng thấp thì mô hình dự đoán văn bản càng chính
       xác; sách dùng perplexity làm độ đo mặc định
       Perplexity "tốt" là bao nhiêu tùy dữ liệu và cách tính:
       ┌──────────────────────────────────────────────────────────────┐
       │ · dữ liệu càng có cấu trúc, perplexity càng thấp (HTML: thấy │
       │   <head> thì biết sẽ có </head>)                             │
       │ · bộ từ vựng càng lớn, perplexity càng cao (sách thiếu nhi   │
       │   thấp hơn Chiến tranh và Hoà bình; theo ký tự thấp hơn theo │
       │   từ)                                                        │
       │ · context càng dài, perplexity càng thấp (Shannon 1951: tới  │
       │   10 token trước; nay 500–10.000 token, tới giới hạn context)│
       └──────────────────────────────────────────────────────────────┘
       · perplexity 3: nếu mọi token đồng khả năng, mô hình đoán đúng
         1 lần trong 3, giữa hàng chục nghìn đến hàng trăm nghìn token
                                │
                                ▼
       Công dụng
       · đại diện cho năng lực: GPT-2 lớn hơn có perplexity thấp hơn
         (LAMBADA: 35,13 → 15,60 → 10,87 → 8,63 khi đi từ 117M đến
         1542M tham số; SOTA trước đó 99,8)
       · CẢNH BÁO: kém tin cậy sau post-training (SFT, RLHF) vì
         perplexity thường TĂNG ("post-training làm sụp entropy"); lượng
         tử hoá cũng làm perplexity đổi khó lường
       · phát hiện NHIỄM DỮ LIỆU: perplexity thấp trên benchmark nghĩa là
         có thể mô hình đã học thuộc benchmark
       · KHỬ TRÙNG LẶP: chỉ thêm dữ liệu mới nếu perplexity của nó cao
       · phát hiện VĂN BẢN BẤT THƯỜNG: "my dog teaches quantum physics in
         his free time", "home cat go eye" có perplexity cao
                                │
                                ▼
       Khung: tính perplexity của một chuỗi [x₁, …, xₙ]
       PPL = P(x₁, …, xₙ)^(−1/n) = (∏ᵢ 1 / P(xᵢ | x₁, …, xᵢ₋₁))^(1/n)
       · cần logprob của từng token; nhiều mô hình thương mại không cho
```

### Mục "Exact Evaluation" — đánh giá chính xác và đánh giá chủ quan (trang PDF 252–253)

```text
  ĐÁNH GIÁ CHÍNH XÁC (exact)              ĐÁNH GIÁ CHỦ QUAN (subjective)
  phán xét không mơ hồ                    phụ thuộc người chấm
  · trắc nghiệm đáp án A, chọn B: sai     · chấm bài luận: người khác cho
                                            điểm khác; cùng người chấm
                                            hai lần cũng có thể khác
                                          · AI làm giám khảo thuộc loại này
       └────────────────────┬─────────────────────┘
                            ▼
       Hai cách cho điểm chính xác với đầu ra MỞ:
       1. functional correctness   2. độ tương đồng với dữ liệu tham chiếu
       · tác vụ đóng (phân loại ý định, chấm điểm) vẫn phổ biến nhưng đã
         được hiểu rõ, nên chương không bàn
```

### Mục "Functional Correctness" — hệ thống có làm đúng chức năng không (trang PDF 253–256)

```text
       Đánh giá theo việc hệ thống có thực hiện đúng chức năng mong muốn
       · tạo website có đúng yêu cầu? đặt bàn nhà hàng có thành công?
       · là độ đo TỐI HẬU, nhưng thường khó đo và khó tự động hoá
                                │
                                ▼
       Sinh code: tự động hoá được (execution accuracy)
       · gcd(15, 20) phải trả về 5; chạy code trong trình thông dịch Python
       · unit test là thực hành chuẩn từ lâu; LeetCode, HackerRank chấm
         bài theo cách này
       · benchmark: HumanEval (OpenAI), MBPP (Google); text-to-SQL:
         Spider, BIRD-SQL, WikiSQL
                                │
                                ▼
       Mỗi bài có bộ test (ví dụ HumanEval: has_close_elements, 7 assert)
       PASS@k: sinh k mẫu code cho mỗi bài; bài được giải nếu ÍT NHẤT
       một mẫu qua hết test; điểm = số bài giải được / tổng số bài
       · 10 bài, giải 5 với k = 3: pass@3 = 50%
       · kỳ vọng pass@1 ≤ pass@3 ≤ pass@10
                                │
                                ▼
       Tác vụ có mục tiêu đo được: bot chơi Tetris (điểm số), lập lịch
       tải để tiết kiệm năng lượng (năng lượng tiết kiệm được)
       · khó: AI thường chỉ làm một phần lời giải, mà chấm một phần có
         thể khó hơn chấm kết cục (chấm một nước cờ khó hơn chấm thắng/thua)
```

### Mục "Similarity Measurements Against Reference Data" — so với dữ liệu tham chiếu (trang PDF 257–259)

```text
       Không chấm được bằng functional correctness thì so đầu ra với dữ
       liệu tham chiếu (dịch Pháp–Anh: so với bản dịch đúng)
       · dữ liệu dạng (đầu vào, các câu trả lời tham chiếu); một đầu vào
         có thể có nhiều tham chiếu (còn gọi ground truth, canonical)
       · độ đo cần tham chiếu: reference-based; không cần: reference-free
       · nghẽn ở tốc độ và lượng dữ liệu tham chiếu; người tạo thì đắt,
         nên ngày càng dùng AI tạo rồi người duyệt
                                │
                                ▼
       Bốn cách đo tương đồng giữa hai văn bản mở:
       ┌─────────────────────────┬──────────────────────────────────┐
       │ 1. người/AI phán xét    │ (AI làm giám khảo: mục sau)      │
       │ 2. khớp chính xác       │ nhị phân: khớp hoặc không        │
       │ 3. tương đồng từ vựng   │ thang trượt, ví dụ 0 đến 1       │
       │ 4. tương đồng ngữ nghĩa │ thang trượt, ví dụ −1 đến 1      │
       └─────────────────────────┴──────────────────────────────────┘
       · độ đo thiết kế tay (2–4) vẫn phổ biến vì tính chính xác
       · công dụng khác: truy xuất/tìm kiếm, xếp hạng, gom cụm, phát
         hiện bất thường, khử trùng lặp
```

### Mục "Exact match" — khớp chính xác (trang PDF 259–261)

```text
       Hợp với câu trả lời ngắn, chính xác: "2 + 3 bằng mấy?", "Người phụ
       nữ đầu tiên đoạt giải Nobel?", "Số dư tài khoản hiện tại?",
       "Paris với Pháp như ___ với Anh"
                                │
                                ▼
       Biến thể: chấp nhận đầu ra CHỨA đáp án ("The answer is 5")
       · rủi ro: "Anne Frank sinh năm nào?" (12/6/1929); đầu ra
         "September 12, 1929" chứa 1929 nhưng sai sự thật
                                │
                                ▼
       Ngoài tác vụ đơn giản, khớp chính xác hiếm khi dùng được:
       "Comment ça va?" có các tham chiếu "How are you?", "How is
       everything?", "How are you doing?"; mô hình trả "How is it going?"
       bị chấm sai dù đúng; vì vậy cần tương đồng từ vựng/ngữ nghĩa
```

### Mục "Lexical similarity" — hai văn bản trông giống nhau đến đâu (trang PDF 261–264)

```text
       Tách văn bản thành token rồi đếm phần chồng lấp
       Tham chiếu: "My cats scare the mice"
       · A "My cats eat the mice": chứa 4/5 từ tham chiếu (80%)
       · B "Cats and mice fight all the time": chứa 3/5 (60%)
       Vậy A được coi là giống tham chiếu hơn
                                │
       ┌────────────────────────┴────────────────────────┐
       ▼                                                 ▼
  FUZZY MATCHING (edit distance):                N-GRAM: so dãy n token
  số phép sửa để biến chuỗi này                  · tham chiếu có 4 bigram:
  thành chuỗi kia                                  my cats, cats scare,
  · xoá: brad → bad                                scare the, the mice
  · chèn: bad → bard                             · A khớp 2/4 bigram; B 0/4
  · thay: bad → bed                                (người tổng hợp tính)
  · (tùy công cụ) đảo hai chữ:
    mats → mast
  "bad" cách "bard" 1, cách "cash" 3
       └────────────────────────┬────────────────────────┘
                                ▼
       Độ đo phổ biến: BLEU, ROUGE, METEOR++, TER, CIDEr (khác nhau ở
       cách tính chồng lấp); benchmark dùng: WMT, COCO Captions, GEMv2
                                │
                                ▼
       Nhược điểm
       · cần bộ tham chiếu đầy đủ: Fuyu (Adept) mô tả ảnh "A nighttime
         view of Big Ben and the Houses of Parliament" đúng nhưng CIDEr
         chỉ 0,4 vì 5 câu tham chiếu không nhắc Big Ben hay Parliament
       · tham chiếu có thể sai: WMT 2023 Metrics thấy nhiều bản dịch tham
         chiếu kém; độ đo không cần tham chiếu cạnh tranh ngang ngửa
       · điểm cao không có nghĩa là tốt: trên HumanEval, BLEU của lời giải
         sai và đúng tương tự nhau (Chen và cộng sự, 2021)
```

### Mục "Semantic similarity" — hai văn bản có cùng nghĩa không (trang PDF 264–266)

```text
       Từ vựng khác mà nghĩa gần: "What's up?" và "How are you?"
       Từ vựng gần mà nghĩa khác: "Let's eat, grandma" và "Let's eat grandma"
                                │
                                ▼
       Biến văn bản thành EMBEDDING (vector số), ví dụ "the cat sits on
       a mat" thành [0,11; 0,02; 0,54]; còn gọi là embedding similarity
                                │
                                ▼
       COSINE: cos(A, B) = (A · B) / (‖A‖ · ‖B‖)
       · A · B: tích vô hướng; ‖A‖: chuẩn Euclid (L2)
       · ‖[0,11; 0,02; 0,54]‖ = √(0,11² + 0,02² + 0,54²) = √0,3041 ≈ 0,5515
       · giống hệt: 1; ngược hẳn: −1
                                │
                                ▼
       Độ đo: BERTScore (embedding từ BERT), MoverScore (hỗn hợp thuật toán)
       · ưu: không cần bộ tham chiếu đầy đủ như tương đồng từ vựng
       · nhược: phụ thuộc chất lượng embedding; tốn tính toán và thời gian
       · CẢNH BÁO: có thể coi là chủ quan vì thuật toán embedding khác cho
         embedding khác; nhưng với hai embedding cho trước, điểm là chính xác
```

### Mục "Introduction to Embedding" — embedding là gì (trang PDF 267–271)

```text
       EMBEDDING: biểu diễn số nhằm nắm được Ý NGHĨA của dữ liệu gốc;
       là một vector, thường 100–10.000 phần tử (vẫn thấp chiều hơn nhiều
       so với dữ liệu thô)
                                │
                                ▼
       Mô hình chuyên tạo embedding: BERT, CLIP, Sentence Transformers
       (mã nguồn mở), API độc quyền; word2vec, GloVe cho embedding từ
       ┌─────────────────────────┬───────────────────────────────────┐
       │ BERT                    │ base 768; large 1024              │
       │ CLIP (OpenAI)           │ ảnh 512; văn bản 512              │
       │ OpenAI Embeddings API   │ 3-small 1536; 3-large 3072        │
       │ Cohere Embed v3         │ english-v3.0 1024; light 384      │
       └─────────────────────────┴───────────────────────────────────┘
       · GPT, Llama cũng có tầng embedding; lấy từ tầng giữa được nhưng
         thường kém mô hình embedding chuyên dụng
                                │
                                ▼
       Embedding TỐT: văn bản giống nhau có embedding gần nhau
       · "the cat sits on a mat" gần "the dog plays on the grass" hơn
         "AI research is super fun"
       · đo theo hữu ích cho tác vụ: phân loại, mô hình chủ đề, gợi ý,
         RAG; benchmark MTEB
       · mọi dữ liệu đều có embedding: sản phẩm (Criteo, Coveo), ảnh, đồ
         thị, truy vấn, người dùng (Pinterest)
                                │
                                ▼
       EMBEDDING ĐA PHƯƠNG THỨC (joint embedding)
       · CLIP: văn bản và ảnh; ULIP: văn bản, ảnh, đám mây điểm 3D;
         ImageBind: sáu phương thức
       · CLIP huấn luyện trên cặp (ảnh, văn bản): bộ mã hoá văn bản và bộ
         mã hoá ảnh tạo hai embedding, nhân với ma trận chiếu để đưa vào
         không gian chung, tính cosine; mục tiêu kéo ảnh gần văn bản của nó
       · ảnh người câu cá gần "a fisherman" hơn "fashion show"; cho phép
         tìm ảnh bằng văn bản
```

### Mục "AI as a Judge" và "Why AI as a Judge?" — dùng AI chấm AI (trang PDF 271–274)

```text
       Đánh giá đầu ra mở khó nên nhiều đội quay về người chấm
       Câu hỏi: AI có tự động hoá được việc chấm? Cách dùng AI chấm AI
       gọi là AI AS A JUDGE (LLM as a judge)
       · ý tưởng có từ lâu (tác giả trình bày MEWR ở NeurIPS 2017), khả thi
         từ khoảng 2020 với GPT-3
       · 58% lượt đánh giá trên nền tảng LangChain (2023) do giám khảo AI
                                │
                                ▼
       Ưu điểm
       · nhanh, dễ dùng, tương đối rẻ; KHÔNG cần dữ liệu tham chiếu nên
         dùng được trong production
       · chấm theo tiêu chí bất kỳ: đúng, lặp, độc hại, lành mạnh,
         hallucination…
       · tương quan cao với người: MT-Bench, GPT-4 đồng ý với người 85%,
         người đồng ý với nhau 81% (Zheng 2023); AlpacaEval tương quan
         0,98 với bảng xếp hạng Chatbot Arena (do người chấm)
       · giải thích được quyết định (GPT-4 cho một đoạn văn 4,5/5, nêu
         điểm mạnh: rõ, có bằng chứng, gọn; cần cải thiện: chuyển ý)
       · với một số ứng dụng, là lựa chọn tự động DUY NHẤT
```

### Mục "How to Use AI as a Judge" — ba cách dùng và cách viết prompt giám khảo (trang PDF 274–281)

```text
  ┌───────────────────────┬────────────────────────┬──────────────────────┐
  │ 1. Chấm MỘT câu trả   │ 2. So câu trả lời với  │ 3. So HAI câu trả    │
  │ lời theo câu hỏi      │ THAM CHIẾU             │ lời                  │
  │ điểm 1 (rất tệ) đến   │ đầu ra True/False      │ đầu ra A hoặc B      │
  │ 5 (rất tốt)           │ (thay độ đo thiết kế   │ (dữ liệu sở thích,   │
  │                       │ tay)                   │ test-time compute,   │
  │                       │                        │ xếp hạng so sánh)    │
  └───────────────────────┴────────────────────────┴──────────────────────┘
                                │
                                ▼
       Tiêu chí tuỳ ý: "nghe có giống Gandalf nói không?", "từ 1 đến 5,
       sản phẩm trong ảnh đáng tin đến đâu?"
       Tiêu chí có sẵn (9/2024): Azure AI Studio, MLflow, LangChain, Ragas
       · KHÔNG chuẩn hoá: "relevance" của Azure khác "relevance" của MLflow
                                │
                                ▼
       Prompt giám khảo cần nói rõ:
       1. nhiệm vụ (ví dụ đánh giá độ liên quan giữa câu trả lời và câu hỏi)
       2. tiêu chí (càng chi tiết càng tốt)
       3. hệ thống điểm: phân loại (tốt/xấu) · số rời rạc (1–5) · số liên
          tục (0–1)
       · MẸO: phân loại tốt hơn chấm số; rời rạc tốt hơn liên tục; thang
         càng rộng càng tệ; thường dùng 1–5; thêm ví dụ cho từng mức điểm
       · ví dụ: prompt "relevance" của Azure AI Studio (mâu thuẫn với đáp
         án chuẩn thì 1–2 điểm; ví dụ "bầu trời có màu xanh không?")
                                │
                                ▼
       GIÁM KHẢO AI gồm mô hình (GPT-4) và mẫu prompt theo tiêu chí
       · đổi mô hình, prompt hay tham số lấy mẫu là thành giám khảo KHÁC
```

### Mục "Limitations of AI as a Judge" — bốn giới hạn (trang PDF 281–290)

```text
       Hoài nghi: AI chấm AI nghe như lập luận vòng; xác suất nên thiếu
       tin cậy; tốn chi phí và độ trễ; một số đội coi là phương án cuối
                                │
  ┌─────────────────────────────┼──────────────────────────────────┐
  ▼                             ▼                                  ▼
KHÔNG NHẤT QUÁN            TIÊU CHÍ MƠ HỒ                    CHI PHÍ, ĐỘ TRỄ
cùng đầu vào, khác prompt  · "faithfulness": MLflow 1–5,     · GPT-4 sinh + GPT-4
hoặc chạy lại: điểm khác     Ragas 0/1, LlamaIndex YES/NO;     chấm: gấp đôi chi phí
· ví dụ trong prompt: GPT-4  ba công cụ chấm cùng câu 3, 1,  · ba tiêu chí: gấp bốn
  nhất quán 65% lên 77,5%    NO thì không biết lấy điểm nào    số lượt gọi API
· nhất quán chưa chắc      · giám khảo đổi theo thời gian:   · giảm: giám khảo yếu
  chính xác; chi phí GPT-4   "coherence" 90% lên 92% có        hơn, spot-check
  tăng gấp bốn               thể do prompt giám khảo đổi       (lấy mẫu)
                           · MẸO: không tin giám khảo nào    · chấm trước khi trả
                             không xem được mô hình và         lời: giảm rủi ro,
                             prompt                            tăng độ trễ
  └─────────────────────────────┼──────────────────────────────────┘
                                ▼
       THIÊN LỆCH
       · tự thiên vị (self-bias): GPT-4 tự ưu tiên +10% tỷ lệ thắng,
         Claude-v1 +25% (Zheng 2023)
       · thiên vị vị trí đầu (first-position); người thì thiên vị câu
         cuối (recency); giảm bằng đổi thứ tự, chạy lại
       · thiên vị độ dài: GPT-4, Claude-1 chọn câu ~100 từ có lỗi sự thật
         hơn câu ~50 từ đúng; dài gấp đôi thì gần như luôn thắng; GPT-4 ít
         bị hơn GPT-3.5; người cũng thích câu dài nhưng ít hơn nhiều
       · quyền riêng tư, sở hữu trí tuệ khi gửi dữ liệu cho mô hình độc quyền
                                │
                                ▼
       Kết luận: sẽ được dùng ngày càng nhiều, nhưng phải bổ sung bằng
       đánh giá chính xác và/hoặc đánh giá của người
```

### Mục "What Models Can Act as Judges?" — giám khảo mạnh hơn, yếu hơn hay chính nó (trang PDF 290–295)

```text
  ┌──────────────────────────┬──────────────────────────┬─────────────────────────┐
  │ GIÁM KHẢO MẠNH HƠN       │ TỰ ĐÁNH GIÁ              │ GIÁM KHẢO YẾU HƠN       │
  │ · người chấm thi nên giỏi│ (self-critique)          │ · chấm dễ hơn sáng tác: │
  │   hơn thí sinh           │ · nghe như gian lận vì   │   ai cũng chê được bài  │
  │ · tiết kiệm: mô hình rẻ  │   self-bias              │   hát                   │
  │   sinh câu trả lời, GPT-4│ · tốt cho kiểm tra hợp lý│ · Zheng 2023: mô hình   │
  │   chấm 1% số câu trả lời │ · giúp tự sửa: "10+3?"   │   mạnh tương quan với   │
  │ · nhanh: mô hình nhanh   │   trả 30, tự hỏi "đúng   │   người tốt hơn         │
  │   sinh, mô hình mạnh     │   không?", sửa thành 13  │ · hướng hứa hẹn: giám   │
  │   chấm chạy nền          │                          │   khảo NHỎ, CHUYÊN BIỆT │
  │ · vướng: mô hình mạnh    │                          │                         │
  │   nhất không có giám khảo│                          │                         │
  └──────────────────────────┴──────────────────────────┴─────────────────────────┘
                                │
                                ▼
       Ba loại giám khảo chuyên biệt
       · REWARD MODEL: nhận (prompt, câu trả lời), cho điểm; Cappy (Google 2023),
         360 triệu tham số, điểm 0–1
       · GIÁM KHẢO DỰA TRÊN THAM CHIẾU: BLEURT (điểm tương đồng, khoảng
         −2,5 đến 1,0); Prometheus (prompt, câu trả lời, tham chiếu, thang
         chấm), cho điểm 1–5, tham chiếu được coi là 5
       · PREFERENCE MODEL: nhận (prompt, câu trả lời 1, câu trả lời 2),
         cho biết câu nào được ưa hơn; PandaLM, JudgeLM
       · ví dụ PandaLM: Bloom và LLaMA giải thích "with a little give in
         them"; PandaLM chọn câu 2 vì rõ và gọn, kèm câu tham chiếu
```

### Mục "Ranking Models with Comparative Evaluation" — đánh giá độc lập và đánh giá so sánh (trang PDF 295–301)

```text
  ĐÁNH GIÁ TỪNG ĐIỂM (pointwise)           ĐÁNH GIÁ SO SÁNH (comparative)
  chấm từng mô hình riêng (ví dụ thang     cho các mô hình đấu nhau rồi suy
  Likert), xếp theo điểm                   ra thứ hạng từ kết quả
  · chấm từng vũ công                      · các vũ công nhảy cạnh nhau,
                                             giám khảo chọn người thích nhất
       └────────────────────┬─────────────────────┘
                            ▼
       Với chất lượng chủ quan, so sánh dễ hơn cho điểm (chọn bài hát hay
       hơn dễ hơn chấm điểm từng bài)
       · Anthropic dùng lần đầu năm 2021; LMSYS Chatbot Arena; ChatGPT
         thỉnh thoảng hỏi "bạn thích câu trả lời nào?"
       · mỗi lần so sánh là một TRẬN (match); cho phép hoà
                            │
                            ▼
       Không phải câu hỏi nào cũng trả lời bằng sở thích
       · "bức xạ điện thoại có gây u não?" không nên để người dùng bình
         chọn Có/Không
       · hỏi toán vì không biết đáp án mà bị bắt chọn: bực mình
       · chỉ hợp khi người bình chọn hiểu lĩnh vực (AI làm trợ lý cho việc
         người dùng biết làm)
       · khác A/B test: A/B test cho người dùng thấy MỘT mô hình mỗi lần
                            │
                            ▼
       Từ lịch sử trận đấu tính TỶ LỆ THẮNG của từng cặp
       · 2 mô hình: dễ; 5 mô hình với 10 cặp tỷ lệ thắng: không hiển nhiên
       · THUẬT TOÁN XẾP HẠNG (Elo, Bradley–Terry, TrueSkill) tính điểm
         mỗi mô hình rồi xếp theo điểm
       · Chatbot Arena chuyển từ Elo sang Bradley–Terry vì Elo nhạy với
         thứ tự người chấm và prompt
       · thứ hạng ĐÚNG: mô hình xếp trên thắng mô hình xếp dưới hơn 50%
         Vì vậy xếp hạng là bài toán DỰ ĐOÁN kết quả trận tương lai
```

### Mục "Challenges of Comparative Evaluation" — ba thách thức (trang PDF 302–308)

```text
  ┌────────────────────────────────────────────────────────────────────┐
  │ 1. NGHẼN KHẢ NĂNG MỞ RỘNG                                          │
  │ · số cặp tăng theo bình phương số mô hình: 57 mô hình có 1.596 cặp;│
  │   244.000 lượt so sánh (1/2024) chỉ ~153 lượt mỗi cặp              │
  │ · thuật toán giả định tính BẮC CẦU (A > B, B > C thì A > C), nhưng │
  │   sở thích người có thể không bắc cầu; mỗi cặp lại do người khác,  │
  │   prompt khác chấm                                                 │
  │ · mô hình mới phải đấu với mô hình cũ, có thể đổi thứ hạng cũ;     │
  │   mô hình nội bộ khó đưa lên bảng công khai                        │
  │ · giảm nghẽn: thuật toán ghép cặp chọn trận giảm bất định nhiều    │
  │   nhất, ngừng ghép cặp đã chắc kết quả                             │
  ├────────────────────────────────────────────────────────────────────┤
  │ 2. THIẾU CHUẨN HOÁ VÀ KIỂM SOÁT CHẤT LƯỢNG                         │
  │ · crowdsourcing (Chatbot Arena): nhiều tín hiệu, khó gian lận,     │
  │   nhưng không chuẩn "tốt hơn", tình nguyện viên không kiểm chứng   │
  │   sự thật                                                          │
  │ · người thích câu lịch sự, người thích không kiểm duyệt; có người  │
  │   cố tình chọn câu độc hại                                         │
  │ · prompt không sát thực tế: 180/33.000 prompt (0,55%) là "hello",  │
  │   "hi"; câu đố "X có 3 chị em gái…" hỏi 44 lần                     │
  │ · không hỗ trợ context phức tạp (RAG) nên không phản ánh hệ thống  │
  │   của bạn                                                          │
  │ · cách xử lý: LMSYS lọc prompt khó; Scale dùng người chấm được đào │
  │   tạo (đắt, ít); nhúng so sánh vào sản phẩm (người dùng có thể     │
  │   không đọc, bấm bừa); có đội dùng AI chấm                         │
  ├────────────────────────────────────────────────────────────────────┤
  │ 3. TỪ HIỆU NĂNG TƯƠNG ĐỐI ĐẾN HIỆU NĂNG TUYỆT ĐỐI                  │
  │ · "B tốt hơn A" có thể là: B tốt A tệ; cả hai tệ; cả hai tốt       │
  │ · A giải quyết 70% ticket hỗ trợ; B thắng A 51%: B giải được bao   │
  │   nhiêu? không biết; 1% tỷ lệ thắng có khi tạo khác biệt lớn, có   │
  │   khi không                                                        │
  │ · B đắt gấp đôi A: không làm được phân tích chi phí–lợi ích        │
  └────────────────────────────────────────────────────────────────────┘
```

### Mục "The Future of Comparative Evaluation" — vì sao đánh giá so sánh vẫn có tương lai (trang PDF 308–309)

```text
       · so sánh hai đầu ra dễ hơn cho điểm cụ thể; khi mô hình vượt
         người, người có thể không chấm điểm được nhưng vẫn phân biệt
         được (Llama 2: người vẫn cho phản hồi giá trị khi so hai câu
         trả lời vượt khả năng viết của người gán nhãn giỏi nhất)
       · nắm đúng thứ ta quan tâm: sở thích con người; không cần liên
         tục tạo benchmark mới; không bão hoà khi còn mô hình mới mạnh hơn
       · khó gian lận (không thể huấn luyện trên dữ liệu tham chiếu) nên
         nhiều người tin bảng so sánh công khai hơn các bảng khác
       · offline: bổ sung cho benchmark; online: bổ sung cho A/B test
```

### Mục "Summary" — tóm tắt chương (trang PDF 309–311)

```text
       Mô hình càng mạnh, rủi ro thất bại càng lớn, đánh giá càng quan
       trọng mà càng khó; người trong vòng lặp luôn có ích, nhưng chương
       tập trung vào đánh giá TỰ ĐỘNG
                                │
                                ▼
       Đầu tư cho đánh giá tụt sau đầu tư cho mô hình và ứng dụng
                                │
                                ▼
       Độ đo ngôn ngữ (perplexity, cross entropy) → đánh giá chính xác
       (functional correctness, độ tương đồng) → AI làm giám khảo (chủ
       quan: điểm phụ thuộc giám khảo, không so được giữa giám khảo, thay
       đổi theo thời gian nên không làm thước đo theo dõi được)
                                │
                                ▼
       Xếp hạng: độc lập hoặc so sánh; so sánh và post-training đều cần
       tín hiệu sở thích đắt đỏ, điều thúc đẩy việc phát triển preference
       model (mô hình dự đoán người dùng thích câu trả lời nào)
                                │
                                ▼
       Chương 4: dựng quy trình đánh giá đáng tin cho ứng dụng mở
```

## Ba câu hỏi chương này trả lời

1. **Vì sao đánh giá mô hình nền tảng khó hơn đánh giá mô hình học máy truyền thống, và vì sao cần đánh giá có hệ thống?** Vì mô hình càng giỏi càng khó chấm (lời giải toán cấp tiến sĩ, bản tóm tắt mạch lạc mà sai), đầu ra mở không thể liệt kê hết đáp án đúng, mô hình là hộp đen, benchmark bão hoà nhanh (GLUE bão hoà sau một năm) và đánh giá còn phải khám phá năng lực mới. Trong khi đó đánh giá bị đầu tư thiếu: chỉ khoảng 40 kho công cụ đánh giá so với khoảng 120 kho cho mô hình hoá và huấn luyện trong 1.000 kho AI phổ biến nhất; nhiều đội chỉ "nhìn qua" kết quả, điều đủ để khởi động dự án nhưng không đủ để lặp cải tiến.
2. **Có những phương pháp tự động nào để đánh giá đầu ra mở, và mỗi phương pháp đo cái gì?** Độ đo mô hình hoá ngôn ngữ (cross entropy, perplexity = 2^H, BPC, BPB) đo khả năng dự đoán token và đại diện cho năng lực chung (GPT-2 1,5 tỷ tham số có perplexity LAMBADA 8,63 so với 35,13 của bản 117 triệu). Đánh giá chính xác đo đầu ra có làm đúng chức năng không (pass@k) hoặc giống tham chiếu đến đâu (khớp chính xác; tương đồng từ vựng như 4/5 từ trùng; tương đồng ngữ nghĩa bằng cosine giữa embedding). AI làm giám khảo chấm theo tiêu chí tùy ý, không cần tham chiếu, đạt 85% đồng ý với người.
3. **Khi nào nên tin AI làm giám khảo và đánh giá so sánh, và giới hạn của chúng là gì?** AI làm giám khảo là một hệ thống (mô hình + prompt + tham số lấy mẫu), nên chỉ tin được khi thấy rõ mô hình và prompt; nó không nhất quán (65–77,5%), tiêu chí không chuẩn hoá, tốn thêm chi phí (ba tiêu chí làm số lượt gọi API tăng gấp bốn) và có thiên lệch (tự thiên vị 10–25%, thích vị trí đầu, thích câu dài), nên phải đi kèm đánh giá chính xác hoặc của người. Đánh giá so sánh nắm sát sở thích người, khó gian lận, không bão hoà, nhưng tốn dữ liệu (153 lượt mỗi cặp với 57 mô hình), giả định bắc cầu có thể sai, khó chuẩn hoá prompt và người chấm, và chỉ cho biết mô hình nào tốt hơn chứ không cho biết tốt đủ chưa (thắng 51% không cho biết sẽ giải được bao nhiêu ticket).

## Khái niệm cần biết

- **Đánh giá chính xác và đánh giá chủ quan (exact vs. subjective evaluation):** đánh giá chính xác cho phán xét không mơ hồ; đánh giá chủ quan cho điểm phụ thuộc vào người hoặc mô hình chấm. Ví dụ: câu trắc nghiệm đáp án A mà chọn B là sai chắc chắn; còn một bài luận có thể được cùng một người chấm 7 điểm hôm nay và 8 điểm tuần sau. Quan trọng vì chương xếp functional correctness và độ tương đồng vào loại chính xác, còn AI làm giám khảo vào loại chủ quan, và mỗi loại cần cách đọc kết quả khác nhau.
- **Benchmark bão hoà (saturated benchmark):** benchmark mà mô hình đã đạt điểm tối đa nên không còn phân biệt được mô hình. Ví dụ: GLUE ra năm 2018 bão hoà sau khoảng một năm, phải thay bằng SuperGLUE (2019); MMLU (2020) được thay phần lớn bằng MMLU-Pro (2024). Quan trọng vì nó là một trong năm lý do mô hình nền tảng khó đánh giá, và là lý do đánh giá so sánh hấp dẫn (không bão hoà).
- **Entropy:** lượng thông tin trung bình mỗi token mang, đo bằng số bit cần để biểu diễn một token; cũng là độ khó đoán token kế tiếp. Ví dụ: ngôn ngữ chỉ có hai token "nửa trên/nửa dưới" có entropy 1 bit; ngôn ngữ bốn token chỉ bốn góc có entropy 2 bit. Quan trọng vì mọi độ đo mô hình ngôn ngữ khác đều dựng từ entropy.
- **Cross entropy:** độ khó mà một mô hình gặp khi dự đoán token kế tiếp trong một tập dữ liệu; bằng entropy của dữ liệu cộng độ lệch KL giữa phân phối thật P và phân phối mô hình Q. Ví dụ: dữ liệu có P = (1/2, 1/4, 1/8, 1/8), mô hình đoán đều 1/4 cho mỗi token thì H(P) = 1,75 bit, D_KL = 0,25 bit, cross entropy 2 bit (người tổng hợp tính). Quan trọng vì đây là hàm mất mát mà hầu hết mô hình ngôn ngữ tự hồi quy được huấn luyện để cực tiểu hoá.
- **Phân kỳ Kullback–Leibler (KL divergence) D_KL(P‖Q):** độ lệch của phân phối mô hình Q so với phân phối thật P; bằng 0 khi Q trùng P. Ví dụ: ở ví dụ trên, D_KL = 0,25 bit là phần "phạt" vì mô hình không biết token thứ nhất phổ biến hơn. Quan trọng vì nó là phần cross entropy mà huấn luyện thực sự giảm được (entropy của dữ liệu là cố định).
- **Bits-per-character (BPC) và bits-per-byte (BPB):** số bit trung bình mô hình cần để biểu diễn một ký tự, hoặc một byte dữ liệu gốc. Ví dụ: 6 bit mỗi token, mỗi token 2 ký tự, cho BPC 3; nếu mỗi ký tự là 7 bit (7/8 byte) thì BPB là 3 / (7/8) ≈ 3,43. Quan trọng vì chúng cho phép so mô hình có tokenizer khác nhau, và BPB cho biết mô hình nén văn bản được bao nhiêu.
- **Perplexity (PPL):** hàm mũ của cross entropy (2^H nếu dùng bit, e^H nếu dùng nat), có thể hiểu là số lựa chọn "hiệu dụng" mà mô hình phân vân khi đoán token kế tiếp. Ví dụ: cross entropy 2 bit cho perplexity 4; GPT-2 bản 1,5 tỷ tham số có perplexity 8,63 trên LAMBADA. Quan trọng vì sách dùng perplexity làm độ đo mô hình ngôn ngữ mặc định, và nó có công dụng thực hành (phát hiện nhiễm dữ liệu, khử trùng lặp, phát hiện văn bản bất thường).
- **Nhiễm dữ liệu (data contamination):** dữ liệu benchmark lọt vào dữ liệu huấn luyện, làm điểm benchmark cao giả tạo. Ví dụ: nếu perplexity của mô hình trên các câu hỏi của một benchmark thấp bất thường so với văn bản cùng loại, có thể mô hình đã "thuộc bài". Quan trọng vì nó làm kết quả benchmark công khai kém tin cậy (Chương 4 bàn tiếp).
- **Functional correctness:** đánh giá hệ thống theo việc nó có thực hiện đúng chức năng mong muốn hay không. Ví dụ: hàm `gcd(15, 20)` do mô hình viết phải trả về 5. Quan trọng vì đây là độ đo tối hậu cho mọi ứng dụng, dù chỉ một số tác vụ (code, game, tối ưu có mục tiêu đo được) tự động hoá được.
- **pass@k:** tỷ lệ bài toán được giải, trong đó một bài được coi là giải nếu ít nhất một trong k mẫu code mô hình sinh ra qua hết các test. Ví dụ: 10 bài, giải được 5 khi k = 3 thì pass@3 bằng 50%. Quan trọng vì đây là độ đo chuẩn của HumanEval, MBPP, và k càng lớn thì điểm càng cao nên phải luôn ghi rõ k.
- **Dữ liệu tham chiếu (reference data, ground truth):** các cặp (đầu vào, câu trả lời tham chiếu) dùng để so đầu ra. Ví dụ: câu tiếng Pháp "Comment ça va?" có ba bản dịch tham chiếu. Quan trọng vì độ đo dựa trên tham chiếu (reference-based) bị giới hạn bởi số lượng và chất lượng tham chiếu, còn độ đo không cần tham chiếu (reference-free) như AI làm giám khảo thì không.
- **Khớp chính xác (exact match):** đầu ra được tính đúng khi trùng hẳn một câu tham chiếu. Ví dụ: "2 + 3 bằng mấy?" có tham chiếu "5"; biến thể "chứa đáp án" chấp nhận "The answer is 5" nhưng cũng chấp nhận nhầm "September 12, 1929" cho câu hỏi về năm sinh của Anne Frank. Quan trọng vì nó chỉ dùng được cho câu trả lời ngắn.
- **Tương đồng từ vựng (lexical similarity):** mức chồng lấp về token giữa hai văn bản. Ví dụ: "My cats eat the mice" chứa 4 trên 5 từ của tham chiếu "My cats scare the mice" (80%). Quan trọng vì đây là cơ sở của BLEU, ROUGE và các độ đo dịch máy cổ điển, nhưng nó không nắm được nghĩa.
- **Edit distance (khoảng cách sửa):** số phép xoá, chèn, thay (và tùy công cụ, đảo hai ký tự kề nhau) ít nhất để biến chuỗi này thành chuỗi kia. Ví dụ: "bad" cách "bard" 1 phép, cách "cash" 3 phép. Quan trọng vì nó là cách đo fuzzy matching.
- **n-gram:** dãy n token liên tiếp. Ví dụ: "My cats scare the mice" có 4 bigram: "my cats", "cats scare", "scare the", "the mice". Quan trọng vì BLEU, ROUGE so chồng lấp n-gram chứ không chỉ từ đơn, nhờ đó phần nào nắm được thứ tự từ.
- **BLEU và ROUGE:** hai độ đo tương đồng từ vựng kinh điển; BLEU (dịch máy) đo tỷ lệ n-gram của câu sinh ra có trong tham chiếu (precision) kèm phạt câu quá ngắn; ROUGE (tóm tắt) đo tỷ lệ n-gram của tham chiếu có trong câu sinh ra (recall). Ví dụ (người tổng hợp tính): với tham chiếu "my cats scare the mice", câu "my cats eat the mice" có BLEU-2 ≈ 0,63 và ROUGE-1 = 0,8. Quan trọng vì sách nêu chúng là độ đo phổ biến và chỉ ra rằng BLEU cao không đồng nghĩa với code đúng.
- **Embedding:** vector số biểu diễn ý nghĩa của dữ liệu. Ví dụ: "the cat sits on a mat" có thể thành [0,11; 0,02; 0,54]; trong thực tế vector có 100–10.000 phần tử (OpenAI text-embedding-3-large: 3.072). Quan trọng vì embedding là nền của tương đồng ngữ nghĩa, tìm kiếm vector (Chương 6) và khử trùng lặp (Chương 8).
- **Độ tương đồng cosine (cosine similarity):** tích vô hướng của hai vector chia cho tích độ dài của chúng; bằng 1 khi cùng hướng, −1 khi ngược hướng. Ví dụ: [0,11; 0,02; 0,54] và [0,10; 0,05; 0,50] có cosine ≈ 0,998 (người tổng hợp tính). Quan trọng vì đây là cách tính tương đồng ngữ nghĩa mặc định.
- **Embedding đa phương thức (multimodal / joint embedding):** không gian chung trong đó dữ liệu khác loại (văn bản, ảnh, âm thanh…) được so sánh trực tiếp. Ví dụ: trong không gian của CLIP, ảnh người câu cá gần câu "a fisherman" hơn câu "fashion show". Quan trọng vì nó cho phép tìm ảnh bằng văn bản và đánh giá đầu ra đa phương thức.
- **AI làm giám khảo (AI as a judge, LLM as a judge):** dùng một mô hình AI để chấm đầu ra của mô hình AI. Ví dụ: prompt yêu cầu GPT-4 chấm câu trả lời từ 1 đến 5 theo câu hỏi. Quan trọng vì đây là phương pháp đánh giá phổ biến nhất trong production lúc sách viết (58% lượt đánh giá trên LangChain năm 2023).
- **Giám khảo AI là một hệ thống:** giám khảo gồm mô hình, prompt và tham số lấy mẫu; đổi một thành phần là đổi giám khảo. Ví dụ: điểm "coherence" tăng từ 90% lên 92% có thể chỉ vì đồng nghiệp sửa lỗi chính tả trong prompt giám khảo. Quan trọng vì nó giải thích vì sao điểm của các giám khảo khác nhau không so được với nhau.
- **Thiên lệch của giám khảo AI:** tự thiên vị (thích câu trả lời của chính mình), thiên vị vị trí đầu, thiên vị độ dài. Ví dụ: Claude-v1 tự ưu tiên mình thêm 25% tỷ lệ thắng; GPT-4 và Claude-1 chọn câu ~100 từ có lỗi sự thật hơn câu ~50 từ đúng. Quan trọng vì biết thiên lệch thì đọc điểm đúng hơn và giảm được thiên lệch (đổi thứ tự, kiểm soát độ dài).
- **Giám khảo chuyên biệt: reward model, giám khảo dựa trên tham chiếu, preference model:** mô hình nhỏ được huấn luyện cho một kiểu phán xét. Ví dụ: Cappy (360 triệu tham số) cho điểm 0–1 cho cặp (prompt, câu trả lời); Prometheus cho điểm 1–5 so với tham chiếu được coi là 5; PandaLM chọn câu trả lời tốt hơn trong hai câu. Quan trọng vì tác giả coi giám khảo nhỏ chuyên biệt là hướng hứa hẹn: tin cậy hơn và rẻ hơn giám khảo đa năng cho phán xét cụ thể.
- **Đánh giá từng điểm và đánh giá so sánh (pointwise vs. comparative evaluation):** chấm từng mô hình độc lập rồi xếp theo điểm, so với cho mô hình đấu từng cặp rồi suy ra thứ hạng. Ví dụ: chấm điểm từng vũ công, so với cho các vũ công nhảy cạnh nhau và hỏi giám khảo thích ai hơn. Quan trọng vì với chất lượng chủ quan, so sánh thường dễ và đáng tin hơn cho điểm.
- **Tỷ lệ thắng (win rate):** xác suất mô hình A được ưa hơn mô hình B, ước lượng bằng tỷ lệ trận A thắng trong mọi trận giữa A và B. Ví dụ: mô hình 1 thắng mô hình 2 ở 900 trong 1.000 trận, tỷ lệ thắng 90%. Quan trọng vì đây là đầu vào của các thuật toán xếp hạng.
- **Thuật toán xếp hạng Elo, Bradley–Terry, TrueSkill:** thuật toán từ cờ vua, thể thao, trò chơi điện tử, gán cho mỗi mô hình một điểm sao cho chênh lệch điểm dự đoán được xác suất thắng. Ví dụ (người tổng hợp tính): theo Elo, mô hình 1.200 điểm gặp mô hình 1.000 điểm có xác suất thắng kỳ vọng 1 / (1 + 10^(−200/400)) ≈ 76%. Quan trọng vì Chatbot Arena dùng Elo rồi chuyển sang Bradley–Terry vì Elo nhạy với thứ tự trận.
- **Tính bắc cầu (transitivity):** nếu A tốt hơn B và B tốt hơn C thì A tốt hơn C. Ví dụ: trong bảng tỷ lệ thắng năm mô hình của sách (Bảng 3-6), mô hình 1 thắng mô hình 2 (90%), mô hình 2 thắng mô hình 5 (80%), nhưng mô hình 5 thắng mô hình 1 (90%), nên không bắc cầu. Quan trọng vì các thuật toán xếp hạng dựa vào giả định này để khỏi phải so mọi cặp, mà sở thích người không chắc bắc cầu.

## Nội dung chi tiết

### 1. Phần mở đầu chương (Chapter 3 introduction, trang PDF 232–234)

AI càng được dùng nhiều thì càng có nhiều cơ hội thất bại nghiêm trọng. Trong thời gian ngắn mô hình nền tảng xuất hiện, đã có nhiều thất bại: một người đàn ông tự tử sau khi được một chatbot khuyến khích; các luật sư nộp chứng cứ giả do AI bịa ra (hallucination); hãng Air Canada bị buộc bồi thường khi chatbot của hãng cung cấp thông tin sai cho một hành khách. Nếu không có cách kiểm soát chất lượng đầu ra của AI, rủi ro của AI có thể lớn hơn lợi ích của nó với nhiều ứng dụng.

Khi các đội vội vã áp dụng AI, nhiều đội nhanh chóng nhận ra trở ngại lớn nhất để đưa ứng dụng AI vào thực tế là đánh giá. Với một số ứng dụng, tìm ra cách đánh giá chiếm phần lớn công sức phát triển. Tác giả dẫn lời Greg Brockman, đồng sáng lập OpenAI, trên Twitter tháng 12/2023: "evals are surprisingly often all you need" (đánh giá thường là tất cả những gì bạn cần, nhiều hơn người ta tưởng).

Vì đánh giá vừa quan trọng vừa phức tạp, sách dành hai chương cho nó. Chương này trình bày các phương pháp đánh giá mô hình có đầu ra mở, cách chúng hoạt động và giới hạn của chúng. Chương sau ([C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md)) trình bày cách dùng các phương pháp này để chọn mô hình cho ứng dụng và dựng quy trình đánh giá (evaluation pipeline).

Tuy đánh giá được bàn trong các chương riêng, nó phải được xét trong bối cảnh cả hệ thống, không tách rời. Đánh giá nhằm giảm rủi ro và phát hiện cơ hội. Để giảm rủi ro, trước hết phải xác định các chỗ hệ thống dễ hỏng và thiết kế đánh giá quanh các chỗ đó; thường điều này đòi hỏi thiết kế lại hệ thống để nhìn thấy rõ hơn các lỗi của nó. Nếu không hiểu rõ hệ thống hỏng ở đâu, không có độ đo hay công cụ đánh giá nào làm hệ thống vững được.

Vì đánh giá khó, nhiều người dựa vào truyền miệng (ai đó nói mô hình X tốt) — một nghiên cứu năm 2023 của quỹ a16z cho thấy 6 trong 70 người ra quyết định chọn mô hình theo truyền miệng — hoặc chỉ nhìn qua kết quả (còn gọi là "vibe check", kiểm tra theo cảm giác). Cách này tạo thêm rủi ro và làm chậm việc lặp cải tiến ứng dụng; cần đầu tư vào đánh giá có hệ thống để kết quả đáng tin hơn.

Vì nhiều mô hình nền tảng có thành phần mô hình ngôn ngữ, chương điểm qua các độ đo đánh giá mô hình ngôn ngữ như cross entropy và perplexity; chúng thiết yếu cho việc huấn luyện và finetuning mô hình ngôn ngữ và được dùng trong nhiều phương pháp đánh giá. Mô hình nền tảng đặc biệt khó đánh giá vì đầu ra mở; người chấm là lựa chọn cần thiết cho nhiều ứng dụng, nhưng vì gán nhãn bằng người chậm và đắt, mục tiêu là tự động hoá. Sách tập trung vào **đánh giá tự động**, gồm cả đánh giá chính xác và đánh giá chủ quan. Ngôi sao đang lên của đánh giá chủ quan là **AI làm giám khảo** — dùng AI chấm câu trả lời của AI. Nó chủ quan vì điểm phụ thuộc vào mô hình và prompt mà giám khảo AI dùng. Cách làm này đang được ngành đón nhận nhanh, nhưng cũng bị phản đối mạnh bởi những người cho rằng AI chưa đủ đáng tin cho việc quan trọng như vậy.

### 2. Thách thức khi đánh giá mô hình nền tảng (Challenges of Evaluating Foundation Models, trang PDF 234–240)

Đánh giá mô hình học máy vốn đã khó; với mô hình nền tảng, nó còn khó hơn vì năm lý do.

**Thứ nhất, mô hình AI càng thông minh thì càng khó đánh giá.** Hầu hết mọi người nhận ra lời giải toán của học sinh lớp một sai; ít người làm được như vậy với lời giải toán cấp tiến sĩ. Dễ nhận ra một bản tóm tắt sách tệ nếu nó vô nghĩa, nhưng khó hơn nhiều nếu nó mạch lạc; để kiểm tra chất lượng, có thể phải đọc cả cuốn sách. Hệ quả là đánh giá tác vụ tinh vi tốn thời gian hơn nhiều: không thể chấm câu trả lời theo cách nó "nghe" thế nào, mà phải kiểm chứng sự thật, suy luận, thậm chí cần chuyên môn của lĩnh vực. Chú thích của sách kể rằng khi mô hình o1 của OpenAI ra mắt tháng 9/2024, nhà toán học đoạt huy chương Fields Terence Tao so sánh làm việc với nó như làm việc với "một nghiên cứu sinh tầm thường nhưng không hoàn toàn bất tài", và đoán có thể chỉ cần một hai thế hệ nữa để AI đạt mức "nghiên cứu sinh có năng lực". Nhiều người đùa rằng nếu đã cần những bộ óc giỏi nhất để đánh giá AI thì sẽ không còn ai đủ trình độ để đánh giá các mô hình tương lai.

**Thứ hai, bản chất mở của mô hình nền tảng làm suy yếu cách đánh giá truyền thống là so với đáp án chuẩn.** Với học máy truyền thống, hầu hết tác vụ là đóng: mô hình phân loại chỉ có thể trả về một trong các lớp định trước; nếu đáp án kỳ vọng là lớp X mà mô hình trả lớp Y thì mô hình sai. Với tác vụ mở, một đầu vào có rất nhiều câu trả lời đúng, không thể lập danh sách đầy đủ để so.

**Thứ ba, hầu hết mô hình nền tảng được đối xử như hộp đen**, vì nhà cung cấp không công bố chi tiết hoặc vì người phát triển ứng dụng thiếu chuyên môn để hiểu. Kiến trúc, dữ liệu huấn luyện, quá trình huấn luyện có thể tiết lộ nhiều về điểm mạnh và điểm yếu của mô hình; thiếu chúng, chỉ có thể đánh giá mô hình qua đầu ra.

**Thứ tư, benchmark công khai tỏ ra không đủ.** Lý tưởng là benchmark nắm được toàn bộ năng lực của mô hình; khi AI tiến bộ, benchmark phải tiến theo. Một benchmark **bão hoà** với một mô hình khi mô hình đạt điểm tuyệt đối. Với mô hình nền tảng, benchmark bão hoà rất nhanh: GLUE (General Language Understanding Evaluation) ra năm 2018 và bão hoà chỉ sau một năm, buộc phải ra SuperGLUE năm 2019; NaturalInstructions (2021) được thay bằng Super-NaturalInstructions (2022); MMLU (2020), benchmark mạnh mà nhiều mô hình nền tảng thời đầu dựa vào, phần lớn đã được thay bằng MMLU-Pro (2024).

**Thứ năm, phạm vi đánh giá mở rộng với mô hình đa năng.** Với mô hình chuyên một tác vụ, đánh giá là đo hiệu năng trên tác vụ đã huấn luyện. Với mô hình đa năng, đánh giá còn phải khám phá các tác vụ mới mà mô hình làm được, có thể vượt khả năng con người; đánh giá gánh thêm trách nhiệm khám phá tiềm năng và giới hạn của AI.

**Tin tốt:** các thách thức mới đã thúc đẩy nhiều phương pháp và benchmark mới. Theo số liệu của Chang và cộng sự (2023) mà sách dẫn (Hình 3-1 của sách), số bài báo về đánh giá LLM là: 0 bài (2020), 3 bài (2021), 3 bài (2022), rồi theo từng tháng năm 2023: 2 bài (tháng 1), 7 (tháng 2), 12 (tháng 3), 15 (tháng 4), 22 (tháng 5) và 33 bài (tháng 6 trở đi) — tức tăng theo hàm mũ từ khoảng 2 lên gần 35 bài mỗi tháng trong nửa đầu 2023. Tác giả tự phân tích 1.000 kho mã liên quan đến AI có nhiều sao nhất trên GitHub (tìm mọi kho có ít nhất 500 sao với từ khoá "LLM", "GPT", "generative", "transformer", cộng các kho do cộng đồng đề xuất qua website huyenchip.com) và tìm được hơn 50 kho chuyên về đánh giá (tính đến tháng 5/2024). Đếm tích luỹ theo tháng tạo kho (Hình 3-2 của sách), số kho đánh giá là: khoảng 1 kho từ cuối 2016, khoảng 4 kho năm 2019, 5 kho năm 2020, 10 kho năm 2021, khoảng 14 kho đầu 2022, khoảng 22 kho cuối 2022, rồi tăng vọt trong năm 2023 lên khoảng 38–40 kho vào đầu 2024; đường cong trông như hàm mũ.

**Tin xấu:** dù được quan tâm hơn, đánh giá vẫn tụt sau phần còn lại của quy trình kỹ thuật AI. Balduzzi và cộng sự ở DeepMind viết rằng "việc phát triển đánh giá nhận được ít sự chú ý có hệ thống so với phát triển thuật toán"; kết quả thí nghiệm hầu như chỉ dùng để cải thiện thuật toán, hiếm khi để cải thiện đánh giá. Nhận thấy đánh giá bị đầu tư thiếu, Anthropic kêu gọi các nhà hoạch định chính sách tăng tài trợ của chính phủ cho cả phát triển phương pháp đánh giá mới lẫn phân tích độ vững của các đánh giá hiện có. Số kho công cụ mã nguồn mở theo hạng mục trong danh sách 1.000 kho AI phổ biến nhất của tác giả (Hình 3-3 của sách) cho thấy đánh giá đứng cuối:

| Hạng mục | Số kho (đọc từ hình, xấp xỉ) |
|---|---:|
| Mô hình hoá và huấn luyện (Modeling & training) | 121 |
| Điều phối AI (AI orchestration) | 78 |
| Tối ưu suy luận (Inference optimization) | 49 |
| Prompt engineering | 47 |
| Giao diện AI (AI interface) | 45 |
| Agent | 44 |
| Đánh giá (Evals) | 40 |

Đầu tư thiếu dẫn tới hạ tầng thiếu, khiến khó đánh giá có hệ thống. Khi được hỏi họ đánh giá ứng dụng AI ra sao, nhiều người nói với tác giả rằng họ chỉ nhìn qua kết quả. Nhiều người có một bộ nhỏ các prompt "ruột" để thử mô hình, được chọn tùy tiện theo kinh nghiệm cá nhân thay vì theo nhu cầu của ứng dụng. Cách làm tùy tiện này có thể tạm dùng khi khởi động dự án, nhưng không đủ cho việc lặp cải tiến ứng dụng. Sách theo hướng đánh giá có hệ thống.

### 3. Hiểu các độ đo mô hình hoá ngôn ngữ (Understanding Language Modeling Metrics, trang PDF 240–252)

#### 3.1. Vì sao cần hiểu các độ đo này (trang PDF 240–242)

Mô hình nền tảng tiến hoá từ mô hình ngôn ngữ, và nhiều mô hình nền tảng vẫn có mô hình ngôn ngữ làm thành phần chính. Với các mô hình này, hiệu năng của thành phần mô hình ngôn ngữ thường tương quan tốt với hiệu năng của mô hình nền tảng trên ứng dụng hạ nguồn (Liu và cộng sự, 2023) — tuy tương quan mạnh, hiệu năng mô hình hoá ngôn ngữ không giải thích hết hiệu năng hạ nguồn, và đây vẫn là hướng nghiên cứu mở (chú thích 6). Vì vậy, hiểu sơ bộ các độ đo này giúp hiểu hiệu năng hạ nguồn.

Như Chương 1 đã nói, mô hình hoá ngôn ngữ có từ nhiều thập kỷ, được Claude Shannon phổ biến trong bài báo năm 1951 "Prediction and Entropy of Printed English". Độ đo dùng để hướng dẫn phát triển mô hình ngôn ngữ không thay đổi nhiều từ đó. Hầu hết mô hình ngôn ngữ tự hồi quy (autoregressive) được huấn luyện bằng **cross entropy** hoặc họ hàng của nó là **perplexity**. Trong bài báo và báo cáo mô hình, còn gặp **bits-per-character (BPC)** và **bits-per-byte (BPB)**, đều là biến thể của cross entropy. Bốn độ đo này liên hệ chặt: biết một độ đo (cùng thông tin cần thiết) thì tính được ba độ đo còn lại. Dù gọi là độ đo mô hình hoá ngôn ngữ, chúng dùng được cho mọi mô hình sinh chuỗi token, kể cả token không phải văn bản.

Mô hình ngôn ngữ mã hoá thông tin thống kê về ngôn ngữ: một token có khả năng xuất hiện bao nhiêu trong một ngữ cảnh. Với ngữ cảnh "I like drinking __", từ kế tiếp nhiều khả năng là "tea" hơn "charcoal". Mô hình nắm được càng nhiều thông tin thống kê thì dự đoán token kế tiếp càng tốt. Trong ngôn ngữ học máy, mô hình ngôn ngữ học **phân phối** của dữ liệu huấn luyện; học càng tốt thì dự đoán điều tiếp theo trong dữ liệu huấn luyện càng tốt và cross entropy huấn luyện càng thấp. Như mọi mô hình học máy, điều ta quan tâm không chỉ là hiệu năng trên dữ liệu huấn luyện mà còn trên dữ liệu production; nhìn chung dữ liệu của bạn càng gần dữ liệu huấn luyện của mô hình thì mô hình càng làm tốt trên dữ liệu của bạn.

Tác giả lưu ý phần này nặng toán hơn phần còn lại của sách; người đọc có thể bỏ qua phần toán và tập trung vào cách diễn giải. Ngay cả khi không huấn luyện hay finetune mô hình, hiểu các độ đo này giúp chọn mô hình, và chúng thỉnh thoảng được dùng cho một số kỹ thuật đánh giá và khử trùng lặp dữ liệu.

#### 3.2. Entropy (trang PDF 242–243)

**Entropy** đo lượng thông tin trung bình một token mang. Entropy càng cao thì mỗi token mang càng nhiều thông tin và càng cần nhiều bit để biểu diễn. (Chú thích 7: token có thể là ký tự, từ hay một phần của từ; khi Shannon đưa ra khái niệm entropy năm 1951, token của ông là ký tự. Theo lời Shannon, entropy là một tham số thống kê đo, theo một nghĩa nào đó, lượng thông tin trung bình được tạo ra cho mỗi chữ cái của văn bản; nếu dịch ngôn ngữ sang chữ số nhị phân theo cách hiệu quả nhất thì entropy là số chữ số nhị phân trung bình cần cho mỗi chữ cái.)

Ví dụ của sách (Hình 3-4 của sách): tạo một ngôn ngữ mô tả vị trí trong một hình vuông.

- Ngôn ngữ (a) chỉ có hai token: hình vuông chia ngang thành ô 1 (nửa trên) và ô 2 (nửa dưới). Mỗi token cho biết vị trí ở trên hay dưới. Vì chỉ có hai token, một bit là đủ; entropy của ngôn ngữ này là 1.
- Ngôn ngữ (b) có bốn token: hình vuông chia thành bốn ô 1, 2, 3, 4 (trên-trái, trên-phải, dưới-trái, dưới-phải). Mỗi token cho vị trí cụ thể hơn, nhưng cần hai bit để biểu diễn bốn token; entropy là 2. Ngôn ngữ này có entropy cao hơn: mỗi token mang nhiều thông tin hơn nhưng cần nhiều bit hơn.

Trực giác: entropy đo độ khó đoán điều tiếp theo trong một ngôn ngữ. Entropy càng thấp (mỗi token mang càng ít thông tin) thì ngôn ngữ càng dễ đoán. Ngôn ngữ hai token dễ đoán hơn ngôn ngữ bốn token (chỉ phải chọn giữa hai thay vì bốn). Giống như nếu bạn đoán trúng hoàn toàn điều tôi sắp nói thì lời tôi không mang thông tin mới.

**Công thức (người tổng hợp bổ sung, sách không ghi):** với phân phối P trên các token, entropy tính bằng bit là

H(P) = −Σₓ P(x) · log₂ P(x).

Giải thích từng bước: (1) với mỗi token x, −log₂ P(x) là "độ bất ngờ" của token đó, tức số bit cần nếu mã hoá tối ưu (token xác suất 1/2 cần 1 bit, xác suất 1/4 cần 2 bit); (2) nhân với P(x) và cộng lại để lấy trung bình theo tần suất xuất hiện. Kiểm tra với ví dụ của sách: ngôn ngữ (a) có hai token đồng khả năng 1/2, H = −2 × (1/2) × log₂(1/2) = 1 bit; ngôn ngữ (b) có bốn token đồng khả năng 1/4, H = −4 × (1/4) × log₂(1/4) = 2 bit. Khớp với sách. Nếu các token không đồng khả năng, entropy nhỏ hơn: P = (1/2, 1/4, 1/8, 1/8) có H = 0,5 × 1 + 0,25 × 2 + 0,125 × 3 + 0,125 × 3 = 1,75 bit, dễ đoán hơn bốn token đồng khả năng.

#### 3.3. Cross entropy (trang PDF 244–245)

Khi huấn luyện mô hình ngôn ngữ trên một tập dữ liệu, mục tiêu là để mô hình học phân phối của dữ liệu đó, tức dự đoán điều tiếp theo trong dữ liệu. **Cross entropy** của mô hình trên một tập dữ liệu đo mô hình gặp khó khăn đến đâu khi dự đoán điều tiếp theo trong tập dữ liệu đó. Cross entropy trên dữ liệu huấn luyện phụ thuộc hai yếu tố:

1. Độ dễ đoán của dữ liệu huấn luyện, đo bằng entropy của dữ liệu.
2. Mức phân phối mà mô hình nắm được lệch khỏi phân phối thật của dữ liệu.

Entropy và cross entropy dùng chung ký hiệu H. Gọi P là phân phối thật của dữ liệu huấn luyện, Q là phân phối mô hình học được. Khi đó entropy của dữ liệu là H(P); độ lệch của Q so với P được đo bằng **phân kỳ Kullback–Leibler** D_KL(P‖Q); và cross entropy của mô hình đối với dữ liệu huấn luyện là

**H(P, Q) = H(P) + D_KL(P‖Q).**

Cross entropy không đối xứng: cross entropy của Q đối với P, H(P, Q), khác cross entropy của P đối với Q, H(Q, P). Mô hình ngôn ngữ được huấn luyện để cực tiểu hoá cross entropy đối với dữ liệu huấn luyện. Nếu mô hình học hoàn hảo, cross entropy của nó bằng đúng entropy của dữ liệu và D_KL bằng 0. Có thể coi cross entropy của mô hình là ước lượng của nó cho entropy của dữ liệu huấn luyện.

**Công thức chi tiết và ví dụ tính (người tổng hợp bổ sung):** H(P, Q) = −Σₓ P(x) · log₂ Q(x) và D_KL(P‖Q) = Σₓ P(x) · log₂ (P(x) / Q(x)). Cộng H(P) với D_KL: −Σ P log P + Σ P log P − Σ P log Q = −Σ P log Q, đúng bằng H(P, Q). Ý nghĩa: token thật xuất hiện với tần suất P(x), nhưng mô hình "trả" −log₂ Q(x) bit cho nó theo xác suất mô hình gán.

Ví dụ: dữ liệu có bốn token với P = (1/2, 1/4, 1/8, 1/8); mô hình chưa học gì, gán đều Q = (1/4, 1/4, 1/4, 1/4).

| Bước | Phép tính | Kết quả |
|---|---|---:|
| Entropy dữ liệu H(P) | 0,5·1 + 0,25·2 + 0,125·3 + 0,125·3 | 1,75 bit |
| Cross entropy H(P, Q) | mỗi token tốn −log₂(1/4) = 2 bit, trung bình 2 bit | 2,00 bit |
| D_KL(P‖Q) | 0,5·log₂(2) + 0,25·log₂(1) + 2·0,125·log₂(0,5) | 0,25 bit |
| Kiểm tra | 1,75 + 0,25 | 2,00 bit |
| Theo chiều ngược H(Q, P) | 0,25·(1 + 2 + 3 + 3) | 2,25 bit |

Hàng cuối cho thấy cross entropy không đối xứng (2,00 khác 2,25). Khi mô hình học tới Q = P, cross entropy giảm về 1,75 bit và không thể giảm thêm: 1,75 bit là "sàn" do bản thân dữ liệu quy định.

#### 3.4. Bits-per-character và bits-per-byte (trang PDF 245–246)

Một đơn vị của entropy và cross entropy là **bit**. Nếu cross entropy của mô hình là 6 bit, mô hình cần 6 bit để biểu diễn mỗi token.

Vì các mô hình có cách tách token khác nhau — mô hình này dùng từ làm token, mô hình kia dùng ký tự — số bit mỗi token không so được giữa các mô hình. Một số người dùng **bits-per-character (BPC)**: nếu số bit mỗi token là 6 và trung bình mỗi token gồm 2 ký tự thì BPC = 6 / 2 = 3.

BPC lại vướng vấn đề bảng mã ký tự: với ASCII mỗi ký tự được mã hoá bằng 7 bit, còn với UTF-8 một ký tự có thể dùng từ 8 đến 32 bit. Độ đo chuẩn hơn là **bits-per-byte (BPB)**: số bit mô hình cần để biểu diễn một byte của dữ liệu huấn luyện gốc. Nếu BPC là 3 và mỗi ký tự là 7 bit, tức 7/8 byte, thì BPB = 3 / (7/8) = 24/7 ≈ 3,43. (Kiểm tra: một byte chứa 8/7 ký tự, mỗi ký tự cần 3 bit, nên một byte cần 3 × 8/7 ≈ 3,43 bit.)

Cross entropy cho biết mô hình nén văn bản hiệu quả đến đâu. BPB 3,43 nghĩa là mỗi byte gốc (8 bit) được biểu diễn bằng 3,43 bit, tức 3,43 / 8 ≈ 42,9% kích thước gốc: mô hình nén được văn bản huấn luyện xuống dưới một nửa.

#### 3.5. Perplexity (trang PDF 246–247)

**Perplexity** là hàm mũ của entropy và cross entropy, thường viết tắt PPL. Với tập dữ liệu có phân phối thật P, perplexity của nó là

PPL(P) = 2^H(P).

Perplexity của mô hình ngôn ngữ (phân phối học được Q) trên tập dữ liệu đó là

PPL(P, Q) = 2^H(P, Q).

Nếu cross entropy đo mô hình gặp khó đến đâu khi dự đoán token kế tiếp, thì perplexity đo mức **không chắc chắn** của mô hình khi dự đoán token kế tiếp: không chắc chắn càng cao nghĩa là có càng nhiều lựa chọn khả dĩ cho token kế tiếp. Ví dụ của sách: mô hình được huấn luyện hoàn hảo trên bốn token vị trí của ngôn ngữ (b) có cross entropy 2 bit; khi dự đoán một vị trí trong hình vuông, nó phải chọn giữa 2² = 4 khả năng, nên perplexity là 4. Áp dụng cho ví dụ của người tổng hợp ở mục 3.3: mô hình đoán đều có perplexity 2² = 4, còn mô hình học hoàn hảo có perplexity 2^1,75 ≈ 3,36 — dữ liệu không đều nên "số lựa chọn hiệu dụng" ít hơn 4.

Cơ số 2 xuất hiện vì mỗi bit biểu diễn 2 giá trị. Các framework học máy phổ biến như TensorFlow và PyTorch lại dùng **nat** (logarit tự nhiên, cơ số e) làm đơn vị cho entropy và cross entropy; khi đó perplexity là e mũ cross entropy:

PPL(P, Q) = e^H(P, Q).

(Chú thích 8: nhiều người thích logarit tự nhiên vì nó làm toán dễ hơn, ví dụ đạo hàm của ln(x) là 1/x.) Kiểm tra quy đổi (người tổng hợp tính): 2 bit bằng 2 × ln 2 ≈ 1,386 nat, và e^1,386 = 4 — perplexity không phụ thuộc đơn vị, còn con số cross entropy thì có. Chính vì lẫn lộn giữa bit và nat, nhiều người báo cáo perplexity thay vì cross entropy.

#### 3.6. Diễn giải perplexity và các trường hợp sử dụng (Perplexity Interpretation and Use Cases, trang PDF 248–252)

Cross entropy, perplexity, BPC, BPB đều là biến thể của phép đo độ chính xác dự đoán của mô hình ngôn ngữ: mô hình dự đoán văn bản càng chính xác thì các độ đo này càng thấp. Sách dùng perplexity làm độ đo mặc định. Mô hình càng không chắc chắn khi dự đoán điều tiếp theo trong một tập dữ liệu thì perplexity càng cao.

Giá trị perplexity "tốt" tùy vào dữ liệu và cách tính chính xác, như mô hình được nhìn bao nhiêu token trước đó. Ba quy tắc chung:

- **Dữ liệu càng có cấu trúc thì perplexity kỳ vọng càng thấp.** Dữ liệu có cấu trúc dễ đoán hơn: mã HTML dễ đoán hơn văn bản đời thường — thấy thẻ mở `<head>` thì đoán được sắp có thẻ đóng `</head>`. Vì vậy perplexity kỳ vọng trên mã HTML thấp hơn trên văn bản đời thường.
- **Bộ từ vựng càng lớn thì perplexity càng cao.** Càng nhiều token khả dĩ thì càng khó đoán token kế tiếp. Perplexity của một mô hình trên sách thiếu nhi có lẽ thấp hơn trên *Chiến tranh và Hoà bình*. Với cùng tập dữ liệu tiếng Anh, perplexity theo ký tự (đoán ký tự kế tiếp) thấp hơn perplexity theo từ (đoán từ kế tiếp), vì số ký tự khả dĩ ít hơn số từ khả dĩ.
- **Context càng dài thì perplexity càng thấp.** Mô hình có càng nhiều ngữ cảnh thì càng ít không chắc chắn. Năm 1951, Shannon đánh giá cross entropy của mô hình bằng cách cho nó đoán token kế tiếp dựa trên tối đa 10 token trước. Lúc sách viết, perplexity thường được tính với 500 đến 10.000 token trước đó, có thể hơn, bị chặn trên bởi độ dài context tối đa của mô hình.

Để tham khảo, perplexity thấp tới 3 hay thấp hơn không hiếm. Nếu mọi token trong một ngôn ngữ giả định đồng khả năng, perplexity 3 nghĩa là mô hình có 1 cơ hội trong 3 đoán đúng token kế tiếp. Với bộ từ vựng cỡ hàng chục nghìn đến hàng trăm nghìn token, tỷ lệ này rất ấn tượng.

**Perplexity là đại diện tốt cho năng lực mô hình.** Ngoài việc hướng dẫn huấn luyện, perplexity hữu ích ở nhiều khâu của quy trình kỹ thuật AI. Nếu mô hình đoán token kế tiếp kém, hiệu năng hạ nguồn của nó nhiều khả năng cũng kém. Báo cáo GPT-2 của OpenAI cho thấy mô hình lớn hơn, cũng là mô hình mạnh hơn, luôn cho perplexity thấp hơn trên nhiều tập dữ liệu (Bảng 3-1 của sách). Phần đọc được của bảng (bản PDF bị cắt bên phải):

| Mô hình | LAMBADA (perplexity) | LAMBADA (độ chính xác, %) | CBT-CN (độ chính xác, %) | CBT-NE (độ chính xác, %) |
|---|---:|---:|---:|---:|
| SOTA trước GPT-2 | 99,8 | 59,23 | 85,7 | 82,3 |
| GPT-2 117M | 35,13 | 45,99 | 87,65 | 83,4 |
| GPT-2 345M | 15,60 | 55,48 | 92,35 | 87,1 |
| GPT-2 762M | 10,87 | 60,12 | 93,45 | 88,0 |
| GPT-2 1542M | 8,63 | 63,24 | 93,30 | 89,05 |

Đọc bảng: perplexity trên LAMBADA giảm đều khi mô hình lớn lên — từ 35,13 xuống 8,63, giảm khoảng 4 lần khi số tham số tăng khoảng 13 lần — và ngay bản nhỏ nhất đã thấp hơn nhiều mức SOTA trước đó (99,8). Độ chính xác cũng tăng gần như đều (LAMBADA từ 45,99% lên 63,24%), trừ cột CBT-CN nơi bản 1542M thấp hơn bản 762M 0,15 điểm. (Theo hiểu biết của người tổng hợp, bảng gốc trong báo cáo GPT-2 còn các cột WikiText2, PTB, enwik8, text8, WikiText103, 1BW.) Đáng tiếc, theo xu hướng các công ty ngày càng giữ kín về mô hình, nhiều công ty đã ngừng công bố perplexity.

**Cảnh báo của sách:** perplexity có thể không phải đại diện tốt để đánh giá mô hình đã qua post-training bằng các kỹ thuật như SFT (supervised finetuning) và RLHF (học tăng cường từ phản hồi người, xem Chương 2 — [C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md)). Post-training dạy mô hình hoàn thành tác vụ; khi mô hình giỏi hoàn thành tác vụ hơn, nó có thể kém đi trong việc đoán token kế tiếp. Perplexity của mô hình ngôn ngữ thường tăng sau post-training; có người nói post-training "làm sụp entropy" (collapses entropy). Tương tự, lượng tử hoá (quantization) — kỹ thuật giảm độ chính xác số của mô hình và nhờ đó giảm bộ nhớ (Chương 7) — cũng có thể làm perplexity thay đổi theo cách khó lường.

**Phát hiện nhiễm dữ liệu và khử trùng lặp.** Perplexity của mô hình đối với một văn bản đo mô hình gặp khó đến đâu khi dự đoán văn bản đó. Với một mô hình cho trước, perplexity thấp nhất với văn bản mà mô hình đã thấy và học thuộc khi huấn luyện. Vì vậy perplexity dùng được để phát hiện một văn bản có nằm trong dữ liệu huấn luyện hay không. Điều này hữu ích để phát hiện **nhiễm dữ liệu**: nếu perplexity của mô hình trên dữ liệu một benchmark thấp, benchmark đó có lẽ đã nằm trong dữ liệu huấn luyện, khiến kết quả của mô hình trên benchmark kém đáng tin. Nó cũng dùng được để khử trùng lặp dữ liệu huấn luyện: chỉ thêm dữ liệu mới vào tập huấn luyện nếu perplexity của dữ liệu mới cao.

**Phát hiện văn bản bất thường.** Perplexity cao nhất với văn bản khó đoán, như văn bản diễn đạt ý tưởng lạ ("my dog teaches quantum physics in his free time" — con chó của tôi dạy vật lý lượng tử lúc rảnh) hoặc vô nghĩa ("home cat go eye"). Vì vậy perplexity dùng được để phát hiện văn bản bất thường.

Perplexity và các độ đo liên quan giúp hiểu hiệu năng của mô hình ngôn ngữ nền, vốn là đại diện cho hiệu năng hạ nguồn. Phần còn lại của chương bàn cách đo trực tiếp hiệu năng hạ nguồn.

#### 3.7. Khung: dùng mô hình ngôn ngữ để tính perplexity của một văn bản (How to Use a Language Model to Compute a Text's Perplexity, trang PDF 252)

Perplexity của mô hình đối với một văn bản đo mô hình gặp khó đến đâu khi dự đoán văn bản đó. Cho mô hình ngôn ngữ X và chuỗi token [x₁, x₂, …, xₙ], perplexity của X trên chuỗi này là

PPL = P(x₁, x₂, …, xₙ)^(−1/n) = (1 / P(x₁, x₂, …, xₙ))^(1/n) = (∏ᵢ₌₁ⁿ 1 / P(xᵢ | x₁, …, xᵢ₋₁))^(1/n),

trong đó P(xᵢ | x₁, …, xᵢ₋₁) là xác suất mô hình X gán cho token xᵢ khi biết các token trước đó.

Giải thích từng bước (người tổng hợp): (1) xác suất của cả chuỗi, theo quy tắc nhân xác suất, bằng tích các xác suất có điều kiện của từng token, nên hai vế cuối bằng nhau; (2) lấy nghịch đảo để "xác suất cao" thành "perplexity thấp"; (3) lấy căn bậc n (trung bình nhân) để không phụ thuộc độ dài chuỗi. Lấy log₂ hai vế: log₂ PPL = −(1/n) Σ log₂ P(xᵢ | …), chính là cross entropy trung bình mỗi token tính bằng bit; nên công thức này nhất quán với PPL = 2^H ở mục 3.5.

Ví dụ tính (người tổng hợp đặt): chuỗi 4 token mà mô hình gán xác suất có điều kiện lần lượt 0,5; 0,25; 0,8; 0,1. Tích bằng 0,5 × 0,25 × 0,8 × 0,1 = 0,01; perplexity = (1 / 0,01)^(1/4) = 100^(1/4) ≈ 3,16. Theo log: cross entropy = −(log₂0,5 + log₂0,25 + log₂0,8 + log₂0,1) / 4 = (1 + 2 + 0,322 + 3,322) / 4 ≈ 1,661 bit; 2^1,661 ≈ 3,16. Cùng kết quả. Tính bằng nat: 1,151 nat, e^1,151 ≈ 3,16.

Để tính perplexity, cần truy cập xác suất (hoặc logprob — logarit của xác suất) mà mô hình gán cho từng token kế tiếp. Đáng tiếc, không phải mô hình thương mại nào cũng công bố logprob, như Chương 2 đã bàn.

### 4. Đánh giá chính xác (Exact Evaluation, trang PDF 252–253)

Khi đánh giá hiệu năng mô hình, cần phân biệt đánh giá chính xác và đánh giá chủ quan. **Đánh giá chính xác** cho phán xét không mơ hồ: câu trắc nghiệm có đáp án A mà bạn chọn B thì bạn sai, không có gì mơ hồ. Ngược lại, chấm bài luận là chủ quan: điểm phụ thuộc người chấm, và cùng một người chấm hai lần cách nhau một thời gian có thể cho điểm khác. Chấm bài luận có thể chính xác hơn nếu có hướng dẫn chấm rõ ràng. AI làm giám khảo là đánh giá chủ quan: kết quả thay đổi theo mô hình giám khảo và prompt.

Sách trình bày hai cách cho điểm chính xác: **functional correctness** và **đo độ tương đồng với dữ liệu tham chiếu**. Phần này tập trung vào đánh giá câu trả lời mở (sinh văn bản tuỳ ý) thay vì câu trả lời đóng (như phân loại). Không phải vì mô hình nền tảng không được dùng cho tác vụ đóng — thực tế nhiều hệ thống có ít nhất một thành phần phân loại, thường để phân loại ý định hoặc chấm điểm — mà vì đánh giá tác vụ đóng đã được hiểu rõ.

#### 4.1. Functional correctness (trang PDF 253–256)

**Functional correctness** là đánh giá hệ thống dựa trên việc nó có thực hiện đúng chức năng mong muốn hay không. Bảo mô hình tạo website: website có đáp ứng yêu cầu không? Bảo mô hình đặt bàn ở một nhà hàng: nó có đặt được không? Đây là độ đo tối hậu cho hiệu năng của mọi ứng dụng, vì nó đo ứng dụng có làm đúng việc nó được thiết kế để làm không. Nhưng functional correctness không phải lúc nào cũng dễ đo, và khó tự động hoá.

**Sinh code** là ví dụ tác vụ đo functional correctness tự động được; trong lập trình, nó đôi khi được gọi là *execution accuracy* (độ chính xác khi thực thi). Bảo mô hình viết hàm Python `gcd(num1, num2)` tìm ước chung lớn nhất của hai số; code sinh ra được đưa vào trình thông dịch Python để kiểm tra có hợp lệ không, và nếu hợp lệ thì có cho kết quả đúng với một cặp (num1, num2) cho trước không. Ví dụ với cặp (15, 20), nếu `gcd(15, 20)` không trả về 5 thì hàm sai.

Từ lâu trước khi AI viết code, kiểm tra tự động functional correctness đã là thực hành chuẩn của kỹ nghệ phần mềm: code thường được kiểm tra bằng **unit test**, chạy code trong các tình huống khác nhau để bảo đảm nó cho đầu ra kỳ vọng. Các nền tảng như LeetCode và HackerRank chấm lời giải nộp lên theo cách này. Các benchmark phổ biến về sinh code như HumanEval của OpenAI và MBPP (Mostly Basic Python Problems) của Google dùng functional correctness; các benchmark text-to-SQL (sinh câu truy vấn SQL từ ngôn ngữ tự nhiên) như Spider (Yu và cộng sự, 2018), BIRD-SQL (Big Bench for Large-scale Database Grounded Text-to-SQL Evaluation; Li và cộng sự, 2023) và WikiSQL (Zhong và cộng sự, 2017) cũng vậy.

Mỗi bài trong benchmark đi kèm một bộ test; mỗi test gồm một tình huống code phải chạy và đầu ra kỳ vọng. Ví dụ một bài HumanEval (bản PDF cắt mép phải; người tổng hợp dựng lại các dòng bị cắt theo bài HumanEval/0 và đã chạy thử):

```python
# Problem
from typing import List

def has_close_elements(numbers: List[float], threshold: float) -> bool:
    """ Check if in given list of numbers, are any two numbers closer to each
    other than given threshold.
    >>> has_close_elements([1.0, 2.0, 3.0], 0.5)
    False
    >>> has_close_elements([1.0, 2.8, 3.0, 4.0, 5.0, 2.0], 0.3)
    True
    """

# Test cases (each assert statement represents a test case)
def check(candidate):
    assert candidate([1.0, 2.0, 3.9, 4.0, 5.0, 2.2], 0.3) == True
    assert candidate([1.0, 2.0, 3.9, 4.0, 5.0, 2.2], 0.05) == False
    assert candidate([1.0, 2.0, 5.9, 4.0, 5.0], 0.95) == True
    assert candidate([1.0, 2.0, 5.9, 4.0, 5.0], 0.8) == False
    assert candidate([1.0, 2.0, 3.0, 4.0, 5.0, 2.0], 0.1) == True
    assert candidate([1.1, 2.2, 3.1, 4.1, 5.1], 1.0) == True
    assert candidate([1.1, 2.2, 3.1, 4.1, 5.1], 0.5) == False
```

Đề bài: kiểm tra trong danh sách số có hai số nào cách nhau ít hơn ngưỡng không. Ví dụ test thứ nhất đúng vì 3,9 và 4,0 cách nhau 0,1 < 0,3; test thứ hai sai vì không cặp nào cách nhau dưới 0,05; test thứ năm đúng vì có hai số 2,0 trùng nhau (cách 0).

**pass@k.** Khi đánh giá, với mỗi bài mô hình sinh k mẫu code. Mô hình giải được bài nếu **bất kỳ** mẫu nào trong k mẫu qua **tất cả** test của bài. Điểm cuối cùng, gọi là **pass@k**, là tỷ lệ bài giải được trên tổng số bài. Có 10 bài và mô hình giải được 5 với k = 3 thì pass@3 = 5/10 = 50%. Mô hình sinh càng nhiều mẫu thì càng có nhiều cơ hội giải mỗi bài, nên điểm càng cao; về kỳ vọng, pass@1 thấp hơn pass@3, và pass@3 thấp hơn pass@10.

*Bổ sung của người tổng hợp (không có trong sách):* nếu mỗi mẫu độc lập và đúng với xác suất p, xác suất ít nhất một trong k mẫu đúng là 1 − (1 − p)^k. Với p = 0,2: pass@1 = 20%, pass@3 = 1 − 0,8³ = 48,8%, pass@10 = 1 − 0,8¹⁰ ≈ 89,3%. Bài báo HumanEval (Chen và cộng sự, 2021) dùng ước lượng không chệch: sinh n ≥ k mẫu, đếm c mẫu đúng, rồi tính pass@k = 1 − C(n − c, k) / C(n, k), trong đó C(a, b) là số tổ hợp chập b của a; C(n − c, k) / C(n, k) là xác suất chọn ngẫu nhiên k mẫu mà không mẫu nào đúng. Với n = 10, c = 2: pass@1 = 1 − 8/10 = 0,2; pass@3 = 1 − C(8,3)/C(10,3) = 1 − 56/120 ≈ 0,533; pass@10 = 1. Điều này cho thấy phải luôn ghi rõ k khi so điểm.

**Các tác vụ khác có mục tiêu đo được.** Bot chơi game là một loại khác: tạo bot chơi *Tetris* thì biết bot giỏi đến đâu qua điểm số. Tác vụ có mục tiêu đo được thường đánh giá được bằng functional correctness; ví dụ bảo AI lập lịch các tác vụ tính toán để tối ưu tiêu thụ năng lượng thì đo bằng lượng năng lượng tiết kiệm được. Chú thích 11 bổ sung một khó khăn: nhiều tác vụ phức tạp có mục tiêu đo được, nhưng AI chưa đủ giỏi để làm trọn từ đầu đến cuối, nên AI chỉ làm một phần lời giải; mà đánh giá một phần lời giải đôi khi khó hơn đánh giá kết cục cuối — như đánh giá khả năng chơi cờ của ai đó qua kết quả ván (thắng/thua/hoà) dễ hơn qua một nước cờ.

#### 4.2. Đo độ tương đồng với dữ liệu tham chiếu (Similarity Measurements Against Reference Data, trang PDF 257–259)

Nếu tác vụ không đánh giá tự động được bằng functional correctness, cách phổ biến là so đầu ra với **dữ liệu tham chiếu**. Ví dụ bảo mô hình dịch một câu từ tiếng Pháp sang tiếng Anh, thì so bản dịch tiếng Anh sinh ra với bản dịch tiếng Anh đúng.

Mỗi ví dụ trong dữ liệu tham chiếu có dạng (đầu vào, các câu trả lời tham chiếu). Một đầu vào có thể có nhiều câu trả lời tham chiếu, như nhiều bản dịch tiếng Anh khả dĩ của một câu tiếng Pháp. Câu trả lời tham chiếu còn gọi là **ground truth** (đáp án chuẩn) hay **canonical response**. Độ đo cần tham chiếu gọi là **reference-based**, độ đo không cần gọi là **reference-free**.

Vì cần dữ liệu tham chiếu, cách đánh giá này bị nghẽn bởi lượng và tốc độ tạo dữ liệu tham chiếu. Dữ liệu tham chiếu thường do người tạo, và ngày càng nhiều do AI tạo. Dùng dữ liệu do người tạo làm tham chiếu nghĩa là coi hiệu năng của người là chuẩn vàng và đo AI so với người. Dữ liệu do người tạo có thể đắt và tốn thời gian, nên nhiều người dùng AI tạo dữ liệu tham chiếu; dữ liệu AI tạo vẫn có thể cần người duyệt, nhưng công duyệt ít hơn nhiều so với công tạo từ đầu.

Câu trả lời sinh ra càng giống tham chiếu thì càng được coi là tốt. Có bốn cách đo độ tương đồng giữa hai văn bản mở:

1. Nhờ một người đánh giá phán xét hai văn bản có giống nhau không.
2. **Khớp chính xác (exact match):** câu trả lời sinh ra có trùng hẳn một câu tham chiếu không.
3. **Tương đồng từ vựng (lexical similarity):** câu trả lời sinh ra *trông* giống tham chiếu đến đâu.
4. **Tương đồng ngữ nghĩa (semantic similarity):** câu trả lời sinh ra gần tham chiếu về *nghĩa* đến đâu.

Người đánh giá ở cách 1 có thể là người hoặc AI; AI ngày càng phổ biến và là chủ đề của mục sau. Mục này tập trung vào các độ đo thiết kế tay: khớp chính xác, tương đồng từ vựng và tương đồng ngữ nghĩa. Điểm khớp chính xác là nhị phân (khớp hoặc không), còn hai loại kia là thang trượt (như từ 0 đến 1 hoặc từ −1 đến 1). Dù AI làm giám khảo dễ dùng và linh hoạt, các độ đo tương đồng thiết kế tay vẫn được dùng rộng rãi vì tính chính xác của chúng.

**Ghi chú của sách:** ngoài đánh giá chất lượng đầu ra, đo độ tương đồng còn dùng cho nhiều việc khác:

- truy xuất và tìm kiếm: tìm mục giống một truy vấn;
- xếp hạng: xếp các mục theo mức giống truy vấn;
- gom cụm: gom các mục theo mức giống nhau;
- phát hiện bất thường: tìm các mục ít giống phần còn lại nhất;
- khử trùng lặp dữ liệu: loại các mục quá giống mục khác.

Các kỹ thuật này sẽ xuất hiện lại trong suốt cuốn sách.

#### 4.3. Khớp chính xác (Exact match, trang PDF 259–261)

Câu trả lời được coi là khớp chính xác nếu nó trùng hẳn một trong các câu tham chiếu. Cách này hợp với tác vụ cần câu trả lời ngắn, chính xác như bài toán đơn giản, câu hỏi kiến thức phổ thông và câu đố kiểu trivia. Ví dụ đầu vào có câu trả lời ngắn, chính xác: "2 + 3 bằng mấy?"; "Ai là người phụ nữ đầu tiên đoạt giải Nobel?"; "Số dư tài khoản hiện tại của tôi là bao nhiêu?"; "Điền vào chỗ trống: Paris với Pháp như ___ với Anh."

Có các biến thể tính đến vấn đề định dạng. Một biến thể chấp nhận mọi đầu ra *chứa* câu tham chiếu: với câu hỏi "2 + 3 bằng mấy?", tham chiếu là "5", biến thể này chấp nhận cả "The answer is 5" và "2 + 3 is 5". Nhưng biến thể này đôi khi chấp nhận lời giải sai. Câu hỏi "Anne Frank sinh năm nào?": Anne Frank sinh ngày 12/6/1929, nên đáp án là 1929; nếu mô hình trả lời "September 12, 1929", năm đúng có trong đầu ra nhưng câu trả lời sai sự thật.

Ngoài các tác vụ đơn giản, khớp chính xác hiếm khi dùng được. Câu tiếng Pháp "Comment ça va?" có nhiều bản dịch tiếng Anh khả dĩ: "How are you?", "How is everything?", "How are you doing?". Nếu dữ liệu tham chiếu chỉ có ba bản này và mô hình sinh "How is it going?", câu trả lời bị chấm sai. Văn bản gốc càng dài và phức tạp thì càng nhiều bản dịch khả dĩ; không thể tạo bộ câu trả lời đầy đủ cho một đầu vào. Với tác vụ phức tạp, tương đồng từ vựng và ngữ nghĩa làm tốt hơn.

#### 4.4. Tương đồng từ vựng (Lexical similarity, trang PDF 261–264)

**Tương đồng từ vựng** đo hai văn bản chồng lấp đến đâu, bằng cách trước hết tách mỗi văn bản thành token nhỏ hơn. (Chú thích 12: có thể cần xử lý thêm tùy việc muốn coi "cats" và "cat", hay "will not" và "won't", là hai token khác nhau hay không.)

Dạng đơn giản nhất là đếm số token chung của hai văn bản. Ví dụ của sách: tham chiếu "My cats scare the mice" và hai câu trả lời sinh ra:

- A: "My cats eat the mice"
- B: "Cats and mice fight all the time"

Coi mỗi từ là một token. Chỉ đếm chồng lấp của từ đơn, câu A chứa 4 trên 5 từ của tham chiếu (my, cats, the, mice), điểm tương đồng 80%; câu B chỉ chứa 3 trên 5 (cats, mice, the), điểm 60%. Vậy A được coi là giống tham chiếu hơn.

**Fuzzy matching và edit distance.** Một cách đo tương đồng từ vựng là so khớp chuỗi gần đúng (approximate string matching), thường gọi là **fuzzy matching**. Nó đo độ giống nhau giữa hai văn bản bằng số phép sửa cần để biến văn bản này thành văn bản kia, gọi là **edit distance**. Ba phép sửa thông thường:

1. Xoá: "brad" thành "bad".
2. Chèn: "bad" thành "bard".
3. Thay: "bad" thành "bed".

Một số công cụ coi việc đảo hai chữ kề nhau ("mats" thành "mast") là một phép sửa; một số khác coi mỗi lần đảo là hai phép (một xoá, một chèn). Ví dụ "bad" cách "bard" 1 phép và cách "cash" 3 phép (thay b bằng c, thay d bằng s, chèn h), nên "bad" được coi là giống "bard" hơn "cash". (Người tổng hợp kiểm tra bằng thuật toán Levenshtein: brad–bad 1, bad–bard 1, bad–bed 1, bad–cash 3; mats–mast là 2 nếu không tính phép đảo.)

**Tương đồng n-gram.** Một cách khác là đo chồng lấp của các dãy token, **n-gram**, thay cho token đơn. 1-gram (unigram) là một token; 2-gram (bigram) là hai token liên tiếp. "My cats scare the mice" gồm bốn bigram: "my cats", "cats scare", "scare the", "the mice". Ta đo tỷ lệ phần trăm n-gram của các câu tham chiếu có mặt trong câu trả lời sinh ra. Áp dụng cho ví dụ trên (người tổng hợp tính): câu A có bigram "my cats", "cats eat", "eat the", "the mice", khớp 2 trên 4 bigram tham chiếu (50%); câu B có sáu bigram ("cats and", "and mice", "mice fight", "fight all", "all the", "the time"), không khớp bigram tham chiếu nào (0%). So với unigram (80% và 60%), bigram phân biệt hai câu rõ hơn vì nó tính đến thứ tự từ.

**Các độ đo phổ biến.** Các độ đo tương đồng từ vựng phổ biến là BLEU, ROUGE, METEOR++, TER và CIDEr; chúng khác nhau ở cách tính chồng lấp. Trước mô hình nền tảng, BLEU, ROUGE và họ hàng rất phổ biến, nhất là cho dịch máy. Từ khi mô hình nền tảng nổi lên, ít benchmark dùng tương đồng từ vựng hơn; ví dụ benchmark còn dùng là WMT, COCO Captions và GEMv2.

*Công thức BLEU và ROUGE (người tổng hợp bổ sung, sách không trình bày):*

- **Độ chính xác n-gram có cắt (clipped n-gram precision)** pₙ = (số n-gram của câu sinh ra có trong tham chiếu, mỗi n-gram chỉ được tính tối đa số lần nó xuất hiện trong tham chiếu) / (tổng số n-gram của câu sinh ra). Phép "cắt" ngăn câu sinh ra gian lận bằng cách lặp một từ đúng nhiều lần.
- **BLEU-N** = BP × exp((1/N) × Σₙ₌₁ᴺ ln pₙ), tức trung bình nhân của p₁ … p_N nhân với hệ số phạt độ ngắn BP. BP = 1 nếu câu sinh ra dài hơn tham chiếu, ngược lại BP = e^(1 − r/c) với r là độ dài tham chiếu, c là độ dài câu sinh ra. Không có BP, câu chỉ gồm một từ đúng sẽ có precision 100%. BLEU chuẩn dùng N = 4.
- **ROUGE-N** = (số n-gram của tham chiếu có trong câu sinh ra) / (tổng số n-gram của tham chiếu) — tức *recall*. Con số 80% và 60% của sách chính là ROUGE-1.

Tính cho ví dụ của sách với BLEU-2 (N = 2, vì câu quá ngắn để dùng N = 4):

| Câu | p₁ | p₂ | BP | BLEU-2 | ROUGE-1 | ROUGE-2 |
|---|---:|---:|---:|---:|---:|---:|
| A "my cats eat the mice" | 4/5 | 2/4 | 1 (dài bằng tham chiếu) | √(0,8 × 0,5) ≈ 0,632 | 4/5 = 0,80 | 2/4 = 0,50 |
| B "cats and mice fight all the time" | 3/7 | 0/6 | 1 (dài hơn) | 0 (vì p₂ = 0) | 3/5 = 0,60 | 0/4 = 0 |

Bảng cho thấy precision và recall khác nhau ở câu B: 3 từ của tham chiếu có trong B (recall 60%) nhưng chỉ 3 trên 7 từ của B có trong tham chiếu (precision ≈ 43%), vì B có nhiều từ thừa.

**Nhược điểm thứ nhất: cần bộ tham chiếu đầy đủ.** Một câu trả lời tốt có thể bị điểm thấp nếu bộ tham chiếu không có câu nào giống nó. Adept nhận thấy trên một số ví dụ benchmark, mô hình Fuyu của họ bị điểm thấp không phải vì đầu ra sai mà vì dữ liệu tham chiếu thiếu một số câu đúng. Ví dụ mô tả ảnh của Adept (Hình 3-5 của sách): bức ảnh chụp đêm tháp đồng hồ Big Ben và toà nhà Quốc hội Anh với các vệt đèn xe chạy. Fuyu mô tả: "A nighttime view of Big Ben and the Houses of Parliament" (cảnh đêm Big Ben và toà nhà Quốc hội) — hoàn toàn đúng. Năm câu tham chiếu là: "A fast moving image of cars on a busy street with a tower clock in the background", "Lit up night traffic is zooming by a clock tower", "A city building is brightly lit and a lot of vehicles are driving by", "A large clock tower and traffic moving near", "there is a large tower with a clock on it". Điểm CIDEr của Fuyu chỉ 0,4, vì không câu tham chiếu nào nhắc tới Big Ben hay Parliament.

**Nhược điểm thứ hai: tham chiếu có thể sai.** Ban tổ chức WMT 2023 Metrics shared task (cuộc thi về độ đo đánh giá dịch máy) báo cáo tìm thấy nhiều bản dịch tham chiếu kém trong dữ liệu của họ. Dữ liệu tham chiếu chất lượng thấp là một lý do khiến các độ đo không cần tham chiếu cạnh tranh ngang ngửa với độ đo dựa trên tham chiếu về mức tương quan với phán xét của người (Freitag và cộng sự, 2023).

**Nhược điểm thứ ba: điểm tương đồng cao không luôn có nghĩa là câu trả lời tốt hơn.** Trên HumanEval, OpenAI thấy điểm BLEU của lời giải sai và lời giải đúng tương tự nhau; tối ưu BLEU không giống tối ưu functional correctness (Chen và cộng sự, 2021).

#### 4.5. Tương đồng ngữ nghĩa (Semantic similarity, trang PDF 264–266)

Tương đồng từ vựng đo hai văn bản có *trông* giống nhau không, không đo chúng có cùng *nghĩa* không. "What's up?" và "How are you?" khác nhau về từ vựng — rất ít chồng lấp về từ và chữ cái — nhưng gần nhau về nghĩa. Ngược lại, văn bản trông giống nhau có thể mang nghĩa rất khác: "Let's eat, grandma" (ăn thôi bà ơi) và "Let's eat grandma" (ăn thịt bà đi) khác nhau hoàn toàn chỉ vì một dấu phẩy.

**Tương đồng ngữ nghĩa** nhằm tính độ giống nhau về nghĩa. Trước hết phải biến văn bản thành một biểu diễn số, gọi là **embedding**; ví dụ câu "the cat sits on a mat" có thể được biểu diễn bằng embedding [0,11; 0,02; 0,54]. Vì vậy tương đồng ngữ nghĩa còn gọi là **tương đồng embedding** (embedding similarity). Giả sử đã có cách biến văn bản thành embedding (mục 4.6), độ giống nhau giữa hai embedding có thể tính bằng các độ đo như **độ tương đồng cosine**: hai embedding giống hệt có điểm 1, hai embedding ngược nhau có điểm −1. Tương đồng ngữ nghĩa tính được cho embedding của mọi loại dữ liệu, kể cả ảnh và âm thanh; với văn bản, nó đôi khi được gọi là semantic textual similarity.

**Cảnh báo của sách:** dù xếp tương đồng ngữ nghĩa vào nhóm đánh giá chính xác, nó có thể được coi là chủ quan, vì các thuật toán embedding khác nhau cho embedding khác nhau. Nhưng với hai embedding cho trước, điểm tương đồng giữa chúng được tính chính xác.

**Công thức cosine.** Gọi A là embedding của câu trả lời sinh ra, B là embedding của câu tham chiếu. Độ tương đồng cosine là

cos(A, B) = (A · B) / (‖A‖ · ‖B‖),

trong đó A · B là tích vô hướng của A và B (nhân từng cặp phần tử rồi cộng lại), còn ‖A‖ là chuẩn Euclid (chuẩn L2), tức độ dài của vector A. Nếu A = [0,11; 0,02; 0,54] thì ‖A‖ = √(0,11² + 0,02² + 0,54²).

Tính từng bước (người tổng hợp): ‖A‖ = √(0,0121 + 0,0004 + 0,2916) = √0,3041 ≈ 0,5515. Lấy B = [0,10; 0,05; 0,50] (câu tham chiếu giả định có nghĩa gần): A · B = 0,11 × 0,10 + 0,02 × 0,05 + 0,54 × 0,50 = 0,011 + 0,001 + 0,27 = 0,282; ‖B‖ = √(0,01 + 0,0025 + 0,25) = √0,2625 ≈ 0,5123; cos(A, B) = 0,282 / (0,5515 × 0,5123) ≈ 0,998, rất giống nhau. Với C = −A = [−0,11; −0,02; −0,54], cos(A, C) = −1 (ngược hẳn). Cosine chỉ xét *hướng* chứ không xét *độ dài* của vector, nhờ chia cho hai chuẩn.

Các độ đo tương đồng văn bản ngữ nghĩa gồm **BERTScore** (embedding do BERT tạo) và **MoverScore** (embedding do hỗn hợp thuật toán tạo). Tương đồng ngữ nghĩa không cần bộ tham chiếu đầy đủ như tương đồng từ vựng. Nhưng độ tin cậy của nó phụ thuộc chất lượng thuật toán embedding: hai văn bản cùng nghĩa vẫn có thể có điểm thấp nếu embedding kém. Nhược điểm nữa là thuật toán embedding có thể cần nhiều tài nguyên tính toán và thời gian.

Embedding là trung tâm của tương đồng ngữ nghĩa và là xương sống của nhiều chủ đề trong sách, gồm tìm kiếm vector ở Chương 6 ([C06-rag-va-agent.md](C06-rag-va-agent.md)) và khử trùng lặp dữ liệu ở Chương 8 ([C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md)), nên sách giới thiệu nhanh về embedding trước khi bàn AI làm giám khảo.

#### 4.6. Giới thiệu về embedding (Introduction to Embedding, trang PDF 267–271)

Máy tính làm việc với số, nên mô hình phải biến đầu vào thành biểu diễn số mà máy tính xử lý được. **Embedding** là biểu diễn số nhằm nắm được ý nghĩa của dữ liệu gốc. Embedding là một vector. Câu "the cat sits on a mat" có thể được biểu diễn bằng vector embedding [0,11; 0,02; 0,54]; đây là vector nhỏ để minh hoạ, còn trong thực tế kích thước embedding (số phần tử của vector) thường từ 100 đến 10.000. (Chú thích 13: không gian 10.000 chiều nghe có vẻ nhiều, nhưng thấp hơn nhiều so với số chiều của dữ liệu thô; vì vậy embedding được coi là biểu diễn dữ liệu phức tạp trong không gian ít chiều hơn.)

Các mô hình được huấn luyện riêng để tạo embedding gồm các mô hình mã nguồn mở BERT, CLIP (Contrastive Language–Image Pre-training) và Sentence Transformers; cũng có các mô hình embedding độc quyền cung cấp qua API. (Chú thích 14: còn có mô hình tạo embedding cho từ thay vì cho cả văn bản, như word2vec — Mikolov và cộng sự, 2013 — và GloVe — Pennington và cộng sự, nhóm NLP Đại học Stanford, 2014.) Kích thước embedding của một số mô hình phổ biến (Bảng 3-2 của sách):

| Mô hình | Kích thước embedding |
|---|---|
| BERT (Google) | BERT base: 768; BERT large: 1.024 |
| CLIP (OpenAI) | ảnh: 512; văn bản: 512 |
| OpenAI Embeddings API | text-embedding-3-small: 1.536; text-embedding-3-large: 3.072 |
| Cohere Embed v3 | embed-english-v3.0: 1.024; embed-english-light-3.0: 384 |

Vì mô hình thường cần biến đầu vào thành vector trước, nhiều mô hình học máy, kể cả GPT và Llama, cũng có bước tạo embedding (tầng embedding trong kiến trúc transformer, xem Chương 2). Nếu truy cập được các tầng giữa của chúng, có thể lấy embedding từ đó, nhưng chất lượng có thể không bằng embedding từ mô hình chuyên tạo embedding.

**Thế nào là embedding tốt?** Mục tiêu của thuật toán embedding là tạo embedding nắm được bản chất của dữ liệu gốc. Kiểm tra thế nào, khi vector [0,11; 0,02; 0,54] trông chẳng giống câu "the cat sits on a mat" chút nào? Ở mức tổng quát, thuật toán embedding được coi là tốt nếu văn bản càng giống nhau thì embedding càng gần nhau, đo bằng cosine hoặc độ đo liên quan. Embedding của "the cat sits on a mat" nên gần embedding của "the dog plays on the grass" hơn embedding của "AI research is super fun". Cũng có thể đánh giá chất lượng embedding theo mức hữu ích cho tác vụ: embedding được dùng cho phân loại, mô hình hoá chủ đề, hệ gợi ý, RAG. Một ví dụ benchmark đo chất lượng embedding trên nhiều tác vụ là MTEB (Massive Text Embedding Benchmark; Muennighoff và cộng sự, 2023).

Mọi loại dữ liệu đều có thể có embedding, không chỉ văn bản. Các giải pháp thương mại điện tử như Criteo và Coveo có embedding cho sản phẩm; Pinterest có embedding cho ảnh, đồ thị, truy vấn và cả người dùng.

**Embedding chung cho nhiều phương thức.** Một hướng mới là tạo embedding chung cho dữ liệu thuộc các phương thức khác nhau. CLIP (Radford và cộng sự, 2021) là một trong các mô hình lớn đầu tiên đưa được dữ liệu của hai phương thức, văn bản và ảnh, vào một không gian embedding chung. ULIP (unified representation of language, images, and point clouds; Xue và cộng sự, 2022) nhắm tới biểu diễn thống nhất cho văn bản, ảnh và đám mây điểm 3D. ImageBind (Girdhar và cộng sự, 2023) học embedding chung cho sáu phương thức, gồm văn bản, ảnh và âm thanh.

Kiến trúc CLIP (Hình 3-6 của sách): CLIP được huấn luyện trên các cặp (ảnh, văn bản); văn bản đi kèm ảnh có thể là chú thích hay bình luận. Với mỗi cặp — trong hình là ảnh một chú chuột hamster đeo kính và dòng chữ "Happy hippie hamster" — CLIP dùng **bộ mã hoá văn bản** biến văn bản thành embedding văn bản (vector độ dài D_t, ví dụ bắt đầu 0,23 … kết thúc 0,19) và **bộ mã hoá ảnh** biến ảnh thành embedding ảnh (vector độ dài D_v, ví dụ 0,31 … 0,44). Sau đó nó chiếu cả hai vào một không gian chung bằng cách nhân với ma trận chiếu ngôn ngữ W_t (kích thước D_e × D_t) và ma trận chiếu thị giác W_v (D_e × D_v), được embedding đa phương thức của văn bản và của ảnh cùng độ dài D_e, rồi tính điểm tương đồng cosine giữa chúng. Mục tiêu huấn luyện là kéo embedding của ảnh lại gần embedding của văn bản tương ứng trong không gian chung này.

Một không gian embedding chung biểu diễn được dữ liệu của nhiều phương thức gọi là **không gian embedding đa phương thức**. Trong không gian chung văn bản–ảnh, embedding của ảnh một người đang câu cá nên gần embedding của câu "a fisherman" hơn câu "fashion show". Không gian chung cho phép so sánh và kết hợp embedding của các phương thức khác nhau, ví dụ tìm ảnh bằng văn bản: cho một đoạn văn bản, tìm các ảnh gần nó nhất.

### 5. AI làm giám khảo (AI as a Judge, trang PDF 271–295)

#### 5.1. Khái niệm và bối cảnh (AI as a Judge, trang PDF 271–272)

Khó khăn khi đánh giá câu trả lời mở khiến nhiều đội quay về đánh giá bằng người. AI đã tự động hoá thành công nhiều tác vụ khó; liệu nó có tự động hoá được việc đánh giá? Cách dùng AI để đánh giá AI gọi là **AI as a judge** hay **LLM as a judge** (AI làm giám khảo); mô hình AI dùng để đánh giá các mô hình khác gọi là **giám khảo AI** (chú thích 15: không nhầm với việc dùng AI làm thẩm phán ở toà án).

Ý tưởng dùng AI tự động hoá đánh giá đã có từ lâu — chú thích 16 kể năm 2017 tác giả trình bày tại một workshop của NeurIPS phương pháp MEWR (Machine translation Evaluation metric Without Reference text), dùng mô hình ngôn ngữ mạnh hơn để tự động đánh giá bản dịch máy, nhưng không theo đuổi tiếp. Ý tưởng chỉ trở nên thực tế khi mô hình AI đủ năng lực, khoảng năm 2020 với GPT-3. Lúc sách viết, AI làm giám khảo là một trong những phương pháp đánh giá mô hình AI trong production phổ biến nhất, nếu không phải phổ biến nhất. Hầu hết bản demo của các startup đánh giá AI mà tác giả xem trong 2023 và 2024 đều dùng AI làm giám khảo dưới hình thức nào đó. Báo cáo State of AI 2023 của LangChain ghi nhận 58% lượt đánh giá trên nền tảng của họ do giám khảo AI thực hiện. Đây cũng là hướng nghiên cứu sôi động.

#### 5.2. Vì sao dùng AI làm giám khảo (Why AI as a Judge?, trang PDF 272–274)

Giám khảo AI nhanh, dễ dùng và tương đối rẻ so với người đánh giá. Chúng còn hoạt động được **không cần dữ liệu tham chiếu**, nên dùng được trong môi trường production nơi không có tham chiếu.

Có thể yêu cầu mô hình AI chấm đầu ra theo bất kỳ tiêu chí nào: tính đúng, sự lặp lại, độc hại, lành mạnh, hallucination, v.v. — giống như có thể hỏi ý kiến một người về bất cứ điều gì. Người ta có thể phản bác rằng không phải lúc nào cũng tin được ý kiến của người; đúng vậy, và cũng không phải lúc nào cũng tin được phán xét của AI. Nhưng vì mỗi mô hình AI là tổng hợp của số đông, mô hình AI có thể đưa ra phán xét đại diện cho số đông; với prompt đúng cho mô hình đúng, có thể có phán xét khá tốt trên nhiều chủ đề.

Nghiên cứu cho thấy một số giám khảo AI tương quan mạnh với người đánh giá. Năm 2023, Zheng và cộng sự thấy trên benchmark MT-Bench của họ, mức đồng ý giữa GPT-4 và người đạt 85%, còn cao hơn mức đồng ý giữa người với người (81%). Nhóm tác giả AlpacaEval (Dubois và cộng sự, 2023) cũng thấy giám khảo AI của họ có tương quan gần hoàn hảo (0,98) với bảng xếp hạng Chat Arena của LMSYS, vốn do người đánh giá.

AI không chỉ chấm được mà còn giải thích được quyết định, rất hữu ích khi cần kiểm toán kết quả đánh giá. Ví dụ của sách (Hình 3-7): người dùng đưa cho GPT-4 chính đoạn văn của sách về nhược điểm thứ ba của tương đồng từ vựng (BLEU của lời giải sai và đúng tương tự nhau trên HumanEval) và yêu cầu chấm từ 1 đến 5 kèm giải thích. GPT-4 cho 4,5/5; điểm mạnh: rõ ràng (giải thích rõ nhược điểm và có ví dụ cụ thể), có bằng chứng (dùng HumanEval và phát hiện của OpenAI), ngắn gọn; cần cải thiện: mạch chuyển ý — câu chuyển trơn tru nhưng có thể nối chặt hơn giữa nhận định chung và ví dụ cụ thể.

Nhờ linh hoạt, AI làm giám khảo hữu ích cho nhiều loại ứng dụng, và với một số ứng dụng, đó là lựa chọn đánh giá tự động duy nhất. Ngay cả khi phán xét của AI không tốt bằng người, chúng có thể vẫn đủ tốt để định hướng phát triển ứng dụng và đủ tin cậy để khởi động dự án.

#### 5.3. Cách dùng AI làm giám khảo (How to Use AI as a Judge, trang PDF 274–281)

Có nhiều cách dùng AI để phán xét: đánh giá chất lượng một câu trả lời tự thân, so câu trả lời với dữ liệu tham chiếu, hoặc so với một câu trả lời khác. Prompt mẫu đơn giản (sách gọi là "naive") cho ba cách:

1. **Đánh giá chất lượng một câu trả lời tự thân, khi biết câu hỏi gốc:**

```text
"Given the following question and answer, evaluate how good the answer is
for the question. Use the score from 1 to 5.
- 1 means very bad.
- 5 means very good.
Question: [QUESTION]
Answer: [ANSWER]
Score:"
```

2. **So câu trả lời sinh ra với câu tham chiếu để xem chúng có giống nhau không** — một lựa chọn thay cho các độ đo tương đồng thiết kế tay:

```text
"Given the following question, reference answer, and generated answer,
evaluate whether this generated answer is the same as the reference answer.
Output True or False.
Question: [QUESTION]
Reference answer: [REFERENCE ANSWER]
Generated answer: [GENERATED ANSWER]"
```

3. **So hai câu trả lời sinh ra để chọn câu tốt hơn hoặc đoán câu người dùng sẽ thích hơn** — hữu ích để tạo dữ liệu sở thích cho post-training alignment, cho test-time compute (cả hai ở Chương 2) và cho xếp hạng mô hình bằng đánh giá so sánh (mục 6):

```text
"Given the following question and two answers, evaluate which answer is
better. Output A or B.
Question: [QUESTION]
A: [FIRST ANSWER]
B: [SECOND ANSWER]
The better answer is:"
```

(Bản PDF cắt mép phải các dòng đầu của ba prompt; phần sau dấu cắt — "how good the answer is", "and generated answer", "same as the reference answer", "evaluate which answer is" — do người tổng hợp nối lại theo ngữ cảnh.)

Giám khảo AI đa năng có thể được yêu cầu chấm theo bất kỳ tiêu chí nào. Làm chatbot nhập vai thì có thể kiểm tra câu trả lời có nhất quán với vai người dùng muốn không, như "Câu trả lời này có giống điều Gandalf sẽ nói không?". Làm ứng dụng tạo ảnh quảng cáo sản phẩm thì có thể hỏi "Từ 1 đến 5, bạn đánh giá độ đáng tin của sản phẩm trong ảnh này thế nào?". Các tiêu chí có sẵn của một số công cụ AI, tính đến tháng 9/2024 (Bảng 3-3 của sách; các tiêu chí sẽ đổi khi công cụ phát triển):

| Công cụ AI | Tiêu chí có sẵn |
|---|---|
| Azure AI Studio | groundedness (bám nguồn), relevance (liên quan), coherence (mạch lạc), fluency (trôi chảy), similarity (tương đồng) |
| MLflow.metrics | faithfulness (trung thành với ngữ cảnh), relevance |
| LangChain Criteria Evaluation | conciseness (ngắn gọn), relevance, correctness (đúng), coherence, harmfulness (gây hại), maliciousness (ác ý), helpfulness (hữu ích), controversiality (gây tranh cãi), misogyny (kỳ thị nữ), insensitivity (vô cảm), criminality (tội phạm) |
| Ragas | faithfulness, answer relevance |

Cần nhớ rằng tiêu chí của AI làm giám khảo **không được chuẩn hoá**: điểm relevance của Azure AI Studio có thể rất khác điểm relevance của MLflow, vì điểm phụ thuộc mô hình nền và prompt của giám khảo.

**Viết prompt cho giám khảo.** Prompt giám khảo giống prompt cho mọi ứng dụng AI khác. Nhìn chung, prompt giám khảo nên giải thích rõ:

1. **Nhiệm vụ** mô hình phải làm, như đánh giá mức liên quan giữa câu trả lời sinh ra và câu hỏi.
2. **Tiêu chí** mô hình phải theo, như "Trọng tâm chính của bạn là xác định câu trả lời sinh ra có chứa đủ thông tin để trả lời câu hỏi theo đáp án chuẩn hay không". Hướng dẫn càng chi tiết càng tốt.
3. **Hệ thống điểm**, một trong ba loại: (a) phân loại, như tốt/xấu hoặc liên quan/không liên quan/trung lập; (b) giá trị số rời rạc, như 1 đến 5 — có thể coi là trường hợp đặc biệt của phân loại, trong đó mỗi lớp có nghĩa số thay vì nghĩa ngữ nghĩa; (c) giá trị số liên tục, như từ 0 đến 1, ví dụ khi muốn đánh giá mức độ tương đồng.

**Mẹo của sách:** mô hình ngôn ngữ thường giỏi với chữ hơn với số. Có báo cáo rằng giám khảo AI làm tốt với phân loại hơn với chấm điểm bằng số. Với chấm điểm bằng số, điểm rời rạc có vẻ tốt hơn điểm liên tục; theo kinh nghiệm, thang rời rạc càng rộng thì mô hình càng tệ; thang rời rạc điển hình là 1 đến 5.

Prompt có ví dụ được chứng minh là cho kết quả tốt hơn. Nếu dùng thang 1 đến 5, hãy đưa ví dụ câu trả lời được 1, 2, 3, 4, 5 điểm trông thế nào, và nếu được thì giải thích vì sao câu đó được điểm đó. Các thực hành tốt về prompt được bàn ở Chương 5 ([C05-prompt-engineering.md](C05-prompt-engineering.md)).

Ví dụ: một phần prompt cho tiêu chí relevance của Azure AI Studio. Nó nêu nhiệm vụ, tiêu chí, hệ thống điểm, một ví dụ đầu vào bị điểm thấp và lý do (một phần đã được lược bớt):

```text
Your task is to score the relevance between a generated answer and the
question based on the ground truth answer in the range between 1 and 5, and
please also provide the scoring reason.
Your primary focus should be on determining whether the generated answer
contains sufficient information to address the given question according to
the ground truth answer. …
If the generated answer contradicts the ground truth answer, it will receive
a low score of 1-2.
For example, for the question "Is the sky blue?" the ground truth answer is
"Yes, the sky is blue." and the generated answer is "No, the sky is not blue."
In this example, the generated answer contradicts the ground truth answer by
stating that the sky is not blue, when in fact it is blue.
This inconsistency would result in a low score of 1–2, and the reason for the
low score would reflect the contradiction between the generated answer and
the ground truth answer.
```

Dịch ý: nhiệm vụ là chấm mức liên quan giữa câu trả lời sinh ra và câu hỏi dựa trên đáp án chuẩn, thang 1–5, kèm lý do; trọng tâm là câu trả lời có đủ thông tin để trả lời câu hỏi theo đáp án chuẩn không; nếu mâu thuẫn với đáp án chuẩn thì 1–2 điểm, ví dụ câu hỏi "Bầu trời có màu xanh không?", đáp án chuẩn "Có", câu trả lời sinh ra "Không".

Sơ đồ một giám khảo AI đánh giá chất lượng câu trả lời theo câu hỏi (Hình 3-8 của sách): đối tượng cần đánh giá là cặp (câu hỏi, câu trả lời); nó được điền vào **mẫu prompt theo tiêu chí** ("Given the following question and answer, evaluate how good the answer is for the question. Use the score from 1 to 5. Q: {question} A: {answer} Score:") để thành prompt cuối cùng; prompt cuối được gửi cho **mô hình** (GPT-4), mô hình trả ra **điểm**. Khung "AI judge" bao trọn cả mẫu prompt và mô hình.

Do đó **giám khảo AI không chỉ là một mô hình — nó là một hệ thống gồm cả mô hình và prompt**. Thay đổi mô hình, prompt hoặc tham số lấy mẫu của mô hình là có một giám khảo khác.

#### 5.4. Giới hạn của AI làm giám khảo (Limitations of AI as a Judge, trang PDF 281–290)

Dù có nhiều ưu điểm, nhiều đội vẫn ngần ngại áp dụng. Dùng AI đánh giá AI có vẻ như lập luận vòng quanh. Bản chất xác suất của AI khiến nó có vẻ quá thiếu tin cậy để làm người chấm. Giám khảo AI có thể thêm chi phí và độ trễ đáng kể cho ứng dụng. Vì các giới hạn này, một số đội coi AI làm giám khảo là phương án dự phòng khi không còn cách nào khác để đánh giá hệ thống, nhất là trong production.

##### Không nhất quán (Inconsistency, trang PDF 282)

Để phương pháp đánh giá đáng tin, kết quả của nó phải nhất quán. Nhưng giám khảo AI, như mọi ứng dụng AI, mang tính xác suất. Cùng giám khảo, cùng đầu vào, có thể cho điểm khác nếu prompt khác; ngay cả cùng giám khảo, cùng hướng dẫn, chạy hai lần cũng có thể cho điểm khác. Sự không nhất quán khiến khó tái lập hay tin kết quả.

Có thể làm giám khảo nhất quán hơn: Chương 2 bàn cách dùng các biến lấy mẫu; Zheng và cộng sự (2023) cho thấy đưa ví dụ đánh giá vào prompt nâng độ nhất quán của GPT-4 từ 65% lên 77,5%. Nhưng họ thừa nhận nhất quán cao chưa chắc chính xác cao — giám khảo có thể nhất quán mắc cùng một lỗi. Thêm nữa, nhiều ví dụ làm prompt dài hơn, và prompt dài hơn nghĩa là chi phí suy luận cao hơn: trong thí nghiệm của Zheng, thêm ví dụ vào prompt làm chi tiêu cho GPT-4 tăng gấp bốn.

##### Tiêu chí mơ hồ (Criteria ambiguity, trang PDF 283–287)

Khác với nhiều độ đo do người thiết kế, độ đo của AI làm giám khảo không được chuẩn hoá, nên dễ hiểu sai và dùng sai. Lúc sách viết, các công cụ mã nguồn mở MLflow, Ragas và LlamaIndex đều có tiêu chí có sẵn **faithfulness** để đo đầu ra trung thành với ngữ cảnh đến đâu, nhưng hướng dẫn và hệ thống điểm của chúng đều khác nhau (Bảng 3-4 của sách):

| Công cụ | Prompt (lược bớt) | Hệ thống điểm |
|---|---|---|
| MLflow | "Faithfulness is only evaluated with the provided output and provided context, please ignore the provided input entirely when scoring faithfulness. Faithfulness assesses how much of the provided output is factually consistent with the provided context.… Faithfulness: Below are the details for different scores: - Score 1: None of the claims in the output can be inferred from the provided context. - Score 2: …" | 1–5 |
| Ragas | "Your task is to judge the faithfulness of a series of statements based on a given context. For each statement you must return verdict as 1 if the statement can be verified based on the context or 0 if the statement can not be verified based on the context." | 0 và 1 |
| LlamaIndex | "Please tell if a given piece of information is supported by the context. You need to answer with either YES or NO. Answer YES if any of the context supports the information, even if most of the context is unrelated. Some examples are provided below. Information: Apple pie is generally double-crusted. Context: An apple pie is a fruit pie… It is generally double-crusted, with pastry both above and below the filling ... Answer: YES" | YES và NO |

Tóm ý ba prompt: MLflow chỉ xét đầu ra và ngữ cảnh, bỏ qua đầu vào, chấm 1 khi không khẳng định nào trong đầu ra suy ra được từ ngữ cảnh; Ragas chấm từng khẳng định 1 nếu kiểm chứng được bằng ngữ cảnh, 0 nếu không; LlamaIndex trả lời YES nếu *bất kỳ* phần nào của ngữ cảnh ủng hộ thông tin, kể cả khi phần lớn ngữ cảnh không liên quan.

Điểm faithfulness của ba công cụ không so được với nhau. Nếu với một cặp (ngữ cảnh, câu trả lời), MLflow cho 3, Ragas cho 1 và LlamaIndex cho NO, bạn dùng điểm nào?

Ứng dụng thay đổi theo thời gian, nhưng lý tưởng là cách đánh giá nó phải cố định, để độ đo theo dõi được thay đổi của ứng dụng. Giám khảo AI lại cũng là ứng dụng AI, nên cũng có thể thay đổi. Giả sử tháng trước điểm coherence của ứng dụng là 90%, tháng này là 92%: ứng dụng có mạch lạc hơn không? Khó trả lời nếu không chắc giám khảo hai lần là một. Có thể prompt giám khảo tháng này đã khác — bạn chuyển sang prompt tốt hơn một chút, hoặc đồng nghiệp sửa một lỗi chính tả trong prompt tháng trước, và giám khảo tháng này dễ dãi hơn. Điều này càng rối nếu ứng dụng và giám khảo do hai đội khác nhau quản lý: đội giám khảo đổi giám khảo mà không báo, và đội ứng dụng nhầm rằng điểm thay đổi là do ứng dụng thay đổi.

**Mẹo của sách:** đừng tin bất kỳ giám khảo AI nào nếu bạn không xem được mô hình và prompt nó dùng.

Phương pháp đánh giá cần thời gian để chuẩn hoá; tác giả hy vọng khi lĩnh vực phát triển và có thêm guardrail (rào chắn an toàn), giám khảo AI tương lai sẽ chuẩn hoá và đáng tin hơn nhiều.

##### Tăng chi phí và độ trễ (Increased costs and latency, trang PDF 288–289)

Có thể dùng giám khảo AI cả khi thử nghiệm lẫn trong production. Nhiều đội dùng giám khảo AI làm guardrail trong production để giảm rủi ro: chỉ cho người dùng thấy câu trả lời được giám khảo cho là tốt.

Dùng mô hình mạnh để chấm có thể đắt. Nếu dùng GPT-4 cả để sinh lẫn để chấm, số lượt gọi GPT-4 tăng gấp đôi, chi phí API xấp xỉ gấp đôi. Nếu có ba prompt đánh giá cho ba tiêu chí — chất lượng tổng thể, nhất quán sự thật, độc hại — số lượt gọi API tăng gấp bốn (1 lượt sinh + 3 lượt chấm). Chú thích 17: trong một số trường hợp, đánh giá chiếm phần lớn ngân sách, nhiều hơn cả việc sinh câu trả lời.

Có thể giảm chi phí bằng cách dùng mô hình yếu hơn làm giám khảo (mục 5.5), hoặc **spot-check**: chỉ đánh giá một phần câu trả lời (chú thích 18: spot-check chính là lấy mẫu). Spot-check nghĩa là có thể bỏ sót lỗi; tỷ lệ mẫu đánh giá càng lớn thì càng tự tin vào kết quả nhưng chi phí càng cao. Tìm cân bằng giữa chi phí và độ tự tin có thể phải thử và sai (Chương 4 bàn tiếp). Xét mọi mặt, giám khảo AI vẫn rẻ hơn người đánh giá nhiều.

Đưa giám khảo AI vào quy trình production có thể thêm độ trễ. Nếu chấm câu trả lời trước khi trả cho người dùng thì phải đánh đổi: giảm rủi ro nhưng tăng độ trễ. Độ trễ thêm có thể khiến cách này không khả thi cho ứng dụng có yêu cầu độ trễ khắt khe.

##### Thiên lệch của AI làm giám khảo (Biases of AI as a judge, trang PDF 289–290)

Người đánh giá có thiên lệch, giám khảo AI cũng vậy, và mỗi giám khảo có thiên lệch riêng. Biết thiên lệch của giám khảo giúp đọc điểm đúng và thậm chí giảm thiên lệch.

- **Tự thiên vị (self-bias):** mô hình ưu tiên câu trả lời của chính nó hơn câu của mô hình khác. Cùng cơ chế giúp mô hình tính ra câu trả lời có khả năng nhất để sinh cũng cho câu đó điểm cao. Trong thí nghiệm năm 2023 của Zheng và cộng sự, GPT-4 tự ưu tiên mình với tỷ lệ thắng cao hơn 10%, Claude-v1 cao hơn 25%.
- **Thiên vị vị trí đầu (first-position bias):** giám khảo có thể ưu tiên câu trả lời thứ nhất trong so sánh cặp hoặc lựa chọn đầu trong một danh sách. Có thể giảm bằng cách lặp lại cùng phép thử với các thứ tự khác nhau, hoặc bằng prompt được soạn cẩn thận. Thiên lệch vị trí của AI ngược với người: người thường ưu tiên câu thấy cuối cùng, gọi là thiên lệch gần đây (recency bias).
- **Thiên vị độ dài (verbosity bias):** một số giám khảo ưu tiên câu trả lời dài hơn bất kể chất lượng. Wu và Aji (2023) thấy cả GPT-4 lẫn Claude-1 chọn câu dài hơn (~100 từ) có lỗi sự thật thay vì câu ngắn hơn (~50 từ) đúng. Saito và cộng sự (2023) nghiên cứu thiên lệch này với tác vụ sáng tạo và thấy khi chênh lệch độ dài đủ lớn (ví dụ một câu dài gấp đôi câu kia), giám khảo gần như luôn chọn câu dài. Chú thích 19: Saito cũng thấy người cũng thích câu dài, nhưng ở mức thấp hơn nhiều. Cả Zheng và Saito đều thấy GPT-4 ít bị thiên lệch này hơn GPT-3.5, gợi ý rằng thiên lệch có thể giảm dần khi mô hình mạnh lên.

Ngoài các thiên lệch, giám khảo AI có cùng giới hạn của mọi ứng dụng AI, gồm **quyền riêng tư** và **sở hữu trí tuệ**: dùng mô hình độc quyền làm giám khảo nghĩa là phải gửi dữ liệu cho mô hình đó; nếu nhà cung cấp không công bố dữ liệu huấn luyện, bạn không chắc giám khảo có an toàn để dùng thương mại không.

Dù có giới hạn, tác giả tin việc dùng AI làm giám khảo sẽ tiếp tục tăng nhờ nhiều ưu điểm; nhưng giám khảo AI nên được bổ sung bằng đánh giá chính xác và/hoặc đánh giá của người.

#### 5.5. Mô hình nào làm được giám khảo? (What Models Can Act as Judges?, trang PDF 290–295)

Giám khảo có thể mạnh hơn, yếu hơn hoặc ngang với mô hình bị chấm; mỗi trường hợp có ưu nhược riêng.

**Giám khảo mạnh hơn.** Thoạt nhìn hợp lý: người chấm thi chẳng phải nên giỏi hơn thí sinh sao? Mô hình mạnh không chỉ phán xét tốt hơn mà còn giúp cải thiện mô hình yếu bằng cách hướng dẫn nó sinh câu tốt hơn. Nếu đã có mô hình mạnh, sao không dùng nó để sinh luôn? Câu trả lời là chi phí và độ trễ. Có thể không đủ ngân sách để dùng mô hình mạnh sinh mọi câu trả lời, nên chỉ dùng nó chấm một phần — ví dụ dùng mô hình nội bộ rẻ để sinh và GPT-4 để chấm 1% câu trả lời. Mô hình mạnh cũng có thể quá chậm cho ứng dụng: dùng mô hình nhanh để sinh, còn mô hình mạnh nhưng chậm chấm ở chế độ nền; nếu mô hình mạnh cho rằng câu trả lời của mô hình yếu tệ, có thể khắc phục, ví dụ thay câu trả lời bằng câu của mô hình mạnh. Kiểu ngược lại cũng phổ biến: mô hình mạnh sinh, mô hình yếu chạy nền để chấm.

Dùng mô hình mạnh hơn làm giám khảo để lại hai thách thức: mô hình mạnh nhất sẽ không có giám khảo đủ tư cách; và cần một phương pháp đánh giá khác để xác định mô hình nào mạnh nhất.

**Tự đánh giá (self-evaluation, self-critique).** Dùng mô hình chấm chính nó nghe như gian lận, nhất là vì tự thiên vị. Nhưng tự đánh giá rất tốt để kiểm tra tính hợp lý: nếu mô hình cho rằng câu trả lời của chính nó sai, có lẽ mô hình không đáng tin lắm. Ngoài ra, yêu cầu mô hình tự đánh giá có thể thúc nó sửa và cải thiện câu trả lời (Press và cộng sự, 2022; Gou và cộng sự, 2023; Valmeekam và cộng sự, 2023; chú thích 20: kỹ thuật này đôi khi gọi là self-critique hay self-ask). Ví dụ:

```text
Prompt [from user]: What's 10+3?
First response [from AI]: 30
Self-critique [from AI]: Is this answer correct?
Final response [from AI]: No it's not. The correct answer is 13.
```

**Giám khảo yếu hơn.** Câu hỏi mở là giám khảo có thể yếu hơn mô hình bị chấm không. Có người lập luận chấm dễ hơn sinh: ai cũng có ý kiến bài hát có hay không, nhưng không phải ai cũng viết được bài hát; vậy mô hình yếu nên chấm được đầu ra của mô hình mạnh. Zheng và cộng sự (2023) thấy mô hình mạnh hơn tương quan tốt hơn với sở thích của người, khiến người ta chọn mô hình mạnh nhất mà họ chi trả được. Nhưng thí nghiệm này chỉ giới hạn ở giám khảo đa năng.

**Giám khảo nhỏ, chuyên biệt.** Hướng nghiên cứu tác giả hào hứng là giám khảo nhỏ chuyên biệt: được huấn luyện để đưa ra phán xét cụ thể, theo tiêu chí cụ thể và hệ thống điểm cụ thể. Với phán xét cụ thể, giám khảo nhỏ chuyên biệt có thể đáng tin hơn giám khảo đa năng lớn. Vì có nhiều cách dùng giám khảo AI nên có nhiều loại giám khảo chuyên biệt; sách nêu ba loại:

- **Reward model (mô hình thưởng):** nhận cặp (prompt, câu trả lời) và chấm câu trả lời tốt đến đâu cho prompt đó. Reward model đã được dùng thành công trong RLHF nhiều năm. Ví dụ Cappy của Google (2023): cho cặp (prompt, câu trả lời), Cappy cho điểm từ 0 đến 1 thể hiện mức đúng của câu trả lời; Cappy là bộ chấm nhẹ với 360 triệu tham số, nhỏ hơn nhiều so với mô hình nền tảng đa năng.
- **Giám khảo dựa trên tham chiếu (reference-based judge):** đánh giá câu trả lời sinh ra so với một hay nhiều câu tham chiếu; có thể cho điểm tương đồng hoặc điểm chất lượng (câu sinh ra tốt đến đâu so với tham chiếu). Ví dụ BLEURT (Sellam và cộng sự, 2020) nhận cặp (câu ứng viên, câu tham chiếu) và cho điểm tương đồng — chú thích 21 nói thang điểm BLEURT gây bối rối, xấp xỉ từ −2,5 đến 1,0, minh hoạ cho vấn đề tiêu chí mơ hồ: thang điểm có thể tùy ý. Prometheus (Kim và cộng sự, 2023) nhận (prompt, câu sinh ra, câu tham chiếu, thang chấm) và cho điểm chất lượng từ 1 đến 5, giả định câu tham chiếu được 5.
- **Preference model (mô hình sở thích):** nhận (prompt, câu trả lời 1, câu trả lời 2) và cho biết câu nào tốt hơn (được người dùng ưa hơn) với prompt đó. Đây có lẽ là một trong những hướng thú vị nhất: đoán được sở thích của người mở ra nhiều khả năng. Như Chương 2 đã bàn, dữ liệu sở thích thiết yếu để căn chỉnh (align) mô hình theo sở thích người, mà lại khó và đắt để thu thập; một bộ đoán sở thích tốt làm đánh giá dễ hơn và mô hình an toàn hơn. Các nỗ lực xây preference model gồm PandaLM (Wang và cộng sự, 2023) và JudgeLM (Zhu và cộng sự, 2023).

Ví dụ đầu ra của PandaLM (Hình 3-9 của sách): người dùng đưa hướng dẫn "giải thích nghĩa của cụm từ bằng lời đơn giản, có ví dụ nếu được" với đầu vào là cụm "with a little give in them". Câu trả lời 1 (của Bloom): "With a little bit of flexibility, they can bend and adapt to different situations." Câu trả lời 2 (của LLaMA): "The phrase 'with a little give in them' means to have a bit of flexibility or room for compromise." PandaLM đánh giá: "Câu trả lời 2 tốt hơn vì nó giải thích rõ và gọn nghĩa của cụm từ", và đưa kèm câu tham chiếu: "The phrase 'with a little give in them' means to have a bit of flexibility or room for compromise." PandaLM không chỉ chọn câu tốt hơn mà còn giải thích lý do.

Dù có giới hạn, AI làm giám khảo linh hoạt và mạnh; dùng mô hình rẻ hơn làm giám khảo càng làm nó hữu ích. Nhiều đồng nghiệp của tác giả, lúc đầu hoài nghi, đã bắt đầu dựa vào nó nhiều hơn trong production. Phương pháp tiếp theo cũng thú vị không kém, lấy cảm hứng từ thiết kế trò chơi.

### 6. Xếp hạng mô hình bằng đánh giá so sánh (Ranking Models with Comparative Evaluation, trang PDF 295–309)

#### 6.1. Đánh giá từng điểm và đánh giá so sánh (trang PDF 296–301)

Thường ta đánh giá mô hình không phải vì quan tâm điểm của chúng, mà vì muốn biết mô hình nào tốt nhất cho mình; điều cần là một **thứ hạng**. Có thể xếp hạng bằng **đánh giá từng điểm** hoặc **đánh giá so sánh**.

- Với đánh giá từng điểm, mỗi mô hình được đánh giá độc lập (chú thích 22: ví dụ dùng thang Likert), rồi xếp theo điểm. Muốn tìm vũ công giỏi nhất thì đánh giá từng người, cho điểm, chọn người điểm cao nhất.
- Với đánh giá so sánh, các mô hình được đánh giá đối đầu nhau, và thứ hạng được tính từ kết quả so sánh. Cùng cuộc thi nhảy đó, có thể yêu cầu các thí sinh nhảy cạnh nhau, hỏi giám khảo thích ai nhất, và chọn người được nhiều giám khảo thích nhất.

Với câu trả lời có chất lượng chủ quan, so sánh thường dễ hơn cho điểm: nói bài hát nào trong hai bài hay hơn dễ hơn cho mỗi bài một điểm cụ thể.

Trong AI, đánh giá so sánh được Anthropic dùng lần đầu năm 2021 để xếp hạng các mô hình. Nó cũng là nền của bảng xếp hạng phổ biến Chatbot Arena của LMSYS, xếp hạng mô hình bằng điểm tính từ các so sánh cặp do cộng đồng thực hiện. Nhiều nhà cung cấp dùng đánh giá so sánh để đánh giá mô hình trong production. Ví dụ (Hình 3-10 của sách): người dùng yêu cầu ChatGPT "write code to write this dictionary into json"; ChatGPT hiện hai câu trả lời cạnh nhau với câu hỏi "Which response do you prefer? Your choice will help make ChatGPT better." — cả hai đều hướng dẫn dùng mô-đun `json` của Python, câu 2 nói rõ thêm hàm `json.dump()`. Hai đầu ra có thể từ hai mô hình khác nhau hoặc cùng mô hình với biến lấy mẫu khác nhau.

Với mỗi yêu cầu, hai hay nhiều mô hình được chọn để trả lời; một người đánh giá (người hoặc AI) chọn bên thắng. Nhiều nhà phát triển cho phép hoà để tránh phải chọn ngẫu nhiên khi hai bản nháp tốt hoặc tệ như nhau.

**Không phải câu hỏi nào cũng nên trả lời bằng sở thích.** Nhiều câu hỏi nên được trả lời bằng tính đúng. Thử hình dung hỏi mô hình "Có mối liên hệ giữa bức xạ điện thoại di động và u não không?" và mô hình đưa hai lựa chọn "Có" và "Không" cho bạn chọn. Bỏ phiếu theo sở thích có thể cho tín hiệu sai, và nếu dùng tín hiệu đó để huấn luyện thì mô hình có thể hành xử lệch. Bắt người dùng chọn còn gây bực mình: bạn hỏi mô hình một câu toán vì không biết đáp án, mô hình đưa hai đáp án khác nhau và hỏi bạn thích cái nào — nếu biết đáp án đúng thì bạn đã không hỏi. Khi thu phản hồi so sánh từ người dùng, một thách thức là xác định câu hỏi nào quyết định được bằng bỏ phiếu sở thích và câu nào không. Bỏ phiếu sở thích chỉ hiệu quả khi người bỏ phiếu hiểu chủ đề; nhìn chung nó hợp với ứng dụng trong đó AI làm thực tập sinh hay trợ lý giúp người dùng làm nhanh việc họ biết làm, không hợp khi người dùng nhờ AI làm việc chính họ không biết làm.

**Không nhầm với A/B test.** Trong A/B test, người dùng mỗi lần chỉ thấy đầu ra của một mô hình ứng viên; trong đánh giá so sánh, người dùng thấy đầu ra của nhiều mô hình cùng lúc.

**Từ trận đấu đến tỷ lệ thắng.** Mỗi lần so sánh gọi là một **trận** (match). Quá trình này cho ra một chuỗi so sánh (Bảng 3-5 của sách):

| Trận số | Mô hình A | Mô hình B | Bên thắng |
|---:|---|---|---|
| 1 | Mô hình 1 | Mô hình 2 | Mô hình 1 |
| 2 | Mô hình 3 | Mô hình 10 | Mô hình 10 |
| 3 | Mô hình 7 | Mô hình 4 | Mô hình 4 |
| … | … | … | … |

Xác suất mô hình A được ưa hơn mô hình B là **tỷ lệ thắng** của A trước B; tính bằng cách xét mọi trận giữa A và B và lấy tỷ lệ phần trăm trận A thắng. Nếu chỉ có hai mô hình, xếp hạng đơn giản: mô hình thắng nhiều hơn xếp trên. Càng nhiều mô hình, xếp hạng càng khó. Ví dụ năm mô hình với tỷ lệ thắng thực nghiệm giữa các cặp (Bảng 3-6 của sách; cột cuối là tỷ lệ trận A được ưa hơn B):

| Cặp số | Mô hình A | Mô hình B | Số trận | A được ưa hơn B |
|---:|---|---|---:|---:|
| 1 | Mô hình 1 | Mô hình 2 | 1.000 | 90% |
| 2 | Mô hình 1 | Mô hình 3 | 1.000 | 40% |
| 3 | Mô hình 1 | Mô hình 4 | 1.000 | 15% |
| 4 | Mô hình 1 | Mô hình 5 | 1.000 | 10% |
| 5 | Mô hình 2 | Mô hình 3 | 1.000 | 60% |
| 6 | Mô hình 2 | Mô hình 4 | 1.000 | 80% |
| 7 | Mô hình 2 | Mô hình 5 | 1.000 | 80% |
| 8 | Mô hình 3 | Mô hình 4 | 1.000 | 70% |
| 9 | Mô hình 3 | Mô hình 5 | 1.000 | 10% |
| 10 | Mô hình 4 | Mô hình 5 | 1.000 | 20% |

Nhìn dữ liệu, không hiển nhiên nên xếp năm mô hình thế nào. Với tín hiệu so sánh, người ta dùng một **thuật toán xếp hạng** (rating algorithm): thường thuật toán tính một điểm cho mỗi mô hình từ tín hiệu so sánh, rồi xếp mô hình theo điểm.

Đánh giá so sánh mới với AI nhưng đã có gần một thế kỷ trong các ngành khác, đặc biệt phổ biến trong thể thao và trò chơi điện tử. Nhiều thuật toán xếp hạng phát triển cho các lĩnh vực đó có thể chuyển sang đánh giá mô hình AI, như **Elo**, **Bradley–Terry** và **TrueSkill**. Chatbot Arena của LMSYS lúc đầu dùng Elo để tính thứ hạng, sau chuyển sang Bradley–Terry vì thấy Elo nhạy với thứ tự của người đánh giá và prompt. Chú thích 23: dù đã thôi dùng Elo, các nhà phát triển Chatbot Arena một thời gian vẫn gọi điểm mô hình là "điểm Elo"; họ co giãn điểm Bradley–Terry để trông giống điểm Elo theo cách khá phức tạp: mỗi điểm nhân với 400 (thang dùng trong Elo) và cộng 1.000 (điểm Elo khởi đầu), rồi co giãn tiếp sao cho mô hình Llama-13b có điểm 800.

*Công thức Elo và Bradley–Terry (người tổng hợp bổ sung, sách không trình bày):*

- **Bradley–Terry:** mỗi mô hình i có một "sức mạnh" βᵢ; xác suất i thắng j là P(i thắng j) = 1 / (1 + e^−(βᵢ − βⱼ)). Chỉ hiệu số βᵢ − βⱼ có ý nghĩa. Các βᵢ được ước lượng một lần từ *toàn bộ* lịch sử trận bằng hợp lý cực đại (chọn β làm xác suất của các kết quả quan sát được lớn nhất), nên thứ tự các trận không ảnh hưởng.
- **Elo:** mỗi mô hình có điểm Rᵢ; xác suất kỳ vọng A thắng B là E_A = 1 / (1 + 10^((R_B − R_A)/400)) — cùng dạng hàm logistic với Bradley–Terry nhưng đổi thang (400 điểm Elo ứng với tỷ số cơ hội 10 ăn 1). Sau mỗi trận, điểm được cập nhật *tuần tự*: R_A mới = R_A + K × (S_A − E_A), với S_A = 1 nếu A thắng, 0 nếu thua, 0,5 nếu hoà, và K là hệ số học (ví dụ 32). Ví dụ: A 1.200 điểm gặp B 1.000 điểm có E_A = 1 / (1 + 10^(−0,5)) ≈ 0,760; nếu A thắng, A lên 1.200 + 32 × 0,24 ≈ 1.207,7; nếu A thua, A xuống 1.200 − 32 × 0,76 ≈ 1.175,7. Vì cập nhật theo từng trận, kết quả phụ thuộc thứ tự trận — chính là điểm yếu khiến Chatbot Arena bỏ Elo.
- **Quy đổi thang (chú thích 23):** điểm theo thang Elo = 1.000 + 400 × β / ln 10, vì e^β = 10^(β/ln 10); nhân 400 và cộng 1.000 là đưa β về thang quen thuộc của Elo.

*Áp dụng cho bảng tỷ lệ thắng năm mô hình ở trên (người tổng hợp tính bằng Python):*

| Mô hình | Tổng số trận thắng / 4.000 | β Bradley–Terry | Điểm theo thang Elo | Hạng |
|---|---:|---:|---:|---:|
| Mô hình 5 | 2.800 (70,0%) | +0,688 | ≈ 1.120 | 1 |
| Mô hình 2 | 2.300 (57,5%) | +0,248 | ≈ 1.043 | 2 |
| Mô hình 3 | 1.800 (45,0%) | −0,171 | ≈ 970 | 3 |
| Mô hình 1 | 1.550 (38,75%) | −0,383 | ≈ 934 | 4 (đồng hạng) |
| Mô hình 4 | 1.550 (38,75%) | −0,383 | ≈ 934 | 4 (đồng hạng) |

Vì mọi cặp có cùng số trận, ước lượng Bradley–Terry xếp hạng đúng theo tổng số trận thắng, và mô hình 1, mô hình 4 đồng điểm. Thứ hạng 5 > 2 > 3 > 1 = 4 dự đoán đúng bên thắng ở 7 trong 10 cặp, không phân định được cặp 1–4 (thực tế mô hình 4 thắng 85%), và dự đoán sai 2 cặp: cặp 1–2 (dự đoán mô hình 1 thắng 35%, thực tế 90%) và cặp 2–5 (dự đoán mô hình 2 thắng 39%, thực tế 80%). Lý do là dữ liệu có vòng không bắc cầu: 1 thắng 2, 2 thắng 5, nhưng 5 thắng 1; và 1 thắng 2, 2 thắng 3, nhưng 3 thắng 1. Không thứ hạng tuyến tính nào khớp hết.

Thử Elo (K = 32, mọi mô hình khởi đầu 1.000) trên đúng 10.000 trận này nhưng xáo trộn thứ tự ngẫu nhiên ba lần cho ba thứ hạng khác nhau: 5 > 2 > 3 > 1 > 4; 5 > 2 > 4 > 3 > 1; 5 > 2 > 1 > 4 > 3 — minh hoạ cho việc Elo nhạy với thứ tự trận.

**Thế nào là thứ hạng đúng.** Một thứ hạng là đúng nếu, với mọi cặp mô hình, mô hình xếp trên có khả năng thắng mô hình xếp dưới trong một trận cao hơn: nếu A xếp trên B, người dùng phải ưa A hơn B quá nửa số lần. Nhìn theo cách này, xếp hạng mô hình là một **bài toán dự đoán**: tính thứ hạng từ kết quả các trận đã qua và dùng nó dự đoán kết quả trận tương lai. Các thuật toán khác nhau có thể cho thứ hạng khác nhau, và không có đáp án chuẩn về thứ hạng đúng; chất lượng thứ hạng được quyết định bởi mức nó dự đoán đúng kết quả trận tương lai. Phân tích của tác giả về thứ hạng của Chatbot Arena (trong kho GitHub của sách) cho thấy thứ hạng tốt, ít nhất với các cặp có đủ số trận.

#### 6.2. Thách thức của đánh giá so sánh (Challenges of Comparative Evaluation, trang PDF 302–308)

Với đánh giá từng điểm, phần nặng nhọc là thiết kế benchmark và độ đo để thu đúng tín hiệu; tính điểm để xếp hạng thì dễ. Với đánh giá so sánh, cả thu tín hiệu lẫn xếp hạng đều khó. Ba thách thức phổ biến:

##### Nghẽn khả năng mở rộng (Scalability bottlenecks, trang PDF 302–304)

Đánh giá so sánh cần nhiều dữ liệu: số cặp mô hình cần so tăng theo bình phương số mô hình. Tháng 1/2024, LMSYS đánh giá 57 mô hình bằng 244.000 lượt so sánh. Nghe nhiều, nhưng chỉ trung bình 153 lượt so sánh mỗi cặp (57 mô hình ứng với 57 × 56 / 2 = 1.596 cặp; 244.000 / 1.596 ≈ 152,9). Đây là con số nhỏ so với phạm vi rộng các tác vụ mà ta muốn mô hình nền tảng làm.

May là không phải lúc nào cũng cần so trực tiếp hai mô hình để biết mô hình nào tốt hơn. Các thuật toán xếp hạng thường giả định **tính bắc cầu**: nếu A xếp trên B và B xếp trên C thì suy ra A xếp trên C; nếu thuật toán chắc chắn A tốt hơn B và B tốt hơn C, nó không cần so A với C. Nhưng không rõ giả định này có đúng với mô hình AI không. Nhiều bài báo phân tích Elo cho đánh giá AI nêu giả định bắc cầu là một giới hạn (Boubdir và cộng sự; Balduzzi và cộng sự; Munos và cộng sự), lập luận rằng sở thích của người không nhất thiết bắc cầu. Ngoài ra, tính không bắc cầu có thể xảy ra vì các cặp mô hình khác nhau được chấm bởi những người khác nhau và trên những prompt khác nhau.

Còn thách thức đánh giá mô hình mới. Với đánh giá độc lập, chỉ cần đánh giá mô hình mới. Với đánh giá so sánh, mô hình mới phải được so với các mô hình hiện có, và điều này có thể làm đổi thứ hạng của các mô hình hiện có. Nó cũng làm khó việc đánh giá mô hình riêng: bạn xây một mô hình cho công ty bằng dữ liệu nội bộ và muốn so với mô hình công khai để quyết định có nên dùng mô hình công khai không; muốn dùng đánh giá so sánh thì có lẽ phải tự thu tín hiệu so sánh và tự dựng bảng xếp hạng, hoặc trả tiền cho một bảng xếp hạng công khai để họ đánh giá riêng.

Có thể giảm nghẽn bằng thuật toán ghép cặp tốt hơn. Tới đây ta giả định mô hình được chọn ngẫu nhiên cho mỗi trận nên mọi cặp xuất hiện trong số trận xấp xỉ bằng nhau. Nhưng không phải cặp nào cũng cần so nhiều như nhau: khi đã chắc kết quả của một cặp thì có thể thôi cho chúng đấu nhau. Thuật toán ghép cặp hiệu quả nên chọn các trận giảm nhiều nhất độ bất định của toàn bộ thứ hạng.

##### Thiếu chuẩn hoá và kiểm soát chất lượng (Lack of standardization and quality control, trang PDF 304–307)

Một cách thu tín hiệu so sánh là crowdsourcing cho cộng đồng như LMSYS Chatbot Arena: ai cũng có thể vào website, nhập một prompt, nhận hai câu trả lời từ hai mô hình ẩn danh và bầu cho câu tốt hơn; tên mô hình chỉ được tiết lộ sau khi bầu. Lợi ích: nắm được nhiều loại tín hiệu và tương đối khó bị gian lận (chú thích 24: khi Chatbot Arena phổ biến hơn, các nỗ lực gian lận cũng phổ biến hơn; không ai thừa nhận với tác giả là đã thử, nhưng nhiều nhà phát triển mô hình nói họ tin đối thủ có làm). Bất lợi: khó áp đặt chuẩn hoá và kiểm soát chất lượng.

Thứ nhất, ai có Internet cũng có thể dùng bất kỳ prompt nào để đánh giá, và không có chuẩn thế nào là câu trả lời tốt hơn. Khó mong tình nguyện viên kiểm chứng sự thật, nên họ có thể vô tình chọn câu nghe hay hơn nhưng sai sự thật. Có người thích câu lịch sự, chừng mực; người khác thích câu không bị lọc. Điều này vừa tốt vừa xấu: tốt vì nắm được sở thích của người ngoài đời thực; xấu vì sở thích đó có thể không hợp với mọi trường hợp sử dụng. Ví dụ người dùng yêu cầu mô hình kể một câu chuyện cười không phù hợp, mô hình từ chối, người dùng có thể bầu chống — trong khi là nhà phát triển ứng dụng, bạn có thể muốn mô hình từ chối. Một số người dùng còn cố tình chọn câu độc hại, làm bẩn thứ hạng.

Thứ hai, crowdsourcing buộc người dùng đánh giá mô hình ngoài môi trường làm việc của họ. Không gắn với thực tế, prompt thử có thể không phản ánh cách mô hình được dùng thật; người ta có thể chỉ dùng prompt đầu tiên nảy ra và ít khi dùng kỹ thuật prompt tinh vi. Trong 33.000 prompt Chatbot Arena công bố năm 2023, 180 prompt là "hello" và "hi", chiếm 0,55% (180 / 33.000 ≈ 0,545%), chưa tính các biến thể như "hello!", "hello.", "hola", "hey". Có nhiều câu đố mẹo; câu "X có 3 chị em gái, mỗi người có một anh/em trai. X có bao nhiêu anh/em trai?" được hỏi 44 lần. Prompt đơn giản dễ trả lời nên khó phân biệt hiệu năng các mô hình; đánh giá bằng quá nhiều prompt đơn giản có thể làm bẩn thứ hạng. Nếu bảng xếp hạng công khai không hỗ trợ dựng context tinh vi, như bổ sung context bằng tài liệu truy xuất từ cơ sở dữ liệu nội bộ, thứ hạng của nó sẽ không phản ánh mô hình làm tốt đến đâu trong hệ thống RAG của bạn; khả năng sinh câu trả lời tốt khác với khả năng truy xuất tài liệu liên quan nhất.

Các cách áp đặt chuẩn hoá:

- Giới hạn người dùng trong một bộ prompt định trước — nhưng có thể làm giảm khả năng của bảng xếp hạng trong việc nắm các trường hợp sử dụng đa dạng. LMSYS thay vào đó cho người dùng dùng prompt bất kỳ, rồi lọc ra prompt khó bằng mô hình nội bộ và chỉ xếp hạng mô hình trên các prompt khó đó.
- Chỉ dùng người đánh giá tin được: đào tạo họ về tiêu chí so sánh hai câu trả lời, hoặc dùng prompt thực tế và kỹ thuật prompt tinh vi. Scale dùng cách này cho bảng xếp hạng so sánh riêng của họ. Nhược điểm: đắt, và có thể giảm mạnh số lượt so sánh thu được.
- Đưa đánh giá so sánh vào sản phẩm, cho người dùng đánh giá mô hình trong quy trình làm việc của họ; ví dụ với tác vụ sinh code, gợi ý hai đoạn code trong trình soạn thảo và để người dùng chọn. Nhiều ứng dụng chat đã làm vậy. Nhưng như đã nói, người dùng có thể không biết đoạn code nào tốt hơn vì không phải chuyên gia; họ cũng có thể không đọc cả hai mà bấm bừa, đưa nhiều nhiễu vào kết quả. Tuy vậy, tín hiệu từ một tỷ lệ nhỏ người dùng bầu đúng đôi khi đủ để xác định mô hình nào tốt hơn.

Một số đội thích AI hơn người làm người đánh giá: AI có thể không giỏi bằng chuyên gia được đào tạo nhưng có thể đáng tin hơn người dùng Internet ngẫu nhiên.

##### Từ hiệu năng tương đối đến hiệu năng tuyệt đối (From comparative performance to absolute performance, trang PDF 307–308)

Với nhiều ứng dụng, không nhất thiết cần mô hình tốt nhất có thể; cần mô hình đủ tốt. Đánh giá so sánh cho biết mô hình nào tốt hơn, không cho biết mô hình tốt đến đâu hay có đủ tốt cho trường hợp sử dụng không. Giả sử thu được thứ hạng mô hình B tốt hơn mô hình A; bất kỳ kịch bản nào sau đây đều có thể đúng:

1. Mô hình B tốt, mô hình A tệ.
2. Cả A và B đều tệ.
3. Cả A và B đều tốt.

Cần hình thức đánh giá khác để biết kịch bản nào đúng. Giả sử đang dùng mô hình A cho chăm sóc khách hàng, giải quyết được 70% ticket. Mô hình B thắng A 51% số lần. Không rõ tỷ lệ thắng 51% chuyển thành bao nhiêu yêu cầu mô hình B giải quyết được. Nhiều người kể với tác giả rằng theo kinh nghiệm của họ, 1% thay đổi tỷ lệ thắng có thể tạo cải thiện hiệu năng rất lớn ở ứng dụng này nhưng chỉ cải thiện tối thiểu ở ứng dụng khác.

Khi quyết định thay A bằng B, sở thích của người không phải là tất cả; còn các yếu tố khác như chi phí. Không biết sẽ cải thiện bao nhiêu thì khó phân tích chi phí–lợi ích: nếu B đắt gấp đôi A, đánh giá so sánh không đủ để biết cải thiện từ B có đáng chi phí thêm không.

*Ví dụ hôm nay (minh hoạ của người tổng hợp):* một ngân hàng thử hai mô hình cho trợ lý tra cứu chính sách tín dụng nội bộ. Trên bảng xếp hạng công khai, mô hình B hơn mô hình A khoảng 30 điểm Elo, tức theo công thức Elo B thắng A khoảng 1 / (1 + 10^(−30/400)) ≈ 54% số trận. Con số này không cho biết B trả lời đúng bao nhiêu phần trăm câu hỏi về chính sách của ngân hàng, cũng không cho biết B có bịa điều khoản không. Ngân hàng vẫn phải dựng bộ câu hỏi có đáp án (đánh giá chính xác) và đo tỷ lệ đúng tuyệt đối của từng mô hình trước khi quyết định trả gấp đôi tiền cho B.

#### 6.3. Tương lai của đánh giá so sánh (The Future of Comparative Evaluation, trang PDF 308–309)

Với nhiều giới hạn như vậy, liệu đánh giá so sánh có tương lai? Có nhiều lợi ích.

Thứ nhất, như đã bàn ở phần Post-Training (Chương 2), so hai đầu ra dễ hơn cho mỗi đầu ra một điểm cụ thể. Khi mô hình mạnh lên và vượt người, người đánh giá có thể không cho điểm cụ thể được nữa, nhưng vẫn có thể nhận ra khác biệt, và đánh giá so sánh có thể là lựa chọn duy nhất. Bài báo Llama 2 chia sẻ rằng khi mô hình viết vượt khả năng của người gán nhãn giỏi nhất, người vẫn cho phản hồi giá trị khi so hai câu trả lời (Touvron và cộng sự, 2023).

Thứ hai, đánh giá so sánh nhắm vào đúng phẩm chất ta quan tâm: sở thích của người. Nó giảm áp lực phải liên tục tạo benchmark mới để đuổi theo năng lực ngày càng mở rộng của AI. Khác với benchmark trở nên vô dụng khi mô hình đạt điểm tuyệt đối, đánh giá so sánh không bao giờ bão hoà chừng nào còn mô hình mới mạnh hơn.

Đánh giá so sánh tương đối khó gian lận, vì không có cách gian lận dễ như huấn luyện mô hình trên dữ liệu tham chiếu. Vì vậy nhiều người tin kết quả của bảng xếp hạng so sánh công khai hơn mọi bảng xếp hạng công khai khác.

Đánh giá so sánh cho tín hiệu phân biệt về mô hình mà không cách nào khác cho được. Với đánh giá offline, nó là bổ sung tốt cho các benchmark; với đánh giá online, nó bổ sung cho A/B test.

### 7. Tóm tắt (Summary, trang PDF 309–311)

Mô hình AI càng mạnh, nguy cơ thất bại nghiêm trọng càng cao, nên đánh giá càng quan trọng. Đồng thời, đánh giá mô hình mạnh, đầu ra mở là khó, khiến nhiều đội quay sang đánh giá bằng người. Có người trong vòng lặp để kiểm tra tính hợp lý luôn có ích, và trong nhiều trường hợp đánh giá bằng người là thiết yếu; nhưng chương này tập trung vào các cách đánh giá tự động.

Chương bắt đầu bằng lý do mô hình nền tảng khó đánh giá hơn mô hình học máy truyền thống. Dù nhiều kỹ thuật đánh giá mới đang được phát triển, đầu tư cho đánh giá vẫn tụt sau đầu tư cho phát triển mô hình và ứng dụng.

Vì nhiều mô hình nền tảng có thành phần mô hình ngôn ngữ, chương đi sâu vào các độ đo mô hình hoá ngôn ngữ như perplexity và cross entropy; nhiều người tác giả gặp thấy chúng khó hiểu, nên chương có phần diễn giải và cách dùng chúng trong đánh giá và xử lý dữ liệu.

Chương sau đó chuyển sang các cách đánh giá câu trả lời mở: functional correctness, điểm tương đồng và AI làm giám khảo. Hai cách đầu là chính xác, còn AI làm giám khảo là chủ quan. Khác với đánh giá chính xác, độ đo chủ quan phụ thuộc nhiều vào giám khảo; điểm của chúng phải được đọc trong bối cảnh giám khảo nào được dùng. Điểm nhằm đo cùng một phẩm chất bởi các giám khảo AI khác nhau có thể không so được. Giám khảo AI, như mọi ứng dụng AI, cần được lặp cải tiến, nghĩa là phán xét của chúng thay đổi; điều đó khiến chúng không đáng tin làm thước đo theo dõi thay đổi của ứng dụng theo thời gian. Dù hứa hẹn, giám khảo AI nên được bổ sung bằng đánh giá chính xác, đánh giá của người, hoặc cả hai.

Khi đánh giá mô hình, có thể đánh giá từng mô hình độc lập rồi xếp theo điểm, hoặc xếp hạng bằng tín hiệu so sánh: trong hai mô hình, mô hình nào tốt hơn? Đánh giá so sánh phổ biến trong thể thao, đặc biệt cờ vua, và đang được dùng nhiều trong đánh giá AI. Cả đánh giá so sánh và quá trình căn chỉnh post-training đều cần tín hiệu sở thích, vốn đắt để thu thập; điều này thúc đẩy phát triển preference model — giám khảo AI chuyên biệt đoán câu trả lời người dùng ưa hơn.

Các độ đo mô hình hoá ngôn ngữ và độ đo tương đồng thiết kế tay đã có từ lâu, còn AI làm giám khảo và đánh giá so sánh chỉ được dùng rộng rãi khi mô hình nền tảng xuất hiện. Nhiều đội đang tìm cách đưa chúng vào quy trình đánh giá. Cách dựng quy trình đánh giá đáng tin cho ứng dụng mở là chủ đề của chương sau.

## Luận điểm cốt lõi

### Mệnh đề

Đánh giá là điểm nghẽn lớn nhất khi đưa ứng dụng dựa trên mô hình nền tảng vào thực tế. Không có một phương pháp đánh giá tự động nào đủ: độ đo mô hình ngôn ngữ chỉ là đại diện gián tiếp; đánh giá chính xác chỉ áp dụng được khi có chức năng kiểm tra được hoặc có dữ liệu tham chiếu; AI làm giám khảo linh hoạt nhưng chủ quan, phụ thuộc mô hình và prompt; đánh giá so sánh nắm sở thích người nhưng chỉ cho thứ hạng tương đối. Người xây dựng ứng dụng phải hiểu mỗi phương pháp đo cái gì và giới hạn của nó, rồi kết hợp chúng.

### Giả định

- Hiệu năng của thành phần mô hình ngôn ngữ tương quan với hiệu năng hạ nguồn (đúng với mô hình pre-trained; kém đúng sau post-training).
- Dữ liệu tham chiếu, nếu dùng, đủ đầy đủ và đúng; embedding đủ tốt để khoảng cách phản ánh nghĩa.
- Giám khảo AI được cố định (mô hình, prompt, tham số lấy mẫu) để điểm so được theo thời gian.
- Sở thích người là bắc cầu và người bình chọn hiểu chủ đề, để thứ hạng từ so sánh cặp có nghĩa.

### Cơ chế

1. Cross entropy H(P, Q) = H(P) + D_KL(P‖Q) tách độ khó vốn có của dữ liệu khỏi phần mô hình học chưa tốt; perplexity 2^H biến nó thành "số lựa chọn hiệu dụng". Đây là thứ mô hình được tối ưu khi huấn luyện, nên nó phản ánh năng lực dự đoán và cả việc mô hình đã thấy văn bản (nhiễm dữ liệu).
2. Functional correctness kiểm tra trực tiếp đầu ra có làm được việc; pass@k gộp xác suất qua k lần thử.
3. Độ tương đồng chuyển câu hỏi "câu trả lời có đúng không" thành "câu trả lời có giống tham chiếu không": theo token (edit distance, n-gram, BLEU, ROUGE) hoặc theo nghĩa (cosine giữa embedding).
4. AI làm giám khảo thay người chấm bằng một hệ thống mô hình + prompt + thang điểm; chất lượng phụ thuộc thiết kế prompt (nhiệm vụ, tiêu chí, thang điểm, ví dụ) và bị ảnh hưởng bởi thiên lệch.
5. Đánh giá so sánh thu kết quả trận cặp rồi dùng thuật toán xếp hạng (Elo, Bradley–Terry) để gán điểm sao cho chênh lệch điểm dự đoán tỷ lệ thắng.

### Bằng chứng và ví dụ tác giả đưa ra

- Thất bại thật: tự tử sau khi chatbot khuyến khích, luật sư nộp chứng cứ bịa, Air Canada bồi thường.
- Benchmark bão hoà: GLUE sau một năm; MMLU thay bằng MMLU-Pro.
- Số liệu đầu tư: bài báo đánh giá LLM tăng từ 2 lên 33 mỗi tháng (nửa đầu 2023); kho công cụ đánh giá ~40 so với ~121 cho mô hình hoá và huấn luyện.
- Ví dụ entropy hình vuông (1 bit, 2 bit; perplexity 4); BPC 3, BPB 3,43.
- Bảng GPT-2: perplexity LAMBADA 35,13 xuống 8,63 khi mô hình lớn lên.
- HumanEval has_close_elements; pass@3 bằng 50% với 5/10 bài.
- Fuyu bị CIDEr 0,4 dù mô tả đúng Big Ben; BLEU của code đúng và sai tương tự trên HumanEval; WMT 2023 có tham chiếu kém.
- GPT-4 đồng ý với người 85% (người với người 81%); AlpacaEval tương quan 0,98 với Chat Arena; 58% đánh giá trên LangChain là AI.
- Nhất quán 65% lên 77,5% với chi phí gấp bốn; faithfulness của MLflow/Ragas/LlamaIndex khác thang; self-bias 10% và 25%; thiên vị độ dài (100 từ sai thắng 50 từ đúng).
- Cappy 360 triệu tham số; BLEURT −2,5 đến 1,0; Prometheus 1–5; PandaLM.
- Chatbot Arena: 57 mô hình, 1.596 cặp, 244.000 lượt, 153 lượt/cặp; 180/33.000 prompt "hello"/"hi"; câu đố hỏi 44 lần; chuyển từ Elo sang Bradley–Terry.
- Mô hình A giải 70% ticket, B thắng 51%: không suy ra được hiệu năng tuyệt đối.

### Kết luận và hàm ý cho người xây dựng ứng dụng AI

- Thiết kế đánh giá xuất phát từ các chỗ hệ thống dễ hỏng, không từ độ đo có sẵn; đừng dựa vào truyền miệng hay "nhìn qua".
- Dùng perplexity để chọn mô hình nền, phát hiện nhiễm dữ liệu, lọc trùng lặp và văn bản bất thường, nhưng không dùng nó để so mô hình đã qua post-training hay lượng tử hoá.
- Ưu tiên functional correctness khi có thể (code, SQL, tác vụ có mục tiêu đo được) và luôn báo rõ k của pass@k.
- Khớp chính xác chỉ cho câu trả lời ngắn; tương đồng từ vựng cần bộ tham chiếu tốt và không thay được kiểm tra đúng/sai; tương đồng ngữ nghĩa phụ thuộc mô hình embedding.
- Khi dùng giám khảo AI: cố định và ghi lại phiên bản mô hình, prompt, tham số; dùng thang phân loại hoặc 1–5 có ví dụ; đổi thứ tự để giảm thiên lệch vị trí; kiểm soát độ dài; tính chi phí (mỗi tiêu chí thêm một lượt gọi); kết hợp với đánh giá chính xác hoặc người.
- Dùng bảng xếp hạng so sánh công khai để lọc sơ bộ, nhưng tự đánh giá tuyệt đối trên dữ liệu và context (RAG) của mình trước khi quyết định, nhất là khi mô hình đắt hơn.

## Thuật ngữ

| Thuật ngữ | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| evaluation / evals | đánh giá | đo chất lượng mô hình hoặc ứng dụng |
| evaluation pipeline | quy trình đánh giá | chuỗi bước đánh giá có hệ thống (Chương 4) |
| word of mouth / vibe check / eyeballing | truyền miệng / kiểm tra theo cảm giác / nhìn qua | các cách đánh giá không hệ thống |
| open-ended / close-ended | mở / đóng | đầu ra tuỳ ý / đầu ra trong tập định trước |
| black box | hộp đen | không biết kiến trúc, dữ liệu, cách huấn luyện |
| benchmark saturation | benchmark bão hoà | mô hình đạt điểm tối đa, benchmark hết giá trị phân biệt |
| downstream performance | hiệu năng hạ nguồn | hiệu năng trên ứng dụng cụ thể |
| language modeling metrics | độ đo mô hình hoá ngôn ngữ | cross entropy, perplexity, BPC, BPB |
| autoregressive language model | mô hình ngôn ngữ tự hồi quy | dự đoán token kế tiếp từ các token trước |
| entropy | entropy | thông tin trung bình mỗi token, đo bằng bit |
| cross entropy | cross entropy | độ khó dự đoán của mô hình trên tập dữ liệu |
| Kullback–Leibler (KL) divergence | phân kỳ KL | độ lệch của phân phối mô hình so với phân phối thật |
| bit / nat | bit / nat | đơn vị thông tin với log cơ số 2 / cơ số e |
| bits-per-character (BPC) | bit mỗi ký tự | cross entropy quy về mỗi ký tự |
| bits-per-byte (BPB) | bit mỗi byte | cross entropy quy về mỗi byte dữ liệu gốc |
| perplexity (PPL) | perplexity | hàm mũ của cross entropy; số lựa chọn hiệu dụng |
| logprob | logprob | logarit xác suất mô hình gán cho token |
| post-training (SFT, RLHF) | post-training | huấn luyện sau pre-training để làm tác vụ và theo sở thích |
| quantization | lượng tử hoá | giảm độ chính xác số để giảm bộ nhớ |
| data contamination | nhiễm dữ liệu | dữ liệu benchmark lọt vào dữ liệu huấn luyện |
| deduplication | khử trùng lặp | loại dữ liệu quá giống dữ liệu đã có |
| exact evaluation | đánh giá chính xác | phán xét không mơ hồ |
| subjective evaluation | đánh giá chủ quan | điểm phụ thuộc người/mô hình chấm |
| functional correctness | functional correctness (đúng chức năng) | hệ thống có làm đúng chức năng mong muốn |
| execution accuracy | độ chính xác khi thực thi | functional correctness cho code |
| unit test / test case | unit test / ca kiểm thử | chạy code trong tình huống và so đầu ra kỳ vọng |
| pass@k | pass@k | tỷ lệ bài có ít nhất một trong k mẫu qua hết test |
| text-to-SQL | text-to-SQL | sinh truy vấn SQL từ ngôn ngữ tự nhiên |
| reference data / ground truth / canonical response | dữ liệu tham chiếu / đáp án chuẩn | câu trả lời đúng dùng để so |
| reference-based / reference-free | dựa trên tham chiếu / không cần tham chiếu | độ đo cần hoặc không cần tham chiếu |
| exact match | khớp chính xác | đầu ra trùng hẳn tham chiếu |
| lexical similarity | tương đồng từ vựng | mức chồng lấp token |
| fuzzy matching / approximate string matching | so khớp mờ / so khớp chuỗi gần đúng | so chuỗi theo số phép sửa |
| edit distance | khoảng cách sửa | số phép xoá, chèn, thay ít nhất |
| n-gram, unigram, bigram | n-gram | dãy n token liên tiếp |
| BLEU, ROUGE, METEOR++, TER, CIDEr | (giữ nguyên) | các độ đo tương đồng từ vựng |
| semantic similarity / semantic textual similarity | tương đồng ngữ nghĩa | mức gần nhau về nghĩa |
| embedding | embedding | vector số biểu diễn ý nghĩa |
| cosine similarity | độ tương đồng cosine | tích vô hướng chia tích độ dài, từ −1 đến 1 |
| dot product / Euclidean (L2) norm | tích vô hướng / chuẩn Euclid | phép tính trong công thức cosine |
| BERTScore, MoverScore | (giữ nguyên) | độ đo tương đồng ngữ nghĩa |
| joint / multimodal embedding space | không gian embedding chung / đa phương thức | nhiều loại dữ liệu trong một không gian |
| text encoder / image encoder / projection matrix | bộ mã hoá văn bản / bộ mã hoá ảnh / ma trận chiếu | thành phần của CLIP |
| MTEB | MTEB | benchmark chất lượng embedding |
| AI as a judge / LLM as a judge | AI làm giám khảo | dùng AI chấm đầu ra của AI |
| AI judge | giám khảo AI | mô hình + prompt dùng để chấm |
| scoring system (classification, discrete, continuous) | hệ thống điểm | phân loại; số rời rạc; số liên tục |
| groundedness, relevance, coherence, fluency, faithfulness | bám nguồn, liên quan, mạch lạc, trôi chảy, trung thành | tiêu chí chấm phổ biến |
| guardrail | guardrail | rào chắn an toàn, ví dụ lọc câu trả lời trước khi hiển thị |
| spot-checking | spot-check (lấy mẫu kiểm tra) | chỉ chấm một phần câu trả lời |
| self-bias | tự thiên vị | giám khảo ưa câu trả lời của chính nó |
| first-position bias / recency bias | thiên vị vị trí đầu / thiên lệch gần đây | AI ưa câu đầu; người ưa câu cuối |
| verbosity bias | thiên vị độ dài | ưa câu dài bất kể chất lượng |
| self-evaluation / self-critique / self-ask | tự đánh giá / tự phê bình | mô hình chấm và sửa câu của chính nó |
| reward model | reward model (mô hình thưởng) | chấm cặp (prompt, câu trả lời) |
| reference-based judge | giám khảo dựa trên tham chiếu | chấm câu trả lời so với tham chiếu |
| preference model | preference model (mô hình sở thích) | đoán câu nào trong hai câu được ưa hơn |
| pointwise evaluation | đánh giá từng điểm | chấm từng mô hình độc lập |
| comparative evaluation | đánh giá so sánh | cho mô hình đấu cặp rồi xếp hạng |
| Likert scale | thang Likert | thang điểm mức độ, ví dụ 1–5 |
| match / win rate | trận / tỷ lệ thắng | một lần so sánh / tỷ lệ trận thắng |
| rating algorithm | thuật toán xếp hạng | tính điểm mỗi mô hình từ kết quả trận |
| Elo, Bradley–Terry, TrueSkill | (giữ nguyên) | các thuật toán xếp hạng |
| transitivity | tính bắc cầu | A > B và B > C thì A > C |
| matching algorithm | thuật toán ghép cặp | chọn cặp mô hình cho trận tiếp theo |
| crowdsourcing | crowdsourcing (huy động cộng đồng) | thu tín hiệu từ người dùng tình nguyện |
| leaderboard | bảng xếp hạng | thứ hạng công khai các mô hình |
| A/B testing | A/B test | mỗi người dùng thấy một phiên bản |
| offline / online evaluation | đánh giá offline / online | trước khi triển khai / trong production |

## Câu nói đáng nhớ

> "Without a way to quality control AI outputs, the risk of AI might outweigh its benefits for many applications." — trang PDF 232
>
> *Dịch: Nếu không có cách kiểm soát chất lượng đầu ra của AI, rủi ro của AI có thể lớn hơn lợi ích của nó với nhiều ứng dụng.*
>
> Ý nghĩa: đặt đánh giá làm điều kiện tiên quyết, không phải bước phụ, của mọi ứng dụng AI.

> "Without a clear understanding of where your system fails, no amount of evaluation metrics or tools can make the system robust." — trang PDF 233
>
> *Dịch: Nếu không hiểu rõ hệ thống của bạn hỏng ở đâu, không độ đo hay công cụ đánh giá nào làm hệ thống vững được.*
>
> Ý nghĩa: đánh giá bắt đầu từ phân tích lỗi, không từ việc chọn độ đo.

> "First, the more intelligent AI models become, the harder it is to evaluate them." — trang PDF 234
>
> *Dịch: Thứ nhất, mô hình AI càng thông minh thì càng khó đánh giá.*
>
> Ý nghĩa: nghịch lý cốt lõi giải thích vì sao đánh giá trở nên khó hơn theo thời gian.

> "If cross entropy measures how difficult it is for a model to predict the next token, perplexity measures the amount of uncertainty it has when predicting the next token." — trang PDF 246–247
>
> *Dịch: Nếu cross entropy đo mô hình gặp khó đến đâu khi dự đoán token kế tiếp, thì perplexity đo mức không chắc chắn của nó khi dự đoán token kế tiếp.*
>
> Ý nghĩa: cách gọn nhất để phân biệt hai độ đo hay bị lẫn.

> "An AI judge is not just a model—it's a system that includes both a model and a prompt." — trang PDF 281
>
> *Dịch: Giám khảo AI không chỉ là một mô hình — nó là một hệ thống gồm cả mô hình và prompt.*
>
> Ý nghĩa: giải thích vì sao điểm của giám khảo AI chỉ có nghĩa khi biết cả mô hình lẫn prompt.

> "Do not trust any AI judge if you can't see the model and the prompt used for the judge." — trang PDF 287
>
> *Dịch: Đừng tin bất kỳ giám khảo AI nào nếu bạn không xem được mô hình và prompt nó dùng.*
>
> Ý nghĩa: quy tắc thực hành trực tiếp rút ra từ vấn đề tiêu chí mơ hồ.

> "A very important thing to keep in mind is that not all questions should be answered by preference." — trang PDF 297
>
> *Dịch: Một điều rất quan trọng cần nhớ là không phải câu hỏi nào cũng nên được trả lời bằng sở thích.*
>
> Ý nghĩa: ranh giới giữa nơi đánh giá so sánh hữu ích và nơi phải dùng tính đúng.

> "Comparative evaluation tells us which model is better. It doesn't tell us how good a model is or whether this model is good enough for our use case." — trang PDF 307
>
> *Dịch: Đánh giá so sánh cho biết mô hình nào tốt hơn. Nó không cho biết mô hình tốt đến đâu hay có đủ tốt cho trường hợp sử dụng của ta không.*
>
> Ý nghĩa: giới hạn quan trọng nhất của bảng xếp hạng khi ra quyết định kinh doanh.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương bao quát gần đủ bộ công cụ đánh giá tự động mà một kỹ sư AI năm 2024 cần, theo trình tự hợp lý từ độ đo nền (perplexity) đến phương pháp đang lên (AI làm giám khảo, so sánh cặp). Phần độ đo ngôn ngữ giải thích mối quan hệ giữa bốn độ đo dễ lẫn (cross entropy, perplexity, BPC, BPB) bằng ví dụ hình vuông dễ hình dung, và chỉ ra các công dụng thực hành ít được nói tới (phát hiện nhiễm dữ liệu, khử trùng lặp, phát hiện văn bản bất thường) cùng cảnh báo về post-training. Phần AI làm giám khảo cân bằng: không cổ vũ mù quáng mà liệt kê cụ thể các giới hạn có số liệu (nhất quán 65–77,5%, self-bias 10–25%, chi phí gấp bốn) và đưa so sánh trực tiếp ba prompt faithfulness thật. Câu "giám khảo AI là một hệ thống gồm mô hình và prompt" là khung tư duy hữu ích. Phần đánh giá so sánh nêu rõ khác biệt giữa thứ hạng tương đối và hiệu năng tuyệt đối — điều thường bị bỏ qua khi đọc bảng xếp hạng.

### Những chỗ đơn giản hoá hoặc chưa chặt

- **Thiếu công thức cho các độ đo được nêu tên:** sách không cho công thức entropy, BLEU, ROUGE, Elo hay Bradley–Terry; người đọc không tự tính được. Bản tổng hợp đã bổ sung.
- **Ví dụ tương đồng từ vựng lẫn precision với recall:** con số 60% của câu B là recall; tính theo precision chỉ 43%. Sách cũng không nói rằng chọn precision hay recall làm đổi kết luận về câu nào giống hơn.
- **Bảng tỷ lệ thắng năm mô hình (Bảng 3-6) có vòng không bắc cầu** (1 thắng 2, 2 thắng 5, 5 thắng 1) mà sách không phân tích; đây lại là ví dụ minh hoạ hay cho giới hạn bắc cầu được bàn ngay sau đó.
- **Phân loại tương đồng ngữ nghĩa vào "đánh giá chính xác"** là quy ước tranh cãi, sách tự thừa nhận trong khung cảnh báo.
- **"Perplexity 3 nghĩa là 1 cơ hội trong 3"** chỉ đúng khi mọi lựa chọn đồng khả năng; với phân phối lệch, mô hình có thể đoán đúng token phổ biến nhất thường xuyên hơn 1/3.
- **Một số số liệu và nhãn không khớp:** Hình 3-2 (khoảng 40 kho) so với lời văn (hơn 50 kho); nhãn "Text embedding" cho vector ảnh trong Hình 3-6; công thức cosine bị lỗi LaTeX; "greatest common denominator".
- **Số liệu thiên lệch lấy từ các mô hình 2023** (GPT-4, Claude-v1, GPT-3.5); mức thiên lệch của các mô hình mới có thể khác, như chính sách gợi ý.

### Những gì đã thay đổi từ cuối 2024 (theo hiểu biết của người tổng hợp)

- **Chatbot Arena** đổi tên thành LMArena và trở thành công ty riêng (2025). Từ giữa 2024 Arena thêm "style control" để tách ảnh hưởng của độ dài và định dạng Markdown khỏi điểm — một cách xử lý thiên vị độ dài ở phía người bình chọn. Năm 2025, nghiên cứu "The Leaderboard Illusion" (Singh và cộng sự) chỉ ra một số nhà cung cấp lớn thử riêng nhiều biến thể rồi chỉ công bố biến thể tốt nhất; vụ Meta đưa một bản Llama 4 "thử nghiệm" tối ưu cho Arena (4/2025) làm lo ngại về gian lận mà sách nêu ở chú thích 24 trở thành sự kiện công khai.
- **Benchmark bão hoà nhanh hơn nữa:** HumanEval, MMLU và cả MMLU-Pro gần bão hoà với các mô hình hàng đầu; cộng đồng chuyển sang GPQA Diamond, SWE-bench Verified, Humanity's Last Exam, ARC-AGI-2 và các benchmark agent.
- **Mô hình suy luận (reasoning models)** như dòng o1/o3, DeepSeek-R1 làm phổ biến việc dùng test-time compute; AI làm giám khảo được dùng rộng rãi làm reward cho học tăng cường (RL from AI feedback, giám khảo theo rubric), và các giám khảo chuyên biệt như Prometheus 2 ra đời đúng theo hướng tác giả kỳ vọng.
- **Mô hình embedding** đã có thế hệ mới (ví dụ Cohere Embed v4, các mô hình embedding mở xếp đầu MTEB như các dòng của Qwen và NVIDIA); kích thước vector và kỹ thuật Matryoshka (cắt ngắn vector) phổ biến hơn.
- **Nhiều mô hình thương mại vẫn không công bố logprob** hoặc chỉ công bố top-k logprob, nên giới hạn "không tính được perplexity" mà sách nêu vẫn còn nguyên.

### Liên hệ các chương khác

- [00-loi-noi-dau.md](00-loi-noi-dau.md): Lời nói đầu giới thiệu cấu trúc sách và vị trí của hai chương đánh giá.
- [C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md](C01-gioi-thieu-xay-dung-ung-dung-ai-voi-mo-hinh-nen-tang.md): lịch sử mô hình ngôn ngữ từ Shannon, khái niệm token, và vai trò của đánh giá trong kỹ thuật AI.
- [C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md): post-training (SFT, RLHF, reward model, dữ liệu sở thích), biến lấy mẫu, logprob, test-time compute — các khái niệm chương này dùng lại.
- [C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md): áp dụng các phương pháp của chương để chọn mô hình, bàn nhiễm dữ liệu benchmark, dựng quy trình đánh giá và cân bằng chi phí–độ tự tin của spot-check.
- [C05-prompt-engineering.md](C05-prompt-engineering.md): thực hành tốt khi viết prompt, áp dụng cho prompt giám khảo.
- [C06-rag-va-agent.md](C06-rag-va-agent.md): embedding và tìm kiếm vector bằng cosine trong RAG.
- [C07-finetuning.md](C07-finetuning.md): lượng tử hoá và ảnh hưởng của nó lên perplexity.
- [C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md): khử trùng lặp dữ liệu bằng độ tương đồng và perplexity; dùng AI tạo và chấm dữ liệu.
- [C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md): guardrail trong production và thu phản hồi so sánh từ người dùng.

### Vận dụng

- **Kỹ sư xây dựng ứng dụng AI:**
  - Liệt kê các chỗ ứng dụng có thể hỏng (bịa thông tin, sai định dạng, độc hại, trả lời lạc đề) trước khi chọn độ đo; với mỗi chỗ, chọn phương pháp rẻ nhất mà chính xác đủ: kiểm tra định dạng bằng code, khớp chính xác cho trường ngắn, functional correctness cho code/SQL, giám khảo AI cho tiêu chí mềm.
  - Khi dùng giám khảo AI, lưu phiên bản mô hình, prompt và tham số lấy mẫu cùng với mỗi điểm; dùng thang phân loại hoặc 1–5 có ví dụ cho mỗi mức; chạy so sánh cặp hai chiều (đổi thứ tự A/B) để triệt thiên vị vị trí; kiểm tra độ đồng thuận của giám khảo với một mẫu nhỏ do người chấm trước khi tin nó.
  - Ước tính chi phí: mỗi tiêu chí chấm là thêm một lượt gọi API; dùng spot-check theo tỷ lệ và giám khảo nhỏ hơn cho production, giám khảo mạnh cho phân tích offline.
  - Đọc bảng xếp hạng công khai như bộ lọc sơ bộ: chênh lệch vài chục điểm Elo chỉ tương ứng tỷ lệ thắng 52–55%; luôn đo lại trên dữ liệu và context RAG của mình.
  - Dùng perplexity của mô hình mở trên benchmark nội bộ để phát hiện rò rỉ dữ liệu, và để lọc dữ liệu huấn luyện trùng lặp hoặc bất thường.
- **Người làm tài chính, kinh tế dùng AI:**
  - Với tác vụ có đáp án kiểm chứng được (trích số liệu từ báo cáo tài chính, tính chỉ số, phân loại giao dịch), ưu tiên đánh giá chính xác: so với bộ dữ liệu tham chiếu do chuyên viên lập, tính tỷ lệ đúng tuyệt đối thay vì tin cảm nhận "câu trả lời nghe hợp lý".
  - Với tác vụ mở (tóm tắt báo cáo, viết nhận định thị trường), giám khảo AI có ích nhưng dễ thưởng cho bài dài và trơn tru; cần tiêu chí cụ thể ("mọi con số phải có trong tài liệu nguồn", tức faithfulness) và kiểm tra ngẫu nhiên bởi người có chuyên môn.
  - Khi so hai nhà cung cấp mô hình có giá khác nhau, đánh giá so sánh chỉ cho biết bên nào được ưa hơn; để phân tích chi phí–lợi ích phải quy về hiệu năng tuyệt đối (tỷ lệ việc làm đúng, thời gian tiết kiệm) — giống phân biệt xếp hạng tín nhiệm tương đối với xác suất vỡ nợ tuyệt đối.
  - Bài học về benchmark bão hoà và nhiễm dữ liệu tương tự hiện tượng "quá khớp" (overfitting) của chiến lược giao dịch kiểm định ngược (backtest) trên dữ liệu đã thấy: điểm cao trên dữ liệu công khai không bảo đảm hiệu năng ngoài mẫu.
