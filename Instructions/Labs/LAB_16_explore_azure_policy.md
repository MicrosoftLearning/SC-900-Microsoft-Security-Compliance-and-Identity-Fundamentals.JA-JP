---
lab:
  title: Azure Policy を探索する
  module: 'Module 4 Lesson 6: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
ms.openlocfilehash: 23e8f4f8417367a16cbd41496428918ca219fa40
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557520"
---
# <a name="lab-explore-azure-policy"></a>ラボ:Azure Policy を探索する

## <a name="lab-scenario"></a>ラボのシナリオ

Azure Policy は、組織の標準を適用し、コンプライアンスを大規模に評価するのに役立ちます。 Azure Policy では、Azure 内のリソースのプロパティをビジネス ルールと比較して、それらのリソースを評価します。 このラボでは、Azure ポリシーのランディング ページの詳細に確認することから始めます。 Azure ポリシー ページを最初に詳細に確認した後、ポリシーを作成し、そのポリシーの影響を確認します。

**推定時間**:20 ～ 25 分

### <a name="task-1"></a>タスク 1

Azure ポリシー ページを簡単に確認します。

1. Microsoft Edge を開きます。 アドレス バーに、「**portal.microsoft.com**」と入力します。

1. 管理者の資格情報でサインインします。
    1. [サインイン] ウィンドウで、「 **admin@WWLxZZZZZZ.onmicrosoft.com** 」と入力してから、 **[次へ]** を選択します (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。

    1. ラボ ホスティング プロバイダーから提供される管理者のパスワードを入力します。 **[サインイン]** をクリックします。
    1. サインインしたままにするかどうかを尋ねられたら、「**はい**」を選択します。

1. これで、Azure portal が表示されます。  検索ボックスのページ上部にある「Microsoft Azure」と表示されている場所の隣の青色バーに、「**ポリシー**」と入力し、検索結果で、「**ポリシー**」を選択します。 これにより、ダッシュボード ビューを表示する「ポリシー ホーム」ページが開きます。  情報が表示されているスコープは、このラボの一部として使用している Azure Pass に適用されます。   ダッシュボードで利用可能な情報に注意してください。

1. ASC の既定値という項目があり、そのスコープは Azure Pass – スポンサーシップです (ASC は Azure Security Center の略です。現在は Microsoft Defender for Cloud と呼ばれています)。   「**ASC の既定値**」を選択します。

1. ページ上部の「Essentials」の下に、名前、説明、その他の重要な情報が表示されます。  説明を読みます (マウスで説明にカーソルを合わせます)。 注:説明フィールドでは、名前が Microsoft Defender for Cloud に変更された Azure Security Center を参照します。

1. ダッシュボードによって提供される情報が、選択された項目である ASC 既定値を反映するように更新されていることに注意してください。 この ASC 既定値は、Azure セキュリティ ベンチマークのイニシアチブ定義です。  イニシアチブ定義は、単一の包括的なゴールを達成することを目的として調整されたポリシー定義のコレクションであることを思い出してください。 情報は、グループ、ポリシー、非準拠のリソース、またはイベントごとに表示できます。

1. ウィンドウの右上隅にある **[X]** を選択して、ASC ページを終了し、ポリシーのホームページに戻ります。

1. 左ナビゲーション パネルで、「**作業の開始**」を選択します。  ここでは、組み込みポリシーを参照してポリシーを大規模に割り当てるオプションなど、さまざまなオプションを表示できます。環境のカスタム ポリシー定義を作成したり、ポリシー割り当てを推奨したりできます。

1. 左ナビゲーション パネルで、「**コンプライアンス**」を選択します。  「概要」ページと同様に、ここでは、一覧表示されたポリシーやイニシアチブのコンプライアンス状態を表示できます。  「ポリシー コンプライアンス」ページで、ポリシーまたはイニシアチブを割り当てることもできます (次のタスクでポリシーを割り当てます)。

1. 左ナビゲーション パネルで、「**修復**」を選択します。  このページには、非準拠のリソースがあるポリシーの一覧が表示されます。  「修復」ページでポリシーを選択することにより、ポリシーを修復するタスクの作成をトリガーできます。  

1. 左ナビゲーション ペインで、「作成」の下の「**割り当て**」を選択します。  ここから、現在のポリシーやイニシアチブの割り当てを確認したり、ポリシーの割り当てやイニシアチブを作成したりできます。  次のタスクでこれに戻ります。  

1. 左ナビゲーション パネルで、「**定義**」を選択します。  このページで、「**パスワードのセキュリティ設定が安全でない監査マシン**」を選択します。  これはイニシアチブの定義であり、多くのポリシーが含まれています。  ポリシー定義がどのように表示されるかを表示するには、「**パスワードの最長有効期限が 70 日でない Windows マシンの監査**」を選択します。  ページが開くと、Java Script Object Notation (JSON) 構造で実際のポリシー定義が表示されます。   赤字のテキストからわかるように、ポリシー定義には、表示名、説明、パラメーター、ポリシー規則などを定義する要素が含まれています。 何も変更しないでください。  

1. ページの右上隅の「**X**」を選択して、「ポリシー定義」ページを終了します。

1. ページの右上隅の「**X**」を選択して、「イニシアティブ義」ページを終了します。

1. 次のタスクのために、このブラウザー タブ (ポリシー – Microsoft Azure) を開いたままにします。

### <a name="task-2"></a>タスク 2

このタスクでは、リソース グループにタグを要求するための基本的なポリシー割り当てを作成します。

1. ブラウザー タブ「ポリシー – Microsoft Azure」を開きます。

1. 左ナビゲーション パネルで、「作成」の下の「**割り当て**」を選択します。

1. ページの上部で、「**ポリシーの割り当て**」を選択します。

1. 「ポリシーの割り当て」ウィザードが開き、管理者がポリシーを割り当てるプロセスをガイドします。  「ポリシー定義」フィールドの隣の **省略記号** を選択します。  使用可能なポリシー定義の一覧が表示されます。  

1. 「検索」バーに「**タグ**」と入力します。

1. 検索結果で、「**リソース グループにタグを要求する**」を選択してから (下にスクロールする必要がある場合があります)、「**選択**」を押します。  注: このポリシーの効果は、要件を満たさない新しいリソース グループの作成を拒否することです。  

1. 既定の割り当て名に注意してください。  名前はそのままにして、ページの下部で、「**次へ**」を選択します。

1. 「タグ名」フィールドに「**環境**」と入力してから、「**次へ**」を選択します。

1. 既定の修復設定はそのままにして、 **[次へ]** を選択します。

1. 非準拠メッセージに「**環境タグが必要です**」と入力し、「**次へ**」を選択します。 注: このメッセージは、ポリシー割り当ての前に作成され、「環境」タグがないリソース グループの非準拠の理由として表示されます。  ポリシーの作成後に作成されたリソースグループの場合、「環境」タグがないと、リソース グループの作成は拒否されます。

1. ポリシーの割り当てを確認してから、「作成」を選択します。  ポリシーすぐに表示されない場合は、「**更新**」を選択します 注: ポリシーが有効になるまで、最大で 30 分かかる可能性があります。

1. 画面の右上隅の「**X**」を選択して、「ポリシーの割り当て」ページを終了します。

1. これで、Azure サービスの「ホーム」ページが表示されます。  次のタスクで必要なため、このページを開いたままにしておきます。

### <a name="task-3"></a>タスク 3

このタスクでは、タグのないリソース グループを Azure で作成することにより、Azure ポリシーの割り当ての影響を確認します。次に、リソース グループを更新してタグを含めます。  注: 前のタスクで作成したポリシーが有効になるまでに最大 30 分かかる場合がありますが、通常はそれよりも速く終了します。

1. ブラウザー タブ「ホーム – Microsoft Azure」を開きます。

1. ページの上部、Azure Services と表示されている場所の下で、「**リソース グループ**」を選択します。

1. ページの左下隅で、「 **+ 作成**」を選択します。

1. 「リソース グループの作成」の「基本」タブで、「サブスクリプション」フィールドをそのままにして、「Azure Pass - スポンサーシップ」を選択します。

1. 「リソース グループ」フィールドに、「**SC900-Labs**」と入力します。

1. [リージョン] の設定を既定のままにして、 **[次へ:タグ]** を選択します。

1. タグの「名前と値」フィールドは空のままにします。  データを入力せずに、「**Review + create**」を選択します。

1. 検証に合格したことが表示され (タグの名と値はウィザードの必須フィールドではありません)、「**作成**」を選択します。

1. 画面上部に「リソース グループの作成に失敗しました。 エラーの詳細を表示します」という失敗メッセージが表示されます。  「**エラーの詳細を表示**」を選択します。 Azure ポリシーの一部である条件が満たされていないため、コンプライアンス違反のため、作成中のリソース グループがブロックされました。

    注: 失敗メッセージが表示されず、リソース グループが作成された場合は、ポリシーがまだ有効になっていないことが原因です。  前のタスクで作成したポリシーの「ポリシー」ページに移動します。ポリシーが有効になると、リソースが準拠していないことがわかります。  詳細ページには、コンプライアンス違反のメッセージが含まれます。 エラーが発生した場合は、デプロイを修復する方法を次の手順に示します。

1. エラーの概要には、「リソース「SC900-Labs」がポリシーによって許可されていません」というエラーの種類が表示されます。  画面の左上隅の「**X**」を選択して、このウィンドウを閉じます。

1. [リソース グループの作成] ウィンドウで、 **[前へ]** を選択します。

1. リソース グループの作成の「タグ」ページに戻ります。  [名前] フィールドに「環境」と入力し、[値] フィールドに「**SC900-Labs**」と入力して、 **[次へ:確認と作成 >]** を選択します。

1. タグを確認し、「**作成**」を選択します。

1. リソース グループが一覧表示されます。  タグがリソース グループで提供されたため、Azure ポリシーの一部として含まれている条件が満たされました。  リソース グループはポリシーに準拠しています。

1. 終了する前に、Azure ポリシーを削除してください。
    1. ページの左上隅で、「ホーム」を選択して、Azure ホームページに戻ります。

    1. Azure サービスと表示されている場所の下で、「Azure ポリシー」を選択します。
    1. ページの中央に、Azure ポリシー/イニシアチブの割り当ての一覧が表示されます。  ポリシー割り当ての省略記号を選択します。リソース グループにタグが必要です。次に、「割り当ての削除」を選択します。
    1. 割り当てを削除してよいか確認するメッセージが表示されます。  「はい」を選択します。

### <a name="review"></a>確認

このラボでは、Azure ポリシーのランディング ページを確認しました。 Azure ポリシー ページを最初に詳細に確認した後、ポリシーを作成するプロセスを行い、そのポリシーの影響を確認することができました。
