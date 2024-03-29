---
title: Tabela AADSpnSignInEventsBeta no esquema de busca avançado
description: Saiba mais sobre informações associadas à Azure Active Directory de serviço e à tabela de eventos de login de identidade gerenciada do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, máquina, usuário, conta, identidade, AAD
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f74972bcd5d0ddaab58d82b72a55991fda44e3b1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583539"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**Aplica-se a:**

- Microsoft 365 Defender

>[!IMPORTANT]
> A tabela está atualmente em beta e está sendo oferecida em curto prazo para permitir que você cace a entidade de serviço Azure Active Directory (AAD) e os eventos de login de identidade `AADSpnSignInEventsBeta` gerenciada. Eventualmente, moveremos todas as informações de esquema de login para a `IdentityLogonEvents` tabela.



A tabela no esquema de busca avançado contém informações sobre Azure Active Directory entidade de serviço e logins de identidade `AADSpnSignInEventsBeta` gerenciada. Você pode saber mais sobre os diferentes tipos de logins em Azure Active Directory relatórios de atividade de login [- visualização](/azure/active-directory/reports-monitoring/concept-all-sign-ins).

Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference).





| Nome da coluna     | Tipo de dados | Descrição   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | Data e hora em que o registro foi gerado                                                                                                     |
| `Application`          | string        | Aplicativo que realizou a ação gravada                                                                                                   |
| `ApplicationId`        | cadeia de caracteres        | Identificador exclusivo do aplicativo                                                                                                           |
| `IsManagedIdentity`    | booliano       | Indica se a assinatura foi iniciada por uma identidade gerenciada                                                                               |
| `ErrorCode`            | int        | Contém o código de erro se ocorrer um erro de login. Para encontrar uma descrição de um código de erro específico, visite <https://aka.ms/AADsigninsErrorCodes> . |
| `CorrelationId`        | cadeia de caracteres        | Identificador exclusivo do evento de login                                                                                                          |
| `ServicePrincipalName` | cadeia de caracteres        | Nome da entidade de serviço que iniciou a login                                                                                        |
| `ServicePrincipalId`   | cadeia de caracteres        | Identificador exclusivo da entidade de serviço que iniciou a login                                                                           |
| `ResourceDisplayName`  | cadeia de caracteres        | Nome de exibição do recurso acessado                                                                                                           |
| `ResourceId`           | cadeia de caracteres        | Identificador exclusivo do recurso acessado                                                                                                      |
| `ResourceTenantId`     | cadeia de caracteres        | Identificador exclusivo do locatário do recurso acessado                                                                                        |
| `IPAddress`            | cadeia de caracteres        | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas                                                              |
| `Country`          | cadeia de caracteres        | Código de duas letras indicando o país onde o endereço IP do cliente está geolocado                                                                |
| `State`                | cadeia de caracteres        | Estado em que a login ocorreu, se disponível                                                                                                  |
| `City`                 | cadeia de caracteres        | Cidade onde o usuário da conta está localizado                                                                                                          |
| `Latitude`             | cadeia de caracteres        | As coordenadas norte a sul do local de login                                                                                          |
| `Longitude`            | cadeia de caracteres        | As coordenadas de leste a oeste do local de login                                                                                            |
| `RequestId`            | cadeia de caracteres        | Identificador exclusivo da solicitação                                                                                                                |
|`ReportId` | cadeia de caracteres | Identificador exclusivo do evento | 

 

## <a name="related-articles"></a>Artigos relacionados

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [Visão geral da busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [Aprender a linguagem de consulta](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [Compreender o esquema](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)