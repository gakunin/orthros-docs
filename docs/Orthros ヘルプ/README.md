>[!NOTE]
>**＜SP管理者様向けのご案内となります＞**
>
>1.概要
>
>先般よりご案内 **※1** しておりましたとおり、  
現在のOrthrosメタデータ証明書は2026/3/31に期限を迎える予定です。  
これに伴い、新しい証明書への切り替え作業を実施しております。
> 
>本日（3/9）、**本運用環境**にて現証明書を新証明書への切り替え作業を実施いたしました。  
つきましては、本運用環境と接続している各SP管理者様におかれましては、テスト環境にてOrthros認証の連携確認の実施をお願い申し上げます。  
>詳細なスケジュールおよび必要な対応内容につきましては、以下をご参照ください。
>
>※1：[「お知らせ一覧」2025/9/18掲載分](/docs/お知らせ一覧/README.md#20250918掲載)  
※2：[「お知らせ一覧」2025/11/26掲載分](/docs/お知らせ一覧/README.md#20251126掲載)  
※3：[「お知らせ一覧」2026/02/02掲載分](/docs/お知らせ一覧/README.md#20260202掲載)  
※4：[「お知らせ一覧」2026/03/02掲載分](/docs/お知らせ一覧/README.md#20260302掲載)  
>
>2.スケジュール（再掲）
>
><img src="/images/image-2025-7-18_15-31-1.png" width="60%">
>
>※新証明書への切り替えをテスト環境から先に実施、1週間後に本運用環境を実施としたスケジュール  
>  
>3.対応内容  
>ご自身が管理されているSPからOrthros経由でログインいただき、問題なく認証・接続できることをご確認ください。
>　[**【お知らせ一覧】**](/docs/お知らせ一覧/README.md)

## **目次**

* [機能について](#機能について)
* [SPについて](#spについて)
* [よくあるご質問](#よくあるご質問)
* [お問い合わせ](#お問い合わせ)

## **機能について**

* [**Orthrosについて**](https://ui.orthros.gakunin.nii.ac.jp/ja/pages/about)
* [**プライバシーポリシー**](https://ui.orthros.gakunin.nii.ac.jp/ja/pages/privacy-policy)
* [**利用規約**](https://ui.orthros.gakunin.nii.ac.jp/ja/pages/terms-of-use)
* [**Orthrosの利用方法**](/docs/利用マニュアル/README.md)

## **SPについて**

* [**OrthrosでログインできるSPについて**](/docs/現在OrthrosでログインできるSP/README.md)
* [**SP管理者向けマニュアル**](/docs/SP管理者向けマニュアル/README.md)


## **よくあるご質問**

#### Q.OpenIdPからOrthrosへの移行作業を忘れていました

<details>

**<summary>ご回答</summary>**

移行期間（2023年10月〜2024年3月）は終了となっておりますので、以下のご対応をお願いします。

・学認クラウドゲートウェイサービスの場合

[Q.学認クラウドゲートウェイサービス上のメンバーが移行期間（2023年10月〜2024年3月）に移行せずに移行期間が終了した場合はどうなりますか？](/docs/よくある問合せ一覧/README.md#q学認クラウドゲートウェイサービス上のメンバーが移行期間2023年10月2024年3月に移行せずに移行期間が終了した場合はどうなりますか)を参照

・学認クラウドゲートウェイサービス以外のSPの場合

「[Orthrosアカウント作成](/docs/利用マニュアル/README.md#新規アカウント登録)」後、アカウントご利用できるようにSP側へご対応（紐づけ直しあるいは新規アカウントへの移行）をご依頼いただくようお願いいたします。（ただし、SP側で対応が可能であることを保証するものではございません）  
SP側へご依頼する際に必要なOrthrosアカウントのePPNにつきましては、[Orthrosマイページ](/docs/利用マニュアル/README.md#orthrosマイページへのサインイン)にて確認可能となっております。

</details>

#### Q.パスワードを何度も間違えアカウントがロックされました

<details>

**<summary>ご回答</summary>**

しばらく時間をおいてから再度実施をしてください

（ロックされている状態でさらに間違え回数が増えるとロック期間が長くなります）  
直ぐにロックを解除したい場合は、「[パスワードを忘れた場合](/docs/利用マニュアル/README.md#パスワードを忘れた場合)」からパスワードの再設定を行ってください

</details>

#### Q.アカウントが不要になったので削除したいです

<details>

**<summary>ご回答</summary>**

マイページの「[アカウント削除](/docs/利用マニュアル/README.md#アカウント削除)」から削除を行ってください

<img src="/images/github_caution_icon.png" width="11%" /><br>
削除を行うと同じメールアドレスでの再登録は出来なくなります

</details>

#### Q.ログインができない状態ですが、アカウントを削除してほしいです

<details>

**<summary>ご回答</summary>**

「[パスワードを忘れた場合](/docs/利用マニュアル/README.md#パスワードを忘れた場合)」からパスワードの再設定を行って頂き、マイページにログイン後、マイページの「アカウント削除」から削除を行ってください

</details>

#### Q.アカウントを作成する際のメールアドレスに、メーリングリストを利用することは可能ですか？

<details>

**<summary>ご回答</summary>**

Orthrosでは1つのアカウントにおいて同一人物が使用するポリシーとなっております。  
そのため、利用者ごとにOrthrosアカウントを作成頂くよういただくようお願いいたします。

<img src="/images/github_note_icon.png" width="11%" /><br>
詳細につきましては[利用規約](https://ui.orthros.gakunin.nii.ac.jp/ja/pages/terms-of-use)をご確認ください。  
また、複数アカウントのご利用につきましては「[Q.同じ利用者が異なるメールアドレスで複数アカウントを作成することは可能ですか？](/docs/よくある問合せ一覧/README.md#q同じ利用者が異なるメールアドレスで複数アカウントを作成することは可能ですか)」を参照ください。

</details>

>[!NOTE]
>**その他のよくあるご質問は**[**こちら**](/docs/よくある問合せ一覧/README.md)

## **お問い合わせ**
サービス自体へのお問い合わせにつきましては、それぞれのサービスの窓口へお願いします

### サービスに関するお問い合わせ窓口
| サービス名 | お問い合わせ先 |
| :-- | :-- |
| AMEDデータ利活用プラットフォーム運用環境 | お問い合わせフォームは[こちら](https://www.amed.go.jp/program/list/14/04/cannds-home.html) |
| eduroam JP申請システム | お問い合わせフォームは[こちら](https://www.eduroam.jp/for_admin/contact) |
| eduroam JP 認証連携IDサービス | お問い合わせフォームは[こちら](https://www.eduroam.jp/for_admin/contact) |
| GakuNin Federated Computing Services at NII (trial) | お問い合わせフォームは[こちら](https://rcos.nii.ac.jp/service/cs/) |
| GakuNin RDM | お問い合わせフォームは[こちら](https://support.rdm.nii.ac.jp/) |
| meatmail | お問い合わせフォームは[こちら](https://nii-auth.atlassian.net/wiki/spaces/meatmailniiacjp/pages/36274344) |
| NII研究クラウド | お問い合わせフォームは[こちら](https://meatwiki.nii.ac.jp/confluence/pages/viewpage.action?pageId=29229288) |
| NII研究クラウド(abc) | お問い合わせは下記まで  <br><img src="/images/nii-cloud-operation.png" width="60%"> |
| NII研究クラウド(xyz) | お問い合わせは下記まで  <br><img src="/images/nii-cloud-operation.png" width="60%"> |
| NII 研究データ基盤 | お問い合わせは下記まで  <br><img src="/images/nii-cloud-operation.png" width="60%"> |
| STEP10聴講申請システム | お問い合わせは下記まで  <br><img src="/images/STEP10.png" width="60%"> |
| インタークラウド - Jupyter Notebook | お問い合わせは下記まで  <br><br><img src="/images/nii-cloud-operation.png" width="60%"> |
| 科学技術の学術情報共有のための双方向コミュニケーションサービス | お問い合わせフォームは[こちら](https://c.yz.yamagata-u.ac.jp/amenity/splash.asp) |
| 学認LMS | お問い合わせフォームは[こちら](https://contents.nii.ac.jp/lms_support/faq) |
| 学認クラウドオンデマンド構築サービス<br>※このサービスの説明は[こちら](https://cloud.gakunin.jp/ocs/)（ログイン方法は各自ご確認ください） | お問い合わせフォームは[こちら](https://cloud.gakunin.jp/ocs/) |
| 学認クラウドゲートウェイサービス（グループ機能） | お問い合わせフォームは[こちら](https://nii-auth.atlassian.net/wiki/spaces/gakuninmappublic/pages/44532020) |
| 学認申請システム | お問い合わせフォームは[こちら](https://www.gakunin.jp/contact) |
| 教員のための生涯学習プラットフォーム | お問い合わせフォームは[こちら](https://o3edu.osaka-kyoiku.ac.jp/contact) |
| しぼすけ | お問い合わせフォームは[こちら](https://shibosuke.net/shibosuke/contact/) |
| デジタルバッジ・パーソナルウォレット | お問い合わせフォームは[こちら](https://o3edu.osaka-kyoiku.ac.jp/contact) |
| 東洋経済デジタルコンテンツライブラリー | お問い合わせフォームは[こちら](https://biz.toyokeizai.net/-/dcl/) |

### Orthrosお問い合わせ窓口
お問い合わせフォームは[こちら](https://ui.orthros.gakunin.nii.ac.jp/ja/pages/support)
#### お問い合わせ内容
・Orthrosアカウントの作成や削除などに関する内容<br>・Orthrosマイページの操作方法<br>・SP接続依頼について
