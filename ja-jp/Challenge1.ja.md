# 課題 1 - チームのセットアップ

## 背景

多くの企業で Office 365 と Azure の普及が急速に進んでいます。現在、Office 365 の月間アクティブ商用ユーザー数は 1 億人を超え、Fortune 500 企業の 90% がマイクロソフトのクラウド サービスを利用しています。この OpenHack では、開発者の皆様にこれらのテクノロジに触れていただきます。OpenHackの中では、Azure Functions、Event Grid、Logic Apps など、Azure の優れた「サーバーレス」テクノロジを使用します。

Office 365 の最新機能である Microsoft Teams は、クラウド コミュニケーションの分野で今最も重要な投資対象となりつつあります。課題 1 では、Office 365 と Microsoft Teams の基礎を学びます。まずは、プロファイル写真の更新、チームの作成、Microsoft Teams へのアプリケーションのサイドローディングなどの基本操作を行っていただきます。Microsoft Teams の経験がある方はすぐに終わる操作ですので、終了された方は続いて OpenHack の主要課題である開発者向けのタスクに取り掛かってください。

## 課題 

各チーム メンバーは、用意された msopenhack.com アカウントで Microsoft Teams にサインインし、プロファイル写真を変更します (このアカウントは OpenHack の後の課題で使用します)。次に、OpenHack グループで 1 つのチームを Microsoft Teams にプロビジョニングします (メンバーごとではありません)。最後に、以下に用意されているアプリケーション パッケージを使用して、グループで OpenHack アプリを Microsoft Teams にサイドローディングします。

[Microsoft Teams 用 OpenHack アプリ パッケージ](https://msopenhack.azurewebsites.net/Manifest/OpenHackValidationApp.zip)

## 成功条件

- 用意された Office 365 アカウントに、チーム メンバー全員が Microsoft Teams を使用してプロファイル写真をアップロードする。

- 共同作業用のチームをグループで 1 つ Microsoft Teams にプロビジョニングする。

- Microsoft Teams 内のチームに [OpenHack 用アプリ パッケージ](https://msopenhack.azurewebsites.net/Manifest/OpenHackValidationApp.zip) をプロビジョニングする。

## 注意事項

- 既に Office 365 を利用しているか、Azure Active Directory を使用している組織に所属している場合、OpenHack 中はシークレット モードやプライベート モードのブラウザーを使用するようにしてください。

- OpenHack アプリは、OpenHack 全体を通してチームの進捗状況を自動的に検証します。**アプリを他のチームにサイドローディングしないでください。**

## 参考資料

- [Microsoft Teams](https://teams.microsoft.com)

- [アプリ パッケージを Microsoft Teams にサイドローディングする (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/apps/apps-upload)