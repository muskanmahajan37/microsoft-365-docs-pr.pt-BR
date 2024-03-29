---
title: Usar um código QR para entrar no Outlook móveis
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Saiba como usar um código QR para autenticar e baixar Outlook celular.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635993"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar um código QR para entrar no Outlook móveis

> [!IMPORTANT]
> Esse recurso só está disponível para organizações que tenham a versão direcionada no Microsoft 365 de administração. Para ativar a versão direcionada e saber mais sobre como ela funciona, consulte Configurar as opções de versão [Padrão ou Direcionada.](release-options-in-office-365.md) Vamos expandir para mais organizações nas próximas semanas por meio da visualização pública. A visualização pública fornece acesso antecipado Microsoft 365 recursos.

Como administrador Microsoft 365, você pode permitir que seus usuários entrem no Outlook para Android ou aplicativo iOS em seus dispositivos móveis sem precisar inserir seu nome de usuário e senha. Ao digitalizar um código QR, os usuários podem autenticar e entrar com segurança Outlook celular.

Em Outlook na Web ou em outros aplicativos Outlook desktop, os usuários podem ver notificações informando que podem usar Outlook em seu dispositivo móvel. Essas notificações podem ser gerenciadas pelo administrador usando Exchange Powershell. Se os usuários optarem por enviar uma mensagem SMS texto para baixar o aplicativo em seu dispositivo móvel, um código QR aparecerá em seu computador. Eles poderão examinar o código QR para fazer logoff Outlook telefone ou tablet. Esse código QR é um token de vida curta que só pode ser resgatado uma vez.

> [!NOTE]
> Em alguns casos, os usuários devem se autenticar no computador para gerar o código QR.

## <a name="use-exchange-powershell"></a>Usar Exchange PowerShell

Esse recurso não está habilitado por padrão. Para desabilitar esse recurso, siga as etapas abaixo.

1. [Conexão para Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Usando o PowerShell, você pode desabilitar as notificações informando aos usuários sobre os aplicativos Outlook móveis. Isso também impede que o fluxo de login do código QR seja mostrado.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Conteúdo relacionado

[Configurar as opções de versão Padrão](release-options-in-office-365.md) ou Direcionada (artigo)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (artigo)