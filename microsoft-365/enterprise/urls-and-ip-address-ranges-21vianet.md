---
title: Intervalos de URLs e endereços IP do Office 365 operados pela 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: Este artigo lista as URLs e intervalos de endereços IP do Office 365 quando operado pela 21Vianet na China.
hideEdit: true
ms.openlocfilehash: ed9b6fdbef1ca121ccf53b635768ebdaab89763a
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418039"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>Intervalos de URLs e endereços IP do Office 365 operados pela 21Vianet

 *Aplica-se a: Office 365 operado pela 21Vianet - Administrador de Pequenas Empresas, Office 365 operado pela 21Vianet - Administrador*

**Resumo**: os pontos de extremidade a seguir (FQDNs, portas, URLs, prefixos IPv4 e IPv6) se aplicam ao Office 365 operado pela 21 Vianet e são projetados para entregar serviços de produtividade às organizações que usam somente esses planos.
  
 **Pontos de extremidade do Office 365:** [global (incluindo GCC)](urls-and-ip-address-ranges.md)  | *Office 365 operado pela 21 Vianet* | [Office 365 Alemanha](microsoft-365-germany-endpoints.md)  |  [Office 365 Governo dos E.U.A. Departamento de Defesa](microsoft-365-u-s-government-dod-endpoints.md) | [GCC High do Office 365 Governo dos E.U.A.](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Última atualização:** 29/03/2021 - Assinatura do Log de Alterações ![ ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [do](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) RSS|**Baixar:** todos os destinos obrigatórios e opcionais em uma lista [no formato em JSON](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Comece com [Gerenciando pontos de extremidade do Office 365 ](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando esses dados. Os dados dos terminais são atualizados conforme necessário no início de cada mês com novos endereços IP e URLs publicados 30 dias antes de serem ativados. Isso permite que os clientes que ainda não possuem atualizações automatizadas concluam seus processos antes que uma nova conectividade seja necessária. Os endpoints também podem ser atualizados durante o mês, se necessário, para lidar com escalações de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Os dados mostrados nesta página a seguir são todos gerados a partir dos serviços da web baseados em REST. Se estiver usando um script ou um dispositivo de rede para acessar esses dados, você deve ir para o [serviço da Web ](microsoft-365-ip-web-service.md) diretamente.

Os dados dos pontos de extremidade abaixo listam requisitos de conectividade do computador de um usuário para o Office 365. Eles não incluem conexões de rede da Microsoft com uma rede de clientes, que são algumas vezes chamadas conexões de rede híbridas ou de entrada.

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: mostra se o conjunto de pontos de extremidade é categorizado como "Otimizar", "Permitir" ou "Padrão". Leia sobre essas categorias e diretrizes para gerenciamento de todos eles em [ https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). Esta coluna também lista quais conjuntos de ponto de extremidade são necessários para que haja conectividade de rede. Para conjuntos de ponto de extremidade que não são necessários para que haja conectividade de rede, fornecemos notas nesse campo para indicar qual funcionalidade estaria ausente se o conjunto de pontos de extremidade estiver bloqueado. Se você estiver excluindo uma área de serviço inteira, os conjuntos de pontos de extremidade listados como necessários não vão precisar de conectividade.

- **ER**: Aqui, você verá um **Sim** se o conjunto de pontos de extremidade tem suporte no Azure ExpressRoute com prefixos de rota do Office 365. A comunidade do BGP que inclui os prefixos de rota mostrados se alinha com a área do serviço listada. Quando o ER estiver marcado como **Não**, isso significa que o ExpressRoute não é suportado para esse conjunto de pontos de extremidade. No entanto, não devemos presumir que não existem rotas anunciadas para um conjunto de ponto de extremidade onde ER está marcado como **Não**.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.
 
- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]