---
title: Proteção antifalsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
description: Os administradores podem saber mais sobre os recursos de anti-falsificação disponíveis na Proteção do Exchange Online (EOP), que podem ajudar a reduzir os ataques de phishing de remetentes e domínios falso.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7680c2f4eae54aa53eba72b328baf1bf92fbcf98
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537962"
---
# <a name="anti-spoofing-protection-in-eop"></a>Proteção antifalsificação no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se você for um cliente do Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo da Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, o EOP incluirá recursos para ajudar a proteger sua organização contra remetentes falsificados (forjados).

Quando se trata de proteger os usuários, a Microsoft leva a sério a ameaça de phishing. A falsificação é uma técnica comum usada por invasores. **As mensagens falsas parecem se originar de alguém ou algum lugar que não é a origem real.** Essa técnica é frequentemente usada em campanhas de phishing projetadas para obter credenciais de usuário. A tecnologia antifalsificação na EOP examina especificamente a falsificação do cabeçalho De no corpo da mensagem (usada para exibir o remetente da mensagem nos clientes de email). Quando a EOP tem alta confiança de que o cabeçalho De é forjado, a mensagem é identificada como falsificada.

As seguintes tecnologias antifalsificação estão disponíveis na EOP:

- **Autenticação de email**: Um componente integrante de qualquer esforço antifalsificação é o uso de autenticação de email (também conhecida como validação de email) pelos registros SPF, DKIM e DMARC no DNS. Você pode configurar esses registros para seus domínios, para que os sistemas de email de destino possam verificar a validade das mensagens que afirmam ser de remetentes em seus domínios. Para mensagens de entrada, o Microsoft 365 requer autenticação de email para domínios do remetente. Para obter mais informações, confira [Autenticação de email no Microsoft 365](email-validation-and-authentication.md).

  A EOP analisa e bloqueia mensagens que não podem ser autenticadas pela combinação de métodos padrão de autenticação de email e técnicas de reputação do remetente.

  ![Verificações antifalsificação da EOP](../../media/eop-anti-spoofing-protection.png)

- **Informações sobre inteligência contra falsificação**: Revise mensagens falsas de remetentes em domínios internos e externos nos últimos 7 dias e permita ou bloqueie esses remetentes. Para saber mais, confira [Informações de inteligência contra falsificação no EOP](learn-about-spoof-intelligence.md).

- **Permitir ou bloquear remetentes na Lista Permitir/Bloquear Locatários**: quando você substitui o remetente nas informações de inteligência contra falsificação, o remetente falsificado se torna uma permissão manual de entrada ou bloqueio que só aparece na guia **Falsificação** na Lista Permitir/Bloquear Locatário. Você também pode criar manualmente entradas de permissão ou bloqueio para remetentes falsificados antes que eles sejam detectados pela inteligência contra falsificação. Para saber mais, confira [Gerenciar a Lista Permitir/Bloquear Locatário no EOP](tenant-allow-block-list.md).

- **Políticas anti phishing**: no EOP, as políticas anti phishing contêm as seguintes configurações contra falsificação:
  - Ativar ou desativar a inteligência contra falsificação.
  - Ativar ou desativar a identificação de remetentes não autenticados no Outlook.
  - Especificar a ação para os remetentes falsificados bloqueados.

  Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).

  **Observação**: as políticas anti phishing no Microsoft Defender para Office 365 contêm proteções de adição, incluindo proteção contra **usurpação de identidade**. Para saber mais, confira [Configurações exclusivas em políticas anti phishing no Microsoft Defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

- **Relatório de detecção de falsificação**: para saber mais, confira [Relatório de Detecções de Falsificações](view-email-security-reports.md#spoof-detections-report).

  **Observação**: as organizações do Defender para Office 365 também podem usar detecções em tempo real (Plano 1) ou o Explorador de Ameaças (Plano 2) para exibir informações sobre tentativas de phishing. Para obter mais informações, confira [Investigação e resposta a ameaças do Microsoft 365](office-365-ti.md).

## <a name="how-spoofing-is-used-in-phishing-attacks"></a>Como a falsificação é usada em ataques de phishing

As mensagens falsificadas têm as seguintes implicações negativas para os usuários:

- **Mensagens falsificadas enganam os usuários**: Uma mensagem falsificada pode induzir o destinatário a clicar em um link e expor suas credenciais, baixar malware ou responder a uma mensagem com conteúdo confidencial (o que é conhecido como comprometimento de email empresarial ou BEC).

  A seguinte mensagem é um exemplo de phishing que usa o remetente falsificado msoutlook94@service.outlook.com:

  ![Mensagem de phishing se passando por service.outlook.com](../../media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)

  Essa mensagem não veio de service.outlook.com, mas o invasor falsificou o campo do cabeçalho **De** para fazer com que parecesse ter vindo. Essa foi uma tentativa de induzir o destinatário a clicar no link **alterar senha** e expor suas credenciais.

  A seguinte mensagem é um exemplo de BEC que usa o domínio de email falsificado contoso.com:

  ![Mensagem de phishing ‒ comprometimento de email empresarial](../../media/da15adaa-708b-4e73-8165-482fc9182090.jpg)

  A mensagem parece legítima, mas o remetente é falso.

- **Os usuários confundem mensagens reais com mensagens falsas**: Mesmo os usuários que conhecem phishing podem ter dificuldade em perceber as diferenças entre mensagens reais e falsificadas.

  A seguinte mensagem é um exemplo de uma mensagem real de redefinição de senha da conta de Segurança da Microsoft:

  ![Redefinição de senha da Microsoft legítima](../../media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)

  A mensagem realmente veio da Microsoft, mas os usuários foram condicionalmente suspeitos. Como é difícil distinguir uma mensagem de redefinição de senha real de uma falsa, os usuários podem ignorar a mensagem, denunciá-la como spam ou denunciá-la desnecessariamente à Microsoft como phishing.

## <a name="different-types-of-spoofing"></a>Diferentes tipos de falsificação

A Microsoft diferencia dois tipos diferentes de mensagens falsas:

- **Falsificação dentro da organização**: Também conhecida como falsificação _self-to-self_. Por exemplo:

  - O remetente e o destinatário estão no mesmo domínio:
    > De: humberto@contoso.com <br> Para: michelle@contoso.com

  - O remetente e o destinatário estão em subdomínios do mesmo domínio:
    > De: laura@marketing.fabrikam.com <br> Para: julia@engineering.fabrikam.com

  - O remetente e o destinatário estão em domínios diferentes que pertencem à mesma organização (ou seja, os dois domínios estão configurados como [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) na mesma organização):
    > De: remetente @ microsoft.com <br> Para: destinatário @ bing.com

    Os espaços são usados nos endereços de email para impedir a coleta de spambots.

  As mensagens reprovadas na [autenticação composta](email-validation-and-authentication.md#composite-authentication) devido à falsificação dentro da organização contêm os seguintes valores de cabeçalho:

  `Authentication-Results: ... compauth=fail reason=6xx`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.11`

  - `reason=6xx` indica falsificação dentro da organização.

  - SFTY é o nível de segurança da mensagem. 9 indica phishing, .11 indica falsificação dentro da organização.

- **Falsificação entre domínios**: Os domínios do remetente e do destinatário são diferentes e não têm relação entre si (também conhecidos como domínios externos). Por exemplo:
    > De: humberto@contoso.com <br> Para: michelle@tailspintoys.com

  As mensagens reprovadas na [autenticação composta](email-validation-and-authentication.md#composite-authentication) devido à falsificação entre domínios contêm os seguintes valores de cabeçalhos:

  `Authentication-Results: ... compauth=fail reason=000/001`

  `X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22`

  - `reason=000` indica que a mensagem foi reprovada na autenticação explícita de email. `reason=001` indica que a mensagem foi reprovada na autenticação implícita de email.

  - `SFTY` é o nível de segurança da mensagem. 9 indica phishing, .22 indica falsificação entre domínios.

> [!NOTE]
> Se você recebeu uma mensagem como ***compauth=fail reason=###** _e precisa saber sobre autenticação composta (compauth) e os valores relacionados a falsificação, consulte [_Cabeçalhos de mensagens anti-spam no Microsoft 365*](anti-spam-message-headers.md). Ou vá diretamente para os códigos [*motivo*](anti-spam-message-headers.md).

Para obter mais informações sobre o DMARC, confira [Usar o DMARC para validar emails no Microsoft 365](use-dmarc-to-validate-email.md).

## <a name="problems-with-anti-spoofing-protection"></a>Problemas com a proteção antifalsificação

Sabe-se que as listas de endereçamento (também conhecidas como listas de discussão) têm problemas com a antifalsificação devido à maneira como encaminham e modificam as mensagens.

Por exemplo, Gabriela Laureano (glaureano@contoso.com) está interessada em observar pássaros, ingressa na lista de endereçamento birdwatchers@fabrikam.com e envia a seguinte mensagem à lista:

> **Por:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Para:** Lista de discussão do Birdwatcher \<birdwatchers@fabrikam.com\> <br> **Assunto:** Belo exemplo de gaios azuis no topo do Monte Rainier esta semana <p> Alguém quer ver a vista do Monte Rainier dessa semana?

O servidor da lista de endereçamento recebe a mensagem, modifica seu conteúdo e a repete aos membros da lista. A mensagem repetida tem o mesmo endereço De (glaureano@contoso.com), mas uma marca é adicionada à linha de assunto e um rodapé é adicionado à parte inferior da mensagem. Esse tipo de modificação é comum em listas de endereçamento, e pode resultar em falsos positivos para falsificação.

> **Por:** "Gabriela Laureano" \<glaureano@contoso.com\> <br> **Para:** Lista de discussão do Birdwatcher \<birdwatchers@fabrikam.com\> <br> **Assunto:** [OBSERVAÇÃODEPÁSSAROS] Belo exemplo de gaios azuis no topo do Monte Rainier esta semana <p> Alguém quer ver a vista do Monte Rainier dessa semana? <p> Esta mensagem foi enviada para a lista de discussão de Observação de Pássaros. Você pode cancelar a assinatura a qualquer momento.

Para ajudar as mensagens da lista de endereçamento a passarem nas verificações antifalsificação, execute as seguintes etapas com base no controle da lista de endereçamento:

- Sua organização possui a lista de endereçamento:

  - Verifique as Perguntas Frequentes em DMARC.org: [Opero uma lista de endereçamento e quero interoperar com o DMARC, o que devo fazer?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F).

  - Leia as instruções nesta postagem do blog: [Uma dica para os operadores de listas de endereçamento interoperarem com o DMARC para evitar falhas](/archive/blogs/tzink/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures).

  - Considere a instalação de atualizações em seu servidor de lista de endereçamento para dar suporte ao ARC, veja <http://arc-spec.org>.

- Sua organização não possui a lista de endereçamento:

  - Peça ao mantenedor da lista de endereçamento para que ele configure a autenticação de email para o domínio do qual a lista de endereçamento está retransmitindo.

    Quando um número suficiente de remetentes responde aos proprietários do domínio que devem configurar registros de autenticação de email, isso os incentiva a agir. Embora a Microsoft também trabalhe com proprietários de domínio para publicar os registros necessários, é ainda mais eficaz quando usuários individuais solicitam isso.

  - Crie regras de caixa de entrada no seu cliente de email para mover as mensagens para a Caixa de Entrada. Você também pode solicitar que seus administradores configurem substituições, conforme descrito em [Informações de Inteligência contra falsificação](learn-about-spoof-intelligence.md) no EOP e em [Gerenciar a Lista Permitir/Bloquear Locatário](tenant-allow-block-list.md).

  - Crie um tíquete de suporte do Microsoft 365 para criar uma substituição para a lista de endereçamento para que ela seja tratada como legítima. Para obter mais informações, confira [Contatar o suporte para produtos comerciais - Ajuda para administradores](../../business-video/get-help-support.md).

Se tudo falhar, você poderá relatar a mensagem como um falso positivo para a Microsoft. Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

Você também pode entrar em contato com seu administrador, que pode criar um tíquete de suporte na Microsoft. A equipe de engenharia da Microsoft investigará por que a mensagem foi marcada como uma falsificação.

## <a name="considerations-for-anti-spoofing-protection"></a>Considerações sobre a proteção antifalsificação

Se você é um administrador que atualmente envia mensagens para o Microsoft 365, precisa garantir que seu email seja autenticado corretamente. Caso contrário, ele pode ser marcado como spam ou phishing. Para obter mais informações, confira [Soluções para remetentes legítimos enviando emails não autenticados](email-validation-and-authentication.md#solutions-for-legitimate-senders-who-are-sending-unauthenticated-email).

Os remetentes na lista de Remetentes Confiáveis de um usuário individual (ou administrador) ignorarão partes da pilha de filtragem, incluindo a proteção contra falsificações. Para obter mais informações, confira [Remetentes Confiáveis do Outlook](create-safe-sender-lists-in-office-365.md#use-outlook-safe-senders).

Os administradores devem evitar (quando possível) o uso de listas de remetentes permitidos ou listas de domínios permitidos. Esses remetentes ignoram toda proteção contra spam, falsificações e phishing, além da autenticação do remetente (SPF, DKIM, DMARC). Para mais informações, confira [Usar listas de remetentes permitidos ou listas de domínios permitidos](create-safe-sender-lists-in-office-365.md#use-allowed-sender-lists-or-allowed-domain-lists).
