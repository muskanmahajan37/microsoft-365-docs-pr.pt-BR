---
title: Preparar a implantação do cliente do Office pelo Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Saiba como instalar automaticamente os aplicativos do Office de 32 bits em computadores Windows 10 e mantê-los atualizados.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580045"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Preparar a implantação do cliente do Office pelo Microsoft 365 para empresas

Este artigo se aplica ao Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Preparar-se para instala automaticamente os aplicativos do Office em computadores de clientes

Você pode usar o Microsoft 365 Business Premium para instalar automaticamente os aplicativos do Office de 32 bits em computadores Windows 10 e mantê-los atualizados com atualizações.
  
A instalação automática funciona melhor se o computador do usuário final estiver no Windows 10 Business e:
  
- Não tiver aplicativos de área de trabalho do Office existentes (por exemplo, Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access e OneDrive).
    
    ou
    
- Tiver instalada uma versão Clique para Executar do Office.
    
Para determinar se você tem a versão Clique para Executar do Office, em qualquer aplicativo do Office, vá para **Arquivo** \> **Conta** ( **Conta do Office**). Se você vir **Atualizações do Office** conforme mostrado na figura a seguir, a instalação foi feita usando Clique para Executar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quem se beneficia de ter esse recurso**
  
O usuário final cujo PC:
  
- **Tem**  uma licença de usuário do Windows 10 Business, uma licença ativa do Microsoft 365 para empresas, Windows 10 Creators Update e está ingressada no Azure Active Directory. 
    
- **Não tem aplicativos** do Office de 64 bits (exemplo: Word, Excel, PowerPoint). Se os aplicativos do Office de 64 bits são necessários, esse recurso não é um bom ajuste porque não há suporte para acionar uma versão Clique para Executar do Office de 64 bits do Office no console de administração do Microsoft 365 para empresas. 
    
- **Não tem** aplicativos autônomos do 2016 Windows Installer (MSI) (por exemplo, Visio ou Project). O Microsoft 365 for business atualiza o Office para a versão Clique para Executar do Office 2016 e isso não funciona com aplicativos autônomos do Office 2016 MSI. 
    
A tabela a seguir mostra qual ação os usuários/administradores finais podem precisar executar, dependendo do estado inicial, para ter uma versão clique para executar bem-sucedida de 32 bits da implantação do Office a partir do console de administração do Microsoft 365 para empresas.
  
|**Status inicial de instalação do Office**|**Ação a ser tomada antes da instalação do Microsoft 365 para empresas do Office**|**Estado final**|
|:-----|:-----|:-----|
|Nenhum pacote do Office instalado  <br/> |Nenhuma  <br/> |O Office 2016 de 32 bits é instalado usando Clique para Executar  <br/> |
|Versão Clique para Executar de 32 bits do Office (2016 ou anterior) existente e nenhum aplicativo autônomo  <br/> |Nenhuma  <br/> |Atualizar para a versão Clique para Executar de 32 bits mais recente do Office 2016, conforme necessário **\*** <br/> |
|Versão de 32 bits clique para executar existente do Office e clique para executar aplicativos do Office autônomos de 32 ou 64 bits (por exemplo, Visio, Project)  <br/> |Nenhum  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> |
|Versão Clique para Executar de 32 bits do Office e qualquer aplicativo autônomo do Office MSI de 32 bits ou 64 bits (exceto 2016)  <br/> |Nenhuma  <br/> |Aplicativos autônomos não são afetados. O pacote é atualizado para a versão Clique para Executar de 32 bits do Office 2016  <br/> ||||
|Qualquer versão Clique para Executar de 64 bits do Office  <br/> |Desinstale os aplicativos do Office de 64 bits, se estiver tudo bem para substituí-los por aplicativos do Office de 32 bits  <br/> |Se os aplicativos do Office de 64 bits forem removidos, a versão Clique para Executar de 32 bits do Office 2016 será instalada  <br/> |
|Uma instalação MSI existente do Office 2016 com ou sem aplicativos autônomos  <br/> |Desinstale o MSI Office 2016.  <br/> |A versão Clique para Executar de 32 bits do Office 2016 está instalada. Nenhuma alteração nos aplicativos autônomos  <br/> |
|Instalação MSI existente do Office 2013 (ou anterior) e/ou aplicativos autônomos do Office  <br/> |Nenhuma  <br/> |A versão Clique para Executar de 32 bits do Office 2016 com a instalação do MSI Office preexistente (e aplicativos autônomos) funcionam lado a lado  <br/> |
||||
   
 **(\*) Observação:** A atualização para a versão Clique para Executar de 32 bits do Office 2016 não é instalada devido a um bug conhecido. Uma correção está em andamento. 
  
