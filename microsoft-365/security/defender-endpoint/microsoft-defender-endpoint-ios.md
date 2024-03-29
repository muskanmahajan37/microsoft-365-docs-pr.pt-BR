---
title: Microsoft Defender para Ponto de Extremidade para iOS
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender para Ponto de Extremidade no iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246411"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>Microsoft Defender para Ponto de Extremidade para iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**O Microsoft Defender para Ponto de Extremidade** no iOS oferecerá proteção contra phishing e conexões de rede não seguras de sites, emails e aplicativos. Todos os alertas estarão disponíveis por meio de um único painel de vidro no Central de Segurança do Microsoft Defender. O portal fornece às equipes de segurança uma exibição centralizada de ameaças em dispositivos iOS juntamente com outras plataformas.

> [!CAUTION]
> A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint no iOS provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.

## <a name="pre-requisites"></a>Pré-requisitos

**Para usuários finais**

- Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo. Consulte [Requisitos de licenciamento do Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

- Os dispositivos são [inscritos por](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune. Isso exige que o usuário final seja atribuído a uma Microsoft Intune de usuário.
    - Portal da Empresa do Intune aplicativo pode ser baixado na [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).
    - Observe que a Apple não permite que os usuários de redirecionamento baixem outros aplicativos da loja de aplicativos e, portanto, essa etapa precisa ser feita pelo usuário antes de entrar no aplicativo Microsoft Defender para Ponto de Extremidade.

- Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).

**Para administradores**

- Acesso ao portal Central de Segurança do Microsoft Defender.

    > [!NOTE]
    > Microsoft Intune é a única solução MDM (Gerenciamento de Dispositivo Móvel) com suporte para a implantação do Microsoft Defender para Ponto de Extremidade no iOS. Atualmente, apenas dispositivos inscritos têm suporte para impor o Defender para o Ponto de Extremidade em políticas de conformidade de dispositivos relacionados ao iOS no Intune.

- Acesso ao [Microsoft Endpoint Manager de](https://go.microsoft.com/fwlink/?linkid=2109431)administração , para implantar o aplicativo em grupos de usuários inscritos em sua organização.

**Requisitos de rede**
- Para o Microsoft Defender for Endpoint no iOS funcionar quando conectado a uma rede, o firewall/proxy precisará ser configurado para habilitar o acesso ao Microsoft Defender para [URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) de serviço de ponto de extremidade

**Requisitos do sistema**

- Dispositivos iOS que executam o iOS 11.0 ou superior. iPad dispositivos são oficialmente compatíveis com a versão 1.1.15010101 em diante.

- O dispositivo está inscrito no aplicativo [Portal da Empresa do Intune .](https://apps.apple.com/us/app/intune-company-portal/id719171358)

> [!NOTE]
> **Microsoft Defender ATP (Microsoft Defender para Ponto de Extremidade) no iOS agora está disponível na [Apple App Store](https://aka.ms/mdatpiosappstore).**

## <a name="installation-instructions"></a>Instruções de instalação

A implantação do Microsoft Defender para Ponto de Extremidade no iOS é via Microsoft Intune (MDM) e há suporte para dispositivos supervisionados e não supervisionados.
Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).

## <a name="resources"></a>Recursos

- Mantenha-se informado sobre as próximas versões visitando Novidades do Microsoft Defender para Ponto de Extremidade [no iOS](ios-whatsnew.md) ou em nosso [blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)

- Fornecer comentários por meio do sistema de comentários no aplicativo ou por meio do [portal SecOps](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>Próximas etapas

- [Implantar o Microsoft Defender para Ponto de Extremidade no iOS](ios-install.md)
- [Configurar o Microsoft Defender para Ponto de Extremidade em recursos do iOS](ios-configure-features.md)
