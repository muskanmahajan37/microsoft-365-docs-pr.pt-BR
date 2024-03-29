---
title: Obter uma atividade de correção por ID
description: Retorna informações para a atividade de correção especificada.
keywords: apis, correção, api de correção, obter, tarefas de correção, correção por ID,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e0f68e8a28b302f0ae1ca06a2f892fea38a219b2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244438"
---
# <a name="get-one-remediation-activity-by-id"></a>Obter uma atividade de correção por ID

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API

Retorna informações para a atividade de correção especificada. Apresenta as mesmas colunas que Obter todas as atividades [de correção](get-remediation-all-activities.md)", mas retorna resultados apenas para a atividade de _correção especificada_.

[Saiba mais sobre atividades de correção.](tvm-remediation.md)

## <a name="list-a-specified-remediation-activity-for-id"></a>Listar uma atividade de correção especificada para (id)

**URL:** GET: /api/remediationTasks/id \{\}

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
:---|:---|:---
Aplicativo | RemediationTask.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegada (conta corporativa ou de estudante) | RemediationTask.Read.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

## <a name="properties"></a>Propriedades

Propriedade (id) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
category | Cadeia de caracteres | Categoria da atividade de correção (Configuração de software/segurança) | Software
completerEmail | Cadeia de caracteres | Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails | null
completerId | Cadeia de caracteres | Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto | null
completionMethod | Cadeia de caracteres | Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída" | Automático
createdOn | DateTime | Hora em que essa atividade de correção foi criada | 2021-01-12T18:54:11.5499478Z
description | Cadeia de caracteres | Descrição dessa atividade de correção | Atualize o Microsoft Silverlight para uma versão posterior para atenuar vulnerabilidades conhecidas que afetam seus dispositivos.
dueOn | DateTime | Data de vencimento do conjunto de criadores para essa atividade de correção | 2021-01-13T00:00:00Z
fixedDevices |  | O número de dispositivos que foram corrigidos | 2
id | Cadeia de caracteres | ID dessa atividade de correção | 097d9735-5479-4899-b1b7-77398899df92
nameId | Cadeia de caracteres | Nome do produto relacionado | Microsoft Silverlight
prioridade | Cadeia de caracteres | Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low) | Alto
productId | Cadeia de caracteres | ID do produto relacionado | microsoft-_-silverlight
productivityImpactRemediationType | Cadeia de caracteres | Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário. Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário". | AllExposedAssets
rbacGroupNames | Cadeia de caracteres | Nomes de grupo de dispositivos relacionados | [ "Windows Servidores", "Windows 10" ]
recommendedProgram | Cadeia de caracteres | Programa recomendado para atualizar para | null
recommendedVendor | Cadeia de caracteres | Fornecedor recomendado para atualizar para | null
recommendedVersion | Cadeia de caracteres | Versão recomendada para atualização/atualização para | null
relatedComponent | Cadeia de caracteres | Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança) | Microsoft Microsoft Silverlight
requesterEmail | Cadeia de caracteres | Endereço de email do criador | globaladmin@UserName.contoso.com
requesterId | Cadeia de caracteres | ID do objeto Creator | r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes | Cadeia de caracteres | As anotações (texto livre) que o criador adicionou para essa atividade de correção | null
scid | Cadeia de caracteres | SCID da recomendação de segurança relacionada | null
status | Cadeia de caracteres | Status da atividade de correção (Ativo/Concluído) | Ativo
statusLastModifiedOn | DateTime | Data em que o campo de status foi atualizado | 2021-01-12T18:54:11.5499487Z
targetDevices | Longo | Número de dispositivos expostos a que essa correção é aplicável | 43
title | Cadeia de caracteres | Título dessa atividade de correção | Microsoft Silverlight
tipo | Cadeia de caracteres | Tipo de correção | Atualizar
vendorId | Cadeia de caracteres | Nome do fornecedor relacionado | Microsoft

## <a name="example"></a>Exemplo

### <a name="request-example"></a>Exemplo de solicitação

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>Exemplo de resposta

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>Confira também

- [Métodos e propriedades de correção](get-remediation-methods-properties.md)

- [Listar todas as atividades de correção](get-remediation-all-activities.md)

- [Listar dispositivos expostos de uma atividade de correção](get-remediation-exposed-devices-activities.md)

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
