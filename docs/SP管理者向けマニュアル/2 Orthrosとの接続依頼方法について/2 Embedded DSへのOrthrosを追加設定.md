>[!NOTE]
>先にOrthrosの接続依頼（[1 Orthrosとの接続依頼方法](1%20Orthrosとの接続依頼方法.md)参照）が必要です

下記手順は典型的なShibboleth SPの場合となっておりますので、そうでない場合は適宜読み替えてください。

目次

- [1.Orthrosメタデータのダウンロード](#1orthrosメタデータのダウンロード)
- [2.Orthrosメタデータの自動更新設定](#2orthrosメタデータの自動更新設定)
- [3.wayf\_additional\_idpsへの追加](#3wayf_additional_idpsへの追加)

## 1.Orthrosメタデータのダウンロード

接続する環境に合わせて以下よりメタデータをダウンロードしてください

表1 メタデータURL一覧
| 環境 | メタデータURL |
| --- | --- |
| 本運用環境 | https://core.orthros.gakunin.nii.ac.jp/metadata/orthros-idp-metadata.xml |
| テスト環境 |https://core-stg.orthros.gakunin.nii.ac.jp/metadata/orthrosstg-idp-metadata.xml |

## 2.Orthrosメタデータの自動更新設定

* 証明書を格納するディレクトリを作成します

```
# mkdir /etc/shibboleth/cert
```
  
* 検証に用いるメタデータ署名検証用証明書をダウンロードして、/etc/shibboleth/cert/ に置きます  
メタデータ署名検証用証明書は、接続する環境に合わせて以下よりダウンロードしてください  
真正性を確実にするために取得した証明書のフィンガープリントが下記と一致するのを確認することをお勧めします
  
表2-1 メタデータ署名検証用証明書（署名証明書）URL一覧

| 環境 | メタデータ署名検証用証明書（署名証明書） | フィンガープリント |
| --- | --- | --- |
| 本運用環境 | https://core.orthros.gakunin.nii.ac.jp/metadata/orthros-signer-2025.cer | SHA1=76:0E:BD:2E:1F:D9:7A:A6:AE:8C:6A:BF:A1:39:61:DF:4A:4E:C8:60<br><br>SHA256=C7:AE:69:98:AC:E7:6A:C2:83:CC:5F:99:0A:C1:3C:A1:62:3D:F6:84:AA:7B:08:30:37:2D:DA:6B:82:AB:BA:44 |
| テスト環境 | https://core-stg.orthros.gakunin.nii.ac.jp/metadata/orthrosstg-signer-2025.cer | SHA1=EB:A5:7E:1B:52:49:40:A4:9C:AD:70:24:60:32:3E:71:8A:F1:F4:76<br><br>SHA256=A3:AF:64:82:1B:BF:C9:28:E9:E7:0D:5E:7C:04:41:1C:2D:87:47:1F:45:1D:24:32:B6:31:FF:91:B5:71:53:0D |

※証明書のフィンガープリントは、例えば以下のコマンドを実行することで確認できます。

```
$ openssl x509 -noout -fingerprint -sha256 -in orthros-signer-2025.cer
SHA256 Fingerprint=...
```
  
* メタデータを自動的にダウンロードする設定を行います

 /etc/shibboleth/shibboleth2.xml ファイルに以下を追加します
```
<!-- Example of remotely supplied batch of signed metadata. -->
<MetadataProvider type="XML" validate="true"
        url="https://core.orthros.gakunin.nii.ac.jp/metadata/orthros-idp-metadata.xml"
                            <!-- ↑参照先のURLを設定 -->
        backingFilePath="orthros-metadata.xml" maxRefreshDelay="7200">
    <MetadataFilter type="Signature" certificate="/etc/shibboleth/cert/orthros-signer-2025.cer" verifyBackup="false"/>
                                                        <!-- ↑自動更新メタデータの検証用証明書設定 -->

    <TransportOption provider="CURL" option="64">1</TransportOption>
    <TransportOption provider="CURL" option="81">2</TransportOption>
    <TransportOption provider="CURL" option="10065">/etc/pki/tls/certs/ca-bundle.crt</TransportOption>
                 <!-- ↑ HTTPSサイトの証明書検証を有効化（メタデータのダウンロード時に利用） -->
</MetadataProvider>
```
※メタデータのURLと検証用証明書は接続する環境に合わせて修正してください
  
以下のローカル読み込みの定義がある場合は削除してください（Orthrosのメタデータ署名検証機能提供以前に接続設定を行っている場合）

```
<MetadataProvider type="XML" path="/etc/shibboleth/metadata/orthros-idp-metadata.xml"/>
```
## 3.wayf\_additional\_idpsへの追加

Embedded DSの設定が記述されているJavaScriptファイルの wayf\_additional\_idps に以下を追加します

```
{name:"＜表3-1 参照＞", entityID:"＜表3-2 参照＞"}
```
  
表3-1 nameに設定する値

| 環境 | nameに設定する値 |
| --- | --- |
| 本運用環境 | Orthros |
| テスト環境 | Orthros-Test |
  
表3-2 entityIDに設定する値

| 環境 | entityIDに設定する値 |
| --- | --- |
| 本運用環境 | https://core.orthros.gakunin.nii.ac.jp/idp |
| テスト環境 | https://core-stg.orthros.gakunin.nii.ac.jp/idp |
  
  
以下のようにDSに所属機関選択肢として「Orthros」が表示され、「Orthros」を選択後にOrthrosのサインイン画面が表示され、認証可能であれば設定完了となります  
（Orthros接続申し込みが未処理の場合、Orthrosの画面が異なる場合があります）

<画面イメージ>

a.DS画面

<img src="/images/image-2023-5-8_17-53-14.png" width="80%">

  
ｂ.Orthrosサインイン画面

<img src="/images/image-2025-11-26_11-36-25-1.png" width="30%">

