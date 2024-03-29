---
title: Localizar seu registrador de domínio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a localizar seu registrador de domínios e seu provedor de hospedagem de DNS usando a pesquisa do InterNIC.
ms.openlocfilehash: 434e30709b112cf591159a1692540b8ef2b6bb65
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655537"
---
# <a name="find-your-domain-registrar"></a>Localizar seu registrador de domínio

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
## <a name="domain-registrar"></a>Registrador de domínios
  
### <a name="find-your-domain-name-registrar"></a>Localizar o registrador de nomes de domínio

>[!NOTE]
> Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.
  
1. Na [página de pesquisa do InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio. Por exemplo,  *contoso.com.* 
    
2. Selecione a opção **Domínio** e selecione **Enviar**.
    
3. Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará a organização que presta o serviço de registrador para o seu domínio. 
    
## <a name="dns-hosting-provider"></a>Provedor de hospedagem de DNS
  
### <a name="find-your-dns-hosting-provider"></a>Localizar o provedor de hospedagem de DNS

>[!NOTE]
> Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.
  
1. Na [página de pesquisa do InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio. Por exemplo, contoso.com. 
    
2. Selecione a opção **Domínio** e selecione **Enviar**.
    
3. Na página **Whois Search Results**, localize a primeira entrada em **Name Server**. 
    
4. Copie o NS (servidor de nomes) que aparece depois dos dois-pontos (:) e cole-o na caixa **Search**, na parte superior da página. Selecione **Nameserver** e depois selecione **Enviar**.
    
5. Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará o provedor de hospedagem de DNS, o provedor de DNS a que pertence o servidor de nomes do seu domínio. 
    
---

