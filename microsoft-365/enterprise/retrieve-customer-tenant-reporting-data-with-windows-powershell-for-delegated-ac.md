---
title: Recuperar dados de relatório de locatários do cliente com Windows PowerShell para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Resumo: use o Windows PowerShell remoto para Microsoft Exchange Online para recuperar os relatórios de locatários individuais do cliente.'
ms.openlocfilehash: 8ea5f9834bfcc0d517fc1e0938c3547d88d1d8a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927211"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Recuperar dados de relatório do locatário do cliente com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Use o Windows PowerShell remoto para Microsoft Exchange Online para recuperar relatórios de locatários de clientes individuais.
  
Os parceiros do Provedor de Soluções na Nuvem (CSP) podem acessar os dados que comem os relatórios de locatários do cliente diretamente por meio de Windows PowerShell para o PowerShell do Exchange Online. Isso permite aos parceiros coletar e salvar os dados dos relatórios e, em seguida, realizar outras operações neles. Depois de abrir uma conexão remota, recuperar dados de relatório de uma locação é o mesmo que executar qualquer cmdlet em uma locação do cliente.
  
Neste artigo, você usa o Windows PowerShell remoto para o Exchange Online para se conectar a um único cliente e recuperar um relatório. Por padrão, o Windows PowerShell não tem suporte para agregar dados de relatórios de várias locações do cliente. Os relatórios que você recuperar com esse procedimento são destinados apenas ao  _DelegatedOrg_ para o qual você se conectar.
  
 
## <a name="before-you-begin"></a>Antes de começar

- Você deve se conectar ao seu locatário do Exchange Online usando o Windows PowerShell remoto. Para obter instruções, confira [Conectar-se aos locatários do Exchange Online com o Windows PowerShell remoto para parceiros com permissões de acesso delegado (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)
    
## <a name="run-the-get-stalemailboxreport-sample"></a>Executar a amostra do Get-StaleMailboxReport

Após abrir uma sessão remota do Exchange Online, execute este comando para recuperar o **Get-StaleMailboxReport** para o intervalo de datas de 25/03/2015 a 31/03/2015.
  
```
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Há vários outros cmdlets de relatório disponíveis para o Exchange Online, para o Lync Online e para o SharePoint Online, dentre outros, que você pode usar para rastreamento de mensagens. Para saber mais sobre os cmdlets de relatórios disponíveis e sobre o Serviço Web de Relatório do Office 365, confira os tópicos da seção a seguir.
  
## <a name="see-also"></a>Confira também

#### 

[Serviço Web de Relatório do Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))
  
[Cmdlets de criação de relatórios no Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)
  
[Ajuda para parceiros](https://go.microsoft.com/fwlink/p/?LinkID=533477)