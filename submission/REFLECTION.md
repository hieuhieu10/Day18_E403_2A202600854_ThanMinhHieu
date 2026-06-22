Team em dễ vướng nhất vào anti-pattern giữ dữ liệu thô nhưng không chuẩn hóa sớm giữa Bronze và Silver. Lý do là khi mới làm data pipeline, mọi người thường ưu tiên ingest cho nhanh, còn việc làm sạch schema, bỏ dữ liệu trùng, và kiểm tra chất lượng bị để lại phía sau.

Nếu kéo dài, hậu quả là Gold metric sẽ thiếu ổn định: cùng một dashboard nhưng số liệu có thể lệch chỉ vì duplicate record, field null, hoặc kiểu dữ liệu không nhất quán. Điều này làm team mất niềm tin vào dữ liệu và tốn thời gian debug lại từ đầu.

Sau bài lab này, em nghĩ team nên giữ Bronze càng gần raw càng tốt, nhưng phải có bước Silver rõ ràng để validate, dedup, và chuẩn hóa schema trước khi đi tiếp sang Gold.
