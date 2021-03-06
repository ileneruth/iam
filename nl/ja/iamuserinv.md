---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# ユーザーの招待とアクセス権限の割り当て
{: #iamuserinv}

{{site.data.keyword.Bluemix_notm}} サービス、アプリケーション、および {{site.data.keyword.Bluemix_notm}} インフラストラクチャーのどこにいるユーザーでも 1 箇所から招待することができます。ユーザーの招待、および未処理の招待の管理を行うには、アカウント所有者、組織管理者のいずれかであるか、あるいはユーザーを追加するためのインフラストラクチャーの許可が必要です。ユーザーの招待、招待のキャンセル、および招待されるユーザーへの保留中の招待の再送を行うことができます。単一のユーザーを招待することも、ユーザー・グループ内のすべてのメンバーに対して同じアクセス権限を与えている場合は、同時に複数のユーザーを招待することもできます。  
{:shortdesc}

## ユーザーの招待

アカウントでユーザーを招待したりユーザーの招待を管理したりするには、以下の手順を実行します。 

1. メニュー・バーで、**「管理」** &gt; **「セキュリティー」** &gt; **「ID およびアクセス権限 (Identity & Access)」** &gt; **「ユーザー」**をクリックします。「ユーザー」ウィンドウに、現在選択されているアカウントにおけるユーザーのリストが、E メール・アドレスおよび現在の状況と共に表示されます。
2. **「ユーザーの招待」**をクリックします。
3. ユーザーの E メール・アドレスまたは IBM ID を指定します。複数のユーザーに同じアクセス権限を提供する場合は、ユーザー ID 項目をコンマ、スペース、または改行で分離して、複数の E メール・アドレスまたは IBMid を入力します。
4. 管理する 1 つ以上のアクセス・オプションを追加します。少なくとも 1 つのアクセス・オプションを割り当てる必要があり、割り当てるアクセス・オプションごとにユーザーの設定を構成します。追加して構成しないその他のアクセス・オプションには、デフォルト値の *no access* が割り当てられます。自分が管理権限を持っているオプションに応じて、アクセス・オプション**「ID およびアクセス対応サービス」**、**「Cloud Foundry アクセス権限」**、**「インフラストラクチャー・アクセス権限」**のうちの 1 つまたはすべてが表示されます。詳しくは、『[ユーザー・アクセスの割り当て](/docs/iam/iamuserinv.html#assignaccess)』を参照してください。

ユーザーのアクセス権限は必要ないと判断した場合は、**「状況」**列に**「処理中」**または**「保留中」**の状態と表示されているユーザーの招待を取り消すことができます。招待されたユーザーが招待を受け取らなかった場合、**「保留中」**状態のユーザーに招待を再送することができます。

CLI を使用してユーザーを招待したい場合は、[bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) コマンドを参照してください。

## ユーザー・アクセスの割り当て
{: #assignaccess}

ユーザーを招待する際に Cloud Foundry の役割、ポリシー、およびインフラストラクチャーの許可を割り当てることにより、ユーザーに対しアクセス権限を割り当てます。管理権限があるアクセス・オプションに応じて、アカウント、組織、スペース、およびサービス・インスタンスの全体にわたるユーザーを招待し、アクセス権限を与えることができます。以下のセクションでは、招待したユーザーに割り当てることができる 3 つのタイプのアクセス権限について説明します。


### ID およびアクセス対応サービス

新規ユーザーを招待する際に、単一のサービス・ポリシーを割り当てることができます。ユーザーが招待を受け入れた後で、さらにサービス・ポリシーを追加できます。役割を追加するためのポリシーの編集、サービス・ポリシーの追加、またはユーザーのポリシーの削除について詳しくは、[ID およびアクセス対応サービスのアクセス・ポリシー](/docs/iam/iamusermanage.html#iammanidaccser)を参照してください。

**注**: ポリシーを割り当てる際にどのサービスを選択するかに応じて、以下の手順で説明するすべてのフィールドが表示されない可能性があります。

1. **「ユーザーの招待」**画面で、**「ID およびアクセス対応サービス」**セクションを展開します。
2. サービスを選択します。
3. プロンプトが出されたら、**「すべての現行地域」**、または特定の地域を選択します。
**注**: すべてのサービスで、地域の選択が必要なわけではありません。
4. **「すべての現行サービス・インスタンス」**を選択するか、特定のサービス・インスタンスを選択します。
5. 選択したサービスに応じて、以下のフィールドが表示される場合があります。これらのフィールドの値を入力しないと、ポリシーの割り当ては、バケット・レベルではなく、サービス・インスタンス・レベルで行われます。 
    * **リソース・タイプ**: **「バケット」** を入力します。
    * **リソース**: バケットの名前を入力します。
6. ポリシーのアクセス権限の有効範囲を定義する役割を選択します。
7. オプション: **「役割の追加」**を選択して、ポリシーに追加の役割を指定します。


サービス・ポリシーを設定する際の、役割に関するより具体的な情報については、『[ID およびアクセス管理のポリシーおよび役割](/docs/iam/users_roles.html#iamusermanpol)』を参照してください。

### Cloud Foundry アクセス権限

新規ユーザーを招待する際、そのユーザーをアカウント内の組織に追加することを選択できます。ユーザーを組織に追加する場合、そのユーザーに組織の役割を割り当てることができます。次に、招待したユーザーに、割り当てられたスペースの役割によって、選択した組織内のいずれかのスペースまたはすべてのスペースへのアクセス権限を付与することを選択します。

1. **「ユーザーの招待」**画面で、**「Cloud Foundry アクセス権限」**セクションを展開します。
2. ユーザーの追加先の組織を選択します。
3. 組織の役割を選択して、選択した組織へのアクセスのレベルを定義します。
4. オプション: **「役割の追加」**を選択して、追加の役割を指定します。
5. **「すべての現行地域」**または特定の地域を選択します。
6. **「すべての現行スペース」**または特定のスペースを選択します。
7. スペースの役割を選択して、選択したスペースへのアクセス・レベルを定義します。
8. オプション: **「役割の追加」**を選択して、追加の役割を指定します。

これらの役割についての具体的な情報は、『[Cloud Foundry の役割](/docs/iam/users_roles.html#cfroles)』を参照してください。

**注**: Cloud Foundry の役割を追加するには、[bluemix iam account-user-invite](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_iam_account_user_invite) CLI コマンドを使用できますが、他のアクセス権限または許可を割り当てるには UI を使用する必要があります。

### インフラストラクチャー・アクセス権限

実際に割り当てられる許可は、招待側が所有する許可のサブセットに自動的に制限されます。許可についての詳細、および各許可でユーザーが実行できるアクションについては、『[インフラストラクチャーの許可](/docs/iam/users_roles.html#infrapermissions)』を参照してください。

1. **「ユーザーの招待」**画面で、**「インフラストラクチャー・アクセス権限」**セクションを展開します。
2. アクセス権限の有効範囲を定義する許可を選択します。

アカウントに追加された後のユーザーのアクセス権限の構成については、『[ユーザーおよびアクセス権限の管理](/docs/iam/iamusermanage.html)』を参照してください。
