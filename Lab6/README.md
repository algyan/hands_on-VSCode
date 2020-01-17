# Lab 6. Extensionの開発体験
ここでは、最もシンプルなVS Codeの拡張機能の開発をしてみましょう。この拡張機能を実行すると指定した文字がVS Codeの通知として表示されます。
>**[Note]** [VS Code - Your First Extension](https://code.visualstudio.com/api/get-started/your-first-extension) サイトで手順と動画を確認できます。

## 1. 拡張機能の開発を使うための準備
1. 使用するプログラミング言語は次の通りです。
* TypeScript
* JavaScript
2. 拡張機能の開発には次をインストールしている環境が必要です。
* [Node.js](https://nodejs.org/ja/)
* [Git](https://git-scm.com/)

## 2. はじめての拡張機能の開発
1. ターミナルで作業ディレクトリを作成します。下記はVSCodeExtensionフォルダを作成する場合の例です。
```
mkdir VSCodeExtension
```
2. 次のコマンドを使ってYeomanジェネレータとVS Code Extension Generatorをインストールします。
```
npm install -g yo generator-code
```
3. 次のyoコマンドを実行してYeomanを起動します。
```
yo code
```
4. Yeomanが表示された後は次のとおり質問に対応します。
* What type of extension do you want to create? New Extension (TypeScript)
* What's the name of your extension? → HelloWorld
* What's the identifier of your extension? → helloworld
* What's the description of your extension? →空欄のままでOK
* Initialize a git repository? → Yes
* Which package manager to use? → npm
5. `helloworld` フォルダに移動します。
```
cd helloworld
```
6. VS Codeを起動します。
```
code .
```
7. F5を押し、デバッグ実行します。作成した拡張機能がビルドされ[拡張機能開発ホスト]と書かれたVS Codeが起動します。
8. コマンドパレットに`hello`と入力し、**Hello World**を選択します。
9. 画面右下に「Hello World!」トースターが表示されます。
10. F5でデバッグ状態を停止します。

## 3. 拡張機能のカスタマイズ
1. srcフォルダ内に格納されているextension.tsファイルを開きます。
2. 20行目のvscode.window.showInformationMessageの後に書かれているHello World!の文字を変更して、ファイルを保存します。
3. VS Codeをリロードします。
4. F5を押し、デバッグ実行します。
5. 先ほどと同様に、[拡張機能開発ホスト]のVS Code上でコマンドパレットから拡張機能を実行します。
6. 変更した文字列が表示されたら成功です。

## 拡張機能のデバッグ
1. extension.tsファイルの20行目の行番号の左にカーソルをホバーし、赤い丸が表示されたら押します。これがブレイクポイントです。
2. アクティブバーに表示されている **[デバッグと実行]** アイコンをクリックします。
3. F5を押し、デバッグ実行します。
4. ブレイクポイントで止まります。

## 4. 拡張機能について解説
### Hello World拡張機能の動き
これら3つの概念を理解することは、VS Codeで拡張機能を作成するために重要です。
*  `onCommand` [Activation Events](https://code.visualstudio.com/api/references/activation-events)：package.jsonファイルの12行目を確認してみます。`onCommand：extension.helloWorld` を定義します。これにより、ユーザーが **Hello World** コマンドを実行すると拡張機能がアクティブになります。
* `Contributors.commands` 16行目 [Contribution Point](https://code.visualstudio.com/api/references/contribution-points)を使用して、コマンドパレットでコマンド`Hello World`を使用可能にし、コマンドID `extension.helloWorld`にバインドします。
* `commands.registerCommand` extension.tsファイルの16行目を確認してみます。 [VS Code API](https://code.visualstudio.com/api/references/vscode-api)を使用して、登録されたコマンドID `extension.helloWorld`にバインドします。

### フォルダの構成
ファイルの中身を理解しておきましょう。
```
.
├── .vscode
│   ├── launch.json     // 拡張機能の起動およびデバッグ用ファイル
│   └── tasks.json      // TypeScriptをコンパイルするビルドタスク設定ファイル
├── .gitignore          // 無視するファイル
├── README.md           // 拡張機能の説明
├── src
│   └── extension.ts    // 拡張機能のソースコード
├── package.json        // 拡張機能のマニュフェストファイル
├── tsconfig.json       // TypeScript設定ファイル
```

## 5. ほかにも公開されている拡張機能サンプル
この拡張機能以外にもMicrosoftのGitHubリポジトリに様々なサンプルの拡張機能が公開されています。試してみましょう。
https://github.com/microsoft/vscode-extension-samples