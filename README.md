# Portfolio

My site: https://upura.github.io/
Forked from: https://github.com/sourcethemes/academic-kickstart

## Requirements

- Hugo extended `0.161+`

## Local development

```bash
sh view.sh
```

## How to deploy

`master` に push すると GitHub Actions
([`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)) が Hugo でビルドし、
生成物を [upura/upura.github.io](https://github.com/upura/upura.github.io) に push する。
ローカルでの作業は不要。

- Actions → Deploy から手動実行 (`workflow_dispatch`) も可能
- デプロイには Secret `ACTIONS_DEPLOY_KEY`(`upura.github.io` の write 権限付き deploy key の秘密鍵)が必要
- 公開は追加のみ (`keep_files: true`)。ビルド生成物に対応物がないファイル
  (`pdf/` など) を消したい場合は `upura.github.io` 側で直接削除する
- Hugo のバージョンはワークフローと `netlify.toml` の両方に書かれているので、上げるときは両方を更新する

`deploy.sh` は Actions が使えないときの手動デプロイ用に残してある。実行前に
`git -C public pull` で手元の `public/` を最新にすること(そうしないと Actions の
コミットと衝突する)。

## Caveats

`themes/academic` は submodule ではなくリポジトリに直接取り込んでいる。上流の
[gcushen/hugo-academic](https://github.com/gcushen/hugo-academic) から、
`site.LanguageCode` / `site.Data`(Hugo 0.158 / 0.156 で deprecated)を置き換える
独自パッチを当てた状態。上流の更新を取り込む場合は手動でマージする。
