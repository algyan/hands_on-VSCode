# Lab 2. 文書ファイルを取り扱う

## 1. ファイル作成
1. VS Codeを起動します。
2. ファイルを新規作成します。
3. 画面右下のステータスバーの `プレーンテキスト` をクリックします。
4. `言語モードの選択` より `Markdown` を選択します。
5. ステータスバーに表示されていた[プレーンテキスト]
が[Markdown]に変わります。

## 2. Markdown形式でファイルを編集
1. Markdown形式で何か入力してみます。初めての人はサンプルをみながら入力してみます。
```
# VS Codeハンズオン体験

## 今日の学ぶこと
1. VS Codeの概要 
2. VS Codeの設定方法
3. Markdownの操作

* 懇親会あり

![](https://imgur.com/ZnIIQOn.png)
```
2. ファイルを保存します。
3. VS Codeの右上の虫眼鏡がついたアイコンをクリックします。
4. プレビューが表示されます。
5. そのまま追加で文字を編集してみます。
6. リアルタイムに左側で編集した内容が右側のプレビューで反映して表示されます。

>**[Note]** デモでは画像アップロードする場所として **[imgur](https://imgur.com/)** を使用しました。サイトへアクセスし、[New post]ボタンから自分の画像ファイルをアップロードすることが可能です。ファイルをアップロードした後は、[Copy link]ボタンまたは[Get share link]からURLを入手できます。

## 3. スニペット (Markdown)
VS Codeではスニペット対応しています。
下記を順番に入力して、スニペットによりコードが挿入されることを確認してみてください。
* `bold`: Insert bold text (太字)
* `link`: Insert link (リンク)
* `image`: Insert image (画像)

## 4. 独自スニペットの作成
ここではMarkdownで議事録を作成するためのスニペットを作成してみます。
1. `[Code] →［基本機能］→［ユーザースニペット］`をクリックします。
2. **Markdown.json** を選択します。
3. ファイル内容がエディタに表示されます。内容を下記のように編集し、保存します。
```
{
	"Print to console": {
		"prefix": "log",
		"body": [
			"console.log('$1');",
			"$2"
		],
		"description": "Log output to console"
	},

		"Meeting Minutes":{
			"prefix": "meeting",
				"body": [
				  "# 会議名",
				  "",
				  "## 日時・場所・出席者",
				  "",
				  "日時: $CURRENT_YEAR 年 $CURRENT_MONTH_NAME $CURRENT_DATE 日   ",
				  "場所: 会議室  ",
				  "出席者:  ",
				  "",
				  "## アジェンダ",
				  "",
				  "1. xxx",
				  "2. xxx",
				  "3. xxx",
				  "",
				  "## 議事内容",
				  "",
				  "1. xxx",
				  "2. xxx",
				  "3. xxx",
				  "",
				  "## 決定事項",
				  "",
				  "* [決定事項 1]  ",
				  "* [決定事項 2]  ",
				  "* [TODO]   (担当:   、期日:MM/DD)"
				],
			"description": "meeting munutes"
			}
}
```
4. 設定ファイル(Settings.json)に下記を追加し、ファイルを保存します。これで
```
"[markdown]": {
"editor.quickSuggestions": true
}
```
5. Markdownファイル上で`meeting`と入力します。
6. meetingのスニペットが表示され、それをクリックすると登録しておいた内容を即座に呼び出すことができます。自由にカスタマイズしてみましょう。

## 5. 拡張機能 (Markdown)
1. VS Codeの`Extension`アイコンをクリックします。
2. ボックスに`Markdown`と入力します。
3. Markdown向け拡張機能が表示されます。
4. `Markdown PDF`をインストールします。
5. コマンドパレットを呼び出します。
6. ボックスに`pdf`と入力します。
7. Markdown PDF拡張機能のメニューが表示されます。好みのファイル形式を選択します。
8. 同じフォルダ内に指定したファイル形式でMarkdownで記述したファイルが保存されていれば成功です！

他にも好みの拡張機能を見つけてインストールして操作を試してみましょう。

> **[Note]** 2020年1月17日現在のダウンロード数 Top5  
> 拡張機能の[その他の操作]アイコンより表示を変更できます。Markdownのランキングを表示したい場合は `@sort:installs markdown` を入力して検索します。  
>1位 [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)  
>2位 [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)  
>3位 [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)  
>4位 [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)  
>5位 [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) 


