---
title: Correção de erros durante o processamento de dados
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
description: Saiba como usar a correção de erros para corrigir problemas de dados na Descoberta eDiscoveria Avançada que podem impedir o processamento adequado do conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2067831a85e3b3a506917fac5b93acfa0b174db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906979"
---
# <a name="error-remediation-when-processing-data"></a>Correção de erros durante o processamento de dados

A correção de erros permite que os administradores de Descobertas Técnicas a capacidade de corrigir problemas de dados que impeçam a Descoberta Avançada de processar corretamente o conteúdo. Por exemplo, os arquivos protegidos por senha não podem ser processados, pois os arquivos são bloqueados ou criptografados. Usando a correção de erros, os administradores de Descobertas Digitais podem baixar arquivos com esses erros, remover a proteção de senha e carregar os arquivos remediados.

Use o fluxo de trabalho a seguir para corrigir arquivos com erros em casos de Descoberta Avançada.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Criar uma sessão de correção de erros para corrigir arquivos com erros de processamento

>[!NOTE]
>Se o assistente de correção de erro estiver fechado a qualquer momento durante o procedimento  a seguir, você poderá  retornar à sessão de correção de erros na guia Processamento selecionando **Correções** no menu suspenso Exibir.

1. Na guia **Processamento** no caso Descoberta Avançada, selecione Erros  no menu suspenso Exibir e selecione um conjunto de  revisão ou todo o caso no menu suspenso Escopo.  Esta seção exibe todos os erros do caso ou erro de um conjunto de revisão específico.

   ![Correção de erros](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Selecione os erros que você deseja corrigir clicando no botão de opção ao lado do tipo de erro ou do tipo de arquivo.  No exemplo a seguir, estamos remediando um arquivo protegido por senha.

3. Clique **em Nova correção de erro**.

    O fluxo de trabalho de correção de erros começa com um estágio de preparação em que os arquivos com erros são copiados para um local de Armazenamento do Azure fornecido pela Microsoft para que você possa baixá-los no computador local para corrigir.

    ![Preparando a correção de erros](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Depois que a preparação for concluída, clique em **Avançar: Baixar arquivos** para continuar com o download.

    ![Baixar arquivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para baixar arquivos, especifique o **caminho de destino para download**. Este é um caminho para a pasta pai em seu computador local onde o arquivo será baixado.  O caminho padrão, %USERPROFILE%\Downloads\errors, aponta para a pasta de downloads do usuário conectado. Você pode alterar esse caminho, se desejado. Se você alterá-lo, recomendamos que você use um caminho de arquivo local para o melhor desempenho. Não use um caminho de rede remoto. Por exemplo, você pode usar o caminho **C:\Remediation**. 

   O caminho para a pasta pai é adicionado automaticamente ao comando AzCopy (como o valor do **parâmetro /Dest).**

6. Copie o comando predefinido clicando em **Copiar para área de transferência**. Abra um Prompt de Comando do Windows, cole o comando do AzCopy e pressione **Enter**.  

    ![Preparar para correção de erros](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > Você deve usar o AzCopy v8.1 para usar com êxito o comando fornecido na página **Baixar arquivos.** Você também deve usar o AzCopy v8.1 para carregar os arquivos na etapa 10. Para instalar essa versão do AzCopy, consulte [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy). Se o comando AzCopy fornecido falhar, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

    Os arquivos selecionados são baixados para o local especificado na etapa 5. Na pasta pai (por exemplo, **C:\Remediation**), a seguinte estrutura de subpasta é criada automaticamente:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *A subpasta 1* é nomeada com a ID do caso ou do conjunto de revisão, dependendo do escopo selecionado na etapa 1.

    - *A Subpasta 2* é nomeada com a ID de arquivo do arquivo baixado

    - O arquivo baixado está localizado na *Subpasta 2* e também é nomeado com a ID do arquivo.

    Veja um exemplo do caminho da pasta e o nome do arquivo de erro criado quando os itens são baixados para a pasta pai **C:\Remediation:**

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Se vários arquivos são baixados, cada um é baixado para uma subpasta chamada com a ID do arquivo.

    > [!IMPORTANT]
    > Quando você carrega arquivos nas etapas 9 e 10, os arquivos remediados devem ter o mesmo nome de arquivo e estar localizados na mesma estrutura de subpastas. A subpasta e os nomes de arquivo são usados para associar o arquivo remediado ao arquivo de erro original. Se a estrutura de pastas ou nomes de arquivo são alterados, você receberá o seguinte erro: `Cannot apply Error Remediation to the current Workingset` . Para evitar problemas, recomendamos manter os arquivos remediados na mesma pasta pai e na estrutura da subpasta.

7. Depois de baixar os arquivos, você pode remediar eles com uma ferramenta apropriada. Para arquivos protegidos por senha, há várias ferramentas de quebra de senha que você pode usar. Se você conhecer as senhas dos arquivos, poderá abri-las e remover a proteção de senha.

8. Retorne à Descoberta Avançada e ao assistente de correção de erros e clique em **Avançar: Carregar arquivos**.  Isso move para a próxima página onde você pode carregar os arquivos.

    ![Carregar arquivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique a pasta pai onde os arquivos corrigidos estão localizados na caixa **Caminho para o local do texto dos** arquivos. Novamente, a pasta pai deve ter a mesma estrutura de subpasta que foi criada quando você baixou os arquivos.

    O caminho para a pasta pai é adicionado automaticamente ao comando AzCopy (como o valor do **parâmetro /Source).**

10. Copie o comando predefinido clicando em **Copiar para área de transferência**. Abra um Prompt de Comando do Windows, cole o comando do AzCopy e pressione **Enter**. carregar os arquivos.

    ![Resultados do carregamento bem-sucedido de arquivos remediados no Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Depois de executar o comando do AzCopy, clique em **Next: Process files**.

    Quando o processamento for concluído, você poderá ir para revisar o conjunto e exibir os arquivos remediados. 

## <a name="remediating-errors-in-container-files"></a>Corrigir erros em arquivos de contêiner

Em situações em que o conteúdo de um arquivo de contêiner (como um arquivo .zip) não pode ser extraído pela Descoberta Avançada, os contêineres podem ser baixados e o conteúdo expandido para a mesma pasta na qual o contêiner original reside. Os arquivos expandidos serão atribuídos ao contêiner pai como se tivesse sido originalmente expandido pela Descoberta Avançada. O processo funciona conforme descrito acima, exceto para carregar um único arquivo como o arquivo de substituição.  Ao carregar arquivos remediados, não inclua o arquivo de contêiner original.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Corrigir erros carregando o texto extraído

Às vezes, não é possível remediar um arquivo no formato nativo que a Descoberta Avançada pode interpretar. Mas você pode substituir o arquivo original por um arquivo de texto que contém o texto original do arquivo nativo (em um processo chamado sobreposição *de texto*). Para fazer isso, siga as etapas descritas neste artigo, mas em vez de remediar o arquivo original no formato nativo, você criaria um arquivo de texto que contém o texto extraído do arquivo original e, em seguida, carregaria o arquivo de texto usando o nome de arquivo original anexado com um sufixo .txt. Por exemplo, você baixa um arquivo durante a correção de erros com o nome do arquivo 335850cc-6602-4af0-acfa-1d14d9128ca2.abc. Você abre o arquivo no aplicativo nativo, copia o texto e, em seguida, o colar em um novo arquivo chamado 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt. Ao fazer isso, remova o arquivo original no formato nativo do local do arquivo corrigido em seu computador local antes de carregar o arquivo de texto corrigido para a Descoberta Avançada.

## <a name="what-happens-when-files-are-remediated"></a>O que acontece quando os arquivos são remediados

Quando os arquivos remediados são carregados, os metadados originais são preservados, exceto para os seguintes campos: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Texto
- WordCount
- WorkingsetId

Para uma definição de todos os campos de metadados em Descoberta Avançada, consulte [Campos de metadados de documento](document-metadata-fields-in-advanced-ediscovery.md).