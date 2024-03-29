---
title: Usar o Microsoft Defender para Office 365 juntamente com o Microsoft Defender para Ponto de Extremidade
f1.keywords:
- NOCSH
keywords: integre, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft Defender para Office 365 juntamente com o Microsoft Defender para Endpoint para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6ad81102a9702a725f40fcdb5421a2b19b0086d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934028"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar o Microsoft Defender para Office 365 juntamente com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[O Microsoft Defender para Office 365](defender-for-office-365.md) pode ser configurado para trabalhar com o [Microsoft Defender para o Ponto de Extremidade.](/windows/security/threat-protection)

A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco. Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos que são potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para Endpoint.

A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:

![Quando o Microsoft Defender for Endpoint está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta. Clicar no link de um dispositivo abre sua página no Centro de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Saiba mais sobre o Centro de Segurança](/windows/security/threat-protection/microsoft-defender-atp/use)** do Microsoft Defender (também conhecido como o portal do Microsoft Defender para Ponto de Extremidade).)

## <a name="requirements"></a>Requisitos

- Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para Ponto de Extremidade.

- Você deve ser um administrador global ou ter uma função de administrador de segurança (como Administrador de Segurança) atribuída no Centro de Conformidade & [Segurança.](https://protection.office.com) (Consulte Permissões no Centro de [Conformidade & Segurança](permissions-in-the-security-and-compliance-center.md))

- Você deve ter acesso ao [Explorer (ou](threat-explorer.md) detecções em tempo real) no Centro de Conformidade & Segurança e no Centro de Segurança do Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Endpoint

A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint é configurada usando o Centro de Conformidade e Segurança & Segurança e o Centro de Segurança do Microsoft Defender.

1. Como administrador global ou administrador de segurança, acesse <https://protection.office.com> e entre. (Isso o leva ao Centro de Conformidade e Segurança & do Office 365.)

2. No painel de navegação, escolha **Explorador de gerenciamento de** \> **ameaças.**

   ![Menu Explorer in Threat Management](../../media/ThreatMgmt-Explorer-nav.png)

3. No canto superior direito da tela, escolha Defender para Configurações do Ponto de Extremidade **(Configurações do MDE)**.

4. Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a ligue Conectar-se ao **Microsoft Defender para Ponto de Extremidade**.

   ![Conexão do Microsoft Defender para Ponto de Extremidade](../../media/Explorer-WDATPConnection-dialog.png)

5. Vá para o Centro de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).

6. Na barra de navegação, escolha **Configurações**. Em **Geral,** escolha **Recursos avançados.**

7. Role para baixo até a conexão de Inteligência de Ameaças do **Office 365** e a ligue.

   ![Conexão de inteligência contra ameaças do Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artigos relacionados

[Recursos de investigação e resposta contra ameaças no Office 365](office-365-ti.md)

[Obter o Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection)