---
title: Configurar um conector para arquivar dados do LinkedIn
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Saiba como os administradores podem configurar & usar um conector nativo para importar dados de uma Página da Empresa do LinkedIn para o Microsoft 365.
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906141"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Configurar um conector para arquivar dados do LinkedIn

Use um conector no centro de conformidade do Microsoft 365 para importar e arquivar dados de páginas da Empresa do LinkedIn. Depois de configurar e configurar um conector, ele se conecta à conta para a página específica da Empresa do LinkedIn uma vez a cada 24 horas. O conector converte as mensagens postadas na página empresa em uma mensagem de email e importa esses itens para uma caixa de correio no Microsoft 365.

Depois que os dados da página da Empresa do LinkedIn são armazenados em uma caixa de correio, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Pesquisa de Conteúdo, Arquivamento de In-Place, Auditoria e políticas de retenção do Microsoft 365 aos dados do LinkedIn. Por exemplo, você pode pesquisar esses itens usando a Pesquisa de Conteúdo ou associar a caixa de correio de armazenamento a um custodiante em um caso de Descoberta Avançada. A criação de um conector para importar e arquivar dados do LinkedIn no Microsoft 365 pode ajudar sua organização a permanecer em conformidade com políticas governamentais e regulatórias.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar um conector

- O usuário que cria um conector de Página da Empresa do LinkedIn deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Isso é necessário para adicionar conectores na página **Conectores de** dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

- Você deve ter as credenciais de entrada (endereço de email ou número de telefone e senha) de uma conta de usuário do LinkedIn que é um administrador da Página da Empresa do LinkedIn que você deseja arquivar. Você usa essas credenciais para entrar no LinkedIn ao configurar o conector.

- O conector do LinkedIn pode importar um total de 200.000 itens em um único dia. Se houver mais de 200.000 itens do LinkedIn em um dia, nenhum desses itens será importado para o Microsoft 365.

## <a name="create-a-linkedin-connector"></a>Criar um conector do LinkedIn

1. Vá para <https://compliance.microsoft.com> e clique em **Conectores de dados** Páginas da Empresa  >  **linkedIn**.

2. Na página do produto páginas da empresa do **LinkedIn,** clique **em Adicionar conector**.

3. Na página **Termos de serviço,** selecione **Aceitar**.

4. Na página **Entrar com LinkedIn,** clique **em Entrar com LinkedIn**.

   A página de login do LinkedIn é exibida.

   ![Página de login do LinkedIn](../media/LinkedInSigninPage.png)

5. Na página de entrada do LinkedIn, insira o endereço de email (ou número de telefone) e a senha da conta do LinkedIn associada à página da empresa que você deseja arquivar e clique em **Entrar**.

   Uma página do assistente é exibida com uma lista de todas as Páginas da Empresa do LinkedIn associadas à conta à qual você se inscreveu. Um conector só pode ser configurado para uma página da empresa. Se sua organização tiver várias Páginas da Empresa do LinkedIn, você terá que criar um conector para cada uma delas.

   ![Uma página com uma lista de Páginas da Empresa do LinkedIn é exibida](../media/LinkedInSelectCompanyPage.png)

6. Selecione a página da empresa da onde você deseja arquivar itens e clique em **Próximo**.

7. Na página **Escolher local de** armazenamento, clique na caixa, selecione o endereço de email de uma caixa de correio do Microsoft 365 para a qual os itens do LinkedIn serão importados e clique em **Próximo**. Os itens são importados para a pasta de caixa de entrada nesta caixa de correio.

8. Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.

Depois de criar o conector, você  pode voltar para a página Conectores de Dados  para ver o andamento do processo de importação do novo conector (selecione Atualizar se necessário para atualizar a lista de conectores). O valor na coluna **Status** está **Aguardando para iniciar**. Leva até 24 horas para que o processo de importação inicial seja iniciado. Após a primeira vez em que o conector é executado e importa os itens do LinkedIn, o conector é executado uma vez a cada 24 horas e importa todos os novos itens criados na Página da Empresa do LinkedIn nas 24 horas anteriores.

Para exibir mais detalhes, selecione o conector na lista na página **Conectores de** dados para exibir a página de sobremenu. Em **Status**, o intervalo de datas exibido indica o filtro de idade selecionado quando o conector foi criado.

## <a name="more-information"></a>Mais informações

Os itens do LinkedIn são importados para a subpasta do LinkedIn na caixa de entrada da caixa de correio de armazenamento no Microsoft 365. Eles aparecem como mensagens de email.