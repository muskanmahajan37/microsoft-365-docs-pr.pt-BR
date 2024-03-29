---
title: Implantação baseada em aplicativo para o Microsoft Defender para Ponto de Extremidade no iOS
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no iOS usando um aplicativo
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f2b9a1365a27bb7397aea51dcd5bc9e2631afe2
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624700"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>Implantar o Microsoft Defender para Ponto de Extremidade no iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Este tópico descreve a implantação do Defender para Ponto de Extremidade no iOS em Portal da Empresa do Intune dispositivos inscritos. Para obter mais informações sobre o registro de dispositivo do Intune, consulte [Registrar dispositivos iOS/iPadOS no Intune](/mem/intune/enrollment/ios-enroll).

## <a name="before-you-begin"></a>Antes de começar

- Verifique se você tem acesso ao Centro de [administração do Gerenciador de Pontos de Extremidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=2109431)

- Certifique-se de que o registro do iOS seja feito para seus usuários. Os usuários precisam ter uma licença do Defender para Ponto de Extremidade atribuída para usar o Defender para o Ponto de Extremidade no iOS. Consulte [Atribuir licenças aos usuários para](/azure/active-directory/users-groups-roles/licensing-groups-assign) obter instruções sobre como atribuir licenças.

> [!NOTE]
> O Microsoft Defender para Ponto de Extremidade no iOS agora está disponível na [Apple App Store](https://aka.ms/mdatpiosappstore).

## <a name="deployment-steps"></a>Etapas de implantação

Implante o Defender para Ponto de Extremidade no iOS por meio Portal da Empresa do Intune.

### <a name="add-ios-store-app"></a>Adicionar aplicativo da loja do iOS

1. No Centro de administração do Gerenciador de Pontos de Extremidade [da Microsoft,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Aplicativos**  ->  **iOS/iPadOS** Adicionar aplicativo da loja  ->    ->  **do iOS** e clique em **Selecionar**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)

1. Na página Adicionar aplicativo, clique em **Pesquisar na Loja de Aplicativos** e digite o Ponto de Extremidade do Microsoft **Defender** na barra de pesquisa. Na seção resultados da pesquisa, clique em Ponto de *Extremidade do Microsoft Defender* e clique em **Selecionar**.

1. Selecione **iOS 11.0 como** o sistema operacional Mínimo. Revise o restante das informações sobre o aplicativo e clique em **Próximo**.

1. Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo**. Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para Ponto de Extremidade no aplicativo iOS. Clique **em Selecionar** e, em **seguida, Em Seguida.**

    > [!NOTE]
    > O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)

1. Na seção *Revisar + Criar,* verifique se todas as informações inseridas estão corretas e selecione **Criar**. Em alguns instantes, o aplicativo Defender para Ponto de Extremidade deve ser criado com êxito, e uma notificação deve aparecer no canto superior direito da página.

1. Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>Integração automática do perfil VPN (Integração Simplificada)

> [!NOTE]
> A integração automática do perfil VPN está atualmente em visualização e as etapas mencionadas nesta seção podem ser substancialmente modificadas antes de serem lançadas comercialmente.

Os administradores podem configurar automaticamente a configuração do perfil vpn. Isso configurará automaticamente o perfil VPN do Defender para Ponto de Extremidade sem que o usuário faça isso durante a integração. Observe que a VPN é usada para fornecer o recurso de Proteção da Web. Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.

1. No Centro de administração do Gerenciador de Pontos de Extremidade [da Microsoft,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para   ->  **Perfis de Configuração** de  ->  **Dispositivos Criar Perfil**.
1. Escolha **Plataforma como** **iOS/iPadOS** e **Tipo de perfil** como **VPN**. Clique em **Criar**.
1. Digite um nome para o perfil e clique em **Próximo**.
1. Selecione **VPN personalizada** para Tipo de Conexão e, na seção VPN **Base,** insira o seguinte:
    - Nome da conexão = Microsoft Defender para Ponto de Extremidade
    - Endereço do servidor VPN = 127.0.0.1
    - Método Auth = "Nome de usuário e senha"
    - Túnel Dividido = Desabilitar
    - Identificador vpn = com.microsoft.scmx
    - Nos pares de valores-chave, insira a **chave AutoOnboard** e despeça o valor como **True**.
    - Tipo de VPN automática = VPN sob demanda
    - Clique **em Adicionar** regras sob **demanda** e selecione Quero fazer o seguinte = Estabelecer **VPN**, quero restringir a = Todos os **domínios**.

    ![Uma captura de tela da configuração de perfil vpn](images/ios-deploy-8.png)

1. Clique em Próximo e atribua o perfil a usuários direcionados.
1. Na seção *Revisar + Criar,* verifique se todas as informações inseridas estão corretas e selecione **Criar**.

## <a name="complete-onboarding-and-check-status"></a>Concluir a integração e verificar o status

1. Depois que o Defender for Endpoint no iOS tiver sido instalado no dispositivo, você verá o ícone do aplicativo.

    ![Uma captura de tela de um telefone inteligente Descrição gerada automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. Toque no ícone do aplicativo Defender para Ponto de Extremidade e siga as instruções na tela para concluir as etapas de integração. Os detalhes incluem a aceitação do usuário final das permissões do iOS exigidas pelo Defender para Ponto de Extremidade no iOS.

3. Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos Central de Segurança do Microsoft Defender.

    > [!div class="mx-imgBorder"]
    > ![Uma captura de tela de um telefone celular Descrição gerada automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>Configurar o Microsoft Defender para Ponto de Extremidade para Modo Supervisionado

O Microsoft Defender for Endpoint no aplicativo iOS tem capacidade especializada em dispositivos iOS/iPadOS supervisionados, dado o aumento dos recursos de gerenciamento fornecidos pela plataforma nesses tipos de dispositivos. Para aproveitar esses recursos, o aplicativo Defender for Endpoint precisa saber se um dispositivo está no modo Supervisionado.

### <a name="configure-supervised-mode-via-intune"></a>Configurar o modo Supervisionado por meio do Intune

O Intune permite configurar o aplicativo Defender para iOS por meio de uma política de Configuração de Aplicativo.

   > [!NOTE]
   > Esta política de configuração de aplicativo para dispositivos supervisionados é aplicável apenas a dispositivos gerenciados e deve ser direcionada para todos os dispositivos iOS gerenciados como uma prática prática prática.

1. Entre no centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) vá para Políticas de configuração do Aplicativo de   >  **Aplicativos**  >  **Adicionar**. Clique em **Dispositivos gerenciados**.

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)

1. Na página *Criar política de configuração de aplicativo,* forneça as seguintes informações:
    - Nome da política
    - Plataforma: Selecione iOS/iPadOS
    - Aplicativo direcionado: selecione **Microsoft Defender ATP** na lista

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)

1. Na próxima tela, selecione **Usar designer de configuração** como o formato. Especifique a seguinte propriedade:
    - Chave de Configuração: supervisionada
    - Tipo de valor: Cadeia de caracteres
    - Valor da configuração: {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)

1. Clique **em Próximo** para abrir a página Marcas de **escopo.** As marcas de escopo são opcionais. Clique em **Avançar** para continuar.

1. Na página **Atribuições,** selecione os grupos que receberão esse perfil. Para esse cenário, é prática ideal direcionar Todos os **Dispositivos.** Para obter mais informações sobre como atribuir perfis, consulte [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).

   Ao implantar em grupos de usuários, um usuário deve entrar em um dispositivo antes da aplicação da política.

   Clique em **Avançar**.

1. Na página **Revisar + criar,** quando terminar, escolha **Criar**. O novo perfil é exibido na lista de perfis de configuração.

1. Em seguida, para recursos avançados de anti-phishing, você pode implantar um perfil personalizado nos dispositivos iOS supervisionados. Siga as etapas abaixo:
    - Baixar o perfil de configuração de [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - Navegar até **dispositivos**  ->  **iOS/iPadOS** Perfis de  ->  **configuração**  ->  **Criar Perfil**

    > [!div class="mx-imgBorder"]
    > ![Imagem do Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)

    - Forneça um nome do perfil. Quando solicitado a importar um arquivo de perfil de configuração, selecione o que foi baixado acima.
    - Na seção **Atribuição,** selecione o grupo de dispositivos ao qual você deseja aplicar esse perfil. Como prática prática, isso deve ser aplicado a todos os dispositivos iOS gerenciados. Clique em **Avançar**.
    - Na página **Revisar + criar,** quando terminar, escolha **Criar**. O novo perfil é exibido na lista de perfis de configuração.

## <a name="next-steps"></a>Próximas etapas

[Configurar o Defender para Ponto de Extremidade em recursos do iOS](ios-configure-features.md)
