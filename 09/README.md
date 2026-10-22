# 09. コンフリクトの発生と解消

2つのブランチで同じファイルの同じ行を別々に変更し，マージしてコンフリクトを発生させよ．\
コンフリクトマーカー（<<<<<<<，=======，>>>>>>>）の意味を確認し，手作業で解消してコミットせよ．

### コンフリクト発生時の git status の結果
> Auto-merging practice/greeting.md\
> CONFLICT (content): Merge conflict in practice/greeting.md\
> Automatic merge failed; fix conflicts and then commit the result.\

### コンフリクト発生時のファイル内容
> <<<<<<< HEAD\
> メッセージ: おはようございます、日本\
> =======\
> メッセージ: Good morning, Japan!\
> >>>>>>> feature/morning-en\
