# gh-label-completion

Bash で [GitHub CLI] を利用しているとき、ラベルの入力補完をするためのスクリプト。

![入力補完のデモ表示しているスクリーンショットの agif](https://github.com/hankei6km/gh-label-completion/blob/master/docs/gh-label-completion.gif?raw=true)

## Install

Bash の入力補完用ファイルを保存するディレクトリーへ `gh-label-completion` をコピー。

## Usage

以下のフラグ用にラベルを入力するとき、タブを押下すると補完される。

### [`gh pr create`]

- `-l`, `--label` - リポジトリのラベル一覧を候補にする

### [`gh pr edit`]

- `--add-label` - リポジトリのラベル一覧を候補にする
- `--remove-label` - PR に設定されているラベル一覧を候補にする


### [`gh issue create`]

- `-l`, `--label` - リポジトリのラベル一覧を候補にする

### [`gh issue edit`]

- `--add-label` - リポジトリのラベル一覧を候補にする
- `--remove-label` - ISSUE に設定されているラベル一覧を候補にする

## Known Issue

- タブ押下時に毎回 GitHub へ一覧を取得しにいく
- `-R`, `--repo` の `HOST/` ありの形式に対応していない(`--remove-label` では対応)
- エラーメッセージを抑止していない
- `--add-label` の候補一覧から設定済ラベルを除外していない
- ラベル数が多いとすべてを表示しない(ページネーションをしていないので)
- カンマ区切りの指定に対応していない
    `--add-label enhancement --add-label documentation` のように指定する

## License

MIT License

Copyright (c) 2022 hankei6km

[GitHub CLI]: https://cli.github.com/
[`gh issue create`]: https://cli.github.com/manual/gh_issue_create
[`gh issue edit`]: https://cli.github.com/manual/gh_issue_edit
[`gh pr create`]: https://cli.github.com/manual/gh_pr_create
[`gh pr edit`]: https://cli.github.com/manual/gh_pr_edit

