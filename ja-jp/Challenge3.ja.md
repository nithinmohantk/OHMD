# 課題 3 - クイズ ボット

## 背景

クイズ アプリの主なロジックは、Microsoft Teams のボットが司っています。これは、ソフトウェア企業や学習管理企業で非常に人気のある、ゲーム感覚で行うことができる評価/クイズ ボットです。

課題 3 では、Microsoft Teams 用のクイズ ボットを構築します。この課題では、チーム名簿情報の取得や初回実行時の使いやすいエクスペリエンスなど、Microsoft Teams ボットの一般的な開発パターンやベスト プラクティスを理解します。

## 課題

ボットを使用してクイズを出題する Microsoft Teams のクイズ アプリを作成します。チームにアプリをインストールすると、アプリがチーム名簿を取得して [Register Team (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_RegisterTeam) API (OpenHack API のドキュメントを参照) に POST します。

クイズ アプリのロジックでは、ボットが [Get Trivia Question (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_GetQuestion) API でクイズを取得し、[Submit Answer (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_SubmitAnswer) API (OpenHack API のドキュメントを参照) を使用して回答を送信します。最終的に、チーム メンバー全員が個別にクイズに回答できるようにします。1 対 1 のチャットかチームの会話で回答します (この両方を実装してもかまいません)。

## 成功条件

- 選択形式で回答する Microsoft Teams クイズ ボットを作成する。

- チーム メンバーが個別にクイズに回答できるようにする。

- クイズ アプリがインストールされているチームの名簿情報を取得し、用意された RegisterTeam API にその名簿を送信する。

## 注意事項

- ローカルでボット ダイアログの基本デバッグを行う場合は、[Bot Framework Emulator (英語)](https://github.com/Microsoft/BotFramework-Emulator/releases) を使用すると便利です。しかし、Microsoft Teams のコンテキストは Microsoft Teams で実行されているボットでしか得られません。Microsoft Teams のボットをデバッグする場合は、ボットのエンドポイントがパブリック インターネットに存在していなければなりません。ローカル ホストからインターネットへのトンネルを作成する場合は、[ngrok (英語)](https://msopenhack.azurewebsites.net/Home/Ngrok) を使用すると便利です。チーム登録時に、ngrok の authkey と予約済みサブドメインが割り当てられます (OpenHack ボットから IM を送信)。詳しい手順は [ngrok 入門ガイド (英語)](https://msopenhack.azurewebsites.net/Home/Ngrok) をご覧ください。**この課題では必ず ngrok を使用してください。**

- OpenHack API は、Microsoft Teams に登録されているチームのコンテキストでのみ動作します。これらの API は、Swagger ドキュメント、または [Postman (英語)](https://www.getpostman.com/) や [Fiddler (英語)](https://www.telerik.com/fiddler) などのツールでテストできます。この場合、チームの詳細情報 (Teams の ID と Azure AD のオブジェクト ID) が必要です。

## 参考資料

- [OpenHack API のドキュメント (英語)](https://aka.ms/msopenhackapi)

- [Microsoft Teams 用ボットを作成する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/bots/bots-create)

- [Microsoft Teams でボットのイベントを処理する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/bots/bots-notifications#team-member-or-bot-addition)

- [Microsoft Teams 用ボットのコンテキストを取得する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/bots/bots-context)

- [.NET 用 BotBuilder のダイアログ (英語)](https://docs.microsoft.com/ja-jp/azure/bot-service/dotnet/bot-builder-dotnet-dialogs)

- [Node.js 用 BotBuilder のダイアログ (英語)](https://docs.microsoft.com/ja-jp/azure/bot-service/nodejs/bot-builder-nodejs-dialog-prompt)

その他の参照情報

- [Microsoft Teams で ngrok を使用してローカルでボットのデバッグを行う (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/resources/general/debug#locally-hosted)

- [Microsoft Teams アプリ用 Yeoman Generator (英語)](https://github.com/OfficeDev/generator-teams)

- [Teams App Studio でアプリをすばやく開発する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/get-started/get-started-app-studio)

- [Bot Framework クイックスタート ガイド (.NET 向け、英語)](https://docs.microsoft.com/ja-jp/bot-framework/dotnet/bot-builder-dotnet-quickstart)

- [Bot Framework クイックスタート ガイド (Node.js 向け、英語)](https://docs.microsoft.com/ja-jp/bot-framework/nodejs/bot-builder-nodejs-quickstart)

- [Bot Framework - 会話フローの設計と制御 (英語)](https://docs.microsoft.com/ja-jp/bot-framework/bot-service-design-conversation-flow)