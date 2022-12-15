[English is here](https://github.com/hisashin0728/AutoClosing-SAMPLEALERT-FromMDfC/blob/main/Readme_en.md)

# 本テンプレートの目的

- Microsoft Sentinel ではオートメーション機能を用いて、Logic Apps を通じて様々な自動化操作を行う機能を提供しています。 
- Microsoft Sentinel のインシデント運用で用いられる、インシデントの自動操作を体験する演習用として公開しました。
- テンプレートを導入することで、ユーザー側で定義した条件に対するインシデントの操作（自動クローズ、タグ付け、重要度変更など）を体験できます。

# 画面イメージ
本テンプレートを導入・設定することにより、Microsoft Defender for Cloud が発砲するサンプルイベント検知時に、インシデントを自動操作することを体験することが出来ます。
![image](https://user-images.githubusercontent.com/55295601/207807787-7d4db6c1-085a-4a57-95b2-98dc391f2ecf.png)

条件は以下で設定しています。

- インシデント名 ``[SAMPLE ALERTS]``が有った場合

条件が ``TRUE`` の場合のアクションとして、以下を設定しています。

- 重要度を下げる (INFORMATIONAL)
- インシデントを自動クローズさせる（理由は ``Undetermined``、コメントは "サンプルアラートのためクローズ" を追加）
- タグを付与 ``SAMPLE``

# 導入されるテンプレートのイメージ
本テンプレートを導入すると、以下ロジックアプリが作成されますので、ワークフローをご確認下さい。
<img width="444" alt="image" src="https://user-images.githubusercontent.com/55295601/207754125-9254f119-5809-49de-a866-ce5356e53f25.png">

# Azure への展開方法
## 1. テンプレートを導入する
以下ボタンを押していただき、テンプレートを用いてロジックアプリを展開します。
後のクリーンナップのため、専用のリソースグループを作成することをお勧めします。

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fhisashin0728%2FAutoClosing-SAMPLEALERT-FromMDfC%2Fmain%2Fazuredeploy.json)

## 2. **Microsoft Sentinel レスポンダー** ロールを、ロジックアプリのマネージドID に付与する
本テンプレートでは、Microsoft Sentinel との API 接続にマネージド ID を用いています。
Microsoft Sentinel と接続するためには ``Microsoft.SecurityInsights/incidents/read`` 権限が必要になります。
演習では、Microsoft Sentinel レスポンダーロールを付与して、接続のための権限を手動でアサインして下さい。
![image](https://user-images.githubusercontent.com/55295601/207772809-3f784ed0-7780-4099-ab6b-c28a3c4752dc.png)
以下がイメージになります。
<img width="964" alt="image" src="https://user-images.githubusercontent.com/55295601/207773171-d6f493cc-0c16-41a3-8b8f-ad9664c00223.png">

## 3. Microsoft Sentinel でオートメーション機能を設定し、ロジックアプリが起動できるようにする
Microsoft Sentinel から、「オートメーション」機能より、ロジックアプリを起動するためのオートメーションルールを作成します。
<img width="1118" alt="image" src="https://user-images.githubusercontent.com/55295601/207773600-b9281b7f-2163-45b8-bdd0-560672f66e9e.png">

# 免責事項

- 本テンプレートは Microsoft Sentinel オートメーションを体験するための演習用として作成されたものです。
- 本テンプレートは個人の見解に基づいた内容であり、所属する会社の公式見解ではありません。また、いかなる保証を与えるものでもありません。正式な情報は、各製品の販売元にご確認ください。
- 現版では、マネージド ID に対する RBAC アサインは手動としています。

# Author
  
* 作成者　Hisashi Nakada (hisashin0728)
