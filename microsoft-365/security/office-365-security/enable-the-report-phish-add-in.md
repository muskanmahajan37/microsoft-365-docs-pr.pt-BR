---
title: Habilitar o complemento De relatório phishing
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Saiba como habilitar o complemento Relatar Phishing para Outlook e Outlook na Web, para usuários individuais ou toda a sua organização.
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625384"
---
# <a name="enable-the-report-phishing-add-in"></a>Habilite o suplemento Relatório de Phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se você for um administrador em uma organização Microsoft 365 com caixas de correio Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança. Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Os complementos De Relatório de Mensagens e Phishing para Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App) permitem que as pessoas reportem facilmente falsos positivos (bons emails marcados como ruins) ou falsos negativos (email ruim permitido) para a Microsoft e suas afiliadas para análise.

A Microsoft usa esses envios para melhorar a eficácia das tecnologias de proteção de email. Por exemplo, suponha que as pessoas estão relatando muitas mensagens usando o add-in De Phishing de relatório. Essas informações são publicadas no [Painel de Segurança](security-dashboard.md) e em outros relatórios. A equipe de segurança da sua organização pode usar essas informações como uma indicação de que as políticas anti-phishing podem precisar ser atualizadas.

Você pode instalar o add-in Report Message ou Report Phishing. Se você quiser que seus usuários reportem mensagens de spam e phishing, implante o complemento Mensagem de Relatório em sua organização. Para obter mais informações, consulte [Enable the Report Message add-in](enable-the-report-message-add-in.md).

O add-in Relatório phishing fornece a opção de relatar apenas mensagens de phishing. Os administradores podem habilitar o complemento Relatar Phishing para a organização, e usuários individuais podem instalá-lo por conta própria.

Se você for um usuário individual, poderá habilitar o [complemento Relatar Phishing para si mesmo.](#get-the-report-phishing-add-in-for-yourself)

Se você for um administrador global ou um administrador de Exchange Online, e Exchange estiver configurado para usar a autenticação OAuth, você poderá habilitar o complemento [Relatório de Phishing](#get-and-enable-the-report-phishing-add-in-for-your-organization)para sua organização. O relatório de phishing Add-In agora está disponível por meio da [Implantação Centralizada.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- O complemento De Relatório de Phishing funciona com a maioria Microsoft 365 assinaturas e os seguintes produtos:

  - Outlook na Web
  - Outlook 2013 SP1 ou posterior
  - Outlook 2016 para Mac ou posterior
  - Outlook incluído com Microsoft 365 aplicativos para Enterprise
  - Outlook aplicativo para iOS e Android

- O complemento Phishing de Relatório não está disponível para caixas de correio compartilhadas ou caixas de correio em organizações Exchange locais.

- Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).

- O navegador da Web existente deve trabalhar com o complemento Relatar Phishing. Mas, se você observar que o complemento não está disponível ou não está funcionando conforme o esperado, tente um navegador diferente.

- Para as instalações organizacionais, a organização precisa ser configurada para usar a autenticação OAuth. Para obter mais informações, [consulte Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Os administradores precisam ser membros do grupo de função Administradores Globais. Para saber mais, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Obter o complemento De relatório phishing para si mesmo

1. Vá para o Microsoft AppSource em <https://appsource.microsoft.com/marketplace/apps> e pesquise o add-in De Phishing de relatório.

2. Clique **em OBTER AGORA**.

3. Na caixa de diálogo exibida, revise os termos de uso e política de privacidade e clique em **Continuar**.

4. Entre usando sua conta comercial ou de estudante (para uso comercial) ou sua conta da Microsoft (para uso pessoal).

Depois que o add-in for instalado e habilitado, você verá os seguintes ícones:

- Em Outlook, o ícone tem esta aparência:

  ![Relatar o ícone do add-in phishing para Outlook](../../media/Outlook-ReportPhishing.png)

- Em Outlook na Web, o ícone tem esta aparência:

  ![Outlook no ícone do add-in Phishing de Relatório da Web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Obter e habilitar o complemento De Relatório de Phishing para sua organização

> [!NOTE]
> Pode levar até 12 horas para que o complemento apareça em sua organização.

1. No centro de administração do **Microsoft 365,** vá para a página ir para a página de Configurações \> **Add-ins** em , Se você não vir a Página de Adicionar, vá para o link Complementos de aplicativos integrados do Configurações na parte superior da página <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Aplicativos integrados.** 

2. Selecione **Implantar o Add-in** na parte superior da página e selecione **Próximo**.

   ![Página serviços e complementos no Microsoft 365 de administração](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. No **sub-sub-projeto** que aparece, revise as informações e clique em **Próximo**.

4. Na próxima página, clique **em Escolher na Loja**.

   ![Implantar uma nova página de complemento](../../media/NewAddInScreen2.png)

5. Na página **Selecionar o add-in** que  aparece, clique na caixa Pesquisar, digite **Relatar Phishing** e clique em **Pesquisar** ícone ![ de ](../../media/search-icon.png) Pesquisa. Na lista de resultados, encontre **Relatar Phishing** e clique em **Adicionar**.

6. Na caixa de diálogo exibida, revise as informações de licenciamento e privacidade e clique em **Continuar**.

7. Na página **Configurar o complemento** que aparece, configure as seguintes configurações:

   - **Usuários atribuídos**: Selecione um dos seguintes valores:

     - **Todos** (padrão)
     - **Usuários/grupos específicos**
     - **Só eu**

   - **Método de implantação**: selecione um dos seguintes valores:

     - **Fixo (Padrão)**: o complemento é implantado automaticamente para os usuários especificados e eles não podem removê-lo.
     - **Disponível**: os usuários podem instalar o add-in em **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Opcional**: o complemento é implantado automaticamente para os usuários especificados, mas eles podem optar por removê-lo.

   Quando terminar, clique em **Implantar**.

8. Na página **Implantar Phishing** de Relatório que aparece, você verá um relatório de progresso seguido de uma confirmação de que o complemento foi implantado. Depois de ler as informações, clique em **Próximo**.

9. Na página **Anunciar o** complemento que aparece, revise as informações e clique em **Fechar**.

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Saiba como usar o complemento Relatar Phishing

As pessoas que têm o complemento atribuído a eles verão os seguintes ícones:

- Em Outlook, o ícone tem esta aparência:

  ![Relatar o ícone do add-in phishing para Outlook](../../media/Outlook-ReportPhishing.png)

- Em Outlook na Web, o ícone tem esta aparência:

  ![Outlook no ícone do Add-in phishing do Relatório da Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Revisar ou editar configurações do add-in Relatar Phishing

1. No centro de administração do **Microsoft 365,** vá para a página ir para a página de Configurações \> **Add-ins** em , Se você não vir a Página de Adicionar, vá para o link Complementos de aplicativos integrados do Configurações na parte superior da página <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Aplicativos integrados.** 

2. Encontre e selecione o **complemento Relatar Phishing.**

3. No flyout **Editar Relatório phishing** que aparece, revise e edite as configurações conforme apropriado para sua organização. Quando concluir, clique em **Salvar**.

## <a name="view-and-review-reported-messages"></a>Exibir e revisar mensagens relatadas

Para revisar as mensagens relatadas pelos usuários à Microsoft, você tem estas opções:

- Use o portal Envios de Administrador. Para obter mais informações, consulte [Exibir envios de usuários para a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Crie uma regra de fluxo de emails (também conhecida como regra de transporte) para enviar cópias de mensagens relatadas. Para obter instruções, [consulte Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).
