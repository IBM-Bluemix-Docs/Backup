---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configure BMR, bmr plug-in, bmr plugin, configuration

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# BMR バックアップ・ジョブの構成
{: #configureBMR}

BMR バックアップを作成するには、BMR プラグインを購入する必要があります。 BMR は Windows ベアメタル・サーバー用のみがあります。 VSI には BMR オプションはありません。 詳しくは、[ベアメタル・リストア・プラグインについて](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)を参照してください。
{:important}

## {{site.data.keyword.backup_notm}} ポータルの開始
{: #startWebCCBMR}

{{site.data.keyword.backup_notm}} ポータルを開始するには、{{site.data.keyword.cloud}} プライベート・ネットワークに接続している必要があります。
{:important}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. バックアップ対象のファイルが存在するサーバーを選択します。 右向きの展開矢印をクリックし、{{site.data.keyword.backup_notm}} ポータル・リンクを表示します。
4. **「{{site.data.keyword.backup_notm}} ポータル・ログイン」**をクリックし、ブラウザーでポータル・クライアントを開始します。

   {{site.data.keyword.backup_notm}} ポータルが開始されない場合は、VPN 接続に問題がある可能性があります。 また、送信しようとしているフォームがセキュアではないというメッセージが表示されることもあります。 このことは予期されることであるため、フォームを送信して続行します。
   {:tip}

## BMR バックアップ・ジョブの構成

1. 左のナビゲーション・ペインで、**「すべてのエージェント」**をクリックして、現在の {{site.data.keyword.backup_notm}} エージェントを表示します。
2. **「これは構成対象の新しいエージェントです (This is a new Agent I would like to configure)」**をクリックします。
3. 作成するジョブのジョブ名とジョブ記述を入力します。
4. **「バックアップ・ソース・タイプ (Backup Source Type)」**で、ファイル・システム・タイプを選択し、次に、**「次へ」**をクリックします。
5. **「ジョブ・タイプの選択 (Job Type Selection)」**メニューが表示されます。 **「ベアメタルのリストア (Bare Metal Restore)」**の隣のボックスをチェックし、**「次へ」**をクリックして続行します。
6. 確認ウィンドウでは**「はい」**をクリックします。
7. 画面のバックアップ・セットに、新しいジョブが表示されるようになります。 **「次へ」**をクリックします。
8. 画面に、暗号化オプションとバックアップの拡張オプションが表示されます。 通常、これらのオプションは必要ありません。 **「次へ」**をクリックします。   
9. **「スケジュールの作成 (Create a schedule)」**ページには 2 つの選択項目があります。
   - **「次へ」**をクリックして手動ジョブを作成し、新しいジョブの実行に進みます。
   - **「追加」**をクリックして時刻ベースのバックアップ・ジョブをスケジュールします。
     1. バックアップを実行する曜日と時刻を選択します。
     2. 保存スキームを選択します。

        保存スキームについて詳しくは、[FAQ](/docs/infrastructure/Backup?topic=Backup-faqs) を参照してください。
        {:tip}
     3. バックアップ・スケジュールを構成した後、**「OK」**をクリックして保存します。 スケジュールに入れたジョブが、スケジュール済みのジョブのリストに追加されます。
10. バックアップ・ジョブのボールトを選択し、**「変更の保存」**をクリックします。


## BMR バックアップ・ジョブの実行

  - 時刻ベースのバックアップ・ジョブをスケジュールした場合は、他に作業を行う必要はありません。 ジョブはスケジュールに従って自動的に実行されます。
  - 手動ジョブを (時刻ベースのスケジュールなしで) セットアップした場合は、ジョブ・リストでその行を選択し、**「バックアップの実行 (Run backup)」**をクリックすることによって実行できます。 <br/> 時刻ベースのジョブについては、**保存スキーム**と**バックアップの拡張オプション**を選択できます。 構成について選択した後、**「バックアップの開始 (Start backup)」**をクリックして、ジョブを開始します。
