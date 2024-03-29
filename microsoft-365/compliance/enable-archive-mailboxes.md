---
title: Ative as caixas de correio de arquivo morto no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom: seo-marvel-apr2020
description: Aprenda a usar o centro de conformidade para habilitar o arquivamento de caixas de correio para dar suporte aos requisitos de retenção de mensagens, descoberta eletrônica e retenção de sua organização.
ms.openlocfilehash: 2bc80d347d1324a317cc2cc2712d475781adc492
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926511"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>Habilitar o arquivamento de caixas de correio no centro de conformidade

O arquivamento no Microsoft 365 (também chamado de *Arquivamento no Local*) fornece aos usuários espaço adicional de armazenamento na caixa de correio. Depois de ativar as caixas de correio de arquivo morto, os usuários podem acessar e armazenar mensagens em suas caixas de correio de arquivo morto usando o Microsoft Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App). Os usuários também podem mover ou copiar mensagens entre sua caixa de correio principal e sua caixa de correio de arquivo morto. Eles também podem recuperar itens excluídos da pasta Itens Recuperáveis em suas caixas de correio de arquivo morto usando a ferramenta Recuperar Itens Excluídos.

> [!NOTE]
> O recurso de arquivamento de expansão automática no Microsoft 365 fornece armazenamento adicional em caixas de correio de arquivamento. Quando o arquivamento de expansão automática está ativado e a cota de armazenamento inicial na caixa de correio de arquivamento de um usuário é atingida, o Microsoft 365 adiciona automaticamente mais espaço de armazenamento. Isso significa que os usuários não ficarão sem espaço de armazenamento na caixa de correio, e você não precisará gerenciar nada depois de habilitar inicialmente a caixa de correio de arquivo morto e ativar o arquivamento de expansão automática para sua organização. Confira mais informações em [Visão geral do arquivamento ilimitado](unlimited-archiving.md).

## <a name="get-the-necessary-permissions"></a>Obtenha as permissões necessárias

Você precisa ter atribuída a função de Destinatários de Email no Exchange Online para habilitar ou desabilitar caixas de correio de arquivo morto. Por padrão, essa função é atribuída aos grupos de funções de Gerenciamento de Destinatários e Gerenciamento de Organização na página **Permissões** no centro de administração do Exchange. Se você não vir a página **Arquivo** na seção Centro de Conformidade e Segurança, peça ao administrador para atribuir as permissões necessárias.

## <a name="enable-an-archive-mailbox"></a>Habilitar uma caixa de correio de arquivo morto

1. Vá para <https://protection.office.com>.

2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo do Centro de Conformidade e Segurança, clique em **Governança de informações** \> **Arquivo**.

   A página **Arquivo** é exibida. A coluna **Caixa de correio de arquivo morto** indica se uma caixa de correio de arquivo morto está habilitada ou desabilitada para cada usuário.

   > [!NOTE]
   > A página **Arquivo** mostra um máximo de 500 usuários.

4. Na lista de caixas de correio, selecione o usuário para o qual você deseja habilitar a caixa de correio de arquivo morto.

   ![Clique em Habilitar, no painel de detalhes do usuário selecionado, para habilitar a caixa de correio de arquivo morto.](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. No painel de detalhes do usuário selecionado, clique em **Habilitar**.

   Um aviso é exibido informando que, se você habilitar a caixa de correio de arquivo morto, os itens na caixa de correio do usuário que forem mais antigos do que a política de arquivamento atribuída à caixa de correio serão movidos para a nova caixa de correio de arquivo morto. A política de arquivamento padrão que faz parte da política de retenção atribuída a caixas de correio do Exchange Online move itens para a caixa de correio de arquivo morto dois anos após a data em que o item foi entregue à caixa de correio ou criado pelo usuário. Para obter mais informações, confira a seção **Mais informações** deste artigo.

6. Clique em **Sim** para habilitar a caixa de correio de arquivo morto.

   A criação da caixa de correio de arquivo morto pode demorar alguns instantes. Quando criada, **Caixa de correio de arquivo morto: habilitada** é exibido no painel de detalhes do usuário selecionado. Talvez seja necessário clicar em **Atualizar** ![Ícone Atualizar](../media/O365-MDM-Policy-RefreshIcon.gif) para atualizar as informações no painel de detalhes.

> [!TIP]
> Você também pode habilitar caixas de correio de arquivo morto selecionando vários usuários com caixas de correio de arquivo morto desabilitadas (use as teclas Shift ou Ctrl). Depois de selecionar várias caixas de correio, clique em **Habilitar** no painel de detalhes.

## <a name="disable-an-archive-mailbox"></a>Desabilitar uma caixa de correio de arquivo morto

Você também pode usar a página **Arquivo** no Centro de Segurança e Conformidade para desabilitar a caixa de correio de arquivo morto do usuário. Após desabilitar uma caixa de correio de arquivo morto, você pode reconectá-la à caixa de correio principal do usuário dentro de 30 dias após desativá-la. Neste caso, o conteúdo original da caixa de correio de arquivo morto é restaurado. Após 30 dias, o conteúdo da caixa de correio de arquivo original é excluído permanentemente e não pode ser recuperado. Portanto, se você reativar o arquivo morto mais de 30 dias após desabilitá-lo, será criada uma nova caixa de correio de arquivo morto.

A política de arquivamento padrão atribuída às caixas de correio dos usuários move itens para a caixa de correio de arquivamento dois anos após a data em que o item é entregue. Se você desabilitar a caixa de correio de arquivo morto do usuário, nenhuma ação será executada nos itens da caixa de correio e eles permanecerão na caixa de correio principal do usuário.

Para desabilitar uma caixa de correio de arquivo morto:

1. Vá para <https://protection.office.com>.

2. Entre usando sua conta de trabalho ou da escola.

3. No painel esquerdo do Centro de Conformidade e Segurança, clique em **Governança de informações** \> **Arquivo**.

   A página **Arquivo** é exibida. A coluna **Caixa de correio de arquivo morto** indica se uma caixa de correio de arquivo morto está habilitada ou desabilitada para cada usuário.

   > [!NOTE]
   > A página **Arquivo** mostra um máximo de 500 usuários.

4. Na lista de caixas de correio, selecione o usuário para o qual você deseja habilitar a caixa de correio arquivo morto.

5. No painel de detalhes, clique em **Desabilitar**.

   Uma mensagem de aviso é exibida dizendo que você terá 30 dias para reabilitar a caixa de correio de arquivo morto e que, após 30 dias, todas as informações do arquivo serão excluídas permanentemente.

6. Clique em **Sim** para desabilitar a caixa de correio de arquivo morto.

   Pode levar alguns instantes para desabilitar a caixa de correio de arquivo morto. Quando desabilitada, é exibido **Caixa de correio de arquivo morto: desabilitada** no painel de detalhes do usuário selecionado. Talvez seja necessário clicar em **Atualizar** ![Ícone Atualizar](../media/O365-MDM-Policy-RefreshIcon.gif) para atualizar as informações no painel de detalhes.

> [!TIP]
> Você também pode desabilitar em massa as caixas de correio de arquivo morto selecionando vários usuários com caixas de correio de arquivo morto habilitadas (use as teclas Shift ou Ctrl). Depois de selecionar várias caixas de correio, clique em **Desabilitar** no painel de detalhes.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Use o PowerShell do Exchange Online para habilitar ou desabilitar caixas de correio de arquivo morto

Você também pode usar o PowerShell do Exchange Online para habilitar caixas de correio de arquivo morto. O principal motivo para usar o PowerShell é que você pode habilitar rapidamente a caixa de correio de arquivo morto para todos os usuários da sua organização.

A primeira etapa é se conectar ao PowerShell do Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Depois de se conectar ao Exchange Online, você pode executar os comandos nas seções a seguir para habilitar ou desabilitar as caixas de correio de arquivo morto.

### <a name="enable-archive-mailboxes"></a>Habilitar caixas de correio de arquivo morto

Execute o seguinte comando para habilitar a caixa de correio de arquivo morto para um único usuário.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

Execute o seguinte comando para habilitar a caixa de correio de arquivo morto para todos os usuários da organização (cujas caixas de correio de arquivo morto não estejam atualmente habilitadas).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>Desabilitar caixas de correio de arquivo morto

Execute o seguinte comando para desabilitar a caixa de correio de arquivo morto para um único usuário.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

Execute o seguinte comando para desabilitar a caixa de correio de arquivo morto para todos os usuários em sua organização (cujas caixas de correio de arquivo morto estejam atualmente habilitadas).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a>Mais informações

- Quando uma caixa de correio de arquivo morto está habilitada, os usuários podem armazenar mensagens em sua caixa de correio de arquivo morto. Os usuários podem acessar suas caixas de correio de arquivo morto usando o Microsoft Outlook e o Outlook na Web. Usando qualquer um desses aplicativos de cliente, os usuários podem exibir mensagens em sua caixa de correio de arquivo morto e mover ou copiar mensagens entre a caixa de correio principal e a caixa de correio de arquivo morto. Os usuários também podem recuperar itens excluídos da pasta Itens Recuperáveis em suas caixas de correio de arquivo morto usando a ferramenta Recuperar Itens Excluídos.

  Para obter uma lista de licenças do Outlook que tenham suporte ao arquivamento in-loco, consulte [Requisitos de licença do Outlook para recursos do Exchange](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99).

- As caixas de correio de arquivo morto ajudam você e seus usuários a atenderem aos requisitos de retenção, descoberta eletrônica e bloqueio da sua organização. Por exemplo, você pode usar a política de retenção do Exchange da sua organização para mover conteúdo de caixa de correio para a caixa de correio de arquivo morto dos usuários. Quando você usa a ferramenta de Pesquisa de Conteúdo no Centro de Conformidade e Segurança para pesquisar por conteúdo específico em uma caixa de correio de usuário, a caixa de correio de arquivo morto do usuário também será pesquisada. Além disso, quando você configura uma Retenção de Litígio ou aplica uma política de retenção a uma caixa de correio de usuário, os itens na caixa de correio de arquivo morto também são retidos.

- Depois que as caixas de correio de arquivo morto estiverem habilitadas, sua organização poderá aproveitar a política de retenção padrão do Exchange (também chamada de Gerenciamento de Registros de Mensagens ou política de MRM) que é atribuída automaticamente a todas as caixas de correio. Quando uma caixa de correio de arquivo morto está habilitada, a política de retenção padrão do Exchange faz o seguinte:

  - Move os itens que têm dois anos ou mais da caixa de correio principal do usuário para suas caixas de correio de arquivo morto.

  - Move os itens que têm 14 dias ou mais da pasta Itens Recuperáveis na caixa de correio principal do usuário para a pasta Itens Recuperáveis nas caixas de correio de arquivo morto.

- Para obter mais informações sobre caixas de correio de arquivo morto e políticas de retenção do Exchange, consulte:

  - [Marcas e políticas de retenção no Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [Política de Retenção Padrão no Exchange Online ](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização](set-up-an-archive-and-deletion-policy-for-mailboxes.md)