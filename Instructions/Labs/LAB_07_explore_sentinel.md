---
lab:
  title: Microsoft Sentinel の詳細
  module: 'Module 3 Lesson 3: Describe the capabilities of Microsoft security solutions: Describe security capabilities of Microsoft Sentinel'
ms.openlocfilehash: c5a7ba866c82f15a4f78099326fd93a734caead8
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894234"
---
# <a name="lab-explore-microsoft-sentinel"></a>ラボ:Microsoft Sentinel の詳細 

## <a name="lab-scenario"></a>ラボのシナリオ
このラボでは、Microsoft Sentinel インスタンスの作成プロセスについて一通り説明します。  また、Microsoft Sentinel をサポートするためにデプロイするリソースへのアクセスを保証するためのアクセス許可を設定します。  この基本設定が完了した後は、Microsoft Sentinel をデータ ソースに接続する手順、組み込みの分析を使用して疑わしい現象に関して通知を受け取る方法について一通り説明し、最後に自動化機能の詳細について説明します。  

  

**推定時間**:30 ～ 45 分

#### <a name="task-1--create-an-microsoft-sentinel-instance"></a>タスク 1:Microsoft Sentinel インスタンスを作成する。

1. Microsoft Edge を開きます。 アドレス バーに、「**portal.azure.com**」と入力します。

2. 管理者の資格情報でサインインします。
    1. [サインイン] ウィンドウで、「 **admin@WWLxZZZZZZ.onmicrosoft.com** 」と入力してから、 **[次へ]** を選択します (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。
    
    1. ラボ ホスティング プロバイダーから提供される管理者のパスワードを入力します。 **[サインイン]** をクリックします。
    1. サインインしたままにするかどうかを尋ねられたら、「**はい**」を選択します。

3. Microsoft Azure の隣の画面の左上隅で、「ポータル メニューの表示」アイコン (3 本の水平方向のラインのあるアイコンで、「ハンバーガー」アイコンとも呼ばれます) を選択してから、「**すべてのサービス**」を選択します。  

4. [サービスのフィルター] ボックスに「**Microsoft Sentinel**」と入力し、一覧から **[Microsoft Sentinel]** を選択します。

5. [Microsoft Sentinel] ページで、 **[Microsoft Sentinel の作成] を選択します**。

6. [ワークスペースへの Microsoft Sentinel の追加] ページで、 **[新しいワークスペースの作成]** を選択します。

7. 「Log Analytics ワークスペースの作成」の「基本」タブに、次の情報を入力します。
    1. [サブスクリプション]: **[Azure Pass – Sponsorship]\(Azure Pass – スポンサーシップ\)**
   
    1. リソース グループ: 「**新規作成**」を選択してから、名前「**SC900-ResourceGroup**」を入力し、その後「**OK**」を選択します。
    1. 名前: **SC900-LogAnalytics-workspace**.
    1. リージョン: **米国東部** (既定のままにします)
    1. **[次へ: 価格レベル]** を選択します。

8. 「価格レベル」については、既定の設定: **[Pay-as-you-go (per GB 2018)]\(従量課金制 (1 GB あたり (2018))\)** のままにして、 **[次へ:タグ >]** を選択できます。

9. 「タグ」については、空白のままにして、「**Review + Create**」を選択します。

10. 入力した情報を確認してから、「**作成**」を選択します。

11. 新しいワークスペースが一覧表示されない場合は、「**更新**」を選択してから、「**追加**」を選択します。

12. 新しいワークスペースが追加されると、[Microsoft Sentinel | News & guides]\(Microsoft Sentinel |ニュースとガイド\) ページが表示されます。  「作業開始」ページに 3 つの手順を一覧表示されることに注意してください。

13. 次のタスクで使用するため、このページを開いたままにしておきます。

#### <a name="task-2--with-the-microsoft-sentinel-instance-created-you-will-want-to-make-sure-that-you-have-the-necessary-access-to-the-resources-that-get-deployed-to-support-microsoft-sentinel--in-this-task-you-will-go-to-the-access-control-iam-page-for-the-resource-group-that-you-created-with-the-instance-of-microsoft-sentinel-view-the-available-roles-and-assign-yourself-mod-administrator-the-required-role-assigning-the-role-at-the-resource-group-level-will-ensure-the-role-will-apply-to-all-the-resources-that-are-deployed-to-support-microsoft-sentinel"></a>タスク 2:Microsoft Sentinel インスタンスが作成されると、Microsoft Sentinel をサポートするためにデプロイするリソースに対して、必要なアクセス権があることを確認する必要があります。  このタスクでは、Microsoft Sentinel のインスタンスを使用して作成したリソース グループのアクセス制御 (IAM) ページに移動して、利用可能なロールを表示し、自分自身 (MOD 管理者) に必要なロールを割り当てます。 リソース グループ レベルにロールを割り当てることで、Microsoft Sentinel をサポートするためにデプロイされるすべてのリソースにロールが適用されることが保証されます。

1. 上に「Microsoft Sentinel」と表示されている [Microsoft Sentinel] ページの左上隅で、 **[すべてのサービス]** を選択します。

2. 「フィルター サービス」ボックスに、「リソース グループ」を入力し、表示される一覧で、「**リソース グループ**」を選択します。

3. [リソース グループ] ページで、Microsoft Sentinel を使用して作成したリソース グループ「**SC900-ResourceGroup**」を選択します。

4. 「SC900-ResourceGroup」ページの左ナビゲーション パネルで、「**アクセス制御 (IAM)** 」を選択します。

5. 「アクセス制御」ページで、「**自分のアクセスの表示**」を選択します。  現在のロールがセキュリティ管理者であることに注意してください。ウィンドウの右上隅の「**X**」を選択して、「MOD 管理者割り当て」ウィンドウを閉じます。

6. 「アクセス制御」ページで、「 **+ 追加**」を選択してから、「**ロール割り当ての追加**」を選択します。

7. 「ロール割り当ての追加」ウィンドウが開きます。  「ロール フィールドの選択」で、ドロップダウン矢印を選択して、利用可能なロールを表示します。  このラボでは、「**所有者**」を選択します。  注:ベスト プラクティスとして、ロールに必要な最小特権を割り当てる必要があります。  参照として、Microsoft Sentinel のアクセス許可を確認してください (https://docs.microsoft.com/en-us/azure/sentinel/roles )。

8. 表示されるユーザーの一覧で、「**MOD 管理者**」を選択します。

9. ページの下部にある **[保存]** を選択します。

10. 「アクセス制御」ページで、「**自分のアクセスの表示**」を選択し、ロールが追加されたことを確認してから、ウィンドウの右上隅で、「**X**」を選択してウィンドウを閉じます。

11. 上部にリソース グループを表示するページの左上隅で、「**すべてのサービス**」を選択して、Azure の「すべてのサービス」ページに戻ります。

#### <a name="task-3--in-this-task-you-will-walk-through-the-process-of-connecting-microsoft-sentinel-to-your-data-source-to-begin-to-collect-data-note-it-can-take-a-bit-time-to-show-the-connected-status-of-a-connector-30-minutes-depending-on-the-tenant"></a>タスク 3:このタスクでは、Microsoft Sentinel をデータ ソースに接続し、データの収集を開始するプロセスについて一通り説明します。 注: コネクタの接続状態を表示するのに少し時間がかかる場合があります (テナントに応じて、約 30 分)。

1. [すべてのサービス] ページの [サービスのフィルター] ボックスに「**Microsoft Sentinel**」と入力し、結果の一覧から **[Microsoft Sentinel]** を選択します。 

2. 「Microsoft Sentinel」ページで、Microsoft Sentinel のインスタンスを使用して作成したワークスペース「**SC900-LogAnalytics-workspace**」を選択します。

3. Microsoft Sentinel の最初の手順では、データを収集できるようにします。 左ナビゲーション パネルで、構成の下に一覧表示される「**データ コネクタ**」を選択します。

4. 「データ コネクタ」ページで、「メイン」ウィンドウで下にスクロールして、利用可能なコネクタの広範な一覧を表示します。 「データ コネクタ」ページの「検索」ボックスに、「**Azure**」と入力して、一覧から「**Azure Active Directory**」を選択します。

5. 「Azure Active Directory コネクタ」ウィンドウが開きます。  **[Open connector page]\(コネクタ ページを開く\)** を選択します。

6. 「Azure Active Directory コネクタ」ページで、説明を確認し、ワークブック、クエリ、分析規則テンプレートを含む関連コンテンツをメモします。  

7. [メイン] ウィンドウの [手順] タブには、Azure Sentinel を Azure Active Directory に統合するための前提条件が表示されます。   構成の下で、「**サインイン ログ**」を選択してから、「変更の適用」を選択します (複数のコネクタを選択できます)。

8. 「次のステップ」タブで、推奨されるワークブックの一覧に注意してください。   「推奨されるワークブック」の下で、「**Azure サインイン ログ**」を選択します (追加ワークブックを選択できます)。

9. 「テンプレート」タブが選択された状態 (下線) の「ワークブック」ページで、「**Azure サインイン ログ**」を選択します。 

10. 開く「Azure AD サインイン ログ」ウィンドウで、説明を確認し、「**テンプレートの表示**」を選択します。  画面に右上隅の「**X**」を選択して、テンプレートを終了します。  ページの下部で、「**保存**」を選択してから、「**OK**」を選択して、ワークブックを既定の場所に保存します。

11. [ブック] ページの左上隅の、"ブック" と表示されている場所の上にある、 **[Microsoft Sentinel]** を選択します。 これにより、Microsoft Sentinel の [データ コネクタ] ページに戻ります。

12. 「データ コネクタ」ページの上部に「1 接続中」と表示されるはずです。これは、現在、あなたが Azure Active Directory に接続していることを反映しています。

13. 左ナビゲーション パネルで、「**ワークブック**」を選択します。

14. 「ワークブック」ページで、「検索」ボックスの上に表示される「**自分のワークブック**」タブを選択します。  保存したばかりのワークブックが一覧表示され、データを確認および監視するために利用できます。

15. 次のタスクで使用するため、このページを開いたままにしておきます。

#### <a name="task-4--in-this-task-you-will-walk-through-the-process-of-using-a-built-in-analytics-rule-template-to-create-a-rule-to-get-notified-when-something-suspicious-occurs"></a>タスク 4:このタスクでは、疑わしいことが発生したときに通知するための規則を作成する組み込み規則テンプレートを使用するプロセスを詳しく説明します。

1. 左ナビゲーション パネルで、「**分析**」を選択します。

2. 「分析」ページには、アクティブな規則 (既定で高度なマルチステージ攻撃の検出が有効になっています) が表示され、規則テンプレートにアクセスすることもできます。  「**規則テンプレート**」タブを選択します。利用可能なテンプレートの一覧と一覧をフィルター処理するためのさまざまな方法に注意してください。  Microsoft Sentinel ワークスペース内で組み込み分析アラートを使用すると、疑わしい現象が発生したときに通知を受け取ることができます。

3. 「検索」バーに、「**Azure portal**」と入力します。  「**Azure portal へのログインに失敗しました**」を選択します。  

4. 開くウィンドウで、説明を読み、テンプレートに関連する情報を確認します。  ページの下部にある「**規則の作成**」を選択します。

5. 分析ルール ウィザードで、情報を確認してから、 **[次へ:ルールのロジックを設定 >]** を選択します。

6. 「ルール ロジックの設定」ページでは、新しい分析規則のロジックを定義します。 テンプレートには、いくつかロジックと事前に定義された設定がすでに提供されています。  ページをスクロールして、利用可能な設定を確認します。  既定値のままにします。 **[次へ: インシデントの設定 (プレビュー)>]** を選択します。

7. [インシデントの設定] では、Microsoft Sentinel のアラートを一緒に考慮する必要のあるインシデントにグループ化できます。 この分析規則によりトリガーされるアラートがインシデントを生成するかどうかを設定できます。  既定の設定のままにして、 **[次へ:自動応答>]** を選択します。

8. 「自動応答」タブでは、応答を自動化するためにプレイブックを追加する方法に注意してください。  同様に、インシデントの自動化規則を作成できます。  「インシデントの自動化」の下で、「 **+ 追加**」を選択します。  新しい自動化規則を作成するためのウィンドウが開きます。  このページで作成される自動化規則は、分析規則によりトリガーされます。規則に条件を追加したり、アクションを設定したりできることに注意してください。   「**キャンセル**」を選択して、ウィンドウを終了します

9. **[次へ: レビュー>]** を選択して、選択したテンプレートに基づいて、そのルールに関連するすべての詳細を確認します。 この時点では、「**作成**」を選択して規則を作成するか、ページの右上隅で、「**X**」を選択して、規則を選択せずに終了することを選択できます。

10. 次のタスクで使用するため、このページを開いたままにしておきます。

#### <a name="task-5--in-the-previous-task-you-created-an-analytics-rule-to-be-alerted-of-suspicious-activities--embedded-in-that-wizard-is-the-option-to-automate-the-response-to-an-incident-based-on-the-specific-rule--but-you-can-also-create-automation-rules-by-going-directly-to-the-automation-configuration-option"></a>タスク 5:前のタスクでは、疑わしいアクティビティを警告するための分析規則を作成しました。  そのウィザードに埋め込まれたオプションは、特定の規則に基づいて、インシデントに対する応答を自動化します。  しかし、自動化構成オプションに直接移動して、自動化規則を作成することもできます。

1. 左ナビゲーション パネルで、「**自動化**」を選択します。  

2. **[+ 作成]** を選択します。 ドロップダウンで、新しいプレイブックの追加、または新しい規則の追加を選択する方法に注意してください。  **[新しいルールの追加]** を選択します。  

3. 新しい自動化規則を作成するためのウィンドウが開きます。  ルールに条件を追加したり、アクションを設定したりできることに注意してください。  唯一の違いは、最初の条件がこの自動化規則を適用する分析規則に関連することです。  これは、前のタスクでは、特定の規則に対して、自動化を構成していため、グレイアウトされていました。  「**キャンセル**」を選択して、「新しい自動化規則の作成」ウィンドウを終了します。

4. 次のタスクで使用するため、このページを開いたままにしておきます。


#### <a name="task-6--delete-microsoft-sentinel-resource-group--microsoft-sentinel-is-billed-based-on-the-volume-of-data-ingested-for-analysis-in-microsoft-sentinel-although-the-amount-of-data-ingested-as-a-result-of-this-lab-is-minimal-it-is-recommended-that-you-delete-the-microsoft-sentinel-resource-group-when-you-are-done-exploring-the-features-of-capabilities-of-microsoft-sentinel"></a>タスク 6:Microsoft Sentinel のリソース グループを削除します。  Microsoft Sentinel の課金は、分析のために Microsoft Sentinel に取り込まれたデータの量に基づいて行われます。 このラボの結果として取り込まれるデータの量は最小限ですが、Microsoft Sentinel の機能を確認した後は、Microsoft Sentinel のリソース グループを削除することをお勧めします。

1. 上に「Microsoft Sentinel」と表示されている [Microsoft Sentinel] ページの左上隅で、 **[すべてのサービス]** を選択します。

2. 「フィルター サービス」ボックスに、「リソース グループ」を入力し、表示される一覧で、「**リソース グループ**」を選択します。

3. [リソース グループ] ページで、Microsoft Sentinel を使用して作成したリソース グループ「**SC900-ResourceGroup**」を選択します。

4. ページの中央上で、「**リソース グループの削除**」を選択します。  警告を確認します。  リソース グループ名「**SC900-ResourceGroup**」を入力してから、ページの下部の「**削除**」を選択します。  リソース グループを削除するのに数分かかります。

5. リソース グループが削除されたことを確認し、「ブラウザー」ページを閉じます。 


#### <a name="review"></a>確認

このラボでは、Microsoft Sentinel インスタンスの作成プロセスについて一通り説明しました。  また、Microsoft Sentinel のインスタンスに関連付けられているリソースへのアクセスを確保するために、アクセス許可を設定しました。  Microsoft Sentinel インスタンスが作成された状態で、Microsoft Sentinel をデータ ソースに接続する手順、組み込みの分析を使用して疑わしい現象に関して通知を受け取る方法について一通り説明し、最後に自動化機能の詳細について説明しました。 作成した Microsoft Sentinel のインスタンスに関連付けられたリソース グループを削除して、ラボを締めくくりました。
