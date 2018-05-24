# 課題 7 - Twitter 連携 (最終課題)

## 背景

Azure Logic Apps では、強力な統合型アプリケーションをコーディングなしで作成できる数々のトリガー、条件、アクションを提供しています。OpenHack の最終課題となる課題 7 では、Azure Event Grid との統合、サードパーティ製の主要なアプリケーションやサービスとの統合などを学習します。

## 課題

2 つ目の Event Grid トピックをセットアップし、このトピックに送られたイベントの data.tweet をツイートするようにサブスクリプションを構成します。Twitter アカウントは、お持ちのものを使用しても、テスト ツイート用のアカウントを新規作成してもかまいません。Event Grid のトピックとサブスクリプションの構成が完了したら、Event Grid トピックの詳細情報 (エンドポイントとアクセス キー) を OpenHack ボットに登録します。OpenHack は、この情報を使用してサブスクリプションがツイートするイベントを追加します。OpenHack がこのツイートを確認したら、すべての課題を無事修了することができます。

## 成功条件

- Event Grid トピックの詳細情報 (エンドポイントとアクセス キー) を OpenHack ボットに登録する。

- Event Grid トピックに送信されたイベントの data.tweet を、以下のスキーマに従ってツイートする。

```
{
"id": "1234",
"eventType": "MSOpenHack.Tweet",
"subject": "msopenhack/tweet",
"eventTime": "2018-07-02T21:03:07+00:00",
"data": {
"tweet": "Some text that you should tweet"
}
}
```

## 参考資料

- [カスタム イベントを作成して Azure Event Grid にルーティングする](https://docs.microsoft.com/ja-jp/azure/event-grid/custom-event-quickstart)

- [Logic Apps で初めてアプリを作成する](https://docs.microsoft.com/ja-jp/azure/logic-apps/quickstart-create-first-logic-app-workflow)

- [Logic Apps で各種コンテンツを取り扱う](https://docs.microsoft.com/ja-jp/azure/logic-apps/logic-apps-content-type)