---
description: Дополнительные сведения см. в статье вопросы безопасности для защищенных сеансов.
title: Соображения о защите безопасных сеансов
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: 565797d9354d4c274dd843350d7c9035e5413c07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632611"
---
# <a name="security-considerations-for-secure-sessions"></a>Соображения о защите безопасных сеансов

Необходимо принять во внимание следующие элементы, влияющие на безопасность при реализации безопасных сеансов. Дополнительные сведения о вопросах безопасности см. в статье [вопросы безопасности](security-considerations-in-wcf.md) и рекомендации [по обеспечению безопасности](best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Безопасные сеансы и метаданные  

 Если установлен безопасный сеанс и <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> свойству присвоено значение `false` , Windows Communication Foundation (WCF) отправляет `mssp:MustNotSendCancel` утверждение в составе метаданных в документе языка описания веб-служб (WSDL) для конечной точки службы. Проверочное утверждение `mssp:MustNotSendCancel` информирует клиентов о том, что служба не отвечает на запросы, чтобы отменить безопасный сеанс. Если <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> свойство имеет значение `true` , WCF не создает `mssp:MustNotSendCancel` утверждение в документе WSDL. Предполагается, что если безопасный сеанс клиентам больше не требуется, они передают службе запрос отмены. При создании клиента с помощью [служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)клиентский код реагирует соответствующим образом на присутствие или отсутствие `mssp:MustNotSendCancel` утверждения.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Безопасные диалоги и пользовательские маркеры  

 Из-за определения, сделанного в спецификации WS-SecureConversation, существует несколько проблем, связанных со смешиванием пользовательских маркеров и производных ключей. Спецификация говорит, что `wsse:SecurityTokenReference` является необязательным элементом, который ссылается на производный токен: " `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Этот необязательный элемент используется для указания маркера контекста безопасности, маркера безопасности или общего ключа или секрета, используемого для наследования. Если указанные компоненты не заданы, предполагается, что получатель может определить общий ключ из контекста сообщения. Если контекст не может быть определен, возникает ошибка, например `wsc:UnknownDerivationSource` ".  
  
 Это означает, что если требуется получить пользовательский маркер, необходимо зашифровать его тип предложения в элементе `SecurityTokenReference`. Формирование ключей можно отключить, но по умолчанию ключи формируются. Если ключ не шифруется, сериализация маркера производного ключа происходит успешно, но при попытке десериализовать его вызывается исключение.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Вопросы безопасности](security-considerations-in-wcf.md)
- [Рекомендации по безопасности](best-practices-for-security-in-wcf.md)
