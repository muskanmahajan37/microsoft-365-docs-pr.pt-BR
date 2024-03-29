---
title: Conceder aos usuários acesso ao Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam ter permissões atribuídas no Centro de Conformidade e Segurança do Microsoft 36 & 5 antes de gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd36ac0dec20851a423acd58e5ad7d38cb65d93
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599918"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Conceder aos usuários acesso ao Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os usuários precisam ter permissões atribuídas no Centro de Conformidade & segurança antes que possam gerenciar qualquer um de seus recursos de segurança ou conformidade. Como administrador global ou membro do grupo de função OrganizationManagement no Centro de Conformidade & Segurança, você pode dar essas permissões aos usuários. Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.

Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no Centro de Conformidade & Segurança, confira Permissões no Centro de Conformidade & [Segurança.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ser um administrador global ou membro do grupo de função OrganizationManage & ment no Centro de Conformidade e Segurança, para concluir as etapas deste artigo.

- Os grupos de função do Centro de Conformidade e Segurança & podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.

- As associações do grupo de funções não são compartilhadas entre o Exchange Online e o Centro de Conformidade & Segurança.

- Parceiros de Permissão de Acesso Delegado (DAP) com permissões Administer On Behalf Of (AOBO) não podem acessar o Centro de Conformidade & Segurança.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Use o Centro de Conformidade & segurança para dar a outro usuário acesso ao Centro de Conformidade & Segurança

1. Abra o Centro de Conformidade & segurança em <https://protection.office.com> e vá para **Permissões**. Para ir diretamente para a guia **Permissões,** abra <https://protection.office.com/permissions> .

2. Na lista de grupos de funções, escolha o grupo de funções e clique em **Editar** ![ ícone editar ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Na página propriedades do grupo de função em **Membros,** clique em Adicionar Ícone e selecione o nome do usuário ![ ](../../media/ITPro-EAC-AddIcon.gif) (ou usuários) que deseja adicionar.

4. Quando você selecionou todos os usuários que deseja adicionar ao grupo de funções, clique em **adicionar \> e** em **OK.**

5. Quando concluir, clique em **Salvar**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Use o & de Conformidade do PowerShell para dar a outro usuário acesso ao Centro de Conformidade & Segurança

1. [Conectar ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Use a seguinte sintaxe:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Para problemas detalhados de sintaxe e parâmetro, consulte [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você concedeu acesso com êxito ao Centro de Conformidade & Segurança, faça uma das seguintes etapas:

- No Centro de Conformidade & segurança, acesse **Permissões** e selecione o grupo de funções. No sobremenu de detalhes que será aberto, verifique os membros do grupo de funções.

- No Centro de Conformidade & segurança do PowerShell, substitua pelo nome do grupo de funções \<RoleGroupName\> e execute o seguinte comando:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).