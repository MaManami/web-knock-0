# web-knock-00
## 自分のPCにGitをインストールし，git --versionでバージョンを確認せよ．

以下のコマンドを実行
> git --version
出力結果
> git version 2.50.1 (Apple Git-155)


## git config --global user.name，user.email を設定し，既定ブランチ名を main にする設定（git config --global init.defaultBranch main）も行うこと．

以下のコマンドを用いて設定
> git config --global user.name “Manami Matsumoto”\
> git config --global user.email "184179951+MaManami@users.noreply.github.com"\
> git config --global init.defaultBranch main

コマンドを使って設定されているか確認
> git config --global --list\
出力結果
> user.name=Manami Matsumoto\
> user.email=184179951+MaManami@users.noreply.github.com\
> init.defaultbranch=main\
