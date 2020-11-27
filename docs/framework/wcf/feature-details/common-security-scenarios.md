---
title: Типовые сценарии безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: 21c8279890d1d1cf746e98f875efb6b1ff869c73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295084"
---
# <a name="common-security-scenarios"></a>Типовые сценарии безопасности

В подразделах этого раздела рассматривается множество возможных конфигураций безопасности клиентов и служб. Конфигурация зависит от ряда факторов: например, находится ли служба или клиент в интрасети, или чем обеспечивается безопасность - Windows или транспортом (таким как HTTPS).  
  
## <a name="in-this-section"></a>в этом разделе  

 [Незащищенные интернет-клиент и служба](internet-unsecured-client-and-service.md)  
 Пример общедоступных, незащищенных клиента и службы.  
  
 [Незащищенные интранет-клиент и служба](intranet-unsecured-client-and-service.md)  
 Служба Basic Windows Communication Foundation (WCF), разработанная для предоставления информации о защищенной частной сети приложению WCF.  
  
 [Безопасность транспорта с обычной проверкой подлинности](transport-security-with-basic-authentication.md)  
 Приложение, позволяющее клиентам входить в систему с использованием пользовательской проверки подлинности.  
  
 [Безопасность транспорта с проверкой подлинности Windows](transport-security-with-windows-authentication.md)  
 Клиент и служба, защищенные механизмом безопасности Windows.  
  
 [Безопасность транспорта с анонимным клиентом](transport-security-with-an-anonymous-client.md)  
 Сценарий с использованием механизма безопасности транспорта (такого как HTTPS) для обеспечения конфиденциальности и целостности.  
  
 [Безопасность транспорта с проверкой подлинности с использованием сертификатов](transport-security-with-certificate-authentication.md)  
 Клиент и служба, защищенные сертификатом.  
  
 [Безопасность сообщений с анонимным клиентом](message-security-with-an-anonymous-client.md)  
 Показывает клиент и службу, защищенные с помощью безопасности сообщений WCF.  
  
 [Безопасность сообщений при использовании клиентом учетных данных пользователя](message-security-with-a-user-name-client.md)  
 Клиент - приложение Windows Forms, позволяющее клиентам входить в систему с использованием имени пользователя и пароля домена.  
  
 [Безопасность сообщений при использовании клиентом сертификата](message-security-with-a-certificate-client.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования по протоколу TLS.  
  
 [Безопасность сообщений с клиентом Windows](message-security-with-a-windows-client.md)  
 Разновидность клиента с сертификатом. Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования TLS.  
  
 [Безопасность сообщений с использованием клиента Windows без согласования учетных данных](message-security-with-a-windows-client-without-credential-negotiation.md)  
 Клиент и служба, защищенные доменом Kerberos.  
  
 [Безопасность сообщений с использованием взаимных сертификатов](message-security-with-mutual-certificates.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Сертификат сервера распространяется вместе с приложением и доступен внештатно.  
  
 [Безопасность сообщений с использованием выданных маркеров](message-security-with-issued-tokens.md)  
 Федеративная безопасность, позволяющая установить доверие между независимыми доменами.  
  
 [Доверенная подсистема](trusted-subsystem.md)  
 Клиент обращается к одной или нескольким веб-службам, распределенным по сети. Веб-службы обращаются к дополнительным ресурсам (таким как базы данных или другие веб-службы), которые должны быть защищены.  
  
## <a name="reference"></a>Справочник  

 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  

 [Авторизация](authorization-in-wcf.md)  
  
 [Обзор безопасности](security-overview.md)  
  
 [Безопасность](security.md)  
  
 [Привязки и безопасность](bindings-and-security.md)  
  
 [Защита служб и клиентов](securing-services-and-clients.md)  
  
 [Аутентификация](authentication-in-wcf.md)  
  
 [Авторизация](authorization-in-wcf.md)  
  
 [Федерация и выданные маркеры](federation-and-issued-tokens.md)  
  
 [Аудит](auditing-security-events.md)  
  
## <a name="see-also"></a>См. также

- [Руководство и рекомендации по безопасности](security-guidance-and-best-practices.md)
- [Модель безопасности для Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
