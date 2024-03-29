---
title: Aplicar um modelo de compreensão de documento em uma biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint
ms.openlocfilehash: 42168537c8d449a075b5e29ef9905b6b98b8d714
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925395"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Aplicar um modelo de compreensão de documento no Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Depois de publicar seu modelo de compreensão de documento, você pode aplicá-lo a uma ou mais bibliotecas de documentos do SharePoint no locatário do Microsoft 365.

> [!NOTE]
> Você só pode aplicar o modelo às bibliotecas de documentos às quais tem acesso.


## <a name="apply-your-model-to-a-document-library"></a>Aplique seu modelo a uma biblioteca de documentos.

Para aplicar o modelo a uma biblioteca de documentos do SharePoint:

1. Na página inicial do modelo, no bloco **Aplicar modelo a bibliotecas**, marque **Publicar modelo**. Ou você pode selecionar  **+Adicionar Biblioteca** na seção **Bibliotecas com esse modelo**. </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. Em seguida, você pode selecionar o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo. Se o site não for mostrado na lista, use a caixa de pesquisa para localizá-lo.</br>

    ![Selecionar um Site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Você deve ter permissões de *Gerenciar Lista* ou direitos de *Editar* na biblioteca de documentos para a qual você está aplicando o modelo.</br>

3. Depois de selecionar o site, selecione a biblioteca de documentos à qual você deseja aplicar o modelo. No exemplo, selecione a biblioteca de documentos do *Documento* do site de *Acompanhamento de Caso da Contoso*. </br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. Já que o modelo está associado a um tipo de conteúdo, quando for aplicado à biblioteca, ele adicionará o tipo de conteúdo e seu modo de exibição com as etiquetas extraídas mostradas como colunas. Esse modo de exibição é a exibição padrão da biblioteca por padrão, mas você pode optar por não ter essa exibição padrão selecionando **Configurações avançadas** e desmarcando **Definir esse novo modo de exibição como padrão**.</br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. Selecione **Adicionar** para aplicar o modelo à biblioteca. 
6. Na página inicial do modelo, na seção **Bibliotecas com esse modelo**, você deverá ver a URL do site do SharePoint listado.</br>

    ![Biblioteca selecionada](../media/content-understanding/selected-library.png)</br>

7. Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo. Observe que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem indicará que o modelo foi aplicado à biblioteca de documentos.

    ![Modo de exibição informações](../media/content-understanding/info-du.png)</br> 

    Você pode selecionar a opção **Exibir modelos ativos** para ver detalhes sobre todos os modelos aplicados à biblioteca de documentos.

8. No painel **Modelos ativos**, você pode ver os modelos aplicados à biblioteca de documentos. Selecione um modelo para ver mais detalhes sobre ele, como uma descrição do modelo, quem publicou o modelo e se ele aplica um rótulo de retenção aos arquivos que ele classifica.

    ![Painel Modelos ativos](../media/content-understanding/active-models.png)</br> 

Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.

O modelo identifica todos os arquivos com o tipo de conteúdo associado do modelo e os lista em seu modo de exibição. Se o modelo tiver os extratores, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Aplicar o modelo aos arquivos que já estão na biblioteca de documentos

Enquanto um modelo aplicado processa todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existem na biblioteca de documentos antes do modelo aplicado:

1. Na biblioteca de documentos, selecione os arquivos que você deseja processar por seu modelo.
2. Depois de selecionar seus arquivos, **Classificar e extrair** aparecerá na faixa de opções da biblioteca de documentos. Selecione **Classificar e extrair**.
3. Os arquivos selecionados serão adicionados à fila a ser processada.

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> Você pode copiar arquivos individuais para uma biblioteca e aplicá-los a um modelo, mas não a pastas.

### <a name="the-classification-date-field"></a>O campo Data de Classificação

Quando a compreensão de um documento do SharePoint Syntex ou um modelo de processamento de formulário é aplicado a uma biblioteca de documentos, um campo <b>Data de Classificação</b> é incluído no esquema de biblioteca. Por padrão, esse campo fica vazio, mas quando os documentos são processados e classificados por um modelo, esse campo é atualizado com um carimbo de data e hora de conclusão. 

   ![Coluna Data de Classificação](../media/content-understanding/class-date-column.png)</br> 

O campo Data de classificação é usado pelo [<b>Quando um arquivo é classificado por um modelo de compreensão de conteúdo</b> aciona o ](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) para executar um fluxo do Power Automate depois que um modelo de compreensão de conteúdo Syntex terminar de processar um arquivo e atualizar o campo "Data de classificação".

   ![Gatilho de fluxo](../media/content-understanding/trigger.png)</br>

O <b>Quando um arquivo é classificado por um modelo de compreensão de conteúdo</b> acionador pode ser usado para iniciar outro fluxo de trabalho usando qualquer informação extraída do arquivo.



## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).