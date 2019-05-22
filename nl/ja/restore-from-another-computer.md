---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 同じデータ・センター内の VSI 間でのデータのリストア
{: #restorefromotherVSI}

同じデータ・センターの別のサーバーからデータをリストアすることが必要な場合があります。 この手順は、OS 以外のファイルのファイル・レベルのリストアに適用されますｓ。 システム・イメージをリストアするには、[Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) の手順に従ってください。

このプロセスには、1 番目のサーバーのボールトの場所にアクセスするために 2 番目のサーバーにバックアップ・エージェントを再登録する作業と、**「別のコンピューターからのリストア (Restore from another Computer)」**の実行が伴います。

**前提条件**

- Server1 と Server2 が同じ OS を搭載していること。 クロスプラットフォーム・リストアはサポートされていません。
- Server1 と Server2 でバックアップ・エージェントが構成済みであること。 バックアップ・エージェントの構成について詳しくは、[{{site.data.keyword.backup_notm}} ポータルでのバックアップ・エージェントの構成](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)を参照してください。
- Server1 のバックアップ・ジョブにより、Server1 のボールトの場所にバックアップが作成されていること。

競合を回避するために、両方のサーバーですべてのスケジュール済みタスクを無効にしてください。
{:important}

## Server2 の {{site.data.keyword.backup_notm}} ポータルの開始
{: #startWebCC}

{{site.data.keyword.BluSoftlayer_full}} プライベート・ネットワークにアクセスするには、{{site.data.keyword.BluVPN}} 接続を開始してください。このようにしないと {{site.data.keyword.backup_notm}} ポータル・リンクが機能しません。
{:tip}

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}){: external}にログインして、左上にある**「メニュー」**アイコンをクリックします。 **「クラシック・インフラストラクチャー」**を選択します。 <br/>
   あるいは、[{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. Server2 を選択します。 右向きの展開矢印をクリックし、{{site.data.keyword.backup_notm}} ポータル・リンクを表示します。
4. **「{{site.data.keyword.backup_notm}} ポータル・ログイン」**をクリックし、ブラウザーでポータル・クライアントを開始します。

## ボールトの再登録
{: #reregistervault}

1. **「すべてのエージェント」**をクリックして、変更する特定のエージェントを開きます。
2. **「編集」**をクリックし、**「ボールト設定 (Vault Settings)」**を選択します。
3. **「再登録 (Reregister)」**をクリックし、Server1 を Server2 に接続します。
4. **「ボールト・プロファイルの使用 (Use a Vault Profile)」**エントリーの**「ボールトの再登録 (Re-register Vault)」**画面で、**「ボールト設定の入力 (Enter Vault Settings)」**を選択します。
5. 「ボールト名 (Vault name)」を入力します。これは Server1 のボールト名と同じにします。
6. Server1 のボールトにログインするための、Server1 の資格情報を入力します。
7. **「コンピューターのロード (Load Computers)」**をクリックします。このアクションにより、ボールトの場所に接続されているサーバーが表示されます。
8. **「変更の保存」**をクリックします。
9. プロンプトが出されたら、**「はい」**をクリックしてボールトの再登録を確認します。

## Server1 のバックアップ・ジョブの Server2 のリストア・ジョブとしての実行
{: #runbackuprestore}

1. **「すべてのエージェント」**をクリックします。

   Server1 で定義されたジョブが Server2 の**「ジョブ」**タブにアクセス可能および同期済みとして表示されるようにするには、ページのリフレッシュが必要な場合があります。
   {:tip}
2. **「拡張」**に移動し、**「別のコンピューターからのリストア (Restore from another Computer)」**を選択します。
3. **「別のコンピューターからのリストア (Restore from another Computer)」**画面で、以下のように選択します。
  - ボールト - このエントリーはデフォルトで Server1 のボールトになっています。
  - コンピューター (Computer) - リストア元のバックアップ・コンピューターとして Server1 を選択します。
  - ジョブ - Server1 のバックアップ・ジョブを選択します。
4. **「次へ」**をクリックします。
5. ソース情報を確認します。
  - **「セーフセットの場所 (Safeset location)」**は Server1 のボールトの場所です。
  - **「バックアップ・バージョンの選択 (Select a Backup Version)」**セクションで、Server1 のバックアップをバックアップ・バージョンとして指定します。
  - 暗号化パスワードとは、Server1 のバックアップの作成時に使用したパスワードです。
6. **「次へ」**をクリックします。
7. Server1 のバックアップからリストアする必要があるファイルを選択します。 リストアするファイルとディレクトリーの横のボックスにチェック・マークを付け、**「追加 (Include)」**をクリックして選択内容を保存します。
8. **「次へ」**をクリックしてリストア・オプションに移動します。
9. 「オプション (Options)」で次のようにします。
  - 宛先 - **「元の場所へのリストア (Restore to original location)」**を選択します。
  - ファイルの上書き (File Overwrite) - **「既存のファイルを上書き (Overwrite existing files)」**を選択します。
10. **「リストアの実行 (Run Restore)」**をクリックします。
11. 「プロセスの詳細 (Process Details)」画面に、リストア・ジョブの状況が表示されます。


## リストアの確認
{: #verifyrestore}

1. SSH 経由で Server2 のルートに接続します。
2. ファイルおよびすべてのディレクトリー・エントリーを長形式でリストします。
  ```
  ls -la
  ```
  {: pre}

3. 出力を比較します。

## 通常のバックアップ・スケジュールの再開
{: #resumeschedule}

1. リストアが完了したら、データのリストア元である server1 の登録情報を削除します。
2. 現在の server2 の登録を入力し、スケジュール・タスクを有効にします。
