---
title: Cadeias de criptografia do Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/1/2021
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Exibir uma lista completa de certificados raiz e autoridades de certificados (CAs) no Microsoft 365.
ms.openlocfilehash: c5b00a3a663c2ae4862cfa3d11f92015c0331e59
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907715"
---
# <a name="microsoft-365-encryption-chains"></a>Cadeias de criptografia do Microsoft 365

O Microsoft 365 aproveita vários provedores de certificados diferentes. A seguir descreve a lista completa de certificados raiz conhecidos do Microsoft 365 que os clientes podem encontrar ao acessar o Microsoft 365. Para obter informações sobre os certificados que você pode precisar instalar em sua própria infraestrutura, consulte [Plan for third-party SSL certificates for Microsoft 365](../enterprise/plan-for-third-party-ssl-certificates.md). As informações de certificado a seguir se aplicam a todas as instâncias de nuvem nacionais e mundiais do Microsoft 365.

Última atualização: **16/10/2020**

>[!NOTE]
>Para obter informações de certificado que se apliquem a clientes do DOD e **GCC High,** consulte Cadeias de criptografia do [Microsoft 365 - DOD e GCC High](encryption-office-365-certificate-chains-itar.md).

| **Tipo de certificado** | **Download P7b** | **Pontos de extremidade CRL** | **Pontos de extremidade OCSP** | **Pontos de extremidade do AIA** |
| --- | --- | --- | --- | --- |
| Certificados raiz confiáveis publicamente | [Pacote de certificados raiz do Microsoft 365 (P7B)](https://download.microsoft.com/download/4/a/b/4ab1c940-826b-444b-b287-b7a902e68da0/m365_root_certs_20201012.p7b) | crl.globalsign.net<br>www.d-trust.net | N/D | N/D |
| Certificados Intermediários Confiáveis Publicamente | [Pacote de certificados intermediários do Microsoft 365 (P7B)](https://download.microsoft.com/download/1/4/7/14777f28-3fde-4958-aebf-bd192a4a7fac/m365_intermediate_certs_20201013.p7b) | cdp1.public-trust.com<br>crl.cnnic.cn<br>crl.entrust.net<br>crl.globalsign.com<br>crl.globalsign.net<br>crl.identrust.com<br>crl.thawte.com<br>crl3.digicert.com<br>crl4.digicert.com<br>s1.symcb.com<br>www.d-trust.net | isrg.trustid.ocsp.identrust.com<br>ocsp.digicert.com<br>ocsp.entrust.net<br>ocsp.globalsign.com<br>ocsp.omniroot.com<br>ocsp.startssl.com<br>ocsp.thawte.com<br>ocsp2.globalsign.com<br>ocspcnnicroot.cnnic.cn<br>root-c3-ca2-2009.ocsp.d-trust.net<br>root-c3-ca2-ev-2009.ocsp.d-trust.net<br>s2.symcb.com | aia.startssl.com<br>apps.identrust.com<br>cacert.omniroot.com<br>www.cnnic.cn |

Expanda as seções raiz e intermediária abaixo para ver detalhes adicionais sobre os provedores de certificados.

## <a name="microsoft-365-root-certificate-details"></a>**Detalhes do certificado raiz do Microsoft 365**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Assunto** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| --- | --- |
| **Número de série** | 02:00:00:B9 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | 12 de maio de 18:46:00 2000 UTC |
| **Validade não após** | 12 de maio de 23:59:00 2025 UTC |
| **Identificador de Chave de Assunto** | e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **Impressão digital (SHA-256)** | 16AF57A9F676B0AB126095AAA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **Pin (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o= |

### <a name="cnnic-root"></a>**RAIZ SÁLMÁTICA**

| **Assunto** | RAIZ CN=CN=CNIC<br>O=CNNIC<br>C=CN |
| --- | --- |
| **Número de série** | 49:33:00:01 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Apr 16 07:09:14 2007 UTC |
| **Validade não após** | Apr 16 07:09:14 2027 UTC |
| **Identificador de Chave de Assunto** | 65:f2:31:ad:2a:f7:f7:dd:52:96:0a:c7:02:c1:0e:ef:a6:d5:3b:11 |
| **Identificador de Chave de Autoridade** | keyid:65:f2:31:ad:2a:f7:f7:dd:52:96:0a:c7:02:c1:0e:ef:a6:d5:3b:11 |
| **Impressão digital (SHA-1)** | 8BAF4C9B1DF02A92F7DA128EB91BACF498604B6F |
| **Impressão digital (SHA-256)** | E28393773DA845A679F2080CC7FB44A3B7A1C3792CB7EB7729FDCB6A8D99AEA7 |
| **Pin (SHA-256)** | H0IkzshPyZztiB/2/P0+IfjFGcVHqmpd094kcwLOUNE= |

### <a name="digicert-global-root-ca"></a>**AC Raiz Global digiCert**

| **Assunto** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Número de série** | 08:3B:E0:56:90:42:46:B1:A1:75:6A:C9:59:91:C7:4A |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Nov 10 00:00:00 2006 UTC |
| **Validade não após** | Nov 10 00:00:00 2031 UTC |
| **Identificador de Chave de Assunto** | 03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Identificador de Chave de Autoridade** | keyid:03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **Impressão digital (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **Pin (SHA-256)** | r/mIkG3eEpVdm+u/ko/cwxzOMo1bk4TyHIlByibiA5E= |

### <a name="digicert-global-root-g2"></a>**DigiCert Global Root G2**

| **Assunto** | CN=DigiCert Global Root G2<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 03:3A:F1:E6:A7:11:A9:A0:BB:28:64:B1:1D:09:FA:E5 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Quinta-feira, 1º de agosto de 2013 5:00 AM |
| **Validade não até** | Sexta-feira, 15 de janeiro de 2038 4:00 AM |
| **Identificador de Chave de Assunto** | 4E2254201895E6E36EE60FFAFAB912ED06178F39 |
| **Identificador de Chave de Autoridade** | KeyID:4e:22:54:20:18:95:e6:e3:6e:e6:0f:fa:fa:b9:12:ed:06:17:8f:39 |
| **Impressão digital (SHA-1)** | DF3C24F9BFD666761B268073FE06D1CC8D4F82A4 |
| **Impressão digital (SHA-256)** | CB3CCBB76031E5E0138F8DD39A23F9DE47FFC35E43C1144CEA27D46A5AB1CB5F |

### <a name="digicert-high-assurance-ev-root-ca"></a>**AC raiz do EV de Alta Garantia digiCert**

| **Assunto** | CN=DigiCert High Assurance EV Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Número de série** | 02:AC:5C:26:6A:0B:40:9B:8F:0B:79:F2:AE:46:25:77 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Nov 10 00:00:00 2006 UTC |
| **Validade não após** | Nov 10 00:00:00 2031 UTC |
| **Identificador de Chave de Assunto** | b1:3e:c3:69:03:f8:bf:47:01:d4:98:26:1a:08:02:ef:63:64:2b:c3 |
| **Identificador de Chave de Autoridade** | keyid:b1:3e:c3:69:03:f8:bf:47:01:d4:98:26:1a:08:02:ef:63:64:2b:c3 |
| **Impressão digital (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **Impressão digital (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **Pin (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18= |

### <a name="d-trust-root-class-3-ca-2-2009"></a>**D-TRUST Root Class 3 CA 2 2009**

| **Assunto** | CN=D-TRUST Root Class 3 CA 2 2009<br>O=D-Trust GmbH<br>C=DE |
| --- | --- |
| **Número de série** | 09:83:F3 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Nov 05 08:35:58 2009 UTC |
| **Validade não após** | Nov 05 08:35:58 2029 UTC |
| **Identificador de Chave de Assunto** | fd:da:14:c4:9f:30:de:21:bd:1e:42:39:fc:ab:63:23:49:e0:f1:84 |
| **Impressão digital (SHA-1)** | 58E8ABB0361533FB80F79B1B6D29D3FF8D5F00F0 |
| **Impressão digital (SHA-256)** | 49E7A442ACF0EA6287050054B52564B650E4F49E42E348D6AA38E039E957B1C1 |
| **Pin (SHA-256)** | 7KDxgUAs56hlKzG00DbfJH46MLf0GlDZHsT5CwBrQ6E= |
| **URLs CRLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |

### <a name="d-trust-root-class-3-ca-2-ev-2009"></a>**D-TRUST Root Class 3 CA 2 EV 2009**

| **Assunto** | CN=D-TRUST Root Class 3 CA 2 EV 2009<br>O=D-Trust GmbH<br>C=DE |
| --- | --- |
| **Número de série** | 09:83:F4 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Nov 05 08:50:46 2009 UTC |
| **Validade não após** | Nov 05 08:50:46 2029 UTC |
| **Identificador de Chave de Assunto** | d3:94:8a:4c:62:13:2a:19:2e:cc:af:72:8a:7d:36:d7:9a:1c:dc:67 |
| **Impressão digital (SHA-1)** | 96C91B0B95B4109842FAD0D82279FE60FAB91683 |
| **Impressão digital (SHA-256)** | EEC5496B988CE98625B934092EEC2908BED0B0F316C2D4730C84EAF1F3D34881 |
| **Pin (SHA-256)** | /zQvtsTIvTCkcG9zSJU58Z5uSMwF9GJUZU9mENvFQOk= |
| **URLs CRLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |

### <a name="dst-root-ca-x3"></a>**DST Root CA X3**

| **Assunto** | CN=DST Root CA X3<br>O=Digital Signature Trust Co. |
| --- | --- |
| **Número de série** | 44:AF:B0:80:D6:A3:27:BA:89:30:39:86:2E:F8:40:6B |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Set 30 21:12:19 2000 UTC |
| **Validade não após** | Set 30 14:01:15 2021 UTC |
| **Identificador de Chave de Assunto** | c4:a7:b1:a4:7b:2c:71:fa:db:e1:4b:90:75:ff:c4:15:60:85:89:10 |
| **Impressão digital (SHA-1)** | DAC9024F54D8F6DF94935FB1732638CA6AD77C13 |
| **Impressão digital (SHA-256)** | 0687260331A72403D909F105E69BCF0D32E1BD2493FFC6D9206D11BCD6770739 |
| **Pin (SHA-256)** | Vjs8r4z+80wjNcr1YKepWQboSIRi63WsWXhIMN+eWys= |

### <a name="entrust-root-certification-authority---g2"></a>**Autoridade de Certificação Raiz Confiada - G2**

| **Assunto** | CN=Confiando Autoridade de Certificação Raiz - G2<br>OU= &quot; (c) 2009 Entrust, Inc. - somente para uso autorizado&quot;<br>OU=Consulte www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **Número de série** | 4A:53:8C:28 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Jul 07 17:25:54 2009 UTC |
| **Validade não após** | Dez 07 17:55:54 2030 UTC |
| **Identificador de Chave de Assunto** | 6a:72:26:7a:d0:1e:ef:7d:e7:3b:69:51:d4:6c:8d:9f:90:12:66:ab |
| **Impressão digital (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **Impressão digital (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **Pin (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U= |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **Assunto** | Autoridade de Certificação CN=Entrust.net (2048)<br>OU=(c) 1999 Entrust.net Limited<br>OU=www.entrust.net/CPS \_ 2048 incorp. por ref. (limite s liab.)<br>O=Entrust.net |
| --- | --- |
| **Número de série** | 38:63:DE:F8 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | 24 de dez de 17:50:51 UTC de 1999 |
| **Validade não após** | Jul 24 14:15:12 2029 UTC |
| **Identificador de Chave de Assunto** | 55:e4:81:d1:11:80:be:d8:89:b9:08:a3:31:f9:a1:24:09:16:b9:70 |
| **Impressão digital (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **Impressão digital (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **Pin (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg= |

### <a name="globalsign-root-ca---r1"></a>**CA Raiz do GlobalSign - R1**

| **Assunto** | CN=GlobalSign Root CA<br>OU=Root CA<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Número de série** | 04:00:00:00:00:01:15:4B:5A:C3:94 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Set 01 12:00:00 1998 UTC |
| **Validade não após** | Jan 28 12:00:00 2028 UTC |
| **Identificador de Chave de Assunto** | 60:7b:66:1a:45:0d:97:ca:89:50:2f:7d:04:cd:34:a8:ff:fc:fd:4b |
| **Impressão digital (SHA-1)** | B1BC968BD4F49D622AA89A81F2150152A41D829C |
| **Impressão digital (SHA-256)** | EBD41040E4BB3EC742C9E381D31EF2A41A48B6685C96E7CEF3C1DF6CD4331C99 |
| **Pin (SHA-256)** | K87oWBWM9UZfyddvDfoxL+8lpNyoUB2ptGtn0fv6G2Q= |

### <a name="globalsign-root-ca---r3"></a>**GlobalSign Root CA - R3**

| **Assunto** | CN=GlobalSign<br>O=GlobalSign<br>OU=GlobalSign Root CA - R3 |
| --- | --- |
| **Emissor** | CN=GlobalSign, O=GlobalSign, OU=GlobalSign Root CA - R3 |
| **Número de série** | 04:00:00:00:00:01:21:58:53:08:A2 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Quarta-feira, 18 de março de 2009 3:00 AM |
| **Validade não até** | Domingo, 18 de março de 2029 3:00 AM |
| **Identificador de Chave de Assunto** | 8FF04B7FA82E4524AE4D50FA639A8BDEE2DD1BBC |
| **Identificador de Chave de Autoridade** | KeyID:8f:f0:4b:7f:a8:2e:45:24:ae:4d:50:fa:63:9a:8b:de:e2:dd:1b:bc |
| **Impressão digital (SHA-1)** | D69B561148F01C77C54578C10926DF5B856976AD |
| **Impressão digital (SHA-256)** | CBB522D7B7F127AD6A0113865BDF1CD4102E7D0759AF635A7CF4720DC963C53B |

### <a name="thawte-primary-root-ca---g3"></a>**ca raiz primária de descongelar - G3**

| **Assunto** | CN=descongelar a CA raiz primária - G3<br>OU= &quot; (c) 2008 descongesto, Inc. - Somente para uso autorizado&quot;<br>Ou=Divisão de Serviços de Certificação<br>O= &quot; descongelar, Inc.&quot;<br>C=US |
| --- | --- |
| **Número de série** | 60:01:97:B7:46:A7:EA:B4:B4:9A:D6:4B:2F:F7:90:FB |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Apr 02 00:00:00 2008 UTC |
| **Validade não após** | Dez 01 23:59:59 2037 UTC |
| **Identificador de Chave de Assunto** | ad:6c:aa:94:60:9c:ed:e4:ff:fa:3e:0a:74:2b:63:03:f7:b6:59:bf |
| **Impressão digital (SHA-1)** | F18B538D1BE903B6A6F056435B171589CAF36BF2 |
| **Impressão digital (SHA-256)** | 4B03F45807AD70F21BFC2CAE71C9FDE4604C064CF5FFB686BAE5DBAAD7FDD34C |
| **Pin (SHA-256)** | GQbGEk27Q4V40A4GbVBUxsN/D6YCjAVUXgmU7drshik= |

### <a name="verisign-class-3-public-primary-certification-authority---g5"></a>**VeriSign Class 3 Public Primary Certification Authority - G5**

| **Assunto** | CN=VeriSign Class 3 Public Primary Certification Authority - G5<br>OU= &quot; (c) 2006 VeriSign, Inc. - Somente para uso autorizado&quot;<br>OU=VeriSign Trust Network<br>O= &quot; VeriSign, Inc.&quot;<br>C=US |
| --- | --- |
| **Número de série** | 18:DA:D1:9E:26:7D:E8:BB:4A:21:58:CD:CC:6B:3B:4A |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Nov 08 00:00:00 2006 UTC |
| **Validade não após** | Jul 16 23:59:59 2036 UTC |
| **Identificador de Chave de Assunto** | 7f:d3:65:a7:c2:dd:ec:bb:f0:30:09:f3:43:39:fa:02:af:33:31:33 |
| **Impressão digital (SHA-1)** | 4EB6D578499B1CCF5F581EAD56BE3D9B6744A5E5 |
| **Impressão digital (SHA-256)** | 9ACFAB7E43C8D880D06B262A94DEEEE4B465989C3D0CAF19BAF6405E41AB7DF |
| **Pin (SHA-256)** | JbQbUG5JMJUoI6brnx0x3vZF6jilxsapbXGVfjhN8Fg= |

## <a name="microsoft-365-intermediate-certificate-details"></a>**Detalhes do certificado intermediário do Microsoft 365**

### <a name="cnnic-sha256-ssl"></a>**SSL SHA256 DA SSL**

| **Assunto** | CN=CNNIC SHA256 SSL <br>O=SSL SHA256 SHA256 <br>C=CN |
| --- | --- |
| **Emissor** | RAIZ CN=CN=CNIC <br>O=CNNIC <br>C=CN |
| **Número de série** | 49:33:00:7C |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Dez 18 12:32:18 UTC 2014 |
| **Validade não após** | Dez 18 12:32:18 UTC 2024 |
| **Identificador de Chave de Assunto** | b7:d1:59:8b:8c:0d:06:28:47:23:00:3a:36:04:a5:ee:38:76:53:3c |
| **Identificador de Chave de Autoridade** | keyid:65:f2:31:ad:2a:f7:f7:dd:52:96:0a:c7:02:c1:0e:ef:a6:d5:3b:11 |
| **Impressão digital (SHA-1)** | FC844648FC708433921BE88B18C48787A3E2813E |
| **Impressão digital (SHA-256)** | FA8B9F99DBB94E7B772AA9190846E777047C15C7A3BF4A1AF9C0CA984A689511 |
| **Pin (SHA-256)** | dKZRcLDh7hBNZTmTIHOGJ6C2Om/ITjUCPkOnLTnrZXk= |
| **AIA URLs** | http://www.cnnic.cn/download/cert/CNNICROOT.cer |
| **URLs CRLs** | ldap:///CN=crl1,%20OU=crl,%20O=CNNIC,%20C=CN?certificateRevocationList;binary,authorityRevocationList;binary,deltaRevocationList;binary<br>http://crl.cnnic.cn/download/rootsha2crl/CRL1.crl |
| **OCSP URLs** | <http://ocspcnnicroot.cnnic.cn> |

### <a name="d-trust-ssl-class-3-ca-1-2009"></a>**D-TRUST SSL Class 3 CA 1 2009**

| **Assunto** | CN=D-TRUST SSL Class 3 CA 1 2009<br>O=D-Trust GmbH<br>C=DE |
| --- | --- |
| **Emissor** | CN=D-TRUST Root Class 3 CA 2 2009<br>O=D-Trust GmbH<br>C=DE |
| **Nome alternativo do assunto** | RFC822 Name=info@d-trust.net<br>URL=http://www.d-trust.net |
| **Número de série** | 09:90:63 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Nov 12 12:46:55 2009 UTC |
| **Validade não após** | Nov 05 08:35:58 2029 UTC |
| **Identificador de Chave de Assunto** | 50:19:32:94:9a:c4:b5:04:4d:56:d0:c0:83:21:d5:35:55:b0:b1:7a |
| **Identificador de Chave de Autoridade** | keyid:fd:da:14:c4:9f:30:de:21:bd:1e:42:39:fc:ab:63:23:49:e0:f1:84 |
| **Impressão digital (SHA-1)** | 2FC5DE6528CDBE50A14C382FC1DE524FAABF95FC |
| **Impressão digital (SHA-256)** | 6AC159B4C2BC8E729F3B84642EF1286BCC80D775FE278C740ADA468D59439025 |
| **Pin (SHA-256)** | 9w0QP9HzLXkfs+4zENaUFq2XKcQON1oyksoJ+Gg2AZE= |
| **URLs CRLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |
| **OCSP URLs** | http://root-c3-ca2-2009.ocsp.d-trust.net |

### <a name="d-trust-ssl-class-3-ca-1-ev-2009"></a>**D-TRUST SSL Class 3 CA 1 EV 2009**

| **Assunto** | CN=D-TRUST SSL Class 3 CA 1 EV 2009<br>O=D-Trust GmbH<br>C=DE |
| --- | --- |
| **Emissor** | CN=D-TRUST Root Class 3 CA 2 EV 2009<br>O=D-Trust GmbH<br>C=DE |
| **Nome alternativo do assunto** | RFC822 Name=info@d-trust.net<br>URL=http://www.d-trust.net |
| **Número de série** | 09:90:64 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Nov 12 12:52:43 2009 UTC |
| **Validade não após** | Nov 05 08:50:46 2029 UTC |
| **Identificador de Chave de Assunto** | ac:ed:a5:9d:7a:a2:b6:43:f1:18:8a:25:6a:6c:b1:cc:a8:f2:5a:d4 |
| **Identificador de Chave de Autoridade** | keyid:d3:94:8a:4c:62:13:2a:19:2e:cc:af:72:8a:7d:36:d7:9a:1c:dc:67 |
| **Impressão digital (SHA-1)** | 1069423D308D0FC54575059638560FC7556E32B3 |
| **Impressão digital (SHA-256)** | B0935DC04B4E60C0C42DEF7EC57A1B1D8F958D17988E71CC80A8CF5E635BA5B4 |
| **Pin (SHA-256)** | lv5BNZ5aWd27ooolULDolFTwIaaWjHvG4yH3rss4X8= |
| **URLs CRLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |
| **OCSP URLs** | http://root-c3-ca2-ev-2009.ocsp.d-trust.net |

### <a name="digicert-basic-rsa-cn-ca-g2"></a>**DigiCert Basic RSA CN CA G2**

| **Assunto** | CN=DigiCert Basic RSA CN CA G2<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 02:F7:E1:F9:82:BA:D0:09:AF:F4:7D:C9:57:41:B2:F6 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Quarta-feira, 4 de março de 2020 4:04 AM |
| **Validade não até** | Segunda-feira, 4 de março de 2030 4:04 AM |
| **Identificador de Chave de Assunto** | 06BDA69B60795031BED5A9024AAA0D095538B2F34 |
| **Identificador de Chave de Autoridade** | KeyID:03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | 4D1FA5D1FB1AC3917C08E43F65015E6AEA571179 |
| **Impressão digital (SHA-256)** | CB57B3FF2040CB269497625BC90FA90D7B4ED4938C6F60F42F69AFDF508AC2993 |
| **URLs CRLs** | http://crl.digicert.cn/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.cn |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert Cloud Services CA-1**

| **Assunto** | CN=DigiCert Cloud Services CA-1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| **Número de série** | 01:9E:C1:C6:BD:3F:59:7B:B2:0C:33:38:E5:51:D8:77 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 4 de agosto de 2015 12:00 AM |
| **Validade não até** | 4 de agosto de 2030 12:00 AM |
| **Identificador de Chave de Assunto** | dd:51:d0:a2:31:73:a9:73:ae:8f:b4:01:7e:5d:8c:57:cb:9f:f0:f7 |
| **Identificador de Chave de Autoridade** | 03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | 81B68D6CD2f221F8F534E677523BB236BBA1DC56 |
| **Impressão digital (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F1333D3 |
| **Pin (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE= |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-cloud-services-ca-1"></a>**DigiCert Cloud Services CA-1**

| **Assunto** | CN=DigiCert Cloud Services CA-1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| **Número de série** | 0F:17:1A:48:C6:F2:23:80:92:18:CD:2E:D6:DD:C0:E8 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 25 de setembro de 2020 00:00 AM |
| **Validade não após** | 24 de setembro de 2030 23:59 |
| **Identificador de Chave de Assunto** | dd:51:d0:a2:31:73:a9:73:ae:8f:b4:01:7e:5d:8c:57:cb:9f:f0:f7 |
| **Identificador de Chave de Autoridade** | 03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | B3F6B64A07BB9611F47174407841F564FB991F29 |
| **Impressão digital (SHA-256)** | 5F88694615E4C61686E106B84C3338C6720C535F60D36F61282ED15E1977DDD44 | -
| **Pin (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE= |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com

### <a name="digicert-sha2-extended-validation-server-ca"></a>**CA do Servidor de Validação Estendida SHA2 digiCert**

| **Assunto** | CN=DigiCert SHA2 Extended Validation Server CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert High Assurance EV Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 0C:79:A9:44:B0:8C:11:95:20:92:61:5F:E2:6B:1D:83 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Terça-feira, 22 de outubro de 2013 5:00 AM |
| **Validade não até** | Domingo, 22 de outubro de 2028 5:00 AM |
| **Identificador de Chave de Assunto** | 3DD350A5D6A0ADEEF34A600A65D321D4F8F8D60F |
| **Identificador de Chave de Autoridade** | KeyID:b1:3e:c3:69:03:f8:bf:47:01:d4:98:26:1a:08:02:ef:63:64:2b:c3 |
| **Impressão digital (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA02966637E986F3F3F3F |
| **Impressão digital (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |
| **URLs CRLs** | http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-sha2-high-assurance-server-ca"></a>**AC do Servidor de Alta Garantia SHA2 digiCert**

| **Assunto** | CN=DigiCert SHA2 High Assurance Server CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert High Assurance EV Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| **Número de série** | 04:E1:E7:A4:DC:5C:F2:F3:6D:C0:2B:42:B8:5D:15:9F |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Oct 22 12:00:00 2013 UTC |
| **Validade não após** | Oct 22 12:00:00 2028 UTC |
| **Identificador de Chave de Assunto** | 51:68:ff:90:af:02:07:75:3c:cc:d9:65:64:62:a2:12:b8:59:72:3b |
| **Identificador de Chave de Autoridade** | keyid:b1:3e:c3:69:03:f8:bf:47:01:d4:98:26:1a:08:02:ef:63:64:2b:c3 |
| **Impressão digital (SHA-1)** | A031C46782E6E6C662C2C87C76DA9AA62CCABD8E |
| **Impressão digital (SHA-256)** | 19400BE5B7A31FB733917700789D2F0A2471C0C0C9D506C0E504C06C16D7CB17C0 |
| **Pin (SHA-256)** | k2v657xBsOVe1PQRwOsHsw3bsGT2VzIqz5K+59sNQws= |
| **URLs CRLs** | http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**CA do Servidor Seguro SHA2 digiCert**

| **Assunto** | CN=DigiCert SHA2 Secure Server CA<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA<br>OU=www.digicert.com<br>O=DigiCert Inc<br>C=US |
| **Número de série** | 01:FD:A3:EB:6E:CA:75:C8:88:43:8B:72:4B:CF:BC:91 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Mar 08 12:00:00 2013 UTC |
| **Validade não após** | Mar 08 12:00:00 2023 UTC |
| **Identificador de Chave de Assunto** | 0f:80:61:1c:82:31:61:d5:2f:28:e7:8d:46:38:b4:2c:e1:c6:d9:e2 |
| **Identificador de Chave de Autoridade** | keyid:03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Impressão digital (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **Pin (SHA-256)** | 5kJvNEMw0KjrCAu7eXY5HZdvyCS13BbA0VJG1RSP91w= |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**CA do Servidor Seguro SHA2 digiCert**

| **Assunto** | CN=DigiCert SHA2 Secure Server CA<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 02:74:2E:AA:17:CA:8E:21:C7:17:BB:1F:FC:FD:0C:A0 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Terça-feira, 22 de setembro de 2020 17:00 |
| **Validade não até** | Domingo, 22 de setembro de 2030 16:59 |
| **Identificador de Chave de Assunto** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Identificador de Chave de Autoridade** | KeyID:03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | 626D44E704D1CEABE3BF0D53397464AC8080142C |
| **Impressão digital (SHA-256)** | C1AD7777796D20BCA65C889A265502156528BB62FF5FA43E1B8E5A83E3D2EAA |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="digicert-tls-rsa-sha256-2020-ca1"></a>**DigiCert TLS RSA SHA256 2020 CA1**

| **Assunto** | CN=DigiCert TLS RSA SHA256 2020 CA1<br>O=DigiCert Inc<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 0A:35:08:D5:5C:29:2B:01:7D:F8:AD:65:C0:0F:F7:E4 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Quarta-feira, 23 de setembro de 2020 17:00 |
| **Validade não até** | Segunda-feira, 23 de setembro de 2030 16:59 |
| **Identificador de Chave de Assunto** | B76BA2EAA8AA848C79EAB4DA0F98B2C59576B9F4 |
| **Identificador de Chave de Autoridade** | KeyID:03:de:50:35:56:d1:4c:bb:66:f0:a3:e2:1b:1b:c3:97:b2:3d:d1:55 |
| **Impressão digital (SHA-1)** | 6938FD4D98BAB03FAADB97B34396831E3780AEA1 |
| **Impressão digital (SHA-256)** | 25768713D3B459F9382D2A594F85F34709FD2A8930731542A4146FFB246BEC69 |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="entrust-certification-authority---l1c"></a>**Autoridade de Certificação de Confiação - L1C**

| **Assunto** | CN=Autoridade de Certificação de Confiação - L1C<br>OU= &quot; (c) 2009 Entrust, Inc.&quot;<br>OU=www.entrust.net/rpa é incorporada por referência<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **Emissor** | Autoridade de Certificação CN=Entrust.net (2048)<br>OU=(c) 1999 Entrust.net Limited<br>OU=www.entrust.net/CPS \_ 2048 incorp. por ref. (limites liab.)<br>O=Entrust.net |
| **Número de série** | 4C:0E:8C:39 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não anterior** | Nov 11 15:40:40 2011 UTC |
| **Validade não após** | Nov 12 02:51:17 2021 UTC |
| **Identificador de Chave de Assunto** | 1e:f1:ab:89:06:f8:49:0f:01:33:77:ee:14:7a:ee:19:7c:93:28:4d |
| **Identificador de Chave de Autoridade** | keyid:55:e4:81:d1:11:80:be:d8:89:b9:08:a3:31:f9:a1:24:09:16:b9:70 |
| **Impressão digital (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Impressão digital (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **Pin (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWWOJL6bOJS+Ui0bQ94= |
| **URLs CRLs** | http://crl.entrust.net/2048ca.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Autoridade de Certificação de Confiação - L1K**

| **Assunto** | CN=Autoridade de Certificação de Confiação - L1K<br>OU= &quot; (c) 2012 Entrust, Inc. - somente para uso autorizado&quot;<br>OU=Consulte www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| --- | --- |
| **Emissor** | CN=Confiando Autoridade de Certificação Raiz - G2<br>OU= &quot; (c) 2009 Entrust, Inc. - somente para uso autorizado&quot;<br>OU=Consulte www.entrust.net/legal-terms<br>O= &quot; Entrust, Inc.&quot;<br>C=US |
| **Número de série** | 0E:E9:4C:C3:00:00:00:00:51:D3:77:85 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Oct 05 19:13:56 2015 UTC |
| **Validade não após** | Dez 05 19:43:56 2030 UTC |
| **Identificador de Chave de Assunto** | 82:a2:70:74:dd:bc:53:3f:cf:7b:d4:f7:cd:7f:a7:60:c6:0a:4c:bf |
| **Identificador de Chave de Autoridade** | keyid:6a:72:26:7a:d0:1e:ef:7d:e7:3b:69:51:d4:6c:8d:9f:90:12:66:ab |
| **Impressão digital (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **Impressão digital (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **Pin (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc= |
| **URLs CRLs** | http://crl.entrust.net/g2ca.crl |
| **OCSP URLs** | http://ocsp.entrust.net |

### <a name="globalsign-extended-validation-ca---sha256---g2"></a>**CA de Validação Estendida globalSign - SHA256 - G2**

| **Assunto** | CN=GlobalSign Extended Validation CA - SHA256 - G2<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign<br>O=GlobalSign<br>OU=GlobalSign Root CA - R2 |
| **Número de série** | 04:00:00:00:00:01:44:4E:F0:4A:55 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Feb 20 10:00:00 2014 UTC |
| **Validade não após** | 15 de dezembro 08:00:00 2021 UTC |
| **Identificador de Chave de Assunto** | da:40:77:43:65:1c:f8:fe:a7:e3:f4:64:82:3e:4d:43:13:22:31:02 |
| **Identificador de Chave de Autoridade** | keyid:9b:e2:07:57:67:1c:1e:c0:6a:06:de:59:b4:9a:2d:df:dc:19:86:2e |
| **Impressão digital (SHA-1)** | 65BE102BE26928650E0EF54DC8F4F15AF5F98E8B |
| **Impressão digital (SHA-256)** | 24F91C0705A0A5338641B365FB0D9D9709B56297CFF1857E73C02C02C1636D486AAAA |
| **Pin (SHA-256)** | LvRiGEjRqfzurezaWuj8Wie2gyHMrW5Q06LspMnox7A= |
| **URLs CRLs** | http://crl.globalsign.net/root-r2.crl |
| **OCSP URLs** | http://ocsp.globalsign.com/rootr2 |

### <a name="globalsign-extended-validation-ca---sha256---g3"></a>**Ca de Validação Estendida globalSign - SHA256 - G3**

| **Assunto** | CN=GlobalSign Extended Validation CA - SHA256 - G3<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign<br>O=GlobalSign<br>OU=GlobalSign Root CA - R3 |
| **Número de série** | 48:A4:02:DD:27:92:0D:A2:08:34:9D:D1:99:7B |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Set 21 00:00:00 2016 UTC |
| **Validade não após** | Set 21 00:00:00 2026 UTC |
| **Identificador de Chave de Assunto** | dd:b3:e7:6d:a8:2e:e8:c5:4e:6e:cf:74:e6:75:3c:94:15:ce:e8:1d |
| **Identificador de Chave de Autoridade** | keyid:8f:f0:4b:7f:a8:2e:45:24:ae:4d:50:fa:63:9a:8b:de:e2:dd:1b:bc |
| **Impressão digital (SHA-1)** | 6023192FE7B59D2789130A9FE4094F9B5570D4A2 |
| **Impressão digital (SHA-256)** | AED5DD9A5339685DFB029F6D89A14335A96512C3CACC52B2994AF8B6B37FA4D2 |
| **Pin (SHA-256)** | 86fLIetopQLDNxFZ0uMI66Xpl1pFgLlHHn9v6kT0i4I= |
| **URLs CRLs** | http://crl.globalsign.com/root-r3.crl |
| **OCSP URLs** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**CA de Validação da Organização GlobalSign - SHA256 - G2**

| **Assunto** | CN=GlobalSign Organization Validation CA - SHA256 - G2<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign<br>O=GlobalSign<br>OU=GlobalSign Root CA - R3 |
| **Número de série** | 04:00:00:00:00:01:31:89:C6:44:C9 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 02 de agosto 10:00:00 2011 UTC |
| **Validade não após** | 02 de agosto 10:00:00 2022 UTC |
| **Identificador de Chave de Assunto** | 96:de:61:f1:bd:1c:16:29:53:1c:c0:cc:7d:3b:83:00:40:e6:1a:7c |
| **Identificador de Chave de Autoridade** | keyid:8f:f0:4b:7f:a8:2e:45:24:ae:4d:50:fa:63:9a:8b:de:e2:dd:1b:bc |
| **Impressão digital (SHA-1)** | EF90B2B86F4756EBE7D36FF3015D63523A0076E9 |
| **Impressão digital (SHA-256)** | 0B339212D7CFF17A2C59E35669B58E77350133750A78DA9404770EDD470DEF76 |
| **Pin (SHA-256)** | IQBnNBEiFuhj+8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4= |
| **URLs CRLs** | http://crl.globalsign.net/root-r3.crl |
| **OCSP URLs** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**CA de Validação da Organização GlobalSign - SHA256 - G2**

| **Assunto** | CN=GlobalSign Organization Validation CA - SHA256 - G2<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign Root CA<br>OU=Root CA<br>O=GlobalSign nv-sa<br>C=BE |
| **Número de série** | 04:00:00:00:00:01:44:4E:F0:42:47 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Feb 20 10:00:00 2014 UTC |
| **Validade não após** | Feb 20 10:00:00 2024 UTC |
| **Identificador de Chave de Assunto** | 96:de:61:f1:bd:1c:16:29:53:1c:c0:cc:7d:3b:83:00:40:e6:1a:7c |
| **Identificador de Chave de Autoridade** | keyid:60:7b:66:1a:45:0d:97:ca:89:50:2f:7d:04:cd:34:a8:ff:fc:fd:4b |
| **Impressão digital (SHA-1)** | 902EF2DEEB3C5B13EA4C3D5193629309E231AE55 |
| **Impressão digital (SHA-256)** | 74EF335E5E18788307FB9D89CB704BEC112ABD23487DBFF41C4DED5070F241D9 |
| **Pin (SHA-256)** | IQBnNBEiFuhj+8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4= |
| **URLs CRLs** | http://crl.globalsign.net/root.crl |
| **OCSP URLs** | http://ocsp.globalsign.com/rootr1 |

### <a name="globalsign-organization-validation-ca---sha256---g3"></a>**CA de Validação da Organização GlobalSign - SHA256 - G3**

| **Assunto** | CN=GlobalSign Organization Validation CA - SHA256 - G3<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign Root CA, OU=Root CA, O=GlobalSign nv-sa, C=BE |
| **Número de série** | 47:07:B1:01:9A:0C:57:AD:39:B3:E1:7D:A9:F9 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Quinta-feira, 3 de setembro de 2015 17:00 |
| **Validade não até** | Quarta-feira, 3 de setembro de 2025 17:00 |
| **Identificador de Chave de Assunto** | 6886B87D7AD96D496B872F188B15346CD7B47A0E |
| **Identificador de Chave de Autoridade** | KeyID:60:7b:66:1a:45:0d:97:ca:89:50:2f:7d:04:cd:34:a8:ff:fc:fd:4b |
| **Impressão digital (SHA-1)** | 20D1EBAB5A71587B9116E4C74415D1A85B0DDDA5 |
| **Impressão digital (SHA-256)** | 699D54B7482A5D32931EA0415CC2EDCD60FDA01D19E71D054196BCE0677735C |
| **URLs CRLs** | http://crl.globalsign.com/root.crl |
| **OCSP URLs** | http://ocsp.globalsign.com/rootr1 |

### <a name="globalsign-rsa-ov-ssl-ca-2018"></a>**GLOBALSign RSA OV SSL CA 2018**

| **Assunto** | CN=GlobalSign RSA OV SSL CA 2018<br>O=GlobalSign nv-sa<br>C=BE |
| --- | --- |
| **Emissor** | CN=GlobalSign, O=GlobalSign, OU=GlobalSign Root CA - R3 |
| **Número de série** | 01:EE:5F:22:1D:FC:62:3B:D4:33:3A:85:57 |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Terça-feira, 20 de novembro de 2018 16:00 |
| **Validade não até** | Segunda-feira, 20 de novembro de 2028 16:00 |
| **Identificador de Chave de Assunto** | F8EF7FF2CD7867A8DE6F8F248D88F1870302B3EB |
| **Identificador de Chave de Autoridade** | KeyID:8f:f0:4b:7f:a8:2e:45:24:ae:4d:50:fa:63:9a:8b:de:e2:dd:1b:bc |
| **Impressão digital (SHA-1)** | DFE83023062B997682708B4EAB8E819AFF5D9775 |
| **Impressão digital (SHA-256)** | B676FFA3179E8812093A1B5EAFEE876AE7A6AAF231078DAD1BFB21CD2893764A |
| **URLs CRLs** | http://crl.globalsign.com/root-r3.crl |
| **OCSP URLs** | http://ocsp2.globalsign.com/rootr3 |

### <a name="lets-encrypt-authority-x3"></a>**Vamos criptografar a autoridade X3**

| **Assunto** | CN=Let's Encrypt Authority X3<br>O=Vamos Criptografar<br>C=US |
| --- | --- |
| **Emissor** | CN=DST Root CA X3<br>O=Digital Signature Trust Co. |
| **Número de série** | 0A:01:41:42:00:00:01:53:85:73:6A:0B:85:EC:A7:08 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Mar 17 16:40:46 2016 UTC |
| **Validade não após** | Mar 17 16:40:46 2021 UTC |
| **Identificador de Chave de Assunto** | a8:4a:6a:63:04:7d:dd:ba:e6:d1:39:b7:a6:45:65:ef:f3:a8:ec:a1 |
| **Identificador de Chave de Autoridade** | keyid:c4:a7:b1:a4:7b:2c:71:fa:db:e1:4b:90:75:ff:c4:15:60:85:89:10 |
| **Impressão digital (SHA-1)** | E6A3B45B062D509B3382282D196EFE97D5956CCB |
| **Impressão digital (SHA-256)** | 25847D668EB4F04FDD40B12B6B0740C567DA7D024308EB6C2C96FE41D9DE218D |
| **Pin (SHA-256)** | YLh1dUR9y6Kja30RrAn7JKnbQG/uEtLMkBgFF2Fuihg= |
| **AIA URLs** | http://apps.identrust.com/roots/dstrootcax3.p7c |
| **URLs CRLs** | http://crl.identrust.com/DSTROOTCAX3CRL.crl |
| **OCSP URLs** | http://isrg.trustid.ocsp.identrust.com |

### <a name="microsoft-azure-tls-issuing-ca-01"></a>**Microsoft Azure TLS Emissão de CA 01**

| **Assunto** | CN=Microsoft Azure TLS Issuing CA 01<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 0A:AF:A6:C5:CA:63:C4:51:41:EA:3B:E1:F7:C7:53:17 |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não anterior** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 16:59 |
| **Identificador de Chave de Assunto** | 0F205DD7A15795DB92CF2BD0C7C27704CE728076 |
| **Identificador de Chave de Autoridade** | KeyID:4e:22:54:20:18:95:e6:e3:6e:e6:0f:fa:fa:b9:12:ed:06:17:8f:39 |
| **Impressão digital (SHA-1)** | 2F2877C5D778C31E0F29C7E371DF5471BD673173 |
| **Impressão digital (SHA-256)** | 24C7299864E0A2A6964F551C0E8DF2461532FA8C48E4DBBB6080716691F190E5 |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-02"></a>**Microsoft Azure TLS Emissão de CA 02**

| **Assunto** | CN=Microsoft Azure TLS Emissão de CA 02<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 0C:6A:E9:7C:CE:D5:99:83:86:90:A0:0A:9E:A5:32:14 |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não anterior** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 16:59 |
| **Identificador de Chave de Assunto** | 00AB91FC216226979AAA8791B61419060A96267FD |
| **Identificador de Chave de Autoridade** | KeyID:4e:22:54:20:18:95:e6:e3:6e:e6:0f:fa:fa:b9:12:ed:06:17:8f:39 |
| **Impressão digital (SHA-1)** | E7EEA674CA718E3BEFD90858E09F8372AD0AE2AAA |
| **Impressão digital (SHA-256)** | 15A98761EBE011554DA3A46D206B0812CB2EB69AE87AAA11A6DD4CB84ED5142A |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-05"></a>**Microsoft Azure TLS Emissão de CA 05**

| **Assunto** | CN=Microsoft Azure TLS Emissão de CA 05<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 0D:7B:ED:E9:7D:82:09:96:7A:52:63:1B:8B:DD:18:BD |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não anterior** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 16:59 |
| **Identificador de Chave de Assunto** | C7B29C7F1CE3B85AEFE9681AA85D94C126526A68 |
| **Identificador de Chave de Autoridade** | KeyID:4e:22:54:20:18:95:e6:e3:6e:e6:0f:fa:fa:b9:12:ed:06:17:8f:39 |
| **Impressão digital (SHA-1)** | 6C3AF02E7F269AA73AFD0EFF2A88A4A1F04ED1E5 |
| **Impressão digital (SHA-256)** | D6831BA43607F5AC19778D627531562AF55145F191CAB5EFAFA0E0005442B302 |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-06"></a>**Microsoft Azure TLS Emissão de CA 06**

| **Assunto** | CN=Microsoft Azure TLS Issuing CA 06<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US |
| **Número de série** | 02:E7:91:71:FB:80:21:E9:3F:E2:D9:83:83:4C:50:C0 |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não anterior** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 16:59 |
| **Identificador de Chave de Assunto** | D5C1673AC2A39DF477525B59123829E65568BBA5 |
| **Identificador de Chave de Autoridade** | KeyID:4e:22:54:20:18:95:e6:e3:6e:e6:0f:fa:fa:b9:12:ed:06:17:8f:39 |
| **Impressão digital (SHA-1)** | 30E01761AB97E59A06B41EF20AF6F2DE7EF4F7B0 |
| **Impressão digital (SHA-256)** | 48FF8B494668C752304B48BFE818758887DEF6582E5F09B921F4B60BB3D6A8DD |
| **URLs CRLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS CA 1**

| **Assunto** | CN=Microsoft IT TLS CA 1<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **Número de série** | 08:B8:7A:50:1B:BE:9C:DA:2D:16:4D:3E:39:51:BF:55 |
| **Comprimento da chave pública** | Rsa 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 20 de maio de 12:51:28 UTC de 2016 |
| **Validade não após** | 20 de maio de 12:51:28 UTC 2024 |
| **Identificador de Chave de Assunto** | 58:88:9f:d6:dc:9c:48:22:b7:14:3e:ff:84:88:e8:e6:85:ff:fa:7d |
| **Identificador de Chave de Autoridade** | keyid:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **Impressão digital (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **Pin (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd+J3+b2LiybIw= |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS CA 2**

| **Assunto** | CN=Microsoft IT TLS CA 2<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **Número de série** | 0F:2C:10:C9:5B:06:C0:93:7F:B8:D4:49:F8:3E:85:69 |
| **Comprimento da chave pública** | Rsa 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 20 de maio de 12:51:57 UTC de 2016 |
| **Validade não após** | 20 de maio de 12:51:57 UTC 2024 |
| **Identificador de Chave de Assunto** | 91:9e:3b:44:6c:3d:57:9c:42:77:2a:34:d7:4f:d1:cc:4a:97:2c:da |
| **Identificador de Chave de Autoridade** | keyid:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **Impressão digital (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **Pin (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H+TT7s= |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS CA 4**

| **Assunto** | CN=Microsoft IT TLS CA 4<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **Número de série** | 0B:6A:B3:B0:3E:B1:A9:F6:C4:60:92:6A:A8:CD:FE:B3 |
| **Comprimento da chave pública** | Rsa 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 20 de maio de 12:52:38 UTC 2016 |
| **Validade não após** | 20 de maio de 12:52:38 UTC 2024 |
| **Identificador de Chave de Assunto** | 7a:7b:8c:c1:cf:e7:a0:ca:1c:d4:6b:fa:fb:e1:33:c3:0f:1a:a2:9d |
| **Identificador de Chave de Autoridade** | keyid:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **Impressão digital (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **Pin (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE++mV7FgIcbn4WhMz1I2k= |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS CA 5**

| **Assunto** | CN=Microsoft IT TLS CA 5<br>OU=Microsoft IT<br>O=Microsoft Corporation<br>L=Redmond<br>S=Washington<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **Número de série** | 08:88:CD:52:5F:19:24:44:4D:14:A5:82:91:DE:B9:52 |
| **Comprimento da chave pública** | Rsa 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 20 de maio de 12:53:03 UTC de 2016 |
| **Validade não após** | 20 de maio de 12:53:03 UTC 2024 |
| **Identificador de Chave de Assunto** | 08:fe:25:9f:74:ea:87:04:c2:bc:bb:8e:a8:38:5f:33:c6:d1:6c:65 |
| **Identificador de Chave de Autoridade** | keyid:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **Impressão digital (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **Pin (SHA-256)** | RCbqB+W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc= |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-01"></a>**Microsoft RSA TLS CA 01**

| **Assunto** | CN=Microsoft RSA TLS CA 01<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root, OU=CyberTrust, O=Baltimore, C=IE |
| **Número de série** | 0F:14:96:5F:20:20:69:99:4F:D5:C7:AC:78:89:41:E2 |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Terça-feira, 21 de julho de 2020 16:00 |
| **Validade não até** | Terça-feira, 8 de outubro de 2024 0:00 |
| **Identificador de Chave de Assunto** | B5760C3011CEC792424D4CC75C2CC8A90CE80B64 |
| **Identificador de Chave de Autoridade** | KeyID:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | 703D7A8F0EBF55AAA59F98EAF4A206004EB2516A |
| **Impressão digital (SHA-256)** | 04EEEA8E50B4775B3C24797262917EE50002EC4C75B56CDF3EE1C18CFCA5BA52 |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-02"></a>**Microsoft RSA TLS CA 02**

| **Assunto** | CN=Microsoft RSA TLS CA 02<br>O=Microsoft Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root, OU=CyberTrust, O=Baltimore, C=IE |
| **Número de série** | 0F:A7:47:22:C5:3D:88:C8:0F:58:9E:FB:1F:9D:4A:3A |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Terça-feira, 21 de julho de 2020 16:00 |
| **Validade não até** | Terça-feira, 8 de outubro de 2024 0:00 |
| **Identificador de Chave de Assunto** | FF2F7FE106F438F32DED258D98C2FE0EF66CFCFA |
| **Identificador de Chave de Autoridade** | KeyID:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | B0C2D2D13CDD56CDAA6AB6E2C04440BE4A429C75 |
| **Impressão digital (SHA-256)** | 05E4005DB0C382F3BD66B47729E9011577601BF6F7B287E9A52CED710D258346 |
| **URLs CRLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.digicert.com |

### <a name="symantec-class-3-ev-ssl-ca---g3"></a>**Symantec Classe 3 EV SSL CA - G3**

| **Assunto** | CN=Symantec Classe 3 EV SSL CA - G3<br>OU=Symantec Trust Network<br>O=Symantec Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=VeriSign Class 3 Public Primary Certification Authority - G5<br>OU= &quot; (c) 2006 VeriSign, Inc. - Somente para uso autorizado&quot;<br>OU=VeriSign Trust Network<br>O= &quot; VeriSign, Inc.&quot;<br>C=US |
| **Nome alternativo do assunto** | Endereço do diretório: CN=SymantecPKI-1-533 |
| **Número de série** | 7E:E1:4A:6F:6F:EF:F2:D3:7F:3F:3F:AD:65:4D:3A:DA:B4 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 31 de outubro de 00:00:00 2013 UTC |
| **Validade não após** | Oct 30 23:59:59 2023 UTC |
| **Identificador de Chave de Assunto** | 01:59:ab:e7:dd:3a:0b:59:a6:64:63:d6:cf:20:07:57:d5:91:e7:6a |
| **Identificador de Chave de Autoridade** | keyid:7f:d3:65:a7:c2:dd:ec:bb:f0:30:09:f3:43:39:fa:02:af:33:31:33 |
| **Impressão digital (SHA-1)** | E3FC0AD84F2F5A83ED6F86F567F8B14B40DCBF12 |
| **Impressão digital (SHA-256)** | 9E6BC5F9ECC52460E8EDC02C644D1BE1CB9F2316F41DAF3B616A0B2058294B31 |
| **Pin (SHA-256)** | gMxWOrX4PMQesK9qFNbYBxjBfjUvlkn/vN1n+L9lE5E= |
| **URLs CRLs** | http://s1.symcb.com/pca3-g5.crl |
| **OCSP URLs** | http://s2.symcb.com |

### <a name="symantec-class-3-secure-server-ca---g4"></a>**Symantec Class 3 Secure Server CA - G4**

| **Assunto** | CN=Symantec Class 3 Secure Server CA - G4<br>OU=Symantec Trust Network<br>O=Symantec Corporation<br>C=US |
| --- | --- |
| **Emissor** | CN=VeriSign Class 3 Public Primary Certification Authority - G5<br>OU= &quot; (c) 2006 VeriSign, Inc. - Somente para uso autorizado&quot;<br>OU=VeriSign Trust Network<br>O= &quot; VeriSign, Inc.&quot;<br>C=US |
| **Nome alternativo do assunto** | Endereço do diretório: CN=SymantecPKI-1-534 |
| **Número de série** | 51:3F:B9:74:38:70:B7:34:40:41:8D:30:93:06:99:FF |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 31 de outubro de 00:00:00 2013 UTC |
| **Validade não após** | Oct 30 23:59:59 2023 UTC |
| **Identificador de Chave de Assunto** | 5f:60:cf:61:90:55:df:84:43:14:8a:60:2a:b2:f5:7a:f4:43:18:ef |
| **Identificador de Chave de Autoridade** | keyid:7f:d3:65:a7:c2:dd:ec:bb:f0:30:09:f3:43:39:fa:02:af:33:31:33 |
| **Impressão digital (SHA-1)** | FF67367C5CD4DE4AE18BCCE1D70FDABD7C866135 |
| **Impressão digital (SHA-256)** | EAE72EB454BF6C3977EBD289E970B2F5282949190093D0D0D26F98D0F0D6A9CF17 |
| **Pin (SHA-256)** | 9n0izTnSRF+W4W4JTq51avSXkWhQB8duS2bxVLfzXsY= |
| **URLs CRLs** | http://s1.symcb.com/pca3-g5.crl |
| **OCSP URLs** | http://s2.symcb.com |

### <a name="thawte-sha256-ssl-ca"></a>**thawte SHA256 SSL CA**

| **Assunto** | CN=descongelar a CA SSL SHA256<br>O= &quot; descongelar, Inc.&quot;<br>C=US |
| --- | --- |
| **Emissor** | CN=descongelar a CA raiz primária - G3<br>OU= &quot; (c) 2008 descongesto, Inc. - Somente para uso autorizado&quot;<br>Ou=Divisão de Serviços de Certificação<br>O= &quot; descongelar, Inc.&quot;<br>C=US |
| **Nome alternativo do assunto** | Endereço do diretório: CN=VeriSignMPKI-2-415 |
| **Número de série** | 36:34:9E:18:C9:9C:26:69:B6:56:2E:6C:E5:AD:71:32 |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | 23 de maio de 00:00:00 2013 UTC |
| **Validade não após** | 22 de maio de 23:59:59 UTC 2023 |
| **Identificador de Chave de Assunto** | 2b:9a:35:ae:01:18:38:30:e1:70:7a:05:e0:11:76:a3:ce:bd:90:14 |
| **Identificador de Chave de Autoridade** | keyid:ad:6c:aa:94:60:9c:ed:e4:ff:fa:3e:0a:74:2b:63:03:f7:b6:59:bf |
| **Impressão digital (SHA-1)** | 67D147D5DAB7F28D663CA5B7A9568F087427B9F7 |
| **Impressão digital (SHA-256)** | 3F3AF9C9CC2C7599EF8F6DD7CA516CFC1797D7D12002254F3BFD0D4D0FE9DE86 |
| **Pin (SHA-256)** | /36ymPAVaJl3QDyB1lUkVf9GqJNug0R8JJPDN6348p8= |
| **URLs CRLs** | http://crl.thawte.com/ThawtePCA-G3.crl |
| **OCSP URLs** | http://ocsp.thawte.com |

### <a name="verizon-akamai-sureserver-ca-g14-sha2"></a>**Verizon Akamai SureServer CA G14-SHA2**

| **Assunto** | CN=Verizon Akamai SureServer CA G14-SHA2<br>OU=Cybertrust<br>Soluções empresariais O=Verizon<br>L=Amsterdã<br>C=NL |
| --- | --- |
| **Emissor** | CN=Baltimore CyberTrust Root<br>OU=CyberTrust<br>O=Baltimore<br>C=IE |
| **Número de série** | 07:27:A4:6B |
| **Comprimento da chave pública** | Bits RSA 2048 (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não anterior** | Apr 02 14:36:10 2014 UTC |
| **Validade não após** | Apr 02 14:35:52 2021 UTC |
| **Identificador de Chave de Assunto** | f8:bd:fa:af:73:77:c6:c7:1b:f9:4b:4d:11:a7:d1:33:af:af:72:11 |
| **Identificador de Chave de Autoridade** | keyid:e5:9d:59:30:82:47:58:cc:ac:fa:08:54:36:86:7b:3a:b5:04:4d:f0 |
| **Impressão digital (SHA-1)** | 6AD2B04E2196E48BF685752890E811CD2ED60606 |
| **Impressão digital (SHA-256)** | 7373D219B42547E41BCB752BCBE93F592FF6F99C340CE57B73D38C3EC0BA98 |
| **Pin (SHA-256)** | 8XFPrRr4VxmEIYKUu35QtR3oGbduX1AlrBzaBUHgp7c= |
| **AIA URLs** | https://cacert.omniroot.com/baltimoreroot.crt<br>https://cacert.omniroot.com/baltimoreroot.der |
| **URLs CRLs** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |
| **OCSP URLs** | http://ocsp.omniroot.com/baltimoreroot |

## <a name="additional-certificate-paths"></a>**Caminhos de certificado adicionais**

A lista a seguir inclui certificados herddos que não estão incluídos acima e serão mesclados com a lista acima ao longo do tempo.

evsecure-aia.verisign.com<br>
sa.symcb.com<br>
sd.symcb.com<br>
\*.omniroot.com<br>
\*.verisign.com<br>
\*.symcb.com<br>
\*.symcd.com<br>
\*.verisign.net<br>
\*.geotrust.com<br>
\*.entrust.net<br>
\*.public-trust.com<br>
EVIntl-ocsp.verisign.com<br>
EVSecure-ocsp.verisign.com<br>
isrg.trustid.ocsp.identrust.com<br>
ocsp.digicert.com<br>
ocsp.entrust.net<br>
ocsp.globalsign.com/ExtendedSSLSHA256CACross<br>
ocsp.globalsign.com/rootr1<br>
ocsp.globalsign.com/rootr2<br>
ocsp2.globalsign.com/rootr3<br>
ocsp.int-x3.letsencrypt.org/<br>
ocsp.msocsp.com<br>
ocsp.omniroot.com/baltimoreroot<br>
ocsp2.globalsign.com/gsextendvalsha2g3r3<br>
ocsp2.globalsign.com/gsorganizationvalsha2g2<br>
ocsp2.globalsign.com/gsorganizationvalsha2g3<br>
ocsp2.globalsign.com/rootr3<br>
ocspx.digicert.com<br>
s2.symcb.com<br>
sr.symcd.com<br>
su.symcd.com<br>
vassg142.ocsp.omniroot.com<br>
cdp1.public-trust.com/CRL/Omniroot2025.crl<br>
crl.entrust.net/2048ca.crl<br>
crl.entrust.net/g2ca.crl<br>
crl.entrust.net/level1k.crl<br>
crl.entrust.net/rootca1.crl<br>
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl<br>
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl<br>
crl.globalsign.com/gsorganizationvalsha2g3.crl<br>
crl.globalsign.com/root.crl<br>
crl.globalsign.net/root-r2.crl<br>
crl.globalsign.com/root-r3.crl<br>
crl.globalsign.net/root.crl<br>
crl.identrust.com/DSTROOTCAX3CRL.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl3.digicert.com/DigiCertGlobalRootCA.crl<br>
crl3.digicert.com/sha2-ev-server-g1.crl<br>
crl3.digicert.com/sha2-ha-server-g5.crl<br>
crl3.digicert.com/ssca-sha2-g5.crl<br>
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl4.digicert.com/DigiCertGlobalRootCA.crl<br>
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl<br>
crl4.digicert.com/sha2-ev-server-g1.crl<br>
crl4.digicert.com/sha2-ha-server-g5.crl<br>
crl4.digicert.com/ssca-sha2-g5.crl<br>
EVIntl-crl.verisign.com/EVIntl2006.crl<br>
EVSecure-crl.verisign.com/pca3-g5.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
s1.symcb.com/pca3-g5.crl<br>
sr.symcb.com/sr.crl<br>
su.symcb.com/su.crl<br>
vassg142.crl.omniroot.com/vassg142.crl<br>
aia.entrust.net/l1k-chain256.cer<br>
apps.identrust.com/roots/dstrootcax3.p7c<br>
<https://cacert.a.omniroot.com/vassg142.crt><br>
<https://cacert.a.omniroot.com/vassg142.der><br>
<https://cacert.omniroot.com/baltimoreroot.crt><br>
<https://cacert.omniroot.com/baltimoreroot.der><br>
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt<br>
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt<br>
cert.int-x3.letsencrypt.org/<br>
EVIntl-aia.verisign.com/EVIntl2006.cer<br>
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt<br>
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt<br>
sr.symcb.com/sr.crt<br>
su.symcb.com/su.crt<br>
<https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt><br>
<https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww1.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww2.crt><br>