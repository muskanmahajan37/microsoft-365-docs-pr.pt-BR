---
title: Ajustar as configurações após o registro
description: Como excluir determinadas contas da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 760fcb94ec6d84a55fe4b8c3cb3540ae29994ae3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918437"
---
# <a name="adjust-settings-after-enrollment"></a>Ajustar as configurações após o registro

Depois de concluir o registro na Área de Trabalho Gerenciada da Microsoft, algumas configurações de gerenciamento podem precisar ser ajustadas. Para verificar e ajustar, se necessário, siga estas etapas:

1. Revise as configurações do Microsoft Intune e do Azure Active Directory descritas na próxima seção.
2. Se algum dos itens se aplicar ao seu ambiente, faça os ajustes descritos.
3. Se você quiser verificar duas vezes se todas as configurações estão corretas, você pode reprisar a ferramenta de avaliação de preparação para garantir que nada conflita com a Área de Trabalho Gerenciada da Microsoft. [](https://aka.ms/mmdart)

> [!NOTE]
> À medida que suas operações continuam nos meses seguintes, se você fizer alterações após o registro em políticas no Microsoft Intune, no Azure Active Directory ou no Microsoft 365 que afetam a Área de Trabalho Gerenciada da Microsoft, é possível que a Área de Trabalho Gerenciada da Microsoft pare de funcionar corretamente. Para evitar problemas com o serviço, verifique as configurações específicas descritas em [Corrigir](../get-ready/readiness-assessment-fix.md) problemas encontrados pela ferramenta de avaliação de preparação antes de alterar as políticas listadas lá. Você também pode reprisar a ferramenta de avaliação de preparação a qualquer momento.


## <a name="microsoft-intune-settings"></a>Configurações do Microsoft Intune

- Perfil de implantação do Piloto Automático: se você usar qualquer política do Autopilot, atualize cada uma delas para excluir o grupo Dispositivos modernos do Local de Trabalho **-All** Azure AD. Para atualizá-los, na seção Grupos excluídos em Atribuições, selecione o grupo **Dispositivos** modernos do Local de Trabalho **-Todos** os Azure AD que foi criado durante o registro da Área de Trabalho Gerenciada da Microsoft.  A Área de Trabalho Gerenciada da Microsoft também terá criado um perfil do Piloto Automático, que terá "Local de Trabalho Moderno" no nome (o Perfil de Piloto Automático do Local de **Trabalho Moderno**). Ao atualizar seus próprios perfis do  **Autopilot,** certifique-se de não excluir o grupo Dispositivos modernos do Local de Trabalho **-Todos** os Azure AD do Perfil de Piloto Automático do Local de Trabalho Moderno que foi criado pela Área de Trabalho Gerenciada da Microsoft.

- Políticas de Acesso Condicional: se você criar novas políticas de acesso condicional relacionadas ao Azure AD, Microsoft Intune ou Microsoft Defender para Ponto de Extremidade após o registro da Área de Trabalho Gerenciada da Microsoft, exclua o grupo Contas de Serviço de Local de Trabalho Modernas do **Azure** AD. Para ver as etapas, [consulte Acesso Condicional: Usuários e grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). A Área de Trabalho Gerenciada da Microsoft mantém políticas de acesso condicional separadas para restringir o acesso a essas contas. Para revisar a política de acesso condicional da Área de Trabalho Gerenciada da Microsoft ( Modern **Workplace – Secure Workstation**), vá até Microsoft Endpoint Manager e navegue até **Acesso** Condicional na Segurança do Ponto **de Extremidade**. Não modifique nenhuma política de acesso condicional do Azure AD criada pela Área de Trabalho Gerenciada da Microsoft que tenha "Local de Trabalho Moderno" no nome.

- Autenticação multifator: se você criar novos requisitos de autenticação multifator em políticas de acesso condicional relacionadas ao Azure AD, Ao Intune ou ao Microsoft Defender para Ponto de Extremidade após o registro da Área de Trabalho Gerenciada da Microsoft, exclua o grupo Contas de Serviço de Local de Trabalho **Modernas** do Azure AD. Para ver as etapas, [consulte Acesso Condicional: Usuários e grupos](/azure/active-directory/conditional-access/concept-conditional-access-users-groups). A Área de Trabalho Gerenciada da Microsoft mantém políticas de acesso condicional separadas para restringir o acesso aos membros desse grupo. Para revisar a política de acesso condicional da Área de Trabalho Gerenciada da Microsoft ( Local de Trabalho Moderno **-**), vá até Microsoft Endpoint Manager e navegue até **Acesso** Condicional em Segurança do Ponto **de Extremidade**. 

- Anel de atualização do Windows 10: para todas as políticas de toque de atualização do Windows 10 criadas, exclua o grupo Dispositivos Modernos do Local de Trabalho **-** Todos os Azure AD de cada política. Para ver etapas, consulte [Create and assign update rings](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings). A Área de Trabalho Gerenciada da Microsoft também terá criado algumas políticas de anel de atualização, todas com "Local de Trabalho Moderno" no nome (por exemplo, Política de Atualização do Local de Trabalho Moderno **[Ampla]**, Política de Atualização do Local de Trabalho **Moderno [Rápido]**, Política de Atualização do Local de Trabalho **Moderno [Primeiro]** e Política de Atualização do Local de Trabalho **Moderno [Teste]**). Ao atualizar suas próprias políticas,  certifique-se de não excluir o grupo Dispositivos Modernos do Local de Trabalho **-** Todos os Azure AD daqueles criados pela Área de Trabalho Gerenciada da Microsoft.


## <a name="azure-active-directory-settings"></a>Configurações do Azure Active Directory

Redefinição de senha de autoatendido: se você usar a redefinição de senha de autoatendida para todos os usuários, ajuste a atribuição para excluir contas de serviço da Área de Trabalho Gerenciada da Microsoft. Para ajustar essa atribuição, crie um grupo dinâmico do Azure AD para todos os usuários, exceto contas de serviço da *Área* de Trabalho Gerenciada da Microsoft, e use esse grupo para atribuição em vez de "todos os usuários".

Para ajudá-lo a encontrar e excluir as contas de serviço, veja um exemplo de uma consulta dinâmica que você pode usar:

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

Nesta consulta, substitua @TENANT nome de domínio do locatário.



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar com a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. Ajustar configurações após o registro (este artigo)
3. [Atribuir licenças](assign-licenses.md)
4. [Implantar o Portal da Empresa do Intune](company-portal.md)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)