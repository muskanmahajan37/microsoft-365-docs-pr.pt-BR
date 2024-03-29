---
title: Privacidade e dados pessoais
description: Detalha os dados coletados, armazenados e usados pelo serviço
keywords: RGPD, retenção, exclusão, armazenamento, retenção, processamento, segurança, auditoria
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908169"
---
# <a name="privacy-and-personal-data"></a>Privacidade e dados pessoais

Os usuários podem receber, transmitir e armazenar dados em dispositivos gerenciados pela Área de Trabalho Gerenciada da Microsoft. Eles confiam que a privacidade dos dados está protegida e usada apenas de forma consistente com suas expectativas. Este artigo explica como a Área de Trabalho Gerenciada da Microsoft coleta, armazena, retém, processa, segura, compartilha, audita e exporta dados pessoais. Você também aprenderá como um administrador pode exibir, corrigir e excluir dados pessoais.

A Área de Trabalho Gerenciada da Microsoft não usa dados pessoais coletados como parte do fornecimento do serviço para fins de criação de perfil, publicidade ou marketing.

## <a name="data-collection-of-microsoft-managed-desktop"></a>Coleção de dados da Área de Trabalho Gerenciada da Microsoft

Quando os usuários registram dispositivos corporativos na Área de Trabalho Gerenciada da Microsoft, a coleta de dados é manipulada – na camada técnica – usando o Windows e o Microsoft Intune. Essas fontes coletam dados pessoais sobre os dispositivos dos usuários, como nomes de dispositivos para a Área de Trabalho Gerenciada da Microsoft para identificar o dispositivo a ser gerenciado e fornecido com as experiências da Área de Trabalho Gerenciada da Microsoft.

A Área de Trabalho Gerenciada da Microsoft não coleta dados por si só para fornecer seu serviço (exceto para informações de contato [do Administrador de IT.](#it-admin-contact-information) Em vez disso, a Área de Trabalho Gerenciada da Microsoft reutiliza dados que outras fontes, como o Windows e o Microsoft Intune, já coletaram. A Área de Trabalho Gerenciada da Microsoft usa dados que esses serviços coletam de dispositivos inscritos:

- Os dados de diagnóstico do Windows de dispositivos gerenciados pela Área de Trabalho Gerenciada da Microsoft são enviados para os armazenamentos de dados de diagnóstico do Windows da Microsoft.
- A Área de Trabalho Gerenciada da Microsoft usa [o gerenciamento moderno](/learn/modules/introduction-to-modern-management-in-microsoft-365/) para gerenciar os dispositivos inscritos. Como parte do "gerenciamento moderno", os dispositivos devem estar inscritos no Azure Active Directory do locatário.
- Para distribuir sua configuração altamente otimizada e segura para dispositivos inscritos, a Área de Trabalho Gerenciada da Microsoft usa o Microsoft Intune.
- A Área de Trabalho Gerenciada da Microsoft usa dados de inteligência de segurança do Microsoft Defender Advanced Thread Protection para os clientes que usam esse serviço.

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Armazenamento de dados e fontes na Área de Trabalho Gerenciada da Microsoft

Depois que a Área de Trabalho Gerenciada da Microsoft obtém os dados, ela precisa fornecer seu serviço, armazenamento e processamento desses dados da seguinte forma:

### <a name="storing-data-storage-location-and-data-retention"></a>Armazenamento de dados, local de armazenamento e retenção de dados

A Área de Trabalho Gerenciada da Microsoft armazena seus dados em um ou mais dos seguintes serviços de armazenamento da Microsoft:

- Azure SQL
- Armazenamento do Azure
- Dynamics 365

A Área de Trabalho Gerenciada da Microsoft armazena seus dados nos Estados Unidos. Os dados pessoais são mantidos pela Área de Trabalho Gerenciada da Microsoft por no máximo 30 dias, exceto os dados de alerta para dispositivos da Área de Trabalho Gerenciada da Microsoft coletados pelo Microsoft Defender para o Ponto de Extremidade. Os dados de alerta reais (que podem incluir dados pessoais) são armazenados por 180 dias. Os dados de alerta com dados pessoais removidos são armazenados por até dois anos. Em conformidade com o Regulamento Geral de Proteção de Dados (RGPD) e a Lei de Privacidade do Consumidor da Califórnia (CCPA), a Área de Trabalho Gerenciada da Microsoft honra os direitos do assunto de dados para quaisquer dados pessoais armazenados em dados de alerta.

### <a name="staff-location"></a>Local da equipe

As equipes de Operações de Área de Trabalho Gerenciadas e Operações de Segurança da Microsoft estão localizadas nos Estados Unidos e na Índia.

## <a name="data-usage-of-microsoft-managed-desktop"></a>Uso de dados da Área de Trabalho Gerenciada da Microsoft

A Área de Trabalho Gerenciada da Microsoft usa esses dados:


| Fontes de dados |Usar com a Área de Trabalho Gerenciada da Microsoft  |
|---------|---------|
|Dados do Azure Active Directory     | Usado em relatórios criados para administradores de locatários, que estão disponíveis no portal de Administração da Área de Trabalho Gerenciada da Microsoft.        |
|Dados do Intune     | Usado em relatórios criados para administradores de locatários, que estão disponíveis no portal de Administração da Área de Trabalho Gerenciada da Microsoft.        |
|Microsoft Defender para Ponto de Extremidade     |  Usado para lidar com ameaças de segurança detectadas em dispositivos inscritos pelo Centro de Operações de Segurança (SOC) da Área de Trabalho Gerenciada da Microsoft.  |
|Dados de diagnóstico do Windows     |Usado para determinar o status de atualização de dispositivos gerenciados e para fornecer e melhorar a oferta de ITaaS (ITaaS) da Área de Trabalho Gerenciada da Microsoft.         |
|Dados de contato do administrador     | Usado pela Área de Trabalho Gerenciada da Microsoft para se comunicar com administradores de locatários.        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Entidades processadas pela Área de Trabalho Gerenciada da Microsoft

A Área de Trabalho Gerenciada da Microsoft processa essas entidades para fornecer o serviço:

- Dados do dispositivo
- Configurações de segurança de dispositivo
- Sistema operacional de dispositivo e hardware
- Informações agregadas sobre a saúde do dispositivo
- Informações de diagnóstico de dispositivo
- Dados do locatário
- Recursos do Azure Active Directory
- Dados de política e configuração
- Dados de alerta e metadados do Microsoft Defender para Endpoint
- Dados de diagnóstico do Windows
- Dados de uso de produtos e serviços

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Os dados de identidade usados pela Área de Trabalho Gerenciada da Microsoft são armazenados pelo Azure Active Directory em uma localização geográfica com base no endereço fornecido pela organização ao inscrever-se em um serviço online da Microsoft, como o Office 365 ou o Azure. Consulte [Microsoft Azure — Onde estão os](http://azuredatacentermap.azurewebsites.net/) dados do meu cliente? para um mapa mostrando os datacenters do Azure Active Directory.

Para obter mais informações sobre as regiões que o Azure usa para armazenamento de dados, consulte [Azure Active Directory–Where is your data located](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9).

### <a name="microsoft-intune"></a>Microsoft Intune

Os dados do Intune podem ser armazenados em algumas regiões diferentes, como Europa Norte (Irlanda) e Europa Ocidental (Países Baixos). O administrador de IT cria uma conta de locatário e escolhe o país onde os dados serão armazenados quando eles se registrarem inicialmente nos serviços do Intune. Para ver uma lista de locais de datacenter usados pelo Intune, consulte [Microsoft Intune— Onde estão meus dados do cliente?](http://intunedatacentermap.azurewebsites.net/). Para obter mais informações sobre armazenamento de dados e uso pelo Intune, consulte [Coleta de dados no Intune](/intune/privacy-data-collect).

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

Os dados do Microsoft Defender para Ponto de Extremidade podem ser armazenados em algumas regiões diferentes. Por esse motivo, o Defender for Endpoint opera nos datacenters do Microsoft Azure na União Europeia, no Reino Unido e nos Estados Unidos, conforme indicado no [Microsoft Defender for Endpoint—](http://intunedatacentermap.azurewebsites.net/)Data storage locations . Para obter mais informações sobre armazenamento de dados e uso pelo Defender para Ponto de Extremidade, consulte Quais dados [o Microsoft Defender for Endpoint coleta?](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Conforme declarado na Declaração de Privacidade da Microsoft , "os dados pessoais coletados pela Microsoft podem ser armazenados e processados em sua região, nos Estados Unidos e em qualquer outro país onde a [Microsoft](https://privacy.microsoft.com/privacystatement)ou suas afiliadas, subsidiárias ou provedores de serviços operam instalações. [...] Normalmente, o local de armazenamento principal está na região do cliente ou nos Estados Unidos, geralmente com um backup para um datacenter em outra região. Os locais de armazenamento são escolhidos para operar com eficiência, melhorar o desempenho e criar redundâncias para proteger os dados se houver uma paralisação ou outro problema. Tomaremos medidas para garantir que os dados coletados sob essa instrução de privacidade são processados de acordo com as disposições desta instrução e os requisitos da lei aplicável onde quer que os dados estejam localizados."

Para obter mais informações sobre a coleção de dados de diagnóstico do Windows 10, consulte a seção "Onde armazenamos e processemos dados [pessoais"](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) da Declaração de Privacidade da Microsoft.

## <a name="data-access-protection"></a>Proteção de acesso a dados

O acesso direto aos armazenamentos de dados internos da Área de Trabalho Gerenciada da Microsoft é restrito de várias maneiras:

- Requer aprovação de nível de líder de engenharia.
- Ele é auditado e limitado por tempo.
- Exige o uso de uma estação de trabalho altamente protegida e restrita.
- Todos os dados são criptografados enquanto são armazenados.
- Não há acesso permanente.
- O acesso ao portal de gerenciamento interno da Área de Trabalho Gerenciada da Microsoft exige uma estação de trabalho altamente protegida e restrita.

## <a name="processing-personal-data-in-a-compliant-manner"></a>Processamento de dados pessoais de maneira compatível
A Área de Trabalho Gerenciada da Microsoft processa dados pessoais com sistemas certificados iso. Para obter mais informações, consulte [Compliance](../intro/compliance.md).

## <a name="profiling-and-marketing"></a>Criação de perfil e marketing

A Área de Trabalho Gerenciada da Microsoft não usa dados pessoais coletados como parte do fornecimento do serviço para fins de criação de perfil, publicidade ou marketing.

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de assunto de dados para o RGPD e o CCPA

O [RGPD (Regulamento](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) Geral de Proteção de Dados) da União Europeia concede direitos às pessoas (conhecidas na regulamentação como titulares de dados) para gerenciar os dados pessoais coletados por um empregador ou outro tipo de agência ou organização (conhecido como controlador de dados ou controlador just). Os dados pessoais são definidos em linhas gerais no GDPR como todos os dados relacionados a uma pessoa física identificada ou identificável. O GDPR fornece às entidades de dados direitos específicos a seus dados pessoais. Esses direitos incluem obter cópias, solicitar alterações, restringir o processamento, excluir ou receber os dados em um formato eletrônico para que eles possam ser passados para outro controlador. Uma solicitação formal feita por uma entidade de dados a um controlador para executar uma ação em seus dados pessoais é chamada neste documento de Solicitação de Direitos da Entidade de Dados  ou DSR.

Da mesma forma, o CCPA fornece direitos de privacidade e obrigações para os consumidores da Califórnia, incluindo direitos semelhantes aos Direitos de Dados do RGPD, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais. O CCPA também fornece determinadas divulgações, proteções contra discriminação ao optar por direitos de exercício e requisitos de "aceitação/aceitação" para determinadas transferências de dados classificadas como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](/compliance/regulatory/offering-ccpa?view=o365-worldwide) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](/compliance/regulatory/ccpa-faq?view=o365-worldwide).

A seção a seguir discute como a Área de Trabalho Gerenciada da Microsoft ajuda os controladores a encontrar, acessar e agir em dados pessoais ou informações pessoais usadas pela Área de Trabalho Gerenciada da Microsoft.

> [!NOTE]
> Se você estiver procurando informações gerais sobre o RGPD, consulte a seção [RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) do Portal de Confiança de Serviço.

### <a name="it-admin-contact-information"></a>Informações de contato do administrador de IT

Um administrador de locatários pode exibir, corrigir e excluir seus próprios dados pessoais (como suas próprias informações de contato) diretamente na seção Contato do Administrador do Portal da Área de Trabalho Gerenciada da Microsoft.

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Dados de alerta do Microsoft Defender para Ponto de Extremidade

Os administradores de segurança podem solicitar uma extração ou exclusão de dados pessoais relacionados ao Microsoft Defender para alertas do Ponto de Extremidade em um dispositivo gerenciado da Área de Trabalho Gerenciada da Microsoft em seu ambiente. O administrador de segurança deve entrar no Portal de Administração da Área de Trabalho [Gerenciada](https://aka.ms/memadmin) da Microsoft e enviar uma solicitação de suporte. Selecione **Tipo** de solicitação de suporte de **Solicitação** de Alteração **,** Categoria de Segurança e **Subcategoria** de Outros **e** forneça os nomes de dispositivo relevantes na descrição juntamente com sua solicitação de extração ou exclusão de dados.

### <a name="user-related-personal-data"></a>Dados pessoais relacionados ao usuário

Além disso, a Área de Trabalho Gerenciada da Microsoft não coleta dados pessoais por conta própria. Em vez disso, ele depende e usa dados pessoais coletados por outros Serviços Do Microsoft Enterprise Online. Os administradores de IT que procuram responder às suas solicitações de usuário para exibir, corrigir e excluir seus dados pessoais podem usar a respectiva funcionalidade dos serviços subjacentes dos quais a Área de Trabalho Gerenciada da Microsoft depende. Se você estiver interessado em exibir ou excluir dados pessoais usados por esses serviços, consulte primeiro o artigo Solicitações de Assunto de Dados do [Azure](/compliance/regulatory/gdpr-dsr-Azure) para o artigo RGPD.

Além disso, use as seguintes diretrizes para exercer DSRs para os serviços que a Área de Trabalho Gerenciada da Microsoft depende para a coleta de dados pessoais:

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)