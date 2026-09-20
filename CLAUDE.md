# zenn_docs

[Zenn](https://zenn.dev/)で公開する記事を管理するリポジトリ。記事は`articles/`、本は`books/`に置く。

## 記事を修正したらtextlintを実行する

`articles/`配下のファイルを新規作成・修正したら、必ず次を実行する。

```bash
npm run lint
```

中身は`textlint --fix articles/.`で、[textlint-rule-preset-smarthr](https://github.com/kufu/textlint-rule-preset-smarthr)のルールが適用される。

`--fix`が付いているため、自動修正できる指摘はファイルが直接書き換わる。実行後は`git diff`で書き換わった内容を確認し、意図と違う修正が入っていないか確かめる。自動修正できない指摘は標準出力に残るので、手で直す。

## 記事のfrontmatter

```yaml
---
title: "記事タイトル"
emoji: "📝"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["AWS", "Terraform"]
published: false
---
```

- `topics`は5つまで
- 執筆中は`published: false`にしておく
- 公開日を指定する場合は`published_at: "2023-12-07"`を追加する

## 記事の文体

既存記事（`articles/`）に合わせる。一人称で、実際に手を動かして分かったことを書く検証メモ調。見出しは`#`から始め、「〜は〜になる」のように結論を含む形にする。

時点によって挙動が変わる話題は、冒頭に注記を置く。

```markdown
:::message alert
2024年7月末時点の検証メモなので、時間が経つと挙動が変わっているかもしれないのでご注意ください
:::
```

## プレビュー

```bash
npx zenn preview
```
