<!---
---
デモ前のセットアップ: タイトル: 'デモのセットアップ'
---
--->

## WWL テナント - 使用条件

講師が指導するトレーニング配信の一環としてテナントを提供されている場合は、講師が指導するトレーニングでハンズオンラボをサポートする目的でテナントを利用できることに注意してください。

テナントを共有したり、ハンズオンラボ以外の目的で使用したりしないでください。 このコースで使われるテナントは試用版テナントであり、クラスが終了し、拡張機能の対象となっていない場合は、使用したりアクセスしたりすることはできません。

テナントを有料サブスクリプションに変換することはできません。 このコースの一環として取得したテナントは Microsoft Corporation の財産のままであり、当社はいつでもアクセス権とリポジトリを取得する権利を留保します。

## Microsoft 365 テナントのデモ前セットアップ

### Microsoft 365 監査ログとファイルの監視を有効にする

このセットアップ タスクでは、Microsoft 365 の監査ログ機能とファイルの監視機能を有効化します。

1. Microsoft Edge を開きます。 アドレス バーに「**https://admin.microsoft.com**」と入力します。

1. 認可されたラボ ホスト (ALH) から提供された Microsoft 365 テナントの管理者資格情報を使ってサインインします。

1. Microsoft 365 管理センターの左ナビゲーション ペインで、**[すべて表示]** を選択します。

1. [管理センター] で、**[セキュリティ]** を選択します。  新しいブラウザー ページが開き、Microsoft Defender のウェルカム ページが表示されます。  

1. Microsoft Purview コンプライアンス ポータルの左ナビゲーション パネルで、**[すべて表示]** を選択します。

1. 左側のナビゲーション パネルで下にスクロールし、**[システム]** を展開します。  展開された一覧から **[監査]** を選択します。  注: 監査機能には、Microsoft Purview ポータルからもアクセスできます。

1. [監査] ページに移動したら、1、2 分間待機します。  監査が有効でない場合、ユーザーと管理者のアクティビティの記録を開始することを伝える青色バーがページの上部に表示されます。  **[ユーザーと管理者のアクティビティの記録を開始する]** を選択します。  監査が有効になると、青色バーが消えます。  青色バーが表示されておらず、監査が既に有効になっている場合、操作は不要です。  "申し訳ございません。アクティビティが記録されているかどうかを確認できません。ページを更新してみてください" というメッセージが表示され、 ページを更新しても変化がなければ、PowerShell を使用して監査を有効にする必要があります。
    1. タスク バーの 青い [Windows PowerShell] アイコンを右クリックし、**[管理者として実行]** を選択します。
    1. Exchange Online PowerShell モジュールがコンピューターにインストールされていることを確認するには、「**`Get-InstalledModule ExchangeOnlineManagement | Format-List Name,Version,InstalledLocation`**」と入力します。  Exchange OnlineManagement の名前、バージョン、インストールされている場所が表示されます。
    1. 次に、「**`Import-Module ExchangeOnlineManagement`**」と入力してモジュールを読み込みます。
    1. 接続するには、「**`Connect-ExchangeOnline -UserPrincipalName admin@WWLxZZZZZZ.onmicrosoft.com`**」と入力します。  UPN の場合は、ラボの [リソース] タブにある管理者ユーザー名を入力します。
    1. サインインを求めるメッセージが表示されます。  ラボの [リソース] タブにある管理ユーザー名とパスワードを入力します。
    1. 監査をオンにするには、「**`Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true`**」と入力します。 変更が有効になるまでに最長 60 分かかる場合があることを示すメッセージが表示されます。
    1. 有効になるまでに最長 60 分かかる場合がありますが、コマンドが受信されたことを確認するには、「**`Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled`**」と入力します。  監査が有効になっている場合、UnifiedAuditLogIngestionEnabled プロパティの値は true になります。

1. 左側のナビゲーション パネルから、[システム] で **[設定]** を選択します。

1. [設定] ページで、**[クラウド アプリ]** を選択します。   下にスクロールし、[Information Protection] で **[ファイル]** を選択します。

1. まだ有効にしていない場合は、**[ファイルの監視を有効にする]** の横にあるボックスを選択し、**[保存]** を選択します。  

### コンプライアンス管理者ロールを構成する

このセットアップ タスクでは、自分自身を MOD 管理者としてコンプライアンス管理者ロール グループに追加します。

1. 新しい Microsoft Edge ブラウザー タブを開き、アドレス バーに「**https://purview.microsoft.com**」と入力します。 新しい Microsoft Purview ポータルにアクセスするには、**データ フローの開示条件とプライバシーに関する声明に同意する**の横にあるボックスを選択し、**[開始する]** を選択します。  
1. 左側のナビゲーション パネルで、**[設定]** を選択します。
1. 開いたナビゲーション パネルで、**[ロールとスコープ]** を選択してオプションを展開し、**[ロール グループ]** を選択します。
1. 画面の右側にある検索ボックスで、**[コンプライアンス]** という用語を検索します。  **[コンプライアンス管理者]** を選択します。
    1. **編集**を選択します。
    1. **[ユーザーの選択]** を選択します。
    1. MOD 管理者を検索し、**MOD 管理者**の横にあるボックスを選択してから、ページの下部にある **[選択]** ボタンを選択します。
    1. **[次へ]** を選択し、**[保存]** を選択して、最後に **[完了]** を選択します。
1. これで、Microsoft 365 テナントのセットアップが終了し、ブラウザー タブを閉じてもかまいません。

## Azure サブスクリプションのデモ前セットアップ

このセットアップでは、提供されている Microsoft 365 テナントとは別の Azure 環境を使用します。 Microsoft 365 テナントからログアウトし、Azure 資格情報を使用してログインします。

### Azure 仮想マシン

VM が既に作成されていることを確認します。 そうでない場合は、今すぐ設定します。 NSG デモの一部として VM を使います。

1. Microsoft Edge を開きます。  アドレス バーに「**https://portal.azure.com**」と入力し、認可されたラボ ホスター (ALH) から提供された Azure 資格情報を使ってサインインします。  これで、Azure サービスのホーム ページが表示されます。

1. ページの上部にある青い検索ボックスに「**Virtual Machines**」と入力し、検索結果から **[Virtual Machines]** を選びます。

1. VM が既に一覧にある場合はこの後の手順をスキップします。ない場合は作成する必要があります。  **[作成]** を選び、ドロップダウン メニューから **[Azure Virtual Machines]** を選びます。 次のパラメーターを構成します (パラメーターが一覧にない場合は、既定値のままにします)。
    1. リソース グループ: **[新規作成]** を選び、「**LabsSC900**」と入力して **[OK]** を選びます。
    1. 仮想マシン名: 「**SC900-WinVM**」と入力します。
    1. 可用性オプション: ドロップダウンから **[インフラストラクチャ冗長は必要ありません]** を選びます。
    1. セキュリティの種類: ドロップダウンから **[標準]** を選択します。
    1. イメージ: ドロップダウンから **[Windows 11 Pro バージョン 22H2 - x64 Gen2]** (または一覧にある Windows 10 または Window 11 イメージ) を選びます。
    1. サイズ: **[すべてのサイズを表示]** を選び、**[Standard_B1s]** を選んでから、ページの下部にある **[選択]** を選びます。
    1. ユーザー名: 「**SC900-VM-User**」と入力します
    1. パスワード: パスワードを入力して書き留めます。後で必要になります。
    1. パスワードの確認入力: パスワードを再入力します。
    1. パブリック受信ポート: **[なし]** 。
    1. ライセンス: [マルチテナントをホストする権利を持つ有効な Windows 10/11 ライセンスを所有しています] を選びます。  チェックマークが表示されます。
    1. **[次へ: ディスク]** を選びます
    1. OS ディスクの種類: ドロップダウンから **[Standard SSD]** を選びます。
    1. **[次: ネットワーク]** を選びます
    1. NIC ネットワーク セキュリティ グループ: **[なし]** を選びます。  デモの一部として NSG を作成するので、ここでは実行しないでください。
    1. VM が削除されたときにパブリック IP と NIC を削除する: ボックスを選んでチェックマークが表示されるようにします。
    1. **[確認および作成]** を選び、検証に成功したら **[作成]** を選びます。
    1. VM のデプロイが完了したら、ページの上部にある **[ホーム]** を選びます。

1. デモ前セットアップを続行するために、Azure ブラウザー タブを開いたままにします。

### ネットワーク セキュリティ グループ

NSG が既に作成されていることを確認します。 NSG が作成されていない場合は、今すぐ設定してください。ただし、インターフェイスは関連付けず、規則も作成しないでください。 これらの手順は NSG デモの一部として行います。

1. ページ上部の青い検索バーに、「**ネットワーク セキュリティ グループ**」と入力します。 結果から **[ネットワーク セキュリティ グループ]** を選択します ([ネットワーク セキュリティ グループ クラシック] は選択しないでください)。

1. **[ネットワーク セキュリティ グループの作成]** を選びます。 [ネットワーク セキュリティ グループの作成] ページの [基本] タブで、次の設定を指定します。
    1. サブスクリプション: 既定値のままにします (これは、承認されたラボ ホストによって提供される Azure サブスクリプションです)
    1. リソース グループ: **LabsSC900**
    1. 名前: **NSG-SC900**
    1. リージョン: 既定値のままにします。
    1. **[確認および作成]** を選択し、**[作成]** を選択します。
    1. デプロイが完了したら (すぐに完了します)、 **[リソースに移動]** を選びます。

### Microsoft Defender for Cloud

ここでの目的は、単に Microsoft Defender to Cloud に初めてアクセスすることです。 Defender for Cloud に最初のセキュア スコアが反映されるまで最長 24 時間かかることがあるので、これは重要です。  

1. ブラウザーで、[ホーム - Microsoft Azure] タブを開きます。

1. 青色の検索バーに「**Microsoft Defender for Cloud**」と入力し、次に結果のリストから **[Microsoft Defender for Cloud]** を選択します。

1. お使いのサブスクリプションで Microsoft Defender for Cloud に初めてアクセスする場合は、[使用の開始] ページが表示され、アップグレードを求められる場合があります。  ページの下部までスクロールし、**[スキップ]** を選択します。  [概要] ページに移動します。

1. すべてのサブスクリプションでは、既定で基本的な CSPM が有効になっており、セキュア スコアが表示されます。ただし、Defender for Cloud に最初のセキュア スコアが反映されるまで最長 24 時間かかることがあります。

1. ページの上部にある **[ホーム]** を選びます。

1. デモ前セットアップを続行するために、ブラウザー タブを開いたままにします。

### Microsoft Sentinel

Microsoft Sentinel のインスタンスが既に作成されていることを確認します。 そうでない場合は、Microsoft Sentinel のチュートリアル デモの一部として必要になるので、今すぐ設定してください。

1. ブラウザーで、[ホーム - Microsoft Azure] タブを開きます。

1. ページ上部の "Microsoft Azure" と表示されている青色のバーの横にある検索ボックスに、「**Microsoft Sentinel**」と入力し、検索結果から **[Microsoft Sentinel]** を選択します。

1. [Microsoft Sentinel] ページで、**[Microsoft Sentinel の作成] を選択します**。

1. [ワークスペースへの Microsoft Sentinel の追加] ページで、**[新しいワークスペースの作成]** を選択します。

1. [Log Analytics ワークスペースの作成] の [基本] タブに、次の情報を入力します。
    1. サブスクリプション: 既定値のままにします。
    1. リソース グループ: **[新規作成]** を選択してから、名前「**SC900-Sentinel-RG**」を入力し、その後 **[OK]** を選択します。
    1. 名前: **SC900-LogAnalytics-workspace**.
    1. リージョン: **米国東部** (場所に基づいて別の既定のリージョンが選択されている場合があります)。
    1. **[確認および作成]** を選択します (タグは構成されません)。
    1. 入力した情報を確認してから、**[作成]** を選択します。
    1. 1 つのワークスペースが一覧表示されるまでに、1 から 2 分かかる場合があります。それでも表示されない場合は、**[更新]** を選択してから、**[追加]** を選択します。

1. 新しいワークスペースが追加されると、[Microsoft Sentinel |ニュース & ガイド] ページが表示され、Microsoft Sentinel の無料試用版がアクティブ化されていることを示します。  **[OK]** を選択します。

### 確認

このセットアップでは、Microsoft 365 テナントで監査ログ機能を有効にし、Azure 環境で VM が事前構成されていることを確認する機能も作成しました。 また、Defender for Cloud と Microsoft Sentinel 環境も準備しました。
