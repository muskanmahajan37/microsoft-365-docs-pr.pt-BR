---
title: Conexão do Microsoft Defender para APIs de Ponto de Extremidade com o Power BI
ms.reviewer: ''
description: Crie um relatório do Power Business Intelligence (BI) em cima das APIs do Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, Power BI, relatórios
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
ms.openlocfilehash: 7c99267d75c89b3484d207cd763131e4bcc91527
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935036"
---
# <a name="create-custom-reports-using-power-bi"></a>Criar relatórios personalizados usando o Power BI

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Nesta seção, você aprenderá a criar um relatório do Power BI em cima das APIs do Defender para Ponto de Extremidade.

O primeiro exemplo demonstra como conectar o Power BI à API de Busca Avançada e o segundo exemplo demonstra uma conexão com nossas APIs OData, como Ações do Computador ou Alertas.

## <a name="connect-power-bi-to-advanced-hunting-api"></a>Conectar o Power BI à API de Busca Avançada

- Abrir o Microsoft Power BI

- Clique **em Obter consulta em** branco de  >  **dados**

    ![Imagem de criar consulta em branco](images/power-bi-create-blank-query.png)

- Clique **em Editor Avançado**

    ![Imagem do editor avançado aberto](images/power-bi-open-advanced-editor.png)

- Copie o abaixo e a colar no editor:

```
    let 
        AdvancedHuntingQuery = "DeviceEvents | where ActionType contains 'Anti' | limit 20",

        HuntingUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries",

        Response = Json.Document(Web.Contents(HuntingUrl, [Query=[key=AdvancedHuntingQuery]])),

        TypeMap = #table(
            { "Type", "PowerBiType" },
            {
                { "Double",   Double.Type },
                { "Int64",    Int64.Type },
                { "Int32",    Int32.Type },
                { "Int16",    Int16.Type },
                { "UInt64",   Number.Type },
                { "UInt32",   Number.Type },
                { "UInt16",   Number.Type },
                { "Byte",     Byte.Type },
                { "Single",   Single.Type },
                { "Decimal",  Decimal.Type },
                { "TimeSpan", Duration.Type },
                { "DateTime", DateTimeZone.Type },
                { "String",   Text.Type },
                { "Boolean",  Logical.Type },
                { "SByte",    Logical.Type },
                { "Guid",     Text.Type }
            }),

        Schema = Table.FromRecords(Response[Schema]),
        TypedSchema = Table.Join(Table.SelectColumns(Schema, {"Name", "Type"}), {"Type"}, TypeMap , {"Type"}),
        Results = Response[Results],
        Rows = Table.FromRecords(Results, Schema[Name]),
        Table = Table.TransformColumnTypes(Rows, Table.ToList(TypedSchema, (c) => {c{0}, c{2}}))

    in Table

```

- Clique **em Feito**

- Clique **em Editar Credenciais**

    ![Imagem de credenciais de edição0](images/power-bi-edit-credentials.png)

- Selecione **Entrar na conta**  >  **organizacional**

    ![Imagem de credenciais definidas1](images/power-bi-set-credentials-organizational.png)

- Insira suas credenciais e aguarde para entrar

- Clique **em Conectar**

    ![Imagem de credenciais definidas2](images/power-bi-set-credentials-organizational-cont.png)

- Agora, os resultados de sua consulta serão exibidos como tabela e você pode começar a criar visualizações em cima dela!

- Você pode duplicar essa tabela, renomeá-la e editar a consulta De Busca Avançada dentro para obter todos os dados que você gostaria.

## <a name="connect-power-bi-to-odata-apis"></a>Conectar o Power BI às APIs OData

- A única diferença do exemplo acima é a consulta dentro do editor. 

- Copie o abaixo e a colar no editor para puxar todas as **Ações do Computador** de sua organização:

```
    let

        Query = "MachineActions",

        Source = OData.Feed("https://api.securitycenter.microsoft.com/api/" & Query, null, [Implementation="2.0", MoreColumns=true])
    in
        Source

```

- Você pode fazer o mesmo para **Alertas** e **Máquinas.**

- Você também pode usar consultas OData para filtros de consultas, consulte [Using OData Queries](exposed-apis-odata-samples.md)


## <a name="power-bi-dashboard-samples-in-github"></a>Exemplos de painel do Power BI no GitHub
Para obter mais informações, consulte os [modelos de relatório do Power BI.](https://github.com/microsoft/MicrosoftDefenderATP-PowerBI)

## <a name="sample-reports"></a>Relatórios de exemplo
Exibir os exemplos de relatório do Microsoft Defender for Endpoint Power BI. Para obter mais informações, consulte [Procurar exemplos de código](https://docs.microsoft.com/samples/browse/?products=mdatp).


## <a name="related-topic"></a>Tópicos relacionados
- [Defender para APIs de Ponto de Extremidade](apis-intro.md)
- [API de Busca Avançada](run-advanced-query-api.md)
- [Usar consultas de OData](exposed-apis-odata-samples.md)
