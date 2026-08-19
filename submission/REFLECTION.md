# Reflection — Lab 19

**Tên:** Hà Anh Tuấn
**Cohort:** A20-K1
**Path đã chạy:** lite

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` / `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

Hybrid thắng hầu hết các query paraphrase và mixed vì kết hợp độ chính xác BM25 với khả năng ngữ nghĩa của embedding. Với query exact, BM25 thường nhanh hơn và đạt độ chính xác cao hơn do trùng khớp từ khóa. Khi yêu cầu latency rất thấp hoặc môi trường không thể warm‑up mô hình embedding, nên dùng pure BM25 (hoặc pure vector nếu dữ liệu ngữ nghĩa mạnh và không có từ khóa). 

---

## Điều ngạc nhiên nhất khi làm lab này

Việc khởi động FastAPI server mất thời gian đáng kể (30‑60s) do việc tải mô hình `Searcher` nặng. Khi server đã chạy, các benchmark latency giảm mạnh, cho thấy tầm quan trọng của warm‑up và việc điều chỉnh RRF depth để tránh latency quá cao.

_(Optional, 1–2 câu)_

---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
