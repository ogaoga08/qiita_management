---
title: git-dev_attention
tags:
  - VSCode
  - devcontainer
	- git
	- GitHub
	- 初心者
private: false
updated_at: ""
id: null
organization_url_name: null
slide: false
---
<!-- # Dev Containerでのgit操作の注意点 -->

# 概要
先日参加した技育CAMP_ハッカソンで初めてDev Containerを使用した際にGitの操作が上手くいかないことがあったので、行った対処法をここに残しておこうと思います！  
※もしかしたら超初歩的なミスかもしれませんが、検索しても出てきませんでした汗

## 今回起こった問題
・GitHubのリモートリポジトリからクローンしたローカルのリポジトリで、Dev Containerを立ち上げてVSCodeのターミナル上でGit操作をすると、Gitリポジトリがない(fatal: not a git repository)と言われる

## 解決方法
**Dev Containerを開いている間はgitの操作をしない。閉じてからcommitなりpushする。**  
です。以下にその理由を説明します。

## 原因
おそらく原因はDev Containerで開いているファイル(workspace)と.devcontainerファイル、.gitファイルが同階層にあるため、Dev Containerで開いているworkspace以下に.gitファイルが存在しないことからgit操作がうまく出来ないからだと考えられます。  
(起動中はVSCode上のソース管理タブでは**リポジトリを初期化**ボタンが出てきてしまう)  
  
なのでDev Containerで開いている間はGitの操作はせず、閉じてからcommitなりpushなりを行うことをお勧めします。