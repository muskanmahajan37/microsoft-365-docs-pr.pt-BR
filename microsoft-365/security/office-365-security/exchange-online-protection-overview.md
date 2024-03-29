---
title: Proteção do Exchange Online (EOP) visão geral
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Saiba como Proteção do Exchange Online (EOP) pode ajudar a proteger sua organização de email local em ambientes autônomos e híbridos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624713"
---
# <a name="exchange-online-protection-overview"></a>Visão geral do Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Proteção do Exchange Online (EOP) é o serviço de filtragem baseado em nuvem que ajuda a proteger sua organização contra spam, malware e outras ameaças de email. O EOP está incluído em todas as organizações Microsoft 365 com Exchange Online caixas de correio.

O restante deste artigo explica como o EOP funciona.

> [!NOTE]
> O EOP também está disponível por si só para proteger caixas de correio locais e em ambientes híbridos para proteger as caixas de correio locais Exchange local. Para obter mais informações, consulte [Autônomo Proteção do Exchange Online](/exchange/standalone-eop/standaonline-eop).

## <a name="how-eop-works"></a>Como o EOP funciona

Para entender como o EOP funciona, ele o ajuda a ver como processa o email de entrada:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico de emails da Internet ou comentários do cliente que passam para o EOP e por meio do Connection, Anti-malware, Mailflow Rules-slash-Policy Filtering e Filtragem de Conteúdo, antes do veredito de lixo eletrônico ou quarentena ou entrega de email de usuário final.":::

- Quando uma mensagem de entrada entra no EOP, ela passa inicialmente pela filtragem de conexão, que verifica a reputação do remetente. A maioria dos spams é interrompida neste ponto e rejeitada pelo EOP. Para obter mais informações, confira [Configurar a filtragem da conexão](configure-the-connection-filter-policy.md).

- Em seguida, a mensagem é inspecionada para malware. Se o malware for encontrado na mensagem ou nos anexos, a mensagem será roteada para um armazenamento de quarentena somente de administrador. Para saber mais sobre a proteção contra malware, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).

- As mensagens continuam por meio da filtragem de política, onde são avaliadas em relação às regras de fluxo de emails personalizadas (também conhecidas como regras de transporte) que você cria ou impõe a partir de um modelo. Por exemplo, você pode ter uma regra que envia uma notificação a um gerente quando o email chega de um remetente específico. Verificações de prevenção contra perda de dados (DLP) também ocorrem neste ponto (Exchange Enterprise CAL com Serviços).

- Em seguida, a mensagem passa pela filtragem anti-spam, onde a mensagem é verificar se há spam, phishing ou email em massa. As mensagens detectadas podem ser enviadas para quarentena ou a pasta Lixo Eletrônico do usuário, entre outras opções. Para obter mais informações, [consulte Configure anti-spam policies](configure-your-spam-filter-policies.md) and Configure [anti-phishing policies](configure-anti-phishing-policies-eop.md).

Qualquer mensagem que passa todas essas camadas de proteção com êxito é entregue ao destinatário.

Para obter mais informações, [consulte Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planos e recursos do EOP para organizações de email locais

Os planos de assinatura do EOP disponíveis são:

- **Autônomo do EOP:** você se inscreva no EOP para proteger sua organização de email local.

- **Recursos do EOP no Exchange Online**: Qualquer assinatura que inclua Exchange Online (autônomo ou como parte do Microsoft 365) usa o EOP para proteger suas caixas de correio Exchange Online.

- **Exchange Enterprise CAL com Serviços**: se você tiver uma organização Exchange local onde comprou licenças adicionais do Exchange Enterprise CAL com Serviços, o EOP faz parte dos serviços incluídos.

Para obter informações sobre requisitos, limites importantes e disponibilidade de recursos em todos os planos de assinatura do EOP, consulte Proteção do Exchange Online [descrição do serviço.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

> [!NOTE]
> Se você tiver uma assinatura Microsoft 365 ou Office 365 que inclua Exchange Online caixas de correio, você terá eOP. Para obter etapas para configurar os recursos de segurança do EOP em sua assinatura e informações sobre a segurança adicionada que uma assinatura do Microsoft Defender para Office 365 pode lhe dar, consulte [protect against threats](protect-against-threats.md). As configurações recomendadas para o recurso EOP para instalação podem ser encontradas em [Configurações recomendadas](recommended-settings-for-eop-and-office365.md)para EOP e Microsoft Defender para Office 365 segurança .

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configuração do EOP para organizações de email locais

A configuração do EOP pode ser simples, especialmente no caso de uma pequena organização com um punhado de regras de conformidade. No entanto, se você tiver uma organização de grande porte com vários domínios, regras de conformidade personalizadas ou fluxo de email híbrido, a configuração pode precisar de mais planejamento e tempo.

Se você já comprou o EOP, consulte [Configurar seu serviço EOP](/exchange/standalone-eop/set-up-your-eop-service) para garantir a conclusão de todas as etapas necessárias de configuração do EOP, a fim de proteger seu ambiente de mensagens.

### <a name="eop-datacenters"></a>Datacenters EOP

O EOP é executado em uma rede mundial de data center projetados para fornecer a melhor disponibilidade. Por exemplo, se um data center ficar indisponível, mensagens de email são automaticamente roteadas para um outro data center sem qualquer interrupção no serviço. Os servidores em cada datacenter aceitam mensagens em seu nome, fornecendo uma camada de separação entre sua organização e a Internet, reduzindo assim a carga em seus servidores. Por meio dessa rede altamente disponível, a Microsoft pode assegurar que esse email chegue a sua organização pontualmente.

EOP realiza balanceamento de carga entre data centers, mas apenas dentro de uma região. Se você for aprovisionado em uma região, todas as suas mensagens serão processadas usando o roteamento de email para essa região. A lista a seguir mostra como o roteamento de email regional funciona para os data centers EOP:

- Na Europa, Oriente Médio e África (EMEA), todas as caixas de correio do Exchange Online são localizadas nos data centers da EMEA e todas as mensagens são roteadas através de data centers da EMEA para filtragem do EOP.
- No Asia-Pacific (APAC), todas as caixas de correio Exchange Online estão localizadas em datacenters APAC, e as mensagens atualmente são roteadas por meio de datacenters APAC para filtragem de EOP.
- Nas Américas, os serviços são distribuídos nos seguintes locais:
  - América do Sul: Exchange Online caixas de correio estão localizadas em datacenters no Brasil e no Chile. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
  - Canadá: Exchange Online caixas de correio estão localizadas em datacenters no Canadá. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
  - Estados Unidos: Exchange Online caixas de correio estão localizadas em datacenters dos EUA. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.
- Para a Nuvem de Comunidade Governamental (GCC), todas as caixas de correio do Exchange Online localizadas em data centers dos EUA e todas as mensagens são roteadas através de data centers dos EUA para filtragem do EOP.

## <a name="eop-help-for-admins"></a>Ajuda do EOP para administradores

O conteúdo da Ajuda para administradores do EOP é composta pelas seguintes categorias de primeiro nível:

- [Configure o EOP, Dia 1,](protect-against-threats.md)para o Microsoft Defender para administradores Office 365 : Configurando ferramentas de proteção e detecção do EOP no núcleo do Microsoft Defender para Office 365.

- [Recursos do EOP](eop-features.md): fornece uma lista de recursos que estão disponíveis no EOP.

- [Configurar seu serviço EOP:](/exchange/standalone-eop/set-up-your-eop-service)fornece etapas para configurar seu serviço EOP e links para informações adicionais.

- Alternar para o EOP do Google Postini, o Firewall de Spam e [Vírus barracuda](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ou Cisco IronPort : descreve o processo para alternar para o EOP de outro produto de proteção de email.

- [Gerenciar destinatários no EOP autônomo](/exchange/standalone-eop/manage-recipients-in-eop): descreve como gerenciar usuários de email e grupos no EOP autônomo.

- Fluxo de emails no [EOP](mail-flow-in-eop.md): descreve como configurar cenários de fluxo de emails personalizados usando conectores, como gerenciar domínios associados ao serviço e como habilitar o recurso DbEB (Bloqueio de Borda Baseado em Diretório).

- [Configurações recomendadas para o EOP](recommended-settings-for-eop-and-office365.md)e o Microsoft Defender para Office 365 segurança: descreve as configurações recomendadas e considerações para depois de configurar e provisionar seu serviço.

- [Relatórios de auditoria no Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): descreve como usar relatórios de auditoria para controlar as alterações de configuração no serviço.

- [Proteção anti-spam e anti-malware](anti-spam-and-anti-malware-protection.md)no EOP : descreve a filtragem de spam e a filtragem de malware e mostra como personalizá-los para atender melhor às necessidades da sua organização. Descreve também as tarefas que os administradores e usuários finais podem realizar em mensagens em quarentena.

- [Relatórios e rastreamento de mensagens Proteção do Exchange Online](reporting-and-message-trace-in-exchange-online-protection.md): descreve os relatórios e as ferramentas de solução de problemas disponíveis.

- [Exchange centro](/exchange/exchange-admin-center) de administração no Exchange Online ou centro de administração do Exchange no [EOP](/exchange/standalone-eop/exchange-admin-center-eop)autônomo : descreve como acessar e navegar pela interface de gerenciamento do Centro de administração do Exchange (EAC) para gerenciar recursos relacionados do EOP.

- [Proteção do Exchange Online PowerShell](/powershell/exchange/exchange-online-protection-powershell): fornece informações sobre o PowerShell remoto, que permite gerenciar seu serviço EOP a partir da linha de comando.

- [Ajuda e suporte para EOP](help-and-support-for-eop.md) Fornece informações sobre como obter ajuda e suporte técnico.