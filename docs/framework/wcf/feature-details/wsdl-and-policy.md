---
title: WSDL и политика
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: 201920a8ebf639c74acfb20b2e990c8bbc0c5b55
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600105"
---
# <a name="wsdl-and-policy"></a>WSDL и политика
В этом разделе рассматриваются Windows Communication Foundation (WCF) WSDL 1,1, WS-Policy и WS-Полициаттачмент, а также дополнительные утверждения WS-Policy и расширения WSDL 1,1, появившиеся в WCF.  
  
 В WCF реализованы спецификации WS-Policy и WS-Полициаттачмент, которые передаются в W3C с ограничениями и пояснениями, описанными в этом документе.  
  
 В этом документе используются префиксы и пространства имен, приведенные в следующей таблице.  
  
|Prefix|Пространство имен|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|wsp (WS-Policy 1.5)|`http://www.w3.org/ns/ws-policy`|  
|http|`http://schemas.microsoft.com/ws/06/2004/policy/http`|  
|msmq|`http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq`|  
|msf|`http://schemas.microsoft.com/ws/2006/05/framing/policy`|  
|mssp|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
|msc|`http://schemas.microsoft.com/ws/2005/12/wsdl/contract`|  
|cdp|`http://schemas.microsoft.com/net/2006/06/duplex`|  
  
## <a name="wcf-wsdl11-extensions"></a>Расширения WCF WSDL1.1  
 WCF использует следующие расширения WSDL 1.1 для описания требований к сеансу контракта.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs: Boolean указывает, что эта операция инициирует сеанс WCF; значение по умолчанию — `false` .  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs: Boolean указывает, что эта операция завершает сеанс WCF; значение по умолчанию — `false` .  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, показывает, что этот контракт требует установления сеанса.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>Универсальные коды ресурса (URI) транспорта привязки SOAP 1.x HTTP  
 WCF использует следующие URI для указания транспортов, которые будут использоваться для элементов расширения привязки WSDL 1,1, SOAP 1,1 и SOAP 1,2.  
  
|Транспорт|URI|  
|---------------|---------|  
|HTTP|`http://schemas.xmlsoap.org/soap/http`|  
|TCP|`http://schemas.microsoft.com/soap/tcp`|  
|MSMQ|`http://schemas.microsoft.com/soap/msmq`|  
|Именованные каналы|`http://schemas.microsoft.com/soap/named-pipe`|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Утверждения политики, реализуемые WCF  
 В дополнение к утверждениям политики, появившимся в спецификациях веб-служб (WS-*) и упомянутых в других разделах этого документа, в WCF реализуются следующие утверждения политики.  
  
|Утверждение политики|Субъект политики|Описание|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Конечная точка|Конечная точка использует обычную проверку подлинности HTTP.|  
|http:HttpDigestAuthentication|Конечная точка|Конечная точка использует дайджест-проверку подлинности HTTP.|  
|http:HttpNegotiateAuthentication|Конечная точка|Конечная точка использует согласованную проверку подлинности HTTP.|  
|http:HttpNtlmAuthentication|Конечная точка|Конечная точка использует проверку подлинности HTTP NTLM.|  
|msf:Streamed|Конечная точка|Конечная точка использует кадрирование потокового сообщения. Это утверждение используется с протоколом кадрирования сообщения, предоставляемого для таких транспортов как TCP и именованные каналы.|  
|msf:SslTransportSecurity|Конечная точка|Конечная точка использует с кадрированием сообщения безопасность на уровне транспорта (TLS).|  
|msf:WindowsTransportSecurity|Конечная точка|Конечная точка использует с кадрированием сообщения согласование с поставщиком безопасности (SPNEGO).|  
|msmq:MsmqBestEffort|Конечная точка|MSMQ с гарантиями наилучшего из возможного.|  
|msmq:MsmqSession|Конечная точка|MSMQ с гарантиями сеансов.|  
|msmq:MsmqVolatile|Конечная точка|Неустойчивый MSMQ.|  
|msmq:Authenticated|Конечная точка|Используется проверка подлинности с транспортом MSMQ.|  
|msmq:WindowsDomain|Конечная точка|MSMQ использует проверку подлинности домена Windows.|  
|cdp:CompositeDuplex|Конечная точка|Конечная точка использует два отдельных подключения встречных транспортов для входящих и исходящих сообщений.|  
|mssp:RsaToken|вложена|Утверждение маркера ключа RSA. Это требование, как правило, удовлетворяется ключом RSA, сериализуемым непосредственно как часть информации о ключе в разрешающей подписи.|  
|mssp:SslContextToken|вложена|Требует использования SecurityContextToken, полученного при подтверждении двоичного протокола TLS с помощью WS-Trust. Вложенные утверждения включают sp:RequireDerivedKeys, mssp:MustNotSendCancel и mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|вложена|Задает требование о том, что сообщения запроса маркера безопасности (RST) [WS-Trust] с использованием привязки Cancel [WS-Trust, WS-SC] не должны отправляться издателю заданного SecurityContextToken. Если присутствует это утверждение, такие сообщения запроса не должны отправляться издателю. Если это утверждение отсутствует, такие сообщения запроса могут отправляться издателю.|  
|mssp:RequireClientCertificate|вложена|Этот необязательный элемент задает требование о том, что сертификат клиента должен предоставляться как часть протокола TLSNEGO. Если это утверждение присутствует, сертификат клиента должен быть предоставлен. Если это утверждение отсутствует, сертификат клиента предоставляться не должен. Это утверждение не должно использоваться за пределами mssp:SslContextToken.|  
  
## <a name="see-also"></a>Дополнительно

- [Пользовательская публикация WSDL](../samples/custom-wsdl-publication.md)
- [Практическое руководство. Экспорт пользовательской информации WSDL](../extending/how-to-export-custom-wsdl.md)
- [Практическое руководство. Импорт пользовательской информации WSDL](../extending/how-to-import-custom-wsdl.md)
