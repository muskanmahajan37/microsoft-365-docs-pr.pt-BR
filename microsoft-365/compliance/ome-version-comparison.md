---
title: Comparação de versão de criptografia de mensagens (OME)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Este artigo ajuda a explicar as diferenças entre diferentes versões de Criptografia de Mensagens do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92beb3625c0b115fe77f1667a448bf0bf9589040
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760129"
---
# <a name="compare-versions-of-ome"></a>Comparar versões de OME

> [!IMPORTANT]
> Em 28 de fevereiro de 2021, a Microsoft preteria o suporte ao AD RMS no Exchange Online. Se você implantou um ambiente híbrido em que suas caixas de correio Exchange estão online e está usando o IRM com o ACTIVE Directory RMS no local, será necessário migrar para o Azure. As organizações que implantaram no GCC ambiente Moderado também são afetadas. Consulte "Visão geral da depreciação do AD RMS no Exchange Online" neste artigo para obter informações.

O restante deste artigo compara o Criptografia de Mensagens do Office 365 (OME) herdado aos novos recursos E Criptografia de Mensagem Avançada do Office 365. Os novos recursos são uma fusão e uma versão mais recente do OME e do GERENCIAMENTO de Direitos de Informação (IRM). Características exclusivas da implantação no GCC High também são descritas. Os dois podem coexistir em sua organização. Para obter informações sobre como os novos recursos funcionam, [consulte Criptografia de Mensagens do Office 365 (OME)](ome.md).

Este artigo faz parte de uma série maior de artigos sobre Criptografia de Mensagens do Office 365. Este artigo destina-se a administradores e ITPros. Se você estiver apenas procurando informações sobre como enviar ou receber uma mensagem criptografada, consulte a lista de artigos no [Criptografia de Mensagens do Office 365 (OME)](ome.md) e localize o artigo que melhor atende às suas necessidades.

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Visão geral da depreciação do AD RMS no Exchange Online

Exchange Online inclui a funcionalidade de Gerenciamento de Direitos de Informação (IRM) que fornece proteção online e offline de mensagens de email e anexos. Por padrão, o Exchange Online usa a Proteção de Informações do Azure. No entanto, sua organização pode ter configurado Exchange Online IRM para usar o Serviço de Gerenciamento de Direitos do Active Directory (AD RMS) local. O suporte ao AD RMS no Exchange Online está se retirando. Em vez disso, a Proteção de Informações do Azure substituirá totalmente o AD RMS.

Para avaliar se essa depreciação afeta sua organização, consulte Como migrar o [AD RMS para o Azure RMS no Exchange Online](https://support.microsoft.com/help/5001237). Este artigo fornece recomendações sobre opções de migração.

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>Comparação lado a lado dos recursos e recursos do OME

|           **Situação**           | **OME Herdado**    | **IRM no AD RMS**        | **Novos recursos OME** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*Enviando um email criptografado*        |Por meio Exchange de fluxo de emails|Usuário final iniciado Outlook área de trabalho ou Outlook na Web; ou por meio Exchange de fluxo de emails|Usuário final iniciado Outlook área de trabalho, Outlook para Mac ou Outlook na Web; por meio Exchange de fluxo de emails (também conhecidas como regras de transporte) e Prevenção contra Perda de Dados (DLP)|
|*Modelo de gerenciamento de direitos*       |   N/D      |Opção Não Encaminhar e modelos personalizados|Opção Não Encaminhar, somente criptografia e modelos personalizados|
|*Tipo de destinatário*                   |Destinatários internos e externos|Somente destinatários internos         |Destinatários internos e externos|
|*Experiência para destinatário interno*|Os destinatários recebem uma mensagem HTML, que baixam e abrem em um navegador da Web ou aplicativo móvel|Experiência em linha nativa em Outlook clientes|Experiência em linha nativa para destinatários na mesma organização usando Outlook clientes.  Os destinatários podem ler mensagens do portal OME usando clientes que não Outlook (sem download ou aplicativo necessário).|
|*Experiência para destinatário externo*|Os destinatários recebem uma mensagem HTML, que baixam e abrem em um navegador da Web ou aplicativo móvel|N/D|Experiência em linha nativa para Microsoft 365 destinatários. Todos os outros destinatários podem ler mensagens do portal OME (sem download ou aplicativo necessário).|
|*Permissões de anexo*           |Sem restrições sobre anexos|Os anexos são protegidos|Os anexos são protegidos para a opção Não Encaminhar e modelos personalizados. Os administradores podem escolher se os anexos da opção somente criptografia estão protegidos ou não.|
|*Traga seu próprio suporte de chave (BYOK)*|Nenhum                |Nenhum               |BYOK com suporte          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>Vantagens dos novos recursos OME em relação ao OME herddo

Os novos recursos oferecem as seguintes vantagens:

- Capacidade de usar a opção somente criptografia (que permite a colaboração segura), a opção Não Encaminhar e as restrições personalizadas.
- Os envios podem enviar emails criptografados com os novos recursos manualmente Outlook desktop, Outlook para Mac e Outlook nos clientes Web.
- Microsoft 365 destinatários podem usar uma experiência em linha em clientes Outlook suporte. Como alternativa, os administradores podem optar por mostrar Microsoft 365 destinatários uma experiência de identidade visual.
- Contas fora do Microsoft 365, como contas do Gmail, Yahoo e Microsoft, são federadas com o portal OME, que oferece uma melhor experiência do usuário para esses destinatários. Todas as outras identidades usam um código de passagem única para acessar mensagens criptografadas.
- Os administradores podem personalizar a identidade visual e criar vários modelos de identidade visual.
- Os administradores podem revogar emails criptografados com os novos recursos.
- Os novos recursos fornecem relatórios de uso detalhados por meio do Centro &amp; de Conformidade e Segurança.

## <a name="office-365-advanced-message-encryption-capabilities"></a>Criptografia de Mensagem Avançada do Office 365 recursos

Criptografia de Mensagem Avançada do Office 365 oferece recursos adicionais além dos novos recursos OME. Você deve ter os novos recursos Criptografia de Mensagens do Office 365 de mensagens em sua organização para usar os recursos avançados de Criptografia de Mensagens. Além disso, para usar esses recursos, os destinatários devem exibir e responder ao email seguro por meio do Portal OME. Os recursos avançados incluem:

- Revogação de mensagens

- Expiração da mensagem

- Vários modelos de identidade visual

Criptografia de Mensagem Avançada do Office 365 não há suporte no GCC Alta.

Para obter informações sobre como usar a Criptografia Avançada de Mensagens, [consulte Criptografia de Mensagem Avançada do Office 365](ome-advanced-message-encryption.md).

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>Características exclusivas do Criptografia de Mensagens do Office 365 em uma implantação GCC Alta

Se você planeja usar Criptografia de Mensagens do Office 365 em um ambiente GCC High, há algumas características exclusivas em relação à experiência do destinatário.

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>Email criptografado entre GCC alta e GCC alta destinatários

Os envios podem criptografar manualmente emails no Outlook para PC e Mac e Outlook na Web, ou as organizações podem configurar uma política para criptografar emails usando Exchange regras de fluxo de emails.

Os destinatários dentro GCC High recebem a mesma experiência de leitura em linha no Outlook para pc e Mac e Outlook na Web como todos os outros usuários.

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>Email criptografado entre GCC alta e não GCC alta destinatários

Os senders dentro GCC High podem enviar emails criptografados fora do limite GCC limite alto e vice-versa.

Todos os destinatários fora do GCC High, incluindo usuários comerciais Microsoft 365, usuários Outlook.com e outros usuários de outros provedores de email, como Gmail e Yahoo, recebem um email de wrapper. Esse email de wrapper redireciona o destinatário para o Portal OME onde o destinatário pode ler e responder à mensagem. Isso também é verdadeiro para os envios fora GCC alto envio de emails criptografados OME para GCC Alta.

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>Coexistência do OME herddo e dos novos recursos no mesmo locatário

Você pode usar o OME herddo e os novos recursos no mesmo locatário. Como administrador, você faz isso escolhendo qual versão do OME deseja usar ao criar suas regras de fluxo de emails.

- Para especificar a versão herdada do OME, use a ação Exchange regra de fluxo de email Aplicar a **versão anterior do OME**.

- Para especificar os novos recursos, use a ação Exchange regra de fluxo de email **Aplicar Criptografia de Mensagens do Office 365 proteção de direitos.**

Os usuários podem enviar emails criptografados manualmente com os novos recursos Outlook desktop, Outlook para Mac e Outlook na Web.

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>Migrar do OME herdado para os novos recursos

Embora ambas as versões do OME possam coexistir, é altamente recomendável que você edite suas regras antigas de fluxo de emails que usam a ação de regra Aplique a versão anterior do **OME** para usar os novos recursos. Atualize essas regras para usar a ação de regra de fluxo de emails **Aplicar Criptografia de Mensagens do Office 365 proteção de direitos.** Para obter instruções, consulte [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-ome"></a>Começar com o OME

Normalmente, os novos recursos OME são habilitados automaticamente para sua organização. Para obter mais informações sobre os novos recursos OME em sua organização, consulte [Configurar novos Criptografia de Mensagens do Office 365 recursos](set-up-new-message-encryption-capabilities.md).

A versão herdada do OME será automaticamente habilitada para sua organização se você habilitar a Proteção de Informações do Azure. No passado, o OME herdado funcionava mesmo se a Proteção de Informações do Azure não estivesse habilitada. Isso não acontece mais.

Para começar a usar o OME herdado, se você habilitar a Proteção de Informações do Azure, configure as regras de fluxo de emails que usam a ação de regra Aplique a versão **anterior do OME**. Para obter instruções, consulte [Definir regras de fluxo de emails para criptografar mensagens de email](define-mail-flow-rules-to-encrypt-email.md).