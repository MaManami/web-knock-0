# 09. コンフリクトの発生と解消

2つのブランチで同じファイルの同じ行を別々に変更し，マージしてコンフリクトを発生させよ．\
コンフリクトマーカー（<<<<<<<，=======，>>>>>>>）の意味を確認し，手作業で解消してコミットせよ．

---

### 1. コンフリクトの発生
`main` ブランチ（日本語の挨拶）と `feature/morning-en` ブランチ（英語の挨拶）で同じファイル・同じ行を同時に変更し、`git merge` を実行して意図的にコンフリクトを発生させました。

#### コンフリクト発生時の git status の結果
```
Auto-merging practice/greeting.md
CONFLICT (content): Merge conflict in practice/greeting.md
Automatic merge failed; fix conflicts and then commit the result.
```
#### コンフリクト発生時のファイル内容
Gitが自動停止し、衝突箇所にマーカー（`<<<<<<<` / `=======` / `>>>>>>>`）が付与されている状態。

| <<<<<<<| `main` ブランチの変更の始まり|
| =======| 変更の境界線 |
| >>>>>>>| （`feature/morning-en` ブランチ）の変更の終わり |

```
<<<<<<< HEAD
メッセージ: おはようございます!
=======
メッセージ: Good morning!
>>>>>>> feature/morning-en
```

---

### 2. コンフリクトの解消（仲裁）
どちらか一方を消すのではなく、日本語と英語の両方の意図が活きるように「日英併記」の形で手作業でファイルを書き換え、競合を解消しました。

#### 解消後のファイル内容
```
# あいさつ
メッセージ: おはようございます！ / Good morning!
```
---

### 3. マージ・コミット履歴の確認
解消後に `git add` と `git commit` を行い、履歴をきれいに統合した。

#### `git log --graph --oneline` の結果
`dc72950` から2つのブランチに枝分かれし、最後のコミット（`b6a8417`）で1つに美しく合流（マージ）していることが確認できる。
```
[main b6a8417] merge: 朝の挨拶を日英併記でコンフリクト解消
On branch main
Your branch is ahead of 'origin/main' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
*   b6a8417 (HEAD -> main) merge: 朝の挨拶を日英併記でコンフリクト解消
|\  
| * 8fae5b3 (feature/morning-en) feat: 朝の英語の挨拶に変更
* | 0a963bf feat: 朝の日本語の挨拶に変更
|/  
* dc72950 feat: あいさつファイルを追加
*   3b3e873 (origin/main, origin/HEAD) Merge branch 'main' of github.com:MaManami/web-knock-0
|\  
| * 52643f3 Update README.md
| *   f71cdab Resolve merge conflict
| |\  
| | * 6f45d85 Add link for 課題03 in README
| | * 6f32362 Fix README formatting for Git remote URLs
| | * 8a77aa3 Fix formatting of origin URLs in README.md
| | * 2722ccb Create README.md
| | * a71c150 Fix formatting in README.md
| | * d8a013a Remove confirmation section from README
| | * 4058caa Update README.md
| | * ea402e0 Update README.md
| | * 2ee8931 Update README.md
| | * d3243f6 Update README.md
| | * 905fc1b Add verification section to README
:
```
