# 課題 4 - ランキング タブ

## 背景

Microsoft Teams のカスタム タブに、サードパーティ アプリを統合することができます。ボットでは対話形式のユーザー エクスペリエンスが提供されますが、このタブでは従来型のユーザー エクスペリエンスが提供されます。課題 4 では、サードパーティの Web コンテンツをカスタム タブとして Microsoft Teams に統合します。

Microsoft Graph API では、メール、カレンダー、連絡先、ドキュメント、ディレクトリ、デバイスなど、生産性に関するデータをすべて取り扱える単一のエンドポイントが提供されます。課題 4 では、Microsoft Graph でさまざまなプロファイル情報に対してクエリを実行し、アプリのプレーヤーに表示します。Microsoft Graph は Azure Active Directory によって保護されているため、この認証機能をカスタム タブに統合します。

## 課題

構成可能なタブを Microsoft Teams アプリに追加し、クイズのランキング ボードを表示します。集計スコアに基づいたチーム ランキングと個人ランキングをユーザーが選択できるように構成します。個人ランキングの場合は、ユーザーのプロファイル写真を Microsoft Graph から取得して表示します。アプリを Active Directory に新規登録して、タブを Azure AD で保護する必要があります。クイズのランキング ボードの情報は、[Get Trivia Leaderboard (英語)](https://msopenhack.azurewebsites.net/swagger/ui/index#!/Trivia/Trivia_GetLeaderboard) API (OpenHack API のドキュメントを参照) で取得されます。

## 成功条件

- 構成可能なタブでクイズ アプリのランキング ボードを構築する。

- 構成可能なタブでユーザーがチーム ランキングと個人ランキングを選択できるようにする。

- 個人ランキング ボードでは Microsoft Graph を使用して各ユーザーのプロファイル写真を表示する。

## 注意事項

- 前の課題で作成したボットは既に Azure Active Directory に登録しましたが、この課題では改めてこのアプリを新規登録する必要があります。前回はボットの通信を保護する目的での登録だったため、再利用しないでください。よって、アプリケーション ID とアプリケーション シークレットが 2 つずつ存在することになります。

- OpenHack API は、Microsoft Teams に登録されているチームのコンテキストでのみ動作します。これらの API は、Swagger ドキュメント、または [Postman (英語)](https://www.getpostman.com/) や [Fiddler (英語)](https://www.telerik.com/fiddler) などのツールでテストすることができます。テストにはチームの詳細情報 (Teams の ID と Azure AD のオブジェクト ID) が必要です。

## 参考資料

- [OpenHack API のドキュメント (英語)](https://aka.ms/msopenhackapi)

- [Microsoft Teams でタブを作成する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/tabs/tabs-overview)

- [Microsoft Teams で構成可能なタブを作成する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/tabs/tabs-configuration)

- [アプリケーションを Azure AD v1 エンドポイントに登録する](https://docs.microsoft.com/ja-jp/azure/active-directory/develop/active-directory-integrating-applications#adding-an-application)

- [アプリケーションを Azure AD v2 エンドポイントに登録する](https://developer.microsoft.com/ja-jp/graph/docs/concepts/auth_register_app_v2)

追加の参照情報:

- [Microsoft Teams のタブで使用するコンテキストを取得する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/tabs/tabs-context)

- [Microsoft Teams のタブでユーザーを認証する (英語)](https://docs.microsoft.com/ja-jp/microsoftteams/platform/concepts/authentication/authentication)

- [Microsoft Teams のタブでの認証、SSO、Microsoft Graph の利用 (英語)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Authentication-SSO-and-Microsoft-Graph-in-Microsoft-Teams-Tabs/ba-p/125366)

- [Microsoft Graph のドキュメント](https://developer.microsoft.com/ja-jp/graph/docs/concepts/overview)

- [Microsoft Graph でプロファイル写真を取得する手順](https://developer.microsoft.com/ja-jp/graph/docs/api-reference/v1.0/api/profilephoto_get)

- ヒント: プロファイル写真を取得するには User.ReadBasic.All またはそれ以上の範囲のアクセス許可が必要です。