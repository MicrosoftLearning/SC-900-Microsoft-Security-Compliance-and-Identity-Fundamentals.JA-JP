---
Demo:
  title: Azure Active Directory ユーザー設定
  module: 'Module 2 Lesson 1: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
ms.openlocfilehash: eb1ffc50ce90922dced58726c39879edfc74fb5b
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557183"
---
# <a name="demo-azure-active-directory-user-settings"></a>デモ:Azure Active Directory ユーザー設定

## <a name="demo-scenario"></a>デモ シナリオ

このデモでは、Azure Active Directoryにアクセスし、既存のユーザーのさまざまな設定について詳しく説明します。

1. ブラウザーで開いている「**ホーム – Microsoft Azure**」タブに移動します。  タブを以前に閉じた場合は、Microsoft Edge を開き、アドレス バーに「portal.azure.com」と入力して、Microsoft 365 テナントと同じ管理者資格情報でサインインします。

1. Azure サービスを表示する Azure portal ランディング ページで、「**Azure Active Directory**」を選択します。 すぐに表示されない場合は、Microsoft Azure と表示されている場所の隣の「検索」ボックスに、「Azure Active Directory」と入力します。  また、Microsoft Azure と表示されている場所の左側にある「ポータルの表示」メニュー アイコン (ページ上部の青色バーにある、「ハンバーガー」アイコンとも呼ばれる 3 本の水平線) からアクセスする方法を示すこともできます。

1. 左ナビゲーション ペインで、「**ユーザー**」を選択します。 ユーザーによりテナントがすでに構成されていることに注意してください。

1. ユーザーの一覧で、「**Adele Vance**」を選択します。

1. 左ナビゲーション パネルで、「**プロファイル**」が選択されていることに注意してください。  「プロファイル」ページに表示されている情報を表示/説明します。

1. 左ナビゲーション パネルで、「**割り当てられたロール**」を選択します。  このユーザーには、管理者ロールは割り当てられていません。  ページの上部で、「 **+ 割り当ての追加**」を選択して、使用可能な管理者ロールの種類を表示します。  追加しないでください。ページの右上にある「**X**」を選択して、ページを閉じてください。

1. 左ナビゲーション パネルで、「**グループ**」を選択します。  このユーザーはいくつかのグループのメンバーであるという事実について説明してください。  ここでは、グループの種類について説明します。  このユーザーを他のグループに追加するには、「 **+ メンバーシップを追加**」を選択するだけです。  新しいグループを追加するのではなく、既存のグループにユーザーを追加するのがいかに簡単かという点について説明してください。 ページの右上隅の「**X**」を選択して、グループ ウィンドウを閉じます。

1. 左ナビゲーション パネルで、「**ライセンス**」を選択します。 このユーザーには、Microsoft 365 E5 ライセンスと EMS ライセンスが割り当てられていることに注意してください。  ライセンスを追加するには、メイン ウィンドウの上部で、「 **+ 割り当て**」を選択します。  このユーザーのライセンスを表示します。 何も変更しないでください。  ページの右上隅の「**X**」を選択して、このウィンドウを閉じます。

1. 左ナビゲーション パネルで、「**デバイス**」を選択します。  何も表示されませんが、このユーザーにデバイスが割り当てられている場合は、ここに表示されます。

1. 左ナビゲーション パネルで、「**Azure ロールの割り当て**」を選択します。  注意点:
    1. これは、前に示した「割り当てられたロール」タブとは異なり、前のタブは Azure Active Directory でのロールベースのアクセス制御用です (Active Directory を強調します)。
    1. このタブでは、Azure リソースのユーザーに割り当てられたロールの割り当てを表示できます。 たとえば、Azure リソース グループを作成する場合、リソース グループの所有者や投稿者など、特定のロールを Adele に割り当てると、そのロールがここに一覧表示されます。 これは、Azure ロールベースのアクセス制御 (Azure RBAC) の一部です。 そのロールの割り当ては、その特定のリソースの一部として管理されます。

1. 左ナビゲーション パネルで、「**認証方法**」を選択します。  「ここでは、ユーザーがM ulti-Factor Authentication とセルフサービス パスワード リセットを実行するために使用する電話番号とメール アドレスを設定し、ユーザーのパスワードをリセットできます」という説明を思い出してください。 ユーザーが SSPR 用に構成されているか、MFA を使用する必要があり、管理者としてこれを入力すると、ユーザーはすでに登録されており、SSPR または MFA の登録手順を実行する必要はありません。  ユーザーが自己登録するのに対して、管理者はこれを行う必要があるのが一般的です。

1. 左ナビゲーション パネルで、「**サインイン**」を選択します。ここでは、このユーザーのサインイン アクティビティを確認できます。  このユーザーはまだサインインしていないため、何も表示されない場合があります。

1. ページの右上隅にある「**X**」を選択します。 これにより、ユーザー一覧に戻ります。  ユーザー一覧を閉じる前に、MFA がページの上部に表示されていることを強調表示できます。  **[Multi-Factor Authentication]** を選択します。  これで新しいブラウザー ウィンドウが開きます。  ここでは、ユーザーの MFA を一括選択できます。  これは、ユーザーに対して MFA を有効にする 1 つの方法です。  実際には、MFA のより詳細な制御を提供する条件付きアクセスのコンテキストで MFA について詳しく説明します。  Multi-Factor Authentication 用ののブラウザー タブを閉じます。

1. ページの右上隅にある「**X**」を選択します。 これにより、Contoso テナントの「メイン」ページに戻ります。

### <a name="review"></a>確認

このデモでは、ユーザーを割り当てることができるグループ、ロールの可用性、ユーザー ライセンスの割り当てなど、既存のユーザーの設定について詳しく説明しました。
