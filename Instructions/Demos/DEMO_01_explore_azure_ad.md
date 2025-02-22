<!---
---
デモ: タイトル: 'Microsoft Entra ID ユーザー設定を調べる' ラーニング パス/モジュール/ユニット: 'ラーニング パス: Microsoft Entra の機能について説明する; モジュール 1: Microsoft Entra ID の関数と ID の種類について説明する; ユニット 3: Microsoft Entra ID の種類について説明する'
---
--->

# デモ: Microsoft Entra ID ユーザー設定

このデモは、次の Learn コンテンツに対応しています。

- ラーニング パス: Microsoft Entra の機能について説明する。
- モジュール: Microsoft Entra ID の関数と ID の種類について説明する。
- ユニット: ID の種類について説明します。

## デモのシナリオ

このデモでは、Microsoft Entra ID にアクセスし、既存のユーザー向けのさまざまな設定について詳しく説明します。

1. Microsoft Edge を開きます。

1. アドレス バーに、「**admin.microsoft.com**」と入力して、Microsoft 365 管理センターにアクセスします。

1. 管理者の資格情報でサインインします。
    1. [サインイン] ウィンドウで、「**admin@WWLxZZZZZZ.onmicrosoft.com**」 (ZZZZZZ はラボ ホスティング プロバイダーから指定された固有のテナント ID) と入力してから、**[次へ]** を選択します。
    1. ラボ ホスティング プロバイダーから提供されている管理者パスワードを入力します。 **[サインイン]** を選択します。
    1. サインインしたままにするかどうかを尋ねられたら、**[はい]** を選択します。

1. Microsoft 365 管理センターの左ナビゲーション ペインで、**[すべて表示]** を選択します。

1. 管理センターの下で、**[ID]** を選択します (下にスクロールする必要があるかもしれません)。  新しいブラウザー ページが開き、Microsoft Entra 管理センターの概要ページが表示されます。 ここでは、Contoso テナントに関する基本情報が表示されます。 メイン ウィンドウを下にスクロールすると、アラート、マイ フィード、機能のハイライトなどの情報も表示されます。  
    1. 発表者/講師への注意: **[entra.microsoft.com](https://entra.microsoft.com)** に移動して、Microsoft Entra 管理センターに直接アクセスすることもできます。

1. 左側のナビゲーション ウィンドウから **[ユーザー]** を展開し、**[すべてのユーザー]** を選びます。  ユーザー ページには、追加のナビゲーション オプションとユーザーの一覧が表示されます。 テナントにはすでにユーザーが構成されています。

1. ユーザーのリストで、**Adele Vance** を選択します。

1. 左側のナビゲーション パネルで、**[概要]** が薄いグレーで強調表示されていることに注意してください。  [概要] ページに表示されている情報を表示または説明します。  ページの上部にある **[監視]** タブを選択すると、ユーザーのサインインが表示されます (以前に Adele Vance としてサインインしていない限り、サインインは表示されません)。  次に、**[プロパティ]** を選択して、Adele Vance ユーザー オブジェクトのすべてのプロパティを表示します。

1. 左ナビゲーション ウィンドウで、**[割り当てられたロール]** を選択します。  このユーザーには、管理者ロールは割り当てられていません。  ページの上部にある **[+ 割り当ての追加]** を選択し、[割り当ての追加] ページで [ロールの選択] の下にある [ロールの検索] フィールドを展開して、使用可能な管理ロールの種類の一覧を表示します。  追加しないでください。ページの右上にある **[X]** を選択して、ページを閉じてください。

1. 左ナビゲーション パネルで、**[グループ]** を選択します。  このユーザーが複数のグループのメンバーであるという事実について説明します。  ここでは、グループの種類について説明することができます。  このユーザーを他のグループに追加するには、**[+ メンバーシップを追加]** を選択します。  新しいグループを追加するのではなく、既存のグループにユーザーを追加するのがいかに簡単かという点のみを説明してください。 ページの右上隅の **[X]** を選択して、[グループの選択] ウィンドウを閉じます。

1. 左ナビゲーション パネルで、**[ライセンス]** を選択します。 このユーザーには Microsoft 365 E5 ライセンスと EMS ライセンスが割り当てられていることに注意してください。  ライセンスを追加するには、メイン ウィンドウの上部で、**[割り当て]** を選択します。  このユーザーのライセンスを表示します。 何も変更しないでください。  ページの右上隅の **[X]** を選択して、このウィンドウを閉じます。

1. 左ナビゲーション ウィンドウで、**[デバイス]** を選択します。  何も表示されませんが、このユーザーがデバイスを割り当てた場合、これが表示される場所であると説明できます。

1. 左ナビゲーション ウィンドウで、**[Azure ロールの割り当て]** を選択します。  呼び出し:
    1. これは、前に示した [割り当てられたロール] タブとは異なり、前のタブは Microsoft Entra でのロールベースのアクセス制御用です。
    1. ここには何も表示されていませんが、これは、Azure リソースの Adele に割り当てられたロールの割り当てを表示できるタブです。 たとえば、Azure リソース グループを作成し、リソース グループの所有者や共同作成者などの特定のロールを Adele に割り当てた場合、そのロールがここに一覧表示されます。 これは、Azure ロールベースのアクセス制御 (Azure RBAC) の一部です。 そのロールの割り当ては、その特定のリソースの一部として追加および管理されます。

1. ページの右上隅にある **[X]** を選択します。 これにより、ユーザーリストに戻ります。

1. ページの右上隅にある **[X]** を選択します。 これにより、Microsoft Entra 管理センターのメイン ページに戻ります。

1. 次のデモで使用するため、このブラウザー タブを開いたままにしておきます。

### 確認

このデモでは、ユーザーを割り当てることができるグループ、ロールの可用性、ユーザー ライセンスの割り当てなど、既存のユーザーの設定について詳しく説明しました。
