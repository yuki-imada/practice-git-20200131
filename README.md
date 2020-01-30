# practice-git

これはgit練習用リポジトリの雛形です。

## 事前準備

* 受講者側
  * GitHubアカウントの開設
  * Visual Studio Codeのインストール
    * 拡張機能「Git Graph」のインストール

* 講師側
  * 勉強会用リポジトリの用意
    * 受講者側がpushできるよう設定変更
      * githubのリポジトリのページ -> Setteings -> Collaborators
        * 受講者のGitHubアカウントの追加

## 練習内容

1. GitHubのメール設定
    * [https://github.com/settings/emails](https://github.com/settings/emails)にアクセス
      * 「Keep my email addresses private」にチェックを入れる
      * 「99999999+xxxxxxxx@users.noreply.github.com」という
        個人用のダミーメールアドレスが発行されているため、この文字列をコピーしておく
    * 以下のコマンドを実行する
      * `git config user.email 99999999+xxxxxxxx@users.noreply.github.com`
        * メールアドレスの部分は先程コピーした個人のメールアドレスを使用

1. リポジトリのクローン - clone
    * リモートリポジトリからローカルリポジトリの作成

1. ブランチの作成 - branch, checkout
    * 各自の作業ブランチの作成

1. コードのコミット - add, commit
    * masterブランチで行わないよう注意

1. ブランチの切り替え - branch, checkout
    * ブランチを切り替えると実際のファイルが変更されることを確認

1. コードのプッシュ - push
    * GitHub上にブランチが増えていることを確認

1. プッシュの失敗 - push
    * 別コミットが作成されているブランチにpushし、失敗することを確認

1. コードのプル - pull
    * historyに他人のブランチが表示されていることを確認

1. プルリクエストの送信 - pull requset
    * 各自の作業ブランチのmasterブランチへの取り込み依頼

## コマンドサンプル

### ブランチ操作

* ブランチの確認
  * `git branch -a`
  * `-a`でリモートリポジトリのブランチも表示する

* ブランチの作成
  * `git checkout -b branch_name`

* ブランチの削除
  * `git branch -d branch_name`

* ブランチの切り替え
  * `git checkout master`
  * `git checkout branch_name`

### コミット操作

* コードのコミット
  * まずは作業ツリーからindexへの追加
    * `git add .`
  * コミットの登録(コメント必須)
    * `git commit -m 'add your comment'`


* コードのプル
  * `git pull`

### プッシュ操作

* コードのプッシュ
  * `git push origin master`
    * originの部分が対象のリモートリポジトリ名、masterの部分が対象のブランチ名
    * カレントブランチをpushする

* コードの強制プッシュ
  * `git push -f origin master`
  * push先の分岐以降のコミットは失われる

* リモートリポジトリの別ブランチにpush
 * `git push origin from-branch:to-branch`

### 設定操作

* user情報の確認
  * `git config user.name`
  * `git config user.email`

* user情報の更新
  * `git config user.name new_name`
  * `git config user.email new_email`
