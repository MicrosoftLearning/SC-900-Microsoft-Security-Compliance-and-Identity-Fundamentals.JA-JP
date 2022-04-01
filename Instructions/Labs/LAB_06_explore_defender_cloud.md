---
lab:
  title: Microsoft Defender for Cloud について調べる
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: 208e11a7e82497fbb900b4fa024fb6fb367d458e
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894226"
---
# <a name="lab-explore-microsoft-defender-for-cloud"></a>ラボ:Microsoft Defender for Cloud について調べる

## <a name="lab-scenario"></a>ラボのシナリオ
このラボでは、Microsoft Defender for Cloud の詳細を確認し、Azure Secure Score を使用して、組織のセキュリティ体勢を改善する方法について学習します。

**推定時間**:30 分

#### <a name="task-1-in-this-task-you-will-take-a-brief-tour-of-microsoft-defender-for-cloud"></a>タスク 1:このタスクでは、Microsoft Defender for Cloud について簡単に確認します。
1.  Microsoft Edge を開きます。 アドレス バーに、「**portal.azure.com**」と入力します。

1. 管理者の資格情報でサインインします。
    1. [サインイン] ウィンドウで、「 **admin@WWLxZZZZZZ.onmicrosoft.com** 」 (ZZZZZZ はラボ ホスティング プロバイダーにより提供される一意のテナント ID です) と入力してから、 **[次へ]** を選択します。
    1. ラボ ホスティング プロバイダーから提供される管理者のパスワードを入力します。 **[サインイン]** をクリックします。
    1. サインインしたままにするかどうかを尋ねられたら、「**はい**」を選択します。

1. Microsoft Azure の隣の画面の左上隅で、「ポータル メニューの表示」アイコン (3 本の水平方向のラインのあるアイコンで、「ハンバーガー」アイコンとも呼ばれます) を選択した後、左側のナビゲーション パネルの [お気に入り] から **[Microsoft Defender for Cloud]** を選択します。  [お気に入り] にこれが表示されていない場合は、検索ボックスに「**Microsoft Defender for Cloud**」と入力し、結果の一覧から **[Microsoft Defender for Cloud]** を選択します。

1. Microsoft Defender for Cloud の [概要] ページに表示される情報を確認してください。  

1. ページの上部に青色の情報ボックスが表示される場合があります。これは、限定情報が表示されていることを示しています。  「**ここをクリック**」を選択します。
    1. テナント全体を表示できるようにするには、自分自身に必要なロールを割り当てます。  「**セキュリティ管理者**」を選択してから、ページの下部で、「**アクセスの取得**」を選択します。
    1. 「ルート管理グループが存在しない」ことを示すメッセージが表示される場合があります。  説明に従い、システムがあなたのためにグループを作成します。  完了までに最大 15 分かかる場合があります (ただし、通常はそれほどかかりません)。  アクセスが付与されたら、ページの左上隅 ([アクセス許可の取得] の上) で、 **[Microsoft Defender for Cloud]** を選択し、Microsoft Defender for Cloud の概要ページを更新します。

1. ページの上部の情報には、Azure サブスクリプションの数、評価されたリソースの数、アクティブな推奨事項の数、セキュリティ アラートが含まれます。  ページの本文には、セキュア スコア、規制コンプライアンス、分析情報などを表す複数のカードがあります。  

1. ページの上部で、「**評価されたリソース**」を選択します。  (これは、Microsoft Defender for Cloud のホーム ページの左ナビゲーション パネルで、[インベントリ] を選択した場合と同じであることに注意してください)。
    1. これにより、Azure Pass サブスクリプションを表示する「**インベントリ**」ページにリダイレクトされます。  「**Azure Pass – スポンサーシップ**」を選択します。
    1. 「リソース正常性」ページには、推奨事項の一覧が表示されます。  利用可能な一覧で、「**複数の所有者がサブスクリプションに割り当てられている必要があります**」を選択します。
    1. 修復手順の隣にあるドロップダウン矢印を選択します。 詳細な修復手順が措置を講じるためのオプションに沿ってどのように提供されるかについて注意してください。  
    1. 画面の左上隅にある **[Microsoft Defender for Cloud]** を選択して、Microsoft Defender for Cloud の [概要] ページに戻ります。

1. ページの上部で、「**アクティブな推奨事項**」を選択します。  (これは、Microsoft Defender for Cloud のホーム ページの左ナビゲーション パネルで、[推奨事項] を選択した場合と同じであることに注意してください)。
    1. 「推奨事項」ページには、セキュア スコア ダッシュボードが表示されます。
    1. セキュア スコア ダッシュボードの下には、制御の一覧があります。 各セキュリティ制御は、軽減する必要のあるセキュリティ リスクを表し、その制御に関連付けられている最大スコア、現在のスコア、潜在的なスコアの増加、およびリソースの状態に関する情報も含まれています。  
    1. 「**MFA を有効にする**」などの制御の 1 つを選択します。  「**サブスクリプションの所有者権限を持つアカウントで MFA を有効にする必要がある**」など、サブ項目の 1 つを選択します。  開いたページに、説明、修復手順、および影響を受けるリソースが表示されます。 画面の右上隅の「**X**」を選択して、このページを終了します。
    1. 画面の右上隅の「**X**」を選択して、「推奨事項」ページを終了し、「概要」ページに戻ります。

1. 「メイン」ページで、「**規制コンプライアンス**」を選択します。 「規制コンプライアンス」ページには、コンプライアンス制御の一覧が表示されます。  各制御の下に、Azure でクラウド ソリューションをセキュリティで保護する方法に関する推奨事項を提供する Azure セキュリティ ベンチマークに基づく一連の評価が表示されます。
    1. **[IM.Identity Management]\(IM. ID 管理\)** を選択してから、 **[IM-6 Use strong authentication controls]\(IM-6 強力な認証制御を使用する\)** を選択します。  一覧には、コンプライアンス体制を改善するために講じることができる顧客責任アクションが表示されます。
    1. 画面に右上隅で **[X]** を選択してページを閉じ、Microsoft Defender for Cloud の概要ページに戻ります。 
    1. 次のタスクで使用するため、Microsoft Defender for Cloud の概要ページを開いたままにしておきます。


#### <a name="task-2-in-this-task-you-will-navigate-to-azure-secure-score-and-explore-recommendations-that-can-improve-your-secure-score"></a>タスク 2:このタスクでは、Azure セキュア スコアに移動して、セキュア スコアを改善できる推奨事項の詳細を確認します。 

1. Microsoft Defender for Cloud の概要ページで、 **[セキュア スコア]** カードを選択します。
1. 「**Azure Pass – スポンサーシップ**」を選択します。  セキュア スコアをメモしてください。
1. 推奨事項ページで、 **[セキュリティのベスト プラクティスを実装する]** を選択して一覧を展開します。 リソース正常性の状態が赤色で表示されていることに注意してください。
1. リソース正常性状態が赤色として表示される項目「**複数の所有者がサブスクリプションに割り当てられている必要があります**」を選択します。 
1. **[影響を受けるリソース]** と表示されている場所の下で、異常なリソースが選択されている (下線が引かれている) ことを確認し、一覧に表示された Azure サブスクリプションを選択します。
1. 「アクセス制御 (IAM)」ページの上部で、「 **+ 追加**」を選択してから、ドロップ ダウンで。「**ロール割り当ての追加**」を選択します。
    1. ページの左側から **[所有者]** (一覧の最初の項目) を選択して、行が灰色で強調表示された状態にします。その後、ページの下部にある **[次へ]** を選択します。
    1. [メンバー] と表示されている場所の横で、 **[+ メンバーの選択]** を選択します。 
    1. 画面の右側に表示される [メンバーの選択] ウィンドウで、 **[Alex]** を選択し、ページの下部にある **[選択]** を押します。  
    1. [ロールの割り当ての追加] ページで、Alex がメンバーとして表示されていることを確認し、 **[次へ]** 、 **[確認 + 割り当て]** の順に選択します。
    1. 状態が更新されるまで最大 24 時間かかる場合があります。その後、アクセスとアクセス許可グループの管理内のすべての項目が満たされるとき、セキュア スコアも更新されます。
    1. ページの左上隅 ([Azure Pass] の上) で、 **[Microsoft Defender for Cloud]** を選択して Microsoft Defender for Cloud の概要ページに戻ります。
1. 後続のタスクのために、このページを開いたままにしておきます。


#### <a name="task-3--recall-that-microsoft-defender-for-cloud-is-offered-in-two-modes-without-enhanced-security-features-free-and-with-enhanced-security-features-which-are-available-through-the-microsoft-defender-for-cloud-plans-in-this-task-you-discover-how-to-enabledisable-the-various-microsoft-defender-for-cloud-plans"></a>タスク 3:先にも説明したように、Microsoft Defender for Cloud は、強化されたセキュリティ機能なし (無料) と、強化されたセキュリティ機能ありの 2 つのモードで提供されています (Microsoft Defender for Cloud プランを通じて利用できます)。 このタスクでは、各種の Microsoft Defender for Cloud プランを有効または無効にする方法について確認します。

1.  Microsoft Defender for Cloud の概要ページで、左側のナビゲーション パネルから **[環境設定]** を選択します。
1. [テナント ルート グループ] の横にある大なり等号 **>** を選択して表示を展開し、 **[Azure Pass - スポンサーシップ]** を選択します ([テナント ルート グループ] を直接選択しないでください。別のページに移動します)
1.  [Defender プラン] ページで、すべてを有効にする方法と、個々の Defender プランを選択する方法を確認します。 設定は、すべてのプランがオフに設定された状態のままにしてください。
1.  「ブラウザー」タブを閉じて、Azure portal を終了することができます。


#### <a name="review"></a>確認
このラボでは、Microsoft Defender for Cloud の詳細を確認し、Azure Secure Score を使用して、組織のセキュリティ体勢を改善する方法について学習しました。

