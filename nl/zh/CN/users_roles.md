---

copyright:

  years: 2015, 2016
lastupdated: "2017-10-06"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 用户角色和许可权
{: #userroles}

可以在帐户的**用户**页面中管理 {{site.data.keyword.Bluemix_notm}} 平台和基础架构服务上的用户。要访问“用户”页面，请在 {{site.data.keyword.Bluemix_notm}} 菜单中，单击**管理** &gt; **帐户** &gt; **用户**。帐户所有者可以执行用于管理用户、许可权、组织和空间的所有操作。Cloud Foundry 组织管理员和空间管理员还有权管理添加到自己所管理的每个组织和空间中的用户的权限。
{:shortdesc}

如果您是添加到其他人帐户的用户，并且希望查看分配给您的角色和许可权，请转至**管理** &gt; **安全性** &gt; **身份和访问权** &gt; **用户**，然后单击您的姓名。

## 帐户角色
{: #userrolesinfo}

在帐户级别，有两个角色支持访问不同的帐户管理功能：

| 帐户角色| 许可权|
|----------------|---------|
|所有者| 帐户所有者有权访问其个人档案、用户、记帐信息、花费通知和使用情况仪表板。在“用户”页面中，所有者可以邀请新用户并调整角色。所有者还可以添加促销信贷，设置或更改记帐限制，设置服务访问权以及管理组织和空间。|
|成员| 成员有权在 {{site.data.keyword.Bluemix_notm}} 标题中访问其个人档案、显示帐户中活动用户的“用户”页面、帐户信贷和记帐限制。|
{:caption="表 1. 帐户角色和许可权" caption-side="top"}

所有新用户都会添加为该帐户的成员。您可以为被邀请者添加组织和空间角色，以在 {{site.data.keyword.Bluemix_notm}} 中启用特定视图和许可权。一旦被邀请者接受邀请并加入 {{site.data.keyword.Bluemix_notm}}，您就可以在“用户”页面上编辑这些被邀请者的角色。

## Cloud Foundry 角色
{: #cfroles}

Cloud Foundry 角色包含帐户中定义的组织和空间的访问许可权。Cloud Foundry 角色不会授予用户在服务上下文中完成操作的许可权。可以在组织级别分配以下角色：

| 组织角色| 许可权|
|-------------------|-------------|
|管理员| 组织管理员可以创建、查看、编辑或删除组织内的空间，查看组织的使用情况和配额，邀请用户加入组织，管理谁有权访问组织及其在组织中的角色，以及管理组织的定制域。|
|记帐管理员| 记帐管理员可以在“使用情况仪表板”页面上查看组织的运行时和服务使用情况信息。|
|审计员| 组织审计员可以查看组织中的应用程序和服务内容。审计员还可以查看组织中的用户及其分配的角色，以及组织的配额。|
{:caption="表 2. 组织角色和许可权" caption-side="top"}

可以在空间级别分配以下角色：

| 空间角色| 许可权|
|------------|-------------|
|管理员| 空间管理员可以添加现有用户，并管理空间内的角色。空间管理员还可以查看空间中每个应用程序的实例数、服务绑定和资源使用情况。|
|开发者| 空间开发者可以创建、删除和管理空间内的应用程序和服务。某些管理任务包括部署应用程序，启动或停止应用程序，重命名应用程序，删除应用程序，重命名空间，将服务绑定到应用程序或从应用程序取消绑定服务，以及查看空间中每个应用程序的实例数、服务绑定和资源使用情况。此外，空间开发者还可以将内部或外部 URL 与空间中的应用程序相关联。|
|审计员| 空间审计员具有对有关空间的所有信息的只读访问权，例如有关空间中每个应用程序的实例数、服务绑定和资源使用情况的信息。|
{:caption="表 3. 空间角色和许可权" caption-side="top"}

**注**：分配有管理员或开发者空间角色的用户可以访问 VCAP_SERVICES 环境变量。但是，分配有审计员角色的用户无法访问 VCAP_SERVICES。

## 身份和访问权管理策略与角色
{: #iamusermanpol}

将自动为帐户所有者分配 Identity And Access Management (IAM) 的帐户管理员角色，这样您就可以分配和管理服务策略。服务策略可分配给个别用户或服务标识，而分配的策略可以为整个服务定义访问权，也可以在单个实例级别定义访问权。

### 服务策略

策略使用属性组合来定义适用的一组资源，从而为用户或服务标识分配对该组资源的一个或多个角色。分配策略时，首先指定服务。然后，可以选择要分配的一个或多个角色。根据选择的服务，可能会提供其他配置选项。

如果您具有合适的角色，那么可以分配和管理策略。下表显示了策略管理任务以及每个任务所需的角色。

| 操作| 所需角色 |
|----------|---------|
| 在所有服务和实例的帐户上创建策略| 帐户管理员|
| 创建关于帐户中某个服务的策略| 帐户管理员，或者帐户中该服务的管理员|
| 创建服务实例| 帐户管理员，或者帐户中该服务的管理员或编辑者|
| 创建关于某个服务实例的策略| 帐户管理员、帐户中该服务的管理员或该服务实例的管理员|
{: caption="表 4. 用于管理启用了 IAM 的服务策略的管理任务" caption-side="top"}

### 服务策略角色
{: #iamusermanrol}

IAM 允许您为帐户中的用户和资源管理和定义访问权。如果可以使用 IAM 来管理您所使用的服务以进行用户访问控制，那么有两种类型的角色可允许在帐户中进行不同的操作：平台管理和服务访问角色。

<dl>
<dt>平台管理角色</dt>
<dd>这些角色可用于可使用 IAM 进行管理以进行用户访问控制的所有服务，其中包括管理员、编辑者、操作员、查看者和记帐管理员。这些角色会映射到可在平台级别对 {{site.data.keyword.Bluemix_notm}} 资源所执行的用户操作。例如，这些操作中有一些可以创建实例、将实例连接到应用程序、管理服务标识、管理用户和许可权，以及管理帐户的帐单和配额。</dd>
<dt>服务访问角色</dt>
<dd>这些角色特定于服务。管理者、作者和读者角色会定义用户使用服务和平台服务 API 调用的能力。由于每个服务都会定义具有特定角色的用户可以执行的操作，因此服务可能不会使用此文档中所描述的所有可用角色。</dd>
</dl>

**注**：当在 UI 中分配策略时，您可能看不到所有的角色都作为选项列出，这是因为仅会显示适用于您在策略中所选服务的角色。有关启用哪些角色以及每个访问角色允许对每个服务执行的操作的特定信息，请参阅该服务的相关文档。


#### 平台管理角色

通过平台管理角色，用户可以分配有不同级别的许可权，以执行平台操作。除了控制台中提供的角色的描述外，下表还提供了分配有每个角色的用户可以执行的一些平台管理操作示例。

| 平台管理角色 | 用户在帐户中可以对服务执行的操作 | 服务标识的操作 |
|:-----------------|:--------------|:---------------|
| 查看者| 查看实例 | 查看标识和 API 密钥 |
| 操作员|  查看和绑定服务实例 | 不适用 |
| 编辑者|  创建、删除、编辑、暂挂、恢复、查看、绑定服务实例 | 删除标识以及创建和删除 API 密钥 |
| 管理员|  服务的所有管理操作 | 创建和删除标识和 API 密钥、向标识分配策略 |
{: caption="表 5. 平台管理角色和操作的示例" caption-side="top"}

一些服务可能将特定操作映射到与服务管理而非与服务访问相关的平台管理角色。作为示例，请查看下表，其详细说明了映射到这些角色的 {{site.data.keyword.containershort_notm}} 服务操作。


| 平台管理角色 | 操作描述| {{site.data.keyword.containershort_notm}} 服务的操作示例 |
|:-----------------|:-----------------|:-----------------|
| 查看者| 可以查看服务实例，但是不能修改它们 | <ul><li>列出集群</li><li>查看集群的详细信息</li></ul>|
| 编辑者| 执行除管理帐户和分配访问策略之外的所有其他平台操作 |<ul><li>将服务绑定到集群</li><li>创建 Webhook</li></ul> |
| 操作员| 执行配置和操作服务实例所需的平台操作，如查看服务的仪表板。| <ul><li>添加或除去工作程序节点</li><li>重新引导或重新装入工作程序节点</li><li>将服务绑定到集群</li></ul> |
| 管理员| 基于分配给此角色的资源执行所有平台操作，包括向其他用户分配访问策略。|<ul><li>除去集群</li><li>创建集群</li><li>更新用户访问策略</li><li>查看者、编辑者和操作员可以执行的所有操作</li></ul>|
{: caption="表 6. 平台管理角色和操作的示例" caption-side="top"}


#### 服务访问角色

服务访问角色可使用户分配有不同级别的许可权，以调用服务 API。下表提供根据所分配的服务访问角色，可使用 {{site.data.keyword.objectstorageshort}} 服务采取的操作示例。

**注**：每个所分配角色可采取的操作根据您为策略所选择的服务而有所不同。

| 服务访问角色 | 操作描述| {{site.data.keyword.objectstorageshort}} 服务的操作示例 |
|:-----------------|:-----------------|:-----------------|
|  读者 | 在服务内执行只读操作，如查看服务特定资源 | 列出和下载对象 |
| 作者 | 作者的许可权高于读者角色，包括创建和编辑服务特定资源。| 创建和销毁存储区和对象 |
| 管理者 | 管理者的许可权高于作者角色，可完成服务所定义的特权操作。此外，还可以创建和编辑服务特定资源。| 管理数据存储的所有方面、创建和销毁存储区和对象 |
{: caption="表 7. 服务访问用户角色和操作的示例" caption-side="top"}


## 基础架构许可权
{: #infrapermissions}

可以在邀请用户时，设置以下初始许可权：

| 许可权设置| 操作描述|
|---------------------------|------------------------|
|仅查看| 具有此许可权的用户只能查看系统内的项。|
|基本用户| 具有此许可权的用户可以在系统内执行基本操作，例如添加凭单和管理设备。|
|超级用户| 具有此许可权的用户可以执行系统中可用的所有操作。|
{:caption="表 8. 基础架构许可权" caption-side="top"}

在用户已经接受邀请后，可以设置其他许可权。在邀请时设置的初始许可权并未授予对设备的访问权，因此在用户接受邀请后，您必须在“控制门户网站”中授予其设备访问权。
