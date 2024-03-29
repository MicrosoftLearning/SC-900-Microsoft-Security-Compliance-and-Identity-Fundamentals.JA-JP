<a name="---"></a><!---
---
デモ: タイトル: 'Azure Policy' ラーニング パス/モジュール/ユニット: 'ラーニング パス: Microsoft コンプライアンスの機能について説明する; モジュール 6: Azure のリソース ガバナンス機能について説明する; ユニット 2: Azure Policy について説明する'
---
--->

# <a name="demo-azure-policy"></a>デモ:Azure Policy

このデモは、次の Learn コンテンツに対応しています。

- ラーニング パス: Microsoft コンプライアンスの機能について説明する
- モジュール: Azure のリソース ガバナンス機能について説明する
- ユニット: Azure Policy について説明する

## <a name="demo-scenario"></a>デモ シナリオ

このデモでは、Azure Policy を設定するプロセスと、そのポリシーの影響について一通り説明します。

### <a name="demo-part-1"></a>デモ パート 1

リソース グループにタグを要求するポリシーを作成します (テンプレートでポリシーを作成する手順を示します)

1. Microsoft Edge を開きます。 アドレス バーに、「**portal.azure.com**」と入力します。  管理者の資格情報で既にサインインしているはずですが、していない場合はサインインしてください。

1. ページの上部で "Microsoft Azure" と表示されている場所の横にある青色のバーの検索ボックスに、「**ポリシー**」と入力して、検索結果から **"ポリシー"** を選択します。

1. これで、[ポリシー] ページの概要が表示されます。 ダッシュボードで利用可能な情報に注意してください。

1. 左ナビゲーション ウィンドウで、[作成] の下の **[割り当て]** を選択します。  既にポリシーが割り当てられていることがわかります。 **[ASC 既定値]** を選択してください。  説明フィールドを確認します。 注: 説明フィールドでは、名前が Microsoft Defender for Cloud に変更された Azure Security Center を参照します。  ページの右上隅で **[X]** を選択し、[ポリシーの管理] ページに戻ります。

1. ページの上部で、**[ポリシーの割り当て]** を選択します。 [ポリシーの割り当て] ウィザードが開き、管理者がポリシーを割り当てるプロセスをガイドします。

1. [基本] タブから開始します。
    1. [スコープ] では、既定の設定のままにします。 この場合、ポリシーのスコープは、Authorized Lab Hoster (ALH) によって提供される Azure サブスクリプションです。
    1. [ポリシー定義] で、**省略記号**を選択します。  使用可能なポリシー定義の一覧が表示されます。  検索バーに「**タグを必須にする**」と入力します。 検索結果で、**[リソース グループにタグを要求する]** を選択してから (下にスクロールする必要がある場合があります)、**[選択]** を押します。  注: このポリシーの効果は、要件を満たさない新しいリソース グループの作成を拒否することです。  
    1. 既定の割り当て名に注意してください。  名前をそのままにしておきます。
    1. [ポリシーの適用] が **[有効]** に設定されていることを確認し **[次へ]** を選択します。

1. これで、[パラメーター] タブが表示されます。[タグ名] フィールドに「**環境**」と入力し、 **[次へ]** を選択します。

1. [修復] タブで、既定の設定のままにして、 **[次へ]** を選択します。

1. [非準拠メッセージ] タブに移動しました。[非準拠メッセージ] フィールドに「**環境タグが必要です**」と入力し、 **[次へ]** を選択します。 注: このメッセージは、ポリシー割り当ての前に作成され、[環境] タグがないリソース グループの非準拠の理由として表示されます。  

1. ポリシーの割り当てを確認してから、 **[作成]** を選択します。  ポリシーがすぐに表示されない場合は、**[更新]** を選択します。 注: ポリシーが有効になるまでに最長 30 分かかる場合がありますが、通常はそれより早く有効になります。

1. 画面の右上隅の **[X]** を選択して、[ポリシーの割り当て] ページを終了します。

1. これで、Azure サービスのホーム ページが表示されます。  次のタスクで必要なため、このページを開いたままにしておきます。

### <a name="demo-part-2"></a>デモ パート 2

このタスクでは、Azure でタグを持たないリソース グループを作成してみて、Azure ポリシーの割り当ての影響を確認します。

1. ブラウザー タブ [ホーム – Microsoft Azure] を開きます。

1. ページの上部、Azure Services と表示されている場所の下で、**[リソース グループ]** を選択します。

1. ページの左下隅で、**[作成]** を選択します。

1. [リソース グループの作成] の [基本] タブで、[サブスクリプション] フィールドをそのままにします。

1. [リソース グループ] フィールドに、「**SC900-Labs**」と入力します。

1. [リージョン] の設定を既定のままにして、 **[次へ:タグ]** を選択します。

1. タグの [名前と値] フィールドは空のままにします。  データを入力せずに、**[作成と確認]** を選択します。

1. 検証に合格したことを示すメッセージが表示されるので (タグの名と値はウィザードの必須フィールドではありません)、 **[作成]** を選択します。

1. 画面上部に次の失敗メッセージが表示されます。"リソース グループの作成に失敗しました。 **[エラーの詳細を表示する]** を選択してください"。 Azure ポリシーの一部である条件が満たされていないため、コンプライアンス違反により、作成中のリソース グループがブロックされました。 注: 失敗メッセージが表示されず、リソース グループが作成された場合は、ポリシーがまだ有効になっていないことが原因です。  前のタスクで作成したポリシーの [ポリシー] ページに移動します。ポリシーが有効になると、リソースが準拠していないことがわかります。  詳細ページには、コンプライアンス違反のメッセージが含まれます。

1. エラーの概要には、"リソース 'SC900-Labs' がポリシーによって許可されませんでした" というエラーの種類が表示されます。  画面の左上隅の **[X]** を選択して、このウィンドウを閉じます。

1. [リソース グループの作成] ウィンドウで、 **[前へ]** を選択します。

1. リソース グループの作成の [タグ] ページに戻ります。  [名前] フィールドに「環境」と入力し、[値] フィールドに「**SC900-Labs**」と入力して、**[次へ: 確認と作成]** を選択します。

1. タグを確認し、**[作成]** を選択します。

1. [名前] フィールドに「**環境**」と入力し、[値] フィールドに「**ラボ**」と入力し (この値は何でもかまいませんが、ポリシーにはタグ値が必要です)、 **[次へ: 確認と作成] >** を選択し、 **[作成]** を選択します。

1. リソース グループが一覧表示されます。  

1. ポリシーの前にリソース グループが作成されていた場合、そのリソース グループはこのポリシー割り当てに対して非準拠として表示されるため、[環境] タグを適用して修復する必要があることを受講者に伝えます。  ResourceGroup1 というラベルの付いた既存のリソース グループがあり、非準拠で修復できますが、修復後に状態が更新される時間は、ラボ環境では通常よりも長くなります。

### <a name="review"></a>確認

このデモでは、Azure Policyを設定するプロセスと、そのポリシーの影響について説明しました。
