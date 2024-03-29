---
title: Criar um novo tópico em Tópicos do Microsoft Viva
description: Como criar um novo tópico em Tópicos do Microsoft Viva.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
ms.service: ''
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 7d1dc1af6e845ccfe2fb0e8f5701a2cd3018c308
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687526"
---
# <a name="create-a-new-topic-in-microsoft-viva-topics"></a>Criar um novo tópico em Tópicos do Microsoft Viva

Em Tópicos do Viva, você pode criar um novo tópico se um não for descoberto por meio da indexação ou se a tecnologia de IA não tiver encontrado evidências suficientes para estabeleça-la como um tópico.

> [!Note] 
> Embora as informações em um tópico coletado pela AI tenham sido cortadas pela [segurança,](topic-experiences-security-trimming.md)observe que a descrição do tópico e as informações das pessoas em um tópico criado manualmente são visíveis para todos os usuários que têm permissões para exibir o tópico. 


## <a name="requirements"></a>Requisitos

Para criar um novo tópico, você precisa:
- Tenha uma licença de Tópicos do Viva.
- Ter permissões para [**Quem pode criar ou editar tópicos**](./topic-experiences-user-permissions.md). Os administradores de conhecimento podem dar aos usuários essa permissão nas configurações de permissões do tópico Tópicos do Viva. 

> [!Note] 
> Os usuários que têm permissão para gerenciar tópicos no centro de tópicos (gerentes de conhecimento) já têm permissões para criar e editar tópicos.

## <a name="to-create-a-topic"></a>Para criar um tópico

Você pode criar um novo tópico a partir de dois locais:

- Home page da central de tópicos: qualquer usuário licenciado com a permissão Quem pode criar ou editar **tópicos** (colaboradores) pode criar um novo tópico a partir da central de tópicos selecionando o **menu** Novo e selecione **Página tópico**. 

    ![Novo tópico do centro de tópicos](../media/knowledge-management/new-topic.png)  

- Página Gerenciar tópicos: qualquer usuário licenciado que tenha Quem pode gerenciar a permissão de **tópicos (gerentes** de conhecimento) pode criar um novo tópico na página Gerenciar tópicos na Central de Tópicos selecionando a página **Novo tópico.** 

    ![Novo tópico de gerenciar tópicos](../media/knowledge-management/new-topic-topic-center.png)  

### <a name="to-create-a-new-topic"></a>Para criar um novo tópico:

1. Selecione a opção para criar uma nova Página de Tópicos na faixa de opções na página Gerenciar Tópicos.

2.  Na seção **Nome deste tópico,** digite o nome do novo tópico.

    ![Nomear este tópico](../media/knowledge-management/k-new-topic-page.png)  

3. Na seção **Nomes Alternativos,** digite quaisquer outros nomes aos qual o tópico possa ser referido. 

    ![Nomes alternativos](../media/knowledge-management/alt-names.png)  

4. Na seção **Descrição,** digite algumas frases que descrevem o tópico. 

    ![Descrição do tópico](../media/knowledge-management/description.png)

4. Na seção **Pessoas fixadas,** você pode "fixar" uma pessoa para mostrar a ela como tendo uma conexão com o tópico (por exemplo, um proprietário de um recurso conectado). Comece digitando seu nome ou  endereço de email na caixa adicionar um novo usuário e selecione o usuário que você deseja adicionar nos resultados da pesquisa. Você também pode "desempinar" selecionando o ícone **Remover** da lista no cartão de usuário. Você também pode arrastar a pessoa para outro lugar na lista.
 
    ![Pessoas fixadas](../media/knowledge-management/pinned-people.png)

5. Na seção **Arquivos fixados e** páginas, você pode adicionar ou "fixar" um arquivo ou página de site do SharePoint associada ao tópico.

   ![Arquivos e páginas fixados](../media/knowledge-management/pinned-files-and-pages.png)
 
    Para adicionar um novo arquivo, selecione **Adicionar**, selecione o site do SharePoint em seus sites Frequent ou Followed e selecione o arquivo na biblioteca de documentos do site.

    Você também pode usar **a opção De um link** para adicionar um arquivo ou página fornecendo a URL. 

    > [!Note] 
    > Os arquivos e páginas que você adiciona devem estar localizados no mesmo locatário do Microsoft 365. Se quiser adicionar um link a um recurso externo no tópico, você pode adicioná-lo por meio do ícone de tela na etapa 8.


6.  A **seção Sites relacionados** mostra sites que têm informações sobre o tópico. 

    ![Seção Sites relacionados](../media/knowledge-management/related-sites.png)

    Você pode adicionar um site relacionado selecionando **Adicionar** e, em seguida, pesquisando o site ou selecionando-o em sua lista de sites Frequentes ou Recentes.
    
    ![Selecionar site](../media/knowledge-management/sites.png)

7. A **seção Tópicos relacionados** mostra conexões existentes entre tópicos. Você pode adicionar uma conexão a um tópico diferente selecionando o botão **Conectar a** um tópico relacionado e digitando o nome do tópico relacionado e selecionando-o nos resultados da pesquisa. 

   ![Tópicos relacionados](../media/knowledge-management/related-topic.png)  

    Em seguida, você pode dar uma descrição de como os tópicos estão relacionados e selecionar **Atualizar**.

   ![Descrição de tópicos relacionados](../media/knowledge-management/related-topics-update.png) 

   O tópico relacionado adicionado será exibido como um tópico conectado.

   ![Tópicos relacionados conectados](../media/knowledge-management/related-topics-final.png) 

   Para remover um tópico relacionado, selecione o tópico que você deseja remover e selecione o **ícone Remover tópico.**
 
   ![Remover tópico relacionado](../media/knowledge-management/remove-related.png)  

   Em seguida, **selecione Remover**.

   ![Confirmar remover](../media/knowledge-management/remove-related-confirm.png) 

8. Você também pode adicionar itens estáticos à página (como texto, imagens ou links) selecionando o ícone de tela, que você pode encontrar abaixo da descrição curta. A seleção abrirá a caixa de ferramentas do SharePoint da qual você pode escolher o item que deseja adicionar à página.

   ![Ícone de tela](../media/knowledge-management/webpart-library.png) 

9. Selecione **Publicar** para salvar suas alterações. 

Depois de publicar a página, o nome do tópico, o nome alternativo, a descrição e as pessoas fixadas serão exibidos para todos os usuários licenciados que exibirem o tópico. Arquivos, páginas e sites específicos só serão exibidos na página de tópicos se o visualizador tiver permissões do Office 365 para o item. 



## <a name="see-also"></a>Confira também



