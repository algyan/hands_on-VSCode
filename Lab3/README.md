# Lab 3. ソースコントロールの使用
ここではオープンソースのバージョン管理システムであるgitを使用してみます。

## 1. gitの確認
1. 手元の環境にgitインストールされているか確認するためコマンドラインまたはターミナルを開き、gitコマンドを実行します。
```
git --version
```
2. gitのバージョン情報が表示されない場合にはgitがインストールされていない可能性があります。
3. [git 公式サイト](https://git-scm.com/)よりインストールします。
4. gitを利用するために、下記のコマンドを実行してユーザー名とメールアドレスを登録します。
* ユーザー名の登録
```
git config --global user.name “名前”
```
* 登録されたかユーザー名の確認方法
```
git config --global user.name
```
* メールアドレスの登録
```
git config --global user.email “メール・アドレス”
```
*登録したメールアドレスの確認方法
```
git config --global user.email
```

## 2. git コマンドの操作
1. Gitリポジトリを初期化します。**ソース管理**アイコンをクリックします。
2. [Gitリポジトリを初期化するワークスペースフォルダを選択してください]のメッセージにしたがってフォルダを選択します。
3. ファイル名の横のアルファベットを確認します。
* U 新しいファイル
* M 変更を加えたファイル
* D 削除したファイル
4. [変更]にカーソルを合わせ＋アイコンをクリックして一括でインデックスに追加します。
5. メッセージボックスにコミットするためのメッセージを入力します。
6. 上のチェックアイコンをクリックします。
7. ローカルリポジトリにコミット完了し、ソース管理アイコンの横に表示されていた数字が消えます。

> **[Note]** 2020年1月18日現在のダウンロード数 Top5  
> 拡張機能の[その他の操作]アイコンより表示を変更できます。Markdownのランキングを表示したい場合は `@sort:installs git` を入力して検索します。  
>1位 [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)  
>2位 [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)  
>3位 [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)  



