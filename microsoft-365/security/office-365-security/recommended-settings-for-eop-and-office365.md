---
title: Recomendações da Microsoft para EOP e Defender para Office 365 de segurança
keywords: Office 365 recomendações de segurança, Estrutura de Política de Remetente, Relatório e Conformidade de Mensagens baseados em domínio, Email Identificado por DomainKeys, etapas, como funciona, linhas de base de segurança, linhas de base para EOP, linhas de base do Defender para Office 365, configurar o Defender para Office 365, configurar o EOP, configurar o Defender para Office 365, configurar eOP, configuração de segurança
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Quais são as práticas recomendadas para Proteção do Exchange Online (EOP) e Defender para Office 365 configurações de segurança? Quais são as recomendações atuais para proteção padrão? O que deve ser usado se você quiser ser mais rigoroso? E quais extras você obterá se também usar o Defender para Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04668932747462d2636b466d87c2655d97569657
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624068"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Configurações recomendadas para o EOP e o Microsoft Defender para Office 365 segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Proteção do Exchange Online (EOP)** é o núcleo de segurança para assinaturas Microsoft 365 e ajuda a impedir que emails mal-intencionados atinjam as caixas de entrada do funcionário. Porém, com ataques novos e mais sofisticados que surgem a cada dia, proteções aprimoradas são frequentemente necessárias. **Microsoft Defender para Office 365** O Plano 1 ou o Plano 2 contém recursos adicionais que dão aos administradores mais camadas de segurança, controle e investigação.

Embora nós capacitamos os administradores de segurança a personalizar suas configurações de segurança, há dois níveis de segurança no EOP e no Microsoft Defender para Office 365 que recomendamos: **Standard** e **Strict**. O ambiente e as necessidades de cada cliente são diferentes, mas acreditamos que esses níveis de filtragem ajudarão a impedir que emails indesejados atinjam a Caixa de Entrada de seus funcionários na maioria das situações.

Para aplicar automaticamente as configurações Standard ou Strict aos usuários, consulte [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

> [!NOTE]
> A regra de lixo eletrônico precisa ser habilitada em caixas de correio para que a filtragem funcione corretamente. Ele está habilitado por padrão, mas você deve verificar se a filtragem não parece estar funcionando. Para obter mais informações, confira [Definir as configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

Este artigo descreve as configurações padrão e também as configurações padrão e estrita recomendadas para ajudar a proteger seus usuários.

> [!TIP]
> O Office 365 do Analisador de Configuração Recomendado para Proteção avançada contra Ameaças (ORCA) para o PowerShell pode ajudá-lo (administradores) a encontrar os valores atuais dessas configurações. Especificamente, o cmdlet **Get-ORCAReport** gera uma avaliação de anti-spam, anti-phishing e outras configurações de higienização de mensagens. Você pode baixar o módulo ORCA em <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Proteção anti-spam, anti-malware e anti-phishing no EOP

Anti-spam, anti-malware e anti-phishing são recursos do EOP que podem ser configurados pelos administradores. Recomendamos as seguintes configurações Padrão ou Estrita.

### <a name="eop-anti-spam-policy-settings"></a>Configurações de política anti-spam do EOP

Para criar e configurar políticas anti-spam, consulte [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Ação de detecção** de spam <p> _SpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de spam** de alta confiança <p> _HighConfidenceSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email de phishing** <p> _PhishSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email de phishing** de alta confiança <p> _HighConfidencePhishAction_|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`|**Mensagem em quarentena** <p> `Quarantine`||
|**Ação de detecção de email** em massa <p> _BulkSpamAction_|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mover mensagem para a pasta Lixo Eletrônico** <p> `MoveToJmf`|**Mensagem em quarentena** <p> `Quarantine`||
|Limite de email em massa <p> _BulkThreshold_|7 |6 |4 |Para obter detalhes, consulte [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Período de retenção de quarentena <p> _QuarantineRetentionPeriod_|15 dias|30 dias|30 dias||
|**Segurança Dicas** <p> _InlineSafetyTipsEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|Senders permitidos <p> _AllowedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios permitidos do Remetente <p> _AllowedSenderDomains_|Nenhum|Nenhum|Nenhum|Adicionar domínios à lista de envios permitidos é uma ideia muito ruim. Os invasores seriam capazes de enviar emails que seriam filtrados de outra forma. <p> Use o insight de inteligência de [spoof](learn-about-spoof-intelligence.md) e a Lista de Locatários [Permitir/Bloquear](tenant-allow-block-list.md) no Centro de Conformidade de Segurança & para analisar todos os remetentes que estão fazendo a spoofing de endereços de email de remetente nos domínios de email da sua organização ou a spoofing de endereços de email de remetente em domínios externos.|
|Senders bloqueados <p> _BlockedSenders_|Nenhum|Nenhum|Nenhum||
|Domínios de remetente bloqueados <p> _BlockedSenderDomains_|Nenhum|Nenhum|Nenhum||
|**Habilitar notificações de spam para o usuário final** <p> _EnableEndUserSpamNotifications_|Desabilitado <p> `$false`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Envie notificações de spam para o usuário final a cada (dias)** <p> _EndUserSpamNotificationFrequency_|3 dias|3 dias|3 dias||
|**Spam ZAP** <p> _SpamZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|_MarkAsSpamBulkMail_|Habilitado|Habilitado|Habilitado|Essa configuração só está disponível no PowerShell.|
|

Há várias outras configurações de Filtro de Spam Avançado (ASF) em políticas anti-spam que estão sendo preteridas. Mais informações sobre as linhas do tempo para a depreciação desses recursos serão comunicadas fora deste artigo.

Recomendamos desativar essas configurações ASF **para** níveis **Padrão** **e Estrito.** Para obter mais informações sobre as configurações do ASF, consulte [AsF (Advanced Spam Filter) settings in Office 365](advanced-spam-filtering-asf-options.md).

<br>

****

|Nome do recurso de segurança|Comentário|
|---|---|
|**Links de imagem para sites remotos** (_IncreaseScoreWithImageLinks_)||
|**Endereço IP numérico na URL** (_IncreaseScoreWithNumericIps_)||
|**Redirecionamento ul para outra porta** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL para sites .biz ou .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Mensagens vazias** (_MarkAsSpamEmptyMessages_)||
|**JavaScript ou VBScript em HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Marcas frame ou IFrame em HTML** (_MarkAsSpamFramesInHtml_)||
|**Marcas de objeto em HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Inserir marcas em HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Marcas de formulário em HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Bugs da Web em HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Aplicar lista de palavras confidenciais** (_MarkAsSpamSensitiveWordList_)||
|**Registro SPF: falha grave** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtragem de ID do Remetente Condicional: falha dura** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter de NDR** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Configurações de política de spam de saída do EOP

Para criar e configurar políticas de spam de saída, consulte [Configure outbound spam filtering in Office 365](configure-the-outbound-spam-policy.md).

Para obter mais informações sobre os limites de envio padrão no serviço, consulte [Enviando limites](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Número máximo de destinatários por usuário: Limite de horário externo** <p> _RecipientLimitExternalPerHour_|0|500|400|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: Limite interno por hora** <p> _RecipientLimitInternalPerHour_|0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Número máximo de destinatários por usuário: Limite diário** <p> _RecipientLimitPerDay_|0|1000|800|O valor padrão 0 significa usar os padrões de serviço.|
|**Ação quando um usuário excede os limites** <p> _ActionWhenThresholdReached_|**Restringir o usuário de enviar emails até o dia seguinte** <p> `BlockUserForToday`|**Restringir o usuário de enviar emails** <p> `BlockUser`|**Restringir o usuário de enviar emails** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Configurações de política anti-malware do EOP

Para criar e configurar políticas anti-malware, consulte [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Deseja notificar os destinatários se suas mensagens estão em quarentena?** <p> _Action_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Não <p> _DeleteMessage_|Se o malware for detectado em um anexo de email, a mensagem será colocada em quarentena e poderá ser liberada somente por um administrador.|
|**Filtro Common Attachment Types** <p> _EnableFileFilter_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|Essa configuração coloca em quarentena as mensagens que contêm anexos executáveis com base no tipo de arquivo, independentemente do conteúdo do anexo.|
|**Limpeza automática de malware zero hora** <p> _ZapEnabled_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Notificar os envios** internos da mensagem não entregue <p> _EnableInternalSenderNotifications_|Desabilitada <p> `$false`|Desabilitada <p> `$false`|Desabilitada <p> `$false`||
|**Notificar os envios** externos da mensagem não entregue <p> _EnableExternalSenderNotifications_|Desabilitada <p> `$false`|Desabilitada <p> `$false`|Desabilitada <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Configurações de política anti-phishing padrão do EOP

Para obter mais informações sobre essas configurações, consulte [Configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings). Para configurar essas configurações, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Habilitar proteção anti-spoofing** <p> _EnableSpoofIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar Remetente Não Autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente Outlook remetentes não identificados. Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para spoofar seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para as pastas lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para as pastas lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar em quarentena a mensagem** <p> `Quarantine`|Essa configuração se aplica a envios com [spoofed](learn-about-spoof-intelligence.md) que foram bloqueados automaticamente, conforme mostrado no insight de inteligência de spoof ou bloqueado manualmente na Lista de Locatários [Permitir/Bloquear.](tenant-allow-block-list.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender para Office 365 segurança

Benefícios adicionais de segurança vêm com uma assinatura do Microsoft Defender Office 365. Para obter as últimas notícias e informações, você pode ver [Novidades no Defender para](whats-new-in-defender-for-office-365.md)Office 365 .

> [!IMPORTANT]
>
> - A política anti-phishing padrão no Microsoft Defender para Office 365 [fornece](set-up-anti-phishing-policies.md#spoof-settings) proteção contra fraudes e inteligência de caixa de correio para todos os destinatários. No entanto, os outros recursos de proteção [de representação](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponíveis e configurações avançadas não estão configurados ou [habilitados](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) na política padrão. Para habilitar todos os recursos de proteção, modifique a política anti-phishing padrão ou crie políticas anti-phishing adicionais.
>
> - Não há políticas de Cofre links padrão ou Cofre de anexos que protejam automaticamente todos os destinatários na organização. Para obter as proteções, você precisa criar pelo menos uma política Cofre Links e Cofre Anexos.
>
> - [Cofre Anexos](mdo-for-spo-odb-and-teams.md) para SharePoint, OneDrive e Microsoft Teams proteção Cofre [documentos](safe-docs.md) não têm dependências de políticas Cofre Links.

Se sua assinatura incluir o Microsoft Defender para Office 365 ou se você comprou o Defender para Office 365 como um complemento, desmarque as seguintes configurações Padrão ou Estrita.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Configurações de política anti-phishing no Microsoft Defender para Office 365

Os clientes do EOP têm anti-phishing básico conforme descrito anteriormente, mas o Microsoft Defender para Office 365 inclui mais recursos e controle para ajudar a evitar, detectar e correção contra ataques. Para criar e configurar essas políticas, consulte [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de representação em políticas anti-phishing no Microsoft Defender para Office 365

Para obter mais informações sobre essas configurações, consulte [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Para configurar essas configurações, consulte [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|Usuários protegidos: **Adicionar usuários para proteger** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Desabilitado <p> `$false` <p> nenhuma|Habilitado <p> `$true` <p> \<list of users\>|Habilitado <p> `$true` <p> \<list of users\>|Dependendo da sua organização, recomendamos adicionar usuários (envios de mensagens) em funções-chave. Internamente, os envios protegidos podem ser seu CEO, CFO e outros líderes sênior. Externamente, os envios protegidos podem incluir membros do conselho ou seu conselho de diretores.|
|Domínios protegidos: **inclua automaticamente os domínios que eu tenho** <p> _EnableOrganizationDomainsProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|Domínios protegidos: **incluir domínios personalizados** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Desabilitado <p> `$false` <p> nenhuma|Habilitado <p> `$true` <p> \<list of domains\>|Habilitado <p> `$true` <p> \<list of domains\>|Dependendo da sua organização, recomendamos adicionar domínios (domínios de remetente) que você não possui, mas você interage com frequência.|
|Usuários protegidos: **se o email for enviado por um usuário personificado** <p> _TargetedUserProtectionAction_|**Não aplique nenhuma ação** <p> `NoAction`|**Colocar em quarentena a mensagem** <p> `Quarantine`|**Colocar em quarentena a mensagem** <p> `Quarantine`||
|Domínios protegidos: **se o email for enviado por um domínio personificado** <p> _TargetedDomainProtectionAction_|**Não aplique nenhuma ação** <p> `NoAction`|**Colocar em quarentena a mensagem** <p> `Quarantine`|**Colocar em quarentena a mensagem** <p> `Quarantine`||
|**Mostrar dica para usuários personificados** <p> _EnableSimilarUsersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para domínios personificados** <p> _EnableSimilarDomainsSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Mostrar dica para caracteres incomuns** <p> _EnableUnusualCharactersSafetyTips_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Habilitar a Inteligência de Caixa de Correio?** <p> _EnableMailboxIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar a proteção de representação baseada em inteligência de caixa de correio?** <p> _EnableMailboxIntelligenceProtection_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Se o email for enviado por um usuário personificado protegido pela inteligência de caixa de correio** <p> _MailboxIntelligenceProtectionAction_|**Não aplique nenhuma ação** <p> `NoAction`|**Mover mensagem para as pastas lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar em quarentena a mensagem** <p> `Quarantine`||
|**Senders confiáveis** <p> _ExcludedSenders_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos adicionar usuários que são marcados incorretamente como phishing devido apenas à representação e não a outros filtros.|
|**Domínios confiáveis** <p> _ExcludedDomains_|Nenhum|Nenhum|Nenhum|Dependendo da sua organização, recomendamos adicionar domínios que são marcados incorretamente como phishing devido apenas à representação e não a outros filtros.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações de spoof em políticas anti-phishing no Microsoft Defender para Office 365

Observe que essas são as mesmas configurações que estão disponíveis nas configurações de política [anti-spam no EOP](#eop-anti-spam-policy-settings).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|---|---|---|---|
|**Habilitar proteção anti-spoofing** <p> _EnableSpoofIntelligence_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Habilitar Remetente Não Autenticado** <p> _EnableUnauthenticatedSender_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Adiciona um ponto de interrogação (?) à foto do remetente Outlook remetentes não identificados. Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md).|
|**Se o email for enviado por alguém que não tenha permissão para spoofar seu domínio** <p> _AuthenticationFailAction_|**Mover mensagem para as pastas lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Mover mensagem para as pastas lixo eletrônico dos destinatários** <p> `MoveToJmf`|**Colocar em quarentena a mensagem** <p> `Quarantine`|Essa configuração se aplica a envios com [spoofed](learn-about-spoof-intelligence.md) que foram bloqueados automaticamente, conforme mostrado no insight de inteligência de spoof ou bloqueado manualmente na Lista de Locatários [Permitir/Bloquear.](tenant-allow-block-list.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurações avançadas em políticas anti-phishing no Microsoft Defender para Office 365

Para obter mais informações sobre essa configuração, consulte Limites avançados de phishing em políticas [anti-phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)no Microsoft Defender para Office 365 . Para configurar essa configuração, consulte [Configure anti-phishing policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Limites avançados de phishing** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - Agressivo** <p> `2`|**3 - Mais agressivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Cofre Configurações de links

Cofre Os links no Defender para Office 365 incluem configurações globais que se aplicam a todos os usuários incluídos em políticas Cofre Links ativas e configurações específicas para cada política de Links Cofre. Para obter mais informações, [consulte Cofre Links no Defender para Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Configurações globais para Cofre Links

Para configurar essas configurações, consulte [Configure global settings for Cofre Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

No PowerShell, você usa o cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Usar Cofre links em: Office 365 aplicativos** <p> _EnableSafeLinksForO365Clients_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`|Use Cofre Links em aplicativos Office 365 desktop e mobile (iOS e Android). Para obter mais informações, [consulte Cofre Configurações de Links para Office 365 aplicativos](safe-links.md#safe-links-settings-for-office-365-apps).|
|**Não rastreia quando os usuários clicam em Cofre Links** <p> _TrackClicks_|Ativada <p> `$false`|Desativada <p> `$true`|Desabilitado <p> `$true`|Desligar essa configuração (definindo _TrackClicks_ como ) rastreia os cliques do usuário em `$true` aplicativos Office 365 suportados.|
|**Não permitir que os usuários cliquem Cofre links para a URL original** <p> _AllowClickThrough_|Habilitado <p> `$false`|Habilitado <p> `$false`|Habilitado <p> `$false`|A ativá-la _(configurando AllowClickThrough_ como ) impede que clique na URL original em `$false` aplicativos Office 365 suportados.|
|

#### <a name="safe-links-policy-settings"></a>Cofre Configurações de política de links

Para configurar essas configurações, consulte Configurar políticas Cofre [Links no Microsoft Defender para Office 365](set-up-safe-links-policies.md).

No PowerShell, você usa os cmdlets [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) e [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há nenhuma política de Cofre Links padrão. Os valores na coluna Padrão são os valores padrão nas novas Cofre links que você cria.

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens** <p> _IsEnabled_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas dentro Microsoft Teams** <p> _EnableSafeLinksForTeams_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos** <p> _ScanUrls_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aguarde a conclusão da verificação de URL antes de entregar a mensagem** <p> _DeliverMessageAfterScan_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Aplicar Cofre links para mensagens de email enviadas dentro da organização** <p> _EnableForInternalSenders_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`||
|**Não rastrear cliques do usuário** <p> _DoNotTrackUserClicks_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Desligar essa configuração (definindo _DoNotTrackUserClicks_ como `$false` ) rastreia os cliques dos usuários.|
|**Não permitir que os usuários cliquem na URL original** <p> _DoNotAllowClickThrough_|Desativada <p> `$false`|Ativada <p> `$true`|Habilitado <p> `$true`|A ativá-la (definindo _DoNotAllowClickThrough_ como ) impede que `$true` clique na URL original.|
|

### <a name="safe-attachments-settings"></a>Cofre Configurações de anexos

Cofre Os anexos no Microsoft Defender para Office 365 incluem configurações globais que não têm nenhuma relação com as políticas de Cofre Anexos e configurações específicas para cada política Cofre Links. Para obter mais informações, [consulte Cofre Anexos no Defender para Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Configurações globais para Cofre anexos

Para configurar essas configurações, consulte Ativar Cofre anexos para [SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) e Cofre Documentos em [Microsoft 365 E5](safe-docs.md).

No PowerShell, você usa o cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) para essas configurações.

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Ativar o Defender para Office 365, para SharePoint, OneDrive e Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|Habilitado <p> `$true`|Habilitado <p> `$true`||
|**Ativar Cofre documentos para Office clientes** <p> _EnableSafeDocs_|Habilitado <p> `$true`|Habilitado <p> `$true`|Essa configuração só está disponível com Microsoft 365 E5 ou Microsoft 365 E5 Security licenças. Para obter mais informações, [consulte Cofre Documentos no Microsoft Defender para Office 365](safe-docs.md).|
|**Permitir que as pessoas cliquem em Exibição Protegida, mesmo que Cofre Documentos identificaram o arquivo como mal-intencionado** <p> _AllowSafeDocsOpen_|Desabilitado <p> `$false`|Desabilitado <p> `$false`|Essa configuração está relacionada Cofre Documentos.|
|

#### <a name="safe-attachments-policy-settings"></a>Cofre Configurações de política de anexos

Para configurar essas configurações, consulte [Configure up Cofre Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md).

No PowerShell, você usa os cmdlets [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) e [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) para essas configurações.

> [!NOTE]
> Conforme descrito anteriormente, não há nenhuma política Cofre Anexos padrão. Os valores na coluna Padrão são os valores padrão em novas Cofre de anexos que você cria.

<br>

****

|Nome do recurso de segurança|Padrão|Padrão|Estrito|Comentário|
|---|:---:|:---:|:---:|---|
|**Cofre Anexos resposta de malware desconhecido** <p> _Action_|Bloquear <p> `Block`|Bloquear <p> `Block`|Bloquear <p> `Block`||
|**Anexo de redirecionamento na detecção** : **Habilitar redirecionamento** <p> _Redirecionar_ <p> _RedirectAddress_|Desligado e nenhum endereço de email especificado. <p> `$true` <p> nenhuma|On e especifique um endereço de email. <p> `$true` <p> um endereço de email|On e especifique um endereço de email. <p> `$true` <p> um endereço de email|Redirecionar mensagens para um administrador de segurança para revisão.|
|**Aplique a seleção acima se ocorrer uma verificação de malware para anexos ou se ocorrer um erro.** <p> _ActionOnError_|Habilitado <p> `$true`|Habilitado <p> `$true`|Habilitado <p> `$true`||
|

## <a name="related-articles"></a>Artigos relacionados

- Você está procurando práticas recomendadas para Exchange de fluxo de **emails (também conhecidas como regras de transporte**)? Consulte [Práticas recomendadas para configurar regras de fluxo](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)de emails em Exchange Online .

- Os administradores e usuários podem enviar falsos positivos (emails bons marcados como ruins) e falsos negativos (email ruim permitido) para a Microsoft para análise. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

- Use esses links para obter informações sobre como **configurar seu** [serviço EOP](/exchange/standalone-eop/set-up-your-eop-service)e **configurar** o Microsoft [Defender para](defender-for-office-365.md)Office 365 . Não se esqueça das instruções úteis em '[Proteger contra ameaças Office 365](protect-against-threats.md)'.

-  As linhas de base de segurança para Windows podem ser encontradas aqui: onde posso obter as linhas de base de [segurança?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) para opções de GPO/local e Usar linhas de base de segurança para configurar Windows 10 dispositivos no Intune para segurança baseada no [Intune.](/intune/protect/security-baselines) Por fim, uma comparação entre o Microsoft Defender para o Ponto de Extremidade e Microsoft Intune de segurança está disponível em Comparar o Microsoft Defender para Ponto de Extremidade e as linhas de base de segurança [do Windows Intune.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
