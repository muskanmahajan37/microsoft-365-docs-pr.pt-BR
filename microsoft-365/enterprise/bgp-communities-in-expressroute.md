---
title: Usando comunidades BGP no ExpressRoute para cenários do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Saiba como usar comunidades BGP no Azure ExpressRoute para gerenciar o número de prefixos IP e a largura de banda necessária para cenários do Office 365.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905207"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Usando comunidades BGP no ExpressRoute para cenários do Office 365

Conectar-se ao Office 365 usando o Azure ExpressRoute baseia-se em anúncios BGP de sub-redes IP específicas que representam redes nas quais os pontos de extremidade do Office 365 são implantados. Devido à natureza global do Office 365 e ao número de serviços que constituem o Office 365, os clientes geralmente precisam gerenciar os anúncios aceitos em sua rede. Reduzindo o número de sub-redes IP; chamado de prefixos IP ao longo do restante deste artigo, para se alinhar com a terminologia de gerenciamento de rede BGP, atende aos seguintes objetivos finais para clientes:
  
- Gerenciar o número de prefixos **IP** anunciados aceitos - Os clientes que possuem uma infraestrutura de rede interna ou uma operadora de rede que só oferece suporte a um número limitado de prefixos IP e clientes que têm uma operadora de rede que cobra por aceitar prefixos acima de um número limitado vão querer avaliar o número total de prefixos já anunciados em sua rede e selecionar quais aplicativos do Office 365 são mais adequados para ExpressRoute.

- Gerencie a quantidade de largura de banda necessária no circuito **do Azure ExpressRoute** - Os clientes podem querer controlar o envelope de largura de banda dos serviços do Office 365 pelo caminho ExpressRoute versus caminho da Internet. Isso permite que os clientes reservem a largura de banda expressRoute para aplicativos específicos, como o Skype for Business, e roteiem os aplicativos restantes do Office 365 pelo caminho da Internet.

Para ajudar os clientes com essas metas, os prefixos IP do Office 365 anunciados no ExpressRoute são marcados com valores de comunidade BGP específicos do serviço, conforme mostrado no exemplo abaixo.
  
> [!NOTE]
> Você deve esperar que algum tráfego de rede associado a outros aplicativos seja incluído no valor da comunidade. Esse é o comportamento esperado para uma oferta global de Software como Serviço com serviços compartilhados e datacenters. Isso foi minimizado sempre que possível com as duas metas acima, gerenciando a contagem de prefixos e/ou a largura de banda em mente.

|**Serviço**|**Valor da comunidade BGP**|**Anotações**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Inclui serviços exchange e EOP\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Serviços do Skype for Business Online & Microsoft Teams  <br/> |
|Outros serviços do Office 365\*  <br/> |12076:5100  <br/> |Inclui o Azure Active Directory (cenários de Autenticação e Sincronização de Diretórios), bem como serviços do Portal do Office 365  <br/> |
|\*O escopo dos cenários de serviço incluídos no ExpressRoute está documentado no artigo de pontos de extremidade [do Office 365.](./urls-and-ip-address-ranges.md)  <br/> \*\*Serviços adicionais e valores de comunidade BGP podem ser adicionados no futuro. [Consulte a lista atual de Comunidades BGP](/azure/expressroute/expressroute-routing).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Quais são os cenários mais comuns para usar comunidades BGP?

Os clientes podem usar comunidades BGP para regular grupos de prefixos IP aceitos por sua rede por meio do Azure ExpressRoute, influenciando a contagem total de prefixos IP e o envelope de largura de banda esperado de determinados serviços do Office 365. É importante entender que todo o Office 365 exigirá tráfego vinculado à Internet independentemente do uso de Comunidades do Azure ExpressRoute ou BGP. Os três cenários a seguir são os usos mais comuns dessa funcionalidade.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Cenário 1: minimizando o número de prefixos IP do Office 365

A Contoso Corporation é uma empresa de 50.000 pessoas que atualmente usa o Office 365 para o Exchange Online e o SharePoint Online. Ao analisar os requisitos do ExpressRoute, a Contoso determina que seus dispositivos de rede em muitos locais regionais não podem lidar com tamanhos de tabela de roteamento acima de 100 entradas de rota adicionais. A Contoso analisou o número total de prefixos IP que o ExpressRoute anunciaria para o conjunto completo de serviços do Office 365 e concluiu que excede 100. Para permanecer sob as 100 entradas de rota adicionais, a Contoso escopos o uso do ExpressRoute para o Office 365 para apenas o valor da comunidade BGP do SharePoint Online, 12076:5020, recebido por meio do peering expressRoute Microsoft.

|**Marca de comunidade BGP usada**|**Tabela de funcionalidades sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive for Business  <br/> | Solicitações DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não são especificamente suportados pelo Azure ExpressRoute  <br/>  Todos os outros serviços de nuvem da Microsoft  <br/>  Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/>  Exchange Online, Proteção do Exchange Online e Skype for Business Online  <br/> |

> [!NOTE]
> Para obter contagens de prefixo menores para cada serviço, uma quantidade mínima de sobreposição entre os serviços persistirá. Esse é um comportamento esperado.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Cenário 2: Scoping ExpressRoute e uso de largura de banda interna para alguns serviços do Office 365

Fabrikam Inc, uma grande empresa multi-nacional com uma rede heterogênea distribuída, é assinante de muitos serviços do Office 365, incluindo; Exchange Online, SharePoint Online e Skype for Business Online. A infraestrutura de roteamento interna da Fabrikam pode manipular milhares de prefixos IP em suas tabelas de roteamento; no entanto, a Fabrikam só deseja provisionar o ExpressRoute e a largura de banda interna para aplicativos do Office 365 que são os mais sensíveis ao desempenho da rede e usam a largura de banda da Internet existente para todos os outros aplicativos do Office 365.
  
Por esse motivo, a Fabrikam escopos sua largura de banda do Azure ExpressRoute apenas para o valor de comunidade BGP do Skype for Business Online, 12076:5030, recebido por meio do peering expressRoute Microsoft. O tráfego de rede restante associado ao Office 365 continua a usar os pontos de saída da Internet.

|**Marca de comunidade BGP usada**|**Tabela de funcionalidades sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Sinalização SIP do Skype, downloads, voz, vídeo e compartilhamento de área de trabalho  <br/> | Solicitações DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não são especificamente suportados pelo Azure ExpressRoute  <br/>  Todos os outros serviços de nuvem da Microsoft  <br/>  Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/>  Telemetria do Skype for Business, dicas rápidas do cliente skype, conectividade pública de mensagens IM  <br/>  Exchange Online, Proteção do Exchange Online e SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Cenário 3: Scoping Azure ExpressRoute somente para serviços do Office 365

O Woodgrove Bank é cliente de vários serviços de nuvem da Microsoft, incluindo o Office 365. Depois de avaliar sua capacidade de rede e consumo, o Woodgrove Bank decide implantar o Azure ExpressRoute como o caminho preferencial para os serviços do Office 365 com suporte. As tabelas de roteamento podem suportar o conjunto completo de prefixos IP do Office 365 e os circuitos do Azure ExpressRoute que eles provisionam suportam todas as necessidades de largura de banda e latência projetadas.
  
Para garantir o tráfego de rede associado a serviços de nuvem da Microsoft que não seja o Office 365, o Woodgrove Bank tem como escopo o uso do ExpressRoute para o Office 365 para todos os prefixos IP marcados com valores de comunidade BGP específicos do Office 365, 12076:5010, 12076:5030, 12076:5100.

|**Marca de comunidade BGP usada**|**Tabela de funcionalidades sobre o Azure ExpressRoute**|**Rotas da Internet necessárias**|
|:-----|:-----|:-----|
|Exchange, Skype for Business & Microsoft Teams, SharePoint, &amp; outros serviços  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Proteção do Exchange Online &amp; do Exchange Online  <br/> SharePoint Online &amp; OneDrive for Business  <br/> Sinalização SIP do Skype, downloads, voz, vídeo e compartilhamento de área de trabalho  <br/> Portal do Office 365, autenticação do Office 365, &amp; Office em um navegador  <br/> | Solicitações DNS, CRL, &amp; CDN  <br/>  Todos os outros serviços do Office 365 não são especificamente suportados pelo Azure ExpressRoute  <br/>  Todos os outros serviços de nuvem da Microsoft  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Principais considerações de planejamento para o uso de comunidades BGP

Os clientes que optarem por tirar proveito das comunidades BGP para influenciar como o ExpressRoute é anunciado e propagado pela rede do cliente devem levar em consideração as seguintes considerações:
  
- Ao usar comunidades BGP em seu design de rede, é importante garantir que a simetria de rota ainda seja mantida. Em alguns casos, a adição ou remoção de comunidades BGP pode criar uma situação em que o roteamento simétrico é quebrado e sua configuração de roteamento deve ser atualizada para restabelecer o roteamento simétrico.

- O scoping do Azure ExpressRoute com valores de comunidade BGP é uma ação do cliente. A Microsoft anunciará todos os prefixos IP associados à relação de paridade, independentemente de qualquer escoriação configurada pelo cliente.

- O Azure ExpressRoute não dá suporte a nenhuma ação na rede da Microsoft com base nas comunidades BGP atribuídas ao cliente.

- Os prefixos IP usados pelo Office 365 são marcados apenas com valores de comunidade BGP específicos do serviço, não há suporte para comunidades BGP específicas de local. Os serviços do Office 365 são de natureza global, não há suporte para a filtragem de prefixos com base no local do locatário ou dos dados na nuvem do Office 365. A abordagem recomendada é configurar sua rede para coordenar o caminho de rede mais curto ou preferencial do local de rede do usuário para a rede global da Microsoft, independentemente da localização física do endereço IP do serviço do Office 365 que está solicitando.

- Os prefixos IP incluídos em cada valor de comunidade BGP representam uma sub-rede que contém endereços IP para o aplicativo do Office 365 associado ao valor. Em alguns casos, mais de um aplicativo do Office 365 tem endereços IP em uma sub-rede, resultando em um prefixo IP existente em mais de um valor de comunidade. Isso é esperado, embora raramente, comportamento devido à fragmentação de alocação e não afeta a contagem de prefixos ou as metas de gerenciamento de largura de banda. Os clientes são incentivados a usar a abordagem "permitir o que é necessário" em vez de "negar o que não é necessário" ao aproveitar as comunidades BGP para o Office 365 para minimizar o efeito.

- O uso de comunidades BGP não altera os requisitos de conectividade de rede ou a configuração subjacentes necessários para usar o Office 365. Os clientes que querem acessar o Office 365 ainda precisam acessar a Internet.

- O scoping do Azure ExpressRoute com comunidades BGP afeta apenas as rotas que sua rede interna pode ver na relação de paração da Microsoft. Talvez seja necessário fazer configurações adicionais no nível do aplicativo, como o uso de uma configuração pac ou WPAD em conjunto com o roteamento com escopo.

- Além de usar as comunidades BGP atribuídas pela Microsoft, os clientes podem optar por atribuir suas próprias comunidades BGP a prefixos IP do Office 365 aprendidos por meio do Azure ExpressRoute para influenciar o roteamento interno. Um caso de uso popular é atribuir uma comunidade BGP baseada em local a todas as rotas aprendidas por meio de cada local de paração ExpressRoute determinado e, em seguida, usar essas informações a jusante na rede do cliente para coordenar o caminho de rede mais curto ou preferencial para a rede da Microsoft. O uso de comunidades BGP atribuídas ao cliente com cenários do ExpressRoute para Office 365 está fora do escopo do controle ou visibilidade da Microsoft.

Aqui está um link curto que você pode usar para voltar: [https://aka.ms/bgpexpressroute365]() .
  
## <a name="related-topics"></a>Tópicos Relacionados

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Microsoft Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Como rotear com o ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Planejamento de rede com o ExpressRoute para Office 365](network-planning-with-expressroute.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute e QoS no Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Fluxo de chamadas usando o ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Como implementar o ExpressRoute para Office 365](implementing-expressroute.md)
  
[Suporte para comunidades BGP](/azure/expressroute/expressroute-routing)
  
[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute para Treinamento do Office 365](https://channel9.msdn.com/series/aer)