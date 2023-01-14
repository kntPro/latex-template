# src
- `.tex`や画像等をいれるディレクトリ
- ファイル分割してある
- 必要に応じてファイルを追加, `main.tex`に追記する
## 構成
File | Description
--- | ---
[main.tex](main.tex) | main, 表紙の定義と全体の構成,各ファイルへの参照を持つ
[ch_*.tex](ch_experiment.tex) | それぞれのchapter（章）, リンクは実験
[reference.bib](reference.bib) | 参考文献
## 参考文献
- BiBTeXは、本文中で`\cite{}`引用されてないやつはエラーになる
- 引用されてないやつもあるなら、`\bibliographystyle{}`の前に`\nocite{*}`
- https://mathlandscape.com/latex-cite/
- https://mathlandscape.com/latex-bib/
- ぐぐりながらやる
## めも
- ファイル分割時、重複は不要
- コンパイルすると、pdflatexで実行されてしまう（たぶん設定の影響）
  - `devcontainer.json`に追記して修正。recipe書かないといけなさそう
- 論文表紙テンプレが使えない！
  - `documentclass`のオプションに`notitlepage`
- `a4paper`だと指導教員の部分がはみでた
  - `a4j`にした
- https://medemanabu.net/latex/