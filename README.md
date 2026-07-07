# ig-mirror(IG投稿用画像の公開ミラー)

役割: Instagram投稿予定の画像を、祐太さんのiPhoneに**ワンタップで一括保存**するための公開置き場。
iOSショートカットが認証なしで読めるように公開リポジトリにしている(2026-07-07 祐太さん承認)。

## 置いてよいもの・ダメなもの

- **置いてよい**: 数時間以内にInstagramで公開する予定の完成画像(検品・仕上げパス済み)のみ
- **置いてはダメ**: 下書き段階の画像・投稿しないボツ画像・レポート類・個人情報を含むもの
  (ここは全世界に公開されている。「どうせIGで公開するもの」以外は絶対に置かない)

## 構成

- `images/YYYY-MM-DD-*.png` — 投稿画像(claude-general の該当assetsからコピー)
- `manifests/YYYY-MM-DD.txt` — その日の画像URL一覧(1行1URL・raw形式)。iOSショートカットがこれを読む

## 運用(Claude向け)

1. IGのGO確認を出すとき、対象画像を `images/` にコピーし、raw URLの一覧を `manifests/YYYY-MM-DD.txt` に書いてコミット・プッシュする
   - raw URLの形式: `https://raw.githubusercontent.com/rimone0511/ig-mirror/master/images/<ファイル名>`
2. GO確認メッセージに「ショートカットに `YYYY-MM-DD` と入力すれば一括保存できます」と添える
3. 古い画像の掃除: 月1目安で、投稿済みから1ヶ月超のファイルを削除してよい(履歴には残るが運用上は問題ない)

ショートカットの作り方は claude-general の `design/iPhone画像一括保存.md` を参照。
