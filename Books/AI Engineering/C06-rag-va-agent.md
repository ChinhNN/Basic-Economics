# Chương 6 — RAG và agent (RAG and Agents)

**Nguồn:** Chip Huyen, *AI Engineering: Building Applications with Foundation Models*, O'Reilly Media, ấn bản đầu tiên (12/2024), Chương 6 "RAG and Agents", trang PDF 494–593.
**Tác giả:** Chip Huyen — nhà văn và nhà khoa học máy tính chuyên về hệ thống học máy; từng làm ở NVIDIA, Snorkel AI, sáng lập một startup hạ tầng AI (sau được mua lại), dạy hệ thống học máy ở Đại học Stanford; tác giả *Designing Machine Learning Systems* (O'Reilly 2022) và bốn sách tiếng Việt bán chạy, trong đó có bộ *Xách ba lô lên và đi*.
**Vị trí trong lập luận của cả cuốn sách:** Chương 5 ([C05-prompt-engineering.md](C05-prompt-engineering.md)) dạy cách viết *chỉ dẫn* (instruction) cho mô hình — phần chung cho mọi truy vấn. Chương 6 bàn phần còn lại của đầu vào: *context* riêng cho từng truy vấn, và hai mẫu hình dựng context phổ biến nhất là RAG (truy xuất rồi sinh) và agent (mô hình dùng công cụ, lập kế hoạch, hành động). Chương dùng lại nhiều khái niệm của các chương trước: embedding và đánh giá bằng AI judge ([C03-phuong-phap-danh-gia.md](C03-phuong-phap-danh-gia.md)), đánh giá hệ thống theo từng thành phần ([C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md)), chain-of-thought, tự phê bình, độ dài context và tấn công prompt ([C05-prompt-engineering.md](C05-prompt-engineering.md)), semantic parsing và đầu ra có cấu trúc ([C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md)). RAG và agent đều là phương pháp dựa trên prompt — không sửa mô hình; Chương 7 ([C07-finetuning.md](C07-finetuning.md)) chuyển sang sửa chính mô hình bằng finetuning. Chương 10 ([C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md)) đặt RAG, agent và bộ nhớ vào kiến trúc tổng thể của một ứng dụng.
**Ý chính:** **Mô hình trả lời sai và bịa nhiều hơn khi thiếu thông tin, nên phải dựng context riêng cho từng truy vấn: RAG lấy thông tin liên quan từ nguồn ngoài, còn agent cho mô hình công cụ để vừa thu thập thông tin vừa tác động lên môi trường; chất lượng của cả hai phụ thuộc vào bộ truy xuất (retriever), khả năng lập kế hoạch của mô hình và hệ thống bộ nhớ.** Phần RAG: mẫu "truy xuất rồi sinh" có từ Chen và cộng sự (2017), tên RAG do Lewis và cộng sự (2020) đặt; tác giả cho rằng context dài không xoá bỏ RAG vì dữ liệu luôn vượt context và mô hình không dùng tốt context dài (Anthropic gợi ý: kho tri thức dưới 200.000 token, khoảng 500 trang, thì đưa thẳng vào prompt). Retriever có hai việc: lập chỉ mục và truy vấn. Truy xuất dựa trên từ khoá (TF-IDF, chỉ mục ngược của Elasticsearch, BM25) nhanh, rẻ, mạnh ngay từ đầu nhưng khó cải thiện; truy xuất dựa trên embedding (cơ sở dữ liệu vector, k-NN hoặc các thuật toán ANN như LSH, HNSW, product quantization, IVF với 100–10.000 vector mỗi cụm, Annoy) hiểu ngữ nghĩa, cải thiện được bằng finetuning nhưng đắt hơn — chi tiêu cho cơ sở dữ liệu vector có thể bằng một phần năm tới một nửa chi tiêu cho API mô hình — và dễ làm mất từ khoá như mã lỗi. Hệ thống thật thường kết hợp (hybrid search): lọc rẻ rồi xếp hạng lại, hoặc gộp nhiều bảng xếp hạng bằng RRF với hằng số k = 60. Bốn chiến thuật tối ưu truy xuất: chia đoạn (chunking), xếp hạng lại, viết lại truy vấn, và truy xuất có ngữ cảnh (Anthropic thêm 50–100 token mô tả vào mỗi đoạn). RAG mở rộng sang ảnh (CLIP) và bảng (text-to-SQL). Phần agent: agent là bất cứ thứ gì cảm nhận và tác động lên môi trường; năng lực của nó do bộ công cụ (tăng cường tri thức, mở rộng năng lực, hành động ghi) và bộ lập kế hoạch quyết định. Agent cần mô hình mạnh vì lỗi cộng dồn: đúng 95% mỗi bước thì sau 10 bước chỉ còn khoảng 60%, sau 100 bước còn 0,6%. Kế hoạch nên tách khỏi thực thi, được kiểm định trước khi chạy, có thể viết bằng tên hàm hoặc ngôn ngữ tự nhiên, theo luồng tuần tự, song song, rẽ nhánh hay vòng lặp; phản tư (ReAct, Reflexion) giúp sửa lỗi nhưng tốn token. Chọn công cụ phải thử nghiệm (Toolformer 5 công cụ, Chameleon 13, Gorilla 1.645 API). Agent hỏng theo ba kiểu: lỗi lập kế hoạch, lỗi công cụ, kém hiệu quả. Cuối chương là bộ nhớ ba tầng (tri thức nội tại, bộ nhớ ngắn hạn là context, bộ nhớ dài hạn là nguồn ngoài) và các chiến lược quản lý bộ nhớ (FIFO, tóm tắt, phản tư).

> **Lưu ý:**
> - **Định nghĩa IDF không nhất quán (trang PDF 504):** lời văn nói IDF là tổng số tài liệu chia cho số tài liệu chứa từ ("10 / 5 = 2"), nhưng công thức ngay dưới lại là IDF(t) = log(N / C(t)). Theo công thức, ví dụ cho log(2) ≈ 0,693 (log tự nhiên) hoặc 0,301 (log cơ số 10), không phải 2. Thứ tự xếp hạng không đổi vì log là hàm đồng biến, nhưng giá trị số khác; công thức có log là dạng chuẩn.
> - **Công thức BM25 không được nêu:** sách chỉ nói BM25 "chuẩn hoá tần suất từ theo độ dài tài liệu". Bản tổng hợp chép công thức BM25 chuẩn (Robertson và Zaragoza 2009, tài liệu sách dẫn ở chú thích) và ghi rõ là người tổng hợp bổ sung.
> - **"Elasticsearch và BM25" được gọi là hai giải pháp ngang hàng (nhận xét của người tổng hợp):** Elasticsearch là phần mềm tìm kiếm, BM25 là hàm chấm điểm; Elasticsearch (qua Lucene) dùng BM25 làm hàm chấm điểm mặc định từ phiên bản 5.0 (2016). So sánh không sai về thực hành nhưng trộn hai cấp khác nhau.
> - **RRF (trang PDF 519–520):** ví dụ trực quan (hạng 1 được 1 điểm, hạng 2 được 0,5 điểm, tổng 1,5) tương ứng với k = 0; với k = 60 như sách khuyên, cùng tài liệu đó được 1/61 + 1/62 ≈ 0,0325. Lý do "tránh chia cho 0" chỉ cần khi hạng đánh số từ 0; vai trò chính của k là làm phẳng chênh lệch giữa các hạng đầu (người tổng hợp tính).
> - **Tham chiếu chương sai (trang PDF 506):** sách viết "Chapter 4 discusses measuring the lexical similarity between two texts based on their n-gram overlap"; phần độ tương đồng từ vựng (lexical similarity) và n-gram nằm ở Chương 3 ([C03-phuong-phap-danh-gia.md](C03-phuong-phap-danh-gia.md)); Chương 4 chỉ nhắc n-gram khi bàn nhiễm bẩn dữ liệu benchmark.
> - **Ví dụ lập kế hoạch Kitty Vogue không nhất quán (trang PDF 555–558):** lời dẫn nói agent có ba công cụ (lấy sản phẩm theo giá, lấy sản phẩm bán chạy, lấy thông tin sản phẩm), nhưng prompt liệt kê năm hành động và không có hàm "theo giá"; prompt khai báo `get_today_date()` nhưng kế hoạch sinh ra gọi `get_time()`; prompt khai báo `fetch_top_products` nhưng ví dụ tham số gọi `retrieve_top_products`. Có thể tác giả cố ý minh hoạ rằng mô hình gọi sai tên hàm, nhưng sách không nói vậy.
> - **Hình 6-11 (trang PDF 566):** ví dụ "If" được dán nhãn "Example: customer support" nhưng nội dung là phân tích báo cáo lợi nhuận rồi mua hay bán cổ phiếu; ví dụ vòng lặp trong hình (truy vết bài đăng lan truyền ngược về người đăng gốc) khác ví dụ trong lời văn (sinh số ngẫu nhiên tới khi ra số nguyên tố). Bản tổng hợp chép cả hai.
> - **Bảng 6-3 (trang PDF 533) bị cắt cột:** cột cuối hiển thị "Unit" với các giá trị 10,99, 25, 18 — thực ra là đơn giá; Hình 6-7 cho đủ cột: Giá/đơn vị (USD), Số lượng (Units), Thành tiền. Câu SQL bị cắt ở cuối dòng ("INTERVAL 7 D…"), đúng là `INTERVAL 7 DAY);`. Bản tổng hợp chép bảng đầy đủ từ Hình 6-7.
> - **Lỗi chính tả:** "Vogager" là Voyager (Wang và cộng sự 2023); câu "tools … that help augment your agent's knowledge of your agent" (trang PDF 541) có lẽ định viết "knowledge of your organization/environment".
> - **Hình 6-14 và lời văn (nhận xét của người tổng hợp):** sách nói ChatGPT "có vẻ ưa" chú thích ảnh còn GPT-4 "ưa" truy xuất tri thức. Số trong hình: trên ScienceQA ChatGPT gọi chú thích ảnh 10% số chương trình so với GPT-4 6%, GPT-4 gọi truy xuất tri thức 81% so với ChatGPT 72%; khác biệt có nhưng nhỏ, từ "ưa" hơi mạnh.
> - **Hình 6-15:** tổng xác suất ra khỏi nút image_captioner là 0,01 + 0,79 + 0,21 = 1,01 do làm tròn.
> - **Kiểu dữ liệu trong Hình 6-10:** tham số `lbs` khai báo `"type": "int"`; JSON Schema dùng `"integer"` hoặc `"number"` (số cân thường không nguyên). Đây là mã giả, sách nói rõ không theo API cụ thể.
> - **Lớp chữ:** các chú thích cuối chương mất số; người tổng hợp khớp 16 chú thích theo nội dung và số trên ảnh trang. Câu "context recall To compute" thiếu dấu chấm. Các hình (6-1 tới 6-16) đều đọc từ ảnh trang.
> - **Quy ước dịch:** giữ tiếng Anh cho RAG, agent, retriever, embedding, chunk, token, prompt, context, finetuning, reranking, function calling, benchmark; "term-based retrieval" dịch là "truy xuất dựa trên từ khoá" (sách cũng gọi là lexical retrieval), "embedding-based retrieval" là "truy xuất dựa trên embedding" (sách cũng gọi là semantic retrieval — truy xuất ngữ nghĩa); "planning" là lập kế hoạch, "reflection" là phản tư, "tool inventory" là bộ công cụ, "write actions" là hành động ghi. Sách dùng "document" cho cả tài liệu và đoạn (chunk); bản tổng hợp cũng vậy.
> - **Những gì đã đổi sau 2024 (theo hiểu biết của người tổng hợp):** xem mục "Những gì đã thay đổi từ cuối 2024" ở cuối file (MCP, mô hình suy luận, agent dùng máy tính, deep research, context 1 triệu token trở lên).

## Sơ đồ

### Phần mở đầu Chương 6 — chỉ dẫn và context (Chapter 6 introduction, trang PDF 494–495)

```text
       Để làm một việc, mô hình cần hai thứ:
       ┌──────────────────────────────┬──────────────────────────────┐
       │ CHỈ DẪN (instruction)         │ CONTEXT (thông tin cần thiết) │
       │ chung cho mọi truy vấn        │ riêng cho từng truy vấn       │
       │ → Chương 5                    │ → Chương 6                    │
       └──────────────────────────────┴──────────────────────────────┘
                                │
                                ▼
       Thiếu context, mô hình dễ trả lời sai và bịa (hallucinate),
       giống người thiếu thông tin
                                │
                                ▼
       Hai mẫu hình dựng context chiếm ưu thế:
       · RAG: truy xuất thông tin từ nguồn dữ liệu bên ngoài
       · Agent: dùng công cụ (tìm web, API tin tức…) để thu thập
         thông tin, và còn làm được nhiều hơn: tác động trực tiếp
         lên thế giới, tự động hoá nhiều việc
```

### Mục "RAG" — nguồn gốc, lý do tồn tại khi context dài ra (RAG, trang PDF 495–498)

```text
       RAG: tăng chất lượng sinh bằng cách truy xuất thông tin liên quan
       từ bộ nhớ ngoài (cơ sở dữ liệu nội bộ, lịch sử chat, internet)
                                │
                                ▼
       2017 Chen và cộng sự: lấy 5 trang Wikipedia liên quan nhất, rồi
       mô hình đọc (document reader, một mạng LSTM) để trả lời
       Ví dụ: "Bao nhiêu cư dân Warsaw nói tiếng Ba Lan năm 1933?"
       → trả lời 833.500
       2020 Lewis và cộng sự đặt tên RAG cho bài toán cần nhiều tri
       thức: chỉ đưa phần liên quan nhất vào mô hình → trả lời chi tiết
       hơn, bớt bịa
                                │
                                ▼
       RAG dựng context riêng cho từng truy vấn; tương đương với
       feature engineering của học máy cổ điển
                                │
                                ▼
       Context dài có giết RAG không? Tác giả: KHÔNG
       · dữ liệu luôn tăng nhanh hơn độ dài context
       · mô hình xử lý được context dài chưa chắc dùng tốt; mỗi token
         thêm tốn tiền và có thể thêm độ trễ
       · Anthropic: kho tri thức < 200.000 token (≈ 500 trang) thì đưa
         thẳng vào prompt của Claude, không cần RAG
```

### Mục "RAG Architecture" — retriever và generator (trang PDF 498–500)

```text
       Người dùng ──prompt──┬──────────────► RETRIEVER ◄── bộ nhớ ngoài
                            │                    │       (tài liệu, bảng,
                            │          context liên quan  lịch sử chat)
                            │                    ▼
                            └──────────────► MÔ HÌNH SINH ──► phản hồi
                                                              cho người dùng
                                │
                                ▼
       · Bài gốc của Lewis: huấn luyện retriever và mô hình sinh cùng
         nhau; nay thường tách rời, dùng hàng có sẵn; finetune cả hệ
         thống đầu–cuối có thể cải thiện đáng kể
       · Thành bại của RAG phụ thuộc chất lượng retriever
       · Retriever có hai việc: LẬP CHỈ MỤC (xử lý dữ liệu để truy xuất
         nhanh) và TRUY VẤN (gửi truy vấn để lấy dữ liệu liên quan)
       · Tài liệu dài 10 token hay 1 triệu token → chia thành đoạn
         (chunk); "tài liệu" trong chương chỉ cả tài liệu lẫn đoạn
```

### Mục "Retrieval Algorithms" — xếp hạng theo độ liên quan; thưa và dày (trang PDF 500–503)

```text
       Truy xuất thông tin có từ thập niên 1920 (bằng sáng chế "máy
       thống kê" của Emanuel Goldberg); là xương sống của máy tìm kiếm,
       hệ gợi ý, phân tích log
                                │
                                ▼
       Cốt lõi: xếp hạng tài liệu theo điểm liên quan với truy vấn;
       các thuật toán khác nhau ở cách tính điểm
                                │
       ┌────────────────────────┴────────────────────────┐
       ▼                                                 ▼
  DỰA TRÊN TỪ KHOÁ                               DỰA TRÊN EMBEDDING
  (thường gọi là "thưa": vector                  (thường gọi là "dày":
  one-hot, gần hết là 0; ví dụ                   phần lớn giá trị khác 0)
  {food:0, banana:1, slug:2} thì
  "banana" là [0, 1, 0])
                                │
                                ▼
       Sách không chia thưa/dày vì SPLADE dùng embedding thưa (BERT +
       điều chuẩn đẩy phần lớn giá trị về 0) nhưng hoạt động giống
       truy xuất embedding dày hơn là truy xuất từ khoá
```

### Mục "Term-based retrieval" — TF, IDF, TF-IDF, chỉ mục ngược, BM25 (trang PDF 503–507)

```text
       Cách thẳng nhất: tìm tài liệu chứa từ khoá ("lexical retrieval")
       Hai vấn đề:
       1. quá nhiều tài liệu chứa từ → ưu tiên tài liệu chứa từ nhiều
          lần nhất: TẦN SUẤT TỪ TF = f(t, D)
       2. truy vấn có nhiều từ, từ nào quan trọng? "for", "at" có ở mọi
          tài liệu → ít thông tin: TẦN SUẤT TÀI LIỆU NGHỊCH ĐẢO
          IDF(t) = log( N / C(t) )
          N: tổng số tài liệu; C(t): số tài liệu chứa t
                                │
                                ▼
       TF-IDF:  Score(D, Q) = Σ (i = 1..q) IDF(t_i) × f(t_i, D)
                                │
                                ▼
       ELASTICSEARCH (2010, trên Lucene): CHỈ MỤC NGƯỢC
       từ → danh sách (mã tài liệu, tần suất)
       ┌──────────┬─────────┬───────────────────────────────────┐
       │ từ       │ số tài  │ (mã tài liệu, tần suất từ)         │
       │          │ liệu    │                                   │
       ├──────────┼─────────┼───────────────────────────────────┤
       │ banana   │ 2       │ (10, 3), (5, 2)                   │
       │ machine  │ 4       │ (1, 5), (10, 1), (38, 9), (42, 5) │
       │ learning │ 3       │ (1, 5), (38, 7), (42, 5)          │
       └──────────┴─────────┴───────────────────────────────────┘
                                │
                                ▼
       OKAPI BM25 (Robertson và cộng sự, thập niên 1980): TF-IDF có
       chuẩn hoá theo độ dài tài liệu (tài liệu dài dễ chứa từ hơn)
       · BM25, BM25+, BM25F vẫn là mốc so sánh rất khó vượt
                                │
                                ▼
       Tách từ: tách theo từ đơn làm vỡ "hot dog" → coi n-gram phổ biến
       là một từ; viết thường, bỏ dấu câu, bỏ stop word (NLTK, spaCy,
       Stanford CoreNLP)
       Truy xuất theo độ trùng n-gram: chỉ tốt khi truy vấn và tài liệu
       dài tương đương
```

### Mục "Embedding-based retrieval" — cơ sở dữ liệu vector, k-NN và ANN (trang PDF 507–512)

```text
       Từ khoá không bắt được nghĩa: "transformer architecture" có thể
       trả về tài liệu về máy biến áp hay phim Transformers
       → TRUY XUẤT NGỮ NGHĨA: xếp hạng theo độ gần nghĩa
                                │
                                ▼
       LẬP CHỈ MỤC: bộ chia đoạn → mô hình embedding → CƠ SỞ DỮ LIỆU VECTOR
       TRUY VẤN: (1) mô hình embedding (cùng mô hình) biến truy vấn
       thành embedding → (2) retriever lấy k đoạn có embedding gần
       nhất → (3) mô hình sinh trả lời
       (hệ thật còn có reranker và cache)
                                │
                                ▼
       Lưu vector thì dễ; khó là TÌM KIẾM VECTOR, tức tìm láng giềng gần nhất
       · k-NN ngây thơ: tính độ tương đồng (cosine) với MỌI vector, xếp
         hạng, lấy k cái đầu → chính xác nhưng chậm; chỉ cho dữ liệu nhỏ
       · Dữ liệu lớn: ANN (láng giềng gần nhất xấp xỉ); thư viện FAISS,
         ScaNN, Annoy, Hnswlib
       · Tổ chức vector thành xô, cây hay đồ thị; có thể lượng tử hoá
         hoặc làm thưa
                                │
                                ▼
  ┌───────────────┬──────────────────────────────────────────────────┐
  │ LSH (1999)    │ băm vector giống nhau vào cùng xô; đổi chút độ    │
  │               │ chính xác lấy tốc độ; có trong FAISS, Annoy       │
  │ HNSW (2016)   │ đồ thị nhiều tầng, nút là vector, cạnh nối vector │
  │               │ giống nhau; tìm bằng cách đi theo cạnh            │
  │ Product       │ cắt vector thành nhiều vector con, biểu diễn gọn  │
  │ quantization  │ ít chiều; tính khoảng cách trên dạng gọn; lõi     │
  │ (2011)        │ của FAISS                                        │
  │ IVF (2003)    │ phân cụm K-means, 100–10.000 vector mỗi cụm; khi   │
  │               │ truy vấn tìm tâm cụm gần nhất rồi xét vector     │
  │               │ trong cụm; IVF + PQ là xương sống của FAISS       │
  │ Annoy (2013)  │ nhiều cây nhị phân, mỗi cây chia vector bằng các  │
  │               │ đường cắt ngẫu nhiên; duyệt cây lấy ứng viên      │
  │ khác          │ SPTAG (Microsoft), FLANN                         │
  └───────────────┴──────────────────────────────────────────────────┘
       Mọi cơ sở dữ liệu lưu được vector đều có thể gọi là cơ sở dữ
       liệu vector; nhiều CSDL truyền thống đã/ sẽ hỗ trợ
```

### Mục "Comparing retrieval algorithms" — so sánh và đánh giá retriever (trang PDF 512–518)

```text
  ┌─────────────┬───────────────────────────┬───────────────────────────┐
  │             │ dựa trên từ khoá           │ dựa trên embedding         │
  ├─────────────┼───────────────────────────┼───────────────────────────┤
  │ tốc độ truy │ nhanh hơn nhiều           │ sinh embedding truy vấn và │
  │ vấn         │                           │ tìm vector có thể chậm     │
  │ hiệu năng   │ mạnh ngay từ đầu nhưng khó│ vượt được nhờ finetuning;  │
  │             │ cải thiện; lấy nhầm do từ │ cho phép truy vấn tự nhiên │
  │             │ đa nghĩa                  │ hơn                        │
  │ chi phí     │ rẻ hơn nhiều              │ embedding, lưu trữ, tìm    │
  │             │                           │ vector có thể đắt          │
  └─────────────┴───────────────────────────┴───────────────────────────┘
       · embedding làm mờ từ khoá: mã lỗi EADDRNOTAVAIL (99), tên sản phẩm
       · chi tiêu CSDL vector có thể bằng 1/5 tới 1/2 chi tiêu API mô hình
                                │
                                ▼
       ĐÁNH GIÁ RETRIEVER
       · context precision: trong số tài liệu lấy về, bao nhiêu % liên quan
         (dễ tính: AI judge so tài liệu lấy về với truy vấn)
       · context recall: trong số tài liệu liên quan, bao nhiêu % được lấy
         (khó: phải gán nhãn mọi tài liệu trong kho)
       · quan tâm thứ hạng: NDCG, MAP, MRR
       · đánh giá embedding (MTEB); đánh giá cả hệ thống RAG đầu–cuối
                                │
                                ▼
       Đánh đổi lập chỉ mục và truy vấn: chỉ mục chi tiết (HNSW) truy vấn
       nhanh, chính xác nhưng dựng lâu, tốn bộ nhớ; chỉ mục đơn giản
       (LSH) dựng nhanh nhưng truy vấn chậm hơn, kém chính xác hơn
       ANN-Benchmarks: recall, QPS, thời gian dựng, kích thước chỉ mục
       BEIR: 14 benchmark truy xuất
       Tóm lại: đánh giá (1) chất lượng truy xuất, (2) đầu ra RAG cuối,
       (3) embedding
```

### Mục "Combining retrieval algorithms" — hybrid search và RRF (trang PDF 518–520)

```text
       HYBRID SEARCH: kết hợp truy xuất từ khoá và embedding
       ┌──────────────────────────────┬──────────────────────────────┐
       │ NỐI TIẾP                      │ SONG SONG (ensemble)          │
       │ bước 1: retriever rẻ, kém     │ nhiều retriever cùng lấy ứng  │
       │ chính xác (từ khoá) lấy ứng   │ viên, rồi gộp các bảng xếp    │
       │ viên                          │ hạng thành một                │
       │ bước 2: cơ chế đắt, chính xác │                               │
       │ (k-NN) chọn cái tốt nhất      │ RRF: Score(D) =               │
       │ gọi là RERANKING              │   Σ (i = 1..n) 1/(k + r_i(D)) │
       │ ví dụ: lấy mọi tài liệu có    │ r_i(D): hạng của D theo       │
       │ "transformer", rồi dùng tìm   │ retriever i; k thường = 60    │
       │ vector chọn tài liệu đúng     │ bản đơn giản (k = 0): hạng 1  │
       │ nghĩa                         │ và hạng 2 → 1 + 0,5 = 1,5     │
       └──────────────────────────────┴──────────────────────────────┘
```

### Mục "Retrieval Optimization" — bốn chiến thuật (trang PDF 520–530)

```text
       ┌─────────────────────────────────────────────────────────────┐
       │ 1. CHIA ĐOẠN (chunking)                                      │
       │ · theo ký tự/từ/câu/đoạn văn (2.048 ký tự, 512 từ, 20 câu)   │
       │ · đệ quy: mục → đoạn văn → câu tới khi vừa kích thước tối đa │
       │ · đặc thù: theo ngôn ngữ lập trình, theo cặp hỏi–đáp         │
       │ · chồng lấn (ví dụ 20 ký tự trên đoạn 2.048) để không cắt    │
       │   "I left my wife a note" thành hai nửa vô nghĩa             │
       │ · theo token của mô hình sinh: tiện, nhưng đổi mô hình phải  │
       │   lập chỉ mục lại                                            │
       │ · đoạn nhỏ: thêm đa dạng, nhưng mất thông tin và gấp đôi số  │
       │   vector khi giảm một nửa kích thước; không có cỡ tốt nhất   │
       ├─────────────────────────────────────────────────────────────┤
       │ 2. XẾP HẠNG LẠI (reranking)                                  │
       │ · lọc rẻ rồi xếp lại bằng cơ chế đắt; hoặc theo thời gian    │
       │ · trong context, vị trí chính xác ít quan trọng hơn tìm kiếm │
       ├─────────────────────────────────────────────────────────────┤
       │ 3. VIẾT LẠI TRUY VẤN (query rewriting)                       │
       │ · "Còn Emily Doe thì sao?" → "Lần cuối Emily Doe mua hàng   │
       │   của chúng ta là khi nào?"                                  │
       │ · có thể cần xác định danh tính ("vợ anh ấy" là ai); không   │
       │   biết thì phải nói không giải được, đừng bịa tên            │
       ├─────────────────────────────────────────────────────────────┤
       │ 4. TRUY XUẤT CÓ NGỮ CẢNH (contextual retrieval)              │
       │ · thêm metadata, thẻ, từ khoá, thực thể (mã lỗi), câu hỏi    │
       │   mà đoạn trả lời được                                      │
       │ · Anthropic: mô hình viết 50–100 token đặt đoạn vào bối cảnh │
       │   tài liệu gốc, nối trước đoạn, rồi lập chỉ mục cả embedding │
       │   lẫn TF-IDF                                                 │
       └─────────────────────────────────────────────────────────────┘
       Khung "Evaluating retrieval solutions": cơ chế hỗ trợ (hybrid?),
       mô hình embedding và thuật toán tìm vector, khả năng mở rộng,
       thời gian lập chỉ mục, độ trễ truy vấn, cách tính giá
```

### Mục "RAG Beyond Texts" — RAG đa phương thức và RAG với bảng (trang PDF 530–535)

```text
       ĐA PHƯƠNG THỨC                     DỮ LIỆU BẢNG (Kitty Vogue)
       "Ngôi nhà trong phim Up màu gì?"    "Bao nhiêu chiếc Fruity Fedora
       → retriever lấy cả văn bản và ảnh    bán trong 7 ngày qua?"
       · theo metadata (tiêu đề, chú thích)        │
       · theo nội dung: embedding đa                ▼
         phương thức (CLIP):               1. text-to-SQL (semantic parsing;
         1. embedding mọi văn bản, ảnh        có thể cần bước chọn bảng)
         2. embedding truy vấn             2. chạy SQL
         3. lấy cái gần nhất               3. sinh câu trả lời từ kết quả
                                │
                                ▼
       Retriever và bộ chạy SQL là công cụ → nhiều công cụ hơn có giúp
       hơn không? → AGENT
```

### Mục "Agents" và "Agent Overview" — môi trường, hành động, lỗi cộng dồn (trang PDF 535–540)

```text
       Russell và Norvig (1995): AI là "nghiên cứu và thiết kế các agent
       hợp lý"; cảnh báo của tác giả: lĩnh vực mới, phần này thử nghiệm hơn
                                │
                                ▼
       AGENT: thứ cảm nhận được môi trường và tác động lên môi trường
       → đặc trưng bởi MÔI TRƯỜNG và TẬP HÀNH ĐỘNG
       · môi trường: trò chơi, internet, nhà bếp, đường sá
       · môi trường quyết định công cụ có thể; công cụ giới hạn môi
         trường (robot chỉ biết bơi thì chỉ ở dưới nước)
       · ChatGPT là agent (tìm web, chạy Python, tạo ảnh); RAG là agent
       · SWE-agent: môi trường là máy tính (terminal, hệ tệp); hành động:
         duyệt repo, tìm tệp, xem tệp, sửa dòng
                                │
                                ▼
       Ví dụ: "Dự báo doanh thu Fruity Fedora 3 tháng tới"
       suy luận → sinh SQL (5 năm doanh số) → chạy → suy luận (thiếu,
       cần dữ liệu chiến dịch tiếp thị) → sinh SQL → chạy → dự báo →
       kết luận đã xong
                                │
                                ▼
       Agent cần mô hình mạnh hơn:
       · LỖI CỘNG DỒN: đúng 95% mỗi bước → 0,95^10 ≈ 60%, 0,95^100 ≈ 0,6%
       · RỦI RO CAO HƠN: có công cụ thì lỗi gây hậu quả nặng hơn
       Thành công phụ thuộc BỘ CÔNG CỤ và BỘ LẬP KẾ HOẠCH
```

### Mục "Tools" — ba nhóm công cụ (trang PDF 540–546)

```text
       Công cụ giúp agent CẢM NHẬN (hành động chỉ đọc) và TÁC ĐỘNG
       (hành động ghi). Nhiều công cụ hơn cho nhiều năng lực hơn nhưng
       khó dùng tốt hơn
                                │
       ┌────────────────────────┼────────────────────────┐
       ▼                        ▼                        ▼
  TĂNG CƯỜNG TRI THỨC      MỞ RỘNG NĂNG LỰC         HÀNH ĐỘNG GHI
  · tìm văn bản, ảnh,      · máy tính bỏ túi        · SQL: đọc và cũng
    SQL, tìm người nội       (199.999 / 292),         sửa/xoá bảng
    bộ, API tồn kho,         lịch, đổi múi giờ,     · email: đọc và trả lời
    Slack, đọc email         đổi đơn vị, dịch       · ngân hàng: xem số dư
  · duyệt web: chống       · trình thông dịch mã      và chuyển tiền
    mô hình "lỗi thời"       (rủi ro tiêm mã)       · tự động hoá cả quy
    (thời tiết, tin tức,   · biến mô hình chữ         trình tiếp cận khách
    giá cổ phiếu); chọn      thành đa phương thức   · đáng sợ: đừng giao
    API cẩn thận             (DALL-E, OCR, phiên      quyền xoá CSDL cho
                             âm)                      thực tập sinh
                           · Chameleon (GPT-4 +     · AI gây hại cả khi
                             13 công cụ): +11,37%     không có thân xác
                             ScienceQA, +17%        · "function calling"
                             TabMWP                   sẽ phổ biến
```

### Mục "Planning" — tổng quan lập kế hoạch (Planning overview, trang PDF 546–551)

```text
       Nhiệm vụ gồm MỤC TIÊU và RÀNG BUỘC (chuyến đi 2 tuần SF → Ấn Độ,
       ngân sách 5.000 USD); kế hoạch là lộ trình các bước
                                │
                                ▼
       Nhiều cách phân rã, không phải cách nào cũng hiệu quả:
       "Bao nhiêu công ty chưa có doanh thu đã gọi ≥ 1 tỷ USD?"
       · cách 1: tìm công ty chưa có doanh thu rồi lọc theo vốn
       · cách 2: tìm công ty gọi ≥ 1 tỷ USD rồi lọc theo doanh thu ← tốt
         hơn, vì tập ban đầu nhỏ hơn rất nhiều
                                │
                                ▼
       TÁCH LẬP KẾ HOẠCH KHỎI THỰC THI (tránh kế hoạch 1.000 bước vô ích)
       sinh kế hoạch ──► kiểm định ──tốt──► thực thi ──► đánh giá kết quả
             ▲              │ xấu                              │
             └──────────────┴──────────────────────────────────┘
       · kiểm định bằng heuristic (loại hành động không có; loại kế
         hoạch quá X bước) hoặc AI judge
       · sinh song song nhiều kế hoạch: nhanh hơn nhưng tốn hơn
       · ba thành phần tạo thành hệ đa agent; bộ phân loại ý định (kể cả
         IRRELEVANT) cũng là một agent
       · con người có thể tham gia ở mọi khâu; thao tác rủi ro cần phê
         duyệt rõ ràng
                                │
                                ▼
       Bốn bước: (1) sinh kế hoạch (phân rã nhiệm vụ) → (2) phản tư,
       sửa lỗi kế hoạch → (3) thực thi → (4) phản tư, sửa lỗi kết quả
```

### Mục "Foundation models as planners" — mô hình nền tảng có lập kế hoạch được không (trang PDF 552–554)

```text
       Hoài nghi: Yann LeCun (2023) "LLM tự hồi quy không lập kế hoạch
       được"; Kambhampati (2023): LLM giỏi trích tri thức, không giỏi
       lập kế hoạch; kế hoạch "trông hợp lý" nhưng lỗi khi chạy
                                │
                                ▼
       Lập kế hoạch là bài toán TÌM KIẾM: tìm các đường tới đích, dự đoán
       kết quả (phần thưởng), chọn đường hứa hẹn nhất; thường cần QUAY LUI
                                │
                                ▼
       Phản bác của tác giả:
       · mô hình tự hồi quy vẫn "quay lui" được: thấy đường A vô lý thì
         sửa sang B hoặc làm lại từ đầu
       · có thể LLM kém vì thiếu công cụ: cần biết KẾT QUẢ của hành động
         (rẽ phải có rơi xuống vực không), không chỉ chuỗi hành động
       · Hao và cộng sự (2023): LLM chứa đủ tri thức về thế giới để dự
         đoán kết quả hành động
       · dù AI không lập kế hoạch được, nó vẫn là một phần của bộ lập
         kế hoạch (kèm công cụ tìm kiếm, theo dõi trạng thái)
                                │
                                ▼
       Khung: agent học tăng cường (RL) với agent mô hình nền tảng (FM)
       · giống: cùng đặc trưng bởi môi trường và hành động
       · khác: RL huấn luyện bộ lập kế hoạch (tốn); FM dùng chính mô hình
         làm bộ lập kế hoạch (prompt hoặc finetune, rẻ hơn)
       · tác giả đoán lâu dài hai loại sẽ hợp nhất
```

### Mục "Plan generation", "Function calling", "Planning granularity", "Complex plans" (trang PDF 555–566)

```text
       SINH KẾ HOẠCH BẰNG PROMPT (Kitty Vogue): system prompt liệt kê 5
       hành động get_today_date, fetch_top_products, fetch_product_info,
       generate_query, generate_response + ví dụ
       "Giá của sản phẩm bán chạy nhất tuần trước?" →
       get_time → fetch_top_products → fetch_product_info →
       generate_query → generate_response
       · tham số suy ra từ đầu ra bước trước (2030-09-13 → từ 09-07
         tới 09-13, 1 sản phẩm); thiếu thông tin thì phải đoán
       · cả hành động lẫn tham số có thể bị bịa → cải thiện: prompt
         nhiều ví dụ, mô tả công cụ tốt, tách hàm phức tạp, mô hình
         mạnh hơn, finetune
                                │
                                ▼
       FUNCTION CALLING: (1) khai báo bộ công cụ (tên, tham số, tài
       liệu); (2) chỉ định công cụ dùng cho mỗi truy vấn: required /
       none / auto. "40 pound là bao nhiêu kg?" → lbs_to_kg(lbs=40)
       Mẹo: luôn yêu cầu hệ thống báo giá trị tham số và kiểm tra lại
                                │
                                ▼
       ĐỘ CHI TIẾT: kế hoạch chi tiết khó sinh, dễ chạy; kế hoạch cấp
       cao dễ sinh, khó chạy → lập kế hoạch PHÂN CẤP (quý → tháng)
       Tên hàm chính xác thì dễ vỡ khi đổi API → viết kế hoạch bằng
       ngôn ngữ tự nhiên rồi dùng BỘ DỊCH (mô hình yếu hơn cũng làm được)
                                │
                                ▼
       LUỒNG ĐIỀU KHIỂN
  ┌────────────┬───────────────────────────────────────────────────────┐
  │ tuần tự    │ B sau A (dịch câu hỏi sang SQL rồi mới chạy SQL)       │
  │ song song  │ A và B cùng lúc (lấy 100 sản phẩm bán chạy rồi lấy    │
  │            │ giá từng cái)                                         │
  │ rẽ nhánh   │ B hoặc C tuỳ kết quả (đọc báo cáo lợi nhuận NVIDIA rồi │
  │            │ mua hay bán)                                          │
  │ vòng lặp   │ lặp A tới khi đạt điều kiện (sinh số ngẫu nhiên tới    │
  │            │ khi ra số nguyên tố)                                  │
  └────────────┴───────────────────────────────────────────────────────┘
       Luồng do AI quyết định → khó sinh và khó dịch hơn; song song
       giảm độ trễ người dùng cảm nhận
```

### Mục "Reflection and error correction" — ReAct và Reflexion (trang PDF 567–571)

```text
       Phản tư không bắt buộc để agent chạy, nhưng cần để agent THÀNH CÔNG
       Bốn chỗ phản tư: sau truy vấn (khả thi?), sau kế hoạch (hợp lý?),
       sau mỗi bước (đúng hướng?), sau cùng (xong chưa?)
                                │
                                ▼
       REACT (Yao 2022): xen kẽ suy nghĩ — hành động — quan sát
       Thought 1 → Act 1 → Observation 1 → … → Act N: Finish[trả lời]
       Ví dụ HotpotQA: Apple Remote → Front Row → Front Row (software)
       → "phím chức năng của bàn phím"
                                │
                                ▼
       REFLEXION (Shinn 2023): bộ đánh giá + mô-đun tự phản tư; mỗi
       bước đề xuất "quỹ đạo" (trajectory) mới
       · mã sai 1/3 ca kiểm thử → nhận ra quên mảng toàn số âm → sửa
                                │
                                ▼
       Dễ làm, cải thiện tốt; nhược: tốn token cho suy nghĩ, quan sát và
       ví dụ trong prompt → tăng chi phí, độ trễ, chiếm chỗ context
```

### Mục "Tool selection" — chọn bộ công cụ (trang PDF 572–576)

```text
       Toolformer: 5 công cụ; Chameleon: 13; Gorilla: 1.645 API
       Nhiều công cụ hơn: nhiều năng lực, nhưng khó dùng và mô tả có
       thể không vừa context
                                │
                                ▼
       Cách chọn: so các bộ công cụ; nghiên cứu cắt bỏ (bỏ một công cụ
       mà không tụt hiệu năng thì bỏ); tìm công cụ hay gọi sai; vẽ phân
       bố số lần gọi
                                │
                                ▼
       Chameleon: ScienceQA dựa vào truy xuất tri thức (72–81% chương
       trình) hơn nhiều TabMWP (16–25%); GPT-4 dùng tập công cụ rộng hơn
       ChatGPT
       Chuyển tiếp công cụ: START → truy xuất tri thức 0,53, phát hiện
       chữ 0,3, sinh truy vấn 0,11, chú thích ảnh 0,06; sinh truy vấn →
       Bing 1,0 → ghép hai công cụ hay đi cùng thành công cụ lớn
       Voyager: bộ quản lý kỹ năng lưu kỹ năng (chương trình) mới hữu ích
```

### Mục "Agent Failure Modes and Evaluation" — ba kiểu hỏng (trang PDF 576–581)

```text
       Đánh giá là phát hiện lỗi: liệt kê kiểu hỏng, đo tần suất từng kiểu
       (Berkeley Function Calling Leaderboard, AgentOps, TravelPlanner)
                                │
       ┌────────────────────────┼────────────────────────┐
       ▼                        ▼                        ▼
  LỖI LẬP KẾ HOẠCH         LỖI CÔNG CỤ              KÉM HIỆU QUẢ
  · công cụ không có       · công cụ cho đầu ra     · số bước trung bình
    (bing_search)            sai (chú thích ảnh     · chi phí trung bình
  · đúng công cụ, sai        sai, SQL sai)          · thời gian mỗi hành
    tham số (2 tham số     · lỗi bộ dịch              động
    cho lbs_to_kg)         · thiếu công cụ (không   · so với agent khác
  · đúng tham số, sai giá    có internet)             hoặc người; 100 trang
    trị (100 thay vì 120)  · kiểm thử riêng từng      web: chậm với người,
  · lỗi mục tiêu: sai đích   công cụ; in mọi lời      tức thì với AI
    (TP.HCM thay Hà Nội),    gọi; hỏi chuyên gia
    vượt ngân sách, trễ      người dùng công cụ gì
    hạn
  · lỗi phản tư: được giao
    xếp 50 người vào 30
    phòng, chỉ xếp 40 mà
    nói đã xong
       └────────────────────────┼────────────────────────┘
                                ▼
       Bộ dữ liệu (nhiệm vụ, bộ công cụ), sinh K kế hoạch mỗi nhiệm vụ,
       đo 6 chỉ số: tỷ lệ kế hoạch hợp lệ; số lần sinh trung bình để có
       một kế hoạch hợp lệ; tỷ lệ lời gọi hợp lệ; tần suất gọi công cụ
       không có; tần suất sai tham số; tần suất sai giá trị tham số
```

### Mục "Memory" — ba cơ chế và quản lý bộ nhớ (trang PDF 581–589)

```text
  ┌──────────────────┬────────────────────────────────────────────────┐
  │ TRI THỨC NỘI TẠI  │ chính mô hình (từ dữ liệu huấn luyện); chỉ đổi │
  │                  │ khi cập nhật mô hình; dùng được ở mọi truy vấn │
  │                  │ → thông tin cần cho mọi nhiệm vụ               │
  │ NGẮN HẠN         │ context; nhanh, dung lượng hạn chế, không giữ │
  │                  │ qua nhiệm vụ → thông tin tức thời              │
  │ DÀI HẠN          │ nguồn ngoài qua retriever; giữ qua nhiệm vụ,   │
  │                  │ xoá được mà không sửa mô hình → thông tin ít   │
  │                  │ dùng                                           │
  └──────────────────┴────────────────────────────────────────────────┘
       Ở người: cách thở là tri thức nội tại; tên người vừa gặp nằm
       trong bộ nhớ ngắn hạn; sách và ghi chép là bộ nhớ dài hạn
                                │
                                ▼
       Lợi ích: xử lý tràn thông tin trong phiên; giữ thông tin giữa các
       phiên (nhớ bạn thích Tam thể); nhất quán hơn; giữ cấu trúc dữ
       liệu (bảng Excel, hàng đợi hành động)
                                │
                                ▼
       Hai chức năng: QUẢN LÝ (thêm, xoá) và TRUY XUẤT (giống RAG)
       · dành 30% context cho thông tin truy xuất → ngắn hạn tối đa 70%;
         vượt ngưỡng thì chuyển phần tràn sang dài hạn
       · FIFO: bỏ tin nhắn cũ nhất (OpenAI, LangChain giữ N tin/token
         cuối) — có thể bỏ mất mục đích cuộc trò chuyện
       · bỏ dư thừa: tóm tắt + theo dõi thực thể; Bae 2022 phân loại
         câu nào giữ; Liu 2023 phản tư: chèn, gộp hay thay thông tin
       · thông tin mâu thuẫn: giữ cái mới, nhờ AI phân xử, hoặc giữ cả
         để có nhiều góc nhìn
```

### Mục "Summary" — tóm tắt chương (trang PDF 589–591)

```text
       RAG: hai bước truy xuất rồi sinh; ra đời để vượt giới hạn context,
       còn giúp dùng thông tin hiệu quả, tăng chất lượng, giảm chi phí
       · từ khoá (Elasticsearch, BM25): nhẹ, mốc mạnh
       · embedding: tốn tính toán, có thể vượt; dựa trên tìm kiếm vector
                                │
                                ▼
       RAG là trường hợp riêng của agent (retriever là một công cụ)
       Agent: môi trường + công cụ; AI là bộ lập kế hoạch; cần mô hình
       mạnh, phản tư và bộ nhớ
       Càng tự động, lỗi càng thảm khốc → cần cơ chế phòng thủ (Chương 5)
                                │
                                ▼
       Bộ nhớ quản lý thông tin vượt context
       RAG và agent chỉ tác động qua đầu vào → Chương 7: sửa mô hình
```

## Ba câu hỏi chương này trả lời

1. **Vì sao vẫn cần RAG khi context của mô hình ngày càng dài, và một hệ RAG gồm những gì?** Vì lượng dữ liệu luôn tăng nhanh hơn độ dài context, và mô hình đọc được context dài chưa chắc dùng tốt nó; mỗi token thêm vào còn tốn tiền và có thể thêm độ trễ. Một hệ RAG có retriever (lập chỉ mục và truy vấn) và mô hình sinh. Anthropic gợi ý ngưỡng thực hành: kho tri thức dưới 200.000 token (khoảng 500 trang) thì có thể đưa cả vào prompt của Claude.
2. **Nên truy xuất bằng từ khoá hay bằng embedding?** Từ khoá (TF-IDF, BM25, Elasticsearch) nhanh hơn, rẻ hơn nhiều và mạnh ngay từ đầu nhưng khó cải thiện và lấy nhầm khi từ đa nghĩa; embedding hiểu nghĩa, vượt được từ khoá sau khi finetune, nhưng chậm hơn, đắt hơn (chi tiêu cho cơ sở dữ liệu vector có thể bằng 1/5 tới 1/2 chi tiêu API mô hình) và làm mờ từ khoá như mã lỗi EADDRNOTAVAIL (99). Hệ thống thật thường kết hợp cả hai (hybrid search): lọc rẻ rồi xếp hạng lại, hoặc gộp bảng xếp hạng bằng RRF với k = 60; rồi tối ưu bằng chia đoạn, xếp hạng lại, viết lại truy vấn và thêm ngữ cảnh 50–100 token cho mỗi đoạn.
3. **Điều gì quyết định một agent thành công, và nó hỏng theo những cách nào?** Bộ công cụ và năng lực lập kế hoạch của mô hình, cộng phản tư và bộ nhớ. Vì lỗi cộng dồn (95% mỗi bước còn khoảng 60% sau 10 bước, 0,6% sau 100 bước), agent cần mô hình mạnh, kế hoạch phải được kiểm định trước khi chạy, và hành động ghi cần con người phê duyệt. Agent hỏng theo ba kiểu: lỗi lập kế hoạch (gọi công cụ không có, sai tham số, sai giá trị, sai mục tiêu, tự cho là đã xong), lỗi công cụ (đầu ra sai, dịch sai, thiếu công cụ) và kém hiệu quả (nhiều bước, tốn tiền, chậm).

## Khái niệm cần biết

- **Context và chỉ dẫn (context, instruction):** chỉ dẫn là phần prompt chung cho mọi truy vấn của một ứng dụng; context là thông tin riêng cho từng truy vấn. Ví dụ: câu hỏi "Máy in fancy-printer-A300 của Acme in được 100 trang mỗi giây không?" cần context là thông số của máy đó. Quan trọng vì cả chương là các cách dựng context.
- **RAG (retrieval-augmented generation — sinh có tăng cường truy xuất):** kỹ thuật lấy thông tin liên quan từ bộ nhớ ngoài rồi đưa vào mô hình để sinh câu trả lời. Ví dụ: hệ của Chen và cộng sự (2017) lấy 5 trang Wikipedia liên quan nhất rồi đọc để trả lời. Quan trọng vì đây là mẫu hình phổ biến nhất để mô hình dùng dữ liệu riêng.
- **Retriever, lập chỉ mục, truy vấn (retriever, indexing, querying):** retriever là thành phần tìm dữ liệu liên quan; lập chỉ mục là xử lý dữ liệu trước để sau tìm nhanh; truy vấn là gửi câu hỏi để lấy dữ liệu. Ví dụ: chỉ mục ngược lưu sẵn "machine" xuất hiện ở tài liệu 1, 10, 38, 42. Quan trọng vì "thành bại của RAG phụ thuộc chất lượng retriever".
- **Đoạn (chunk) và chia đoạn (chunking):** cắt tài liệu thành phần nhỏ vừa context. Ví dụ: tài liệu 10.000 ký tự, đoạn 2.048 ký tự, chồng lấn 20 ký tự cho 5 đoạn (người tổng hợp tính). Quan trọng vì kích thước đoạn đổi cả chất lượng lẫn chi phí truy xuất.
- **Truy xuất dựa trên từ khoá (term-based / lexical retrieval):** xếp hạng tài liệu theo việc chứa các từ của truy vấn. Ví dụ: truy vấn "transformer" lấy cả tài liệu về máy biến áp. Quan trọng vì nó là mốc so sánh mạnh, nhanh, rẻ.
- **TF, IDF, TF-IDF:** TF là số lần từ xuất hiện trong tài liệu; IDF đo độ hiếm của từ, log(N / C(t)); TF-IDF cộng TF × IDF qua các từ của truy vấn. Ví dụ: với 50 tài liệu, "machine" có ở 4 tài liệu thì IDF = ln(12,5) ≈ 2,53. Quan trọng vì nó là nền của BM25 và Elasticsearch.
- **Chỉ mục ngược (inverted index):** từ điển ánh xạ từ sang danh sách tài liệu chứa nó, kèm tần suất. Ví dụ: "banana" → (10, 3), (5, 2). Quan trọng vì nó giúp tìm theo từ khoá cực nhanh.
- **BM25:** biến thể TF-IDF có bão hoà tần suất từ và chuẩn hoá theo độ dài tài liệu. Ví dụ (người tổng hợp tính): tài liệu dài 1.000 từ chứa "machine" 9 lần xếp trên cùng theo TF-IDF nhưng xuống thứ hai theo BM25. Quan trọng vì đây là mốc so sánh "rất khó vượt" trong công nghiệp.
- **Thưa và dày (sparse, dense):** vector thưa phần lớn là 0 (one-hot), vector dày phần lớn khác 0 (embedding). Ví dụ: "banana" trong từ điển ba từ là [0, 1, 0]. Quan trọng vì tài liệu chuyên ngành hay chia truy xuất theo cách này; sách chọn chia theo từ khoá và embedding vì SPLADE.
- **Truy xuất dựa trên embedding (embedding-based / semantic retrieval) và cơ sở dữ liệu vector:** biến tài liệu và truy vấn thành embedding, lấy k tài liệu có embedding gần nhất; nơi lưu embedding là cơ sở dữ liệu vector. Ví dụ: truy vấn "kiến trúc transformer" lấy đúng tài liệu về mạng nơ-ron. Quan trọng vì nó bắt được nghĩa và cải thiện được bằng finetuning.
- **k-NN và ANN:** k-NN tính độ tương đồng với mọi vector rồi lấy k cái gần nhất (chính xác, chậm); ANN tìm gần đúng nhanh hơn nhiều. Ví dụ: IVF chỉ xét vector trong vài cụm, mỗi cụm 100–10.000 vector. Quan trọng vì mọi kho vector lớn đều dùng ANN.
- **Context precision và context recall:** precision là tỷ lệ tài liệu lấy về có liên quan; recall là tỷ lệ tài liệu liên quan được lấy về. Ví dụ (minh hoạ): lấy 10 tài liệu, 6 liên quan, trong kho có 8 tài liệu liên quan thì precision 60%, recall 75%. Quan trọng vì đây là hai chỉ số chính đánh giá retriever; recall khó đo hơn vì phải gán nhãn cả kho.
- **Hybrid search, reranking, RRF:** hybrid là kết hợp từ khoá và embedding; reranking là xếp hạng lại ứng viên bằng cơ chế chính xác hơn; RRF cộng 1/(k + hạng) qua các retriever. Ví dụ: với k = 60, tài liệu hạng 1 và hạng 2 được 1/61 + 1/62 ≈ 0,0325. Quan trọng vì hệ thống thật hầu như luôn kết hợp.
- **Viết lại truy vấn (query rewriting):** chuyển câu hỏi phụ thuộc hội thoại thành câu tự đủ nghĩa. Ví dụ: "Còn Emily Doe thì sao?" thành "Lần cuối Emily Doe mua hàng của chúng ta là khi nào?". Quan trọng vì truy vấn mơ hồ lấy về tài liệu không liên quan.
- **Truy xuất có ngữ cảnh (contextual retrieval):** thêm metadata hoặc đoạn mô tả bối cảnh vào mỗi đoạn trước khi lập chỉ mục. Ví dụ: Anthropic cho mô hình viết 50–100 token nói đoạn này nằm ở đâu trong tài liệu gốc. Quan trọng vì đoạn bị cắt rời thường thiếu thông tin để retriever hiểu.
- **Text-to-SQL:** sinh câu SQL từ câu hỏi tự nhiên và lược đồ bảng. Ví dụ: "Bao nhiêu chiếc Fruity Fedora bán trong 7 ngày qua?" thành SELECT SUM(units)…. Quan trọng vì nó là cách RAG dùng dữ liệu bảng.
- **Agent, môi trường, hành động:** agent là thứ cảm nhận môi trường và tác động lên nó; năng lực do môi trường và tập hành động (công cụ) quyết định. Ví dụ: SWE-agent có môi trường là máy tính, hành động là duyệt repo, tìm, xem, sửa tệp. Quan trọng vì đây là định nghĩa làm việc của nửa sau chương.
- **Lỗi cộng dồn (compound mistakes):** độ chính xác cả chuỗi bằng tích độ chính xác từng bước. Ví dụ: 0,95¹⁰ ≈ 0,60. Quan trọng vì nó giải thích vì sao agent cần mô hình mạnh.
- **Bộ công cụ (tool inventory), hành động chỉ đọc và hành động ghi:** bộ công cụ là tập công cụ agent được dùng; hành động đọc chỉ cảm nhận, hành động ghi thay đổi môi trường. Ví dụ: API ngân hàng xem số dư (đọc) và chuyển tiền (ghi). Quan trọng vì hành động ghi mang rủi ro lớn nhất.
- **Function calling:** tính năng của API mô hình cho phép mô hình chọn công cụ và sinh tham số. Ví dụ: "40 pound là bao nhiêu kg?" thành lbs_to_kg(lbs=40), cho 18,14 kg. Quan trọng vì đây là cơ chế thực thi của agent.
- **Lập kế hoạch, phân rã nhiệm vụ (planning, task decomposition):** biến nhiệm vụ (mục tiêu + ràng buộc) thành chuỗi hành động. Ví dụ: tìm công ty gọi vốn ≥ 1 tỷ USD trước rồi lọc theo doanh thu. Quan trọng vì thứ tự phân rã quyết định hiệu quả.
- **Luồng điều khiển (control flow):** thứ tự thực thi hành động: tuần tự, song song, rẽ nhánh, vòng lặp. Ví dụ: duyệt 10 trang web song song. Quan trọng vì luồng phức tạp khó sinh hơn nhưng giảm độ trễ.
- **Phản tư và sửa lỗi (reflection, error correction); ReAct; Reflexion:** phản tư là đánh giá kế hoạch hay kết quả để tìm lỗi; ReAct xen kẽ suy nghĩ, hành động, quan sát; Reflexion tách bộ đánh giá và mô-đun tự phản tư. Ví dụ: mã sai 1/3 ca kiểm thử, agent nhận ra quên trường hợp mảng toàn số âm. Quan trọng vì "phản tư không bắt buộc để chạy, nhưng cần để thành công".
- **Bộ nhớ ba tầng (internal knowledge, short-term memory, long-term memory):** tri thức trong trọng số mô hình, context, và nguồn ngoài truy xuất được. Ví dụ: dành 30% context cho thông tin truy xuất thì bộ nhớ ngắn hạn tối đa 70%. Quan trọng vì RAG và agent đều xử lý thông tin vượt context.

## Nội dung chi tiết

### 1. Phần mở đầu: chỉ dẫn và context (Chapter 6 introduction, trang PDF 494–495)

Để giải một nhiệm vụ, mô hình cần hai thứ: chỉ dẫn cách làm và thông tin cần thiết để làm. Người thiếu thông tin dễ trả lời sai; mô hình AI thiếu context cũng dễ mắc lỗi và bịa (hallucinate). Trong một ứng dụng, chỉ dẫn là chung cho mọi truy vấn, còn context là riêng cho từng truy vấn. Chương 5 bàn cách viết chỉ dẫn tốt; Chương 6 bàn cách dựng context liên quan cho từng truy vấn.

Hai mẫu hình chiếm ưu thế trong việc dựng context là **RAG** (retrieval-augmented generation — sinh có tăng cường truy xuất) và **agent**. RAG cho mô hình truy xuất thông tin liên quan từ nguồn dữ liệu bên ngoài. Mẫu hình agent cho mô hình dùng công cụ như tìm kiếm web hay API tin tức để thu thập thông tin. RAG chủ yếu dùng để dựng context, còn agent làm được nhiều hơn: công cụ bên ngoài bù đắp điểm yếu và mở rộng năng lực của mô hình, và quan trọng nhất là cho mô hình khả năng tương tác trực tiếp với thế giới, tự động hoá nhiều mặt của đời sống. Cả hai mẫu hình đã nhanh chóng chiếm lĩnh trí tưởng tượng chung, sinh ra những bản demo và sản phẩm khiến nhiều người tin chúng là tương lai.

### 2. RAG: nguồn gốc và lý do tồn tại (RAG, trang PDF 495–498)

#### Định nghĩa và lịch sử

RAG là kỹ thuật tăng chất lượng sinh của mô hình bằng cách truy xuất thông tin liên quan từ các nguồn bộ nhớ ngoài. Bộ nhớ ngoài có thể là cơ sở dữ liệu nội bộ, các phiên chat trước của người dùng, hoặc internet.

Mẫu hình "truy xuất rồi sinh" (retrieve-then-generate) được giới thiệu lần đầu trong bài "Reading Wikipedia to Answer Open-Domain Questions" (Chen và cộng sự, 2017). Hệ thống trước hết truy xuất năm trang Wikipedia liên quan nhất tới câu hỏi, rồi một mô hình đọc thông tin từ các trang đó để sinh câu trả lời. Hình minh hoạ của sách (Hình 6-1) cho thấy câu hỏi "How many of Warsaw's inhabitants spoke Polish in 1933?" đi qua "document retriever" tới trang Wikipedia về Warsaw, rồi "document reader" — một mạng hai chiều đọc câu hỏi Q và đoạn văn P — xuất ra câu trả lời 833.500. Theo chú thích của sách, mô hình đọc khi đó là một mạng nơ-ron hồi quy loại LSTM (Long Short-Term Memory), kiến trúc thống trị xử lý ngôn ngữ tự nhiên trước khi transformer thay thế vào năm 2018.

Thuật ngữ "retrieval-augmented generation" được đặt ra trong bài "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks" (Lewis và cộng sự, 2020). Bài này đề xuất RAG cho các nhiệm vụ cần nhiều tri thức, khi không thể đưa toàn bộ tri thức vào mô hình: chỉ thông tin liên quan nhất tới truy vấn, do retriever xác định, được lấy ra và đưa vào mô hình. Lewis và cộng sự thấy rằng có thông tin liên quan giúp mô hình trả lời chi tiết hơn và bớt bịa. Chú thích của sách ghi rằng cùng thời gian đó, một bài khác cũng của Facebook, "How Context Affects Language Models' Factual Predictions" (Petroni và cộng sự, 5/2020), cho thấy gắn hệ truy xuất vào mô hình ngôn ngữ đã huấn luyện cải thiện rất mạnh kết quả với câu hỏi về sự kiện.

Ví dụ (sách cảm ơn Chetan Tekur): với câu hỏi "Can Acme's fancy-printer-A300 print 100pps?" (máy in fancy-printer-A300 của Acme có in được 100 trang mỗi giây không?), mô hình trả lời tốt hơn nếu được cho thông số của máy đó.

#### RAG là dựng context riêng cho từng truy vấn

Có thể xem RAG là kỹ thuật dựng context riêng cho từng truy vấn thay vì dùng cùng một context cho mọi truy vấn. Điều này cũng giúp quản lý dữ liệu người dùng: dữ liệu của một người chỉ được đưa vào các truy vấn liên quan tới người đó. Tác giả so sánh: dựng context cho mô hình nền tảng tương đương với feature engineering (thiết kế đặc trưng) cho mô hình học máy cổ điển — cả hai cùng mục đích là đưa cho mô hình thông tin cần thiết để xử lý đầu vào.

#### Context dài có làm RAG biến mất không?

Thời đầu của mô hình nền tảng, RAG nổi lên như một mẫu hình phổ biến nhất, chủ yếu để vượt giới hạn context. Nhiều người nghĩ context đủ dài sẽ chấm dứt RAG; tác giả không nghĩ vậy, vì hai lý do:

1. **Dữ liệu luôn nhiều hơn context.** Dù context dài bao nhiêu, vẫn sẽ có ứng dụng cần context dài hơn. Lượng dữ liệu chỉ tăng theo thời gian: người ta sinh và thêm dữ liệu mới nhưng hiếm khi xoá. Độ dài context tăng nhanh, nhưng không đủ nhanh cho nhu cầu của mọi ứng dụng. Chú thích của sách nêu một "định luật" tự đặt của tác giả, phỏng theo định luật Parkinson ("công việc nở ra để lấp đầy thời gian có để hoàn thành nó"): context của một ứng dụng nở ra để lấp đầy giới hạn context mà mô hình hỗ trợ.
2. **Xử lý được context dài không có nghĩa là dùng tốt.** Như đã bàn ở mục "Context Length and Context Efficiency" của Chương 5, context càng dài, mô hình càng dễ chú ý nhầm phần. Mỗi token context thêm vào tốn thêm tiền và có thể thêm độ trễ. RAG cho mô hình chỉ dùng thông tin liên quan nhất cho mỗi truy vấn, giảm số token đầu vào và có thể tăng hiệu năng.

Nỗ lực kéo dài context diễn ra song song với nỗ lực giúp mô hình dùng context hiệu quả hơn; tác giả không ngạc nhiên nếu một nhà cung cấp mô hình tích hợp cơ chế giống truy xuất hay giống attention để mô hình tự chọn phần nổi bật nhất của context.

**Ghi chú của sách:** Anthropic gợi ý với mô hình Claude, nếu "kho tri thức của bạn nhỏ hơn 200.000 token (khoảng 500 trang tài liệu), bạn có thể đưa toàn bộ kho tri thức vào prompt, không cần RAG hay phương pháp tương tự" (Anthropic, 2024). Tác giả mong các nhà phát triển mô hình khác cũng đưa hướng dẫn tương tự. (Người tổng hợp tính: 200.000 / 500 = 400 token mỗi trang.)

### 3. Kiến trúc RAG (RAG Architecture, trang PDF 498–500)

Một hệ RAG có hai thành phần: **retriever** truy xuất thông tin từ các nguồn bộ nhớ ngoài, và **generator** (mô hình sinh) sinh phản hồi dựa trên thông tin đã truy xuất. Sơ đồ kiến trúc cơ bản (Hình 6-2 của sách): người dùng gửi prompt; prompt đi tới retriever, retriever đọc từ "bộ nhớ ngoài: tài liệu, bảng, lịch sử chat…" và đưa "context liên quan tới truy vấn" xuống mô hình sinh; prompt gốc cũng đi thẳng tới mô hình sinh; mô hình sinh trả phản hồi cho người dùng.

Trong bài RAG gốc, Lewis và cộng sự huấn luyện retriever và mô hình sinh cùng nhau. Trong các hệ RAG ngày nay, hai thành phần thường được huấn luyện riêng, và nhiều đội dựng hệ RAG bằng retriever và mô hình có sẵn. Tuy vậy, finetune cả hệ RAG đầu–cuối có thể cải thiện hiệu năng đáng kể.

Thành công của hệ RAG phụ thuộc vào chất lượng retriever. Retriever có hai chức năng chính: **lập chỉ mục** (indexing) — xử lý dữ liệu sao cho sau này truy xuất nhanh; và **truy vấn** (querying) — gửi truy vấn để lấy dữ liệu liên quan. Cách lập chỉ mục phụ thuộc vào cách bạn muốn truy xuất sau này.

**Một ví dụ vận hành.** Giả sử bộ nhớ ngoài là một cơ sở dữ liệu tài liệu, như ghi nhớ, hợp đồng, biên bản họp của công ty. Một tài liệu có thể dài 10 token hoặc 1 triệu token. Lấy nguyên tài liệu có thể làm context dài tuỳ ý, nên mỗi tài liệu được chia thành các **đoạn** (chunk) dễ xử lý hơn. Với mỗi truy vấn, mục tiêu là lấy các đoạn liên quan nhất. Thường cần một bước hậu xử lý nhỏ để ghép các đoạn đã lấy với prompt của người dùng thành prompt cuối, rồi đưa vào mô hình sinh.

**Ghi chú về thuật ngữ:** trong chương, tác giả dùng "tài liệu" (document) cho cả tài liệu và đoạn, vì về kỹ thuật một đoạn của tài liệu cũng là một tài liệu; cách gọi này nhất quán với thuật ngữ của xử lý ngôn ngữ tự nhiên cổ điển và truy xuất thông tin (information retrieval, IR).

### 4. Thuật toán truy xuất (Retrieval Algorithms, trang PDF 500–520)

Truy xuất không phải là thứ riêng của RAG. Truy xuất thông tin là ý tưởng đã có cả thế kỷ — chú thích của sách dẫn các bằng sáng chế thập niên 1920 của Emanuel Goldberg cho một "máy thống kê" tìm tài liệu lưu trên phim (xem "The History of Information Retrieval Research", Sanderson và Croft, Proceedings of the IEEE, 4/2012). Nó là xương sống của máy tìm kiếm, hệ gợi ý, phân tích log… Nhiều thuật toán phát triển cho hệ truy xuất truyền thống dùng được cho RAG. Đây là một lĩnh vực nghiên cứu lớn có cả một ngành công nghiệp hậu thuẫn, nên chương chỉ phác những nét lớn; kho GitHub của sách có tài liệu sâu hơn.

**Ghi chú của sách:** truy xuất (retrieval) thường giới hạn trong một cơ sở dữ liệu hay hệ thống, còn tìm kiếm (search) là truy xuất qua nhiều hệ thống; chương dùng hai từ thay cho nhau.

Về cốt lõi, truy xuất là **xếp hạng tài liệu theo độ liên quan tới truy vấn**. Các thuật toán truy xuất khác nhau ở cách tính điểm liên quan. Tác giả bắt đầu với hai cơ chế phổ biến: truy xuất dựa trên từ khoá và truy xuất dựa trên embedding.

#### Khung "Sparse Versus Dense Retrieval" (trang PDF 502–503)

Tài liệu chuyên ngành thường chia thuật toán truy xuất thành **thưa** (sparse) và **dày** (dense); sách chọn cách chia "dựa trên từ khoá" và "dựa trên embedding".

- **Retriever thưa** biểu diễn dữ liệu bằng vector thưa — vector mà phần lớn giá trị là 0. Truy xuất dựa trên từ khoá được coi là thưa, vì mỗi từ có thể biểu diễn bằng vector one-hot: bằng 0 ở mọi vị trí trừ một vị trí bằng 1; độ dài vector bằng kích thước từ vựng, vị trí số 1 là chỉ số của từ trong từ vựng. Ví dụ với từ điển {"food": 0, "banana": 1, "slug": 2}, vector one-hot của "food", "banana", "slug" lần lượt là [1, 0, 0], [0, 1, 0], [0, 0, 1].
- **Retriever dày** biểu diễn dữ liệu bằng vector dày — phần lớn giá trị khác 0. Truy xuất dựa trên embedding thường được coi là dày vì embedding thường là vector dày.
- Nhưng cũng có embedding thưa. **SPLADE** (Sparse Lexical and Expansion, Formal và cộng sự, 2021) dùng embedding sinh bởi BERT nhưng dùng điều chuẩn (regularization) đẩy phần lớn giá trị về 0; độ thưa làm phép tính trên embedding hiệu quả hơn. Cách chia thưa/dày xếp SPLADE chung nhóm với thuật toán từ khoá, dù cách vận hành, điểm mạnh và điểm yếu của SPLADE giống truy xuất embedding dày hơn nhiều. Cách chia từ khoá/embedding tránh xếp nhầm như vậy.

#### Truy xuất dựa trên từ khoá (Term-based retrieval, trang PDF 503–507)

Với một truy vấn, cách thẳng nhất để tìm tài liệu liên quan là dùng từ khoá; có người gọi cách này là **truy xuất từ vựng** (lexical retrieval). Ví dụ với truy vấn "AI engineering", hệ thống lấy mọi tài liệu chứa "AI engineering". Cách này có hai vấn đề:

1. **Quá nhiều tài liệu chứa từ đó**, và context của mô hình không đủ chỗ cho tất cả. Một heuristic là lấy các tài liệu chứa từ đó nhiều lần nhất, với giả định từ xuất hiện càng nhiều trong một tài liệu thì tài liệu đó càng liên quan tới từ. Số lần một từ xuất hiện trong một tài liệu gọi là **tần suất từ** (term frequency, TF).
2. **Prompt dài có nhiều từ, từ nào quan trọng?** Ví dụ prompt "Easy-to-follow recipes for Vietnamese food to cook at home" (công thức món Việt dễ làm tại nhà) có chín từ: easy-to-follow, recipes, for, vietnamese, food, to, cook, at, home. Ta muốn tập trung vào các từ nhiều thông tin như *vietnamese* và *recipes*, không phải *for* và *at*. Trực giác là: càng nhiều tài liệu chứa một từ, từ đó càng ít thông tin — "for" và "at" có trong hầu hết tài liệu. Vậy tầm quan trọng của một từ tỷ lệ nghịch với số tài liệu chứa nó. Chỉ số này gọi là **tần suất tài liệu nghịch đảo** (inverse document frequency, IDF). Lời văn của sách tả cách tính: đếm số tài liệu chứa từ, rồi lấy tổng số tài liệu chia cho số đó; nếu có 10 tài liệu và 5 tài liệu chứa từ, IDF là 10 / 5 = 2. IDF càng cao, từ càng quan trọng. (Công thức ngay sau đó có thêm log; xem khối Lưu ý.)

**TF-IDF** là thuật toán kết hợp hai chỉ số TF và IDF. Về toán học, điểm TF-IDF của tài liệu D với truy vấn Q tính như sau:

- Gọi t₁, t₂, …, t_q là các từ trong truy vấn Q.
- Với một từ t, tần suất của từ trong tài liệu D là f(t, D).
- Gọi N là tổng số tài liệu, C(t) là số tài liệu chứa t. Giá trị IDF của từ t là:

  IDF(t) = log( N / C(t) )

- Điểm TF-IDF "ngây thơ" của tài liệu D với Q là:

  Score(D, Q) = Σ_{i=1}^{q} IDF(t_i) × f(t_i, D)

Giải thích từng bước: (1) với mỗi từ của truy vấn, đếm số lần nó xuất hiện trong tài liệu (TF); (2) nhân với độ hiếm của từ trong cả kho (IDF), để từ phổ biến như "for" gần như không đóng góp (nếu một từ có trong mọi tài liệu, C(t) = N nên IDF = log 1 = 0); (3) cộng lại qua mọi từ của truy vấn; (4) xếp hạng tài liệu theo điểm.

**Elasticsearch và chỉ mục ngược.** Hai giải pháp truy xuất từ khoá phổ biến là Elasticsearch và BM25. Elasticsearch (Shay Banon, 2010), dựng trên Lucene, dùng cấu trúc dữ liệu **chỉ mục ngược** (inverted index): một từ điển ánh xạ từ sang các tài liệu chứa nó, cho phép tìm nhanh tài liệu theo từ. Chỉ mục có thể lưu thêm tần suất từ và số tài liệu chứa từ — hữu ích để tính TF-IDF. Bảng 6-1 của sách là ví dụ chỉ mục ngược đơn giản:

| Từ | Số tài liệu chứa từ | (Mã tài liệu, tần suất từ) cho mọi tài liệu chứa từ |
|---|---:|---|
| banana | 2 | (10, 3), (5, 2) |
| machine | 4 | (1, 5), (10, 1), (38, 9), (42, 5) |
| learning | 3 | (1, 5), (38, 7), (42, 5) |
| … | … | … |

**Ví dụ hôm nay (minh hoạ của người tổng hợp): tính TF-IDF trên chỉ mục ngược vừa chép.** Giả sử kho có N = 50 tài liệu và truy vấn là "machine learning". Dùng log tự nhiên:

- IDF(machine) = ln(50 / 4) = ln 12,5 ≈ 2,526; IDF(learning) = ln(50 / 3) ≈ 2,813.
- Tài liệu 1: 5 × 2,526 + 5 × 2,813 ≈ 26,70.
- Tài liệu 10: 1 × 2,526 + 0 ≈ 2,53.
- Tài liệu 38: 9 × 2,526 + 7 × 2,813 ≈ 42,43.
- Tài liệu 42: giống tài liệu 1, ≈ 26,70.
- Tài liệu 5 (chỉ chứa "banana"): 0.

Thứ hạng: 38 > 1 = 42 > 10. "learning" hiếm hơn "machine" (3 tài liệu so với 4) nên mỗi lần xuất hiện được tính nặng hơn một chút.

**BM25.** Okapi BM25 — thế hệ thứ 25 của thuật toán Best Matching — do Robertson và cộng sự phát triển trong thập niên 1980. Hàm chấm điểm của nó là một biến thể của TF-IDF: so với TF-IDF ngây thơ, BM25 chuẩn hoá điểm tần suất từ theo độ dài tài liệu, vì tài liệu dài hơn dễ chứa một từ hơn và có tần suất từ cao hơn. BM25 và các biến thể (BM25+, BM25F) vẫn được dùng rộng rãi trong công nghiệp và là mốc so sánh đáng gờm cho các thuật toán hiện đại phức tạp hơn như truy xuất embedding. Chú thích của sách giới thiệu bài của chính các tác giả BM25, "The Probabilistic Relevance Framework: BM25 and Beyond" (Robertson và Zaragoza, 2009), và dẫn tweet của Aravind Srinivas, CEO của Perplexity: "Cải thiện thực sự so với BM25 hay tìm kiếm toàn văn là việc khó."

Sách không chép công thức BM25. Người tổng hợp bổ sung dạng chuẩn (theo Robertson và Zaragoza 2009):

  Score(D, Q) = Σ_{i=1}^{q} IDF(t_i) × [ f(t_i, D) × (k₁ + 1) ] / [ f(t_i, D) + k₁ × (1 − b + b × |D| / avgdl) ]

trong đó |D| là độ dài tài liệu (số từ), avgdl là độ dài trung bình của tài liệu trong kho, k₁ (thường 1,2–2,0) điều khiển mức **bão hoà** của tần suất từ (từ xuất hiện lần thứ 10 đóng góp ít hơn nhiều so với lần thứ nhất), b (thường 0,75) điều khiển mức **chuẩn hoá theo độ dài**; IDF thường dùng dạng ln[(N − C(t) + 0,5) / (C(t) + 0,5) + 1].

**Ví dụ hôm nay (tiếp, minh hoạ của người tổng hợp):** giữ dữ liệu trên, thêm độ dài tài liệu: tài liệu 1 và 42 dài 100 từ, tài liệu 10 dài 300 từ, tài liệu 38 dài 1.000 từ (avgdl = 375), k₁ = 1,2, b = 0,75. Điểm BM25: tài liệu 1 và 42 ≈ 10,14; tài liệu 38 ≈ 8,36; tài liệu 10 ≈ 2,64. Tài liệu 38 đứng đầu theo TF-IDF ngây thơ nhưng xuống thứ hai theo BM25, vì 9 lần "machine" trong 1.000 từ là mật độ thấp hơn 5 lần trong 100 từ, và tần suất cao bị bão hoà.

**Tách từ (tokenization).** Một bước tác giả đã lướt qua là tách truy vấn thành các từ riêng. Cách đơn giản nhất là tách theo từ, mỗi từ là một "term". Nhưng cách này làm vỡ các cụm nhiều từ: "hot dog" bị tách thành "hot" và "dog", không phần nào giữ nghĩa gốc (bánh mì kẹp xúc xích). Một cách giảm nhẹ là coi các n-gram phổ biến nhất là một từ: nếu bigram "hot dog" phổ biến, nó được coi là một từ. Ngoài ra có thể chuyển mọi ký tự thành chữ thường, bỏ dấu câu, bỏ stop word (như "the", "and", "is"). Các giải pháp truy xuất từ khoá thường tự làm những việc này; các thư viện NLP cổ điển như NLTK (Natural Language Toolkit), spaCy và CoreNLP của Stanford cũng có chức năng tách từ.

**Truy xuất theo độ trùng n-gram.** Sách nhắc lại việc đo độ tương đồng từ vựng giữa hai văn bản bằng độ trùng n-gram (sách ghi "Chương 4"; nội dung này nằm ở Chương 3 — xem khối Lưu ý). Có thể truy xuất tài liệu theo độ trùng n-gram với truy vấn không? Có. Cách này tốt nhất khi truy vấn và tài liệu dài tương đương. Nếu tài liệu dài hơn truy vấn nhiều, khả năng chúng chứa n-gram của truy vấn tăng lên, nhiều tài liệu có điểm trùng cao như nhau, khó phân biệt tài liệu thực sự liên quan với tài liệu ít liên quan.

#### Truy xuất dựa trên embedding (Embedding-based retrieval, trang PDF 507–512)

Truy xuất dựa trên từ khoá tính độ liên quan ở mức từ vựng chứ không ở mức ngữ nghĩa. Như Chương 3 đã nói, bề ngoài của văn bản không nhất thiết phản ánh nghĩa của nó, nên có thể trả về tài liệu không đúng ý. Ví dụ truy vấn "transformer architecture" (kiến trúc transformer) có thể trả về tài liệu về thiết bị điện (máy biến áp) hay phim *Transformers*. Retriever dựa trên embedding thì xếp hạng tài liệu theo mức nghĩa của chúng gần với truy vấn; cách này còn gọi là **truy xuất ngữ nghĩa** (semantic retrieval).

Với truy xuất embedding, lập chỉ mục có thêm một việc: chuyển các đoạn dữ liệu gốc thành embedding. Cơ sở dữ liệu lưu các embedding đó gọi là **cơ sở dữ liệu vector** (vector database). Truy vấn gồm hai bước:

1. **Mô hình embedding:** chuyển truy vấn thành embedding, dùng cùng mô hình embedding đã dùng khi lập chỉ mục.
2. **Retriever:** lấy k đoạn có embedding gần embedding của truy vấn nhất. Số đoạn k phụ thuộc vào trường hợp sử dụng, mô hình sinh và truy vấn.

Sơ đồ của sách (Hình 6-3): trong khối "Index", bộ nhớ ngoài (tài liệu, bảng, lịch sử chat) đi qua **bộ chia đoạn** (splitter) rồi tới **mô hình embedding** (bước 1), embedding được lưu vào **VectorDB**; khi người dùng gửi truy vấn, truy vấn đi qua cùng mô hình embedding thành "query embedding", tới **retriever** (bước 2) đọc VectorDB, retriever trả "context liên quan tới truy vấn" cho **mô hình sinh** (bước 3), mô hình sinh trả phản hồi. Quy trình này đã đơn giản hoá; hệ truy xuất ngữ nghĩa thật có thể có thêm reranker để xếp hạng lại mọi ứng viên, và cache để giảm độ trễ. Chú thích của sách: quy trình truy xuất của RAG có nhiều bước giống hệ gợi ý truyền thống.

Embedding (đã bàn ở Chương 3) là vector nhằm giữ các thuộc tính quan trọng của dữ liệu gốc. Retriever dựa trên embedding không thể tốt nếu mô hình embedding kém.

**Tìm kiếm vector.** Truy xuất embedding mang thêm một thành phần mới: cơ sở dữ liệu vector. Lưu vector là phần dễ; phần khó là **tìm kiếm vector** — cho embedding của truy vấn, tìm và trả về các vector gần nó trong cơ sở dữ liệu. Vector phải được lập chỉ mục và lưu sao cho tìm nhanh và hiệu quả. Tìm kiếm vector không riêng gì AI tạo sinh: nó phổ biến trong mọi ứng dụng dùng embedding — tìm kiếm, gợi ý, tổ chức dữ liệu, truy xuất thông tin, phân cụm, phát hiện gian lận…

Tìm kiếm vector thường được đặt thành bài toán **tìm láng giềng gần nhất**: cho một truy vấn, tìm k vector gần nhất. Lời giải ngây thơ là **k-NN** (k-nearest neighbors):

1. Tính điểm tương đồng giữa embedding truy vấn và mọi vector trong cơ sở dữ liệu, dùng chỉ số như độ tương đồng cosine.
2. Xếp hạng mọi vector theo điểm tương đồng.
3. Trả về k vector có điểm cao nhất.

Cách này cho kết quả chính xác nhưng nặng tính toán và chậm; chỉ nên dùng cho tập dữ liệu nhỏ. (Người tổng hợp minh hoạ: với 10 triệu vector 1.024 chiều, mỗi truy vấn cần khoảng 10⁷ × 1.024 ≈ 10¹⁰ phép nhân–cộng.)

Với tập dữ liệu lớn, tìm kiếm vector thường dùng thuật toán **láng giềng gần nhất xấp xỉ** (approximate nearest neighbor, ANN). Các thư viện phổ biến: FAISS (Facebook AI Similarity Search, Johnson và cộng sự, 2017), ScaNN của Google (Scalable Nearest Neighbors, Sun và cộng sự, 2020), Annoy của Spotify (Bernhardsson, 2013) và Hnswlib (Hierarchical Navigable Small World, Malkov và Yashunin, 2016). Phần lớn nhà phát triển ứng dụng không tự viết tìm kiếm vector, nên tác giả chỉ tổng quan nhanh — hữu ích khi đánh giá giải pháp.

Nói chung, cơ sở dữ liệu vector tổ chức vector thành **xô** (bucket), **cây** hoặc **đồ thị**. Các thuật toán khác nhau ở heuristic dùng để tăng khả năng các vector giống nhau nằm gần nhau. Vector cũng có thể được **lượng tử hoá** (giảm độ chính xác số) hoặc **làm thưa**, vì vector lượng tử hoá và thưa tính toán nhẹ hơn. (Sách giới thiệu loạt bài của Zilliz cho ai muốn học thêm.) Các thuật toán đáng chú ý:

- **LSH** (locality-sensitive hashing — băm nhạy vị trí, Indyk và Motwani, 1999): thuật toán mạnh và linh hoạt, dùng được cho nhiều thứ ngoài vector. Nó băm các vector giống nhau vào cùng xô để tăng tốc tìm kiếm tương đồng, đổi một phần độ chính xác lấy hiệu quả. Có trong FAISS và Annoy.
- **HNSW** (Hierarchical Navigable Small World, Malkov và Yashunin, 2016): dựng đồ thị nhiều tầng, nút là vector, cạnh nối các vector giống nhau; tìm láng giềng gần nhất bằng cách đi theo các cạnh. Bản cài đặt của tác giả là mã nguồn mở, cũng có trong FAISS và Milvus.
- **Product quantization** (lượng tử hoá tích, Jégou và cộng sự, 2011): rút mỗi vector thành biểu diễn đơn giản hơn, ít chiều hơn, bằng cách tách vector thành nhiều vector con; khoảng cách được tính trên biểu diễn ít chiều, nhanh hơn nhiều. Đây là thành phần chủ chốt của FAISS và được hầu hết thư viện tìm kiếm vector phổ biến hỗ trợ.
- **IVF** (inverted file index — chỉ mục tệp ngược, Sivic và Zisserman, 2003): dùng phân cụm K-means để gom vector giống nhau vào cùng cụm. Tuỳ số vector trong cơ sở dữ liệu, thường đặt số cụm sao cho trung bình mỗi cụm có 100 tới 10.000 vector. Khi truy vấn, IVF tìm các tâm cụm gần embedding truy vấn nhất, và các vector trong các cụm đó thành láng giềng ứng viên. IVF cùng product quantization tạo nên xương sống của FAISS. (Người tổng hợp tính: với 10 triệu vector, quy tắc này cho 1.000 tới 100.000 cụm.)
- **Annoy** (Approximate Nearest Neighbors Oh Yeah, Bernhardsson, 2013): cách tiếp cận dựa trên cây. Nó dựng nhiều cây nhị phân, mỗi cây chia vector thành cụm theo tiêu chí ngẫu nhiên, ví dụ vẽ ngẫu nhiên một đường và chia vector thành hai nhánh theo đường đó. Khi tìm, nó duyệt các cây để gom láng giềng ứng viên. Spotify đã mở mã nguồn.

Còn các thuật toán khác như SPTAG của Microsoft (Space Partition Tree And Graph) và FLANN (Fast Library for Approximate Nearest Neighbors).

Dù cơ sở dữ liệu vector nổi lên thành một hạng mục riêng cùng với RAG, mọi cơ sở dữ liệu lưu được vector đều có thể gọi là cơ sở dữ liệu vector. Nhiều cơ sở dữ liệu truyền thống đã hoặc sẽ mở rộng để hỗ trợ lưu và tìm vector.

#### So sánh các thuật toán truy xuất (Comparing retrieval algorithms, trang PDF 512–518)

Truy xuất có lịch sử dài nên có nhiều giải pháp chín muồi; cả truy xuất từ khoá lẫn embedding đều tương đối dễ bắt đầu. Mỗi cách có ưu nhược riêng.

- **Truy xuất từ khoá** nói chung nhanh hơn nhiều so với truy xuất embedding, cả khi lập chỉ mục lẫn khi truy vấn: trích từ nhanh hơn sinh embedding, và ánh xạ từ sang tài liệu chứa nó rẻ hơn tìm láng giềng gần nhất. Nó cũng chạy tốt ngay từ đầu: Elasticsearch và BM25 đã vận hành thành công nhiều ứng dụng tìm kiếm và truy xuất. Nhưng sự đơn giản cũng có nghĩa là ít thành phần để tinh chỉnh nhằm cải thiện.
- **Truy xuất embedding** có thể cải thiện đáng kể theo thời gian và vượt truy xuất từ khoá: có thể finetune mô hình embedding và retriever, riêng rẽ, cùng nhau hoặc cùng với mô hình sinh. Nhưng chuyển dữ liệu thành embedding có thể làm mờ từ khoá, như mã lỗi cụ thể (ví dụ EADDRNOTAVAIL (99)) hay tên sản phẩm, khiến chúng khó tìm về sau. Có thể khắc phục bằng cách kết hợp hai cách truy xuất (xem phần kết hợp bên dưới).

**Đánh giá retriever.** Chất lượng retriever có thể đánh giá qua chất lượng dữ liệu nó lấy về. Hai chỉ số các khung đánh giá RAG hay dùng là **context precision** và **context recall** (gọi tắt precision và recall; context precision còn gọi là context relevance):

- **Context precision:** trong số tài liệu được lấy về, bao nhiêu phần trăm liên quan tới truy vấn?
- **Context recall:** trong số tài liệu liên quan tới truy vấn, bao nhiêu phần trăm được lấy về?

Để tính, dựng một tập đánh giá gồm danh sách truy vấn kiểm thử và một tập tài liệu. Với mỗi truy vấn, gán nhãn mỗi tài liệu là liên quan hay không — do người hoặc AI judge làm. Rồi tính precision và recall của retriever trên tập này. Trong sản xuất, một số khung RAG chỉ hỗ trợ context precision: muốn tính context recall cho một truy vấn phải gán nhãn độ liên quan của *mọi* tài liệu trong cơ sở dữ liệu với truy vấn đó; còn context precision chỉ cần so các tài liệu đã lấy với truy vấn, việc AI judge làm được.

Nếu quan tâm thứ hạng (tài liệu liên quan hơn nên đứng trước), có thể dùng NDCG (normalized discounted cumulative gain), MAP (mean average precision) và MRR (mean reciprocal rank).

Với truy xuất ngữ nghĩa còn phải đánh giá chất lượng embedding. Như Chương 3 đã bàn, embedding có thể đánh giá độc lập — tốt nếu tài liệu giống nhau hơn có embedding gần nhau hơn — hoặc qua mức hữu ích cho nhiệm vụ cụ thể. Benchmark MTEB (Muennighoff và cộng sự, 2023) đánh giá embedding trên nhiều nhiệm vụ, gồm truy xuất, phân loại, phân cụm. Chất lượng retriever cũng phải được đánh giá trong bối cảnh cả hệ RAG: rốt cuộc retriever tốt là retriever giúp hệ thống sinh câu trả lời tốt (đánh giá đầu ra mô hình sinh ở Chương 3 và 4).

**Chi phí và độ trễ.** Lời hứa hiệu năng của truy xuất ngữ nghĩa có đáng theo đuổi hay không tuỳ mức bạn ưu tiên chi phí và độ trễ, nhất là ở pha truy vấn. Vì phần lớn độ trễ của RAG đến từ việc sinh đầu ra, nhất là đầu ra dài, độ trễ thêm do sinh embedding truy vấn và tìm vector có thể nhỏ so với tổng; dù vậy, nó vẫn có thể ảnh hưởng trải nghiệm người dùng. Chi phí là mối lo khác: sinh embedding tốn tiền, nhất là khi dữ liệu đổi thường xuyên và phải sinh lại embedding — hình dung phải sinh embedding cho 100 triệu tài liệu mỗi ngày. Tuỳ cơ sở dữ liệu vector, lưu trữ và truy vấn vector cũng có thể đắt. Không hiếm công ty chi cho cơ sở dữ liệu vector bằng một phần năm, thậm chí một nửa chi tiêu cho API mô hình.

Bảng 6-2 của sách so sánh hai cách:

| | Truy xuất dựa trên từ khoá | Truy xuất dựa trên embedding |
|---|---|---|
| Tốc độ truy vấn | Nhanh hơn nhiều so với truy xuất embedding | Sinh embedding truy vấn và tìm vector có thể chậm |
| Hiệu năng | Thường mạnh ngay từ đầu, nhưng khó cải thiện. Có thể lấy nhầm tài liệu do từ đa nghĩa | Có thể vượt truy xuất từ khoá nhờ finetuning. Cho phép dùng truy vấn tự nhiên hơn vì tập trung vào nghĩa thay vì từ |
| Chi phí | Rẻ hơn nhiều so với truy xuất embedding | Embedding, lưu trữ vector và giải pháp tìm vector có thể đắt |

**Đánh đổi giữa lập chỉ mục và truy vấn.** Chỉ mục càng chi tiết, truy xuất càng chính xác, nhưng lập chỉ mục càng chậm và tốn bộ nhớ. Tác giả lấy ví dụ dựng chỉ mục khách hàng tiềm năng: thêm chi tiết (tên, công ty, email, điện thoại, sở thích) giúp tìm người phù hợp dễ hơn nhưng dựng lâu hơn và tốn chỗ hơn. Nói chung, chỉ mục chi tiết như HNSW cho độ chính xác cao và truy vấn nhanh nhưng dựng tốn nhiều thời gian và bộ nhớ; chỉ mục đơn giản như LSH dựng nhanh và nhẹ hơn nhưng truy vấn chậm hơn và kém chính xác hơn.

Trang ANN-Benchmarks so sánh các thuật toán ANN trên nhiều tập dữ liệu bằng bốn chỉ số chính, có tính tới đánh đổi lập chỉ mục–truy vấn:

- **Recall:** tỷ lệ láng giềng gần nhất thật mà thuật toán tìm được.
- **Số truy vấn mỗi giây (QPS):** quan trọng với ứng dụng lưu lượng cao.
- **Thời gian dựng chỉ mục:** đặc biệt quan trọng nếu phải cập nhật chỉ mục thường xuyên (vì dữ liệu đổi).
- **Kích thước chỉ mục:** quan trọng để đánh giá khả năng mở rộng và nhu cầu lưu trữ.

Ngoài ra, BEIR (Benchmarking IR, Thakur và cộng sự, 2021) là bộ khung đánh giá truy xuất, hỗ trợ 14 benchmark truy xuất phổ biến.

Tóm lại, chất lượng hệ RAG phải được đánh giá cả theo từng thành phần lẫn đầu–cuối: (1) đánh giá chất lượng truy xuất; (2) đánh giá đầu ra RAG cuối cùng; (3) đánh giá embedding (với truy xuất embedding).

#### Kết hợp các thuật toán truy xuất (Combining retrieval algorithms, trang PDF 518–520)

Vì mỗi thuật toán có ưu điểm riêng, hệ truy xuất sản xuất thường kết hợp nhiều cách. Kết hợp truy xuất từ khoá với truy xuất embedding gọi là **hybrid search** (tìm kiếm lai).

**Nối tiếp.** Trước tiên một retriever rẻ, kém chính xác (như hệ từ khoá) lấy ứng viên; sau đó một cơ chế chính xác hơn nhưng đắt hơn (như k-nearest neighbors) chọn những ứng viên tốt nhất. Bước thứ hai gọi là **xếp hạng lại** (reranking). Ví dụ: với từ "transformer", lấy mọi tài liệu chứa từ này, dù nói về thiết bị điện, kiến trúc nơ-ron hay bộ phim; rồi dùng tìm kiếm vector để chọn trong đó các tài liệu thực sự liên quan tới truy vấn về transformer. Ví dụ khác, truy vấn "Ai chịu trách nhiệm cho doanh số lớn nhất với X?": trước hết lấy mọi tài liệu liên quan tới X bằng từ khoá X, rồi dùng tìm kiếm vector để lấy context liên quan tới "Ai chịu trách nhiệm cho doanh số lớn nhất?".

**Song song (ensemble).** Nhớ rằng retriever xếp hạng tài liệu theo điểm liên quan. Có thể dùng nhiều retriever lấy ứng viên cùng lúc, rồi gộp các bảng xếp hạng thành bảng cuối. Một thuật toán gộp là **reciprocal rank fusion** (RRF — hợp nhất theo nghịch đảo thứ hạng, Cormack và cộng sự, 2009). Nó cho mỗi tài liệu một điểm dựa trên thứ hạng do từng retriever đưa ra. Trực giác: xếp thứ nhất được 1/1 = 1 điểm, thứ hai được 1/2 = 0,5 điểm; hạng càng cao điểm càng cao. Điểm cuối của tài liệu là tổng điểm theo mọi retriever: xếp thứ nhất ở một retriever và thứ hai ở retriever khác thì được 1 + 0,5 = 1,5. Đây là bản đơn giản hoá; công thức thật cho tài liệu D là:

  Score(D) = Σ_{i=1}^{n} 1 / (k + r_i(D))

- n là số bảng xếp hạng; mỗi bảng do một retriever tạo ra.
- r_i(D) là thứ hạng của tài liệu theo retriever i.
- k là hằng số để tránh chia cho 0 và để điều khiển ảnh hưởng của các tài liệu xếp hạng thấp. Giá trị thường dùng của k là 60.

**Ví dụ hôm nay (minh hoạ của người tổng hợp):** hai retriever, k = 60.

| Tài liệu | Hạng theo BM25 | Hạng theo embedding | Điểm RRF (k = 60) | Điểm bản đơn giản (k = 0) |
|---|---:|---:|---:|---:|
| A | 1 | 2 | 1/61 + 1/62 ≈ 0,0325 | 1,5 |
| B | 3 | 3 | 2/63 ≈ 0,0317 | 0,67 |
| C | 1 | 10 | 1/61 + 1/70 ≈ 0,0307 | 1,1 |
| D | 1 | không có | 1/61 ≈ 0,0164 | 1 |

Với k = 60, tài liệu B (hạng 3 ở cả hai) gần ngang A và vượt C (hạng 1 và 10); với k = 0, C vượt xa B. k lớn làm phẳng chênh lệch giữa các hạng đầu, thưởng cho tài liệu được *nhiều* retriever đồng ý thay vì tài liệu được *một* retriever xếp rất cao.

### 5. Tối ưu truy xuất (Retrieval Optimization, trang PDF 520–530)

Tuỳ nhiệm vụ, một số chiến thuật làm tăng khả năng lấy được tài liệu liên quan. Bốn chiến thuật được bàn: chiến lược chia đoạn, xếp hạng lại, viết lại truy vấn và truy xuất có ngữ cảnh.

#### Chiến lược chia đoạn (Chunking strategy, trang PDF 520–523)

Dữ liệu nên được lập chỉ mục thế nào tuỳ vào cách bạn định truy xuất nó. Phần trước giả định tài liệu đã được chia thành đoạn vừa phải; phần này bàn các chiến lược chia đoạn — một cân nhắc quan trọng vì nó có thể ảnh hưởng lớn tới hiệu năng truy xuất.

- **Chia đều theo đơn vị.** Cách đơn giản nhất: chia tài liệu thành các đoạn dài bằng nhau theo một đơn vị — ký tự, từ, câu, đoạn văn. Ví dụ đoạn 2.048 ký tự hoặc 512 từ; hoặc mỗi đoạn một số câu cố định (như 20 câu) hay một số đoạn văn (như mỗi đoạn văn là một đoạn).
- **Chia đệ quy.** Chia bằng các đơn vị nhỏ dần cho tới khi mỗi đoạn vừa kích thước tối đa: chia tài liệu thành các mục; mục quá dài thì chia thành đoạn văn; đoạn văn vẫn quá dài thì chia thành câu. Cách này giảm khả năng các phần văn bản liên quan bị cắt rời tuỳ tiện.
- **Chia đặc thù.** Có bộ chia riêng cho từng ngôn ngữ lập trình; tài liệu hỏi–đáp có thể chia theo cặp câu hỏi–câu trả lời, mỗi cặp một đoạn; văn bản tiếng Trung có thể phải chia khác tiếng Anh. Chú thích của sách: một số đội nói hệ truy xuất của họ chạy tốt nhất khi dữ liệu được tổ chức dạng hỏi–đáp.
- **Chồng lấn (overlap).** Chia không chồng lấn có thể cắt giữa một ý quan trọng. Câu "I left my wife a note" (tôi để lại cho vợ một mẩu giấy) nếu cắt thành "I left my wife" (tôi bỏ vợ) và "a note" (một mẩu giấy) thì không đoạn nào giữ được thông tin then chốt — đoạn thứ nhất còn mang nghĩa khác hẳn. Chồng lấn đảm bảo thông tin ở ranh giới có mặt trong ít nhất một đoạn. Với đoạn 2.048 ký tự, có thể đặt chồng lấn khoảng 20 ký tự. (Người tổng hợp tính: bước nhảy là 2.048 − 20 = 2.028 ký tự, nên một tài liệu 10.000 ký tự cho ⌈(10.000 − 20) / 2.028⌉ = 5 đoạn.)
- **Giới hạn kích thước.** Kích thước đoạn không được vượt độ dài context tối đa của mô hình sinh; với truy xuất embedding, cũng không được vượt giới hạn context của mô hình embedding.
- **Chia theo token.** Có thể dùng token, do tokenizer của mô hình sinh xác định, làm đơn vị. Ví dụ dùng Llama 3 làm mô hình sinh thì tách tài liệu bằng tokenizer của Llama 3 rồi chia theo ranh giới token. Cách này tiện cho các mô hình phía sau, nhưng nếu đổi sang mô hình sinh có tokenizer khác thì phải lập chỉ mục lại.

**Kích thước đoạn quan trọng dù chọn chiến lược nào.**

- Đoạn nhỏ cho thông tin **đa dạng** hơn: nhét được nhiều đoạn hơn vào context — giảm một nửa kích thước đoạn thì nhét được gấp đôi số đoạn — cho mô hình phạm vi thông tin rộng hơn, có thể trả lời tốt hơn.
- Nhưng đoạn nhỏ có thể **làm mất thông tin quan trọng**. Hình dung một tài liệu chứa thông tin quan trọng về chủ đề X suốt từ đầu tới cuối, nhưng chữ X chỉ xuất hiện ở nửa đầu. Chia làm hai đoạn thì nửa sau có thể không được lấy về, và mô hình không dùng được thông tin trong đó.
- Đoạn nhỏ còn **tăng chi phí tính toán**, nhất là với truy xuất embedding: giảm một nửa kích thước đoạn nghĩa là gấp đôi số đoạn phải lập chỉ mục, gấp đôi số vector embedding phải sinh và lưu; không gian tìm kiếm vector lớn gấp đôi, có thể làm chậm truy vấn.

Không có kích thước đoạn hay kích thước chồng lấn tốt nhất cho mọi trường hợp; phải thử nghiệm.

#### Xếp hạng lại (Reranking, trang PDF 523–524)

Thứ hạng ban đầu do retriever tạo có thể được xếp lại cho chính xác hơn. Xếp hạng lại đặc biệt hữu ích khi cần giảm số tài liệu lấy về, để vừa context của mô hình hoặc để giảm số token đầu vào. Một mẫu phổ biến đã nêu ở phần kết hợp thuật toán: retriever rẻ nhưng kém chính xác lấy ứng viên, rồi cơ chế chính xác hơn nhưng đắt hơn xếp lại. Tài liệu cũng có thể được xếp lại theo thời gian, cho dữ liệu mới hơn trọng số cao hơn — hữu ích cho ứng dụng nhạy thời gian như tổng hợp tin tức, chat với email của bạn (chatbot trả lời câu hỏi về email), hay phân tích thị trường chứng khoán.

Xếp hạng lại context khác xếp hạng lại trong tìm kiếm truyền thống ở chỗ vị trí chính xác ít quan trọng hơn. Trong tìm kiếm, hạng (thứ nhất hay thứ năm) rất quan trọng. Trong context, thứ tự tài liệu vẫn có ảnh hưởng vì nó tác động tới mức mô hình xử lý chúng — mô hình có thể hiểu tài liệu ở đầu và cuối context tốt hơn (mục "Context Length and Context Efficiency" của Chương 5) — nhưng miễn là tài liệu được đưa vào, ảnh hưởng của thứ tự nhỏ hơn so với xếp hạng tìm kiếm.

#### Viết lại truy vấn (Query rewriting, trang PDF 524–526)

Viết lại truy vấn còn gọi là tái lập truy vấn (query reformulation), chuẩn hoá truy vấn (query normalization), đôi khi là mở rộng truy vấn (query expansion). Xét hội thoại:

> User: When was the last time John Doe bought something from us?
> AI: John last bought a Fruity Fedora hat from us two weeks ago, on January 3, 2030.
> User: How about Emily Doe?

(Người dùng: Lần cuối John Doe mua hàng của chúng ta là khi nào? — AI: John mua một chiếc mũ Fruity Fedora hai tuần trước, ngày 3/1/2030. — Người dùng: Còn Emily Doe thì sao?)

Câu cuối "How about Emily Doe?" mơ hồ nếu không có context. Dùng nguyên văn câu này để truy xuất sẽ lấy về kết quả không liên quan. Phải viết lại cho phản ánh điều người dùng thực sự hỏi, và câu mới phải tự đủ nghĩa: "When was the last time Emily Doe bought something from us?" (Lần cuối Emily Doe mua hàng của chúng ta là khi nào?).

Viết lại truy vấn không riêng gì RAG. Trong máy tìm kiếm truyền thống, việc này thường làm bằng heuristic. Trong ứng dụng AI, có thể dùng mô hình AI khác với prompt kiểu "Given the following conversation, rewrite the last user input to reflect what the user is actually asking" (cho đoạn hội thoại sau, viết lại câu cuối của người dùng để phản ánh điều họ thực sự hỏi). Hình 6-4 của sách cho thấy ChatGPT nhận prompt này cùng ba lượt hội thoại trên và trả về đúng câu "When was the last time Emily Doe bought something from us?".

Viết lại truy vấn có thể phức tạp, nhất là khi cần xác định danh tính (identity resolution) hoặc thêm tri thức khác. Nếu người dùng hỏi "How about his wife?" (còn vợ anh ấy thì sao?), trước hết phải tra cơ sở dữ liệu xem vợ anh ấy là ai. Nếu không có thông tin này, mô hình viết lại phải thừa nhận truy vấn không giải được, thay vì bịa ra một cái tên dẫn tới câu trả lời sai.

#### Truy xuất có ngữ cảnh (Contextual retrieval, trang PDF 526–529)

Ý tưởng là bổ sung cho mỗi đoạn context liên quan để dễ lấy đúng đoạn hơn.

- **Metadata:** kỹ thuật đơn giản là thêm thẻ và từ khoá. Với thương mại điện tử, sản phẩm có thể được bổ sung mô tả và đánh giá; ảnh và video có thể được truy vấn qua tiêu đề hay chú thích.
- **Thực thể:** metadata có thể gồm thực thể tự động trích từ đoạn. Nếu tài liệu chứa thuật ngữ cụ thể như mã lỗi EADDRNOTAVAIL (99), thêm chúng vào metadata giúp hệ thống lấy được tài liệu theo từ khoá đó, kể cả sau khi tài liệu đã chuyển thành embedding.
- **Câu hỏi mà đoạn trả lời được:** với hỗ trợ khách hàng, mỗi bài viết có thể được bổ sung các câu hỏi liên quan. Bài hướng dẫn đặt lại mật khẩu có thể được thêm các truy vấn như "How to reset password?", "I forgot my password", "I can't log in", hay cả "Help, I can't find my account".
- **Ngữ cảnh của tài liệu gốc:** khi tài liệu bị chia thành nhiều đoạn, một số đoạn thiếu context để retriever hiểu chúng nói về gì. Có thể bổ sung cho mỗi đoạn context từ tài liệu gốc, như tiêu đề và tóm tắt của tài liệu.

Anthropic dùng mô hình AI sinh một đoạn context ngắn, thường 50–100 token, giải thích đoạn và quan hệ của nó với tài liệu gốc. Prompt Anthropic dùng (Anthropic, 2024):

```text
<document>
{{WHOLE_DOCUMENT}}
</document>
Here is the chunk we want to situate within
the whole document:
<chunk>
{{CHUNK_CONTENT}}
</chunk>
Please give a short succinct context to
situate this chunk within the overall document
for the purposes of improving search retrieval
of the chunk. Answer only with the succinct
context and nothing else.
```

(Dịch ý: đưa toàn bộ tài liệu và đoạn cần đặt vào bối cảnh; yêu cầu mô hình viết một context ngắn gọn đặt đoạn này trong tổng thể tài liệu nhằm cải thiện truy xuất, và chỉ trả lời bằng context đó.)

Context sinh ra được nối vào trước mỗi đoạn, và đoạn đã bổ sung được thuật toán truy xuất lập chỉ mục. Sơ đồ của Anthropic (Hình 6-5 của sách, khối "Preprocessing (new)"): kho tài liệu (corpus) được chia thành Chunk 1, Chunk 2, …, Chunk X; với mỗi đoạn, chạy prompt "đặt đoạn này trong tài liệu"; Claude trả 50–100 token context, nối trước đoạn tương ứng thành "Context 1 + Chunk 1", …, "Context X + Chunk X"; các đoạn này đi song song vào hai nhánh: mô hình embedding → cơ sở dữ liệu vector, và TF-IDF → chỉ mục TF-IDF; truy vấn của người dùng đi vào cả hai.

#### Khung "Evaluating Retrieval Solutions" (trang PDF 530)

Các yếu tố cần cân nhắc khi đánh giá một giải pháp truy xuất:

- Hỗ trợ những cơ chế truy xuất nào? Có hybrid search không?
- Nếu là cơ sở dữ liệu vector: hỗ trợ mô hình embedding và thuật toán tìm vector nào?
- Khả năng mở rộng về lưu trữ dữ liệu và lưu lượng truy vấn? Có hợp với kiểu lưu lượng của bạn không?
- Lập chỉ mục dữ liệu của bạn mất bao lâu? Xử lý (thêm/xoá) hàng loạt được bao nhiêu dữ liệu một lần?
- Độ trễ truy vấn với từng thuật toán truy xuất?
- Nếu là dịch vụ được quản lý: cấu trúc giá ra sao — theo khối lượng tài liệu/vector hay theo khối lượng truy vấn?

Danh sách này chưa gồm các chức năng thường gắn với giải pháp doanh nghiệp như kiểm soát truy cập, tuân thủ, tách mặt phẳng dữ liệu và mặt phẳng điều khiển.

### 6. RAG ngoài văn bản (RAG Beyond Texts, trang PDF 530–535)

Nguồn dữ liệu ngoài không chỉ là văn bản mà còn có thể là dữ liệu đa phương thức và dữ liệu bảng.

#### RAG đa phương thức (Multimodal RAG, trang PDF 531–532)

Nếu mô hình sinh là đa phương thức, context có thể được bổ sung cả ảnh, video, âm thanh… từ nguồn ngoài (tác giả dùng ảnh cho gọn; thay bằng phương thức nào cũng được). Cho một truy vấn, retriever lấy cả văn bản và ảnh liên quan. Ví dụ với "What's the color of the house in the Pixar movie Up?" (ngôi nhà trong phim *Up* của Pixar màu gì?), retriever có thể lấy một bức ảnh ngôi nhà trong *Up* để giúp mô hình trả lời. Sơ đồ của sách (Hình 6-6): cơ sở dữ liệu văn bản và cơ sở dữ liệu ảnh cùng nối vào retriever; retriever đưa cho mô hình sinh cả đoạn văn "Inside, the house from Up …" lẫn một bức ảnh ngôi nhà treo bóng bay (ảnh minh hoạ tự vẽ, không phải ảnh thật vì lý do bản quyền); mô hình sinh trả lời người dùng.

Nếu ảnh có metadata — tiêu đề, thẻ, chú thích — có thể lấy ảnh qua metadata: ảnh được lấy nếu chú thích của nó được coi là liên quan tới truy vấn. Muốn lấy ảnh theo *nội dung*, cần cách so ảnh với truy vấn. Nếu truy vấn là văn bản, cần mô hình embedding đa phương thức sinh embedding cho cả ảnh và văn bản. Với CLIP (Radford và cộng sự, 2021), retriever làm như sau:

1. Sinh embedding CLIP cho mọi dữ liệu, cả văn bản và ảnh, lưu vào cơ sở dữ liệu vector.
2. Cho một truy vấn, sinh embedding CLIP của nó.
3. Tìm trong cơ sở dữ liệu vector mọi ảnh và văn bản có embedding gần embedding truy vấn.

#### RAG với dữ liệu bảng (RAG with tabular data, trang PDF 532–535)

Phần lớn ứng dụng làm việc không chỉ với dữ liệu phi cấu trúc mà cả dữ liệu bảng; nhiều truy vấn cần thông tin từ bảng. Quy trình bổ sung context bằng dữ liệu bảng khác hẳn quy trình RAG cổ điển.

Ví dụ: bạn làm cho trang thương mại điện tử Kitty Vogue chuyên thời trang cho mèo (ví dụ tưởng tượng). Cửa hàng có bảng đơn hàng tên Sales (Bảng 6-3 của sách, các cột đầy đủ lấy theo Hình 6-7):

| Order ID | Timestamp | Product ID | Product | Giá/đơn vị (USD) | Units | Total |
|---:|---|---:|---|---:|---:|---:|
| 1 | … | 2044 | Meow Mix Seasoning | 10,99 | 1 | 10,99 |
| 2 | … | 3492 | Purr & Shake | 25 | 2 | 50 |
| 3 | … | 2045 | Fruity Fedora | 18 | 1 | 18 |
| … | … | … | … | … | … | … |

Để trả lời "How many units of Fruity Fedora were sold in the last 7 days?" (bao nhiêu chiếc Fruity Fedora được bán trong 7 ngày qua?), hệ thống phải truy vấn bảng này lấy mọi đơn có Fruity Fedora và cộng số lượng. Giả sử bảng truy vấn được bằng SQL, câu SQL có thể là:

```sql
SELECT SUM(units) AS total_units_sold
FROM Sales
WHERE product_name = 'Fruity Fedora'
AND timestamp >= DATE_SUB(CURDATE(), INTERVAL 7 DAY);
```

(Dòng cuối bị cắt trong sách; người tổng hợp hoàn thành theo cú pháp MySQL.)

Quy trình (Hình 6-7 của sách), hệ thống phải sinh được và chạy được câu SQL:

1. **Text-to-SQL:** dựa trên truy vấn người dùng và lược đồ (schema) bảng được cung cấp, xác định câu SQL cần chạy. Text-to-SQL là một ví dụ của semantic parsing (Chương 2).
2. **Chạy SQL:** thực thi câu SQL.
3. **Sinh:** sinh phản hồi dựa trên kết quả SQL và truy vấn gốc.

Trong sơ đồ, câu hỏi đi vào khối "Text-to-SQL → SQL execution" đọc bảng Sales; "kết quả SQL" đi xuống mô hình sinh; câu hỏi gốc cũng đi thẳng tới mô hình sinh; mô hình sinh trả lời người dùng.

Ở bước text-to-SQL, nếu có quá nhiều bảng mà lược đồ không vừa context, có thể cần một bước trung gian dự đoán bảng nào dùng cho mỗi truy vấn. Text-to-SQL có thể do chính mô hình sinh câu trả lời cuối làm, hoặc một mô hình text-to-SQL chuyên biệt.

Phần này đã cho thấy các công cụ như retriever và bộ chạy SQL giúp mô hình xử lý nhiều truy vấn hơn và trả lời tốt hơn. Cho mô hình nhiều công cụ hơn có làm nó giỏi hơn nữa không? Dùng công cụ là đặc trưng cốt lõi của mẫu hình agent.

### 7. Agent (Agents, trang PDF 535–536)

Nhiều người coi agent thông minh là mục tiêu tối hậu của AI. Sách kinh điển của Stuart Russell và Peter Norvig, *Artificial Intelligence: A Modern Approach* (Prentice Hall, 1995), định nghĩa ngành nghiên cứu trí tuệ nhân tạo là "nghiên cứu và thiết kế các agent hợp lý" (the study and design of rational agents).

Năng lực chưa từng có của mô hình nền tảng mở cửa cho các ứng dụng agent trước đây không tưởng tượng nổi: agent tự chủ, thông minh làm trợ lý, đồng nghiệp, huấn luyện viên của ta. Chúng có thể giúp dựng website, thu thập dữ liệu, lên kế hoạch chuyến đi, nghiên cứu thị trường, quản lý tài khoản khách hàng, tự động nhập liệu, chuẩn bị cho ta phỏng vấn, phỏng vấn ứng viên, đàm phán hợp đồng… Khả năng có vẻ vô tận và giá trị kinh tế tiềm năng rất lớn.

**Cảnh báo của sách:** agent chạy bằng AI là lĩnh vực mới nổi, chưa có khung lý thuyết vững để định nghĩa, phát triển và đánh giá. Phần này là nỗ lực hết mức để dựng một khung từ tài liệu hiện có, nhưng sẽ thay đổi theo lĩnh vực; so với phần còn lại của sách, phần này mang tính thử nghiệm hơn.

Phần agent đi qua: tổng quan; hai yếu tố quyết định năng lực agent là công cụ và lập kế hoạch; rồi các kiểu hỏng mới và cách đánh giá. Dù agent là mới, chúng dựng trên các khái niệm đã có trong sách: tự phê bình, chain-of-thought, đầu ra có cấu trúc.

### 8. Tổng quan về agent (Agent Overview, trang PDF 536–540)

Từ "agent" được dùng trong nhiều bối cảnh kỹ thuật: software agent, intelligent agent, user agent, conversational agent, reinforcement learning agent. Vậy agent chính xác là gì?

**Agent là bất cứ thứ gì có thể cảm nhận môi trường của nó và tác động lên môi trường đó.** (Chú thích của sách: *Artificial Intelligence: A Modern Approach* định nghĩa agent là bất cứ thứ gì có thể được xem là cảm nhận môi trường qua cảm biến và tác động lên môi trường qua cơ cấu chấp hành.) Nghĩa là agent được đặc trưng bởi **môi trường** nó hoạt động và **tập hành động** nó thực hiện được.

**Môi trường** do trường hợp sử dụng xác định. Agent chơi game (Minecraft, cờ vây, Dota) thì game là môi trường. Agent thu thập tài liệu từ internet thì môi trường là internet. Robot nấu ăn thì môi trường là nhà bếp. Xe tự lái thì môi trường là hệ thống đường và khu vực xung quanh.

**Tập hành động** của agent AI được mở rộng bởi các công cụ nó được dùng. Nhiều ứng dụng AI tạo sinh ta dùng hằng ngày là agent có công cụ, dù đơn giản. ChatGPT là một agent: nó tìm web, chạy mã Python, tạo ảnh. Hệ RAG là agent, và các bộ truy xuất văn bản, truy xuất ảnh, chạy SQL là công cụ của nó.

Môi trường và bộ công cụ phụ thuộc chặt vào nhau. Môi trường quyết định công cụ nào agent có thể dùng: nếu môi trường là ván cờ vua, hành động khả dĩ duy nhất là các nước đi hợp lệ. Ngược lại, bộ công cụ giới hạn môi trường agent hoạt động được: robot chỉ biết bơi thì chỉ hoạt động dưới nước.

**SWE-agent** (Yang và cộng sự, 2024) là agent viết mã dựng trên GPT-4. Theo sơ đồ của sách (Hình 6-8), "LM agent" giao tiếp với máy tính qua một "giao diện agent–máy tính": phía đi có các lệnh thân thiện với mô hình ngôn ngữ — duyệt repo (navigate repo), tìm tệp (search files), xem tệp (view files), sửa dòng (edit lines) — gửi tới máy tính gồm terminal và hệ tệp (ví dụ thư mục sklearn/, examples/, tệp README.rst); phía về là "phản hồi môi trường thân thiện với mô hình ngôn ngữ".

Agent AI nhằm hoàn thành nhiệm vụ do người dùng giao trong đầu vào. Trong agent AI, AI là bộ não: xử lý thông tin nhận được (nhiệm vụ và phản hồi từ môi trường), lập kế hoạch một chuỗi hành động để đạt nhiệm vụ, và xác định nhiệm vụ đã xong chưa.

**Ví dụ Kitty Vogue.** Hệ RAG với dữ liệu bảng ở trên là một agent đơn giản có ba hành động: sinh phản hồi, sinh câu SQL, chạy SQL. Với truy vấn "Project the sales revenue for Fruity Fedora over the next three months" (dự báo doanh thu Fruity Fedora trong ba tháng tới), agent có thể làm chuỗi hành động sau:

1. Suy luận cách làm. Nó có thể quyết định rằng để dự báo doanh số tương lai, trước hết cần số liệu doanh số năm năm qua. (Suy luận của agent hiện ra như phản hồi trung gian.)
2. Gọi sinh SQL để tạo câu truy vấn lấy doanh số năm năm qua.
3. Gọi chạy SQL.
4. Suy luận về đầu ra công cụ và mức hữu ích của nó cho dự báo. Nó có thể kết luận các số này chưa đủ để dự báo tin cậy, có thể do thiếu giá trị, và quyết định cần thêm thông tin về các chiến dịch tiếp thị trước đây.
5. Gọi sinh SQL để tạo câu truy vấn về các chiến dịch tiếp thị.
6. Gọi chạy SQL.
7. Suy luận rằng thông tin mới đã đủ, và sinh dự báo.
8. Suy luận rằng nhiệm vụ đã hoàn thành.

**Agent cần mô hình mạnh hơn** so với trường hợp không phải agent, vì hai lý do:

- **Lỗi cộng dồn:** agent thường phải làm nhiều bước, và độ chính xác tổng giảm khi số bước tăng. Nếu mỗi bước đúng 95%, sau 10 bước độ chính xác còn 60%, sau 100 bước chỉ còn 0,6%. (Người tổng hợp kiểm tra: 0,95¹⁰ ≈ 0,599; 0,95¹⁰⁰ ≈ 0,0059 — số của sách đúng, với giả định các bước độc lập và một bước sai làm hỏng cả chuỗi. Để đạt 90% sau 10 bước, mỗi bước cần đúng 0,9^(1/10) ≈ 98,95%.)
- **Rủi ro cao hơn:** có công cụ, agent làm được việc có tác động lớn hơn, nhưng mọi thất bại có thể gây hậu quả nặng hơn.

Một nhiệm vụ nhiều bước có thể tốn thời gian và tiền để chạy (chú thích của sách: một lời phàn nàn thời đầu là agent chỉ giỏi đốt tín dụng API của bạn). Tuy vậy, nếu agent tự chủ được, chúng tiết kiệm nhiều thời gian của con người, xứng đáng chi phí.

Trong một môi trường cho trước, thành công của agent phụ thuộc vào **bộ công cụ** nó được dùng và **sức mạnh của bộ lập kế hoạch AI**.

### 9. Công cụ (Tools, trang PDF 540–546)

Một hệ thống không cần công cụ ngoài để là agent, nhưng không có công cụ, năng lực của agent bị hạn chế. Tự thân, một mô hình thường làm được một hành động — LLM sinh văn bản, mô hình sinh ảnh sinh ảnh. Công cụ ngoài làm agent mạnh hơn rất nhiều.

Công cụ giúp agent vừa cảm nhận môi trường vừa tác động lên nó. Hành động cho agent cảm nhận môi trường là **hành động chỉ đọc** (read-only actions); hành động cho agent tác động lên môi trường là **hành động ghi** (write actions). Phần này tổng quan các loại công cụ; cách dùng công cụ được bàn ở phần lập kế hoạch.

Tập công cụ agent được dùng là **bộ công cụ** (tool inventory) của nó. Vì bộ công cụ quyết định agent làm được gì, phải cân nhắc kỹ cho agent công cụ nào và bao nhiêu. Nhiều công cụ cho nhiều năng lực hơn, nhưng càng nhiều công cụ càng khó hiểu và dùng tốt chúng; cần thử nghiệm để tìm bộ đúng (mục chọn công cụ bên dưới). Tuỳ môi trường có rất nhiều công cụ khả dĩ; tác giả nêu ba nhóm: tăng cường tri thức (tức dựng context), mở rộng năng lực, và công cụ cho agent tác động lên môi trường.

#### Tăng cường tri thức (Knowledge augmentation, trang PDF 541–542)

Một nhóm công cụ quan trọng giúp tăng tri thức của agent. Một số đã bàn: truy xuất văn bản, truy xuất ảnh, chạy SQL. Công cụ khác có thể là tìm người trong nội bộ, API tồn kho trả trạng thái các sản phẩm, truy xuất Slack, đọc email… Nhiều công cụ như vậy đưa quy trình và thông tin riêng của tổ chức vào mô hình. Nhưng công cụ cũng có thể cho mô hình truy cập thông tin công khai, nhất là từ internet.

**Duyệt web** là một trong những năng lực sớm nhất và được mong đợi nhất khi đưa vào chatbot như ChatGPT. Duyệt web giúp mô hình không bị **lỗi thời** (stale) — tình trạng dữ liệu huấn luyện đã cũ. Nếu dữ liệu huấn luyện bị cắt tuần trước, mô hình không trả lời được câu hỏi cần thông tin tuần này, trừ khi thông tin được đưa vào context. Không có duyệt web, mô hình không nói được về thời tiết, tin tức, sự kiện sắp tới, giá cổ phiếu, tình trạng chuyến bay… Tác giả dùng "duyệt web" làm từ bao trùm cho mọi công cụ truy cập internet, gồm trình duyệt và các API cụ thể như API tìm kiếm, API tin tức, API GitHub, hay API mạng xã hội (X, LinkedIn, Reddit). Duyệt web giúp agent dùng thông tin cập nhật để trả lời tốt hơn và bớt bịa, nhưng cũng có thể mở agent ra trước những "vũng lầy" của internet; phải chọn API internet cẩn thận.

#### Mở rộng năng lực (Capability extension, trang PDF 543–544)

Nhóm thứ hai là công cụ bù các giới hạn vốn có của mô hình AI — cách dễ để tăng hiệu năng. Mô hình AI nổi tiếng kém toán: hỏi 199.999 chia 292 bằng bao nhiêu, mô hình nhiều khả năng sai; nhưng phép tính này tầm thường nếu mô hình có máy tính (người tổng hợp tính: 199.999 / 292 ≈ 684,93). Thay vì huấn luyện mô hình giỏi số học, cho nó dùng công cụ tiết kiệm tài nguyên hơn nhiều. Các công cụ đơn giản khác: lịch, đổi múi giờ, đổi đơn vị (như từ pound sang kg), dịch sang và từ những ngôn ngữ mô hình không giỏi.

Công cụ phức tạp hơn nhưng mạnh là **trình thông dịch mã** (code interpreter). Thay vì huấn luyện mô hình hiểu mã, cho nó chạy một đoạn mã, nhận kết quả, hay phân tích lỗi của mã. Năng lực này cho agent làm trợ lý lập trình, nhà phân tích dữ liệu, thậm chí trợ lý nghiên cứu viết mã chạy thí nghiệm và báo kết quả. Nhưng chạy mã tự động đi kèm rủi ro tấn công tiêm mã (mục "Defensive Prompt Engineering" của Chương 5); biện pháp bảo mật đúng mức là thiết yếu.

Công cụ ngoài có thể biến mô hình chỉ-văn-bản hay chỉ-ảnh thành đa phương thức. Mô hình chỉ sinh văn bản có thể dùng mô hình text-to-image làm công cụ để sinh cả văn bản và ảnh; với một yêu cầu, bộ lập kế hoạch AI quyết định gọi sinh văn bản, sinh ảnh hay cả hai. Đó là cách ChatGPT sinh được cả văn bản và ảnh — nó dùng DALL-E làm bộ sinh ảnh. Agent cũng có thể dùng trình thông dịch mã để vẽ biểu đồ, trình biên dịch LaTeX để hiển thị công thức, hay trình duyệt để hiển thị trang web từ mã HTML. Tương tự, mô hình chỉ xử lý văn bản đầu vào có thể dùng công cụ chú thích ảnh để xử lý ảnh, công cụ phiên âm để xử lý âm thanh, và OCR (nhận dạng ký tự quang học) để đọc PDF.

Dùng công cụ có thể tăng hiệu năng mô hình đáng kể so với chỉ prompt hay cả finetuning. **Chameleon** (Lu và cộng sự, 2023) cho thấy một agent chạy bằng GPT-4, có thêm 13 công cụ, vượt GPT-4 đơn lẻ trên nhiều benchmark; các công cụ gồm truy xuất tri thức, bộ sinh truy vấn, bộ chú thích ảnh, bộ phát hiện chữ, tìm kiếm Bing. Trên ScienceQA (benchmark hỏi đáp khoa học), Chameleon cải thiện kết quả few-shot tốt nhất đã công bố thêm 11,37%. Trên TabMWP (Tabular Math Word Problems — bài toán đố có bảng, Lu và cộng sự, 2022), Chameleon tăng độ chính xác 17%.

#### Hành động ghi (Write actions, trang PDF 545–546)

Ngoài hành động chỉ đọc, công cụ còn có thể thực hiện hành động ghi — thay đổi nguồn dữ liệu. Bộ chạy SQL có thể đọc bảng (đọc) nhưng cũng có thể sửa hay xoá bảng (ghi). API email có thể đọc email và cũng trả lời. API ngân hàng có thể xem số dư và cũng khởi tạo chuyển tiền.

Hành động ghi cho hệ thống làm được nhiều hơn, ví dụ tự động hoá toàn bộ quy trình tiếp cận khách hàng: tìm hiểu khách tiềm năng, tìm thông tin liên hệ, soạn email, gửi email đầu, đọc phản hồi, theo dõi tiếp, trích đơn hàng, cập nhật đơn mới vào cơ sở dữ liệu…

Nhưng viễn cảnh để AI tự động thay đổi đời sống ta thật đáng sợ. Như không nên cho thực tập sinh quyền xoá cơ sở dữ liệu sản xuất, không nên cho một AI chưa đáng tin khởi tạo chuyển khoản. Niềm tin vào năng lực và biện pháp bảo mật của hệ thống là thiết yếu; phải bảo vệ hệ thống khỏi kẻ xấu tìm cách thao túng nó làm việc có hại.

Khi tác giả nói về agent AI tự chủ, thường có người nhắc tới xe tự lái: "Nếu ai đó hack xe để bắt cóc bạn thì sao?". Ví dụ này gây ấn tượng mạnh vì tính vật lý, nhưng một hệ AI có thể gây hại mà không cần hiện diện vật lý: thao túng thị trường chứng khoán, ăn cắp bản quyền, xâm phạm quyền riêng tư, củng cố định kiến, lan truyền thông tin sai và tuyên truyền (Chương 5). Đây là những mối lo chính đáng, và tổ chức nào muốn dùng AI cũng phải nghiêm túc với an toàn và bảo mật. Nhưng điều đó không có nghĩa hệ AI không bao giờ được hành động trong thế giới thật. Nếu ta tin máy móc đưa ta vào vũ trụ được, tác giả hy vọng một ngày biện pháp an ninh đủ để ta tin hệ AI tự chủ. Con người cũng có thể sai; cá nhân tác giả tin xe tự lái hơn một người lạ trung bình.

Như công cụ phù hợp giúp con người năng suất hơn rất nhiều — thử hình dung kinh doanh không có Excel, hay xây nhà chọc trời không có cần cẩu — công cụ cho mô hình làm được nhiều việc hơn. Nhiều nhà cung cấp mô hình đã hỗ trợ dùng công cụ, tính năng thường gọi là **function calling**; tác giả dự đoán function calling với nhiều công cụ sẽ phổ biến ở hầu hết mô hình.

### 10. Lập kế hoạch (Planning, trang PDF 546–571)

Ở trung tâm của agent mô hình nền tảng là mô hình chịu trách nhiệm giải nhiệm vụ. Một nhiệm vụ được xác định bởi **mục tiêu** và **ràng buộc**. Ví dụ: lên lịch chuyến đi hai tuần từ San Francisco tới Ấn Độ với ngân sách 5.000 USD — mục tiêu là chuyến đi hai tuần, ràng buộc là ngân sách.

Nhiệm vụ phức tạp cần lập kế hoạch. Đầu ra của quá trình lập kế hoạch là **kế hoạch** — lộ trình nêu các bước cần để hoàn thành nhiệm vụ. Lập kế hoạch hiệu quả thường đòi mô hình hiểu nhiệm vụ, cân nhắc các phương án và chọn phương án hứa hẹn nhất. Ai từng dự họp lập kế hoạch đều biết việc này khó; là một bài toán tính toán quan trọng, nó đã được nghiên cứu kỹ, cần nhiều tập sách mới nói hết; chương chỉ chạm bề mặt.

#### Tổng quan lập kế hoạch (Planning overview, trang PDF 547–551)

Một nhiệm vụ có nhiều cách phân rã, nhưng không phải cách nào cũng thành công, và trong các cách đúng, có cách hiệu quả hơn. Xét truy vấn "How many companies without revenue have raised at least $1 billion?" (có bao nhiêu công ty chưa có doanh thu đã gọi được ít nhất 1 tỷ USD?). Hai phương án minh hoạ:

1. Tìm mọi công ty chưa có doanh thu, rồi lọc theo số vốn đã gọi.
2. Tìm mọi công ty đã gọi ít nhất 1 tỷ USD, rồi lọc theo doanh thu.

Phương án 2 hiệu quả hơn: số công ty chưa có doanh thu nhiều hơn rất nhiều so với số công ty đã gọi được 1 tỷ USD. Chỉ với hai phương án này, agent thông minh nên chọn phương án 2. (Người tổng hợp nhận xét: đây là nguyên tắc "lọc theo điều kiện chọn lọc nhất trước" của tối ưu truy vấn cơ sở dữ liệu.)

**Tách lập kế hoạch khỏi thực thi.** Có thể ghép lập kế hoạch với thực thi trong cùng prompt: yêu cầu mô hình suy nghĩ từng bước (chain-of-thought) rồi thực hiện các bước đó, tất cả trong một prompt. Nhưng nếu mô hình nghĩ ra kế hoạch 1.000 bước mà còn không đạt mục tiêu thì sao? Không có giám sát, agent có thể chạy các bước đó hàng giờ, phí thời gian và tiền gọi API trước khi bạn nhận ra nó không đi tới đâu. Để tránh thực thi vô ích, nên tách lập kế hoạch khỏi thực thi: yêu cầu agent sinh kế hoạch trước, và chỉ thực thi sau khi kế hoạch được **kiểm định**.

- Kiểm định bằng **heuristic**: loại kế hoạch có hành động không hợp lệ (kế hoạch cần Google Search mà agent không có công cụ này thì không hợp lệ); loại mọi kế hoạch nhiều hơn X bước.
- Kiểm định bằng **AI judge**: hỏi một mô hình kế hoạch có hợp lý không, hay cải thiện thế nào.

Nếu kế hoạch bị đánh giá là tệ, yêu cầu bộ lập kế hoạch sinh kế hoạch khác. Nếu tốt, thực thi; nếu kế hoạch dùng công cụ ngoài, function calling được gọi. Đầu ra của việc thực thi lại phải được đánh giá. Kế hoạch không nhất thiết là kế hoạch đầu–cuối cho cả nhiệm vụ; có thể là kế hoạch nhỏ cho một nhiệm vụ con. Sơ đồ của sách (Hình 6-9): truy vấn → sinh kế hoạch → kiểm định kế hoạch (không đạt thì quay lại sinh kế hoạch) → thực thi (gọi hàm) → đánh giá đầu ra (chưa đạt thì quay lại sinh kế hoạch) → phản hồi.

Hệ thống giờ có ba thành phần: sinh kế hoạch, kiểm định kế hoạch, thực thi kế hoạch. Nếu coi mỗi thành phần là một agent, đây là **hệ đa agent** (multi-agent system). (Chú thích của sách: vì phần lớn quy trình agent đủ phức tạp để gồm nhiều thành phần, phần lớn agent là đa agent.)

Để nhanh hơn, thay vì sinh kế hoạch tuần tự, có thể sinh nhiều kế hoạch song song và nhờ bộ đánh giá chọn cái hứa hẹn nhất — một đánh đổi độ trễ/chi phí khác, vì sinh nhiều kế hoạch cùng lúc tốn thêm tiền.

**Ý định.** Lập kế hoạch cần hiểu ý định đằng sau nhiệm vụ: người dùng muốn làm gì với truy vấn này? Bộ **phân loại ý định** (intent classifier) thường được dùng để giúp agent lập kế hoạch; như ở mục "Break Complex Tasks into Simpler Subtasks" của Chương 5, phân loại ý định có thể làm bằng một prompt khác hoặc một mô hình phân loại huấn luyện riêng, và có thể coi là một agent nữa trong hệ đa agent. Biết ý định giúp chọn đúng công cụ: trong hỗ trợ khách hàng, truy vấn về hoá đơn có thể cần công cụ lấy các khoản thanh toán gần đây của người dùng; truy vấn về đặt lại mật khẩu thì cần công cụ truy xuất tài liệu hướng dẫn. **Mẹo của sách:** một số truy vấn nằm ngoài phạm vi agent; bộ phân loại ý định nên phân loại được chúng là IRRELEVANT (không liên quan) để agent lịch sự từ chối thay vì phí FLOP nghĩ ra lời giải bất khả.

**Con người trong vòng lặp.** Tới đây ta giả định agent tự động hoá cả ba khâu. Thực tế con người có thể tham gia ở bất kỳ khâu nào để hỗ trợ và giảm rủi ro: chuyên gia có thể đưa kế hoạch, kiểm định kế hoạch, hay thực thi một phần. Với nhiệm vụ phức tạp mà agent khó sinh cả kế hoạch, chuyên gia có thể đưa kế hoạch cấp cao để agent mở rộng. Nếu kế hoạch có thao tác rủi ro, như cập nhật cơ sở dữ liệu hay gộp thay đổi mã, hệ thống có thể xin phê duyệt rõ ràng của con người trước khi thực thi, hoặc để con người thực thi. Muốn vậy phải định rõ mức tự động hoá agent được có với từng hành động.

**Tóm lại**, giải một nhiệm vụ thường gồm các quá trình sau (phản tư không bắt buộc nhưng tăng hiệu năng đáng kể):

1. **Sinh kế hoạch:** nghĩ ra kế hoạch hoàn thành nhiệm vụ. Kế hoạch là chuỗi hành động dễ quản lý, nên quá trình này còn gọi là **phân rã nhiệm vụ** (task decomposition).
2. **Phản tư và sửa lỗi:** đánh giá kế hoạch; tệ thì sinh kế hoạch mới.
3. **Thực thi:** thực hiện các hành động trong kế hoạch, thường bằng cách gọi các hàm cụ thể.
4. **Phản tư và sửa lỗi:** nhận kết quả hành động, đánh giá và xác định mục tiêu đã đạt chưa; tìm và sửa lỗi; chưa xong thì sinh kế hoạch mới.

Sách đã có các kỹ thuật này: yêu cầu mô hình "think step by step" là yêu cầu nó phân rã nhiệm vụ; yêu cầu "verify if your answer is correct" là yêu cầu nó phản tư.

#### Mô hình nền tảng làm bộ lập kế hoạch (Foundation models as planners, trang PDF 552–554)

Một câu hỏi mở là mô hình nền tảng lập kế hoạch giỏi tới đâu. Nhiều nhà nghiên cứu tin rằng mô hình nền tảng, ít nhất là loại dựng trên mô hình ngôn ngữ tự hồi quy, không lập kế hoạch được. Yann LeCun, nhà khoa học AI trưởng của Meta, khẳng định dứt khoát LLM tự hồi quy không lập kế hoạch được (2023). Trong bài "Can LLMs Really Reason and Plan?", Kambhampati (2023) lập luận LLM giỏi trích xuất tri thức nhưng không giỏi lập kế hoạch; các bài báo tuyên bố LLM lập kế hoạch được đã nhầm tri thức chung về lập kế hoạch trích từ LLM với kế hoạch thực thi được: "Các kế hoạch ra từ LLM có thể trông hợp lý với người không chuyên, nhưng lại dẫn tới tương tác và lỗi khi thực thi." Tuy có nhiều bằng chứng giai thoại rằng LLM lập kế hoạch kém, vẫn chưa rõ đó là vì ta chưa biết dùng LLM đúng cách hay vì LLM về bản chất không lập kế hoạch được.

**Lập kế hoạch là bài toán tìm kiếm.** Về cốt lõi, lập kế hoạch là tìm trong các đường tới đích, dự đoán kết quả (phần thưởng) của mỗi đường, và chọn đường có kết quả hứa hẹn nhất; thường có thể kết luận không đường nào tới đích. Tìm kiếm thường cần **quay lui** (backtracking): ở một bước có hai hành động A và B; sau khi làm A, bạn vào trạng thái không hứa hẹn, nên phải quay lại trạng thái trước để làm B.

Có người lập luận mô hình tự hồi quy chỉ sinh hành động tiến tới, không quay lui để sinh hành động khác, nên không lập kế hoạch được. Tác giả cho rằng không nhất thiết vậy: sau khi thực thi một đường với hành động A, nếu mô hình thấy đường này vô lý, nó có thể sửa đường bằng hành động B — thực chất là quay lui; mô hình cũng luôn có thể làm lại từ đầu và chọn đường khác.

Cũng có thể LLM lập kế hoạch kém vì không được cho công cụ cần thiết. Muốn lập kế hoạch, không chỉ phải biết các hành động có thể mà còn phải biết **kết quả** tiềm năng của mỗi hành động. Ví dụ đơn giản: bạn muốn leo núi; hành động có thể là rẽ phải, rẽ trái, quay lại, đi thẳng; nhưng nếu rẽ phải làm bạn rơi xuống vực, bạn không muốn xét hành động đó. Nói kỹ thuật: một hành động đưa bạn từ trạng thái này sang trạng thái khác, và phải biết trạng thái kết quả mới quyết định có làm hay không. Vì vậy chỉ prompt mô hình sinh một chuỗi hành động như kỹ thuật chain-of-thought phổ biến là chưa đủ. Bài "Reasoning with Language Model is Planning with World Model" (Hao và cộng sự, 2023) lập luận rằng LLM, vì chứa quá nhiều thông tin về thế giới, có khả năng dự đoán kết quả của mỗi hành động và đưa dự đoán đó vào để sinh kế hoạch mạch lạc.

Ngay cả nếu AI không lập kế hoạch được, nó vẫn có thể là một phần của bộ lập kế hoạch: có thể bổ sung cho LLM một công cụ tìm kiếm và một hệ theo dõi trạng thái để giúp nó lập kế hoạch.

**Khung "Foundation Model (FM) Versus Reinforcement Learning (RL) Planners".** Agent là khái niệm cốt lõi của học tăng cường (RL), được Wikipedia định nghĩa là lĩnh vực "quan tâm tới việc một agent thông minh nên hành động thế nào trong môi trường động để tối đa hoá phần thưởng tích luỹ". Agent RL và agent FM giống nhau ở nhiều mặt: đều được đặc trưng bởi môi trường và các hành động khả dĩ. Khác biệt chính là cách bộ lập kế hoạch hoạt động: trong agent RL, bộ lập kế hoạch được huấn luyện bằng thuật toán RL, việc này có thể tốn nhiều thời gian và tài nguyên; trong agent FM, chính mô hình là bộ lập kế hoạch, có thể được prompt hay finetune để lập kế hoạch tốt hơn, thường tốn ít thời gian và tài nguyên hơn. Không gì ngăn agent FM dùng thuật toán RL để cải thiện; tác giả đoán về lâu dài agent FM và agent RL sẽ hợp nhất.

#### Sinh kế hoạch (Plan generation, trang PDF 555–559)

Cách đơn giản nhất biến mô hình thành bộ sinh kế hoạch là prompt engineering. Giả sử bạn tạo agent giúp khách tìm hiểu sản phẩm ở Kitty Vogue, với ba công cụ ngoài: lấy sản phẩm theo giá, lấy sản phẩm bán chạy nhất, lấy thông tin sản phẩm. Prompt minh hoạ (prompt sản xuất có lẽ phức tạp hơn):

```text
SYSTEM PROMPT
Propose a plan to solve the task. You have
access to 5 actions:
get_today_date()
fetch_top_products(start_date, end_date,
num_products)
fetch_product_info(product_name)
generate_query(task_history, tool_output)
generate_response(query)
The plan must be a sequence of valid actions.
Examples
Task: "Tell me about Fruity Fedora"
Plan: [fetch_product_info, generate_query,
generate_response]
Task: "What was the best selling product last
week?"
Plan: [fetch_top_products, generate_query,
generate_response]
Task: {USER INPUT}
Plan:
```

(Dịch ý: đề xuất kế hoạch giải nhiệm vụ; có 5 hành động: lấy ngày hôm nay, lấy các sản phẩm bán chạy nhất trong khoảng ngày với số lượng cho trước, lấy thông tin một sản phẩm, sinh truy vấn từ lịch sử nhiệm vụ và đầu ra công cụ, sinh phản hồi; kế hoạch phải là chuỗi hành động hợp lệ; hai ví dụ: "Kể về Fruity Fedora" và "Sản phẩm bán chạy nhất tuần trước là gì?".)

Hai điểm cần lưu ý: (1) định dạng kế hoạch ở đây — danh sách hàm, tham số do agent tự suy ra — chỉ là một trong nhiều cách cấu trúc luồng điều khiển của agent; (2) hàm `generate_query` nhận lịch sử hiện tại của nhiệm vụ và đầu ra công cụ gần nhất để sinh truy vấn đưa vào bộ sinh phản hồi; đầu ra công cụ ở mỗi bước được thêm vào lịch sử nhiệm vụ.

Với đầu vào "What's the price of the best-selling product last week" (giá của sản phẩm bán chạy nhất tuần trước là bao nhiêu), kế hoạch sinh ra có thể là:

1. get_time()
2. fetch_top_products()
3. fetch_product_info()
4. generate_query()
5. generate_response()

**Tham số.** Tham số chính xác khó đoán trước vì thường được trích từ đầu ra công cụ trước đó. Nếu bước đầu `get_time()` cho "2030-09-13", agent có thể suy ra tham số cho bước tiếp theo:

```text
retrieve_top_products(
      start_date="2030-09-07",
      end_date="2030-09-13",
      num_products=1
)
```

(Khoảng từ 7 tới 13/9 là 7 ngày, tính cả hai đầu.) Thường không đủ thông tin để xác định chính xác tham số. Ví dụ người dùng hỏi "What's the average price of best-selling products?" (giá trung bình của các sản phẩm bán chạy nhất?) thì không rõ: người dùng muốn xem bao nhiêu sản phẩm bán chạy? Bán chạy tuần trước, tháng trước hay mọi thời gian? Mô hình thường phải đoán, và đoán có thể sai.

Vì cả chuỗi hành động lẫn tham số đều do mô hình sinh, chúng có thể bị bịa: gọi hàm không hợp lệ, hoặc gọi hàm hợp lệ với tham số sai. Các kỹ thuật cải thiện mô hình nói chung dùng được để cải thiện khả năng lập kế hoạch:

- Viết system prompt tốt hơn, nhiều ví dụ hơn.
- Mô tả công cụ và tham số tốt hơn để mô hình hiểu rõ.
- Viết lại chính các hàm cho đơn giản hơn, như tách một hàm phức tạp thành hai hàm đơn giản.
- Dùng mô hình mạnh hơn; nói chung mô hình mạnh hơn lập kế hoạch tốt hơn.
- Finetune một mô hình để sinh kế hoạch.

#### Function calling (trang PDF 559–562)

Nhiều nhà cung cấp mô hình cho phép dùng công cụ, thực chất biến mô hình thành agent. Một công cụ là một hàm, nên gọi công cụ thường được gọi là **function calling** (gọi hàm). API mỗi hãng khác nhau, nhưng nhìn chung:

1. **Tạo bộ công cụ.** Khai báo mọi công cụ bạn muốn mô hình có thể dùng. Mỗi công cụ được mô tả bằng điểm vào để thực thi (như tên hàm), tham số, và tài liệu (hàm làm gì, cần tham số gì).
2. **Chỉ định công cụ agent được dùng.** Vì truy vấn khác nhau cần công cụ khác nhau, nhiều API cho chỉ định danh sách công cụ đã khai báo dùng cho mỗi truy vấn. Một số cho kiểm soát thêm: `required` (mô hình phải dùng ít nhất một công cụ), `none` (không được dùng công cụ nào), `auto` (mô hình tự quyết định dùng công cụ nào).

Hình 6-10 của sách là mã giả đại diện cho nhiều API:

```python
def lbs_to_kg(lbs):
    return lbs * 0.45359237

def ft_to_meters(ft):
    return ft * 0.3048

lbs_to_kg_tool = FunctionDeclaration(
    name="lbs_to_kg",
    description="Convert from pounds to kilograms",
    parameters={
        "type": "object",
        "properties": {
            "lbs": {"type": "int", "description": "The value to be converted"}
        },
        "required": ["lbs"]
    },
)

ft_to_m_tool = FunctionDeclaration(name="ft_to_meters", ...)

messages = [{"role": "user", "content": [USER_QUERY]}]

response = model_client.chat.completions.create(
    model=[MODEL_NAME],
    messages=messages,
    tools=[lbs_to_kg_tool, ft_to_m_tool],
    tool_choice="auto",
)
```

Các chú thích bên lề của hình: phần đầu là "định nghĩa công cụ" (hai hàm đổi pound sang kg và foot sang mét); phần thứ hai là "(1) mô tả công cụ"; dòng `messages` là "truy vấn người dùng"; phần cuối là "(2) truy vấn này có thể dùng hai công cụ".

Với một truy vấn, agent định nghĩa như trên sẽ tự sinh ra cần dùng công cụ nào và tham số gì. Một số API function calling đảm bảo chỉ sinh hàm hợp lệ, nhưng không đảm bảo được giá trị tham số đúng. Ví dụ với "How many kilograms are 40 pounds?", agent có thể quyết định cần công cụ `lbs_to_kg_tool` với tham số 40; phản hồi của agent có thể như sau:

```python
response = ModelResponse(
   finish_reason='tool_calls',
   message=chat.Message(
       content=None,
       role='assistant',
       tool_calls=[
           ToolCall(
               function=Function(
                   arguments='{"lbs":40}',
                   name='lbs_to_kg'),
               type='function')
       ])
)
```

Từ phản hồi này, bạn gọi hàm `lbs_to_kg(lbs=40)` và dùng đầu ra để trả lời người dùng. (Người tổng hợp tính: 40 × 0,45359237 ≈ 18,14 kg.) Lưu ý `finish_reason='tool_calls'` và `content=None`: mô hình chưa trả lời mà yêu cầu ứng dụng chạy công cụ trước.

**Mẹo của sách:** khi làm việc với agent, luôn yêu cầu hệ thống báo giá trị tham số dùng cho mỗi lời gọi hàm, và kiểm tra các giá trị đó.

#### Độ chi tiết của kế hoạch (Planning granularity, trang PDF 562–564)

Kế hoạch là lộ trình các bước, và lộ trình có thể ở nhiều mức chi tiết. Để lập kế hoạch một năm, kế hoạch theo quý cấp cao hơn kế hoạch theo tháng, kế hoạch theo tháng lại cao hơn kế hoạch theo tuần.

Có đánh đổi giữa lập kế hoạch và thực thi: kế hoạch chi tiết khó sinh nhưng dễ thực thi; kế hoạch cấp cao dễ sinh nhưng khó thực thi. Một cách lách là **lập kế hoạch phân cấp**: dùng một bộ lập kế hoạch sinh kế hoạch cấp cao (theo quý), rồi với mỗi quý dùng cùng bộ đó hoặc bộ khác sinh kế hoạch theo tháng.

Các ví dụ trên đều dùng tên hàm chính xác, rất chi tiết. Vấn đề: bộ công cụ có thể thay đổi theo thời gian — hàm lấy ngày hiện tại `get_time()` có thể đổi tên thành `get_current_time()`; khi công cụ đổi, phải cập nhật prompt và mọi ví dụ. Dùng tên hàm chính xác cũng khó tái dùng bộ lập kế hoạch cho các trường hợp có API công cụ khác. Nếu đã finetune mô hình sinh kế hoạch theo bộ công cụ cũ, phải finetune lại theo bộ mới.

Để tránh vấn đề này, kế hoạch có thể viết bằng ngôn ngữ tự nhiên hơn, cấp cao hơn tên hàm chuyên biệt. Với cùng truy vấn "giá của sản phẩm bán chạy nhất tuần trước", agent có thể được yêu cầu xuất kế hoạch:

1. get current date (lấy ngày hiện tại)
2. retrieve the best-selling product last week (lấy sản phẩm bán chạy nhất tuần trước)
3. retrieve product information (lấy thông tin sản phẩm)
4. generate query (sinh truy vấn)
5. generate response (sinh phản hồi)

Ngôn ngữ tự nhiên giúp bộ sinh kế hoạch bền trước thay đổi API công cụ. Nếu mô hình được huấn luyện chủ yếu trên ngôn ngữ tự nhiên, nó có lẽ hiểu và sinh kế hoạch bằng ngôn ngữ tự nhiên tốt hơn và ít bịa hơn. Nhược điểm là cần một **bộ dịch** chuyển mỗi hành động ngôn ngữ tự nhiên thành lệnh thực thi được (chú thích của sách: Chameleon gọi bộ dịch này là "program generator"). Tuy vậy, dịch đơn giản hơn nhiều so với lập kế hoạch và có thể giao cho mô hình yếu hơn, ít rủi ro bịa hơn.

#### Kế hoạch phức tạp (Complex plans, trang PDF 564–566)

Các kế hoạch tới đây đều tuần tự: hành động sau luôn chạy khi hành động trước xong. Thứ tự thực thi các hành động gọi là **luồng điều khiển** (control flow). Tuần tự chỉ là một loại; các loại khác gồm song song, rẽ nhánh (if) và vòng lặp (for):

- **Tuần tự:** làm B sau khi A xong, thường vì B phụ thuộc A. Ví dụ: câu SQL chỉ chạy được sau khi đã dịch từ câu hỏi tự nhiên.
- **Song song:** làm A và B cùng lúc. Ví dụ với "Find me best-selling products under $100" (tìm các sản phẩm bán chạy dưới 100 USD), agent có thể trước hết lấy 100 sản phẩm bán chạy nhất rồi, với mỗi sản phẩm, lấy giá của nó (các lần lấy giá chạy song song).
- **Rẽ nhánh (if):** làm B hoặc C tuỳ đầu ra bước trước. Ví dụ: agent kiểm tra báo cáo lợi nhuận của NVIDIA, rồi dựa vào đó quyết định bán hay mua cổ phiếu NVIDIA.
- **Vòng lặp (for):** lặp lại A cho tới khi đạt một điều kiện. Ví dụ: sinh số ngẫu nhiên cho tới khi ra một số nguyên tố.

Hình 6-11 của sách vẽ bốn luồng, mỗi luồng là chuỗi "Task A → Control flow decision → …", kèm ví dụ: tuần tự — "nói chuyện với dữ liệu": A dịch văn bản thành SQL, B chạy SQL; song song — phân tích dữ liệu: A tìm các sản phẩm bán chạy tuần trước, B/C/… lấy giá từng sản phẩm; rẽ nhánh — A phân tích báo cáo lợi nhuận của một công ty, tích cực thì mua cổ phiếu, tiêu cực thì bán (nhãn hình ghi "customer support"); vòng lặp — truy vết nguồn gốc (lineage): lần theo các lượt đăng lại của một bài lan truyền về tới người đăng gốc.

Trong kỹ thuật phần mềm truyền thống, điều kiện của luồng điều khiển là chính xác. Với agent AI, mô hình AI quyết định luồng điều khiển. Kế hoạch có luồng không tuần tự khó sinh hơn và khó dịch thành lệnh thực thi hơn. Khi đánh giá một khung agent, hãy kiểm tra nó hỗ trợ luồng điều khiển nào: nếu hệ thống cần duyệt mười trang web, nó có làm đồng thời được không? Thực thi song song có thể giảm đáng kể độ trễ người dùng cảm nhận.

#### Phản tư và sửa lỗi (Reflection and error correction, trang PDF 567–571)

Ngay cả kế hoạch tốt nhất cũng cần liên tục được đánh giá và điều chỉnh để tối đa khả năng thành công. Phản tư không thực sự cần để agent vận hành, nhưng cần để agent thành công. Phản tư hữu ích ở nhiều chỗ:

- Sau khi nhận truy vấn: đánh giá yêu cầu có khả thi không.
- Sau khi sinh kế hoạch ban đầu: kế hoạch có hợp lý không.
- Sau mỗi bước thực thi: có đi đúng hướng không.
- Sau khi thực thi cả kế hoạch: nhiệm vụ đã hoàn thành chưa.

Phản tư và sửa lỗi là hai cơ chế khác nhau nhưng đi cùng nhau: phản tư sinh ra nhận định giúp phát hiện lỗi cần sửa. Phản tư có thể do chính agent làm bằng prompt tự phê bình, hoặc do thành phần riêng, như một bộ chấm điểm chuyên biệt — mô hình xuất điểm cụ thể cho mỗi kết quả.

**ReAct.** Được đề xuất lần đầu trong ReAct (Yao và cộng sự, 2022), việc xen kẽ suy luận và hành động đã thành mẫu phổ biến cho agent. Yao và cộng sự dùng "suy luận" bao gồm cả lập kế hoạch và phản tư. Ở mỗi bước, agent được yêu cầu giải thích suy nghĩ (lập kế hoạch), hành động, rồi phân tích quan sát (phản tư), cho tới khi agent cho rằng nhiệm vụ xong. Agent thường được prompt bằng ví dụ để xuất theo định dạng:

```text
Thought 1: …
Act 1: …
Observation 1: …
… [continue until reflection determines that the task is finished] …
Thought N: …
Act N: Finish [Response to query]
```

Hình 6-12 của sách là ví dụ ReAct trả lời một câu hỏi của HotpotQA (Yang và cộng sự, 2018 — benchmark hỏi đáp nhiều bước suy luận). Câu hỏi: "Ngoài Apple Remote, thiết bị nào khác điều khiển được chương trình mà Apple Remote ban đầu được thiết kế để tương tác?"

- Thought 1: cần tìm Apple Remote và chương trình nó được thiết kế để tương tác. Act 1: Search[Apple Remote]. Obs 1: Apple Remote là điều khiển từ xa Apple ra mắt tháng 10/2005… ban đầu thiết kế để điều khiển chương trình Front Row media center…
- Thought 2: cần tìm Front Row và thiết bị nào khác điều khiển nó. Act 2: Search[Front Row]. Obs 2: không tìm thấy [Front Row]; tương tự: 'Front Row Seat to Earth', 'Front Row Motorsports', 'Front Row (software)'…
- Thought 3: Front Row không tìm thấy; cần tìm Front Row (software). Act 3: Search[Front Row (software)]. Obs 3: Front Row là phần mềm trung tâm đa phương tiện đã ngừng phát triển…
- Thought 4: Front Row (software) được điều khiển bằng Apple Remote hoặc các phím chức năng của bàn phím; vậy câu trả lời là phím chức năng bàn phím. Act 4: Finish[keyboard function keys].

Có thể làm phản tư trong bối cảnh đa agent: một agent lập kế hoạch và hành động, agent khác đánh giá kết quả sau mỗi bước hay sau một số bước. (Chú thích của sách: điều này gợi tới phương pháp actor-critic trong học tăng cường, Konda và Tsitsiklis, 1999.)

**Reflexion.** Nếu phản hồi của agent không hoàn thành nhiệm vụ, có thể prompt agent phản tư xem vì sao thất bại và cải thiện thế nào; dựa trên gợi ý đó, agent sinh kế hoạch mới — tức agent học từ sai lầm. Ví dụ với nhiệm vụ sinh mã, bộ đánh giá có thể thấy mã sai 1/3 số ca kiểm thử; agent phản tư rằng lý do là chưa tính các mảng mà mọi số đều âm; actor (thành phần hành động) sinh mã mới có tính tới mảng toàn số âm. Đây là cách Reflexion (Shinn và cộng sự, 2023) làm: phản tư được tách thành hai mô-đun — **bộ đánh giá** (evaluator) đánh giá kết quả, và **mô-đun tự phản tư** (self-reflection) phân tích chỗ sai. Các tác giả dùng từ "quỹ đạo" (trajectory) cho kế hoạch; ở mỗi bước, sau đánh giá và tự phản tư, agent đề xuất quỹ đạo mới.

Hình 6-13 của sách cho hai ví dụ Reflexion, mỗi ví dụ qua năm tầng (a) nhiệm vụ → (b) quỹ đạo → (c) đánh giá → (d) phản tư → (e) quỹ đạo kế tiếp:

| Tầng | 1. Ra quyết định (môi trường nhà ảo) | 2. Lập trình |
|---|---|---|
| (a) Nhiệm vụ | Bạn ở giữa một căn phòng… Nhiệm vụ: làm sạch một chiếc chảo và đặt lên mặt bếp | Cho danh sách hai chuỗi chỉ gồm dấu ngoặc mở '(' hoặc đóng ')'… |
| (b) Quỹ đạo | Action: lấy chảo 1 từ bếp đun 1 — Obs: không có gì xảy ra; Action: rửa chảo 1 ở bồn rửa 1 — Obs: không có gì xảy ra | Hàm `match_parens` kiểm tra nếu tổng số '(' bằng tổng số ')' trong hai chuỗi … thì `return 'No'` |
| (c) Đánh giá | Heuristic theo quy tắc/mô hình ngôn ngữ: Hallucination (bịa) | Kiểm thử đơn vị tự sinh thất bại: `assert match_parens(...)` |
| (d) Phản tư | …đã cố lấy chảo ở bếp đun 1… nhưng chảo không nằm ở bếp đun 1… | …sai vì chỉ kiểm tra tổng số ngoặc mở và đóng có bằng nhau không… [mà bỏ qua] thứ tự của các dấu ngoặc… |
| (e) Quỹ đạo kế tiếp | Action: lấy chảo 1 từ bếp đun 2 … Obs: bạn đặt chảo 1 lên mặt bếp 1 | `return 'Yes' if check(S1) or check(S2) else 'No'` |

**Ưu nhược.** So với sinh kế hoạch, phản tư tương đối dễ cài đặt và có thể cải thiện hiệu năng tốt đến bất ngờ. Nhược điểm là độ trễ và chi phí: suy nghĩ, quan sát, đôi khi cả hành động có thể tốn nhiều token để sinh, làm tăng chi phí và độ trễ người dùng cảm nhận, nhất là với nhiệm vụ nhiều bước trung gian. Để agent theo đúng định dạng, cả tác giả ReAct lẫn Reflexion đều dùng nhiều ví dụ trong prompt, làm tăng chi phí token đầu vào và giảm chỗ trong context cho thông tin khác.

#### Chọn công cụ (Tool selection, trang PDF 572–576)

Vì công cụ thường đóng vai trò then chốt cho thành công, chọn công cụ cần cân nhắc kỹ. Công cụ nên cho agent phụ thuộc vào môi trường và nhiệm vụ, và cả vào mô hình AI chạy agent. Không có hướng dẫn chắc chắn nào để chọn bộ công cụ tốt nhất. Tài liệu về agent có đủ cỡ bộ công cụ: Toolformer (Schick và cộng sự, 2023) finetune GPT-J để học 5 công cụ; Chameleon (Lu và cộng sự, 2023) dùng 13 công cụ; Gorilla (Patil và cộng sự, 2023) thử prompt agent chọn đúng lời gọi API trong 1.645 API.

Nhiều công cụ cho agent nhiều năng lực hơn, nhưng càng nhiều công cụ càng khó dùng hiệu quả — như con người khó làm chủ một bộ đồ nghề lớn. Thêm công cụ cũng nghĩa là thêm mô tả công cụ, có thể không vừa context. Như nhiều quyết định khác, chọn công cụ cần thử nghiệm và phân tích:

- So sánh hiệu năng agent với các bộ công cụ khác nhau.
- Làm **nghiên cứu cắt bỏ** (ablation study) xem hiệu năng giảm bao nhiêu khi bỏ một công cụ; bỏ được mà không giảm hiệu năng thì bỏ.
- Tìm công cụ agent hay dùng sai; nếu một công cụ quá khó cho agent — prompt nhiều và cả finetune vẫn không dạy được — hãy đổi công cụ.
- Vẽ phân bố lời gọi công cụ để xem công cụ nào dùng nhiều nhất, ít nhất.

Hình 6-14 của sách (từ Lu và cộng sự 2023) cho tỷ lệ phần trăm chương trình do Chameleon sinh có gọi mỗi công cụ, với ChatGPT và GPT-4 làm bộ lập kế hoạch:

| Benchmark | Công cụ | Chameleon (ChatGPT) gọi | Chameleon (GPT-4) gọi |
|---|---|---:|---:|
| ScienceQA | Truy xuất tri thức | 72% | 81% |
| ScienceQA | Phát hiện chữ (text detector) | 17% | 30% |
| ScienceQA | Chú thích ảnh | 10% | 6% |
| ScienceQA | Sinh truy vấn | 2% | 11% |
| ScienceQA | Tìm kiếm Bing | 3% | 11% |
| TabMWP | Tra hàng (row lookup) | 47% | 26% |
| TabMWP | Tra cột (column lookup) | 4% | 6% |
| TabMWP | Diễn đạt bảng thành lời (table verbalizer) | 3% | 7% |
| TabMWP | Truy xuất tri thức | 16% | 25% |
| TabMWP | Sinh chương trình (program generator) | 71% | 72% |

Thí nghiệm của Lu và cộng sự cho thấy hai điều:

1. **Nhiệm vụ khác cần công cụ khác.** ScienceQA dựa vào công cụ truy xuất tri thức nhiều hơn hẳn TabMWP (72–81% so với 16–25% theo bảng trên).
2. **Mô hình khác có sở thích công cụ khác.** GPT-4 có vẻ chọn tập công cụ rộng hơn ChatGPT (trên ScienceQA, GPT-4 gọi phát hiện chữ, sinh truy vấn và Bing nhiều hơn rõ rệt). ChatGPT có vẻ ưa chú thích ảnh, còn GPT-4 ưa truy xuất tri thức.

**Mẹo của sách:** khi đánh giá một khung agent, xem nó hỗ trợ bộ lập kế hoạch và công cụ nào. Các khung khác nhau tập trung vào nhóm công cụ khác nhau: AutoGPT tập trung vào API mạng xã hội (Reddit, X, Wikipedia), còn Composio tập trung vào API doanh nghiệp (Google Apps, GitHub, Slack). Vì nhu cầu sẽ thay đổi, hãy đánh giá mức dễ mở rộng agent để thêm công cụ mới.

**Tạo công cụ mới.** Con người năng suất hơn không chỉ nhờ dùng công cụ được cho mà còn nhờ tạo công cụ mạnh dần từ công cụ đơn giản. AI có tạo được công cụ mới từ công cụ ban đầu không? Chameleon đề xuất nghiên cứu **chuyển tiếp công cụ** (tool transition): sau công cụ X, agent gọi công cụ Y với xác suất bao nhiêu? Hình 6-15 của sách là cây chuyển tiếp công cụ của Lu và cộng sự (2023):

| Từ | Sang | Xác suất |
|---|---|---:|
| START | knowledge_retrieval (truy xuất tri thức) | 0,53 |
| START | text_detector (phát hiện chữ) | 0,30 |
| START | query_generator (sinh truy vấn) | 0,11 |
| START | image_captioner (chú thích ảnh) | 0,06 |
| query_generator | bing_search | 1,0 |
| bing_search | solution_generator (sinh lời giải) | 0,97 |
| bing_search | knowledge_retrieval | 0,02 |
| bing_search | image_captioner | 0,01 |
| image_captioner | knowledge_retrieval | 0,79 |
| image_captioner | solution_generator | 0,21 |
| image_captioner | query_generator | 0,01 |
| text_detector | knowledge_retrieval | 0,78 |
| text_detector | solution_generator | 0,22 |
| knowledge_retrieval | solution_generator | 1,0 |
| solution_generator | answer_generator (sinh câu trả lời) | 1,0 |
| answer_generator | END | 1,0 |

Nếu hai công cụ thường đi cùng nhau, có thể gộp chúng thành một công cụ lớn hơn (ví dụ query_generator luôn dẫn tới bing_search với xác suất 1,0). Nếu agent biết thông tin này, chính nó có thể kết hợp công cụ ban đầu để liên tục dựng công cụ phức tạp hơn.

**Voyager** (Wang và cộng sự, 2023; sách in nhầm "Vogager") đề xuất một **bộ quản lý kỹ năng** theo dõi các kỹ năng (công cụ) mới agent học được để dùng lại. Mỗi kỹ năng là một chương trình. Khi bộ quản lý xác định một kỹ năng mới hữu ích (ví dụ vì đã giúp agent hoàn thành nhiệm vụ), nó thêm kỹ năng vào thư viện kỹ năng (về khái niệm giống bộ công cụ); kỹ năng có thể được truy xuất để dùng cho nhiệm vụ khác.

Thành công của agent phụ thuộc vào bộ công cụ và năng lực lập kế hoạch; hỏng ở mặt nào cũng có thể làm agent thất bại.

### 11. Các kiểu hỏng của agent và đánh giá (Agent Failure Modes and Evaluation, trang PDF 576–581)

Đánh giá là phát hiện lỗi. Agent làm nhiệm vụ càng phức tạp, càng nhiều điểm có thể hỏng. Ngoài các kiểu hỏng chung của mọi ứng dụng AI (Chương 3 và 4), agent có kiểu hỏng riêng do lập kế hoạch, thực thi công cụ và hiệu quả; có kiểu dễ bắt hơn kiểu khác. Để đánh giá agent, hãy xác định các kiểu hỏng và đo tần suất mỗi kiểu. Tác giả dựng một benchmark đơn giản minh hoạ các kiểu hỏng trên kho GitHub của sách; ngoài ra có các benchmark và bảng xếp hạng agent như Berkeley Function Calling Leaderboard, bộ khung đánh giá AgentOps, và benchmark TravelPlanner.

#### Lỗi lập kế hoạch (Planning failures, trang PDF 577–579)

Kiểu lỗi lập kế hoạch phổ biến nhất là **lỗi dùng công cụ**. Agent có thể sinh kế hoạch có một hay nhiều lỗi sau:

- **Công cụ không hợp lệ:** kế hoạch có `bing_search` nhưng `bing_search` không có trong bộ công cụ.
- **Công cụ hợp lệ, tham số không hợp lệ:** gọi `lbs_to_kg` với hai tham số, trong khi hàm chỉ cần một tham số `lbs`.
- **Công cụ hợp lệ, giá trị tham số sai:** gọi `lbs_to_kg` với một tham số `lbs` nhưng dùng giá trị 100 thay vì 120.

Kiểu khác là **lỗi mục tiêu**: agent không đạt mục tiêu, vì kế hoạch không giải nhiệm vụ, hoặc giải mà không tuân ràng buộc. Ví dụ yêu cầu lập kế hoạch chuyến đi hai tuần từ San Francisco tới Hà Nội với ngân sách 5.000 USD: agent có thể lập chuyến đi từ San Francisco tới TP. Hồ Chí Minh, hoặc lập chuyến đi hai tuần tới Hà Nội nhưng vượt xa ngân sách.

Một ràng buộc hay bị bỏ qua khi đánh giá agent là **thời gian**. Nhiều khi thời gian agent mất không quan trọng lắm, vì bạn giao việc rồi chỉ cần quay lại khi xong. Nhưng nhiều khi agent kém hữu ích dần theo thời gian: nhờ agent soạn hồ sơ xin tài trợ mà nó xong sau hạn nộp thì chẳng giúp được gì.

Một kiểu thú vị là lỗi do **phản tư sai**: agent tin đã hoàn thành nhiệm vụ trong khi chưa. Ví dụ nhờ xếp 50 người vào 30 phòng khách sạn, agent có thể chỉ xếp 40 người và khăng khăng rằng đã xong.

**Cách đánh giá lỗi lập kế hoạch:** tạo một tập dữ liệu lập kế hoạch, mỗi mẫu là một bộ (nhiệm vụ, bộ công cụ). Với mỗi nhiệm vụ, dùng agent sinh K kế hoạch, rồi tính:

1. Trong mọi kế hoạch sinh ra, bao nhiêu kế hoạch hợp lệ?
2. Với một nhiệm vụ, trung bình agent phải sinh bao nhiêu kế hoạch mới có một kế hoạch hợp lệ?
3. Trong mọi lời gọi công cụ, bao nhiêu lời gọi hợp lệ?
4. Bao lâu thì một công cụ không hợp lệ được gọi?
5. Bao lâu thì công cụ hợp lệ được gọi với tham số không hợp lệ?
6. Bao lâu thì công cụ hợp lệ được gọi với giá trị tham số sai?

(Người tổng hợp nhận xét: nếu mỗi lần sinh độc lập và có tỷ lệ hợp lệ p, chỉ số 2 xấp xỉ 1/p — ví dụ 40% kế hoạch hợp lệ thì trung bình cần 2,5 lần sinh.)

Phân tích đầu ra tìm quy luật: agent hỏng nhiều hơn ở loại nhiệm vụ nào? Có giả thuyết vì sao không? Mô hình hay dùng sai công cụ nào? Một số công cụ khó dùng hơn; có thể cải thiện bằng prompt tốt hơn, thêm ví dụ hay finetuning; nếu mọi cách thất bại, cân nhắc thay công cụ bằng thứ dễ dùng hơn.

#### Lỗi công cụ (Tool failures, trang PDF 579–580)

Lỗi công cụ xảy ra khi dùng đúng công cụ nhưng đầu ra công cụ sai. Một kiểu là công cụ cho đầu ra sai: bộ chú thích ảnh trả mô tả sai, bộ sinh SQL trả câu SQL sai. Nếu agent chỉ sinh kế hoạch cấp cao và có mô-đun dịch từ mỗi hành động trong kế hoạch sang lệnh thực thi, lỗi có thể do dịch sai. Lỗi công cụ cũng có thể do agent không có công cụ phù hợp: rõ nhất là nhiệm vụ cần lấy giá cổ phiếu hiện tại từ internet mà agent không có internet.

Lỗi công cụ phụ thuộc từng công cụ; mỗi công cụ cần được kiểm thử độc lập. Luôn in ra mỗi lời gọi công cụ và đầu ra của nó để kiểm tra và đánh giá. Nếu có bộ dịch, dựng benchmark đánh giá nó. Phát hiện lỗi thiếu công cụ đòi hỏi hiểu công cụ nào nên được dùng; nếu agent thường hỏng ở một lĩnh vực cụ thể, có thể vì thiếu công cụ cho lĩnh vực đó — hãy làm việc với chuyên gia lĩnh vực và quan sát họ dùng công cụ gì.

#### Hiệu quả (Efficiency, trang PDF 580–581)

Agent có thể sinh kế hoạch hợp lệ, dùng đúng công cụ để hoàn thành nhiệm vụ, nhưng kém hiệu quả. Nên theo dõi:

- Trung bình agent cần bao nhiêu bước để hoàn thành một nhiệm vụ?
- Trung bình agent tốn bao nhiêu tiền cho một nhiệm vụ?
- Mỗi hành động thường mất bao lâu? Có hành động nào đặc biệt tốn thời gian hay tiền không?

So các chỉ số này với mốc so sánh — một agent khác hoặc một người làm. Khi so agent AI với người, nhớ rằng người và AI vận hành rất khác nhau, nên điều được coi là hiệu quả với người có thể kém hiệu quả với AI và ngược lại. Ví dụ vào 100 trang web có thể kém hiệu quả với người chỉ xem được một trang mỗi lúc, nhưng tầm thường với agent AI xem được mọi trang cùng lúc.

Cả RAG và agent thường xử lý thông tin vượt giới hạn context của mô hình. Một hệ bộ nhớ bổ sung cho context có thể tăng năng lực đáng kể — chủ đề của phần cuối.

### 12. Bộ nhớ (Memory, trang PDF 581–589)

Bộ nhớ là các cơ chế cho phép mô hình giữ lại và sử dụng thông tin. Hệ bộ nhớ đặc biệt hữu ích cho ứng dụng giàu tri thức như RAG và ứng dụng nhiều bước như agent. Hệ RAG dựa vào bộ nhớ cho context bổ sung, có thể lớn dần qua nhiều lượt khi truy xuất thêm thông tin. Hệ agent cần bộ nhớ để lưu chỉ dẫn, ví dụ, context, bộ công cụ, kế hoạch, đầu ra công cụ, phản tư… RAG và agent đòi hỏi bộ nhớ nhiều hơn, nhưng mọi ứng dụng AI cần giữ thông tin đều được lợi.

#### Ba cơ chế bộ nhớ

- **Tri thức nội tại (internal knowledge):** chính mô hình là một cơ chế bộ nhớ, vì nó giữ tri thức từ dữ liệu huấn luyện. Tri thức này không đổi trừ khi mô hình được cập nhật, và mô hình truy cập được nó ở mọi truy vấn.
- **Bộ nhớ ngắn hạn (short-term memory):** context của mô hình là một cơ chế bộ nhớ. Các tin nhắn trước trong cuộc hội thoại có thể được thêm vào context để mô hình dùng khi trả lời tiếp. Context được coi là bộ nhớ ngắn hạn vì nó không tồn tại qua các nhiệm vụ (truy vấn). Truy cập nhanh nhưng dung lượng hạn chế, nên thường dùng cho thông tin quan trọng nhất với nhiệm vụ hiện tại.
- **Bộ nhớ dài hạn (long-term memory):** nguồn dữ liệu ngoài mô hình truy cập qua truy xuất, như trong hệ RAG. Coi là bộ nhớ dài hạn vì nó tồn tại qua các nhiệm vụ. Khác tri thức nội tại, thông tin trong bộ nhớ dài hạn có thể xoá mà không cần cập nhật mô hình.

Con người có cơ chế tương tự: cách thở là tri thức nội tại (thường không quên trừ khi gặp chuyện nghiêm trọng); bộ nhớ ngắn hạn chứa thông tin liên quan ngay tới việc đang làm, như tên người vừa gặp; bộ nhớ dài hạn được bổ sung bằng sách, máy tính, ghi chép…

Chọn cơ chế nào cho dữ liệu tuỳ tần suất dùng: thông tin thiết yếu cho mọi nhiệm vụ nên đưa vào tri thức nội tại qua huấn luyện hay finetuning; thông tin hiếm khi cần nên nằm ở bộ nhớ dài hạn; bộ nhớ ngắn hạn dành cho thông tin tức thời, riêng cho context. Sơ đồ của sách (Hình 6-16, "thứ bậc thông tin của agent"): context (bộ nhớ ngắn hạn) đi thẳng vào mô hình; bộ nhớ ngoài (dài hạn) đi qua retriever vào mô hình; dữ liệu huấn luyện (tri thức nội tại) đi vào mô hình từ dưới; từ context có hai mũi tên chấm: "thông tin ít dùng" chuyển lên bộ nhớ ngoài, "thông tin thiết yếu cho nhiều nhiệm vụ" chuyển xuống dữ liệu huấn luyện.

#### Lợi ích của hệ bộ nhớ

Bộ nhớ thiết yếu cho con người vận hành; khi ứng dụng AI phát triển, các nhà phát triển nhanh chóng nhận ra bộ nhớ cũng quan trọng với mô hình AI. Nhiều công cụ quản lý bộ nhớ cho mô hình đã ra đời, và nhiều nhà cung cấp đã tích hợp bộ nhớ ngoài. Một số lợi ích:

- **Quản lý tràn thông tin trong một phiên:** khi thực thi nhiệm vụ, agent thu nhiều thông tin mới, có thể vượt độ dài context tối đa; phần dư có thể lưu vào hệ bộ nhớ dài hạn.
- **Giữ thông tin giữa các phiên:** một huấn luyện viên AI gần như vô dụng nếu mỗi lần xin lời khuyên bạn phải kể lại cả cuộc đời; trợ lý AI cứ quên sở thích của bạn thì thật phiền. Có lịch sử hội thoại, agent cá nhân hoá được hành động — ví dụ khi bạn hỏi gợi ý sách, nếu mô hình nhớ bạn từng mê *Tam thể* (*The Three-Body Problem*), nó có thể gợi ý sách tương tự.
- **Tăng tính nhất quán:** nếu bạn hỏi tác giả một câu chủ quan hai lần, như chấm một câu đùa từ 1 tới 5, tác giả nhiều khả năng trả lời nhất quán hơn nếu nhớ câu trả lời trước. Tương tự, mô hình tham chiếu được câu trả lời trước thì hiệu chỉnh được câu trả lời sau cho nhất quán.
- **Giữ toàn vẹn cấu trúc dữ liệu:** văn bản vốn phi cấu trúc, nên dữ liệu lưu trong context của mô hình văn bản là phi cấu trúc. Có thể đưa dữ liệu có cấu trúc vào context — như đưa bảng từng dòng — nhưng không có gì đảm bảo mô hình hiểu đó là một bảng. Hệ bộ nhớ lưu được dữ liệu có cấu trúc giúp giữ cấu trúc: agent tìm khách hàng tiềm năng có thể dùng một bảng Excel để lưu danh sách; agent cũng có thể dùng một hàng đợi để lưu chuỗi hành động cần làm.

#### Quản lý bộ nhớ

Hệ bộ nhớ cho mô hình AI thường gồm hai chức năng:

- **Quản lý bộ nhớ:** quyết định thông tin nào lưu ở bộ nhớ ngắn hạn và dài hạn.
- **Truy xuất bộ nhớ:** lấy thông tin liên quan tới nhiệm vụ từ bộ nhớ dài hạn — giống truy xuất trong RAG vì bộ nhớ dài hạn là nguồn dữ liệu ngoài. Phần này tập trung vào quản lý.

Quản lý bộ nhớ thường có hai thao tác: thêm và xoá. Nếu bộ nhớ không hạn chế thì có thể không cần xoá — điều này có thể đúng với bộ nhớ dài hạn vì lưu trữ ngoài khá rẻ và dễ mở rộng. Nhưng bộ nhớ ngắn hạn bị giới hạn bởi độ dài context tối đa của mô hình, nên cần chiến lược thêm gì và xoá gì.

Bộ nhớ dài hạn có thể dùng để chứa phần tràn của bộ nhớ ngắn hạn, tuỳ bạn dành bao nhiêu chỗ cho bộ nhớ ngắn hạn. Với một truy vấn, context đưa vào mô hình gồm bộ nhớ ngắn hạn và thông tin lấy từ bộ nhớ dài hạn; nên dung lượng ngắn hạn được quyết định bởi phần context dành cho thông tin truy xuất. Ví dụ dành 30% context thì mô hình dùng tối đa 70% giới hạn context cho bộ nhớ ngắn hạn; chạm ngưỡng này thì phần tràn được chuyển sang bộ nhớ dài hạn. (Người tổng hợp minh hoạ: với context 128.000 token, bộ nhớ ngắn hạn tối đa 89.600 token, 38.400 token dành cho thông tin truy xuất.)

Như nhiều thành phần khác trong chương, quản lý bộ nhớ không riêng gì ứng dụng AI; nó là nền móng của mọi hệ dữ liệu, và nhiều chiến lược đã được phát triển.

- **FIFO (first in, first out — vào trước ra trước):** thứ được thêm vào bộ nhớ ngắn hạn đầu tiên sẽ được chuyển ra lưu trữ ngoài đầu tiên. Khi hội thoại dài ra, các nhà cung cấp API như OpenAI có thể bắt đầu bỏ phần đầu cuộc hội thoại; các khung như LangChain có thể cho giữ N tin nhắn cuối hoặc N token cuối. Chiến lược này giả định tin nhắn sớm ít liên quan tới thảo luận hiện tại — giả định có thể sai nghiêm trọng: trong một số cuộc hội thoại, tin nhắn đầu tiên mang nhiều thông tin nhất, nhất là khi chúng nêu mục đích cuộc trò chuyện. (Chú thích của sách: với hội thoại giữa người với người, điều ngược lại có thể đúng nếu vài tin nhắn đầu chỉ là chào hỏi.) FIFO dễ cài đặt nhưng có thể làm mô hình mất dấu thông tin quan trọng.
- **Loại bỏ dư thừa:** ngôn ngữ người chứa dư thừa để tăng độ rõ và bù hiểu lầm. Nếu tự động phát hiện được dư thừa, dung lượng bộ nhớ giảm đáng kể. Một cách là dùng **tóm tắt** cuộc hội thoại, do cùng mô hình hay mô hình khác sinh; tóm tắt kèm theo dõi thực thể có tên (named entities) đi được khá xa. Bae và cộng sự (2022) tiến thêm: sau khi có tóm tắt, họ dựng bộ nhớ mới bằng cách ghép bộ nhớ với thông tin then chốt mà tóm tắt bỏ sót; họ phát triển một bộ phân loại, với mỗi câu trong bộ nhớ và mỗi câu trong tóm tắt, quyết định chỉ một, cả hai, hay không câu nào được thêm vào bộ nhớ mới.
- **Phản tư:** Liu và cộng sự (2023) yêu cầu agent sau mỗi hành động làm hai việc: (1) phản tư về thông tin vừa sinh ra; (2) quyết định thông tin mới nên được chèn vào bộ nhớ, gộp với bộ nhớ hiện có, hay thay thế thông tin khác — nhất là khi thông tin kia đã lỗi thời và mâu thuẫn với thông tin mới.
- (Chú thích của sách: chiến lược dựa trên mức sử dụng, như bỏ thông tin ít dùng nhất, khó hơn vì cần cách biết khi nào mô hình dùng một mẩu thông tin.)

**Thông tin mâu thuẫn:** có người chọn giữ thông tin mới hơn; có người nhờ mô hình AI phán xử giữ cái nào. Cách xử lý tuỳ trường hợp sử dụng: mâu thuẫn có thể làm agent bối rối, nhưng cũng có thể giúp nó nhìn từ nhiều góc độ.

### 13. Tóm tắt (Summary, trang PDF 589–591)

Vì sự phổ biến của RAG và tiềm năng của agent, những độc giả đọc sớm nói đây là chương họ hào hứng nhất.

Chương bắt đầu với RAG, mẫu hình ra đời trước. Nhiều nhiệm vụ cần lượng tri thức nền lớn, thường vượt cửa sổ context: trợ lý viết mã có thể cần cả codebase, trợ lý nghiên cứu có thể phải phân tích nhiều cuốn sách. Ban đầu sinh ra để vượt giới hạn context, RAG còn giúp dùng thông tin hiệu quả hơn, cải thiện chất lượng trả lời đồng thời giảm chi phí. Ngay từ đầu đã rõ RAG có giá trị lớn cho nhiều ứng dụng, và nó được áp dụng nhanh cả ở sản phẩm tiêu dùng lẫn doanh nghiệp.

RAG là quy trình hai bước: truy xuất thông tin liên quan từ bộ nhớ ngoài, rồi dùng thông tin đó để sinh câu trả lời chính xác hơn. Thành công của hệ RAG phụ thuộc chất lượng retriever. Retriever từ khoá như Elasticsearch và BM25 nhẹ hơn nhiều và cho mốc so sánh mạnh; retriever embedding tốn tính toán hơn nhưng có tiềm năng vượt. Truy xuất embedding chạy trên tìm kiếm vector — cũng là xương sống của nhiều ứng dụng internet cốt lõi như tìm kiếm và hệ gợi ý — nên nhiều thuật toán tìm kiếm vector phát triển cho các ứng dụng này dùng được cho RAG.

RAG có thể xem là trường hợp riêng của agent, trong đó retriever là một công cụ mô hình dùng được. Cả hai giúp mô hình vượt giới hạn context và cập nhật hơn, nhưng agent làm được nhiều hơn. Agent được xác định bởi môi trường và các công cụ nó dùng được. Trong agent AI, AI là bộ lập kế hoạch phân tích nhiệm vụ, cân nhắc các lời giải và chọn lời giải hứa hẹn nhất. Nhiệm vụ phức tạp có thể cần nhiều bước, đòi hỏi mô hình mạnh để lập kế hoạch; khả năng lập kế hoạch có thể được tăng bằng phản tư và hệ bộ nhớ để theo dõi tiến độ.

Càng cho mô hình nhiều công cụ, nó càng nhiều năng lực, giải được nhiệm vụ khó hơn. Nhưng agent càng tự động, thất bại của nó càng có thể thảm khốc. Dùng công cụ làm agent lộ ra trước nhiều rủi ro bảo mật bàn ở Chương 5; để agent chạy trong thế giới thật, cần các cơ chế phòng thủ chặt chẽ.

RAG và agent đều làm việc với nhiều thông tin, thường vượt độ dài context tối đa của mô hình nền; điều này đòi hỏi một hệ bộ nhớ để quản lý và dùng mọi thông tin mô hình có.

RAG và agent đều là phương pháp dựa trên prompt: chúng tác động lên chất lượng mô hình chỉ qua đầu vào, không sửa chính mô hình. Sửa mô hình nền có thể mở ra nhiều khả năng hơn nữa — chủ đề của chương sau.

## Luận điểm cốt lõi

### Mệnh đề

Chất lượng câu trả lời của mô hình nền tảng phụ thuộc vào context riêng cho từng truy vấn, không chỉ vào chỉ dẫn. RAG dựng context bằng cách truy xuất thông tin liên quan; agent mở rộng ý tưởng đó bằng cách cho mô hình công cụ để cả thu thập thông tin lẫn hành động. Thành công của RAG phụ thuộc vào retriever; thành công của agent phụ thuộc vào bộ công cụ và khả năng lập kế hoạch, được hỗ trợ bởi phản tư và bộ nhớ. Context dài hơn không làm RAG lỗi thời.

### Giả định

- Lượng dữ liệu cần dùng luôn lớn hơn context, và mô hình không dùng đều mọi phần của context dài.
- Tài liệu có thể chia thành đoạn mà vẫn giữ đủ nghĩa (nhờ chồng lấn, chia đệ quy, thêm ngữ cảnh).
- Độ liên quan có thể biểu diễn bằng một điểm số để xếp hạng (TF-IDF, BM25, độ tương đồng cosine, RRF).
- Mô hình nền tảng, nếu được hỗ trợ (ví dụ, công cụ, kiểm định), đủ năng lực để lập kế hoạch dùng được, dù câu hỏi "LLM có thật sự lập kế hoạch được không" còn mở.
- Các bước của agent gần như độc lập về xác suất lỗi (phép tính 0,95ⁿ).

### Cơ chế

1. **RAG:** lập chỉ mục (chia đoạn → từ khoá hoặc embedding → chỉ mục ngược hoặc cơ sở dữ liệu vector) → truy vấn (viết lại truy vấn → truy xuất → xếp hạng lại) → ghép đoạn vào prompt → mô hình sinh.
2. **Chọn retriever:** đánh đổi tốc độ, chi phí và khả năng cải thiện giữa từ khoá và embedding; thực tế kết hợp (hybrid search, RRF).
3. **Agent:** mô hình làm bộ não trong vòng lặp sinh kế hoạch → kiểm định → thực thi (function calling) → phản tư → sinh lại kế hoạch nếu cần; con người tham gia ở các hành động rủi ro.
4. **Lỗi cộng dồn** làm độ tin cậy giảm theo cấp số nhân với số bước, nên phải dùng mô hình mạnh, kiểm định sớm, và phản tư.
5. **Bộ nhớ** phân thông tin theo tần suất dùng vào ba tầng và quản lý tầng ngắn hạn bằng FIFO, tóm tắt hay phản tư.

### Bằng chứng và ví dụ tác giả đưa ra

- Chen và cộng sự (2017) lấy 5 trang Wikipedia; Lewis và cộng sự (2020) thấy RAG giảm bịa; Petroni và cộng sự (2020) cho thấy truy xuất cải thiện mạnh câu hỏi sự kiện.
- Gợi ý của Anthropic: dưới 200.000 token (khoảng 500 trang) thì đưa thẳng vào prompt.
- Bảng chỉ mục ngược (banana, machine, learning); công thức TF-IDF; BM25 là mốc khó vượt (dẫn lời CEO Perplexity).
- Bảng so sánh từ khoá và embedding; chi tiêu cơ sở dữ liệu vector bằng 1/5–1/2 chi tiêu API mô hình; IVF với 100–10.000 vector mỗi cụm; RRF với k = 60.
- Prompt truy xuất có ngữ cảnh của Anthropic (50–100 token mỗi đoạn).
- Ví dụ Kitty Vogue: text-to-SQL, agent dự báo doanh thu, prompt sinh kế hoạch.
- Lỗi cộng dồn: đúng 95% mỗi bước thì sau 10 bước chỉ còn 60%, sau 100 bước còn 0,6%.
- Chameleon: +11,37% trên ScienceQA, +17% trên TabMWP; phân bố gọi công cụ và cây chuyển tiếp công cụ.
- ReAct trên HotpotQA; Reflexion trên ra quyết định và lập trình.
- Toolformer 5, Chameleon 13, Gorilla 1.645 API.
- Các ví dụ lỗi: bing_search không có, lbs_to_kg hai tham số, 100 thay vì 120, Hà Nội thành TP. Hồ Chí Minh, xếp 40 trong 50 người vào 30 phòng.

### Kết luận và hàm ý cho người xây dựng ứng dụng AI

- Bắt đầu bằng truy xuất từ khoá (BM25) làm mốc; chỉ thêm embedding khi đo được lợi ích bù được chi phí; trong sản xuất thường dùng hybrid.
- Đánh giá RAG theo ba lớp: chất lượng truy xuất (precision, recall, NDCG/MRR), chất lượng embedding, và đầu ra cuối.
- Chia đoạn, xếp hạng lại, viết lại truy vấn và thêm ngữ cảnh là bốn đòn bẩy rẻ trước khi nghĩ tới finetuning.
- Với agent: dùng mô hình mạnh; tách lập kế hoạch khỏi thực thi; kiểm định kế hoạch; in và kiểm tra mọi lời gọi công cụ và tham số; giới hạn và xin phê duyệt cho hành động ghi.
- Chọn công cụ bằng thực nghiệm (ablation, phân bố lời gọi); ưu tiên ít công cụ nhưng dễ dùng.
- Đánh giá agent theo ba kiểu hỏng: lập kế hoạch, công cụ, hiệu quả; tính cả ràng buộc thời gian.
- Thiết kế bộ nhớ có chủ đích: đừng để FIFO lặng lẽ xoá mục đích của cuộc hội thoại.

## Thuật ngữ

| Thuật ngữ | Tiếng Việt | Giải thích ngắn |
|---|---|---|
| context | context (ngữ cảnh đầu vào) | thông tin riêng cho từng truy vấn đưa vào mô hình |
| context construction | dựng context | chọn và ghép thông tin vào prompt |
| retrieval-augmented generation (RAG) | sinh có tăng cường truy xuất | truy xuất thông tin rồi dùng nó để sinh |
| retrieve-then-generate | truy xuất rồi sinh | mẫu hình gốc của RAG |
| document reader | bộ đọc tài liệu | mô hình đọc tài liệu đã lấy để trả lời |
| knowledge-intensive task | nhiệm vụ cần nhiều tri thức | không thể đưa hết tri thức vào mô hình |
| hallucination | bịa | mô hình sinh thông tin sai như thật |
| feature engineering | thiết kế đặc trưng | dựng đầu vào cho mô hình học máy cổ điển |
| retriever / generator | retriever / mô hình sinh | thành phần truy xuất / thành phần sinh |
| external memory | bộ nhớ ngoài | nguồn dữ liệu ngoài mô hình |
| indexing / querying | lập chỉ mục / truy vấn | chuẩn bị dữ liệu / gửi câu hỏi để lấy dữ liệu |
| chunk, chunking | đoạn, chia đoạn | phần nhỏ của tài liệu; cách cắt tài liệu |
| overlap | chồng lấn | phần lặp giữa hai đoạn liền nhau |
| recursive splitting | chia đệ quy | chia bằng đơn vị nhỏ dần |
| information retrieval (IR) | truy xuất thông tin | ngành tìm thông tin liên quan |
| relevance score | điểm liên quan | điểm dùng để xếp hạng tài liệu |
| term-based / lexical retrieval | truy xuất dựa trên từ khoá / từ vựng | xếp hạng theo việc chứa từ của truy vấn |
| embedding-based / semantic retrieval | truy xuất dựa trên embedding / ngữ nghĩa | xếp hạng theo độ gần nghĩa |
| sparse / dense vector | vector thưa / dày | phần lớn bằng 0 / phần lớn khác 0 |
| one-hot vector | vector one-hot | chỉ một vị trí bằng 1 |
| SPLADE | SPLADE | embedding thưa dựa trên BERT |
| term frequency (TF) | tần suất từ | số lần từ xuất hiện trong tài liệu |
| inverse document frequency (IDF) | tần suất tài liệu nghịch đảo | log(N / số tài liệu chứa từ) |
| TF-IDF | TF-IDF | tổng TF × IDF qua các từ của truy vấn |
| inverted index | chỉ mục ngược | từ → danh sách tài liệu chứa từ |
| Elasticsearch, Lucene | Elasticsearch, Lucene | phần mềm tìm kiếm toàn văn |
| BM25 (Okapi BM25) | BM25 | TF-IDF có bão hoà và chuẩn hoá theo độ dài |
| tokenization | tách từ | chia văn bản thành đơn vị |
| n-gram, bigram | n-gram, bigram | chuỗi n từ liên tiếp; chuỗi hai từ |
| stop word | stop word (từ dừng) | từ quá phổ biến, thường bị bỏ |
| vector database | cơ sở dữ liệu vector | nơi lưu và tìm embedding |
| vector search | tìm kiếm vector | tìm vector gần vector truy vấn |
| nearest neighbor search, k-NN | tìm láng giềng gần nhất, k-NN | lấy k vector gần nhất |
| approximate nearest neighbor (ANN) | láng giềng gần nhất xấp xỉ | tìm gần đúng, nhanh |
| cosine similarity | độ tương đồng cosine | cosin góc giữa hai vector |
| LSH (locality-sensitive hashing) | băm nhạy vị trí | băm vector giống nhau vào cùng xô |
| HNSW | HNSW | đồ thị nhiều tầng để tìm láng giềng |
| product quantization | lượng tử hoá tích | nén vector bằng các vector con |
| IVF (inverted file index) | chỉ mục tệp ngược | phân cụm K-means rồi tìm trong cụm gần |
| quantization | lượng tử hoá | giảm độ chính xác số |
| FAISS, ScaNN, Annoy, Hnswlib | FAISS, ScaNN, Annoy, Hnswlib | thư viện tìm kiếm vector |
| context precision / context recall | context precision / context recall | tỷ lệ liên quan trong số lấy về / tỷ lệ được lấy trong số liên quan |
| NDCG, MAP, MRR | NDCG, MAP, MRR | chỉ số đánh giá thứ hạng |
| MTEB | MTEB | benchmark đánh giá embedding |
| ANN-Benchmarks, BEIR | ANN-Benchmarks, BEIR | bộ so sánh ANN; bộ đánh giá truy xuất |
| QPS (queries per second) | số truy vấn mỗi giây | thông lượng truy vấn |
| hybrid search | tìm kiếm lai | kết hợp từ khoá và embedding |
| reranking / reranker | xếp hạng lại / bộ xếp hạng lại | xếp lại ứng viên bằng cơ chế chính xác hơn |
| reciprocal rank fusion (RRF) | hợp nhất theo nghịch đảo thứ hạng | Σ 1/(k + hạng) |
| query rewriting / reformulation / expansion | viết lại / tái lập / mở rộng truy vấn | làm truy vấn tự đủ nghĩa |
| identity resolution | xác định danh tính | tìm ra thực thể được nhắc tới |
| contextual retrieval | truy xuất có ngữ cảnh | thêm mô tả bối cảnh vào đoạn |
| metadata | metadata (siêu dữ liệu) | thẻ, từ khoá, tiêu đề đi kèm dữ liệu |
| multimodal RAG | RAG đa phương thức | truy xuất cả ảnh, âm thanh, video |
| CLIP | CLIP | mô hình embedding chung cho ảnh và văn bản |
| text-to-SQL | text-to-SQL | sinh SQL từ câu hỏi tự nhiên |
| semantic parsing | phân tích ngữ nghĩa | chuyển ngôn ngữ tự nhiên thành dạng hình thức |
| table schema | lược đồ bảng | mô tả cột và kiểu dữ liệu |
| agent / intelligent agent / rational agent | agent / agent thông minh / agent hợp lý | thứ cảm nhận và tác động lên môi trường |
| environment | môi trường | nơi agent hoạt động |
| action | hành động | việc agent làm được |
| tool, tool inventory | công cụ, bộ công cụ | hàm agent gọi được; tập các hàm đó |
| read-only actions / write actions | hành động chỉ đọc / hành động ghi | cảm nhận / thay đổi môi trường |
| knowledge augmentation | tăng cường tri thức | công cụ đưa thêm thông tin |
| capability extension | mở rộng năng lực | công cụ bù điểm yếu của mô hình |
| stale model | mô hình lỗi thời | dữ liệu huấn luyện đã cũ |
| code interpreter | trình thông dịch mã | công cụ chạy mã |
| code injection | tiêm mã | tấn công đưa mã độc vào để chạy |
| OCR | nhận dạng ký tự quang học | đọc chữ từ ảnh |
| function calling | function calling (gọi hàm) | mô hình chọn công cụ và sinh tham số |
| tool_choice: required / none / auto | bắt buộc / không / tự động | thiết lập dùng công cụ |
| compound mistakes | lỗi cộng dồn | độ chính xác giảm theo số bước |
| planning, plan, planner | lập kế hoạch, kế hoạch, bộ lập kế hoạch | biến nhiệm vụ thành chuỗi hành động |
| goal / constraint | mục tiêu / ràng buộc | hai thành phần của nhiệm vụ |
| task decomposition | phân rã nhiệm vụ | chia nhiệm vụ thành bước nhỏ |
| plan validation | kiểm định kế hoạch | kiểm tra kế hoạch trước khi chạy |
| multi-agent system | hệ đa agent | nhiều thành phần, mỗi thành phần một agent |
| intent classifier | bộ phân loại ý định | xác định người dùng muốn gì |
| human-in-the-loop | con người trong vòng lặp | người tham gia một số khâu |
| autoregressive | tự hồi quy | sinh token sau dựa trên token trước |
| backtracking | quay lui | trở lại trạng thái trước để thử nhánh khác |
| world model | mô hình thế giới | dự đoán kết quả của hành động |
| reinforcement learning (RL) | học tăng cường | học hành động để tối đa phần thưởng |
| actor-critic | actor-critic | một bên hành động, một bên đánh giá |
| planning granularity | độ chi tiết của kế hoạch | kế hoạch cấp cao hay chi tiết |
| hierarchical planning | lập kế hoạch phân cấp | kế hoạch cấp cao rồi chi tiết dần |
| translator / program generator | bộ dịch / bộ sinh chương trình | đổi kế hoạch ngôn ngữ tự nhiên thành lệnh |
| control flow: sequential, parallel, if, for | luồng điều khiển: tuần tự, song song, rẽ nhánh, vòng lặp | thứ tự thực thi hành động |
| reflection / error correction | phản tư / sửa lỗi | đánh giá để tìm lỗi / sửa lỗi |
| self-critique | tự phê bình | mô hình tự đánh giá đầu ra |
| ReAct | ReAct | xen kẽ suy nghĩ, hành động, quan sát |
| Reflexion, trajectory | Reflexion, quỹ đạo | khung phản tư; kế hoạch theo cách gọi của Reflexion |
| evaluator / self-reflection module | bộ đánh giá / mô-đun tự phản tư | hai mô-đun của Reflexion |
| tool selection, ablation study | chọn công cụ, nghiên cứu cắt bỏ | thử bỏ từng công cụ để đo tác động |
| tool transition | chuyển tiếp công cụ | xác suất gọi Y sau X |
| skill manager / skill library | bộ quản lý kỹ năng / thư viện kỹ năng | lưu kỹ năng mới để dùng lại (Voyager) |
| failure mode | kiểu hỏng | một loại lỗi có thể đo tần suất |
| planning failure / tool failure / efficiency | lỗi lập kế hoạch / lỗi công cụ / hiệu quả | ba nhóm hỏng của agent |
| goal failure | lỗi mục tiêu | không đạt mục tiêu hoặc vi phạm ràng buộc |
| memory, internal knowledge | bộ nhớ, tri thức nội tại | cơ chế giữ thông tin; tri thức trong trọng số |
| short-term / long-term memory | bộ nhớ ngắn hạn / dài hạn | context / nguồn ngoài truy xuất được |
| memory management / memory retrieval | quản lý / truy xuất bộ nhớ | thêm, xoá / lấy thông tin |
| FIFO | vào trước ra trước | bỏ thông tin cũ nhất trước |
| named entity | thực thể có tên | tên người, tổ chức, địa điểm |

## Câu nói đáng nhớ

> "Just like how a human is more likely to give a wrong answer when lacking information, AI models are more likely to make mistakes and hallucinate when they are missing context." — mở đầu chương, trang PDF 494
>
> *Dịch: Cũng như con người dễ trả lời sai hơn khi thiếu thông tin, mô hình AI dễ mắc lỗi và bịa hơn khi thiếu context.*
>
> Ý nghĩa: đặt lý do tồn tại cho cả chương — nhiều lỗi "bịa" là lỗi thiếu thông tin chứ không phải lỗi mô hình.

> "Context construction for foundation models is equivalent to feature engineering for classical ML models." — mục RAG, trang PDF 497
>
> *Dịch: Dựng context cho mô hình nền tảng tương đương với thiết kế đặc trưng cho mô hình học máy cổ điển.*
>
> Ý nghĩa: nối kỹ năng mới với kỹ năng cũ — phần lớn công sức vẫn là chuẩn bị đúng đầu vào.

> "Many people think that a sufficiently long context will be the end of RAG. I don't think so." — mục RAG, trang PDF 497
>
> *Dịch: Nhiều người nghĩ context đủ dài sẽ là dấu chấm hết cho RAG. Tôi không nghĩ vậy.*
>
> Ý nghĩa: lập trường rõ của tác giả trong một tranh luận còn nóng tới nay.

> "The success of a RAG system depends on the quality of its retriever." — mục RAG Architecture, trang PDF 499
>
> *Dịch: Thành công của một hệ RAG phụ thuộc vào chất lượng retriever của nó.*
>
> Ý nghĩa: chỉ ra chỗ nên đầu tư công sức trước tiên khi RAG trả lời kém.

> "Making a genuine improvement over BM25 or full-text search is hard." — Aravind Srinivas, dẫn trong chú thích, trang PDF 592
>
> *Dịch: Cải thiện thực sự so với BM25 hay tìm kiếm toàn văn là việc khó.*
>
> Ý nghĩa: lời nhắc khiêm tốn từ CEO một công ty tìm kiếm AI — đừng bỏ qua mốc so sánh cũ.

> "If the model's accuracy is 95% per step, over 10 steps, the accuracy will drop to 60%, and over 100 steps, the accuracy will be only 0.6%." — mục Agent Overview, trang PDF 539
>
> *Dịch: Nếu mô hình đúng 95% mỗi bước, qua 10 bước độ chính xác giảm còn 60%, qua 100 bước chỉ còn 0,6%.*
>
> Ý nghĩa: phép tính đơn giản giải thích vì sao agent dài hơi khó đáng tin.

> "Just as you shouldn't give an intern the authority to delete your production database, you shouldn't allow an unreliable AI to initiate bank transfers." — mục Write actions, trang PDF 545
>
> *Dịch: Cũng như không nên cho thực tập sinh quyền xoá cơ sở dữ liệu sản xuất, không nên để một AI chưa đáng tin khởi tạo chuyển khoản.*
>
> Ý nghĩa: nguyên tắc phân quyền tối thiểu áp vào agent.

> "To avoid fruitless execution, planning should be decoupled from execution." — mục Planning overview, trang PDF 548
>
> *Dịch: Để tránh thực thi vô ích, lập kế hoạch nên được tách khỏi thực thi.*
>
> Ý nghĩa: quy tắc thiết kế agent quan trọng nhất của chương.

> "While reflection isn't strictly necessary for an agent to operate, it's necessary for an agent to succeed." — mục Reflection and error correction, trang PDF 567
>
> *Dịch: Phản tư không thực sự cần để agent vận hành, nhưng cần để agent thành công.*
>
> Ý nghĩa: phân biệt "chạy được" với "làm đúng".

> "Evaluation is about detecting failures." — mục Agent Failure Modes and Evaluation, trang PDF 576
>
> *Dịch: Đánh giá là việc phát hiện thất bại.*
>
> Ý nghĩa: định hướng đánh giá agent bằng danh mục kiểu hỏng thay vì một con số tổng.

## Đánh giá và phát hiện đáng chú ý

### Sức mạnh của chương

Chương gom hai chủ đề nóng nhất của 2023–2024 vào một khung chung: cả RAG lẫn agent đều là cách dựng context, và RAG là trường hợp riêng của agent với retriever là công cụ. Phần RAG đặt nền vững bằng lịch sử truy xuất thông tin (TF-IDF, BM25, chỉ mục ngược, ANN) thay vì chỉ nói về cơ sở dữ liệu vector, nên người đọc hiểu vì sao BM25 vẫn là mốc khó vượt và vì sao hybrid search là mặc định. Bảng so sánh từ khoá và embedding, danh sách câu hỏi khi chọn giải pháp truy xuất, và sáu chỉ số đánh giá lỗi lập kế hoạch đều dùng ngay được. Phần agent thẳng thắn gắn nhãn "thử nghiệm" và đưa ra khung rõ: môi trường + công cụ + bộ lập kế hoạch; tách lập kế hoạch khỏi thực thi; ba kiểu hỏng. Phép tính lỗi cộng dồn 0,95ⁿ là lập luận đơn giản mà thuyết phục.

### Những chỗ đơn giản hoá hoặc chưa chặt

- **Công thức:** IDF được tả hai cách khác nhau (có và không có log); BM25 không có công thức; RRF có ví dụ k = 0 nhưng khuyên k = 60 mà không giải thích vai trò làm phẳng (xem khối Lưu ý).
- **Đánh giá retriever:** precision và recall được định nghĩa nhưng không có ví dụ số; NDCG, MAP, MRR chỉ được nêu tên.
- **Chiến lược chia đoạn:** không có con số thực nghiệm nào về kích thước đoạn tốt; "phải thử nghiệm" là đúng nhưng không cho điểm khởi đầu.
- **Truy xuất có ngữ cảnh:** sách không nêu kết quả đo của Anthropic; theo hiểu biết của người tổng hợp, bài "Introducing Contextual Retrieval" (9/2024) báo giảm khoảng 49% số lần truy xuất thất bại khi kết hợp contextual embedding với contextual BM25, và khoảng 67% khi thêm reranking — và chi phí sinh context được giảm nhờ prompt caching.
- **Ví dụ Kitty Vogue** có các chỗ không nhất quán về tên hàm và số công cụ; hình về luồng điều khiển có nhãn ví dụ lệch nội dung.
- **Lỗi cộng dồn** giả định các bước độc lập và một lỗi làm hỏng cả chuỗi; trong thực tế, phản tư có thể sửa lỗi giữa chừng (chính chương nói vậy), nên 0,6% là cận dưới bi quan.
- **Lập kế hoạch:** phần tranh luận LLM có lập kế hoạch được không chỉ dẫn quan điểm, không có số liệu benchmark (ví dụ TravelPlanner được nêu tên nhưng không nêu kết quả).
- **Bảo mật agent** (prompt injection gián tiếp qua tài liệu truy xuất hay trang web) chỉ được trỏ về Chương 5, dù đây là rủi ro lớn nhất của agent duyệt web.
- **Bộ nhớ:** phần quản lý bộ nhớ ngắn, không bàn bộ nhớ dạng đồ thị tri thức hay cách đánh giá bộ nhớ.

### Những gì đã thay đổi từ cuối 2024 (theo hiểu biết của người tổng hợp)

- **Chuẩn kết nối công cụ:** Anthropic công bố Model Context Protocol (MCP) cuối 11/2024; trong 2025 MCP được OpenAI, Google, Microsoft và nhiều khung agent hỗ trợ, trở thành cách phổ biến khai báo bộ công cụ — phần "Function calling" của chương giờ thường đi qua máy chủ MCP.
- **Mô hình suy luận:** OpenAI o1 (9/2024), o3, DeepSeek-R1 (1/2025), Claude với "extended thinking", Gemini 2.5 "thinking" được huấn luyện bằng học tăng cường để suy luận dài trước khi trả lời; khả năng lập kế hoạch và dùng công cụ nhiều bước tăng rõ. Điều này phần nào đúng với dự đoán của tác giả rằng agent mô hình nền tảng và agent học tăng cường sẽ hợp nhất.
- **Agent dùng máy tính và agent nghiên cứu:** Anthropic Computer Use (10/2024), OpenAI Operator (1/2025), các sản phẩm "Deep Research" của Google (12/2024) và OpenAI (2/2025), và các agent lập trình chạy trong terminal (Claude Code, OpenAI Codex) biến khung "môi trường + công cụ + lập kế hoạch" thành sản phẩm đại trà. Các nhà cung cấp cũng ra SDK agent (OpenAI Responses API và Agents SDK, 3/2025).
- **Context dài hơn nữa:** GPT-4.1 (4/2025) có context 1 triệu token, Llama 4 Scout công bố 10 triệu token; tranh luận "context dài có thay RAG không" tiếp diễn, nhưng thực hành phổ biến vẫn kết hợp cả hai, đúng như lập luận của tác giả. Khái niệm "context engineering" (kỹ thuật dựng context) trở thành từ khoá năm 2025, gần như đồng nghĩa với cách tác giả mở chương.
- **Biến thể RAG mới:** GraphRAG (Microsoft, 2024) dùng đồ thị tri thức; "agentic RAG" để agent tự quyết định truy xuất bao nhiêu lần; truy xuất trực tiếp trên ảnh trang tài liệu (ColPali, 2024) cho RAG đa phương thức; tìm kiếm vector được tích hợp vào nhiều cơ sở dữ liệu thông thường (PostgreSQL với pgvector, Elasticsearch, MongoDB), như tác giả dự đoán.
- **Bộ nhớ trong sản phẩm:** ChatGPT mở rộng bộ nhớ sang tham chiếu toàn bộ lịch sử chat (4/2025); Claude và Gemini cũng thêm bộ nhớ giữa các phiên — đúng lợi ích "giữ thông tin giữa các phiên" mà chương nêu.

### Liên hệ các chương khác

- [C02-hieu-ve-mo-hinh-nen-tang.md](C02-hieu-ve-mo-hinh-nen-tang.md): semantic parsing, text-to-SQL, đầu ra có cấu trúc — nền của function calling.
- [C03-phuong-phap-danh-gia.md](C03-phuong-phap-danh-gia.md): embedding, độ tương đồng từ vựng và ngữ nghĩa, AI judge — dùng để đánh giá retriever và kế hoạch.
- [C04-danh-gia-he-thong-ai.md](C04-danh-gia-he-thong-ai.md): đánh giá theo thành phần và đầu–cuối, chọn mô hình — áp cho hệ RAG và agent.
- [C05-prompt-engineering.md](C05-prompt-engineering.md): độ dài và hiệu quả context, chain-of-thought, tự phê bình, chia nhỏ nhiệm vụ, phòng thủ trước tấn công prompt — các viên gạch của agent.
- [C07-finetuning.md](C07-finetuning.md): khi dựng context chưa đủ thì sửa mô hình; finetune mô hình embedding, retriever hay bộ lập kế hoạch.
- [C08-ky-thuat-du-lieu.md](C08-ky-thuat-du-lieu.md): dữ liệu để finetune và đánh giá, tương tự tập (nhiệm vụ, bộ công cụ) của chương này.
- [C09-toi-uu-suy-luan.md](C09-toi-uu-suy-luan.md): độ trễ và chi phí — vấn đề lớn của agent nhiều bước và phản tư.
- [C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md](C10-kien-truc-ky-thuat-ai-va-phan-hoi-nguoi-dung.md): đặt RAG, agent, guardrail và bộ nhớ vào kiến trúc ứng dụng hoàn chỉnh.

### Vận dụng

- **Kỹ sư xây dựng ứng dụng AI:**
  - Trước khi dựng RAG, kiểm tra kho tri thức: nếu dưới vài trăm nghìn token và ít thay đổi, thử đưa thẳng vào prompt (kèm prompt caching) và đo; chỉ dựng RAG khi cần.
  - Dựng RAG theo thứ tự: BM25 làm mốc → thêm embedding → hybrid với RRF (k = 60) → reranker → truy xuất có ngữ cảnh; đo context precision/recall trên một tập truy vấn có nhãn ở mỗi bước.
  - Thêm mã lỗi, tên sản phẩm, mã giao dịch vào metadata để không bị embedding làm mờ.
  - Với agent: bắt đầu với ít công cụ, mô tả kỹ; ghi log mọi lời gọi công cụ và tham số; tách lập kế hoạch khỏi thực thi; đặt phê duyệt của người cho mọi hành động ghi; đo sáu chỉ số lỗi lập kế hoạch và chi phí/độ trễ trung bình mỗi nhiệm vụ.
  - Tính trước "ngân sách lỗi": nếu cần 90% thành công cho 10 bước, mỗi bước phải đúng khoảng 99%.
- **Người làm tài chính/kinh tế dùng AI:**
  - RAG trên báo cáo tài chính, văn bản pháp quy hay biên bản họp: dùng hybrid search vì mã chứng khoán, số hiệu văn bản, mã tài khoản là từ khoá mà embedding dễ làm mờ; xếp hạng lại theo thời gian để ưu tiên số liệu mới nhất.
  - Câu hỏi về số liệu (doanh thu quý, tồn kho) nên đi qua text-to-SQL trên bảng thay vì truy xuất văn bản; luôn hiện câu SQL và kết quả để kiểm tra.
  - Ví dụ của chương về agent mua bán cổ phiếu theo báo cáo lợi nhuận là minh hoạ luồng rẽ nhánh, không phải khuyến nghị: hành động ghi có hậu quả tài chính (chuyển tiền, đặt lệnh) cần phê duyệt của người và giới hạn quyền.
  - Phép tính lỗi cộng dồn áp cho mọi quy trình phân tích nhiều bước bằng AI (thu thập dữ liệu → làm sạch → mô hình → báo cáo): mỗi bước cần kiểm tra độc lập, giống kiểm soát nội bộ nhiều lớp.
