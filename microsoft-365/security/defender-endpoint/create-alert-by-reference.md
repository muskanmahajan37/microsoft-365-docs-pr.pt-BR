---
title: Criar alerta a partir da API de evento
description: Saiba como usar a API Criar alerta para criar um novo Alerta em cima do Evento no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, alerta, informações, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166296"
---
# <a name="create-alert-api"></a>Criar API de alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>Descrição da API
Cria um [novo Alerta](alerts.md) em cima do **evento**.
<br>**O Evento Do Microsoft Defender para Ponto** de Extremidade é necessário para a criação do alerta.
<br>Você precisará fornecer 3 parâmetros do Evento na solicitação: Hora do Evento, **ID do** Computador e **ID do Relatório.** Veja o exemplo a seguir.
<br>Você pode usar um evento encontrado na API de Busca Avançada ou portal.
<br>Se houver um alerta aberto no mesmo Dispositivo com o mesmo Título, o novo alerta criado será mesclado com ele.
<br>Uma investigação automática é iniciada automaticamente em alertas criados por meio da API.


## <a name="limitations"></a>Limitações
1. Limitações de taxa para essa API são 15 chamadas por minuto.


## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)

Tipo de permissão |   Permissão  |   Nome de exibição de permissão
:---|:---|:---
Aplicativo |   Alerts.ReadWrite.All |  'Ler e gravar todos os alertas'
Delegada (conta corporativa ou de estudante) | Alert.ReadWrite | 'Alertas de leitura e gravação'

>[!Note]
> Ao obter um token usando credenciais de usuário:
>- O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)
>- O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)

## <a name="http-request"></a>Solicitação HTTP

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

Nome | Tipo | Descrição
:---|:---|:---
Autorização | Cadeia de caracteres | Portador {token}. **Obrigatório**.
Content-Type | Cadeia de Caracteres | application/json. **Obrigatório**.

## <a name="request-body"></a>Corpo da solicitação

No corpo da solicitação, fornece os seguintes valores (todos são necessários):

Propriedade | Tipo | Descrição
:---|:---|:---
eventTime | DateTime(UTC) | O tempo preciso do evento como cadeia de caracteres, conforme obtido da busca avançada. por exemplo, ```2018-08-03T16:45:21.7115183Z``` **obrigatório.**
reportId | Cadeia de caracteres | O reportId do evento, conforme obtido da busca avançada. **Obrigatório**.
machineId | Cadeia de caracteres | ID do dispositivo no qual o evento foi identificado. **Obrigatório**.
severity | Cadeia de caracteres | Gravidade do alerta. Os valores da propriedade são: 'Low', 'Medium' e 'High'. **Obrigatório**.
title | Cadeia de caracteres | Título do alerta. **Obrigatório**.
descrição | Cadeia de caracteres | Descrição do alerta. **Obrigatório**.
recommendedAction| Cadeia de caracteres | Ação recomendada pelo agente de segurança ao analisar o alerta. **Obrigatório**.
category| Cadeia de caracteres | Categoria do alerta. Os valores da propriedade são: "Geral", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltração", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistência", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200 OK e um novo objeto [de](alerts.md) alerta no corpo da resposta. Se o evento com as propriedades especificadas (_reportId,_ _eventTime_ e _machineId_) não for encontrado - 404 Não Encontrado.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
