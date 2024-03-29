---
title: Opções de conformidade para Microsoft 365 grupos, Teams e SharePoint colaboração
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Saiba mais sobre opções de conformidade Microsoft 365 grupos, Teams e SharePoint colaboração.
ms.openlocfilehash: 236b977b22066830e1b36bc87676fd5fa2c9d3f5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538118"
---
# <a name="compliance-options-for-microsoft-365-groups-teams-and-sharepoint-collaboration"></a>Opções de conformidade para Microsoft 365 grupos, Teams e SharePoint colaboração

Microsoft 365 oferece um pacote completo de ferramentas para manter a conformidade à medida que seus usuários colaboram. Revise essas opções e considere como elas mapeiam para suas necessidades de negócios, a sensibilidade de seus dados e o escopo das pessoas com as qual os usuários precisam colaborar.

A tabela a seguir fornece uma referência rápida para os controles de conformidade disponíveis Microsoft 365. Outras informações são fornecidas nas seções a seguir.

|Categoria|Descrição|Referência|
|:-------|:----------|:--------|
|Retenção de informações|||
||Reter grupos de email e SharePoint conteúdo|[Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](../compliance/retention-policies-sharepoint.md)|
||Reter chat e mensagens|[Saiba mais sobre as políticas de retenção do Microsoft Teams](../compliance/retention-policies-teams.md)|
|Classificação de informações|||
||Classificar grupos e equipes|[Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Classificar automaticamente conteúdos confidenciais|[Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](../compliance/apply-sensitivity-label-automatically.md)|
||Criptografar conteúdos confidenciais|[Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](../compliance/encryption-sensitivity-labels.md)|
|Proteção de informações|||
||Impedir a perda de informações confidenciais|[Saiba mais sobre prevenção contra perda de dados](../compliance/dlp-learn-about-dlp.md)|
||Proteja informações confidenciais no chat.|[Prevenção contra perda de dados e Microsoft Teams](../compliance/dlp-microsoft-teams.md)|
||Definir as informações confidenciais da sua organização|[Tipos personalizados de informações confidenciais](../compliance/sensitive-information-type-learn-about.md)|
|Segmentação de usuário|||
||Restringir a comunicação entre segmentos de usuário|[Barreiras de informações](../compliance/information-barriers.md)|
|Residência de dados|||
||Armazenar dados em localizações geográficas específicas|[Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)|

## <a name="information-retention"></a>Retenção de informações

As políticas de retenção estão disponíveis para reter ou excluir itens usados para colaboração em grupos e equipes, incluindo arquivos, mensagens e emails. As políticas podem ser definidas para reter e excluir, para reter somente ou excluir somente. As informações cobertas por uma política de retenção são protegidas caso o grupo ou a equipe expire ou seja excluído de outra forma.

A configuração de uma política de retenção Microsoft 365 grupos abrange a caixa de correio do grupo e os arquivos SharePoint site e arquivos associados.

- [Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](../compliance/retention-policies-sharepoint.md)

As políticas de retenção para Teams retêm mensagens de chat e canal. Embora as mensagens de chat e canal sejam armazenadas Exchange caixas de correio, elas não são afetadas por políticas Exchange retenção. Você deve definir suas políticas de retenção para se aplicar Teams chats e Teams de canal. 

Os chats de usuário são mantidos indefinidamente, mesmo se uma conta de usuário for excluída. Se você não quiser manter esses dados indefinidamente, considere usar uma política de retenção para excluir chats de usuários após um tempo especificado ou incluir essa exclusão no processo de exclusão do usuário.

- [Saiba mais sobre as políticas de retenção do Microsoft Teams](../compliance/retention-policies-teams.md)

- [Políticas de retenção no Microsoft Teams](/microsoftteams/retention-policies)

Uma única política de retenção pode ser definida para aplicar-se Teams mensagens de Teams de canal. 

Recursos adicionais:

- [Saiba mais sobre políticas de retenção](../compliance/retention.md)

- [Marcas de retenção e políticas de](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) retenção no Exchange

## <a name="information-classification"></a>Classificação de informações

Você pode usar rótulos de sensibilidade para governar o acesso de convidados, a privacidade de grupo e a equipe e o acesso por dispositivos não autorizados para grupos e equipes. Ao aplicar o rótulo, essas configurações são configuradas automaticamente conforme especificado pelas configurações do rótulo.

- [Use rótulos de confidencialidade para proteger o conteúdo do Microsoft Teams, grupos do Microsoft 365 e sites do SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

Você pode configurar o Microsoft 365 para aplicar automaticamente rótulos de sensibilidade a arquivos e emails com base nos critérios especificados, incluindo a detecção de tipos de informações confidenciais ou correspondência de padrão com classificadores treináveis.

- [Aplicar um rótulo de confidencialidade automaticamente ao conteúdo](../compliance/apply-sensitivity-label-automatically.md)

Você pode usar rótulos de sensibilidade para criptografar arquivos, permitindo apenas aqueles com permissões para descriptografá-los e lê-los.

- [Restringir o acesso ao conteúdo usando rótulos de confidencialidade para aplicar criptografia](../compliance/encryption-sensitivity-labels.md)

- [Configurar uma equipe com isolamento de segurança](./secure-teams-security-isolation.md)

Recursos adicionais:

- [Saiba mais sobre rótulos de confidencialidade](../compliance/sensitivity-labels.md)


## <a name="information-protection"></a>Proteção de informações

As políticas de DLP podem impedir o compartilhamento acidental de informações confidenciais entre SharePoint, Exchange e Teams. Você pode criar políticas que especifiquem ações a tomar (como bloquear o acesso) com base em um conjunto de regras.

- [Saiba mais sobre prevenção contra perda de dados](../compliance/dlp-learn-about-dlp.md)

A DLP no Teams pode ajudar a proteger informações confidenciais Teams mensagens de chat e canal excluindo mensagens que contêm informações confidenciais.

- [Prevenção contra perda de dados e Microsoft Teams](../compliance/dlp-microsoft-teams.md)

Se você tiver informações confidenciais exclusivas da sua organização, como nomes de código do projeto, poderá criar seus próprios tipos de informações confidenciais e aplicá-los a políticas de DLP para proteger o conteúdo em grupos, equipes e Sharepoint.

- [Tipos personalizados de informações confidenciais](../compliance/sensitive-information-type-learn-about.md)

## <a name="user-segmentation"></a>Segmentação de usuário

Com barreiras de informações, você pode segmentar seus dados e usuários para restringir a comunicação e a colaboração indesejadas entre grupos e evitar conflitos de interesse em sua organização. As barreiras de informações permitem que você crie políticas para permitir ou impedir a colaboração de arquivos, conversas, chamada ou convites de reunião entre grupos de pessoas em sua organização.

- [Barreiras de informações](../compliance/information-barriers.md)

- [Barreiras de informação no Microsoft Teams](/microsoftteams/information-barriers-in-teams)

- [Usar barreiras de informações com SharePoint](/sharepoint/information-barriers)

## <a name="data-residency"></a>Residência de dados

Com Microsoft 365 multigeogeo, você pode provisionar e armazenar dados em repouso nas localizações geográficas escolhidas para atender aos requisitos de residência de dados. Em um ambiente Multi-Geo, seu locatário Microsoft 365 consiste em um local central (onde sua assinatura Microsoft 365 foi originalmente provisionada) e um ou mais locais de satélite onde você pode armazenar dados.

- [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo)

- [Plano do Microsoft 365 Multi-Geo](/microsoft-365/enterprise/plan-for-multi-geo)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Segurança e conformidade para Exchange Online](/exchange/security-and-compliance/security-and-compliance)

[Proteger informações](../compliance/information-protection.md)
