---
title: Referência de Prevenção contra Perda de Dados
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: material de referência de prevenção contra perda de dados
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572556"
---
# <a name="data-loss-prevention-reference"></a>Referência de prevenção contra perda de dados
 
> [!IMPORTANT]
> Este é o tópico de referência não é mais o principal recurso para Microsoft 365 de prevenção contra perda de dados (DLP). O conjunto de conteúdo DLP está sendo atualizado e reestruturado. Os tópicos abordados neste artigo mudarão para artigos novos e atualizados. Para obter mais informações sobre DLP, consulte [Learn about data loss prevention](dlp-learn-about-dlp.md).

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> Os recursos de prevenção contra perda de dados foram recentemente adicionados às mensagens de chat e de canal do Microsoft Teams para usuários licenciados para a Conformidade Avançada do Office 365, disponível como uma opção independente e está incluso na Conformidade do Office 365 E5 e no Microsoft 365 E5. Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>Criar e gerenciar políticas DLP

Você cria e gerencia políticas DLP na página Prevenção Contra Perda de Dados no Centro de conformidade do Microsoft 365.
  
![Página de Prevenção contra Perda de Dados no Centro de Conformidade &amp; Segurança do Office 365](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
Você pode usar uma regra para atender a um requisito específico de proteção e depois usar uma política DLP para agrupar requisitos de proteção comuns, como todas as regras necessárias para manter a conformidade com uma regulamentação específica.
  
Por exemplo, você pode ter uma política DLP que ajuda a detectar a presença de informações sujeitas à lei americana HIPAA (Health Insurance Portability Accountability Act). Essa política DLP pode ajudar a proteger dados HIPAA (objeto) em todos os sites do SharePoint Online e OneDrive for Business (local) ao encontrar qualquer documento com essas informações confidenciais que são compartilhadas com pessoas de fora da sua organização (condições) e, em seguida, bloquear o acesso ao documento e enviar uma notificação (ações). Esses requisitos são armazenados como regras individuais e agrupadas como uma política DLP para simplificar o gerenciamento e a geração de relatório.
  
![O diagrama mostra que a política de DLP contém locais e regras](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

Se você optar por incluir grupos de distribuição específicos no Exchange, a política DLP será delimitada somente aos membros desse grupo. Da mesma maneira, a exclusão de um grupo de distribuição excluirá todos os membros desse grupo de distribuição da avaliação de políticas. Você pode optar por criar uma política para os membros das listas de distribuição, grupos de distribuição dinâmicas e grupos de segurança. Uma política DLP pode conter, no máximo, 50 inclusões e exclusões.

Se optar por incluir ou excluir sites específicos do SharePoint, uma política de DLP poderá conter até 100 inclusões e exclusões. Embora esses limites existam, você pode excede-los ao ignorar uma política no âmbito da organização ou uma política que se aplica a locais inteiros.

Se optar por incluir ou excluir contas ou grupos específicos do OneDrive, uma política DLP não poderá conter mais de 100 contas de usuários ou 50 grupos como inclusão ou exclusão.

> [!NOTE]
> O escopo de política do OneDrive for Business está usando as contas ou grupos em visualização pública. Durante essa fase, é possível incluir ou excluir contas de usuários e grupos como parte de uma política DLP. Não há suporte para inclusão e exclusão como parte da mesma política.
  
### <a name="rules"></a>Regras

> [!NOTE]
> O comportamento padrão de uma política DLP, quando não há alerta configurado, não é o de alertar ou acionar. Isso se aplica apenas aos tipos de informações padrão. Para tipos de informações personalizadas, o sistema alertará mesmo se não houver nenhuma ação definida na política.

As regras aplicam os requisitos de negócios para o conteúdo da sua organização. Uma política contém uma ou mais regras, e cada regra consiste em condições e ações. Para cada regra, quando as condições forem atendidas, as ações são executadas automaticamente. As regras são executadas sequencialmente, começando pela prioridade mais alta em cada política.
  
Uma regra também fornece opções para notificar os usuários (com dicas de política e notificações por email) e os administradores (com relatórios de incidentes por email) cujo conteúdo correspondeu à regra.
  
Veja a seguir os componentes de uma regra, cada um explicado abaixo.
  
![Seções do editor regras DLP](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Condições

As condições são importantes porque elas determinam que tipos de informações confidenciais está procurando e quando uma ação deve ser executada. Por exemplo, você pode optar por ignorar o conteúdo com números de passaporte, a menos que o conteúdo contenha mais de 10 números e seja compartilhado com pessoas de fora da sua organização.
  
As condições se concentram no **conteúdo**, como quais tipos de informações confidenciais está procurando e também no **contexto**, como com quem o documento é compartilhado. Você pode usar condições para atribuir ações diferentes a diferentes níveis de risco. Por exemplo, o conteúdo confidencial compartilhado internamente pode diminuir o risco e exigir menos ações do que o conteúdo confidencial compartilhado com pessoas de fora da organização. 
  
![Lista que mostra as condições DLP disponíveis](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
As condições disponíveis agora podem determinar se:
  
- O conteúdo contém um tipo de informação confidencial.
    
- O conteúdo contém um rótulo. Para saber mais, confira a seção a seguir [Usar um rótulo de retenção como condição em uma política de DLP](#using-a-retention-label-as-a-condition-in-a-dlp-policy).
    
- O conteúdo é compartilhado com pessoas de fora ou de dentro da sua organização.

  > [!NOTE]
  > Os usuários que têm contas não convidadas no Active Directory ou no locatário do Azure Active Directory de uma organização são considerados como pessoas dentro da organização.
    
#### <a name="types-of-sensitive-information"></a>Tipos de informações confidenciais

Uma política DLP ajuda a proteger informações confidenciais, que são definidas como um **tipo de informações confidenciais**. O Microsoft 365 inclui definições para vários tipos comuns de informações confidenciais em diferentes regiões que estão prontos para uso, como um número de cartão de crédito, números de contas bancárias, números de carteiras de identidade e números de passaporte. 
  
![Lista de tipos de informações confidenciais disponíveis](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
Quando uma política DLP procura por um tipo de informação confidencial, como um número de cartão de crédito, ela não procura simplesmente por um número de 16 dígitos. Cada tipo de informação confidencial é definido e detectado usando uma combinação de:
  
- Palavras-chave.
    
- Funções internas para validar as somas de verificação ou a composição.
    
- Avaliação de expressões regulares para localizar correspondências padrão.
    
- Análise de outros conteúdos.
    
Isso ajuda a detecção de DLP a alcançar um alto grau de precisão, reduzindo o número de falsos positivos que pode interromper o trabalho das pessoas.
  
#### <a name="actions"></a>Ações

Quando o conteúdo corresponde a uma condição em uma regra, você pode aplicar ações para proteger automaticamente o conteúdo.
  
![Lista de ações DLP disponíveis](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Com as ações agora disponíveis, você pode:
  
- **Restringir o acesso ao conteúdo** Dependendo das suas necessidades, você pode restringir o acesso ao conteúdo de três maneiras:

  1. Restringir o acesso ao conteúdo para todos.
  2. Restringir o acesso ao conteúdo para pessoas de fora da organização.
  3. Restringir o acesso a "Qualquer pessoa com o link".

  Para conteúdo de site, significa que as permissões para o documento são restritas a todos, exceto o administrador principal do conjunto de sites, o proprietário do documento e a pessoa que modificou o documento pela última vez. Essas pessoas podem remover as informações confidenciais do documento ou executar outras ações corretivas. Quando o documento estiver em conformidade, as permissões originais serão restauradas automaticamente. Quando o acesso a um documento é bloqueado, o documento é exibido com um ícone de dica de política especial na biblioteca do site. 
    
  ![A dica de política mostrando acesso ao documento está bloqueada](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  Para conteúdo de email, essa ação bloqueia o envio da mensagem. Dependendo de como a regra DLP estiver configurada, o remetente verá uma notificação de falha na entrega (se a regra usar uma notificação) ou uma dica de política e/ou notificação por email.
    
  ![Aviso de que destinatários não autorizados devem ser removidos da mensagem](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Notificações e substituições do usuário

Você pode usar notificações e substituições para instruir usuários sobre políticas de DLP e ajudá-los a permanecer em conformidade sem bloquear seu trabalho. Por exemplo, se um usuário tentar compartilhar um documento que contém informações confidenciais, uma política de DLP pode enviar uma notificação por email e mostrar uma dica de política no contexto da biblioteca de documentos que permite substituir a política se ele tivere uma justificativa de negócios.
  
![Seções de notificações e substituições do usuário do editor de regras DLP](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
O email pode notificar a pessoa que enviou, compartilhou ou modificou o conteúdo por último e, no caso de conteúdo de sites, o administrador principal do conjunto de sites e o proprietário do documento. Além disso, você pode adicionar ou remover quem quiser na notificação por email.
  
Além de enviar uma notificação por email, uma notificação do usuário exibe uma dica de política:
  
- No Outlook e no Outlook na Web.
    
- Para o documento no SharePoint ou no site do OneDrive for Business.
    
- No Excel, PowerPoint, e Word, quando o documento está armazenado em um site incluído em uma política DLP.
    
A notificação de email e a dica de política explicam a razão do conflito do conteúdo com uma política DLP. Se você escolher, a notificação por email e a dica de política podem permitir que usuários substituam uma regra ao relatar um falso positivo ou fornecer uma justificativa de negócios. Isso pode ajudar você a treinar os usuários sobre as políticas de DLP e aplicá-las sem impedir que as pessoas façam seu trabalho. Informações sobre substituições e falsos positivos também são registradas para relatório (veja abaixo sobre os relatórios de DLP) e incluídas nos relatórios de incidentes (próxima seção), para que o responsável pela conformidade possa analisar regularmente essas informações.
  
Esta é a aparência de uma dica de política em uma conta do OneDrive for Business.
  
![Dica de política para um documento em uma conta do OneDrive](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 Para saber mais sobre as notificações de usuário e as dicas de política em políticas DLP, confira [Usar notificações e dicas de política](use-notifications-and-policy-tips.md).

#### <a name="alerts-and-incident-reports"></a>Relatórios de alertas e Incidentes

Quando uma regra é correspondida, você pode enviar um email de alerta ao responsável pela conformidade (ou a qualquer pessoa(s) que você escolher) com os detalhes do alerta. O email de alerta carregará um link do [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md) que o responsável pela conformidade pode acessar para exibir os detalhes do alerta e eventos. O painel contém detalhes do evento que acionou o alerta junto com detalhes da política DLP combinada e o conteúdo confidencial detectado.

Além disso, também pode ser enviado um relatório de incidentes com detalhes do evento. Esse relatório inclui informações sobre o item que foi correspondido, o conteúdo real que correspondeu à regra e o nome da pessoa que modificou o conteúdo por último. Para mensagens de email, o relatório também inclui a mensagem original como anexo que corresponde a uma política DLP.

> [!div class="mx-imgBorder"]
> ![Página para configurar relatórios de incidente](../media/Alerts-and-incident-report.png)

O DLP verifica os e-mails de forma diferente da dos itens do SharePoint Online ou do OneDrive for Business. No Microsoft Office SharePoint Online e no Microsoft OneDrive for Business, a DLP verifica os itens existentes e também os novos e gera um alerta e relatório de incidentes sempre que uma correspondência é encontrada. No Exchange Online, a DLP verifica apenas novas mensagens de email e gera um relatório se houver uma correspondência de política. O DLP ***não*** verifica ou combina os itens de e-mail existentes anteriormente que são armazenados em uma caixa de correio ou arquivo morto.
  
## <a name="grouping-and-logical-operators"></a>Agrupamento e operadores lógicos

Muitas vezes, sua política DLP tem um requisito direto, como identificar todo o conteúdo que contém um número de CPF. No entanto, em outras situações, talvez seja necessário que sua política DLP identifique dados definidos de forma mais flexível.
  
Por exemplo, para identificar conteúdo sujeito à HIPAA (Lei de Seguro de Saúde) dos EUA, você precisa procurar:
  
- Conteúdo que apresente tipos específicos de informações confidenciais, como um Número de Seguro Social dos EUA ou Número da DEA (Agência de Combate às Drogas dos EUA).
    
    E
    
- Conteúdo que é mais difícil de identificar, como comunicações sobre cuidados de um paciente ou descrições de serviços médicos fornecidos. Identificar esse conteúdo requer a combinação de palavras-chave de listas de palavras-chave muito extensas, como a Classificação Internacional de Doenças (ICD-9-CM ou ICD-10-CM).
    
Você pode identificar facilmente esses dados definidos de forma mais flexível usando agrupamentos e operadores lógicos (E, OU). Ao criar uma política DLP, você pode:
  
- Agrupar tipos de informações confidenciais.
    
- Escolher o operador lógico entre os tipos de informações confidenciais dentro de um grupo e entre os próprios grupos.
    
### <a name="choosing-the-operator-within-a-group"></a>Escolher o operador dentro de um grupo

Dentro de um grupo, você pode escolher se uma ou todas as condições desse grupo devem ser atendidas para que o conteúdo corresponda à regra.
  
![Grupo que mostra os operadores dentro do grupo](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Adicionar um grupo

Você pode adicionar rapidamente um grupo, que pode ter suas próprias condições e operador dentro desse grupo.
  
![Botão Adicionar Grupo](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Escolher o operador entre grupos

Entre grupos, você pode escolher se as condições em apenas um grupo ou todos os grupos devem ser atendidas para que o conteúdo corresponda à regra.
  
Por exemplo, a política interna **HIPAA (Lei de Seguro de Saúde) dos EUA** tem uma regra que usa um operador **E** entre os grupos para que identifique o conteúdo que apresente: 
  
- do grupo **Identificadores PII** (pelo menos um número de CPF **OU** número da Agência de Combate às Drogas) 
    
    **E**
    
- do grupo **Termos Médicos** (pelo menos uma palavra-chave do ICD-9-CM **OU** do ICD-10-CM) 
    
![Grupos que mostram o operador entre grupos](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>A prioridade em que as regras são processadas

Quando você cria regras em uma política, cada regra recebe uma prioridade na ordem em que ela é criada, ou seja, a regra criada primeiro tem a primeira prioridade, a regra criada em segundo lugar tem a segunda prioridade e assim por diante.

> [!div class="mx-imgBorder"]
> ![Regras na ordem de prioridade](../media/dlp-rules-in-priority-order.png)
  
Após configurar mais de uma política DLP, você pode alterar a prioridade de uma ou mais políticas. Para fazer isso, selecione uma política, clique em **Editar política** e use a lista **Prioridade** para especificar a prioridade.

> [!div class="mx-imgBorder"]
> ![Definir prioridade de uma política](../media/dlp-set-policy-priority.png)

Quando o conteúdo é avaliado em relação às regras, estas são processadas na ordem de prioridade. Se o conteúdo corresponde a várias regras, as regras são processadas na ordem de prioridade, e a ação mais restritiva será aplicada. Por exemplo, se o conteúdo corresponder a todas as regras a seguir, a Regra 3 será aplicada porque tem a prioridade mais alta, é a regra mais restritiva:
  
- Regra 1: apenas notifica os usuários
    
- Regra 2: notifica os usuários, restringe o acesso e permite o usuário substituir
    
- Regra 3: notifica os usuários, restringe o acesso e não permite o usuário substituir
    
- Regra 4: apenas notifica os usuários
    
- Regra 5: restringe o acesso
    
- Regra 6: notifica os usuários, restringe o acesso e não permite o usuário substituir
    
Nesse exemplo, observe que as correspondências para todas as regras são registradas nos logs de auditoria e exibidas nos relatórios de DLP, embora apenas a regra mais restritiva seja aplicada.
  
Referente às dicas de política, observe que:
  
- Apenas a dica de política da prioridade mais alta e restritiva será exibida. Por exemplo, uma dica de política de uma regra que bloqueia o acesso ao conteúdo será mostrada em detrimento de uma dica de política de uma regra que simplesmente envia uma notificação. Isso impede que as pessoas vejam uma cascata de dicas de política.
    
- Se as dicas de política na regra mais restritiva permitir que as pessoas substituam a regra, substituir essa regra também substitui quaisquer outras regras que o conteúdo correspondeu.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Ajustar as regras para que a correspondência seja mais fácil ou mais difícil

Após criar e ativar as políticas de DLP, algumas vezes ocorre esses problemas:
  
- Grande parte do conteúdo que **não é** confidencial corresponde com as regras, ou seja, há muitos falsos positivos. 
    
- Pequena parte do conteúdo que **tem** informações confidenciais corresponde com as regras. Em outras palavras, as ações de proteção não estão sendo aplicadas nas informações confidenciais. 
    
Para resolver esses problemas, você pode regular suas regras ajustando a contagem de instância e a precisão da correspondência para dificultar ou facilitar a correspondência do conteúdo às regras. Cada tipo de informação confidencial usado em uma regra tem uma contagem de instância e uma precisão de correspondência.
  
### <a name="instance-count"></a>Contagem de instâncias

A contagem de instâncias se refere à quantidade de ocorrências de um tipo específico de informação confidencial que deve estar presente para que o conteúdo corresponda à regra. Por exemplo, o conteúdo corresponde com a regra mostrada abaixo se entre 1 e 9 passaportes únicos dos EUA ou UE são identificados.

> [!NOTE]
> A contagem de instâncias inclui apenas correspondências **exclusivas** para palavras-chave e tipos de informações confidenciais. Por exemplo, se um email contém 10 ocorrências do mesmo número de cartão de crédito, as 10 ocorrências são contadas como uma única instância de um número de cartão de crédito.
  
Para usar a contagem de instâncias para ajustar as regras, a orientação é simples:
  
- Para tornar a regra mais fácil para a correspondência, diminua a contagem **mín** e/ou aumente a contagem **máx**. Também é possível definir o **máx** para **qualquer** excluindo o valor numérico. 
    
- Para tornar a regra mais difícil para a correspondência, aumente a contagem **mín**. 
    
Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma contagem de instâncias inferior (por exemplo, 1-9). E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça substituição, em uma regra com uma contagem de instância superior (por exemplo, 10 – qualquer).
  
![Contagens de instância no editor de regra](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Precisão de correspondência

Conforme descrito acima, o tipo de informação confidencial é definido e detectado usando uma combinação de diferentes tipos de evidências. Em geral, um tipo de informação confidencial é definido por várias dessas combinações, chamadas padrões. Um padrão que requer menos evidências tem uma precisão de correspondência inferior (ou nível de confiança), enquanto um padrão que exige mais evidências tem uma maior precisão de correspondência (ou nível de confiança). Para saber mais sobre os padrões reais e os níveis de confiança usados por todos os tipos de informações confidenciais, consulte [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md).
  
Por exemplo, o tipo de informação confidencial chamado Número de Cartão de Crédito é definido por dois padrões:
  
- Um padrão com confiança de 65% que exige:
    
  - Um número no formato de um número de cartão de crédito.
    
  - Um número que passa na soma de verificação.
    
- Um padrão com confiança de 85% que exige:
    
  - Um número no formato de um número de cartão de crédito.
    
  - Um número que passa na soma de verificação.
    
  - Uma palavra-chave ou uma data de validade no formato certo.
    
Você pode usar esses níveis de confiança (ou precisão de correspondência) em suas regras. Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma precisão de correspondência inferior. E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça uma substituição, em uma regra com uma precisão de correspondência superior.
  
É importante compreender que quando um tipo específico de informação confidencial, como um número de cartão de crédito, é identificado no conteúdo, somente um único nível de confiança é retornado:
  
- Se todas as correspondências forem para um único padrão, o nível de confiança para aquele padrão será retornado.
    
- Se houver correspondências para mais de um padrão (ou seja, há correspondências com dois níveis de confiança diferentes), o nível de confiança maior do que qualquer um dos padrões únicos sozinhos será retornado. Esta é a parte desafiadora. Por exemplo, para um cartão de crédito, se os padrões de 65% e 85% forem atendidos, o nível de confiança retornado para aquele tipo de informação confidencial será maior que 90%, pois quanto mais evidências, mais confiança.
    
Portanto, se você quiser criar duas regras mutuamente exclusivas para cartões de crédito, uma para a precisão de correspondência de 65% e outro para a precisão de correspondência de 85%, os intervalos para a precisão de correspondência serão parecidos com isto: A primeira regra pega apenas as correspondências ao padrão de 65%. A segunda regra pega as correspondências com **pelo menos uma** correspondência de 85% e **pode ter** outras correspondências de confiança inferiores. 
  
![Duas regras com intervalos diferentes para precisão de correspondência](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Por essas razões, a orientação para a criação de regras com diferentes precisões de correspondência é:
  
- O menor nível de confiança normalmente usa o mesmo valor para **mín** e **máx** (não um intervalo). 
    
- O nível mais alto de confiança é um intervalo entre o valor logo acima do nível de confiança inferior a 100.
    
- Qualquer nível de confiança intermediário normalmente varia de um valor logo acima do nível de confiança inferior para um valor logo abaixo do nível de confiança superior.
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Usar um rótulo de retenção como condição em uma política DLP

Ao usar um [rótulo de retenção](retention.md#retention-labels) criado e publicado anteriormente como condição em uma política DLP, há algumas coisas a serem observadas:

- O rótulo de retenção deve ser criado e publicado antes de tentar usá-lo como condição em uma política DLP.
- Os rótulos de retenção publicados podem levar de um a sete dias para sincronização. Para obter mais informações, confira [Quando os rótulos de retenção se tornam disponíveis para aplicar](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) para rótulos de retenção publicados em uma política de retenção e [Quanto tempo leva para os rótulos de retenção entrarem em vigor](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) para os rótulos de retenção que são publicados automaticamente.
- O uso de um rótulo de retenção em uma política **só tem suporte para itens do Microsoft Office SharePoint Online e OneDrive***.

  ![Rótulos como uma condição](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  Talvez você queira usar um rótulo de retenção em uma política DLP se tiver itens que estão sob retenção e descarte, e também aplicar outros controles a eles, por exemplo:

  - Você publicou um rótulo de retenção denominado **ano fiscal 2018**, que quando aplicado aos documentos fiscais de 2018 armazenados no SharePoint, os retém por dez anos e só após esse prazo os descarta. Use também uma política DLP para impedir que itens sejam compartilhados fora da organização.

  > [!IMPORTANT]
  > Você receberá a seguinte mensagem de erro se especificar um rótulo de retenção como uma condição em uma política DLP e também incluir o Exchange e/ou Teams como um local: **"não há suporte para a proteção de conteúdo rotulado em mensagens de email e equipes. Remova a etiqueta a seguir ou desative o Exchange e o Teams como um local."** Isso ocorre porque o transporte do Exchange não avalia os metadados do rótulo durante o envio e a entrega da mensagem. 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>Usar um rótulo de confidencialidade como condição em uma política DLP

[Saiba mais](./dlp-sensitivity-label-as-condition.md) sobre como usar o rótulo de sensibilidade como condição nas políticas de DLP.
  
### <a name="how-this-feature-relates-to-other-features"></a>Como esse recurso se relaciona a outros recursos

Diversos recursos podem ser aplicados ao conteúdo com informações confidenciais:
  
- Um [rótulo de retenção e uma política de retenção](retention.md) podem impor ações de **retenção** nesse conteúdo. 
    
- Uma política de DLP pode impor ações de **proteção** nesse conteúdo. E antes de aplicar essas ações, uma política de DLP pode exigir que outras condições sejam atendidas além do conteúdo que contém um rótulo. 
    
![Diagrama de recursos que podem ser aplicados a informações confidenciais](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Observe que uma política de DLP tem um recurso de detecção mais avançado do que um rótulo ou política de retenção aplicada a informações confidenciais. Uma política de DLP pode impor ações de proteção ao conteúdo que contiver informações confidenciais e se as informações confidenciais forem removidas do conteúdo, essas ações de proteção serão desfeitas da próxima vez que o conteúdo for verificado. Mas se uma política ou rótulo de retenção for aplicado ao conteúdo com informações confidenciais, essa será uma ação única que não será desfeita, mesmo se as informações confidenciais forem removidas.
  
Usando um rótulo como uma condição em uma política de DLP, você pode aplicar ações de retenção e proteção no conteúdo com esse rótulo. Pense no conteúdo com um rótulo exatamente como um conteúdo com informações confidenciais – tanto um rótulo quanto um tipo de informação confidencial são propriedades usadas para classificar o conteúdo, para poder impor ações para esse conteúdo.
  
![Diagrama de política de DLP usando rótulo como uma condição](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Configurações simples versus configurações avançadas

Ao criar uma política DLP, decida entre configurações simples ou avançadas:
  
- **Configurações simples** facilitam a criação do tipo mais comum de política DLP sem usar o editor de regras para criar ou modificar regras. 
    
- **Configurações avançadas** usam o editor de regras para oferecer controle completo sobre cada configuração para a sua política DLP. 
    
As configurações simples e as avançadas funcionam exatamente da mesma forma, aplicando regras compostas por condições e ações. A única diferença e que, com as configurações simples, você não ver o editor de regras. Trata-se de uma maneira rápida de criar uma política DLP.
  
### <a name="simple-settings"></a>Configurações simples

Sem dúvida, o cenário mais comum de DLP é criar uma política para ajudar a evitar que um conteúdo com informações confidenciais seja compartilhado com pessoas fora da sua organização e realizar uma ação corretiva automática, como restringir quem pode acessar o conteúdo, enviar notificações ao usuário final ou ao administrador e auditar o evento para investigação posterior. As pessoas usam a DLP para ajudar a evitar a divulgação acidental de informações confidenciais.
  
Para simplificar essa meta, ao criar uma política DLP, você pode escolher **Usar configurações simples**. Essas configurações fornecem todos os elementos necessários para implementar a política DLP mais comum, sem precisar acessar o editor de regras.
  
![Opções de DLP para configurações simples e avançadas](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Configurações avançadas

Se você precisa criar políticas DLP mais personalizadas, pode escolher **Usar configurações avançadas**.
  
As configurações avançadas apresentam o editor de regras, no qual você tem controle total sobre todas as opções possíveis, incluindo a contagem de instâncias e a precisão de correspondência (nível de confiança) de cada regra.
  
Para acessar rapidamente uma seção, clique em um item na navegação superior do editor de regras para ir até essa seção abaixo.
  
![Menu de navegação superior do editor de regras DLP](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>Modelos de política DLP

A primeira etapa na criação de uma política DLP é escolher quais informações serão protegidas. A partir de um modelo DLP, você economiza o trabalho de criar um novo conjunto de regras do zero e descobrir quais tipos de informações devem ser incluídas por padrão. Em seguida, você pode adicionar ou modificar esses requisitos para ajustar a regra para atender aos requisitos específicos da sua organização.
  
Um modelo de política DLP pré-configurado pode ajudar a detectar tipos específicos de informações confidenciais, como dados de HIPAA, dados de PCI-DSS, dados da Lei Gramm-Leach-Bliley ou até informações de identificação pessoal (PII) específicas de localidade. Para facilitar a localização e a proteção de tipos comuns de informações confidenciais, os modelos de política incluídos no Microsoft 365 já contêm os tipos mais comuns de informações confidenciais necessários para você começar.
  
![Lista de modelos para políticas de prevenção contra perda de dados com o foco no modelo para a Lei Patriota dos EUA](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Sua organização também pode ter suas próprias exigências específicas e, nesse caso, você pode criar uma política DLP do zero, escolhendo a opção **Política personalizada**. Uma política personalizada é vazia e não contém regras pré-criadas. 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>Relatórios DLP

Após criar e ativar as políticas de DLP, verifique se elas estão funcionando conforme esperado e se estão ajudando a manter a conformidade. Com os relatórios de DLP, você pode exibir rapidamente o número de correspondências de regra e política de DLP ao longo do tempo e o número de falsos positivos e substituições. Para cada relatório, você pode filtrar as correspondências por local, intervalo de tempo e até mesmo restringi-lo a uma diretiva, regra ou ação específica.
  
Com os relatórios de DLP, você pode obter ideias de negócios e:
  
- Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.
    
- Descobrir os processos de negócios que violam as políticas de conformidade da sua organização.
    
- Compreender qualquer impacto nos negócios das políticas de DLP.
    
Além disso, você pode usar os relatórios de DLP para ajustar suas políticas de DLP conforme as executar.
  
![Painel de Relatórios no Centro de Conformidade e Segurança](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Como funcionam as políticas de DLP

A DLP detecta informações confidenciais usando análise profunda de conteúdo (não apenas uma simples verificação de texto). Essa análise profunda de conteúdo usa correspondências de palavra-chave, correspondências de dicionário, a avaliação de expressões regulares, funções internas e outros métodos para detectar conteúdos que violam as políticas de DLP. Possivelmente, apenas uma pequena porcentagem dos seus dados é considerada confidencial. Uma política de DLP pode identificar, monitorar e proteger automaticamente apenas esses dados, sem impedir ou afetar as pessoas que trabalham com o restante do seu conteúdo.
  
### <a name="policies-are-synced"></a>As políticas são sincronizadas

Após criar uma política de DLP no Centro de Segurança &amp; Conformidade, ela é armazenada em um repositório central de políticas e sincronizada com várias fontes de conteúdo, incluindo:
  
- Exchange Online, e de lá para o Outlook na Web e o Outlook.
    
- Sites do OneDrive for Business.
    
- Sites do SharePoint Online.
    
- Programas da área de trabalho do Office (Excel, PowerPoint e Word)

- Mensagens de canais e de chats do Microsoft Teams.
    
Após a sincronização da política com os locais corretos, ela começa avaliar o conteúdo e aplicar as ações.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Avaliação da política em sites do OneDrive for Business e do SharePoint Online

Em todos os seus sites do SharePoint Online e sites do OneDrive for Business, os documentos estão em constante mudança — eles estão continuamente sendo criados, editados, compartilhados, movidos e assim por diante. Isso significa que os documentos podem conflitar ou ficar em conformidade com uma política de DLP a qualquer momento. Por exemplo, uma pessoa pode carregar um documento que não contém nenhuma informação confidencial para seus sites de equipe, mas, posteriormente, outra pessoa pode editar o mesmo documento e adicionar informações confidenciais a ele.
  
Por esse motivo, as políticas de DLP verificam documentos em busca de correspondências de política com frequência em segundo plano. Você pode considerar isso uma avaliação assíncrona da política.<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Como funciona
 
À medida em que as pessoas adicionam ou alteram documentos em seus sites, o mecanismo de pesquisa examina o conteúdo, para que você possa pesquisá-lo posteriormente. Enquanto isso, o conteúdo também será verificado quanto às informações confidenciais e para verificar se ele é compartilhado. Todas as informações confidenciais encontradas serão armazenadas de forma segura no índice de pesquisa, de modo que somente a equipe de conformidade possa acessá-la, mas não usuários comuns. Cada política de DLP ativada é executada em segundo plano (de forma assíncrona), verificando a pesquisa frequentemente por qualquer conteúdo que corresponda a uma política e aplicando ações para protegê-lo contra perdas acidentais.
  
![Diagrama mostrando como a política DLP avalia o conteúdo de forma assíncrona](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --> Por fim, os documentos podem conflitar uma política de DLP, mas eles também podem ficar em conformidade com ela. Por exemplo, se uma pessoa adicionar números de cartão de crédito a um documento, isso poderá fazer com que uma política de DLP bloqueie o acesso ao documento automaticamente. Mas, se a pessoa remover, mais tarde, as informações confidenciais, a ação (neste caso, bloqueio) será desfeita na próxima vez que se avaliar se o documento está de acordo com a política.
  
A DLP avalia qualquer conteúdo que pode ser indexado. Para saber mais sobre os tipos de arquivo que são rastreados por padrão, confira [Extensões de nomes de arquivos rastreados e tipos de arquivos padrão analisados no SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).

> [!NOTE]
> Para evitar que os documentos sejam compartilhados antes que as políticas DLP tivessem a oportunidade de analisá-los, o compartilhamento de novos arquivos no SharePoint pode ser bloqueado até que seu conteúdo seja indexado. Confira [Marcar novos arquivos como confidenciais por padrão](/sharepoint/sensitive-by-default) para obter informações detalhadas. 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Avaliação de políticas no Exchange Online, Outlook e Outlook na Web

Ao criar uma política DLP que inclui o Exchange Online como um local, a política foi sincronizada no Centro de Conformidade &amp; Segurança do Office 365 para o Exchange Online e, em seguida, do Exchange Online para o Outlook na Web e no Outlook.
  
Quando uma mensagem está sendo redigida no Outlook, o usuário pode ver dicas de política à medida que o conteúdo sendo criado é avaliado em relação às políticas DLP. Após uma mensagem ser enviada, ela é avaliada em relação às políticas DLP como parte normal do fluxo de emails, juntamente com regras de fluxo de emails do Exchange e as políticas DLP criadas no Centro de Administração do Exchange. As políticas DLP examinam tanto a mensagem quanto os anexos.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Avaliação de política nos programas da área de trabalho do Office

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint e Word incluem os mesmos recursos para identificar informações confidenciais e aplicar políticas de DLP como o SharePoint Online e o OneDrive for Business. Esses programas do Office sincronizam suas políticas DLP diretamente do repositório central de políticas e, em seguida, avaliam continuamente o conteúdo em relação às políticas DLP quando as pessoas trabalham com documentos abertos de um site incluso em uma política DLP.
  
A avaliação das políticas DLP no Office foi desenvolvida para não afetar o desempenho dos programas ou a produtividade de pessoas que trabalham no conteúdo. Se estiverem trabalhando em um documento grande ou o computador do usuário estiver ocupado, pode demorar alguns segundos para uma dica de política ser exibida.

### <a name="policy-evaluation-in-microsoft-teams"></a>Avaliação de políticas no Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

Ao criar uma política DLP que inclui o Microsoft Teams como um local, a política foi sincronizada no centro de Conformidade &amp; Segurança do Office 365 para contas de usuários e mensagens de chat e de canais do Microsoft Teams. Dependendo da configuração das políticas DLP, quando alguém tentar compartilhar informações confidenciais em uma mensagem de chat ou canal do Microsoft Teams, a mensagem pode ser bloqueada ou revogada. Os documentos com informações confidenciais e que são compartilhados com convidados (usuários externos) não abrirão para esses usuários. Para saber mais, confira [Prevenção contra perda de dados no Microsoft Teams](dlp-microsoft-teams.md).
 
## <a name="permissions"></a>Permissões

Os membros da sua equipe de conformidade que irão criar políticas DLP precisam de permissões ao Centro de Conformidade &amp; Segurança. Por padrão, o administrador de locatário terá acesso a esse local e pode conceder aos responsáveis pela conformidade e outras pessoas acesso ao Centro de Conformidade &amp; Segurança, sem conceder todas as permissões de um administrador de locatário. Para fazer isso, recomendamos:
  
1. Crie um grupo no Microsoft 365 e adicione os responsáveis pela conformidade.
    
2. Criar um grupo de funções na página **Permissões** do Centro de Conformidade &amp; Segurança. 

3. Ao criar o grupo de função, use a seção **Escolher funções** para adicionar a seguinte função ao Grupo de função: **Gerenciamento de conformidade DLP**.
    
4. Use a seção **Escolher membros** para adicionar o grupo Microsoft 365 que você criou anteriormente ao grupo de função.

Você também pode criar um grupo de função com privilégios de somente exibição às Políticas DLP e aos Relatórios DLP, concedendo a função **Gerenciamento de conformidade DLP somente exibição**.

Para saber mais, consulte [Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Essas permissões são necessárias somente para criar e aplicar uma política de DLP. A imposição da política não exige acesso ao conteúdo.
  
## <a name="find-the-dlp-cmdlets"></a>Encontre os cmdlets da DLP

Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:
  
1. [Conectar-se ao Centro de Conformidade &amp; e Segurança do Office 365 usando o PowerShell Remoto](/powershell/exchange/connect-to-scc-powershell).
    
2. Usar qualquer um destes [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).
    
No entanto, os relatórios DLP precisam extrair dados do Microsoft 365, incluindo o Exchange Online. Por esse motivo, **os cmdlets para os relatórios DLP estão disponíveis no Exchange Online Powershell, e não no Centro de Conformidade &amp; Segurança do Powershell**. Portanto, para usar os cmdlets para os relatórios DLP, você precisa:
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Usar qualquer um destes cmdlets para os relatórios DLP:
    
    - [Get-DlpDetectionsReport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailReport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>Mais informações

- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
    
- [Enviar notificações e exibir dicas de políticas para as políticas DLP](use-notifications-and-policy-tips.md)
    
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](protect-documents-that-have-fci-or-other-properties.md)
    
- [O que os modelos de política DLP incluem](what-the-dlp-policy-templates-include.md)
    
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
    
- [O que as funções DLP procuram](what-the-dlp-functions-look-for.md)
    
- [Criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md)
