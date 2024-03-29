---
title: Gerenciamento de registros no Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Com o gerenciamento de registros no Microsoft 365, você pode aplicar seus agendamentos de retenção em um plano de arquivo que gerencia a retenção, a declaração e a disposição dos registros.
ms.openlocfilehash: 853303dcaffcbacfcf805b8617b836254cf31ad8
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245427"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Saiba mais sobre gerenciamento de registros no Microsoft 365

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Organizações de todos os tipos exigem uma solução de gerenciamento de registros para gerenciar registros regulatórios, jurídicos e comerciais em seus dados corporativos O gerenciamento de registros no Microsoft 365 ajuda a sua organização a gerenciar suas obrigações legais, oferecer a capacidade de demonstrar a conformidade com as regulamentações e aumentar a eficiência com o descarte regular de itens que não precisam mais ser mantidos, não são mais importantes ou obrigatórios para fins comerciais.

Use os seguintes recursos para dar suporte à sua solução de gerenciamento de registros no Microsoft 365:

- **Conteúdo do rótulo como um registro**. Crie e configure os rótulos de retenção para marcar o conteúdo como um [registro](#records) que poderá ser aplicado pelos usuários ou aplicado automaticamente pela identificação de informações confidenciais, palavras-chave ou tipos de conteúdo.

- **Migre e gerencie seus requisitos de retenção com um planejamento de arquivo**. Usando um [plano de arquivo](file-plan-manager.md), é possível introduzir um plano de retenção existente no Microsoft 365 ou criar um novo para os recursos de gerenciamento aprimorados.

- **Defina as configurações de retenção e exclusão com rótulos de retenção**. Configure [rótulos de retenção](retention.md#retention-labels) com as ações e os períodos de retenção com base em vários fatores que incluem a data da última modificação ou criação.

- **Iniciar períodos de retenção diferentes quando um evento ocorrer** com [retenção baseada em eventos](event-driven-retention.md).

- **Examine e valide o descarte** com [revisões de descarte](disposition.md#disposition-reviews) e a prova de [exclusão de registros](disposition.md#disposition-of-records).

- **Exportar informações sobre todos os itens descartados** com a [opção exportar](disposition.md#filter-and-export-the-views).

- **Defina permissões** específicas para as funções do Gerenciador de registros em [sua organização para que](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)ele tenha o acesso certo.

Usando esses recursos, você pode incorporar os cronogramas e os requisitos de retenção da sua organização em uma solução de gerenciamento de registros que gerencie a retenção, a declaração de registros e o descarte, para dar suporte a todo o ciclo de vida do seu conteúdo.

Além da documentação online, você pode achar útil ouvir a [gravação do webinar](https://aka.ms/MIPC/Video-RecordsManagementWebinar) sobre o gerenciamento de registros e baixar o [conjunto que acompanha as perguntas frequentes](https://aka.ms/MIPC/Blog-RecordsManagementWebinar).

## <a name="records"></a>Registros

Quando o conteúdo for declarado como um registro:

- Restrições são colocadas nos itens em termos de quais [ações são permitidas ou bloqueadas](#compare-restrictions-for-what-actions-are-allowed-or-blocked).

- Atividades adicionais sobre o item são registradas.

- Você tem prova de disposição quando os itens são excluídos no final do período de retenção.

Use os [rótulos de retenção](retention.md#retention-labels) para marcar o conteúdo como um **registro** ou um **registro regulatório**. A diferença entre esses dois são explicadas na próxima seção. Você pode publicar esses rótulos para que os usuários e administradores possam aplicá-los manualmente ao conteúdo ou aplicar automaticamente esses rótulos ao conteúdo que você deseja marcar como um registro ou um registro regulatório.

Usando rótulos de retenção para declarar registros, você pode implementar uma estratégia única e consistente para o gerenciamento de registros em seu ambiente Microsoft 365.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Comparar restrições para quais ações são permitidas ou bloqueadas

Use a tabela a seguir para identificar quais restrições são colocadas no conteúdo como resultado da aplicação de um rótulo de retenção padrão e de rótulos de retenção que marcam o conteúdo como registro regulatório ou registro. 

Um rótulo de retenção padrão tem configurações de retenção e ações, mas não marca o conteúdo como um registro ou um registro regulatório.

>[!NOTE] 
> Para garantir a integridade, a tabela inclui colunas para um registro bloqueado e desbloqueado, aplicável ao SharePoint e OneDrive, mas não ao Exchange. A capacidade de bloquear e desbloquear um registro usa o [controle de versão do registro](record-versioning.md) que não tem suporte para itens do Exchange. Portanto, para todos os itens do Exchange marcados como registro, o comportamento é mapeado para a coluna **Registro - bloqueado** e a coluna **Registro - desbloqueado** não é relevante.


|Action| Rótulo de retenção |Registro - bloqueado| Registro - desbloqueado| Registro regulatório |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Editar conteúdo|Permitido | **Bloqueado** | Permitido | **Bloqueado**|
|Editar propriedades, incluindo renomear|Permitido |Permitido | Permitido| **Bloqueado**|
|Excluir|Permitido <sup>1</sup> |**Bloqueado** |**Bloqueado**| **Bloqueado**|
|Copiar|Permitido |Permitido | Permitido| Permitido|
|Mover dentro do contêiner <sup>2</sup>|Permitido |Permitido | Permitido| Permitido|
|Mover entre contêineres <sup>2</sup>|Permitido |Permitido se nunca desbloqueado | **Bloqueado** | **Bloqueado**|
|Abrir/Ler|Permitido |Permitido | Permitido| Permitido|
|Alterar rótulo|Permitido |Permitido - somente administrador do contêiner | Permitido - somente administrador do contêiner| **Bloqueado**
|Remover rótulo|Permitido |Permitido - somente administrador do contêiner | Permitido - somente administrador do contêiner| **Bloqueado**

Notas de rodapé:

<sup>1</sup> Com suporte do OneDrive e Exchange, mantendo uma cópia em um local seguro, mas bloqueado pelo SharePoint.

Quando você aplica um rótulo de retenção a um item de lista que tem um anexo de documento, esse documento não herda as configurações de retenção e pode ser excluído do item da lista. Em comparação, se esse item da lista fosse declarado um registro com um rótulo de retenção, o anexo do documento herdaria as configurações de retenção e não poderia ser excluído. 

<sup>2</sup> Os contêineres incluem bibliotecas de documentos do SharePoint, contas do OneDrive e caixas de correio do Exchange.

>[!IMPORTANT] 
> A diferença mais importante para um registro regulatório é que depois que ele é aplicado ao conteúdo, ninguém, nem mesmo um administrador global, pode remover o rótulo. 
>
> Rótulos de retenção configurados para registros regulatórios também têm as seguintes restrições de administrador:
> - Não é possível tornar o período de retenção mais curto depois que o rótulo é salvo, somente estendido.
> - Esses rótulos não têm suporte por políticas de rotulamento automático e devem ser aplicados usando [políticas de rótulo de retenção](create-apply-retention-labels.md). 
>
> Além disso, uma etiqueta regulamentar não pode ser aplicada a um documento que foi retirado no Microsoft Office SharePoint Online.
> 
> Por causa das restrições e ações irreversíveis, certifique-se de que realmente precisa usar registros regulatórios antes de selecionar esta opção para seus rótulos de retenção. Para ajudar a evitar a configuração acidental, essa opção não está disponível por padrão, mas deve ser habilitada primeiro usando o Windows PowerShell. As instruções estão incluídas no [Declarar registros usando os rótulos de retenção](declare-records.md).

## <a name="configuration-guidance"></a>Instruções de configuração

Confira [introdução ao gerenciamento de registros](get-started-with-records-management.md). Este artigo tem informações sobre assinaturas, permissões e links para orientações de configuração de ponta a ponta para cenários de gerenciamento de registros.