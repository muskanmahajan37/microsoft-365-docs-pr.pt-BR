---
title: Configurar um conector para arquivar dados do MS SQL Database
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
description: Os administradores podem configurar um conector para importar e arquivar dados do MS SQL Database. Esse conector permite arquivar dados de fontes de dados de terceiros no Microsoft 365. Depois de arquivar esses dados, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar dados de terceiros.
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164207"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Configurar um conector para arquivar dados do MS SQL Database

Use um conector Veritas no centro de conformidade do Microsoft 365 para importar e arquivar dados do MS SQL Database para caixas de correio de usuário em sua organização do Microsoft 365. A Veritas fornece um conector MS SQL Importador de Banco de Dados configurado para capturar itens de um banco de dados usando um arquivo de configuração XML e importar esses itens para o Microsoft 365. O conector converte conteúdo do MS SQL Banco de Dados em um formato de mensagem de email e importa esses itens para caixas de correio de usuário no Microsoft 365.

Após o conteúdo do MS SQL Banco de Dados armazenado em caixas de correio de usuário, você pode aplicar recursos de conformidade do Microsoft 365, como Retenção de Litígio, Descoberta Eletrônico, políticas de retenção e rótulos de retenção. Usar um conector de banco de dados de SQL MS para importar e arquivar dados no Microsoft 365 pode ajudar sua organização a se manter em conformidade com políticas governamentais e regulatórias.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Visão geral do arquivamento dos dados de SQL MS

A visão geral a seguir explica o processo de uso de um conector para arquivar dados SQL MS no Microsoft 365.

![Fluxo de trabalho de arquivamento para MS SQL dados](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Sua organização trabalha com um provedor de banco de dados de SQL MS para configurar e configurar um site de banco de dados MS SQL Banco de Dados.

2. Uma vez a cada 24 horas, os itens MS SQL Database são copiados para o site Veritas Merge1. O conector também converte esse conteúdo em um formato de mensagem de email.

3. O conector de Importador de Banco de Dados do MS SQL que você cria no centro de conformidade do Microsoft 365, se conecta ao site mesclar Veritas1 todos os dias e transfere as mensagens para um local seguro de Armazenamento do Azure na nuvem da Microsoft.

4. O conector importa os itens de banco de dados SQL MS convertidos para as caixas de correio de usuários específicos usando o valor da propriedade *Email* do mapeamento automático do usuário conforme descrito na [Etapa 3](#step-3-map-users-and-complete-the-connector-setup). Uma subpasta na pasta Caixa de Entrada chamada **MS SQL Importador** de Banco de Dados é criada nas caixas de correio do usuário e os itens são importados para essa pasta. O conector determina para qual caixa de correio importar itens usando o valor da *propriedade Email.* Cada item do banco de dados MS SQL contém essa propriedade, que é preenchida com o endereço de email de cada participante do item.

## <a name="before-you-begin"></a>Antes de começar

- Crie uma conta Veritas Merge1 para conectores da Microsoft. Para criar uma conta, entre em contato com [o Suporte ao Cliente veritas.](https://www.veritas.com/content/support/) Você precisa entrar nessa conta ao criar o conector na Etapa 1.

- O usuário que cria o conector MS SQL Importador de Banco de Dados na Etapa 1 (e o conclui na Etapa 3) deve ser atribuído à função de Exportação de Importação de Importação de Caixa de Correio no Exchange Online. Essa função é necessária para adicionar conectores na página Conectores de dados no centro de conformidade do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um grupo de funções, atribuir a função Exportar Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Etapa 1: Configurar o conector MS SQL Importador de Banco de Dados

A primeira etapa é acessar a página **Conectores** de Dados no centro de conformidade do Microsoft365 e criar um conector para o banco de dados MS SQL.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados**  >  **MS SQL Importador de Banco de Dados.**

2. Na página **MS SQL descrição do produto importador** de banco de dados, clique **em Adicionar novo conector**.

3. Na página **Termos de serviço,** clique em **Aceitar**.

4. Insira um nome exclusivo que identifique o conector e clique em **Próximo**.

5. Entre na sua conta Merge1 para configurar o conector.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>Etapa 2: Configurar o conector de Importador de Banco de Dados SQL MS no site Veritas Merge1

A segunda etapa é configurar o conector MS SQL Importador de Banco de Dados no site Merge1. Para obter informações sobre como configurar o MS SQL Importador de Banco de Dados, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Depois de clicar em Salvar &  **Concluir**, a página de mapeamento do usuário no assistente de conector no centro de conformidade do Microsoft 365 será exibida.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Etapa 3: mapear usuários e concluir a configuração do conector

Para mapear usuários e concluir a configuração do conector, siga estas etapas:

1. Na página Mapear usuários do MS SQL Importador de Banco de Dados para usuários do **Microsoft 365,** habilita o mapeamento automático do usuário. Os itens MS SQL Database incluem uma propriedade chamada *Email*, que contém endereços de email para usuários em sua organização. Se o conector puder associar esse endereço a um usuário do Microsoft 365, os itens serão importados para a caixa de correio desse usuário.

2. Clique **em Avançar,** revise suas configurações e vá até a página **Conectores** de dados para ver o andamento do processo de importação do novo conector.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Etapa 4: Monitorar o conector de Importador de Banco de Dados SQL MS

Depois de criar o conector MS SQL Importador de Banco de Dados, você poderá exibir o status do conector no centro de conformidade do Microsoft 365.

1. Vá para <https://compliance.microsoft.com/> e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o **conector MS** SQL **Importador** de Banco de Dados para exibir a página de sobrevoo, que contém as propriedades e informações sobre o conector.

3. Em **Status do conector com origem**, clique no link Baixar **log** para abrir (ou salvar) o log de status do conector. Esse log contém dados que foram importados para a nuvem da Microsoft.

## <a name="known-issues"></a>Problemas conhecidos

- Neste momento, não há suporte para importação de anexos ou itens maiores que 10 MB. O suporte para itens maiores estará disponível posteriormente.