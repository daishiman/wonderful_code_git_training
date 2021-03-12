# wonderful_code_git_training

Git トレーニング

- 名前：2 回目
  - 好きなメソッド：2 回目
- 名前：1 回目
  - 好きなメソッド：1 回目

# コンフリクトの解消手順

### 1. 作業ブランチを作成して作業ブランチに移動する

```rb
$ git checkout -b 作業ブランチ名
# 今回は作業ブランチ名は誰が作成したかわかるように feature/name/task_name で作成して下さい
```

### 2. 作業ブランチに移動していることを確認した上で、README.md を修正する

```rb:README.md
# wonderful_code_git_training
Git トレーニング

- * 名前：
-   * 好きなメソッド：
+ * 名前：daishiman
+   * 好きなメソッド：each
```

### 3. 変更を確認する

```rb
$ git status
On branch feature/name/task_name
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

### 4. 変更したファイルをステージに移動する（add）

```rb
$ git add .
# . は全てのファイルという意味
```

### 5. 変更したファイルをローカルリポジトリ記録する（commit）

```rb
$ git commit -m "メッセージ"
# -m はエディターを立ち上げることなく変更を記録できる
[feature/name/task_name 554a431] メッセージ
 1 file changed, 2 insertions(+), 3 deletions(-)
```

### 6. 変更を確認する

```rb
$ git status
On branch feature/name/task_name
nothing to commit, working tree clean
```

### 7. コミットをリモートリポジトリに push する

```rb
$ git push origin HEAD
# HED:現在のブランチの最新のコミット
```

### 8. **みんなで同時に README.md の同じ箇所を 1 ~ 7 の手順をして push するとコンフリクトが起きる**

```rb:README.md
# wonderful_code_git_training
Git トレーニング

* 名前： 自分の名前
  * 好きなメソッド：　メソッド
```

### 9. Github 上で PR 出すときにコンフリクトしている事に気づく（「Merge pull request」ボタンが押せない）

### 10. ローカル main ブランチに移動

```rb
$ git checkout main
```

### 11. リモートの main ブランチの状態をローカルの main ブランチに引っ張ってくる

**作業ブランチに pull しないこと！**
**リモートリポジトリのデータは main ブランチに pull する**

```rb
$ git pull origin main

# または
$ git featch origin main
$ git merge orgigin/main
```

### 12. 作業ブランチに移動

```rb
$ git checkout 作業ブランチ名
```

### 13. main ブランチを作業ブランチにマージする

```rb
$ git merge main
```

### 14. コンフリクトを解消する

### 15. 再度 add & commit & push

### 16. GitHub 上で「Merge pull request」ボタンが押せることを確認

### 17. コンフリクト解消
