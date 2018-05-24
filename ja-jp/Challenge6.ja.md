# 課題 6 - メッセージング拡張機能

## 背景

Microsoft Teams では、メッセージング拡張機能を使用することで、サードパーティのデータやレコードを検索してすばやく会話にプルし、重要な情報を利用することができます。これにより、情報やリンクを会話にコピー アンド ペーストする時間を節約することができます。課題 6 では、Microsoft Teams 用のメッセージング拡張機能を作成します。

## 課題

プレーヤーの検索や会話用の「プレーヤー カード」をレンダリングするメッセージング拡張機能を Microsoft Teams アプリに追加します。このカードには、プレーヤー名、スコア、実績バッジ、プロファイル写真を含めます。カードの写真は、ユーザーのプロファイル写真に実績バッジを重ねて表示します。このレンダリングは、Azure Function で構築することをお勧めします。[Search Trivia (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_Search) API (OpenHack API のドキュメントを参照) を使用してプレーヤーを検索します。検索した「プレーヤー カード」を OpenHack ボットに送信し、課題を解決できたことを確認します。

## 成功条件

- アプリケーションで Search API を呼び出してプレーヤーの情報を検索し、メッセージング拡張機能で表示する。

- メッセージング拡張機能の情報にプレーヤー名、スコア、実績バッジ、プロファイル写真が含まれている。

- カードの写真は、プロファイル写真に実績バッジが重なっている ([例 (英語)](https://msopenhack.azurewebsites.net/content/msgext.png))。

- 作成したメッセージング拡張機能を使用して OpenHack ボットに「プレーヤー カード」を送信する。

## 参考資料

- [OpenHack API のドキュメント (英語)](https://aka.ms/msopenhackapi)

- [Microsoft Teams 用メッセージング拡張機能を作成する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/messaging-extensions)

- [Microsoft Teams のカードと操作](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/bots/bots-cards)

- [1 つの HTTP 呼び出しで複数の Microsoft Graph 要求を統合する](https://developer.microsoft.com/ja-jp/graph/docs/concepts/json_batching)