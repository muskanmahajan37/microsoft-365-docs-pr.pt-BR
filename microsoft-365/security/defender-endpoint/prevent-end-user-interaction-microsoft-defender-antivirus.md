---
title: Ocultar a interface do Microsoft Defender Antivírus
description: Você pode ocultar o tile de proteção contra vírus e ameaças no aplicativo Segurança do Windows.
keywords: bloqueio da interface do usuário, modo sem cabeça, ocultar aplicativo, ocultar configurações, ocultar interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274911"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedir que os usuários vejam ou interajam com a interface do usuário do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar a Política de Grupo para impedir que os usuários nos pontos de extremidade possam ver a interface do Microsoft Defender Antivírus. Você também pode impedi-los de pausar verificações.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ocultar a interface do Microsoft Defender Antivírus

No Windows 10, versões 1703, ocultar a interface ocultará as notificações do Microsoft Defender Antivírus e impedirá que o & proteção contra vírus apareça no aplicativo segurança do Windows.

Com a configuração definida como **Habilitado:**

![Captura de tela do Windows Security sem o ícone de escudo e a seção proteção contra vírus e ameaças](images/defender/wdav-headless-mode-1703.png)

Com a configuração definida como **Desabilitada** ou não configurada:

![Captura de tela do Windows Security mostrando o ícone de escudo e a seção proteção contra vírus e ameaças](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
>Ocultar a interface também impedirá que as notificações do Microsoft Defender Antivírus apareçam no ponto de extremidade. As notificações do Microsoft Defender para Ponto de Extremidade ainda serão exibidas. Você também pode configurar individualmente [as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)

Em versões anteriores do Windows 10, a configuração ocultará a interface Windows Defender cliente. Se o usuário tentar abri-lo, ele receberá um aviso informando: "O administrador do sistema tem acesso restrito a esse aplicativo".

![Mensagem de aviso quando o modo sem cabeça está habilitado no Windows 10, versões anteriores a 1703](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Usar a Política de Grupo para ocultar a interface do Microsoft Defender AV dos usuários

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.**

5. Clique duas vezes na **configuração Habilitar modo de interface** do usuário sem cabeça e de definir a opção **como Habilitado**. Clique em **OK**. 

Consulte [Impedir que os usuários modifiquem localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) as configurações de política para obter mais opções sobre como impedir que os usuários formem modificar a proteção em seus PCs.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedir que os usuários pausem uma verificação

Você pode impedir que os usuários pausem verificações, o que pode ser útil para garantir que as verificações agendadas ou sob demanda não sejam interrompidas pelos usuários.

> [!NOTE]
> Essa configuração não é suportada no Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Usar a Política de Grupo para impedir que os usuários pausem uma verificação

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Scan**.

5. Clique duas vezes na **configuração Permitir que os usuários pausem a verificação** e de definir a opção como **Desabilitada**. Clique em **OK**. 

## <a name="related-articles"></a>Artigos relacionados

- [Configurar as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)

- [Configurar a interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)