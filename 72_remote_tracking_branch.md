# ローカルブランチ、リモート追跡ブランチ、リモートブランチ

| 用語 | ざっくりとした意味 |
| ---- | ---- |
| ローカルブランチ | 端末の .git ディレクトリ内にある、コマンド操作等の方法で操作するブランチ。 |
| リモート追跡ブランチ<br>remote tracking branch | 端末の .git ディレクトリ内にある、直接操作することのないブランチ。<br>リモートリポジトリにあるブランチの状態を追跡している。 |
| リモートブランチ | リモートリポジトリにあるブランチのこと。 |

ローカル端末のリポジトリがリモートリポジトリと関連づけられると、.git ディレクトリ内に、「リモート追跡ブランチ」という隠れたブランチができます。  
リモート追跡ブランチは、リモートリポジトリにあるブランチの状態を追跡(tracking)するためのものです。

リモート追跡ブランチは、直接編集されることはありません。  
リモートリポジトリにあるブランチの状態の追跡は、 `git fetch` コマンドによって行われます。  
`git fetch` コマンドは、リモートリポジトリから最新のコミット履歴を取得し、リモート追跡ブランチの内容を更新します。

ローカル端末でコマンド操作や Pycharm 等の IDE の操作で更新される git のリポジトリは、リモート追跡ブランチと `git merge`  コマンドによって統合されます。(補足1)

リモートリポジトリの内容を更新するには、 `git push` コマンドを使います。(補足2)  

***

以下は、補足情報です。  
あとで改めて解説しますが、今の段階でいちおう触れておきます。

- `git fetch` と `git merge` を分けて行うことは基本的にありません。  
      `git pull` コマンドを使う場合がほとんどです。
- `git push` コマンドは、ローカル端末のリポジトリがリモートリポジトリと同期された状態でないと実行できません。  
    `git push` が拒絶された場合は、いったん `git pull` を行い、それから再度 `git push` コマンドを実行します。
