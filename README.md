# pull_requestの練習リポジトリ
ほげほげ

## pushの流れ

## pullの流れ
1. リモートリポジトリをローカルより育てる
2. `git pull origin master`コマンドでリモート上の最新リポジトリをローカルに持ってくる

## Pull Requestの流れ
1. `git checkout -b ブランチ名`コマンドで新規ブランチを作成（同時にブランチの切り替えも行ってくれる）
2. 何かしらのアップデートをする
3. `git add .`,`git commit -m "コメント"`ノ順で保存する
4. `git push prigin 新しいブランチ名`コマンドでリモーー途上に新しくブランチ作成してpush
5. Github上でpull requestを送る
6. 管理者がrequestをレビューする
7. 問題があれば差し戻す（コメントを自由につけられる）
8. 再度問題を修正し、`add`,`commit`,`push`で修正内容をpull reqに上乗せして送る
    +pull req中に同じブランチに修正内容pushすると、それだけで修正内容がpull reqにのっかる
9. 修正内容を確認し、margeする
10. ブランチを削除する   

### ブランチの切り替え方
+ `git checkout ブランチ名` コマンドでブランチを行き来できる
  +現在いるブランチ上で何かしらの変更を行っていた場合はその変更内容を保存もしくは削除してからブランチを移動すること

### commitコメントの修正
+`git commit --amend -m "新規コメント"`コマンドで編集可能

###指定したコミットまでコードを遡る方法
1. Github上（もしくはlog上）でコミットのハッシュをコピー
2. `git checkout ハッシュ`コマンドで指定したコミットまで戻る
3. `git checkout ブランチ名`コマンドで最新のコミットに戻る

### 別ブランチのコミットをmasterブランチへ追加する方法
1. 別ブランチでの変更をcommitしきる
2. `git log --oneline`でコミットのハッシュを見る
3. `git checkout master`でmasterブランチへ移動
4. `git cherry-pick ハッシュ`で別ブランチのコミットをmasterへ追加

###ローカルブランチの削除
+`git branch -d ブランチ名`
+もし`git branch -D ブランチ名` is not fully merged.`がでれば、
  +`git branch -D ブランチ名`で強制削除も可能
