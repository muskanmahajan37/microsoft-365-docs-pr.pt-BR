---
title: Roteiro de rede para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: O roteiro para implementar a rede do Microsoft 365.
ms.openlocfilehash: be1691138290a592822bfb4d59286fe795270450
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923547"
---
# <a name="networking-roadmap-for-microsoft-365"></a>Roteiro de rede para o Microsoft 365

O Microsoft 365 para empresas inclui serviços de nuvem de produtividade e colaboração, o Microsoft Intune e muitos serviços de identidade e segurança do Microsoft Azure. Todos esses serviços baseados em nuvem dependem da segurança, desempenho e confiabilidade das conexões de dispositivos clientes pela Internet ou circuitos dedicados. Para hospedar esses serviços e disponibilizá-los para clientes em todo o mundo, a Microsoft desenvolveu uma infraestrutura de rede que enfatiza o desempenho e a integração. 

Uma parte essencial da integração do Microsoft 365 é garantir que suas conexões de rede e Internet sejam configuradas para acesso otimizado. Configurar sua rede local para acessar uma nuvem de Software como Serviço (SaaS) globalmente distribuída é diferente de uma rede tradicional otimizada para o tráfego para datacenters locais e uma conexão de Internet central. 

Use estes artigos para entender as principais diferenças e modificar seus dispositivos de borda, computadores clientes e rede local para obter o melhor desempenho para seus usuários locais.

## <a name="plan"></a>Planejar

Na fase de planejamento da implementação de rede:

- [Entender como funciona a rede do Microsoft 365](microsoft-365-networking-overview.md)
- [Avaliar sua conectividade de rede atual](assessing-network-connectivity.md)
- [Determinar se ExpressRoute é o correto para sua organização](network-planning-with-expressroute.md)
- [Planejar seus dispositivos de rede](plan-for-network-devices.md)
- [Configurar sua rede para migração](network-and-migration-planning.md)

## <a name="deploy"></a>Implantar

Na fase de implantação da implementação de rede:

- [Verifique se sua rede corporativa está otimizada para a conectividade do Microsoft 365](set-up-network-for-microsoft-365.md)
- [Adicionar os domínios DNS para sua organização](../admin/setup/add-domain.md)
- [Otimizar sua conectividade com pontos de extremidade do Microsoft 365](microsoft-365-ip-web-service.md)
- [Otimizar a conectividade para funcionários remotos](microsoft-365-vpn-split-tunnel.md)
- Se necessário, [configure ExpressRoute](azure-expressroute.md)

## <a name="manage"></a>Gerenciar

Na fase de gerenciamento da implementação de rede:

- [Verifique se seus dispositivos de rede estão usando os pontos de extremidade mais recentes do Office 365](microsoft-365-endpoints.md)
- [Monitorar e ajustar o desempenho da rede](network-planning-and-performance.md)
- [Monitorar suas conexões ExpressRoute](managing-expressroute-for-connectivity.md)

## <a name="network-equipment-vendors"></a>Fornecedores de equipamentos de rede

Se você for um fornecedor de equipamentos de rede, participe do Programa de Parceiros de [Rede do Microsoft 365.](microsoft-365-networking-partner-program.md) Inscreva-se no programa para criar princípios de conectividade de rede do Microsoft 365 em seus produtos e soluções. 

## <a name="how-contoso-did-networking-for-microsoft-365"></a>Como a Contoso fazia rede para o Microsoft 365

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [otimizou seus dispositivos de rede e conexões com a internet](contoso-networking.md) para os serviços de nuvem do Microsoft 365.

![A Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Próxima etapa

Inicie o planejamento de rede com a visão geral de conectividade de [rede do Microsoft 365.](microsoft-365-networking-overview.md)