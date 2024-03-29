---
title: Adicionar dados de um conjunto de revisão a outro conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como selecionar documentos de um conjunto de revisão e trabalhar com eles individualmente em outro conjunto em um caso de Descoberta Avançada.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285175"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Adicionar dados a um conjunto de revisão de outro conjunto de revisão

Em alguns casos, pode ser necessário selecionar documentos de um conjunto de revisão e trabalhar com eles individualmente em outro conjunto de revisão. Isso é especialmente útil se você tiver definido o conteúdo em um conjunto de revisão e quiser executar análises no subconjunto de dados.

Siga o fluxo de trabalho neste artigo para adicionar conteúdo de um conjunto de revisão para outro.

## <a name="create-a-review-set"></a>Criar um conjunto de revisão

Antes de começar, você precisará criar um conjunto de revisão para adicionar os dados.  Um novo conjunto de revisão pode ser adicionado na guia **Conjuntos de** revisão da ocorrência. Para obter mais informações, consulte [Criar um conjunto de revisão.](managing-review-sets.md#create-a-review-set)

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Etapa 1: identificar o conteúdo a ser acrescentado a outro conjunto de revisão

Você pode adicionar conteúdo de um conjunto de revisão a outro selecionando documentos específicos no conjunto de revisão de origem ou selecionando todos os itens retornados pela consulta do conjunto de revisão. Se você estiver adicionando itens selecionados, selecione os itens, selecione **Ação** e, em seguida, **selecione Adicionar a outro conjunto de revisão.**

![Adicionar a outro conjunto de revisão no menu Ação](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Etapa 2: Especificar opções para adicionar a outro conjunto de revisão

In the **Add to another review set options** flyout page, choose the review set you want to add the items to. Escolha se adicionará Todos **os resultados da pesquisa ou** itens **selecionados.**   Informações adicionais fornece opções para incluir todos os metadados dos  itens e se devem ser incluídos as marcas (marcando a caixa de seleção Rótulos) no conjunto de revisão de origem quando os documentos são adicionados ao novo conjunto de revisão.  

![Opções para adicionar dados a outro conjunto de revisão](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Depois de clicar **em Ok,** um novo trabalho **(chamado** Adicionar dados a outro conjunto de revisão) é criado para adicionar o conteúdo a outro conjunto de revisão. Você pode ir para a **guia Trabalhos** e monitorar o progresso desse trabalho. Para obter mais informações, consulte [Gerenciar trabalhos.](managing-jobs-ediscovery20.md)
