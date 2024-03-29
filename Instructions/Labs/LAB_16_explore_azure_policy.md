<!---
---
ラボ: タイトル: 'Azure Policy を探索する' ラーニング パス/モジュール/ユニット: 'ラーニング パス: Microsoft コンプライアンスの機能について説明する; モジュール 6: Azure のリソース ガバナンス機能について説明する; ユニット 2: Azure Policy について説明する'
---
--->

# ラボ:Azure Policy を探索する

このラボは、次の Learn コンテンツに対応しています。

- ラーニング パス: Microsoft コンプライアンスの機能について説明する
- モジュール: Azure のリソース ガバナンス機能について説明する
- ユニット: Azure Policy について説明する

## ラボのシナリオ

Azure Policy は、組織の標準を適用し、コンプライアンスを大規模に評価するのに役立ちます。 Azure Policy では、Azure 内のリソースのプロパティをビジネス ルールと比較して、それらのリソースを評価します。 このラボでは、ポリシーを作成し、そのポリシーの影響を確認します。  また、[ポリシー] ページで得られるコンプライアンスおよび修復情報も確認します。

**推定時間**:15 ～ 20 分

### タスク 1

このタスクでは、リソース グループのタグを要求するための基本的なポリシー割り当てを作成します。
1.  Microsoft Edge を開きます。 アドレス バーに、「**portal.azure.com**」と入力します。

1. Azure サブスクリプションの管理者資格情報を使用してサインインします (これらの管理者資格情報は、Microsoft 365 管理者資格情報とは異なります)。
    1. [サインイン] ウィンドウで、「 **User1-XXXXXXXX@LODSPRODMSLEARNMCA.onmicrosoft.com** 」と入力し (XXXXXXXX はラボ ホスティング プロバイダーから提供された固有のテナント ID)、 **[次へ]** を選択します。

    1. ラボ ホスティング プロバイダーから提供された管理者パスワードを入力します。 **[サインイン]** を選択します。
    1. サインインしたままにするかどうかを尋ねられたら、 **[はい]** を選択します。

1. これで、Azure portal が表示されます。  ページの上部で "Microsoft Azure" と表示されている場所の横にある青色のバーの検索ボックスに、「**ポリシー**」と入力して、検索結果から **"ポリシー"** を選択します。 これにより、ダッシュボード ビューを表示する [ポリシー] ホーム ページが開きます。  ダッシュボード ビューのスコープは、Authorized Lab Hoster (ALH) によって提供される Azure サブスクリプションです。 ポリシーが一覧表示されます。これは、Azure サブスクリプションを使用するために ALH によって作成されたポリシーです。

1. 左ナビゲーション ウィンドウで、[作成] の下の **[割り当て]** を選択します。

1. ページの上部で、**[ポリシーの割り当て]** を選択します。 ポリシーの割り当てウィザードが開き、管理者がポリシーを割り当てるプロセスをガイドします。

1. [基本] タブから開始します。
    1. [スコープ] では、既定の設定のままにします。 この場合、ポリシーのスコープは、Authorized Lab Hoster (ALH) によって提供される Azure サブスクリプションです。
    1. [ポリシー定義] で、**省略記号**を選択します。  使用可能なポリシー定義の一覧が表示されます。  検索バーに「**タグを必須にする**」と入力します。 検索結果で、 **[リソース グループにタグを要求する]** を選択してから (下にスクロールする必要がある場合があります)、 **[追加]** を押します。  注: このポリシーの効果は、要件を満たさない新しいリソース グループの作成を拒否することです。  
    1. 既定の割り当て名に注意してください。  名前をそのままにしておきます。
    1. [ポリシーの適用] が、 **[有効]** に設定されていることを確認します

1. **[次へ]** を選択してから、もう一度 **[次へ]** を選択して [パラメーター] タブに移動します ([パラメーター] タブを直接選択することもできます)。

1. これで、[パラメーター] タブが表示されます。[タグ名] フィールドに「**環境**」と入力し、**[次へ]** を選択します。

1. [修復] タブで、既定の設定のままにして、**[次へ]** を選択します。

1. [非準拠メッセージ] タブに移動しました。[非準拠メッセージ] フィールドに「**環境タグが必要です**」と入力し、**[次へ]** を選択します。 注: このメッセージは、ポリシー割り当ての前に作成され、[環境] タグがないリソース グループの非準拠の理由として表示されます。

1. ポリシーの割り当てを確認してから、**[作成]** を選択します。  ポリシーがすぐに表示されない場合は、**[更新]** を選択します。 注: ポリシーが有効になるまでに最長 30 分かかる場合がありますが、通常はそれより早く有効になります。

1. 画面の右上隅の **[X]** を選択して、[ポリシーの割り当て] ページを終了します。

1. これで、Azure サービスのホーム ページが表示されます。  次のタスクで必要なため、このページを開いたままにしておきます。

### タスク 2

このタスクでは、Azure でタグを持たないリソース グループを作成してみて、Azure ポリシーの割り当ての影響を確認します。

1. ブラウザー タブ [ホーム – Microsoft Azure] を開きます。

1. ページの上部、Azure Services と表示されている場所の下で、**[リソース グループ]** を選択します。

1. ページの左下隅で、**[作成]** を選択します。

1. [リソース グループの作成] の [基本] タブで、[サブスクリプション] フィールドをそのままにします。

1. [リソース グループ] フィールドに、「**SC900-Labs**」と入力します。

1. [リージョン] の設定を既定のままにして、**[次へ:タグ]** を選択します。

1. タグの [名前と値] フィールドは空のままにします。  データを入力せずに、**[作成と確認]** を選択します。

1. 検証成功メッセージが表示されたら (ウィザードでは、タグの名前と値は必須フィールドではありません)、 **[作成]** を選択します。

1. 画面上部に、"リソース グループを作成できませんでした" という失敗メッセージが表示されます。 **[エラーの詳細を表示]** を選択します。 Azure ポリシーに含まれている条件が満たされておらず、準拠していないため、リソース グループの作成がブロックされました。 注: 失敗メッセージが表示されず、リソース グループが作成された場合は、ポリシーがまだ有効になっていないことが原因です。  前のタスクで作成したポリシーの [ポリシー] ページに移動します。ポリシーが有効になると、リソースが準拠していないことがわかります。  詳細ページには、コンプライアンス違反のメッセージが含まれます。

1. エラーの概要には、"リソース 'SC900-Labs' がポリシーによって許可されませんでした" というエラーの種類が表示されます。  画面の左上隅の **[X]** を選択して、このウィンドウを閉じます。

1. [リソース グループの作成] ウィンドウで、**[前へ]** を選択します。

1. リソース グループの作成の [タグ] ページに戻ります。  [名前] フィールドに「環境」と入力し、[値] フィールドに「**SC900-Labs**」と入力して、**[次へ: 確認と作成]** を選択します。

1. タグを確認し、**[作成]** を選択します。

1. [名前] フィールドに「**環境**」と入力し、[値] フィールドに「**ラボ**」と入力し (この値は何でもかまいませんが、ポリシーにはタグ値が必要です)、**[次へ: 確認と作成] >** を選択し、**[作成]** を選択します。

1. リソース グループが一覧表示されます。  

1. ページの左上隅にある階層リンクで、 **[ホーム]** を選択して、Azure ホームページに戻ります。

1. 次のタスクで必要なため、ブラウザー タブは開いたままにしておきます。

### タスク 3 (省略可能)

このタスクでは、準拠していないリソース グループを修復する手順について説明します。 注: ラボに使用される Azure サブスクリプションでは、修復されたリソース グループのコンプライアンス状態が更新されるまで、通常より長い遅延が発生します。

1. Azure ホーム ページで、 **[ポリシー]** を選択します。 これにより、ダッシュボード ビューを表示する [ポリシー] ホーム ページが開きます。  ダッシュボード ビューのスコープは、Authorized Lab Hoster によって提供される Azure サブスクリプションです。  

1. 前に作成したポリシーが表示されます。それを選択します。

1. ページ上部の "Essentials" の下に、名前、説明、その他の重要な情報が表示されます。  ポリシーは非準拠として表示されることに注意してください。  ポリシーが非準拠である理由の詳細については、そのポリシーを選択します。 ここでは、resourgegroup1 として一覧に表示されたリソースが準拠していません。  これは、ポリシーを作成する前に作成されたリソース グループの例です。 詳細については、 **[詳細]** を選択します。  ここでは、環境タグが必須であるというコンプライアンス メッセージを確認できます。  右上にある **[X]** を選択してウィンドウを閉じます。

1. 次に、ページの上部で **[resourcegroup1]** を選択し、 **[リソースの表示]** を選択します。
    1. [タグ] と表示されている場所の横にある **[編集]** を選択します
    1. マウスのカーソルを [タグ] フィールドに位置付け、 **[環境]** を選択します。
    1. マウスのカーソルを [値] フィールドに位置付けて **[ラボ]** を選択し、 **[保存]** を選択します。

1. [ポリシー] ページに戻ります。  ページの上部にある青色の検索ボックスにマウスのカーソルを位置付け、 **[ポリシー]** を選択します。

1. 左ナビゲーション ウィンドウで、**[コンプライアンス]** を選択します。  [概要] ページと同様に、ここでは、一覧表示されたポリシーやイニシアチブのコンプライアンスの状態を表示できます。  注: リソース グループにタグを追加しましたが、状態が更新するまで時間がかかります。  ラボの目的で使用される Azure サブスクリプションでは、通常よりも長い遅延が発生する可能性があります。 このリソースのコンプライアンス状態が更新されるまで待機する場合は、ラボを終了しないでください。 ラボ環境によっては、更新に 1 時間以上かかる場合があります。  

### 確認

このラボでは、Azure ポリシーの割り当てを作成するプロセスを実行し、そのポリシーの影響を確認することができました。

