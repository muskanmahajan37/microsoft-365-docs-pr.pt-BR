---
title: Baixa das ferramentas de Descoberta Eletrônica herdadas
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Place Descoberta Eletrônica e In-Place (e os cmdlets correspondentes do PowerShell) no Exchange Online serão retirados no primeiro semestre de 2020. O Search-Mailbox cmdlet e a Descoberta Eletrônica Avançada v1.0 também estão sendo retirados no mesmo período.
ms.openlocfilehash: 48a20b9e73c5379325afb715a86c4945385fd0b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903601"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>Baixa das ferramentas de Descoberta Eletrônica herdadas

> [!IMPORTANT]
> A Microsoft está avaliando a situação de saúde pública e entendemos o impacto que isso está tendo em nossos clientes. Queremos ser parceiros fortes e cidadãos globais responsáveis. Para aliviar uma das muitas cargas que você está enfrentando, vamos atrasar a reforma agendada para as ferramentas de Descoberta eDiscovery herdadas descritas neste artigo por três meses. **As datas de aposentadoria atualizadas são refletidas abaixo.**

Ao longo dos anos, a Microsoft forneceu ferramentas de Descoberta Eletrônico que permitem que você pesquise, visualize e exporte conteúdo de email do Exchange Online. No entanto, essas ferramentas não oferecem mais uma maneira eficaz de pesquisar conteúdo que não seja do Exchange em outros serviços do Microsoft 365, como o SharePoint Online e grupos do Microsoft 365. Para resolver isso, a Microsoft oferece outras ferramentas de Descoberta Eletrônico que ajudam você a pesquisar uma ampla variedade de conteúdo do Microsoft 365. E estamos trabalhando duro para incorporar a funcionalidade de Descoberta EDiscovery mais atual e poderosa no centro de conformidade [do Microsoft 365.](https://compliance.microsoft.com) Isso permite que as organizações respondam a solicitações legais, internas e de outros documentos para conteúdo em vários serviços do Microsoft 365, incluindo o Exchange Online.

Como resultado dessa nova e aprimorada funcionalidade de Descoberta Eletrônico no centro de conformidade do Microsoft 365, estamos reatendendo aos seguintes recursos e funcionalidades relacionados à Descoberta Eletrônico relacionados à pesquisa de conteúdo de email no Exchange Online e no Microsoft 365:

- [Descoberta In-place e](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) Retém [in-place](/exchange/security-and-compliance/create-or-remove-in-place-holds) no centro de administração do Exchange.

- Os cmdlets do PowerShell do Exchange Online que suportam In-Place Descoberta Eletrônica e In-Place Retém (esses cmdlets são identificados coletivamente como **-MailboxSearch* cmdlets). Isso inclui os seguintes cmdlets:

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > Os cmdlets [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) e [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) estarão disponíveis após os outros cmdlets ****-MailboxSearch*** serem removidos para que você possa usá-los para ajudar na transição para outras ferramentas de Descoberta Eletrônica e de espera. No entanto, após uma determinada data (citada abaixo), o Suporte da Microsoft não dará mais suporte a esses dois cmdlets.

- O cmdlet [Search-Mailbox](/powershell/module/exchange/search-mailbox) no PowerShell do Exchange Online.

- As seguintes operações na API dos Serviços Web do Exchange:

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md), que é a primeira versão da Descoberta Digital Avançada acessada por meio de um caso de Descoberta Digital Principal no Centro de Conformidade e Segurança & do Office 365. A aposentadoria da Descoberta Avançada da Descoberta e 1.0 não afeta sua capacidade de criar e gerenciar os principais casos de Descoberta eDiscovery.

> [!NOTE]
> A funcionalidade de Descoberta Digital que está sendo retirada só se aplica às versões baseadas em nuvem do Microsoft 365 e do Office 365. A funcionalidade de Descoberta Digital em versões locais do Exchange e do SharePoint ainda terá suporte até nova notificação.

As seções a seguir neste artigo fornecem orientações sobre cada recurso que está sendo retirado. Essas informações, incluindo linhas do tempo e ferramentas alternativas que você pode usar em vez da ferramenta reformada.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place descoberta e In-Place no centro de administração do Exchange 

De acordo com o comunicado original de 1º de julho de 2017, In-Place funcionalidade de & de Descoberta & no Centro de administração do Exchange (EAC) está sendo retirada. A In-Place página & de Descoberta Virtual no EAC permitiu que você pesquise, segure e exporte conteúdo do Exchange Online. In-Place eDiscovery também permite copiar resultados de pesquisa para uma caixa de correio de descoberta para que você ou outros gerentes de Descoberta Eletrônico pudessem revisar o conteúdo e torná-lo disponível para solicitações legais, regulatórias e públicas.

Como todos esses recursos (exceto a cópia dos resultados da pesquisa para uma caixa de correio de descoberta) agora estão disponíveis na pesquisa de conteúdo, nas ferramentas de Descoberta Eletrônico e Descoberta Avançada no Centro de conformidade do [Microsoft 365](./microsoft-365-compliance-center.md) (com funcionalidade, confiabilidade e suporte aprimorados para uma ampla variedade de serviços do Microsoft 365), recomendamos que você comece a usar essas ferramentas assim que possível. Para ajudá-lo na transição para essas outras ferramentas de Descoberta In-Place, a tabela a seguir lista as ferramentas que você pode usar em vez de In-Place Descoberta In-Place.

### <a name="scope-of-affected-organizations"></a>Escopo das organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e do Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 Government; isso inclui GCC, GCC High e DoD

- Office 365 Alemanha

### <a name="timeline-for-retirement"></a>Linha do tempo para a aposentadoria

- 1º de julho de 2020: Você não poderá criar novas pesquisas e resções, mas ainda poderá executar, editar e excluir pesquisas existentes por sua conta e risco. O Suporte da Microsoft não In-Place mais & de Descoberta & no EAC.

- 1º de outubro de 2020: a funcionalidade In-Place & de Descoberta & no EAC será colocada em um modo somente leitura. Isso significa que você só poderá remover pesquisas e restituições existentes.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo retirada.

<table>
<thead>
<tr class="header">
<th>Funcionalidade</th>
<th>Ferramenta alternativa</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisar, exportar e manter em espera para fins legais</td>
<td>Principais casos de Descoberta e No Centro de conformidade do Microsoft 365 </td>
<td><p>Usar os recursos dos principais casos de Descoberta eDiscovery fornece a paridade funcional para In-Place Descoberta In-Place e In-Place Holds. Isso inclui:</p>
<ul>
<li>
<p>Escalas de pesquisa para milhões de locais</p>
</li>
<li>
<p>Maior confiabilidade para pesquisar, exportar e colocar conteúdo em espera</p>
</li>
<li>
<p>Procurando conteúdo no Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams, Grupos do Yammer, Grupos do Microsoft 365 e outros conteúdos armazenados em aplicativos do Office 365</p></li></ul>
</td>
</tr>
<tr class="even">
<td>Retenção para fins de retenção</td>
<td>Políticas de retenção no centro de conformidade do Microsoft 365</td>
<td><p>Você pode usar políticas de retenção para reter conteúdo e, se desejado, excluí-lo após o período de retenção expirar. Outros recursos incluem:</p>
<ul>
<li>
<p>Aplicando políticas a toda a sua organização </p>
</li><li>
<p>Aplicando políticas a locais de conteúdo específicos, como Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, Microsoft Teams e Grupos do Office 365</p></li>
<li>
<p>Aplicando políticas a usuários específicos</p></li></ul>
<p>Para obter mais informações, <a href="/microsoft-365/compliance/retention-policies">consulte Saiba mais sobre políticas de retenção e rótulos de retenção.</a></td>
</tr>
<tr class="odd">
<td>Copiar resultados da pesquisa de email para uma caixa de correio de descoberta para revisão</td><td>Conjuntos de revisão no Advanced eDiscovery v2.0</td>
<td><p>A revisão de conteúdo no Microsoft 365 nunca foi mais fácil. Conjuntos de revisão têm muitos recursos excelentes para ajudar a reduzir a quantidade de tempo e dados necessários para revisão, incluindo:</p>
<ul>
<li><p>Executar consultas de pesquisa rápidas e filtrar conteúdo em um conjunto de revisão</p></li>
<li><p>Analisar o conteúdo em um conjunto de revisão; isso inclui threading de email, detecção quase duplicada, análise de temas e codificação preditiva</p></li>
<li><p>Marcar documentos em um conjunto de revisão</p></li>
<li><p>Sugestões de marcação para ajudar a identificar o conteúdo de privilégio do cliente advogado</p></li></ul>
<p>Para obter mais informações, confira <a href="/microsoft-365/compliance/overview-ediscovery-20">Visão geral da solução de Descoberta Eletrônica Avançada no Microsoft 365</a>.</p>
<p>
<p>Como alternativa, você pode exportar resultados de pesquisa para arquivos PST e, em seguida, usar o serviço de Importação do Microsoft 365 para importar os PSTs para uma caixa de correio de descoberta. Para instruções passo a passo, consulte <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.
</tr>
<tr class=even>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário sai da sua organização e você precisa dar a outra pessoa acesso ao email do ex-funcionário), recomendamos que você atribua permissões a essa pessoa para acessar a caixa de correio do ex-funcionário. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou uma caixa de correio compartilhada, basta atribuir permissões de usuário para acessar a caixa de correio de origem.</td>
  
  </tr>
<tr class="odd">
<td>Restaurar itens da pasta Itens Recuperáveis</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>Você pode restaurar itens excluídos <i></i> permanentemente (também conhecidos como itens excluídos de forma suave) em caixas de correio, desde que o período de retenção de item excluído para um item não tenha expirado. Para obter mais informações, consulte <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Pasta Itens Recuperáveis no Exchange Online</a>.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>Perguntas frequentes sobre In-Place eDiscovery e In-Place Holds

**Uso a funcionalidade de resultados de pesquisa de cópia de In-Place eDiscovery & Retém no EAC para copiar resultados de pesquisa para uma caixa de correio de descoberta para revisão por advogados. Quais opções eu tenho agora?**

Há duas maneiras de replicar essa funcionalidade hoje. O primeiro é usar conjuntos [de revisão na Descoberta Avançada de Descoberta e v2.0](./view-documents-in-review-set.md). Conjuntos de revisão têm muitos dos mesmos recursos que você vê em uma ferramenta de revisão tradicional, como pesquisa rápida de documentos, marcação, threading de email, agrupação quase duplicada, análise de temas e codificação preditiva. Se você ainda quiser usar caixas de correio de descoberta para revisão, a segunda opção é exportar resultados de pesquisa para arquivos PST e importar os arquivos PST para uma caixa de correio de descoberta usando o recurso de importação [PST](use-network-upload-to-import-pst-files.md) no centro de conformidade da Microsoft.

**Como posso controlar quais locais de conteúdo (como caixas de correio ou sites) que podem ser pesquisados por um gerente de Descoberta Eletrônico usando as novas ferramentas?**

O Centro de conformidade do [](set-up-compliance-boundaries.md) Microsoft 365 também usa limites de conformidade para controlar quais locais de conteúdo um Gerenciador de Descobertas E pode pesquisar. Os limites de conformidade são úteis em entidades governamentais que precisam permanecer dentro dos limites da agência ou de corporações multi-nacionais necessárias para respeitar os tabuleiros geográficos.

**Como posso mover minhas pesquisas atuais e retém para o centro de conformidade do Microsoft 365?**

É possível migrar pesquisas In-Place descoberta e retês do EAC usando o PowerShell. Para obter instruções, [consulte Migrate searches and holds from the EAC to the Microsoft 365 compliance center](./migrate-legacy-ediscovery-searches-and-holds.md).

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlets

De acordo com o aviso original anunciado em 1º de julho de 2017 no Centro de administração do Exchange, In-Place funcionalidade de & De Descoberta Eletrônica e os cmdlets **\* correspondentes -MailboxSearch** estão sendo retirados. Esses cmdlets fornecem aos usuários a capacidade de pesquisar, segurar e exportar conteúdo de caixa de correio para solicitações legais, regulamentadas e públicas.

Como esses recursos agora estão disponíveis no Centro de conformidade do [<span class="underline">Microsoft 365</span>](./microsoft-365-compliance-center.md) e no Centro de Conformidade do Office 365 & PowerShell com desempenho e escalabilidade aprimorados, você deve usar esses cmdlets aprimorados. Esses cmdlets incluem [<span class="underline"> \* -ComplianceCase</span>](/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch,</span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)e [<span class="underline"> \* -ComplianceSearchAction</span>](/powershell/module/exchange/get-compliancesearchaction).

### <a name="scope-of-affected-organizations"></a>Escopo das organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e do Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 Government; isso inclui GCC, GCC High e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1º de julho de 2020: Você não poderá usar **New-MailboxSearch** para criar novas pesquisas de Descoberta Eletrônica do In-Place e retém In-Place, mas você ainda pode usar cmdlets para executar, editar e excluir pesquisas existentes e retém por sua conta e risco. O Suporte da Microsoft não fornecerá mais assistência para esses tipos de pesquisas e respaldo.

- 1º de outubro de 2020: conforme mencionado anteriormente, a funcionalidade In-Place Descoberta & Detém no EAC será colocada em um modo somente leitura. Isso também significa que você não poderá usar os cmdlets **New-MailboxSearch,** **Start-MailboxSearch** ou **Set-MailboxSearch.** Você só poderá obter e remover pesquisas e restituições existentes.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo retirada.

<table>
<thead>
<tr class="header">
<th>Funcionalidade</th>
<th>Ferramentas alternativas</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisar e exportar</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Os cmdlets ComplianceSearch e ComplianceSearchAction trabalham juntos para ajudá-lo a pesquisar e exportar conteúdo. Você pode criar uma nova pesquisa e exibir a estimativa de pesquisa usando os cmdlets <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> Em seguida, você pode usar o cmdlet <strong>New-ComplianceSearchAction</strong> para exportar os resultados da pesquisa. Você ainda terá que usar a ferramenta principal de Descoberta Digital no centro de conformidade do Microsoft 365 para baixar esses resultados de pesquisa no computador local.</p>
<p>
<p><strong>Observação:</strong> Se você usar esses cmdlets para criar pesquisas que não estão associadas a um caso principal <strong></strong> de Descoberta Eletrônica, essas pesquisas estarão localizadas na página de pesquisa de conteúdo no centro de conformidade do Microsoft 365.</p></td>
</tr>
<tr class="even">
<td>Manter conteúdo em uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Os reteres no centro de conformidade do Microsoft 365 devem estar associados a um ComplianceCase. Primeiro, crie o caso de conformidade e crie um CaseHoldPolicy e um CaseHoldRule.</p>
<p><strong>Observação:</strong> Criar um CaseHoldPolicy sem criar CaseHoldRule renderizará a cisão inoperável até que CaseHoldRule seja criado e associado ao CaseHoldPolicy. Consulte a documentação do cmdlet para obter mais informações.</p></td>
</tr>
<tr class="odd">
<td>Copiar resultados da pesquisa para uma caixa de correio de descoberta</td>
<td>Nenhum</td>
<td>Não há substituição direta para essa funcionalidade porque ela não fornece acesso a todos os serviços do Microsoft 365. Consulte as perguntas frequentes a seguir para encontrar soluções alternativas.</td>
</tr>
  <tr class=even>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário sai da sua organização e você precisa dar a outra pessoa acesso ao email do ex-funcionário), recomendamos que você atribua permissões a essa pessoa para acessar a caixa de correio do ex-funcionário. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou uma caixa de correio compartilhada, basta atribuir permissões de usuário para acessar a caixa de correio de origem.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Perguntas frequentes sobre ***-MailboxSearch** cmdlets

**Usamos a Pesquisa de Cópia para exportar mensagens de email ou mensagens instantâneas para fins de outras investigações legais e descobertas e descobertas. Quais outras opções temos depois que esses cmdlets são retirados?**

As [<span class="underline">APIs</span>](https://developer.microsoft.com/en-us/graph) do Microsoft Graph fornecem vários métodos para extrair dados para análise e outras finalidades muito mais resilientes e escalonáveis do que o uso dos cmdlets **\* -MailboxSearch.**

**Como migrar minhas pesquisas e retê-lo para o centro de conformidade do Microsoft 365?**

É possível migrar pesquisas In-Place descoberta e retês do centro de administração do Exchange usando um script do PowerShell. Para obter mais informações, [consulte Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center](migrate-legacy-eDiscovery-searches-and-holds.md).

**Depois que os cmdlets são removidos, ainda posso remover ou recuperar pesquisas?**

Sim, embora estamos removendo a capacidade de criar e modificar pesquisas, você ainda poderá usar **Get-MailboxSearch** e **Remove-MailboxSearch** até aviso prévio. No entanto, o uso desses cmdlets estará em seu próprio risco após as datas de aposentadoria e o Suporte da Microsoft não poderá mais fornecer assistência.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

O cmdlet **Search-Mailbox** no PowerShell do Exchange Online está sendo retirado conforme anunciado originalmente em um aviso na saída do cmdlet a partir de 2018. O cmdlet **Search-Mailbox** foi originalmente usado para pesquisar a caixa de correio de um usuário e limpar o conteúdo mal-intencionado. Recomendamos que você comece a usar os cmdlets **New-ComplianceSearch** e **New-ComplianceSearchAction** no Office 365 Security & Compliance Center PowerShell para pesquisar e limpar o conteúdo. Para uma experiência de segurança interna, os recursos de segurança do [<span class="underline">Microsoft 365</span>](../security/index.yml) fornecem proteção robusta contra ameaças para email e muitos outros serviços da Microsoft.

### <a name="scope-of-affected-organizations"></a>Escopo das organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e do Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 Government; isso inclui GCC, GCC High e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

-  1º de julho de 2020: o cmdlet **Search-Mailbox** não estará mais disponível e o Suporte da Microsoft não fornecerá mais assistência.

### <a name="alternative-tools"></a>Ferramentas alternativas

A tabela a seguir descreve outras ferramentas que você pode usar para substituir a funcionalidade existente que está sendo retirada.

<table>
<thead>
<tr class="header">
<th>Funcionalidade</th>
<th>Ferramentas alternativas</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pesquisar uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>Os cmdlets ComplianceSearch e ComplianceSearchAction trabalham juntos para ajudá-lo a pesquisar e exportar conteúdo. Você pode criar uma nova pesquisa e exibir a estimativa de pesquisa usando os cmdlets <strong>New-</strong>, <strong>Get-</strong>e <strong>Start-ComplianceSearch.</strong> Em seguida, você pode usar <strong>o comando New-ComplianceSearchAction -Export</strong> para exportar os resultados da pesquisa. Você ainda terá que usar a ferramenta principal de Descoberta Digital no centro de conformidade do Microsoft 365 para baixar esses resultados de pesquisa no computador local.</p></p>
</td>
</tr>
<tr class="even">
<td>Excluir emails em massa de uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">Configurar uma política de arquivamento e exclusão para caixas de correio</span></a></p>
<p></p></td>
<td><p>Os administradores podem criar uma política de arquivamento e exclusão que move automaticamente itens para a caixa de correio de arquivo morto de um usuário e exclui automaticamente itens da caixa de correio.</p>
</td>
</tr>
<tr class="even">
<td>Copiar resultados da pesquisa para uma caixa de correio de descoberta</td>
<td> </td>
<td>Não há substituição direta para essa funcionalidade porque ela não fornece acesso a todos os serviços do Microsoft 365. Consulte as perguntas frequentes na <strong>seção *-MailboxSearch cmdlets</strong> para encontrar soluções alternativas. </td>
</tr>
<tr class=odd>
  <td>Copiar mensagens de uma caixa de correio para uma caixa de correio diferente</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
  <td>Para dar a uma pessoa acesso ao email de outro usuário (como quando um funcionário sai da sua organização e você precisa dar a outra pessoa acesso ao email do ex-funcionário), recomendamos que você atribua permissões a essa pessoa para acessar a caixa de correio do ex-funcionário. Portanto, em vez de copiar itens de caixa de correio para outra caixa de correio de usuário ou uma caixa de correio compartilhada, basta atribuir permissões de usuário para acessar a caixa de correio de origem.</td>
</tr>
<tr class=even>
  <td>Limpar mensagens de uma caixa de correio</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>Os cmdlets ComplianceSearch e ComplianceSearchAction trabalham juntos para ajudá-lo a pesquisar e limpar o conteúdo. Você pode criar e executar uma pesquisa com cmdlets <strong>New-ComplianceSearch</strong> e <strong>New-ComplianceSearch</strong> e limpar o conteúdo usando o comando <strong>New-ComplianceSearchAction -Purge -PurgeType.</strong> Para obter mais informações, consulte <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">Pesquisar e excluir mensagens</span></a>.</p>
</td>
</tr>
<tr class="odd"> 
<td>Limpar mensagens de uma caixa de correio</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">Atribuir permissões a uma caixa de correio</a></td>
<td>Para limpar mensagens de uma caixa de correio, atribua permissões de administrador para acessar a caixa de correio do funcionário. As mensagens podem ser excluídas e recicladas conforme necessário, aproveitando os recursos de pesquisa e visualização integrados no Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Operações da API do Exchange Web Services

Essas operações na API dos Serviços Web do Exchange são usadas pelo recurso In-Place eDiscovery & Holds no centro de administração do Exchange e pelos cmdlets **\* -MailboxSearch** correspondentes no PowerShell do Exchange Online. Eles também serão retirados como parte da retirada das outras ferramentas de Descoberta eDiscovery herddas.

### <a name="scope-of-affected-organizations"></a>Escopo das organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e do Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 Government; isso inclui GCC, GCC High e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1º de julho de 2020: As operações GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes e GetHoldOnMailboxes não estarão mais disponíveis e o Suporte da Microsoft não fornecerá mais assistência.

## <a name="advanced-ediscovery-v10"></a>Descoberta eDiscoveria Avançada v1.0

A Descoberta Digital Avançada v1.0, que é a versão da Descoberta Avançada e disponível em um caso de Descoberta eDiscovery principal clicando em **Alternar** para Descoberta Avançada , está sendo retirada. Sua funcionalidade foi substituída pela nova [solução de Descoberta](./ediscovery.md) Técnica Avançada no centro de conformidade do Microsoft 365.

Para determinar se sua organização está usando a Descoberta Avançada de Descoberta e v1.0:

1. Vá para o Centro de Conformidade e Segurança [& do Office 365.](https://protection.office.com)

2. No painel de navegação esquerdo do Centro de Conformidade & Segurança, clique em Descoberta > Descoberta > **eDiscovery** e abra um caso de Descoberta Principal de Descoberta Digital.

3. Se você vir o botão **Alternar** para Descoberta Avançada e, em seguida, clicar nele levará você para a versão 1.0 da Descoberta Digital Avançada, que está sendo retirada. A capacidade de criar e gerenciar casos na Descoberta Principal não será afetada. Somente a capacidade de adicionar e analisar dados de caso em Descoberta Avançada v1.0 (clicando em **Alternar** para Descoberta Avançada ) está sendo retirada.

A nova solução de Descoberta Online Avançada no Microsoft 365 (também conhecida como Descoberta Avançada da Descoberta Online *v2.0*) fornece todos os recursos da solução original, mas agora inclui uma abordagem baseada em custodia para identificar conteúdo em outros serviços do Microsoft 365, coletar esse conteúdo e, em seguida, adicioná-lo a um conjunto de revisão onde os revisadores podem tirar proveito de consultas rápidas, marcação e recursos de análise para ajudar a coletar documentos relevantes. A Descoberta Interna Avançada agora inclui processamento aprimorado e visualizadores nativos para tipos de arquivos microsoft e não-Microsoft, uma lista completa de tipos de arquivo está [aqui](./supported-filetypes-ediscovery20.md) e os campos de metadados com suporte estão [aqui](./document-metadata-fields-in-advanced-ediscovery.md). Além disso, a nova solução de Descoberta Interna Avançada fornece um poderoso recurso de gerenciamento de reter custodiantes que permite aplicar reter o conteúdo em serviços diferentes, notificar os usuários sobre os reteres e acompanhar as respostas custodiantes, tudo dentro de um caso de Descoberta Avançada.

Para acessar o Advanced eDiscovery v2.0:

1. Vá para o centro de conformidade do [Microsoft 365.](https://compliance.microsoft.com)

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Avançado**.

Neste momento, recomendamos que você comece a fazer a transição do fluxo de trabalho de Descoberta Eletrônico para a nova funcionalidade de Descoberta Eletrônico Avançada. Se necessário, você pode arquivar seus casos de Descoberta Avançada 1.0 exportando o conteúdo e o armazenar offline. Embora você ainda consiga acessar a Descoberta Avançada da Descoberta e 1.0 em casos existentes até 31 de dezembro de 2020, o Suporte da Microsoft não fornecerá suporte após 1º de outubro de 2020. Consulte a linha do tempo a seguir para obter mais detalhes.

### <a name="scope-of-affected-organizations"></a>Escopo das organizações afetadas

- Organizações do Office 365 e do Microsoft 365 Enterprise

- Organizações do Office 365 e do Microsoft 365 Education

- Organizações do Office 365 e do Microsoft 365 Government; isso inclui GCC, GCC High e DoD

- Office 365 Alemanha

### <a name="timeline"></a>Linha do tempo

- 1º de julho de 2020: Você não poderá criar novos casos de Descoberta Avançada de Descoberta e v1.0.

- 1º de outubro de 2020: Você não poderá adicionar novos dados (Preparar resultados de pesquisa para Descoberta Avançada) a quaisquer casos. Você poderá continuar trabalhando com dados em casos existentes por sua conta e risco. O Suporte da Microsoft não fornecerá mais assistência. 

- 31 de dezembro de 2020: Você não poderá acessar os casos de Descoberta Avançada de Descoberta e v1.0.

### <a name="alternative-tools"></a>Ferramentas alternativas

A [solução de Descoberta Técnica Avançada no](./overview-ediscovery-20.md) centro de conformidade do Microsoft 365.