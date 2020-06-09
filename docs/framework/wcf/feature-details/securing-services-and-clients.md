---
title: Защита служб и клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: db0a0dcfbe04a7b7dbfabfed59f9b8637d0a2797
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586212"
---
# <a name="securing-services-and-clients"></a>Защита служб и клиентов
Сведения в этом разделе посвящены безопасности программирования в Windows Communication Foundation (WCF). Обычно обеспечение безопасности включает выбор подходящей предоставляемой системой привязки, задание свойств элемента безопасности и задание свойств поведений службы, управляющих извлечением учетных данных для использования службой или клиентом. Эти методы охватывают требования большинства пользователей для большинства сценариев, как показано в [типичных сценариях безопасности](common-security-scenarios.md). Если ваш сценарий требует больше возможностей, сначала ознакомьтесь [с возможностями безопасности с помощью пользовательских привязок](security-capabilities-with-custom-bindings.md). Если решение не очевидно, см. раздел [расширение безопасности](../extending/extending-security.md). При создании (или взаимодействии с) системой, использующей обширные утверждения, см. разделы в разделе [авторизация](authorization-in-wcf.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Программирование безопасности WCF](programming-wcf-security.md)  
 Общие сведения о модели программирования, используемой для защиты сообщений.  
  
 [Общие сведения о безопасности транспорта](transport-security-overview.md)  
 Общие сведения о защите сообщений на транспортном уровне.  
  
 [Безопасность сообщений](message-security-in-wcf.md)  
 Суммирует причины использования безопасности на уровне сообщений в Windows Communication Foundation (WCF).  
  
 [Безопасные сеансы](secure-sessions.md)  
 Обсуждение вопросов, необходимых при защите сеанса WCF.  
  
 [Работа с сертификатами](working-with-certificates.md)  
 Описание некоторых стандартных задач, которые требуется выполнять при использовании сертификатов X.509.  
  
## <a name="reference"></a>Справочник  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Основные понятия безопасности](security-concepts.md)  
  
 [Расширение безопасности](../extending/extending-security.md)  
  
 [Типовые сценарии безопасности](common-security-scenarios.md)  
  
 [Привязки и безопасность](bindings-and-security.md)  
  
 [Возможности безопасности при использовании пользовательских привязок](security-capabilities-with-custom-bindings.md)  
  
 [Расширение безопасности](../extending/extending-security.md)  
  
 [Авторизация](authorization-in-wcf.md)  
  
## <a name="see-also"></a>См. также

- [Базовое программирование для WCF](../basic-wcf-programming.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
