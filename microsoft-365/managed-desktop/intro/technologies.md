---
title: Tecnologias de Área de Trabalho Gerenciada da Microsoft
description: Este artigo lista as tecnologias e aplicativos usados na Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920571"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de Área de Trabalho Gerenciada da Microsoft

Este artigo lista as tecnologias e aplicativos usados na Área de Trabalho Gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O licenciamento do Microsoft 365 Enterprise é necessário para todos os usuários da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre requisitos de licenciamento para o serviço, consulte [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).

Este artigo resume os componentes incluídos nas licenças enterprise necessárias, com uma descrição de como o serviço usa cada componente com dispositivos da Área de Trabalho Gerenciada da Microsoft. Funções e responsabilidades específicas para cada área são detalhadas em toda a documentação da Área de Trabalho Gerenciada da Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 ou E5
 |
 --- | ---
Aplicativos do Microsoft 365 para empresas (64 bits) | Esses aplicativos do Office serão fornecidos com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>As versões completas de 64 bits do Microsoft Project e do Microsoft Visio não estão incluídas. No entanto, como a instalação desses aplicativos depende da instalação do Microsoft 365 Apps para empresas, a Área de Trabalho Gerenciada da Microsoft criou implantações padrão do Microsoft Intune e grupos de segurança que você pode usar para implantar esses aplicativos para usuários licenciados. Para obter mais informações, [consulte Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).
OneDrive |O Logom Único do Azure Active Directory está habilitado para usuários quando eles fazem logom pela primeira vez no OneDrive.<br><br>O Redirecionamento de Pasta Conhecido para pastas "Desktop", "Document" e "Pictures" está incluído; habilitado e configurado pela Área de Trabalho Gerenciada da Microsoft.
Aplicativos da Loja |    O Microsoft Sway e o Power BI não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Teams não é fornecido com o dispositivo, mas é empacotado e fornecido pela Microsoft para dispositivos da Área de Trabalho Gerenciada da Microsoft. O Cliente de Proteção de Informações do Azure não é fornecido com o dispositivo, mas você pode empacotá-lo para implantação.
Aplicativos Web |  Yammer, Office em um navegador, Delve, Flow, StaffHub, PowerApps e Planner não são fornecidos com o dispositivo. Os usuários podem acessar a versão da Web desses aplicativos com um navegador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 ou E3 com o Microsoft Defender para Ponto de Extremidade
Recomendamos que os administradores de IT configurem as configurações a seguir. Essas configurações não são incluídas ou gerenciadas como parte da Área de Trabalho Gerenciada da Microsoft.

 |
 --- | ---
Windows Hello para Empresas | Você deve implementar o Windows Hello para Empresas para substituir senhas por autenticação forte de dois fatores para dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).
Virtualização de aplicativo | Você pode implantar pacotes de Virtualização de Aplicativo (App-V) usando o cliente de gerenciamento de aplicativos do Intune Win32. Para obter mais informações, consulte [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Prevenção contra perda de dados do Microsoft 365 | Você deve implementar a prevenção contra perda de dados do Microsoft 365 para monitorar as ações que estão sendo tomadas em itens que você determinou como confidenciais e para ajudar a evitar o compartilhamento não intencional desses itens. Para obter mais informações, consulte Prevenção contra perda de [dados do Microsoft 365](../../compliance/endpoint-dlp-learn-about.md).


Recursos incluídos e gerenciados como parte da Área de Trabalho Gerenciada da Microsoft:

 |
 --- | ---
Criptografia de unidade do BitLocker | A Criptografia de Unidade do BitLocker é usada para criptografar todas as unidades do sistema. Para obter mais informações, consulte [BitLocker Drive Encryption](/windows/security/information-protection/bitlocker/bitlocker-overview).
Windows Defender System Guard | Protege a integridade do sistema na inicialização e valida que a integridade do sistema foi realmente mantida. Para obter mais informações, [consulte Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Windows Defender Credential Guard | Windows Defender Credential Guard usa a segurança baseada em virtualização para isolar segredos para que somente o software do sistema privilegiado possa acessá-los. Para obter mais informações, [consulte Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender para Ponto de Extremidade - Detecção e Resposta do Ponto de Extremidade | As Operações de Segurança da Área de Trabalho Gerenciada da Microsoft respondem a alertas e toma medidas para correção de ameaças usando a Detecção e a Resposta do Ponto de Extremidade. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender para Ponto de Extremidade - Especialistas em Ameaças | A Área de Trabalho Gerenciada da Microsoft se integra com informações e dados de especialistas em ameaças por meio de notificações de ataque direcionadas. Você terá que fornecer consentimento adicional antes que esse serviço seja habilitado. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender para Ponto de Extremidade - Gerenciamento de Ameaças e Vulnerabilidades | Obrigatório para uso futuro no plano de serviço da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Threat and Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).
Microsoft Defender para Ponto de Extremidade - Redução de Superfície de Ataque | A redução de superfície de ataque tem como alvo comportamentos de software arriscados que geralmente são abusadas por invasores. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Attack Surface Reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).
Microsoft Defender para Ponto de Extremidade - Exploit Protection | Protege contra malware que usa explorações para infectar dispositivos e se propagar aplicando automaticamente técnicas de mitigação de exploração a processos e aplicativos do sistema operacional. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).
Microsoft Defender para Ponto de Extremidade - Proteção de Rede | A proteção de rede expande o escopo do Microsoft Defender SmartScreen para bloquear todo o tráfego HTTP e HTTPS de saída que tenta se conectar a fontes de baixa reputação. Para obter mais informações, consulte [Microsoft Defender for Endpoint - Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection).
Proteção contra Adulteração do Microsoft Defender | A Proteção contra Adulteração do Windows é usada para impedir que as configurações de segurança, como a proteção antivírus, seja alterada. Para obter mais informações, consulte [Microsoft Defender Tamper Protection](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Proteção antivírus baseada em comportamento do Microsoft Defender Antivírus, heurística e em tempo real | Sempre em busca de ameaças de arquivo e processo que podem não ser detectadas como malware. Para obter mais informações, consulte [Microsoft Defender Antivírus Behavior-based, heuristic, and real-time antivír protection]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).
Microsoft Defender Antivírus Cloud-delivered Protection | Fornece proteção dinâmica quase instantânea e automatizada contra ameaças novas e emergentes. Para obter mais informações, consulte [Microsoft Defender Antivírus Cloud-delivered Protection](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
Microsoft Defender "Bloquear à primeira vista" | Fornece detecção e bloqueio de novo malware quando o Windows detecta um arquivo suspeito ou desconhecido. Para obter mais informações, consulte [Microsoft Defender Block à primeira vista](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus).
Aplicativos potencialmente indesejados do Microsoft Defender AV | Aplicativos potencialmente indesejados são usados para bloquear aplicativos que podem fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outros softwares que podem ser inesperados ou indesejados. Para obter mais informações, consulte [Microsoft Defender AV Potentially Unwanted Applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).
Windows Defender Firewall com Segurança Avançada | Filtragem de tráfego de rede de duas vias baseada em host para um dispositivo, Windows Defender Firewall bloqueia o tráfego de rede não autorizado fluindo para ou para fora do dispositivo local. Para obter mais informações, [consulte Windows Defender Firewall com Segurança Avançada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
Controle de Conta de Usuário | O Controle de Conta de Usuário alterna para a Área de Trabalho Segura quando uma tarefa ou ação exige o acesso do tipo de conta do administrador. Os usuários da Área de Trabalho Gerenciada da Microsoft são atribuídos Acesso padrão ao usuário no registro. Para obter mais informações, consulte [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e do Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Microsoft Cloud App Security |  Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
Proteção de Informações do Azure P2  | Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.