---
title: Configurar o Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Ao comprar o Microsoft 365 Business Standard, você tem a opção de usar um domínio que possui ou comprar um durante a inscrição.
ms.openlocfilehash: ca9cc359aaabfc16a5d0c57a75362c7826dea0db
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635625"
---
# <a name="set-up-microsoft-business-standard"></a>Configurar o Microsoft Business Standard



## <a name="add-your-domain-to-personalize-sign-in"></a>Adicione seu domínio para personalizar o login

Ao comprar o Microsoft 365 Business Standard, você tem a opção de usar um domínio que possui ou comprar um durante a inscrição.

- Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

1. Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global. 

2. Clique em **Ir para a Configuração** pra iniciar o assistente.

3. Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.
    
4. Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Vá para [Adicionar usuários](#add-users-and-assign-licenses) em vez disso.

    
4. Siga as etapas no assistente para [Criar registros DNS em qualquer provedor de hospedagem DNS do Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifique se você é o proprietário do domínio. Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../add-users/add-users.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Adicionar usuários ao assistente

Todos os usuários que você adicionar no assistente recebem automaticamente uma licença do Microsoft 365 Business Standard.

1. Se sua assinatura do Microsoft 365 Business Standard tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você obterá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.

2. Depois de adicionar os usuários, você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

## <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínio](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**. Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.
    - Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), você irá desejar gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Veja [domínios básicos](/office365/admin/get-help-with-domains/dns-basics) para mais informações.

2. Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.

    Quando o processo de inscrição for concluído, você será direcionado para o centro de administração, onde acompanhará um assistente para instalar os aplicativos do Office, adicionar seu domínio, adicionar usuários e atribuir licenças. Depois de concluir a configuração inicial, você poderá usar a página de **configuração** no centro de administração para continuar a instalar e configurar os serviços que vêm com as assinaturas.

    Para obter mais informações sobre o assistente de configuração e a página de **instalação** do centro de administração, confira [Diferença entre o assistente de configuração e a página de configuração](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Concluir a configuração

### <a name="set-up-outlook-for-email"></a>Configurar o Outlook para e-mail

1. No menu Iniciar do Windows, procure Outlook e selecione-o.

    (Se estiver usando um Mac, abra o Outlook na barra de ferramentas ou localize-o usando o Finder).

    Se você tiver acabado de instalar o Outlook, na página inicial, selecione **Avançar**.

2. Escolha **Arquivo** \>**Informações**\>**Adicionar Conta**.

3. Digite seu endereço de e-mail do Microsoft e selecione **conectar**.

## <a name="watch-set-up-outlook-for-email"></a>Assista: configurar o Outlook para e-mail

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Veja mais em [Configurar o Outlook para email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importar e-mail

Se você estava usando o Outlook com outra conta de email, poderá importar seus emails, calendário e contatos antigos para sua nova conta da Microsoft.
  
1. **Exportar seus emails antigos**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.

    Selecione **Exportar para um Arquivo** e siga as etapas para exportar o Arquivo de Dados do Outlook (.pst) e quaisquer subpastas.

2. **Importar seus emails antigos**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.

    Desta vez, selecione **Importar de outro programa ou arquivo** e siga as etapas para importar o arquivo de backup criado ao exportar os emails antigos.

## <a name="watch-import-and-redirect-email"></a>Assista: importar e redirecionar emails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Veja mais em [Importar emails com o Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

Você também pode usar o centro de administração do Exchange para importar e-mails de todos os usuários. Para obter mais informações, consulte [migrar várias contas de e-mail](/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Usar um site público

O Microsoft 365 não inclui um site público para a sua empresa. Se quiser configurar um, considere usar um parceiro da Microsoft, como o GoDaddy ou o WIX.
  
1. No Centro de Administração, vá para **Recursos** e selecione **Site público**.

2. Selecione **Saiba mais** em uma das opções e depois inscreva-se com um parceiro de site e use as ferramentas dele para configurar e projetar seu site.

## <a name="watch-create-your-business-website"></a>Assista: criar seu site de negócios

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

## <a name="related-content"></a>Conteúdo relacionado

[Crie um site](../../business-video/create-web-site.md) (vídeo)\
[Microsoft 365 para seus negócios ](../../business-video/index.yml) (página de link)
