# 課題 5 - 実績を評価する

## 背景

アプリケーションでイベントが発生すると、開発者はさまざまな場所や方法で対応する必要があります。Azure Event Grid では、インテリジェントなイベント ルーティング サービスにより、パブリッシュ/サブスクライブ方式でイベントを画一的に配信することができます。課題 5 では、Event Grid のトピックを構築し、複数のサブスクリプションを作成します。

ボットでの会話は通常ユーザー側が開始します。これが一般的なボットの使用方法です。しかし、まったく新しい会話をボット側で開始し、プロアクティブにメッセージを送信することもあります。今回は、このボット開発における一般的なシナリオを、Event Grid サブスクリプションで実行します。

また、この課題では Microsoft Graph を使用してユーザー プロファイルを更新します。Microsoft Graph で取得できるデータは、ファーストパーティのデータに限りません。拡張機能によって、サードパーティのデータに拡張することもできます。この課題では、オープン拡張機能を使用して、クイズ アプリの優秀な成績者にバッジを授与します。

## 課題

ボットがユーザーに実績バッジを返す [Submit Answer (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_SubmitAnswer) API を呼び出します。ユーザーが実績バッジを新たに獲得したら、Azure Event Grid トピックを作成してデータを送信します。Azure Functions で Event Grid トピックにサブスクリプションを作成します。このサブスクリプションは、Microsoft Teams の **Event Referee** にプロアクティブにメッセージを送信し、実績を通知します。Event Referee は既に OpenHack の他の課題で追加されているため、プロアクティブにメッセージを送信するユーザーの詳細は名簿情報から取得することができます (メッセージは自由にハードコード可能)。Event Grid トピックに 2 つ目のサブスクリプションを作成します。これにより、ユーザーが実績バッジを新たに獲得する際に Microsoft Graph のユーザー プロファイルを更新します。実績バッジは、"**com.msopenhack.trivia**" という extensionName を使用して、オープン拡張機能の "**badge**" プロパティに格納します。

注: ここでは、エンドユーザーのボット エクスペリエンスの速度低下を回避するため、Event Grid を使用してボットの会話ロジックから高負荷な処理を分離します。

## 成功条件

- ユーザーが実績バッジを新たに獲得する際に、ボットが OpenHack 管理者にプロアクティブにメッセージを送信する。

- Azure Event Grid トピックのサブスクリプションからメッセージをプロアクティブに送信する。

- ユーザーが実績バッジを新たに獲得したら、**com.msopenhack.trivia** という extensionName と **badge** というプロパティを使用してその値をオープン拡張機能に格納する。

## 注意事項

- ランキング ボードと同様に、このプロセスでは Microsoft Graph に対する操作を実行するトークンが必要です。ユーザーのオープン拡張機能を作成および更新する場合、代理管理権限として User.ReadWrite が必要です。

## 参考資料

- [カスタム イベントを作成して Azure Event Grid にルーティングする](https://docs.microsoft.com/ja-jp/azure/event-grid/custom-event-quickstart)

- [Azure Functions 入門ガイド](https://docs.microsoft.com/ja-jp/azure/azure-functions/functions-overview)

- [Microsoft Teams のボットで会話を作成する](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/bots/bots-conversations#creating-a-conversation)

- [オープン拡張機能を使用して Microsoft Graph にカスタム データを追加する](https://developer.microsoft.com/ja-jp/graph/docs/concepts/extensibility_open_users)

- [Bot Framework の OAuth 用 BotAuth パッケージ (英語)](https://github.com/MicrosoftDX/botauth)

- [Microsoft Teams のボット用認証フロー (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/authentication/auth-flow-bot)

- [Azure Botサービス経由でボットに認証を追加する](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-tutorial-authentication?view=azure-bot-service-3.0）