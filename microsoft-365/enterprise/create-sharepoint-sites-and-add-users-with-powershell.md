---
title: Criar sites do SharePoint Online e adicionar usuários com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: 'Resumo: use o PowerShell para criar novos sites do SharePoint Online e adicionar usuários e grupos a esses sites.'
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907613"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Criar sites do SharePoint Online e adicionar usuários com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Quando você usa o PowerShell para o Microsoft 365 para criar sites do SharePoint Online e adicionar usuários, você pode executar tarefas de forma rápida e repetida muito mais rápida do que pode no centro de administração do Microsoft 365. Você também pode executar tarefas que não são possíveis de executar no Centro de administração do Microsoft 365. 

## <a name="connect-to-sharepoint-online"></a>Conectar ao SharePoint Online

Os procedimentos neste tópico exigem que você se conecte ao SharePoint Online. Para obter instruções, [consulte Conectar-se ao PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Etapa 1: Criar novos conjunto de sites usando o PowerShell

Crie vários sites usando o PowerShell e um arquivo .csv que você criar usando o código de exemplo fornecido e o Bloco de Notas. Para este procedimento, você substituirá as informações de espaço reservado mostradas em colchetes por suas próprias informações específicas do site e do locatário. Esse processo permite que você crie um único arquivo e execute um único comando do PowerShell que usa esse arquivo. Isso torna as ações realizadas repetitivas e portáteis e elimina muitos, se não todos, erros que podem vir da digitação de comandos longos no Shell de Gerenciamento do SharePoint Online. Há duas partes para este procedimento. Primeiro, você criará um arquivo .csv e, em seguida, fará referência a esse arquivo .csv usando o PowerShell, que usará seu conteúdo para criar os sites.

O cmdlet do PowerShell importa o arquivo .csv e o canalização para um loop dentro dos colchetes curvados que lê a primeira linha do arquivo como headers de coluna. O cmdlet do PowerShell, em seguida, itera pelos registros restantes, cria um novo conjunto de sites para cada registro e atribui propriedades do conjunto de sites de acordo com os headers da coluna.

### <a name="create-a-csv-file"></a>Criando um arquivo .csv

> [!NOTE]
> O parâmetro de cota de recursos só funciona em sites clássicos. Se você usar esse parâmetro em um site moderno, poderá receber uma mensagem de aviso de que ele foi preterido. 

1. Abra o bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Onde *locatário* é o nome  do seu locatário e proprietário é o nome de usuário do usuário em seu locatário ao qual você deseja conceder a função de administrador principal do conjunto de sites.<br/>(Você pode pressionar Ctrl+H ao usar o Bloco de Notas para substituir em massa mais rapidamente.)<br/>

2. Salve o arquivo em sua área de trabalho como **SiteCollections.csv**.<br/>

> [!TIP]
> Antes de usar esse ou qualquer outro arquivo de script .csv ou Windows PowerShell, é uma boa prática garantir que não haja caracteres extraneos ou não impressos. Abra o arquivo no Word, e na faixa de opções, clique no ícone do parágrafo  para mostrar caracteres não imprimíveis. Não deve haver caracteres estranhos não imprimíveis. Por exemplo, não deve haver marcas do parágrafo no final do arquivo.

### <a name="run-the-windows-powershell-command"></a>Execute o comando do Windows PowerShell:

1. No prompt Windows PowerShell, digite ou copie e colar o seguinte comando e pressione Enter:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Onde *MyAlias* é igual ao alias do usuário.<br/>

2. Aguarde o prompt Windows PowerShell reaparecer. Pode demorar um minuto ou dois.<br/>

3. No prompt Windows PowerShell, digite ou copie e copie o seguinte cmdlet e pressione Enter:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Observe os novos conjuntos de sites na lista. Usando nosso arquivo CSV de exemplo, você verá os seguintes conjunto de sites: **TeamSite01**, **Blog01**, **Project01** e **Community01**

É isso. Você criou vários conjunto de sites usando o arquivo .csv criado e um único comando Windows PowerShell. Agora você está pronto para criar e alocar usuários nestes sites.

## <a name="step-2-add-users-and-groups"></a>Etapa 2: Adicionar usuários ou grupos

Agora você criará usuários e irá adicioná-los ao grupo do site. Então você usará um arquivo csv. para fazer o carregamento em massa de novos grupos e usuários.

Os procedimentos a seguir continuam usando os sites de exemplo TeamSite01, Blog01, Project01 e Community01.

### <a name="create-csv-and-ps1-files"></a>Criando arquivos .csv e .ps1

1. Abra o bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/>Onde *locatário* é igual ao nome do locatário.<br/>

2. Salve o arquivo na área de trabalho como **GroupsAndPermissions.csv**.<br/>

3. Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/>Onde *o locatário* é igual ao nome do locatário e *o* nome de usuário é igual ao nome de usuário de um usuário existente.<br/>

4. Salve o arquivo na área de trabalho como **Users.csv**.<br/>

5. Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Onde MyAlias é igual ao nome de usuário do usuário que está conectado no momento.<br/>

6. Salve o arquivo na área de trabalho como **UsersAndGroups.ps1**. Este é um script Windows PowerShell simples.

Agora você está pronto para executar o script UsersAndGroup.ps1 para adicionar usuários e grupos a vários conjuntos de sites.

### <a name="run-usersandgroupsps1-script"></a>Execute o script UsersAndGroups.ps1

1. Retorne ao shell de gerenciamento do SharePoint Online<br/>
2. No prompt Windows PowerShell, digite ou copie e colar a seguinte linha e pressione Enter:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. No prompt de confirmação, pressione **Y**.<br/>

4. No prompt Windows PowerShell, digite ou copie e copie o seguinte e pressione Enter:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Onde *MyAlias* é igual ao seu nome de usuário.<br/>

5. Aguarde a solicitação de retorno do prompt antes de prosseguir. Os grupos aparecerão de acordo com a criação dos mesmos. Então você verá a repetição da lista do grupo de acordo com os usuários que são agregados.

## <a name="see-also"></a>Confira também

[Conectar ao PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Gerenciar grupos de sites do SharePoint Online com o PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)