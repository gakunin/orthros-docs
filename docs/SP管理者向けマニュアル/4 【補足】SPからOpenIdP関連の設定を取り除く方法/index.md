>[!IMPORTANT]
>本ドキュメントは「OpenIdPからOrthrosへの移行につきましてSP設定追加のお願い」として過去に提供していたものですが、移行期間が終了し不要となりましたので、最後のフェーズのSPからOpenIdP関連の設定を取り除く部分のみ残し他の部分は削除しております。

#### 7\. 2024/3/末 Embedded DSからOpenIdPの削除

Embedded DSからOpenIdPのエントリを削除します。加えて、OpenIdPのメタデータ読み込みを停止します。  
変更箇所については以下を参照してください。  
⇒[Embedded DSへのOrthrosを追加設定](/docs/SP管理者向けマニュアル/2%20Orthrosとの接続依頼方法について/2%20Embedded%20DSへのOrthrosを追加設定.md)  
  
JavaScriptファイル内の配列 wayf\_additional\_idps に以下のような配列要素があると思いますので、当該行だけを削除してください。

```
    {name:"OpenIdP",
    entityID:"https://openidp.nii.ac.jp/idp/shibboleth",
    SAML1SSOurl: "https://openidp.nii.ac.jp/idp/profile/Shibboleth/SSO"},
```
また、/etc/shibboleth/shibboleth2.xml に以下のような行があると思いますので、削除した上でshibdをrestartしてください。

```
        <MetadataProvider type="XML" path="/etc/shibboleth/metadata/openidp-metadata.xml"/>
```
>[!WARNING]
>上記はOpenIdPのメタデータ読み込み設定です。Orthrosメタデータのほうを削除しないようご注意ください。

  

  

以上
