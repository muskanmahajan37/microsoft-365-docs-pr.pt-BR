---
title: Configure sua infraestrutura para trabalho remoto com o Microsoft 365
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: trabalhar de casa, trabalhar-de-casa, híbrido, trabalhador remoto, trabalho híbrido, funcionários remotos, conectividade híbrida, acesso remoto, trabalho à distância, teletrabalho, trabalho móvel, trabalho remoto, trabalhar de qualquer lugar, local de trabalho flexível
description: Passe através das camadas de infraestrutura para que seus trabalhadores remotos possam acessar com segurança os recursos no local e no Microsoft 365.
ms.openlocfilehash: 1a8cf471cf92e1301c231f395ed0238bb35359cb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246315"
---
# <a name="set-up-your-infrastructure-for-remote-work-with-microsoft-365"></a>Configure sua infraestrutura para trabalho remoto com o Microsoft 365

Para assegurar e otimizar a produtividade e colaboração do trabalhador remoto, configure sua infraestrutura de TI e de nuvem para permitir o trabalho remoto e fornecer acesso às informações, ferramentas e recursos de sua organização no local e na nuvem. Esta solução passa pela implantação de camadas principais de infraestrutura que capacitam seus funcionários a fazer seu melhor trabalho, onde quer que estejam.

Permitir que os funcionários trabalhem fora do escritório é importante para várias organizações para:

- Economizar espaço no escritório.
- Contratar e reter funcionários que não estão dispostos a ser realocados.
- Reduza o deslocamento dos funcionários, deixando-os com mais tempo para serem produtivos e para atividades de redução de estresse fora do trabalho.

O Microsoft 365 tem os recursos para permitir que seus funcionários trabalhem remotamente.

![Capacite funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

>[!Note]
>Se você é novo no Microsoft 365, confira [estes recursos](https://www.microsoft.com/microsoft-365).
>

Assista a esse vídeo para obter uma visão geral do processo de implementação.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

Para profissionais de TI que gerenciam infraestrutura local e baseada em nuvem para permitir a produtividade do funcionário, esta solução oferece estes recursos principais:

- Conectado

  De qualquer lugar do mundo e a qualquer momento, os funcionários remotos podem acessar: 

  - Serviços e dados baseados em nuvem na sua assinatura do Microsoft 365. 

  - Recursos da organização, como os oferecidos por centros de dados de aplicativos locais.

- Seguro

  Os logins são protegidos com autenticação multifator (MFA) e os recursos de segurança internos do Microsoft 365 e do Windows 10 protegem contra malwares, ataques maliciosos e perda de dados.

- Gerenciado

  Os dispositivos dos seus trabalhadores remotos podem ser gerenciados na nuvem com configurações de segurança, aplicativos permitidos e exigir conformidade com a integridade do sistema.

- Colaborativo e produtivo

  Seus funcionários remotos podem ser tão produtivos quanto locais, de uma maneira altamente colaborativa com:

  - Reuniões on-line e sessões de bate-papo com o Teams. 

  - Áreas de trabalho compartilhadas para armazenamento de arquivos baseados em nuvem com acessibilidade global e colaboração em tempo real com o SharePoint e o OneDrive.

  - Tarefas e fluxos de trabalho compartilhados para dividir o trabalho e realizar as tarefas. 

Para uma experiência perfeita de entrada, suas contas de usuário dos Serviços de domínio do Active Directory (AD DS) locais devem ser sincronizadas com o Azure Active Directory (Azure AD). Para proteger os dispositivos com Windows 10, eles devem ser registrados no Intune. Veja a seguir uma visão geral da infraestrutura.

![A infraestrutura básica para funcionários remotos com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

Para habilitar as funcionalidades do Microsoft 365 para seus trabalhadores remotos, utilize esses recursos do Microsoft 365.

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| MFA imposta com padrões de segurança   | Proteja-se contra os dispositivos e identidades comprometidos exigindo uma segunda forma de autenticação para as entradas. O padrão de segurança exige MFA para todas as contas de usuário.   | Microsoft 365 E3 ou E5 |
| MFA imposta com Acesso Condicional| Exija MFA com base nas propriedades da entrada com políticas de Acesso Condicional.    | Microsoft 365 E3 ou E5 | 
| MFA imposta com Acesso Condicional baseado em risco   | Exija MFA com base no risco de o usuário entrar no Microsoft Defender para Identidade. | Microsoft 365 E5 ou E3 com as licenças do Azure AD Premium P2 | 
| Redefinição de Senha por autoatendimento (SSPR)    | Permita que os usuários redefinam ou desbloqueiem suas contas ou senhas.  | Microsoft 365 E3 ou E5 |
| Proxy do Aplicativo Azure AD    | Forneça acesso remoto seguro para aplicativos baseados na web hospedados em servidores da intranet.   | Exige uma assinatura paga do Azure paga |
| VPN de Ponto a Site do Azure   | Criar uma conexão segura do dispositivo de um trabalhador remoto para sua intranet por meio de uma rede virtual do Azure.   | Exige uma assinatura paga do Azure paga |
| Área de Trabalho Virtual do Windows   | Suporte a funcionários remotos que só podem usar seus dispositivos pessoais e não gerenciados com as áreas de trabalho virtuais que estão sendo executadas no Azure. | Exige uma assinatura paga do Azure paga |
| Serviços de Área de Trabalho Remota (RDS) | Permitir que os funcionários se conectem a computadores baseados no Windows na intranet. | Microsoft 365 E3 ou E5 | 
| Gateway dos Serviços de Área de Trabalho Remota   | Criptografe comunicações e impeça que os hosts RDS sejam expostos diretamente à Internet. | Exige licenças separadas do Windows Server |
| Microsoft Intune | Gerenciar dispositivos e aplicativos.   | Microsoft 365 E3 ou E5 | 
| Gerenciador de Configurações | Gerenciar instalações, atualizações e configurações de software em seus dispositivos | Exige licenças separadas do Configuration Manager |
| Análise de Área de Trabalho | Determine a prontidão de atualização dos seus clientes Windows.   | Exige licenças separadas do Configuration Manager |
| Windows Autopilot | Configure e configure novamente os novos dispositivos com Windows 10 para uso produtivo.   | Microsoft 365 E3 ou E5 |
| Microsoft Teams, Exchange Online, SharePoint Online e OneDrive, Microsoft 365 Apps, Microsoft Power Platform e Yammer | Criar, comunicar e colaborar. | Microsoft 365 E3 ou E5 |
||||

Para critérios de segurança e conformidade, confira [Implantar segurança e conformidade para funcionários remotos](empower-people-to-work-remotely-security-compliance.md).

<a name="poster"></a> Para obter um resumo de 2 páginas dessa solução, consulte o pôster [Capacitar trabalhadores remotos](../downloads/empower-remote-workers.pdf).

[![Pôster Capacitar trabalhadores remotos](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

Você também pode baixar este cartaz nos formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) ou [PowerPoint](https://download.microsoft.com/download/5/1/1/511b77a9-a34c-4ea7-af2a-32b07f20b780/empower-remote-workers.pptx) e imprimi-lo em papel tamanho carta, legal, ou tabloide (11 x 17).

## <a name="provide-remote-working-for-all-of-your-workers"></a>Fornecer trabalho remoto para todos os seus funcionários

Você pode permitir que todos os seus funcionários permaneçam produtivos em qualquer lugar com estes dispositivos:

- Um dispositivo moderno, como um laptop Surface e Windows 10, que possui os recursos, a segurança e o desempenho para acessar os aplicativos e serviços em nuvem do Microsoft 365 diretamente pela web.

- Qualquer dispositivo, incluindo laptops ou desktops mais antigos usados em casa, que podem acessar aplicativos e serviços em nuvem da Microsoft 365 indiretamente por meio de um desktop virtual [baseado em Windows 10 de rápida implantação](empower-people-to-work-remotely-remote-access.md#deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices). Essa opção oferece alto desempenho, forte segurança e gerenciamento simplificado de TI.

## <a name="next-steps"></a>Próximas etapas

Use essas etapas para proteger e otimizar o acesso aos servidores e serviços em nuvem da sua organização e maximizar a produtividade do seu trabalhador remoto.

1. [Aumentar a segurança de entrada com a MFA](empower-people-to-work-remotely-secure-sign-in.md)
2. [Fornecer acesso remoto a aplicativos e serviços e aplicativos locais](empower-people-to-work-remotely-remote-access.md)
3. [Implantar serviços de segurança e conformidade](empower-people-to-work-remotely-security-compliance.md)
4. [Implantar o gerenciamento de pontos de extremidade em seus dispositivos, PCs e outros pontos de extremidade](empower-people-to-work-remotely-manage-endpoints.md)
5. [Implantar aplicativos e serviços de produtividade de trabalhador remoto](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [Treinar os funcionários remotos e responder a questões sobre o uso](empower-people-to-work-remotely-train-monitor-usage.md)

[![As etapas para configurar sua infraestrutura para trabalho remoto com o Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

Para ver como uma organização multinacional fictícia, mas representativa, montou sua infraestrutura para o trabalho remoto, confira [Resposta e infraestrutura da Contoso à COVID-19 para uma força de trabalho híbrida](contoso-remote-onsite-work.md).
