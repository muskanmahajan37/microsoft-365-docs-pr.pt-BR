---
title: Comparar grupos
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Os membros do grupo do Microsoft 365 receberão um email do grupo e um espaço de trabalho compartilhado para conversas, arquivos e eventos do calendário, como o Stream e um Planner.
ms.openlocfilehash: 3e4fa36520247179b653f799f7b2a061b9d9f4a9
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635589"
---
# <a name="compare-groups"></a>Comparar grupos

Na seção **Grupos** do centro de administração do Office 365, você pode criar e gerenciar estes quatro tipos de grupos: 

- **Grupos do Microsoft 365** (anteriormente grupos do Office 365) são usados para colaborar entre os usuários, dentro e fora da empresa.
- Os **Grupos de distribuição** são usados para enviar notificações a um grupo de pessoas.
- Os **Grupos de segurança** são usados para conceder acesso aos recursos, como o SharePoint.
- Os **Grupos de segurança habilitados** para e-mails são usados para conceder acesso a recursos como o SharePoint e enviar notificações por e-mail a esses usuários.
- As **caixas de correio compartilhadas** são usadas quando várias pessoas precisam acessar a mesma caixa de correio, como uma informação da empresa ou um endereço de email de suporte.

## <a name="microsoft-365-groups"></a>Grupos do Microsoft 365

Os grupos do Microsoft 365 são usados para colaboração entre usuários, dentro e fora da empresa. Com cada grupo do Microsoft 365, os membros obtêm um e-mail de grupo e um espaço de trabalho compartilhado para conversas, arquivos e eventos de calendário, Stream e um Planner.

Você pode adicionar pessoas de fora da sua organização a um grupo, desde que isso tenha sido [ativado pelo administrador](manage-guest-access-in-groups.md). Permita também que remetentes externos enviem email para o endereço de email do grupo.

Os grupos do Microsoft 365 podem ser [configurados para associação dinâmica no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), permitindo que os membros do grupo sejam adicionados ou removidos automaticamente com base em atributos de usuário, como departamento, local, título, etc.

Os grupos do Microsoft 365 podem ser acessados através de aplicativos móveis, como o Outlook para iOS e o Outlook para Android.

Os membros do grupo podem enviar como ou enviar em nome do endereço de email do grupo, caso tenha sido [habilitado pelo administrador](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Grupos de distribuição

Os [grupos de distribuição](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) são usados para enviar notificações a um grupo de pessoas. Eles podem receber emails externos se habilitado pelo administrador.

Os grupos de distribuição são ideais para situações em que você precisa transmitir informações a um determinado grupo de pessoas, como "Pessoas do Edifício A" ou "Todos da Contoso".

Os grupos de distribuição podem ser [atualizados para os Grupos do Microsoft 365](../manage/upgrade-distribution-lists.md).

Os grupos de distribuição podem ser adicionados a uma equipe no Microsoft Teams.

## <a name="security-groups"></a>Grupos de segurança

Os [grupos de segurança](../email/create-edit-or-delete-a-security-group.md) são usados para conceder acesso aos recursos do Microsoft 365, como o SharePoint. Você precisará administrar apenas o grupo em vez de adicionar usuários a cada recurso individualmente, facilitando a administração.

Grupos de segurança podem conter usuários e dispositivos. A criação de um grupo de segurança para dispositivos pode ser usado com serviços de gerenciamento de dispositivos móveis, como o Intune.

Os grupos de segurança podem ser [configurados para associação dinâmica no Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), permitindo que os membros do grupo ou dispositivos sejam adicionados ou removidos automaticamente com base em atributos de usuário, como departamento, local, ou título; ou atributos de dispositivo, como uma versão de sistema operacional.

Os grupos de segurança podem ser adicionados a uma equipe.

## <a name="mail-enabled-security-groups"></a>Grupos de segurança habilitados para email

Os grupos de segurança habilitados para email funcionam da mesma forma que os grupos de segurança regulares, exceto que eles não podem ser gerenciados dinamicamente pelo Azure Active Directory e nem conter dispositivos.

Eles incluem o recurso de enviar email para todos os membros do grupo.

Grupos de segurança habilitados para email podem ser adicionados a uma equipe.

## <a name="shared-mailboxes"></a>Caixas de correio compartilhadas

As [caixas de correio compartilhadas](../email/create-a-shared-mailbox.md) são usadas quando várias pessoas precisam acessar a mesma caixa de correio, como uma informação da empresa ou um endereço de email de suporte, para mesa de recepção ou qualquer outra função que possa ser compartilhada por várias pessoas.

As caixas de correio compartilhadas podem receber emails externos se o administrador tiver habilitado essa opção.

As caixas de correio compartilhadas incluem um calendário que pode ser usado para colaboração.

Os usuários com permissões para a caixa de correio do grupo podem enviar como ou enviar em nome do endereço de email da caixa de correio, se o administrador tiver dado permissões para isso. Isso é particularmente útil para caixas de correio de ajuda e suporte, pois os usuários podem enviar emails de "Suporte da Contoso" ou "Criar uma Mesa de Recepção".

Atualmente, não é possível migrar uma caixa de correio compartilhada para um grupo do Microsoft 365. Era disso que você estava precisando? Fale conosco. **[Vote aqui](https://go.microsoft.com/fwlink/?linkid=871518)**.

## <a name="related-content"></a>Conteúdo relacionado

[Saiba mais sobre os grupos do Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artigo)\
[Por que você deve atualizar suas listas de distribuição para grupos no Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (artigo)
