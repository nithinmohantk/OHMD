# 課題 2 - チームの通知

## 背景

OpenHack を通じて、チームで選択形式の (雑学) クイズ アプリを構築 (およびプレイ) します。このアプリは既に各チームに関連付けられており、最終的に Microsoft Teams でホストします。課題 2 では、サードパーティ アプリケーション (今回は SharePoint を使用) に新しいクイズの問題が追加されるタイミングで Microsoft Teams に通知するプロセスを構築します。

Microsoft Teams 宛ての通知はよくある開発シナリオであり、実装方法もさまざまです。Microsoft Graph、Microsoft Flow、Azure Logic Apps では、ユーザーとして Microsoft Teams にメッセージを送信することができます。アプリケーションとしてメッセージを送信する場合は、Microsoft Teams でボットまたはコネクタを使用する必要があります。Microsoft Teams では、簡単な構成で使用できる一般的な「受信 Webhook」コネクタも使用できます。どの方法で課題を解決してもかまいません。

## 課題

SharePoint でクイズのリストを監視し、新しいクイズの追加時に Microsoft Teams に通知します。自分が担当したカテゴリのクイズの通知のみが、自分のチームだけに送信されるようにします (**{0}**)。通知はリッチ カード形式で、クイズのタイトルとカテゴリを含みます。テスト用に、新しい問題が 1 分ごとに追加されます (課題が完了するとクイズの追加は停止します)。

[SharePoint のクイズ リスト](https://{1}.sharepoint.com/Lists/Trivia%20Questions)

## 成功条件

- SharePoint のクイズ リストに新規項目が追加されたときに Microsoft Teams のチームに通知する。

- 自分が担当するカテゴリのクイズの場合のみ通知を送信する (**{0}**)。

- 通知はリッチ カード形式で、クイズのタイトルとカテゴリを含む。

## 参考資料

- [Logic Apps で初めてアプリを作成する](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-create-a-logic-app)

- [Microsoft Flow でフローを初めて作成する](https://docs.microsoft.com/ja-jp/flow/getting-started)

- [Microsoft Graph でチャット スレッドを作成する (英語)](https://developer.microsoft.com/ja-jp/graph/docs/api-reference/beta/api/channel_post_chatthreads)

- [Microsoft Teams のコネクタ (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/connectors#setting-up-a-custom-incoming-webhook)

- [メッセージ カードのテスト環境 (英語)](https://messagecardplayground.azurewebsites.net/)