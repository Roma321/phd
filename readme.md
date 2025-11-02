### Компиляция Markdown в pdf
```bash
alias md2pdf='f(){ pandoc "$1" -o "${1%.md}.pdf" \
  --from=gfm \
  --pdf-engine=xelatex \
  -V mainfont="DejaVu Sans" \
  -V geometry:margin=1in \
  -V float-placement=H \
  -V linkcolor=blue \
  --include-in-header=<(echo "\usepackage{float}"); }; f'
md2pdf file.md
```