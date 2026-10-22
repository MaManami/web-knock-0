## web-knock-00
・自分のPCにGitをインストールし，git --versionでバージョンを確認せよ．

git --version
git version 2.50.1 (Apple Git-155)


・git config --global user.name，user.email を設定し，既定ブランチ名を main にする設定（git config --global init.defaultBranch main）も行うこと．
user.email には，GitHubが用意する公開用のアドレス（ID+ユーザー名@users.noreply.github.com．GitHubの「Settings → Emails」で確認できる）を設定すること．コミットに記録したメールアドレスは誰でも見られるため，個人のメールアドレスは使わないこと．

git config --global user.name “Manami Matsumoto”
git config --global user.email "184179951+MaManami@users.noreply.github.com"
git config --global init.defaultBranch main

git config --global --list
user.name=Manami Matsumoto
user.email=184179951+MaManami@users.noreply.github.com
init.defaultbranch=main
