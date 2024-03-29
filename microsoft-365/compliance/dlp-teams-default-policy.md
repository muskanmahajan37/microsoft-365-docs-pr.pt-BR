---
title: Saiba mais sobre a política padrão de prevenção contra perda de dados no Microsoft Teams (visualização)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Saiba mais sobre a política de prevenção de perda de dados padrão Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114139"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Saiba mais sobre a política padrão de prevenção contra perda de dados no Microsoft Teams (visualização)

[Os recursos de prevenção](dlp-learn-about-dlp.md) contra perda de dados foram estendidos para incluir Microsoft Teams de chat e de canal, incluindo mensagens de canal privado. Como parte dessa versão, criamos uma política DLP padrão para clientes de primeira para o Centro de Conformidade.

## <a name="applies-to"></a>Aplicável a

Qualquer locatário licenciado com uma ou mais das licenças abaixo e que tenha usuários Teams ativos
 
- ME5, 
- MA5, 
- Conformidade com e5/A5, 
- IP+G, 
- OE5, 
- Conformidade avançada do O365 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>O que a política padrão faz?

A política DLP padrão rastreia todos os números de cartão de crédito compartilhados interna e externamente para a organização. Essa política está em uso por padrão para todos os usuários do locatário. Ele não gera dicas de política para usuários finais, mas gera um evento Alert e também dispara um email de baixa gravidade para o administrador (adicionado na política). O administrador pode exibir as atividades e editar os detalhes das políticas fazendo logo em log no Centro de Conformidade.

Os administradores podem exibir essa política na página Centro de [Conformidade >](https://compliance.microsoft.com/compliancesettings) políticas de prevenção contra perda de dados.


> [!div class="mx-imgBorder"]
> ![política Teams DLP padrão](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Editar ou excluir a política padrão

Para editar a política padrão para melhorar o desempenho ou [excluí-la,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)basta usar uma conta com permissões de Gerenciamento de Conformidade de **DLP.** Para obter mais informações, consulte [Permissões](create-test-tune-dlp-policy.md#permissions).

