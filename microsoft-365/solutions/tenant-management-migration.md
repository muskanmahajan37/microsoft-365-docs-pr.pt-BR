---
title: Etapa 4. Migração para seu Microsoft 365 para locatários corporativos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migre seus dispositivos Windows, aplicativos cliente do Office e servidores do Office para seus locatários do Microsoft 365.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929139"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Etapa 4. Migração para seu Microsoft 365 para locatários corporativos

A maioria das organizações corporativas tem um ambiente heterogêneo que inclui várias versões de sistemas operacionais, software cliente e software de servidor. O Microsoft 365 para empresas inclui as versões mais seguras dos principais componentes da infraestrutura de TI. Ele também inclui recursos de produtividade projetados para tirar proveito das tecnologias de nuvem.

Para maximizar o valor de negócios do Microsoft 365 para o pacote de produtos integrados da empresa, comece a planejar e implementar uma estratégia para migrar essas versões:

| From | To |
|:-------|:-----|
| Windows 7 e Windows 8.1 | Windows 10 Enterprise |
| Produtos do cliente do Office instalados nos dispositivos do seu funcionário | Microsoft 365 Apps para empresas |
| Produtos do servidor do Office instalados em servidores locais | Seus serviços equivalentes baseados em nuvem no Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrando para o Windows 10

Cada licença do Microsoft 365 para empresas inclui uma licença para o Windows 10 Enterprise. Para migrar seus dispositivos que executem o Windows 7 ou o Windows 8.1, você pode fazer uma atualização in-locar. O suporte terminou para o Windows 7 em *14 de janeiro de 2020*. 

Para obter métodos adicionais de instalação do Windows 10 Enterprise além de uma atualização in-locar, consulte Cenários de implantação [do Windows 10.](/windows/deployment/windows-10-deployment-scenarios) Você também pode [planejar a implantação do Windows 10](/windows/deployment/planning/) por conta própria.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrando para o Microsoft 365 Apps para empresas

O Microsoft 365 para empresas inclui o Microsoft 365 Apps para empresas, uma versão dos produtos cliente do Office (Word, PowerPoint, Excel e Outlook) que é instalado e atualizado a partir da nuvem da Microsoft. Para obter mais informações, consulte [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).

Em vez de manter seus computadores atualizados para o Office 2019 ou versões anteriores, tome as seguintes etapas:

1. Obter e atribuir uma licença do Microsoft 365 para seus usuários.
2. Desinstale o Office 2013 ou o Office 2016 em seus computadores.
3. Instale o Microsoft 365 Apps para empresas, individualmente ou durante uma implantação de IT. Para obter mais informações, consulte [Guia de implantação para Aplicativos do Microsoft 365.](/deployoffice/deployment-guide-microsoft-365-apps)

O Microsoft 365 Apps for enterprise instala atualizações de segurança e novas atualizações de recursos automaticamente e pode aproveitar os serviços baseados em nuvem no Microsoft 365 para aumentar a segurança e a produtividade.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migrando servidores e dados locais para o Microsoft 365

O Microsoft 365 para empresas inclui versões baseadas em nuvem dos serviços de servidor do Office que usam algumas das mesmas ferramentas que as versões locais do software do servidor do Office, como navegadores da Web e o cliente do Outlook. Esses serviços baseados em nuvem são atualizados automaticamente para segurança e novos recursos. Após a migração, seu departamento de IT pode economizar o tempo necessário para manter e atualizar servidores locais.

Use os seguintes recursos para obter informações sobre como migrar usuários e dados para cargas de trabalho específicas do Microsoft 365:

- [Mover caixas de correio de caixas de correio locais Exchange Server para o Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrar dados do SharePoint Do SharePoint Server para o SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar o Skype for Business Online para o Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Transição para toda a organização

Para obter uma imagem melhor de como mover toda a organização para os produtos e serviços no Microsoft 365 para empresas, baixe este cartaz de transição:

[![Imagem mostrando o cartaz Transição para o Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Esse pôster de duas páginas é uma maneira rápida de fazer o inventário da infraestrutura existente. Use-o para obter orientações para mover para um produto ou serviço no Microsoft 365 para empresas. Ele mostra produtos do Windows e do Office e outros elementos de infraestrutura e segurança, como gerenciamento de dispositivos, proteção contra identidade e ameaças e proteção e conformidade de informações.

## <a name="results-of-step-4"></a>Resultados da Etapa 4

Para migração para seu locatário do Microsoft 365, você determinou:

- Quais dispositivos estão executando o Windows 7 ou Windows 8.1 e o plano para atualizá-los para o Windows 10 Enterprise.
- Quais dispositivos estão executando os aplicativos cliente do Office e o plano para atualizá-los para aplicativos do Microsoft 365 para empresas.
- Quais serviços de servidor do Office locais devem ser migrados para o equivalente do Microsoft 365 e o plano para migrar eles e seus dados.

Aqui está um exemplo de um locatário com uma migração concluída de servidores locais.

![Exemplo de um locatário com uma migração concluída de servidores locais](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

Nesta ilustração, a organização tem:

- Migrou suas caixas de correio Exchange Server local para o Exchange Online.
- Migrou seus sites e dados locais do SharePoint Server para o SharePoint no Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Manutenção contínua para migração

Em uma base contínua, talvez seja necessário:

- Dependendo do estado da migração de caixa de correio do Exchange, continue a rolar a transição para o Exchange Online para sua organização.
- Dependendo do estado da migração do site local do SharePoint, continue a rolar a transição para o SharePoint no Microsoft 365 para sua organização.

## <a name="next-step"></a>Próxima etapa

[![Etapa 5. Implantar o gerenciamento de dispositivos e aplicativos](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continue com [o gerenciamento de dispositivos e aplicativos](tenant-management-device-management.md) para implantar o gerenciamento de dispositivos e aplicativos.