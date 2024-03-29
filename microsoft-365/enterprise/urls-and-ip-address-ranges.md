---
title: 'URLs e intervalos de endereço IP do Office 365 '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Resumo: o Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem estar acessíveis para os clientes que usam os planos do Office 365, incluindo a Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 65e69465c56b3c7da63ca5cdcc1287c4794f199c
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651255"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Intervalos de endereços IP e URLs do Office 365

O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis para os clientes que usam os planos do Office 365, incluindo a nuvem pública da Comunidade (GCC).
  
*Office 365 Worldwide (+GCC)* | [Office 365 operado pela 21 Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Alemanha](microsoft-365-germany-endpoints.md) | [Office 365 Departamento de Defesa do Governo dos E.U.A.](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 GCC Alta do Governo dos E.U.A.](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Última atualização:** 19/05/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Alterar assinatura do Log](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Baixar:** todos os destinos obrigatórios e opcionais em uma lista [no formato em JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> | **Use:** nossos arquivos proxy [PAC](managing-office-365-endpoints.md#pacfiles) <br/> |

 Comece com [Gerenciar os pontos de extremidade do Office 365](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando estes dados. Os dados dos pontos de extremidade são atualizados, conforme necessário, no início de cada mês com novos endereços IP e URLs publicadas 30 dias antes de se tornarem ativas. Isso permite que os clientes que ainda não têm atualizações automáticas completem seus processos antes que uma nova conectividade seja necessária. Os pontos de extremidade também podem ser atualizados durante o mês, se necessário, para tratar de escalações de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Todos os dados exibidos abaixo nesta página são gerados a partir dos serviços Web baseados em REST. Se estiver usando um script ou dispositivo de rede para acessar esses dados, vá diretamente para o [serviço Web](microsoft-365-ip-web-service.md).

Os dados do terminal abaixo listam os requisitos de conectividade da máquina de um usuário ao Office 365. Ele não inclui conexões de rede da Microsoft em uma rede de clientes, às vezes chamadas de conexões de rede híbridas ou de entrada. Consulte [Terminais adicionais](additional-office365-ip-addresses-and-urls.md) para obter mais informações.

Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.

As colunas de dados exibidas são:

- **ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.

- **Categoria**: mostra se o conjunto de pontos de extremidade está classificado como “Otimizar”, “Permitir” ou “Padrão”. Você pode ler sobre essas categorias e orientações para o gerenciamento delas em [Novas categorias de pontos de extremidade do Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Esta coluna também lista quais conjunto de pontos de extremidade são necessário para se ter conectividade de rede. Quanto aos conjuntos de pontos de extremidade que não precisam ter conectividade de rede, fornecemos notas neste campo para indicar qual funcionalidade faltaria se o conjunto de pontos de extremidade estivesse bloqueado. Se você excluir uma área de serviço inteira, os conjuntos de pontos de extremidade listados conforme necessário não exigirão conectividade.

- **ER**: Aqui, você verá um **Sim** se o conjunto de pontos de extremidade tem suporte no Azure ExpressRoute com prefixos de rota do Office 365. A comunidade do BGP que inclui os prefixos de rota mostrados se alinha com a área do serviço listada. Quando o ER estiver marcado como **Não**, isso significa que o ExpressRoute não é suportado para esse conjunto de pontos de extremidade. No entanto, não devemos presumir que não existem rotas anunciadas para um conjunto de ponto de extremidade onde ER está marcado como **Não**.

- **Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.
 
- **Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Para recomendações sobre endereços IP e URLs do Yammer, consulte [Não é recomendável usar endereços IP codificados para o Yammer](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) no blog do Yammer.
>

## <a name="related-topics"></a>Tópicos Relacionados
[Pontos de extremidades adicionais não incluídos no endereço IP do Office 365 e serviço da Web de URL](additional-office365-ip-addresses-and-urls.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[Pontos de extremidade gerais do Microsoft Stream](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Monitorar a conectividade do Microsoft 365](./monitor-connectivity.md)

[CA raiz e o pacote da autoridade de certificação intermediária no sistema de aplicativos de terceiros](../compliance/encryption-office-365-certificate-chains.md)
  
[Conectividade de cliente](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Redes de distribuição de conteúdo](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem Pública](https://www.microsoft.com/download/details.aspx?id=56519)

[Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem do Governo dos EUA](https://www.microsoft.com/download/details.aspx?id=57063)

[Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem da Alemanha](https://www.microsoft.com/download/details.aspx?id=57064)

[Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem da China](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Grupos de notícias públicos da Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)

[Nome do Serviço e Registro de Número de Porta de Protocolo de Transporte](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
