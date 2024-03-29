---
title: Como relatar falsos positivos ou falsos negativos após investigação automatizada no Microsoft Defender para Office 365
description: Algo falhou ou errou ao ser detectado pelo AIR no Microsoft Defender para Office 365? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 036ef1c97788f310c5b906ae5f80076ca2359cdb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275079"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se os recursos automatizados de investigação e resposta [(AIR)](automated-investigation-response-office.md) em Office 365 algo perdido ou detectado incorretamente, há etapas que sua equipe de operações de segurança pode tomar para corrigi-lo. Essas ações incluem:

- [Relatando um falso positivo/negativo para a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Ajustando alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e
- [Desfazer ações de correção que foram tomadas.](#undo-a-remediation-action)

Use este artigo como um guia.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Relatar um falso positivo/negativo à Microsoft para análise

Se o AIR no Microsoft Defender para Office 365 não tiver perdido uma mensagem de email, um anexo de email, uma URL em uma mensagem de email ou uma URL em um arquivo Office, você poderá enviar [spam, phish, URLs](admin-submission.md)e arquivos suspeitos para a Microsoft para Office 365 verificação.

Você também pode [enviar um arquivo para a Microsoft para análise de malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Ajustar um alerta para evitar que falsos positivos se repitam

Se um alerta for disparado por uso legítimo ou o alerta for impreciso, você poderá Gerenciar [alertas no portal](/cloud-app-security/managing-alerts)Cloud App Security .

Se sua organização estiver usando o [Microsoft Defender para Ponto](/windows/security/threat-protection) de Extremidade, além do Office 365, e um arquivo, endereço IP, URL ou domínio for tratado como malware em um dispositivo, mesmo que seja seguro, você poderá criar um indicador personalizado com uma ação ["Permitir"](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)para seu dispositivo.

## <a name="undo-a-remediation-action"></a>Desfazer uma ação de correção

Na maioria dos casos, se uma ação de correção tiver sido tomada em uma mensagem de email, anexo de email ou URL, e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção e tomar medidas para impedir que o falso positivo seja recorrente. Você pode usar o [Explorador de Ameaças](#undo-an-action-using-threat-explorer) ou a guia Ações para uma [investigação](#undo-an-action-in-the-action-center) desfazer uma ação.

> [!IMPORTANT]
> Certifique-se de ter as permissões necessárias antes de tentar executar as seguintes tarefas.

### <a name="undo-an-action-using-threat-explorer"></a>Desfazer uma ação usando o Explorador de Ameaças

Com o Explorador de Ameaças, sua equipe de operações de segurança pode encontrar um email afetado por uma ação e, potencialmente, desfazer a ação.

|Cenário|Desfazer opções|Saiba mais|
|---|---|---|
|Uma mensagem de email foi roteada para a pasta Lixo Eletrônico de um usuário|- Mover a mensagem para a pasta Itens Excluídos do usuário<br/>- Mover a mensagem para a Caixa de Entrada do usuário<br/>- Excluir a mensagem|[Encontre e investigue emails mal-intencionados que foram entregues Office 365](investigate-malicious-email-that-was-delivered.md)|
|Uma mensagem de email ou um arquivo foi colocado em quarentena|- Liberar o email ou o arquivo<br/>- Excluir o email ou o arquivo|[Gerenciar mensagens em quarentena como administrador](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Desfazer uma ação no centro de ações

No Centro de ações, você pode ver ações de correção que foram tomadas e potencialmente desfazer a ação.

1. Vá para o Microsoft 365 de segurança ( <https://security.microsoft.com> ).
2. No painel de navegação, selecione **Centro de ações**.
3. Selecione a **guia Histórico** para exibir a lista de ações concluídas.
4. Selecione um item. Seu painel de sobrevoo é aberto.
5. No painel de sobrevoos, selecione **Desfazer**. (Somente ações que podem ser desfeitas terão um **botão Desfazer.)**

## <a name="see-also"></a>Confira também

- [Obter o Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigações automatizadas no Microsoft Defender para Office 365](office-365-air.md)
