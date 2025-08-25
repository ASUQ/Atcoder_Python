# AtCoder Python Dev Container

このリポジトリは AtCoder用の競技プログラミング開発環境を VS Code Dev Containerを用いて整備したものです。

## 環境
- [Python 3.13 (slim)](https://hub.docker.com/layers/library/python/3.13-slim/images/sha256-cd4cb2ba193c13d36b59f01c9518d709b41b886388c3af2bbe7d7b29f15a303f)
- [online-judge-tools (oj)](https://pypi.org/project/online-judge-tools/)
- [Jupyter](https://pypi.org/project/jupyter/)
- [Selenium](https://pypi.org/project/selenium/)
 (oj実行時の警告を抑制するため)

## 🚀 セットアップ

1. 必要なツールのインストール

	- [Git](https://git-scm.com/)
	- [Docker](https://docs.docker.com/get-started/get-docker/)
		- Windows/macOS → Docker Desktop をインストール
		- Linux → install Docker engine をインストール
	- [Visual Studio Code (VS Code)](https://code.visualstudio.com/)
	- Dev Containers extension for VS Code ([See tutorial](https://code.visualstudio.com/docs/devcontainers/containers))

2. このリポジトリをフォーク
	- GitHub 上でこのリポジトリを開く
	- Fork をクリックして、自分のアカウントにコピーを作成

3. フォークしたリポジトリをクローン
ターミナルで以下を実行します（`<your-github-username>` は自分の GitHub ユーザー名に置き換えてください）：
	```bash
	git clone https://github.com/<your-github-username>/Atcoder_Python.git
	cd Atcoder_Python
	```

4. VS Code で開く
	1.  VS Code でフォルダを開く
	2.  「Reopen in Container」（またはコマンドパレットから Dev Containers: Reopen in Container）を実行

	実行後、 VS Code が以下を自動で行います：
	- `.devcontainer/Dockerfile` からイメージをビルド
	- プロジェクトを `/workspaces/<repo>` にマウント
	- `Python` / `online-judge-tools` / `Jupyter` / `Selenium` をインストール


> [!WARNING]
work/ フォルダについて
> - リポジトリには work/ フォルダが含まれています。
> - ここに 自分のコンテスト用コードやノートブック を保存してください
> - 利用を開始する前に、既存の work/ フォルダの内容を削除してください。(中身は私のサンプルコードです)


## ✅ 使い方
Python スクリプトを実行:
`python main.py`

online-judge-toolsの使い方は以下のリンクを参照してください：https://github.com/online-judge-tools/oj

問題をダウンロード:

`oj download https://atcoder.jp/contests/abc999/tasks/abc999_a`

ローカルテストを実行:
`oj test`

JupyterLab を起動（ポート 8888 が転送されます）:

`jupyter lab --ip=0.0.0.0 --no-browser --NotebookApp.token=''`

## 🐳 その他
- 必ず フォーク → 自分のフォークをクローン → 自分のコードをプッシュ の流れで利用してください
- Windows、macOS（Intel / Apple Silicon）、Linux のすべてで動作します
