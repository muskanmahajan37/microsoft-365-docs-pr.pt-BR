---
title: Ameaças detectadas pelo Microsoft Defender Antivirus
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como o Microsoft Defender Antivírus protege seus dispositivos Windows contra ameaças de software, como vírus, malware e spyware.
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198358"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Ameaças detectadas pelo Microsoft Defender Antivirus

O Microsoft Defender Antivírus protege seus dispositivos Windows contra ameaças de software, como vírus, malware e spyware.

- Os vírus geralmente se propagam anexando seu código a outros arquivos em seu dispositivo ou rede e podem fazer com que programas infectados funcionem incorretamente.
- O malware inclui arquivos mal-intencionados, aplicativos e código que podem causar danos e interromper o uso normal de dispositivos. Além disso, o malware pode permitir acesso não autorizado, usar recursos do sistema, roubar senhas e informações da conta, bloquear você fora do computador e solicitar resgate e muito mais.
- O spyware coleta dados, como atividades de navegação na Web, e envia os dados para servidores remotos.
 
Para fornecer proteção contra ameaças, o Microsoft Defender Antivírus usa vários métodos. Esses métodos incluem proteção entregue na nuvem, proteção em tempo real e atualizações de proteção dedicadas.

- A proteção entregue na nuvem ajuda a fornecer detecção quase instantânea e o bloqueio de ameaças novas e emergentes.
- A verificação always-on usa monitoramento de comportamento de arquivo e processo e outras técnicas (também conhecidas como *proteção em tempo real*).
- As atualizações de proteção dedicadas são baseadas no aprendizado de máquina, análise de big data humana e automatizada e pesquisa detalhada de resistência a ameaças. 

Para saber mais sobre malware e Microsoft Defender Antivírus, consulte os seguintes artigos: 

- [Noções básicas sobre malware & outras ameaças](/windows/security/threat-protection/intelligence/understanding-malware)
- [Como a Microsoft identifica malware e aplicativos potencialmente indesejados](/windows/security/threat-protection/intelligence/criteria)
- [Proteção de última geração no Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>O que acontece quando uma solução antivírus não Microsoft é usada? 

O Microsoft Defender Antivírus faz parte do sistema operacional e está habilitado em dispositivos que executam o Windows 10. No entanto, se você estiver usando uma solução antivírus que não seja da Microsoft e não estiver usando o [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)Ponto de Extremidade, o Microsoft Defender Antivírus entrará automaticamente no modo desabilitado.  

Quando no modo desabilitado, os usuários e clientes ainda podem usar o Microsoft Defender Antivírus para verificações agendadas ou sob demanda para identificar ameaças; no entanto, o Microsoft Defender Antivírus não será mais:

- ser usado como o aplicativo antivírus padrão.
- examinar ativamente arquivos em busca de ameaças.
- correção ou resolução de ameaças.

Se você desinstalar a solução antivírus que não é da Microsoft, o Microsoft Defender Antivírus entrará automaticamente no modo ativo para proteger seus dispositivos Windows contra ameaças.

> [!TIP]
> - Se você estiver usando o Microsoft 365, considere usar o Microsoft Defender Antivírus como sua solução antivírus principal. A integração pode oferecer melhor proteção. Consulte [Melhor juntos: Microsoft Defender Antivírus e Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Certifique-se de manter o Microsoft Defender Antivírus atualizado, mesmo se você estiver usando uma solução antivírus que não seja da Microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>O que esperar quando as ameaças são detectadas

Quando as ameaças são detectadas pelo Microsoft Defender Antivírus, as seguintes coisas ocorrem:

- Os usuários [recebem notificações no Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- As detecções estão listadas no aplicativo [Segurança do Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) na página Histórico **de** proteção.  
- Se você tiver protegido seus dispositivos [Windows 10](secure-win-10-pcs.md) e os inscritos no [Intune](/mem/intune/enrollment/windows-enrollment-methods), e sua organização tiver 800 ou menos dispositivos  inscritos, você verá detecções e percepções de ameaças no centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> na página Ameaças e antivírus, que você pode acessar a partir do cartão **Microsoft Defender Antivírus** na **home** page (ou no painel de navegação selecionando **Ameaças** de Saúde & antivírus  >  ).

    Se sua organização tiver mais de 800 dispositivos inscritos no Intune, você será solicitado a exibir detecções e percepções de ameaças do [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) em vez da página Ameaças e **antivírus.**
 
    > [!NOTE]
    > A **página Do Microsoft Defender Antivírus** card e Threats and **antivírus** estão sendo lançados em fases, portanto, você pode não ter acesso imediato a eles.

Na maioria dos casos, os usuários não precisam tomar nenhuma outra ação. Assim que um arquivo ou programa mal-intencionado é detectado em um dispositivo, o Microsoft Defender Antivírus o bloqueia e o impede de ser executado. Além disso, as ameaças recém-detectadas são adicionadas ao mecanismo antivírus e antimalware para que outros dispositivos e usuários também sejam protegidos.  

Se houver uma ação que um usuário precisa tomar, como aprovar a remoção de um arquivo mal-intencionado, ele verá isso na notificação recebida. Para saber mais sobre as ações que o Microsoft Defender Antivírus assume em nome de um usuário ou ações que os usuários podem precisar tomar, consulte [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Para saber como gerenciar detecções de ameaças como um profissional/administrador de IT, consulte [Review detected threats and take action](review-threats-take-action.md).

Para saber mais sobre diferentes ameaças, visite o site ameaças do <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence</a>, onde você pode executar as seguintes ações: 

- Exibir informações atuais sobre as principais ameaças.
- Exibir as ameaças mais recentes para uma região específica.
- Pesquise a enciclopédia de ameaças para obter detalhes sobre uma ameaça específica.

## <a name="related-content"></a>Conteúdo relacionado

[Proteger dispositivos Windows 10](secure-windows-10-devices.md) (artigo)\
[Avaliar o Microsoft Defender Antivírus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (artigo)\
[Como ativar a proteção antivírus](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) em tempo real e entregue na nuvem (artigo)\
[Como ativar e usar o Microsoft Defender Antivírus no aplicativo de Segurança do Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (artigo)\
[Como ativar o Microsoft Defender Antivírus usando a Política de Grupo](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (artigo)\
[Como atualizar suas definições de antivírus](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (artigo)\
[Como enviar malware e não malware à Microsoft para análise](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (artigo)
