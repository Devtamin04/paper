# StatLM — Bài báo IEEE (song ngữ)

Bài báo định dạng IEEE Journal (`IEEEtran`), rút gọn từ khóa luận
*"Phương pháp nâng cao hiệu suất phân loại văn bản đa nhãn tiếng Việt không giám sát"*
(Nguyễn Quang Tuấn — đồng tác giả Lê Khánh Trình, UET-VNU), độ dài ~7–8 trang.

## Tệp
- `statlm_paper.tex` — **bản tiếng Việt**.
- `statlm_paper_en.tex` — **bản tiếng Anh** (English version).
- `references.bib` — tài liệu tham khảo (dùng chung cho cả hai bản).
- `figures/overview.png` — Hình 1: kiến trúc tổng quan encoder–decoder.
- `figures/stage1.png` — Hình 2: đồ thị câu TextRank (Tầng 1).
- `figures/stage2.png` — Hình 3: pipeline KeyBERT (Tầng 2).
- `figures/statlm_figures.drawio` — nguồn draw.io (3 trang) để chỉnh sửa hình.
- `figures/statlm.png`, `figures/notebooklm.png` — ảnh cũ, **không còn dùng** (có thể xóa).

Hai bản bám sát cùng một format/quy định IEEE (Index Terms, `\IEEEPARstart`,
two-column journal, `\bibliographystyle{IEEEtran}`), nội dung và số liệu khớp nhau.

## Biên dịch
Cần `IEEEtran.cls`, `IEEEtran.bst` (đi kèm gói template IEEE) và gói **vntex**
(font T5) để hiển thị tiếng Việt — bản tiếng Anh cũng chứa vài nhãn ví dụ tiếng
Việt (vd. "Giáo dục", "Hà Nội"). Chạy theo trình tự (thay `statlm_paper` bằng
`statlm_paper_en` cho bản tiếng Anh):

```bash
pdflatex statlm_paper
bibtex   statlm_paper
pdflatex statlm_paper
pdflatex statlm_paper
```

Khuyến nghị dùng **Overleaf** (đã có sẵn `IEEEtran` và `vntex`): tải cả thư mục
lên, chọn tệp chính, compiler **pdfLaTeX**.

### Nếu môi trường không có vntex / T5
Chuyển compiler sang **XeLaTeX** (hoặc LuaLaTeX) và thay hai dòng font ở đầu tệp

```latex
\usepackage[utf8]{inputenc}
\usepackage[T5]{fontenc}
```

bằng

```latex
\usepackage{fontspec}
\setmainfont{TeX Gyre Termes}  % font kiểu Times, hỗ trợ đầy đủ tiếng Việt
```

(bản tiếng Việt thì thay khối `inputenc/fontenc/vietnam` tương ứng.)
