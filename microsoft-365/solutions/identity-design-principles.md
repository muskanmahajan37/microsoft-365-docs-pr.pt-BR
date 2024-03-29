---
title: Planejamento de recursos corporativos do Microsoft 365 - Arquitetura de segurança
description: Saiba mais sobre as principais estratégias de design para a arquitetura do Microsoft Enterprise com Alex Shteynberg, Arquiteto Técnico Principal da Microsoft.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: c94b387bbd73e2c4f9b3de243131ae023ddb4cb8
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222520"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>Para identidade e além — o ponto de vista de um arquiteto

Neste artigo, [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), Arquiteto Técnico Principal da Microsoft, discute as principais estratégias de design para organizações corporativas que adotam o Microsoft 365 e outros serviços de nuvem da Microsoft.

## <a name="about-the-author"></a>Sobre o autor

![Foto de Alex Shteynberg](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

Sou um arquiteto técnico principal no Centro de Tecnologia [da Microsoft de Nova York.](https://www.microsoft.com/mtc?rtc=1) Trabalho principalmente com clientes grandes e requisitos complexos. Meus pontos de vista e opiniões se baseiam nessas interações e podem não se aplicar a todas as situações. No entanto, na minha experiência, se podemos ajudar os clientes com os desafios mais complexos, podemos ajudar todos os clientes.

Normalmente trabalho com mais de 100 clientes por ano. Embora toda organização tenha características exclusivas, é interessante ver tendências e semelhanças. Por exemplo, uma tendência é o interesse entre empresas para muitos clientes. Afinal, uma filial bancária também pode ser uma cafeteria e um centro de comunidade.

Na minha função, foco em ajudar os clientes a chegarem à melhor solução técnica para atender ao conjunto exclusivo de metas de negócios. Oficialmente, foco em Identidade, Segurança, Privacidade e Conformidade. Eu amo o fato de que eles tocam em tudo o que fazemos. Isso me dá a oportunidade de estar envolvido com a maioria dos projetos. Isso me mantém bastante ocupado e curtindo essa função.

Vivo na cidade de Nova York (o melhor!) e realmente gosto da diversidade de sua cultura, alimentação e pessoas (não o tráfego). Eu amo viajar quando posso e espero ver a maior parte do mundo em minha vida. No momento, estou pesquisando uma viagem para a África para saber mais sobre a vida selvagem.

## <a name="guiding-principles"></a>Princípios orientadores

- **Simples geralmente é melhor:** você pode fazer (quase) qualquer coisa com tecnologia, mas isso não significa que você deve. Especialmente no espaço de segurança, muitos clientes superengenhar soluções. Eu gosto [deste vídeo](https://www.youtube.com/watch?v=SOQgABDSYZE) da conferência stripe do Google para sublinhar este ponto.
- **Pessoas, processos, tecnologia**: [Projetar para que as pessoas](https://en.wikipedia.org/wiki/Human-centered_design) aprimoram o processo, não a tecnologia primeiro. Não há soluções "perfeitas". Precisamos equilibrar vários fatores de risco e as decisões serão diferentes para cada empresa. Muitos clientes projetam uma abordagem que seus usuários mais tarde evitam.
- **Concentre-se em "por que" primeiro e "como" mais** tarde : Seja o filho irritante de 7 anos com um milhão de perguntas. Não podemos chegar à resposta certa se não sabemos as perguntas corretas a fazer. Muitos clientes fazem suposições sobre como as coisas precisam funcionar em vez de definir o problema comercial. Sempre há vários caminhos que podem ser tomados.
- **Cauda longa das práticas recomendadas passadas:** reconheça que as práticas recomendadas estão mudando na velocidade da luz. Se você já viu o Azure AD há mais de três meses, provavelmente está desa datado. Tudo aqui está sujeito a alterações após a publicação. A opção "Melhor" hoje pode não ser os mesmos seis meses a partir de agora.

## <a name="baseline-concepts"></a>Conceitos de linha de base

Não pule esta seção. Muitas vezes, devo voltar a esses tópicos, mesmo para clientes que usam serviços de nuvem há anos.
Infelizmente, o idioma não é uma ferramenta precisa. Muitas vezes usamos a mesma palavra para significar conceitos diferentes ou palavras diferentes para significar o mesmo conceito. Geralmente, uso este diagrama abaixo para estabelecer uma terminologia de linha de base e um "modelo de hierarquia".
<br><br>

![Ilustração de locatário, assinatura, serviço e dados](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

Quando você aprender a nadar, é melhor começar na piscina e não no meio do oceano. Não estou tentando ser tecnicamente preciso com este diagrama. É um modelo para discutir alguns conceitos básicos.

No diagrama:

- Tenant = uma instância do Azure AD. Ele está na "parte superior" de uma hierarquia, ou Nível 1 no diagrama. Podemos considerar isso como o "[limite](/azure/active-directory/users-groups-roles/licensing-directory-independence)" onde tudo o resto ocorre ([Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) à parte). Todos os serviços de nuvem empresarial da Microsoft fazem parte de um desses locatários. Os serviços de consumidor são separados. "Locatário" aparece na documentação como locatário do Office 365, locatário do Azure, locatário WVD e assim por diante. Geralmente, essas variações causam confusão para os clientes.
- Serviços/assinaturas, Nível 2 no diagrama, pertencem a um e apenas um locatário. A maioria dos serviços SaaS é 1:1 e não pode se mover sem migração. O Azure é diferente, você pode [mover cobrança e/ou](/azure/cost-management-billing/manage/billing-subscription-transfer) uma [assinatura](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) para outro locatário. Há muitos clientes que precisam mover assinaturas do Azure. Isso tem várias implicações. Objetos que existem fora da assinatura não se movem (por exemplo, controle de acesso baseado em função ou objetos do Azure RBAC e do Azure AD, incluindo grupos, aplicativos, políticas e assim por diante). Além disso, alguns serviços (como o Azure Key Vault, Data Bricks e assim por diante). Não migre serviços sem uma boa necessidade de negócios. Alguns scripts que podem ser úteis para a migração são [compartilhados no GitHub](https://github.com/lwajswaj/azure-tenant-migration).
- Um determinado serviço geralmente tem algum tipo de limite de "sub-nível" ou Nível 3 (L3). Isso é útil para entender a segregação de segurança, políticas, governança e assim por diante. Infelizmente, não há nenhum nome uniforme que eu saiba. Alguns exemplos de nomes para L3 são: Assinatura do Azure = [recurso](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [instância](/dynamics365/admin/new-instance-management); Power BI = [espaço de trabalho;](/power-bi/service-create-the-new-workspaces) Power Apps = [ambiente](/power-platform/admin/environments-overview); e assim por diante.
- O nível 4 é onde os dados reais residem. Esse 'plano de dados' é um tópico complexo. Alguns serviços estão usando o Azure AD para RBAC, outros não. Discutirei um pouco quando chegarmos aos tópicos de delegação.

Alguns conceitos adicionais que eu encontro muitos clientes (e funcionários da Microsoft) estão confusos ou têm perguntas sobre incluir o seguinte:

- Qualquer pessoa [pode criar](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) muitos locatários [sem custo.](https://azure.microsoft.com/pricing/details/active-directory/) Você não precisa de um serviço provisionado nele. Tenho dezenas. Cada nome de locatário é exclusivo no serviço de nuvem mundial da Microsoft (em outras palavras, nenhum dois locatários pode ter o mesmo nome). Todos eles estão no formato de TenantName.onmicrosoft.com. Também há processos que criam locatários automaticamente ([locatários](/azure/active-directory/users-groups-roles/directory-self-service-signup)não administrativos ). Por exemplo, isso pode ocorrer quando um usuário se insissar em um serviço empresarial com um domínio de email que não existe em qualquer outro locatário.
- Em um locatário gerenciado, muitos [domínios DNS](/azure/active-directory/fundamentals/add-custom-domain) podem ser registrados nele. Isso não altera o nome do locatário original. Atualmente, não há uma maneira fácil de renomear um locatário (diferente da migração). Embora o nome do locatário tecnicamente não seja crítico nos dias de hoje, alguns podem achar que isso é limitador.
- Você deve reservar um nome de locatário para sua organização, mesmo se ainda não estiver planejando implantar quaisquer serviços. Caso contrário, alguém pode tirar isso de você e não há um processo simples para reamentá-lo (mesmo problema que nomes DNS). Eu ouvi isso com muita frequência dos clientes. O nome do locatário também deve ser um tópico de debate.
- Se você possui namespaces DNS, você deve adicionar todos eles aos seus locatários. Caso contrário, pode-se criar um [locatário](/azure/active-directory/users-groups-roles/directory-self-service-signup) não gerenciado com esse nome, o que causa interrupção para [torná-lo gerenciado.](/azure/active-directory/users-groups-roles/domains-admin-takeover)
- Namespace DNS (como contoso.com) pode pertencer a um e somente um Locatário. Isso tem implicações para vários cenários (por exemplo, compartilhar um domínio de email durante uma fusão ou aquisição e assim por diante). Há uma maneira de registrar um sub DNS (como div.contoso.com) em um locatário diferente, mas isso deve ser evitado. Ao registrar um nome de domínio de nível superior, presume-se que todos os subdomas pertencem ao mesmo locatário. Em cenários de vários locatários (consulte abaixo), normalmente recomendaria usar outro nome de domínio de nível superior (como contoso.ch ou ch-contoso.com).
- Quem deve "possuir" um locatário? Geralmente, vejo clientes que não sabem quem é o proprietário do locatário. Esse é um sinalizador vermelho grande. Chame o suporte da Microsoft o mais rápido possível. Assim como problemático é quando um proprietário de serviço (geralmente um administrador do Exchange) é designado para gerenciar um locatário. O locatário conterá todos os serviços que você pode querer no futuro. O proprietário do locatário deve ser um grupo que pode tomar uma decisão para habilitar todos os serviços de nuvem em uma organização. Outro problema é quando um grupo de proprietários de locatários é solicitado a gerenciar todos os serviços. Isso não é dimensionar para grandes organizações.
- Não há conceito de um sub/super locatário. Por algum motivo, esse mito continua se repetindo. Isso também se aplica [aos locatários do Azure AD B2C.](/azure/active-directory-b2c/) Eu ouvi muitas vezes: "Meu ambiente B2C está no meu locatário XYZ" ou "Como faço para mover meu locatário do Azure para meu locatário do Office 365?"
- Este documento se concentra principalmente na nuvem comercial em todo o mundo, pois é isso que a maioria dos clientes está usando. Às vezes, é útil saber sobre [nuvens soberanas.](/azure/active-directory/develop/authentication-national-cloud) Nuvens soberanas têm implicações adicionais para discutir quais estão fora do escopo para essa discussão.

## <a name="baseline-identity-topics"></a>Tópicos de identidade da linha de base

Há muita documentação sobre a plataforma de identidade da Microsoft – Azure Active Directory (Azure AD). Para aqueles que estão apenas começando, isso geralmente parece avassalador. Mesmo depois de aprender sobre isso, acompanhar a inovação e a mudança constantes podem ser desafiadores. Em minhas interações com o cliente, muitas vezes me vejo servindo como "tradutor" entre metas comerciais e abordagens "Bom, Melhor, Melhor" para abordar essas abordagens (e "anotações de borda" humanas para esses tópicos). Raramente há uma resposta perfeita e a decisão "correta" é um equilíbrio de vários fatores de risco. Abaixo estão algumas das perguntas comuns e áreas de confusão que eu tendem a discutir com os clientes.

### <a name="provisioning"></a>Provisionamento

O Azure AD não resolve a falta de governança em seu mundo de identidade! [A governança de identidade](/azure/active-directory/governance/identity-governance-overview) deve ser um elemento crítico independente de qualquer decisão na nuvem. Os requisitos de governança mudam ao longo do tempo, por isso é um programa e não uma ferramenta.

[Azure AD Connect](/azure/active-directory/hybrid/whatis-azure-ad-connect) vs. [Microsoft Identity Manager](/microsoft-identity-manager/microsoft-identity-manager-2016) (MIM) vs. algo mais (de terceiros ou personalizado)? Salve a si mesmo muita dor de cabeça agora e no futuro e vá com o Azure AD Connect. Há todos os tipos de smarts nesta ferramenta para lidar com configurações de clientes e inovações contínuas.

Alguns casos de borda que podem levar a uma arquitetura mais complexa:

- Tenho várias florestas do AD sem conectividade de rede entre elas. Há uma nova opção chamada [Provisionamento de Nuvem.](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Não tenho o Active Directory nem quero instalá-lo. O Azure AD Connect pode ser configurada para sincronizar [a partir do LDAP](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) (parceiro pode ser necessário).
- Preciso provisionar os mesmos objetos para vários locatários. Isso não é tecnicamente suportado, mas depende da definição de "mesmo".

Devo personalizar as regras de sincronização padrão ([objetos de filtro,](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [atributos de alteração,](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)ID de [logon](/azure/active-directory/hybrid/plan-connect-userprincipalname)alternativo e assim por diante)? Evite!! Uma plataforma de identidade é tão valiosa quanto os serviços que a usam. Embora você possa fazer todos os tipos de configurações nozes, para responder a essa pergunta, você precisa ver o impacto nos aplicativos. Se você filtrar objetos habilitados para email, a GAL para serviços online ficará incompleta; se o aplicativo se basear em atributos específicos, filtre-os terá impacto imprevisível; e assim por diante. Não é uma decisão de equipe de identidade.

O XYZ SaaS dá suporte ao provisionamento just-in-time (JIT), por que você está exigindo que eu sincronizar? Veja acima. Muitos aplicativos precisam de informações de "perfil" para a funcionalidade. Não será possível ter uma GAL se todos os objetos habilitados para email não estão disponíveis. O mesmo se aplica [ao provisionamento do usuário](/azure/active-directory/app-provisioning/user-provisioning) em aplicativos integrados ao Azure AD.

### <a name="authentication"></a>Autenticação

[Sincronização de hash de](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) senha (PHS) vs. [autenticação](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) de passagem (PTA) vs. [federação](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).

Normalmente, há um debate [entusiasmado em torno](/azure/active-directory/hybrid/choose-ad-authn) da federação. Mais simples geralmente é melhor e, portanto, use PHS, a menos que você tenha um bom motivo para não usar. Também é possível configurar diferentes métodos de autenticação para diferentes domínios DNS no mesmo locatário. 

Alguns clientes habilitam federação + PHS principalmente para:

- Uma opção [para retornar](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) (para recuperação de desastres) se o serviço de federação não estiver disponível.
- Recursos adicionais (ex.: [Azure AD DS](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) e serviços de segurança (ex.: [credenciais vazadas](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- Suporte para serviços no Azure que não entendem a autenticação federada (por exemplo, [Arquivos do Azure](/azure/storage/files/storage-files-active-directory-overview)).

Geralmente, passo os clientes pelo fluxo de autenticação do cliente para esclarecer alguns equívocos. O resultado se parece com a imagem abaixo, que não é tão bom quanto o processo interativo de chegar lá.

![Exemplo de conversa de quadro de diálogo](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

Esse tipo de desenho de quadro de trabalho ilustra onde as políticas de segurança são aplicadas no fluxo de uma solicitação de autenticação. Neste exemplo, as políticas impostas por meio do Serviço de Federação do Active Directory (AD FS) são aplicadas à primeira solicitação de serviço, mas não às solicitações de serviço subsequentes. Esse é pelo menos um motivo para mover os controles de segurança para a nuvem o máximo possível.

Estamos seguindo o sonho de [logom](/azure/active-directory/manage-apps/what-is-single-sign-on) único (SSO) desde que me lembre. Alguns clientes acreditam que podem fazer isso escolhendo o provedor de federação "correto" (STS). O Azure AD pode ajudar significativamente a habilitar recursos [de SSO,](/azure/active-directory/manage-apps/plan-sso-deployment) mas nenhum STS é mágico. Há muitos métodos de autenticação "herdáveis" que ainda são usados para aplicativos críticos. Estender o Azure AD com soluções [de parceiros](/azure/active-directory/saas-apps/tutorial-list) pode resolver muitos desses cenários. O SSO é uma estratégia e uma jornada. Você não pode chegar lá sem se mover em direção [aos padrões para aplicativos](/azure/active-directory/develop/v2-app-types). Relacionado a este tópico [](/azure/active-directory/authentication/concept-authentication-passwordless) está uma jornada para a autenticação sem senha, que também não tem uma resposta mágica.

[A autenticação multifa factor](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) é essencial hoje em dia ([aqui](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) para mais). Adicione a ela [a análise de](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) comportamento do usuário e você tem uma solução que impede ataques cibernéticos mais comuns. Até os serviços de consumidor estão se movendo para exigir MFA. No entanto, ainda me encontro com muitos clientes que não querem mudar para abordagens [modernas de autenticação.](../enterprise/hybrid-modern-auth-overview.md) O maior argumento que ouvi é que afetará usuários e aplicativos herdados. Às vezes, um bom movimento pode ajudar os clientes a seguir em frente - Alterações [anunciadas pelo](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)Exchange Online. Muitos relatórios do Azure [AD](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) agora estão disponíveis para ajudar os clientes com essa transição.

### <a name="authorization"></a>Autorização

Por [Wikipédia,](https://en.wikipedia.org/wiki/Authorization)"autorizar" é definir uma política de acesso. Muitas pessoas o olham como a capacidade de definir controles de acesso para um objeto (arquivo, serviço e assim por diante). No mundo atual das ameaças cibernéticas, esse conceito está evoluindo rapidamente para uma política dinâmica que pode reagir a vários vetores de ameaças e ajustar rapidamente os controles de acesso em resposta a eles. Por exemplo, se eu acessar minha conta bancária de um local incomum, receberão etapas de confirmação adicionais. Para abordar isso, precisamos considerar não apenas a política em si, mas o ecossistema de metodologias de detecção de ameaças e correlação de sinais.

O mecanismo de política do Azure AD é implementado usando políticas [de Acesso Condicional](/azure/active-directory/conditional-access/overview). Esse sistema depende de informações de vários outros sistemas de detecção de ameaças para tomar decisões dinâmicas. Uma exibição simples seria algo como a ilustração a seguir:

![Mecanismo de política no Azure AD](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

Combinar todos esses sinais em conjunto permite políticas dinâmicas como estas:

- Se uma ameaça for detectada em seu dispositivo, o acesso aos dados será reduzido para a Web apenas sem a capacidade de baixar.
- Se você estiver baixando um volume de dados excepcionalmente alto, tudo o que você baixar será criptografado e restrito.
- Se você acessar um serviço de um dispositivo não autorizado, será bloqueado de dados altamente confidenciais, mas poderá acessar dados não restritos sem a capacidade de copiá-lo para outro local.

Se você concordar com essa definição expandida de autorização, precisará implementar soluções adicionais. Quais soluções você implementar dependerá da dinâmica que você deseja que a política seja e quais ameaças você deseja priorizar. Alguns exemplos desses sistemas são:

- [Azure AD Identity Protection](/azure/active-directory/identity-protection/) 
- [Microsoft Defender para Identidade?](/azure-advanced-threat-protection/)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md?view=o365-worldwide)
- [Microsoft Cloud App Security](/cloud-app-security/) (MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md?view=o365-worldwide)
- [Microsoft Intune](/mem/intune/)
- [Microsoft Information Protection](../compliance/information-protection.md?view=o365-worldwide) (MIP)
- [Azure Sentinel](/azure/sentinel/)

Obviamente, além do Azure AD, vários serviços e aplicativos têm seus próprios modelos de autorização específicos. Alguns deles são discutidos posteriormente na seção delegação.

### <a name="audit"></a>Auditoria

O Azure AD tem recursos detalhados [de auditoria e relatórios.](/azure/active-directory/reports-monitoring/) No entanto, essa geralmente não é a única fonte de informações necessárias para tomar decisões de segurança. Consulte mais discussão sobre isso na seção delegação.

## <a name="theres-no-exchange"></a>Não há nenhum Exchange

Não entre em pânico! Isso não significa que o Exchange está sendo preterido (ou SharePoint e assim por diante). Ainda é um serviço principal. O que quero dizer é que, há algum tempo, os provedores de tecnologia têm feito a transição de experiências do usuário (UX) para abranger componentes de vários serviços. No Microsoft 365, um exemplo simples é " anexos modernos " onde os anexos ao email são[armazenados](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)no SharePoint Online ou no OneDrive for Business.

![Anexando um arquivo a um email](../media/solutions-architecture-center/modern-attachments.png)

Ao olhar para o cliente do Outlook, você pode ver muitos serviços que estão "conectados" como parte dessa experiência, não apenas o Exchange. Isso inclui grupos do Azure AD, Pesquisa da Microsoft, Aplicativos, Perfil, Conformidade e Office 365. 

![Interface do Outlook com callouts](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

Leia sobre [o Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) para visualização dos recursos futuros. Na visualização agora, posso ler e responder a conversas do Teams diretamente no Outlook. Na verdade, o [cliente do Teams](https://products.office.com/microsoft-teams/download-app) é um dos exemplos mais proeminentes dessa estratégia. 

Em geral, está se tornando mais difícil desenhar uma linha clara entre o Office 365 e outros serviços nas nuvens da Microsoft. Eu o vejo como um grande benefício para os clientes, pois eles podem se beneficiar da inovação total em tudo o que fazemos, mesmo que eles usem um componente. Muito legal e tem implicações de longo alcance para muitos clientes.

Hoje, vejo que muitos grupos de IT do cliente estão estruturados em torno de "produtos". É lógico para um mundo local, pois você precisa de um especialista para cada produto específico. No entanto, estou totalmente feliz por não ter que depurar um banco de dados do Active Directory ou do Exchange novamente, pois esses serviços foram movidos para a nuvem. A automação (que tipo de nuvem é) remove determinados trabalhos manuais repetitivos (veja o que aconteceu com as fábricas). No entanto, eles são substituídos por requisitos mais complexos para entender a interação entre serviços, impacto, necessidades de negócios e assim por diante. Se você estiver disposto a [aprender](/learn/), há ótimas oportunidades habilitadas pela transformação na nuvem. Antes de entrar na tecnologia, geralmente converso com os clientes sobre como gerenciar as alterações nas habilidades de EQUIPE e estruturas de equipe.

Para todos os desenvolvedores e pessoas de fãs do SharePoint, pare de perguntar "Como posso fazer XYZ no SharePoint online?" Use [o Power Automate](/power-automate/) (ou Flow) para fluxo de trabalho, é uma plataforma muito mais poderosa. Use [o Azure Bot Framework](/azure/bot-service/?view=azure-bot-service-4.0) para criar um UX melhor para sua lista de itens de 500 K. Comece a [usar o Microsoft Graph em](https://developer.microsoft.com/graph/) vez de CSOM. [O Microsoft Teams](/MicrosoftTeams/Teams-overview) inclui o SharePoint, mas também um mundo mais. Há muitos outros exemplos que posso listar. Há um vasto e maravilhoso universo lá fora. Abra a porta e [comece a explorar]().

O outro impacto comum está na área de conformidade. Essa abordagem entre serviços parece confundir completamente muitas políticas de conformidade. Continuo vendo organizações que afirmam: "Preciso fazer o diário de todas as comunicações de email para um sistema de Descoberta Eletrônica". O que isso realmente significa quando o email não é mais apenas um email, mas uma janela para outros serviços? O Office 365 tem uma abordagem abrangente para [conformidade,](../compliance/index.yml)mas alterar pessoas e processos geralmente é muito mais difícil do que a tecnologia.

Há muitas outras pessoas e implicações de processo. Na minha opinião, essa é uma área crítica e pouco discutida. Talvez mais em outro artigo.

## <a name="tenant-structure-options"></a>Opções de estrutura de locatário

### <a name="single-tenant-vs-multi-tenant"></a>Locatário único versus multi-locatário

Em geral, a maioria dos clientes deve ter apenas um locatário de produção. Há muitos motivos pelos quais vários locatários são desafiadores (dê uma pesquisa [do Bing](https://www.bing.com/search?q=office%20365%20multiple%20tenants)) ou leia esse [whitepaper](https://aka.ms/multi-tenant-user). Ao mesmo tempo, muitos clientes corporativos com os que trabalho têm outro locatário (pequeno) para aprendizado, teste e experimentação de IT. O acesso entre locatários do Azure é mais fácil com o [Farol do Azure.](https://azure.microsoft.com/services/azure-lighthouse/) O Office 365 e muitos outros serviços SaaS têm limites para cenários entre locatários. Há muito a considerar em cenários [do Azure AD B2B.](/azure/active-directory/b2b/what-is-b2b)

Muitos clientes terminam com vários locatários de produção após uma fusão e aquisição (M&A) e querem consolidar. Hoje isso não é simples e exigiria o Microsoft Consulting Services (MCS) ou um parceiro mais software de terceiros. Há um trabalho de engenharia em andamento para resolver vários cenários com clientes multi-locatários no futuro.

Alguns clientes optam por ir com mais de um locatário. Essa deve ser uma decisão muito cuidadosa e quase sempre orientada por motivos de negócios! Alguns exemplos incluem o seguinte:

- Uma estrutura de empresa de tipo de exploração em que a colaboração fácil entre diferentes entidades não é necessária e há fortes necessidades administrativas e de isolamento.
- Após uma aquisição, uma decisão de negócios é tomada para manter duas entidades separadas.
- Simulação do ambiente de um cliente que não altera o ambiente de produção do cliente. 
- Desenvolvimento de software para clientes.

Nesses cenários de vários locatários, os clientes geralmente querem manter alguma configuração igual entre locatários ou relatar alterações e desvios de configuração. Isso geralmente significa mudar de alterações manuais para a configuração como código. O suporte ao Microsoft Premier oferece um workshop para esses tipos de requisitos com base neste IP público: [https://Microsoft365dsc.com](https://Microsoft365dsc.com) .

### <a name="multi-geo"></a>Multi-Geo

Para [Multi-Geo](../enterprise/microsoft-365-multi-geo.md) ou não para Multi-Geo, essa é a questão. Com o Office 365 Multigeogeo, você pode provisionar e armazenar dados em repouso nas localizações geográficas escolhidas para atender aos requisitos de [residência de](../enterprise/o365-data-locations.md) dados. Há muitos equívocos sobre esse recurso. Lembre-se do seguinte:

- Ele não oferece benefícios de desempenho. Pode tornar o desempenho pior se o [design da rede](https://aka.ms/office365networking) não estiver correto. Obter dispositivos "próximos" à rede da Microsoft, não necessariamente aos seus dados.
- Não é uma solução para a conformidade [do RGPD.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) O RGPD não se concentra na soberania de dados ou locais de armazenamento. Há outras estruturas de conformidade para isso.
- Ele não resolve a delegação de administração (consulte abaixo) ou as [barreiras de informações.](../compliance/information-barriers.md)
- Ele não é o mesmo que vários locatários e requer fluxos de trabalho de [provisionamento de usuários](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) adicionais.
- Ele não move [seu locatário](../enterprise/moving-data-to-new-datacenter-geos.md) (seu Azure AD) para outra geografia. 

## <a name="delegation-of-administration"></a>Delegação de administração

Na maioria das grandes organizações, a separação de funções e o RBAC (controle de acesso baseado em função) é uma realidade necessária. Vou pedir desculpas com antecedência. Isso não é tão simples quanto alguns clientes querem que seja. Clientes, jurídicos, conformidade e outros requisitos são diferentes e, às vezes, conflitantes em todo o mundo. A simplicidade e a flexibilidade geralmente estão em lados opostos um do outro. Não me faça mal, podemos fazer um trabalho melhor nisso. Houve (e haverá) melhorias significativas ao longo do tempo. Visite o Centro [de Tecnologia da Microsoft local](https://www.microsoft.com/mtc) para trabalhar o modelo que atende aos requisitos de negócios sem ler 379230 documentos! Aqui, vou me concentrar no que você deve pensar e não no motivo pelo qual é assim. Abaixo estão cinco áreas diferentes para planejar e algumas das perguntas comuns que eu tenho encontrado.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Centros de administração do Azure AD e do Microsoft 365

Há uma lista longa e crescente de [funções criadas.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Cada função consiste em uma lista de permissões de função agrupadas para permitir que ações específicas sejam executadas. Você pode ver essas permissões na guia "Descrição" dentro de cada função. Como alternativa, você pode ver uma versão acessível mais humana delas no Centro de Administração do Microsoft 365. As definições para funções de dentro não podem ser modificadas. Geralmente, os agrupa em três categorias:

- **Administrador global**: essa função "toda poderosa" deve ser [altamente protegida,](../enterprise/protect-your-global-administrator-accounts.md) assim como você faria em outros sistemas. As recomendações típicas incluem: nenhuma atribuição permanente e usar o Azure AD Privileged Identity Management (PIM); autenticação forte; e assim por diante. Interessantemente, essa função não dá acesso a tudo por padrão. Normalmente, vejo confusão sobre acesso à conformidade e acesso ao Azure, discutido posteriormente. No entanto, essa função sempre pode atribuir acesso a outros serviços no locatário. 
- **Administradores de serviço específicos**: Alguns serviços (Exchange, SharePoint, Power BI e assim por diante) consomem funções de administração de alto nível do Azure AD. Isso não é consistente em todos os serviços e há funções mais específicas do serviço discutidas posteriormente.
- **Funcional**: há uma longa (e crescente) lista de funções voltadas para operações específicas (convidador convidado e assim por diante). Periodicamente, mais delas são adicionadas com base nas necessidades do cliente.

Não é possível delegar tudo (embora a lacuna está diminuindo), o que significa que a função de administrador global precisaria ser usada às vezes. A configuração como código e a automação devem ser consideradas em vez da associação de pessoas a essa função.

**Observação**: o Centro de administração do Microsoft 365 tem uma interface mais amigável, mas tem um subconjunto de recursos em comparação com a experiência de administrador do Azure AD. Ambos os portais usam as mesmas funções do Azure AD, portanto, as alterações estão ocorrendo no mesmo local. Dica: se você quiser uma interface do usuário de administrador com foco em gerenciamento de identidade sem toda a desordem do Azure, use [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

O que há no nome? Não faça suposições do nome da função. Idioma não é uma ferramenta muito precisa. O objetivo deve ser definir operações que precisam ser delegadas antes de ver quais funções são necessárias. Adicionar alguém à função "Leitor de Segurança" não faz com que eles vejam configurações de segurança em tudo.

A capacidade de criar [funções personalizadas](/azure/active-directory/users-groups-roles/roles-custom-overview) é uma pergunta comum. Isso está limitado no Azure AD hoje (consulte abaixo), mas aumentará em recursos ao longo do tempo. Eu os vejo como aplicáveis às funções no Azure AD e pode não abranger "para baixo" o modelo de hierarquia (discutido acima). Sempre que lido com "personalizado", tendem a voltar para minha entidade principal de "simples é melhor".

Outra pergunta comum é a capacidade de escopo de funções para um subconjunto de um diretório. Um exemplo é algo como "Administrador de Helpdesk somente para usuários na UE". [As Unidades Administrativas](/azure/active-directory/users-groups-roles/directory-administrative-units) (AU) destinam-se a resolver isso. Como acima, eu penso nisso como aplicável às funções no Azure AD e pode não abranger "para baixo". Obviamente, determinadas funções não fazem sentido para escopo (administradores globais, administradores de serviço e assim por diante).

Hoje, todas essas funções exigem associação direta (ou atribuição dinâmica se você usar o [PIM do Azure AD](/azure/active-directory/privileged-identity-management/)). Isso significa que os clientes devem gerenciá-los diretamente no Azure AD e eles não podem se basear em uma associação a um grupo de segurança. Não sou um fã da criação de scripts para gerenciá-los, pois precisaria ser executado com direitos elevados. Geralmente, recomendamos a integração da API com sistemas de processo como ServiceNow ou o uso de ferramentas de governança de parceiros, como Saviynt. Há trabalho de engenharia em curso para resolver isso ao longo do tempo.

Eu mencionei [o PIM do Azure AD](/azure/active-directory/privileged-identity-management/) algumas vezes. Há uma solução PAM (Gerenciamento de Acesso [Privilegiado)](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) do Microsoft Identity Manager (MIM) correspondente para controles locais. Você também pode querer ver As Estações de Trabalho do [Acesso](/windows-server/identity/securing-privileged-access/privileged-access-workstations) Privilegiado (PAWs) e a Governança de Identidade do [Azure AD.](/azure/active-directory/governance/identity-governance-overview) Há várias ferramentas de terceiros também, que podem habilitar a elevação de função just-in-time, just-enough e dynamic role. Isso geralmente faz parte de uma discussão maior para proteger um ambiente. 

Às vezes, os cenários chamam para adicionar um usuário externo a uma função (consulte a seção de vários locatários, acima). Isso funciona muito bem. [O Azure AD B2B](/azure/active-directory/b2b/) é outro tópico grande e divertido para passar pelos clientes, talvez em outro artigo.

### <a name="security-and-compliance-center-scc"></a>Centro de Conformidade e Segurança (SCC)

As permissões no Centro de Conformidade e Segurança do [Office 36 & 5](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) são uma coleção de "grupos de funções", separados e distintos das funções do Azure AD. Isso pode ser confuso porque alguns desses grupos de função têm o mesmo nome que funções do Azure AD (por exemplo, Leitor de Segurança), mas eles podem ter uma associação diferente. Eu prefiro o uso de funções do Azure AD. Cada grupo de funções consiste em uma ou mais "funções" (veja o que quero dizer sobre reutilização da mesma palavra?) e têm membros do Azure AD, que são objetos habilitados para email. Além disso, você pode criar um grupo de funções com o mesmo nome de uma função, que pode ou não conter essa função (evitar essa confusão).

De certa forma, eles são uma evolução do modelo de grupos de função do Exchange. No entanto, o Exchange Online tem sua própria interface [de gerenciamento de grupo de](/exchange/permissions-exo) funções. Alguns grupos de função no Exchange Online são bloqueados e gerenciados do Azure AD ou do Centro de Conformidade do & segurança, mas outros podem ter os mesmos nomes ou nomes semelhantes e são gerenciados no Exchange Online (adicionando à confusão). Eu recomenda que você evite usar a interface do usuário do Exchange Online, a menos que você precise de escopos para gerenciamento do Exchange.

Não é possível criar funções personalizadas. As funções são definidas pelos serviços criados pela Microsoft e crescerão à medida que novos serviços são introduzidos. Isso é semelhante no conceito às [funções definidas por aplicativos](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) no Azure AD. Quando novos serviços são habilitados, muitas vezes novos grupos de função precisam ser criados para conceder ou delegar acesso a eles (por exemplo, gerenciamento de riscos [insider](../compliance/insider-risk-management-configure.md?view=o365-worldwide)).

Esses grupos de função também exigem associação direta e não podem conter grupos do Azure AD. Infelizmente, hoje esses grupos de função não têm suporte do PIM do Azure AD. Como funções do Azure AD, eu tendem a recomendar o gerenciamento delas por meio de APIs ou um produto de governança de parceiros, como Saviynt, ou outros.

As & do Centro de Conformidade abrangem o Microsoft 365 e você não pode escopo desses grupos de funções para um subconjunto do ambiente (como você pode com unidades administrativas no Azure AD). Muitos clientes perguntam como eles podem subdelegar. Por exemplo, "crie uma política de DLP somente para usuários da UE". Hoje, se você tiver direitos para uma função específica no Centro de Conformidade & segurança, terá direitos sobre tudo o que for abordado por essa função no locatário. No entanto, muitas políticas têm recursos para direcionar um subconjunto do ambiente (por exemplo, "disponibilizar esses rótulos somente para esses usuários"). [](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) A governança e a comunicação adequadas são um componente-chave para evitar conflitos. Alguns clientes optam por implementar uma abordagem de "configuração como código" para resolver a subdelegação no Centro de Conformidade & Segurança. Alguns serviços específicos suportam subdelegação (consulte abaixo).

Vale a pena notar que os controles gerenciados atualmente por meio do Centro de Conformidade do & de Segurança (protection.office.com) estão em processo de migração para dois portais de administração separados: security.microsoft.com e compliance.microsoft.com. A alteração é a única constante!

### <a name="service-specific"></a>Específico do serviço

Como dito anteriormente, muitos clientes estão procurando obter um modelo de delegação mais granular. Um exemplo comum: "Gerenciar o serviço XYZ somente para usuários e locais da Divisão X" (ou alguma outra dimensão). A capacidade de fazer isso depende de cada serviço e não é consistente entre serviços e recursos. Além disso, cada serviço pode ter um modelo RBAC separado e exclusivo. Em vez de discutir tudo isso (levará uma vida), estou adicionando links relevantes para cada serviço. Esta não é uma lista completa, mas ela o iniciará.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](/sharepoint/manage-site-collection-administrators) 
- **Microsoft Teams**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](/microsoftteams/itadmin-readiness)
- **Descoberta eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](../compliance/index.yml) 
  + **Filtragem de Permissões**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](../compliance/index.yml)
  + **Limites de conformidade**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](../compliance/set-up-compliance-boundaries.md)
  + **Descoberta Avançada de EDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](../compliance/overview-ediscovery-20.md)
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](/yammer/manage-yammer-users/manage-yammer-admins) 
- **Multi-geo** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](../enterprise/add-a-sharepoint-geo-admin.md) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](/dynamics365/) <br>
  Observação: este link é a raiz da documentação. Há vários tipos de serviços com variações no modelo de administração/delegação.
- **Plataforma Power**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](/power-platform/admin/admin-documentation)
  + **Power Apps**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](/power-platform/admin/wp-security) <br>
    Observação: há vários tipos com variações nos modelos de administração/delegação.
  + **Power Automate**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](/power-automate/environments-overview-admin)
  + **Power BI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](/power-bi/service-admin-governance) <br>
Observação: a segurança e a delegação da plataforma de dados (que o Power BI é um componente) é uma área complexa.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](/mem/intune/fundamentals/role-based-access-control)
- **Microsoft Defender para Ponto de Extremidade**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](../security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](/stream/assign-administrator-user-role)
- **Barreiras de informações**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](../compliance/information-barriers.md)

Para o restante, a pesquisa em Documentos tem sido muito boa recentemente - [https://docs.microsoft.com/](../compliance/information-barriers.md) . 

### <a name="activity-logs"></a>Logs de atividades

O Office 365 tem um [log de auditoria unificado.](../compliance/search-the-audit-log-in-security-and-compliance.md) É um [log muito detalhado,](/office/office-365-management-api/office-365-management-activity-api-schema)mas não leia muito no nome. Ele pode não conter tudo o que você deseja ou precisa para suas necessidades de segurança e conformidade. Além disso, alguns clientes estão realmente interessados em [Auditoria Avançada.](../compliance/advanced-audit.md)

Exemplos de logs do Microsoft 365 acessados por outras APIs incluem o seguinte:

- [Azure AD](/azure/azure-monitor/platform/diagnostic-settings) (atividades não relacionadas ao Office 365)
- [Controle de mensagens do Exchange](/powershell/module/exchange/get-messagetrace)
- Sistemas threat/UEBA discutidos acima (por exemplo, Proteção de Identidade do Azure AD, Microsoft Cloud App Security, Microsoft Defender para Ponto de Extremidade e assim por diante)
- [Proteção de informações da Microsoft](../compliance/data-classification-activity-explorer.md?view=o365-worldwide)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

É importante primeiro identificar todas as fontes de log necessárias para um programa de segurança e conformidade. Observe também que logs diferentes têm limites de retenção online diferentes. 

Da perspectiva de delegação do administrador, a maioria dos logs de atividades do Microsoft 365 não tem um modelo RBAC integrado. Se você tiver permissão para ver um log, poderá ver tudo nele. Um exemplo comum de um requisito do cliente é: "Quero poder consultar a atividade somente para usuários da UE" (ou alguma outra dimensão). Para atingir esse requisito, precisamos transferir logs para outro serviço. Na nuvem da Microsoft, recomendamos transferi-la para o [Azure Sentinel](/azure/sentinel/overview) ou [o Log Analytics.](/azure/azure-monitor/learn/quick-create-workspace) 

Diagrama de alto nível:

![diagrama de fontes de log para um programa de segurança e conformidade](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

O diagrama acima representa os recursos integrados para enviar logs ao Hub de Eventos e/ou ao Armazenamento do Azure e/ou ao Azure Log Analytics. Nem todos os sistemas incluem isso pronto para uso ainda. Mas há outras abordagens para enviar esses logs para o mesmo repositório. Por exemplo, consulte [Protegendo o Teams com o Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761).

Combinar todos os logs em um local de armazenamento inclui benefícios adicionais, como correlações cruzada, tempos de retenção personalizados, aumento com dados necessários para dar suporte ao modelo RBAC e assim por diante. Depois que os dados estão nesse sistema de armazenamento, você pode criar um painel do Power BI (ou outro tipo de visualização) com um modelo RBAC apropriado.

Os logs não têm que ser direcionados apenas para um local. Também pode ser útil integrar logs do [Office 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) com o Microsoft Cloud App Security ou um modelo RBAC personalizado no [Power BI](../admin/usage-analytics/usage-analytics.md?view=o365-worldwide). Repositórios diferentes têm diferentes benefícios e audiências.

Vale a pena mencionar que há um sistema de análise integrado muito rico para segurança, ameaças, vulnerabilidades e assim por diante em um serviço chamado [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md?view=o365-worldwide).

Muitos clientes grandes querem transferir esses dados de log para um sistema de terceiros (por exemplo, SIEM). Há diferentes abordagens para isso, mas, em geral, o Hub de Eventos do [Azure](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) [e o Graph](/graph/security-integration) são bons pontos de partida.

### <a name="azure"></a>Azure

Muitas vezes, sou perguntado se há uma maneira de separar funções de alto privilégio entre o Azure AD, o Azure e o SaaS (ex.: Administrador Global do Office 365, mas não o Azure).  Na verdade, não.  A arquitetura de vários locatários será necessária se a separação administrativa completa for necessária, mas isso adiciona complexidade [significativa](https://aka.ms/multi-tenant-user) (consulte acima). Todos esses serviços fazem parte do mesmo limite de segurança/identidade (veja o modelo de hierarquia acima).  

É importante entender as relações entre vários serviços no mesmo locatário. Estou trabalhando com muitos clientes que estão criando soluções de negócios que abrangem o Azure, o Office 365 e a Plataforma Power (e geralmente também serviços de nuvem locais e de terceiros). Um exemplo comum:

1. Quero colaborar em um conjunto de documentos/imagens/etc (Office 365)
2. Envie cada um deles por meio de um processo de aprovação (Plataforma Power)
3.  Depois que todos os componentes são aprovados, monte-os em uma API unificada do [Microsoft Graph](/azure/active-directory/develop/microsoft-graph-intro) (Azure) é seu melhor amigo para eles.  Não é impossível, mas é significativamente mais complexo projetar uma solução abrangendo [vários locatários.](/azure/active-directory/develop/single-and-multi-tenant-apps)

O Azure Role-Based Controle de Acesso (RBAC) permite o gerenciamento de acesso fino para o Azure. Usando o RBAC, você pode gerenciar o acesso aos recursos concedendo aos usuários o menor tempo de permissão necessário para executar seus trabalhos. Os detalhes estão fora do escopo deste documento, mas para obter mais informações sobre o RBAC, consulte O que é o controle de acesso baseado em função [(RBAC) no Azure?](/azure/role-based-access-control/overview) O RBAC é importante, mas apenas parte das considerações de governança para o Azure. [A Estrutura de](/azure/cloud-adoption-framework/govern/) Adoção de Nuvem é um ótimo ponto de partida para saber mais. Gosto de como meu amigo, Andres Ravinet, orienta os clientes passo a passo, embora vários componentes decidam sobre a abordagem. Exibição de alto nível para vários elementos (não tão bom quanto o processo para chegar ao modelo de cliente real) é algo assim:

![Exibição de alto nível dos componentes do Azure para administração delegada](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

Como você pode ver na imagem acima, muitos outros serviços devem ser considerados como parte do design (ex.: Políticas do [Azure,](/azure/governance/policy/overview) [Projetos do Azure,](/azure/governance/blueprints/overview)Grupos de Gerenciamento [e](/azure/governance/management-groups/)assim por diante).

## <a name="conclusion"></a>Conclusão

Iniciado como um breve resumo, terminou por mais tempo do que eu esperava.  Espero que agora você esteja pronto para se aventurar em uma análise profunda sobre como criar um modelo de delegação para sua organização.  Essa conversa é muito comum com os clientes. Não há um modelo que funcione para todos. Aguardando algumas melhorias planejadas da engenharia da Microsoft antes de documentar padrões comuns que vemos entre os clientes. Enquanto isso, você pode trabalhar com sua equipe de conta da Microsoft para organizar uma visita ao Centro de Tecnologia [da Microsoft mais próximo.](https://www.microsoft.com/mtc)  Até lá!