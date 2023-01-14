# latex-template
- Docker + VSCodeでLaTeXをかけるようにするリポジトリ
- VSCode devcontainerを使用
- uplatex + dvipdfmx
## 注意
- まだ整備中（動きはする）
- Dockerよくわからん
- devcontainerわからん
- LaTeXわからん
- latexindentいれてるけど、わからんからなにもしてない
## 構成
| Directory or File | Description
| ------ | -------
| [.devcontainer](.devcontainer) | VSCode devcontainer関連, Dockerfileもこの中
| [src](src) | `.tex`が入ってる
| [.latexmkrc](.latexmkrc) | コンパイルの自動化(?)ツール, ぐぐってください
## 環境構築
### そのまま動かすのに必要なもの
- Docker
- VSCode
  - Remote -Containers
  - LaTeX Workshop
### 導入
- template repositoryにしてるので、`Use this template`をおせばいける、、、はず
## 参考
- https://pyteyon.hatenablog.com/entry/2021/01/05/140841
- https://zenn.dev/being/articles/how-to-use-my-latex
## 自分用めも
- 安全でないリポジトリ...
  - `git config --global -l`で表示
  - リビルドするたびに出る？