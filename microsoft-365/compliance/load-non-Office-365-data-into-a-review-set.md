---
title: Carregar dados que não são do Microsoft 365 em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como importar dados que não são do Microsoft 365 para um conjunto de revisão para análise em um caso de Descoberta Avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903497"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Carregar dados que não são do Microsoft 365 em um conjunto de revisão

Nem todos os documentos que você precisa analisar na Descoberta Avançada estão localizados no Microsoft 365. Com o recurso de importação de dados que não é do Microsoft 365 na Descoberta Avançada, você pode carregar documentos que não estão localizados no Microsoft 365 para um conjunto de revisão. Este artigo mostra como trazer seus documentos que não são do Microsoft 365 para a Descoberta Avançada para análise.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para carregar conteúdo que não seja do Office 365

O uso do recurso de carregamento que não seja do Microsoft 365 descrito neste artigo exige que você tenha o seguinte:

- Todos os custodiantes aos que você deseja associar conteúdo que não seja do Microsoft 365 devem ter a licença apropriada. Para obter mais informações, [consulte Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Um caso de Descoberta Avançada avançada existente.

- Os custodiantes devem ser adicionados ao caso antes de você poder carregar e associar os dados que não são do Microsoft 365 a eles.

- Os dados que não são do Microsoft 365 devem ser um tipo de arquivo com suporte da Descoberta Avançada. Para obter mais informações, consulte [Tipos de arquivo com suporte em Descoberta Avançada de eDiscovery](supported-filetypes-ediscovery20.md).

- Todos os arquivos carregados em um conjunto de revisão devem estar localizados em pastas, onde cada pasta está associada a um custodiante específico. Os nomes dessas pastas devem usar o seguinte formato de nome: *alias@domainname*. O alias@domainname deve ser o alias e o domínio do Microsoft 365 do usuário. Você pode coletar todas as alias@domainname em uma pasta raiz. A pasta raiz só pode conter as alias@domainname pastas. Arquivos soltos na pasta raiz não são suportados.

   A estrutura de pastas para os dados que não são do Microsoft 365 que você deseja carregar seria semelhante ao exemplo a seguir:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Onde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com são os endereços SMTP dos custodiantes no caso.

   ![Estrutura de pasta de carregamento de dados que não seja do Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Uma conta atribuída ao grupo de funções do Gerenciador de Descobertas e Descobertas (e adicionada como Administrador de Descoberta Digital).

- A ferramenta do AzCopy v8.1 instalada em um computador que tem acesso à estrutura de pasta de conteúdo que não é do Microsoft 365. Para instalar o AzCopy, consulte [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy). Instale o AzCopy no local padrão, que é **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**. Você deve usar o AzCopy v8.1. Outras versões do AzCopy podem não funcionar ao carregar dados que não são do Microsoft 365 na Descoberta Eletrônica Avançada.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Carregar conteúdo que não seja do Microsoft 365 em Descoberta Avançada

1. Como um Gerente de Descoberta De eDiscovery ou Administrador de DescobertaS EDiscovery, abra a Descoberta Avançada e vá para o caso em que os dados que não são do Microsoft 365 serão carregados.  

2. Clique **em Revisar conjuntos** e selecione o conjunto de revisão para carregar os dados que não são do Microsoft 365.  Se você não tiver um conjunto de revisão, poderá criar um. 
 
3. No conjunto de revisão, clique em **Gerenciar** conjunto de revisão e, em seguida, clique em Exibir **carregamentos** no pacote de dados **Não-Microsoft 365.**

4. Clique **em Carregar arquivos** para iniciar o assistente de importação de dados.

   ![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   A primeira etapa do assistente prepara um local seguro do Armazenamento do Azure fornecido pela Microsoft para carregar os arquivos.  Quando a preparação é concluída, o **botão Próximo: Carregar arquivos** fica ativo.

   ![Importação que não seja do Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Clique **em Próximo: Carregar arquivos**.

6. Na página **Carregar arquivos,** faça o seguinte:

   ![Não Importação do Microsoft 365: Carregar arquivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Na caixa **Caminho para a localização** dos arquivos, verifique ou digite o local da pasta raiz onde você armazenou os dados que não são do Microsoft 365 que você deseja carregar. Por exemplo, para o local dos arquivos de exemplo mostrados na seção Antes de **começar,** digite **%USERPROFILE\Downloads\nonO365**. Fornecer o local correto garante que o comando do AzCopy exibido na caixa sob o caminho seja atualizado corretamente.

   b. Clique **em Copiar para área de** transferência para copiar o comando exibido na caixa.

7. Inicie um prompt de comando do Windows, cole o comando que você copiou na etapa anterior e pressione **Enter** para iniciar o comando AzCopy.  Depois de iniciar o comando, os arquivos que não são do Microsoft 365 serão carregados no local de Armazenamento do Azure que foi preparado na etapa 4.

   ![Importação não do Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Como mencionado anteriormente, você deve usar o AzCopy v8.1 para usar com êxito o comando fornecido na página **Carregar arquivos.** Se o comando AzCopy fornecido falhar, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Volte para o Centro de Conformidade & segurança e clique em **Next: Process files** in the wizard.  Isso inicia o processamento, extração de texto e indexação dos arquivos que não são do Microsoft 365 que foram carregados no local do Armazenamento do Azure.  

9. Acompanhe o progresso do processamento  dos arquivos na  página Arquivos de processo ou na guia Trabalhos exibindo um trabalho chamado Adicionando dados que não são do **Microsoft 365 a** um conjunto de revisão.  Depois que o trabalho for concluído, os novos arquivos estarão disponíveis no conjunto de revisão.

   ![Não Importação do Microsoft 365: Processar arquivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Depois que o processamento for concluído, você poderá fechar o assistente.