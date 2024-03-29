---
title: Desativar a sincronização de diretórios do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: Neste artigo, encontre informações sobre como usar o PowerShell para desativar a sincronização de diretórios do Microsoft 365.
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445703"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Desativar a sincronização de diretórios do Microsoft 365
Você pode usar o PowerShell para desativar a sincronização de diretórios e converter seus usuários sincronizados em somente nuvem. No entanto, não é recomendável desativar a sincronização de diretório como uma etapa de solução de problemas. Se você precisar de ajuda para solucionar problemas de sincronização de diretório, consulte o artigo Corrigir problemas com a sincronização de diretórios do [Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[Contate o suporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) para produtos comerciais, se necessário.
  
## <a name="turn-off-directory-synchronization"></a>Desativar a sincronização de diretórios  
Para desativar a sincronização de diretório:
  
1. Primeiro, instale o software necessário e conecte-se à sua assinatura do Microsoft 365. Para obter instruções, [consulte Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Use [Set-MsolDirSyncEnabled para](/previous-versions/azure/dn194097(v=azure.100)) desabilitar a sincronização de diretório: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Se você usar esse comando, deverá aguardar 72 horas para poder ativar novamente a sincronização de diretórios.
>
