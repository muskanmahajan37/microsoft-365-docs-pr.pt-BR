---
title: Acessar as APIs do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Saiba como você pode usar APIs para automatizar fluxos de trabalho e inovar com base nos recursos do Microsoft Defender para o Ponto de Extremidade
keywords: apis, api, wdatp, api aberta, microsoft defender para api de ponto de extremidade, microsoft defender atp, api pública, apis com suporte, alertas, dispositivo, usuário, domínio, ip, arquivo, busca avançada, consulta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571824"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Acessar as APIs do Microsoft Defender para Ponto de Extremidade 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Aplica-se a:** 
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



O Defender for Endpoint expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs permitirão que você automatize fluxos de trabalho e inove com base nos recursos do Defender para Ponto de Extremidade. O acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Assista a este vídeo para uma visão geral rápida do Defender para APIs do Ponto de Extremidade. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Em geral, você precisará seguir as seguintes etapas para usar as APIs:
- Criar um [aplicativo AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API do Defender para Ponto de Extremidade


Você pode acessar a API do Defender para Ponto de Extremidade com **Contexto de Aplicativo** ou Contexto do **Usuário.**

- **Contexto do aplicativo: (Recomendado)** <br>
    Usado por aplicativos que são executados sem um usuário assinado presente. por exemplo, aplicativos que são executados como serviços em segundo plano ou daemons.

    Etapas que precisam ser tomadas para acessar a API do Defender for Endpoint com contexto de aplicativo:

  1. Crie um Aplicativo Web do AAD.
  2. Atribua a permissão desejada ao aplicativo, por exemplo, 'Alertas de leitura', 'Isolar Máquinas'. 
  3. Crie uma chave para este Aplicativo.
  4. Obter token usando o aplicativo com sua chave.
  5. Usar o token para acessar a API do Microsoft Defender para Ponto de Extremidade

     Para obter mais informações, consulte [Obter acesso com o contexto do aplicativo](exposed-apis-create-app-webapp.md).


- **Contexto do usuário:** <br>
    Usado para executar ações na API em nome de um usuário.

    Etapas a serem tomadas para acessar a API do Defender para Ponto de Extremidade com contexto de aplicativo:

  1. Criar aplicativo nativo do AAD.
  2. Atribua a permissão desejada ao aplicativo, por exemplo, "Alertas de leitura", "Isolar Máquinas" etc. 
  3. Obter token usando o aplicativo com credenciais de usuário.
  4. Usar o token para acessar a API do Microsoft Defender para Ponto de Extremidade

     Para obter mais informações, consulte [Obter acesso com o contexto do usuário](exposed-apis-create-app-nativeapp.md).


## <a name="related-topics"></a>Tópicos relacionados
- [APIs do Microsoft Defender para Ponto de Extremidade](exposed-apis-list.md)
- [Acessar o Microsoft Defender para Ponto de Extremidade com contexto de aplicativo](exposed-apis-create-app-webapp.md)
- [Acessar o Microsoft Defender para Ponto de Extremidade com contexto de usuário](exposed-apis-create-app-nativeapp.md)
