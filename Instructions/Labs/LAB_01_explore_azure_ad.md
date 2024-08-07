---
lab:
  title: Microsoft Entra ID ユーザー設定を確認する
  module: Describe the function and identity types of Microsoft Entra ID
---

# ラボ:Microsoft Entra ID ユーザー設定を確認する

このラボは、次の Learn コンテンツに対応しています。

- ラーニング パス: Microsoft Entra の機能について説明する。
- モジュール: Microsoft Entra ID の関数と ID の種類について説明する。
- ユニット: ID の種類について説明します。

## ラボのシナリオ

このラボでは、Microsoft Entra ID (以前は Azure Active Directory と呼ばれていました) にアクセスします。  さらに、ユーザーを作成し、ライセンスの追加を含む、さまざまな設定を構成します。  

**推定時間**:10 ～ 15 分

### タスク 1

Microsoft 365 のサブスクライバーとして、Microsoft Entra ID (以前は Azure AD と呼ばれていました) を既に使用しています。  このタスクでは、Microsoft Entra ID で新しいユーザーを作成し、ユーザー レベルで管理できるサービスの一部を調べる方法について説明します。

1. Microsoft Edge ブラウザーを開きます。 アドレス バーに「**[admin.microsoft.com](https://admin.microsoft.com)**」と入力し、認可されたラボ ホスト (ALH) から提供された Microsoft 365 資格情報を使ってサインインします。
    1. [サインイン] ウィンドウで「**admin@WWLxZZZZZZ.onmicrosoft.com**」 (この ZZZZZZ はお使いの ALH から提供された一意のテナント ID です) と入力し、**[次へ]** を選びます。
    1. ラボ ホスティング プロバイダーから提供されている管理者パスワードを入力します。 **[サインイン]** を選択します。
    1. サインインしたままにするかどうかを尋ねられたら、**[はい]** を選択します。

1. [管理センター] で **[ID]** を選択します (**[すべて表示]** を選択して下にスクロールする必要がある場合があります)。  新しいブラウザー ページが開き、Microsoft Entra 管理センターの概要ページが表示されます。 ここでは、Contoso テナントに関する基本情報が表示されます。 メイン ウィンドウを下にスクロールすると、アラート、マイ フィード、機能のハイライトなどの情報も表示されます。

1. 左側のナビゲーション ウィンドウから **[ユーザー]** を展開し、**[すべてのユーザー]** を選びます。 テナントにはすでにユーザーが構成されていることに注意してください。

1. ページの上部で **[+ 新しいユーザー]** を選び、ドロップダウン ボックスから **[新しいユーザーの作成]** を選びます。

1. これで、[新しいユーザーの作成] ページの **[基本]** タブが表示されます。 フィールドに次のように入力します。
    1. ユーザー プリンシパル名: **sara**.

    1. メール ニックネーム: ユーザー プリンシパル名から派生するように設定されている既定値のままにします。

    1. 表示名: **Sara Perez**。

    1. パスワード: [パスワードを自動生成] というボックスのチェックを外し、パスワード要件に準拠した一時パスワードを入力し、後続のタスクを完了するために必要となるのでメモしておきます。

    1. アカウントが有効: チェックマークを付けたままにして、アカウントが有効になっていることを確認します。

    1. ページの下部にある **[次へ: プロパティ]** を選択します。

1. ここでは、**[プロパティ]** タブのいくつかのフィールドを構成します。

    1. 名: Sara

    1. 姓: Perez

    1. ユーザー タイプ: デフォルトを **[メンバー]** のままにしますが、ドロップダウンからゲストを選択するオプションがあることに注意してください。

    1. 使用場所: お住まいの国/地域を選択します。  [使用状況の場所] フィールドに移動するには、ページの最後のフィールドであるため、ページを下にスクロールする必要があることに注意してください。  **注**: これを行わない場合、後続の手順でライセンスを割り当てることはできません。

    1. **[次へ: 割り当て]** を選びます。

1. これで **[割り当て**] タブが表示され、グループの割り当てを追加し、ロールを追加するための使用可能なオプションが表示されます。

    1. **[グループの追加]** を選択します。

    1. 開いたウィンドウには、使用可能なすべてのグループが表示されます。  

    1. 使用可能なグループの一覧に注意してください。  一覧から **[操作]** を選びます。  ページの下部にある **[選択]** ボタンを選びます。  数秒かかる場合がありますが、操作グループが割り当てページに表示されます。

    1. ページの上部で **[ロールの追加]** を選びます。  使用可能なすべてのディレクトリ ロールを示すウィンドウが開きます。  使用可能なオプションを表示しますが、新しいロールは追加しないでください。  [ディレクトリロール] ページの右上隅の **[X]** を選択して、このページを閉じます。
    1. ページの下部で **[確認および作成]** を選択します。 設定の要約が表示されます。  ページの下部で、**[作成]** ボタンを選択します。

1. [ユーザー] ページに戻ります。  数秒後、Sara Perez が表示されます。  場合によっては、ページの上部にある **[更新]** アイコンを選択する必要があります。

1. ユーザーの一覧から、作成したユーザー **Sara Perez** を選びます。  **[概要]** ページが開きます。

1. 左側のナビゲーション パネルには、ユーザーに対して構成できるさまざまなオプションが表示されます。 使用可能なオプションを表示します。

1. 左ナビゲーション パネルで、**[ライセンス]** を選択します。  このユーザーのライセンス割り当てが見つからないことに注意してください。  注: ライセンスは、使用場所が構成されている場合にのみ割り当てることができます。 使用場所を設定していない場合は、前のタスクでその手順に戻ります。

    1. ライセンスを追加するには、メイン ウィンドウの上部で **[+ 割り当て]** を選択します。

    1. [ライセンスの選択] で、**[Microsoft Power Apps for Developer]** と **[Microsoft Power Automate Free]** を選択し、画面の下部にある **[保存]** ボタンを選択します。 画面の右上隅に、ライセンスの割り当てが成功したことを示す通知が表示されます。

    1. 画面右上で **[X]** を選択して、[ライセンスの割り当て] ウィンドウを閉じます。

    1. ページの上部にある **[更新] アイコン**を選択して、ライセンスの割り当てを確認します。

1. 左側のナビゲーション パネルまたは画面の左上 (パンくず) から **[ホーム]** を選択して、Microsoft Entra 管理センターに戻ります。その上に「Sara Perez | ライセンス」と表示されます。

1. Microsoft Entra ID でユーザーを正常に作成して構成しました。

1. 開いているすべてのブラウザー タブからサインアウトします。 画面右上隅のメール アドレスの隣のユーザー アイコンを選択し、**[サインアウト]** を選択してサインアウトします。すべてのブラウザー ウィンドウを閉じます。

### タスク 2

このタスクでは、Sara Perez として初めてサインインします。

1. Microsoft Edge を開きます。

2. アドレス バーに「**https://login.microsoft.com**」と入力します。

3. **sara@WWLxZZZZZ.onmicrosoft.com** としてサインインします、(ZZZZZZ はALHから支給された固有のテナント ID)
4. 前のタスクで設定した一時パスワードを入力します。

5. パスワードを更新するように求められます。 [現在のパスワード] フィールドに、前のタスクの一時パスワードを入力します。

6. [新しいパスワード] フィールドに新しいパスワードを入力し、パスワードを確認してから、**[サインイン]** を選択します。  SSPR での後続のラボ演習に必要な新しいパスワードを書き留めておきます。

7. これで、Sara の Microsoft 365 に正常にサインインできるはずです。  前のタスクで割り当てた Sara のライセンスは、Power Automate Free と Power Apps for Developer のみに限定されており、E5 ライセンスは含まれていませんでした。

8. Microsoft 365 では、Microsoft 365 ウィンドウの右上隅にある SP という文字が付いた円形のアイコン (疑問符アイコンの横) を選び、**[サインアウト]** を選んでサインアウトしてから、ブラウザーを閉じます。

### 確認

このラボでは、Microsoft Entra ID の最初の探索を開始しました。 Microsoft 365 のサブスクライバーは Microsoft Entra ID を自動的に使用するため、Microsoft 365 管理ポータルまたは Azure portal から Microsoft Entra ID の機能とサービスにアクセスしていることがわかりました。  どちらのアプローチでも、同じ場所に到達することができます。  また、新しいユーザーの作成プロセスを確認し、ユーザーを割り当てることができるグループ、ロールの可用性、ユーザー ライセンスの割り当てなど、構成できるさまざまな設定について確認しました。
