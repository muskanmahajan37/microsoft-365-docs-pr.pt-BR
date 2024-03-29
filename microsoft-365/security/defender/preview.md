---
title: Recursos de visualização no Microsoft 365 Defender
description: Saiba mais sobre os novos recursos de segurança do Microsoft 365
keywords: prévia, novo, segurança do m365, segurança, 365, recursos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c82e1abf9e539ad169bbc488ade9cd21bb8e6727
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029069"
---
# <a name="microsoft-365-defender-preview-features"></a>Recursos de visualização do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> As versões de visualização são fornecidas sem um contrato de nível de serviço e não são recomendadas para cargas de trabalho de produção. Determinados recursos podem não ser suportados ou podem ter recursos restritos.

**Aplica-se a:**
- Microsoft 365 Defender

O serviço do Microsoft 365 Defender está constantemente sendo atualizado para incluir novos aprimoramentos e recursos de recursos.

Saiba mais sobre os novos recursos na versão de visualização do Microsoft 365 Defender e entre os primeiros a experimentar os recursos futuros, a partir da experiência de visualização.

Para obter mais informações sobre novos recursos que geralmente estão disponíveis, consulte [Novidades no Microsoft 365 Defender](whats-new.md).

## <a name="required-permissions"></a>Permissões obrigatórias

As contas atribuídas às seguintes funções do Azure Active Directory (Azure AD) podem ativar os recursos do Microsoft 365 Defender Preview:

- Administrador global
- Administrador de segurança
- Operador de segurança

## <a name="turn-on-preview-features"></a>Habilitar recursos de prévia

Você terá acesso aos recursos futuros que você pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos geralmente estão disponíveis.

Ative a configuração de experiência de visualização para ser uma das primeiras pessoas a experimentar os recursos futuros.

1. No painel de navegação, selecione **Configurações**.
2. Selecione **Microsoft 365 Defender**.
3. Selecione **Prévia dos recursos** > **Ativar prévia dos recursos**. 
4. Selecione **Salvar**.

Você saberá que tem prévia dos recursos ativados quando vir que a caixa de seleção **Ativar prévia dos recursos** está marcada. 

## <a name="preview-features"></a>Recursos em versão prévia

Os recursos e aprimoramentos a seguir estão disponíveis em prévia:

- **[APIs do Microsoft 365 Defender](api-overview.md)** - As APIs de nível superior do Microsoft 365 Defender permitirão automatizar fluxos de trabalho com base no incidente compartilhado e em tabelas avançadas de busca. 
- **[Tomar medidas na busca avançada](advanced-hunting-take-action.md)**— contenha rapidamente ameaças ou endereços de ativos comprometidos que você encontra na busca [avançada.](advanced-hunting-overview.md)
- **[Referência de esquema no portal](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**— Obter informações sobre tabelas avançadas de esquema de busca diretamente no centro de segurança. Além das descrições de tabela e coluna, essa referência inclui tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo.
- **[Função DeviceFromIP() —](advanced-hunting-devicefromip-function.md)** Obter informações sobre quais dispositivos receberam um endereço IP específico ou endereços em um determinado intervalo de tempo.
