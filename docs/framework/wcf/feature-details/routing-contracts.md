---
title: Контракты маршрутизации
ms.date: 03/30/2017
ms.assetid: 9ceea7ae-ea19-4cf9-ba4f-d071e236546d
ms.openlocfilehash: 4c75034a8fdbf02bf568bc5392361113a37427be
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295500"
---
# <a name="routing-contracts"></a>Контракты маршрутизации

Контракты маршрутизации определяют схемы обмена сообщениями, которые может обрабатывать служба маршрутизации.  Эти контракты являются бестиповыми, с их помощью служба может получать сообщение без набора знаний о схеме сообщения или действии. Благодаря этому служба маршрутизации может перенаправлять сообщения без дополнительной настройки под особенности маршрутизируемых сообщений.  
  
## <a name="routing-contracts"></a>Контракты маршрутизации  

 Поскольку служба маршрутизации принимает общий объект сообщения WCF, наиболее важным аспектом при выборе контракта является форма канала, который будет использоваться для связи с клиентами и серверами. При обработке сообщений служба маршрутизации использует симметричные циклы обработки сообщений, поэтому, как правило, форма входящего контракта должна быть такой же, как форма исходящего контракта. Однако в некоторых случаях диспетчер Service Model может изменять фигуры, например, когда диспетчер преобразует дуплексный канал в канал запроса-ответа или удаляет поддержку сеанса из канала, если он не является обязательным и не используется (т **. е. Если SessionMode. Allowed**, преобразование **иинпутсессиончаннел** в **IInputChannel**).  
  
 Для поддержки этих циклов сообщений служба маршрутизации предоставляет контракты из пространства имен <xref:System.ServiceModel.Routing>, которые должны использоваться при определении конечных точек службы, используемых службой маршрутизации. Эти контракты являются бестиповыми, что позволяет принимать любые типы сообщений или действия, а также позволяет службе маршрутизации обрабатывать сообщения без набора знаний их схемы. Дополнительные сведения о контрактах, используемых службой маршрутизации, см. в разделе [Маршрутизация контрактов](routing-contracts.md).  
  
 Контракты, предоставляемые службой маршрутизации, находятся в пространстве имен <xref:System.ServiceModel.Routing>, они описаны в следующей таблице.  
  
|Контракт|Фигурная|Форма канала|  
|--------------|-----------|-------------------|  
|<xref:System.ServiceModel.Routing.ISimplexDatagramRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|IInputChannel-> IOutputChannel|  
|<xref:System.ServiceModel.Routing.ISimplexSessionRouter>|SessionMode = SessionMode.Required<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true|Иинпутсессиончаннел-> IOutputSessionChannel|  
|<xref:System.ServiceModel.Routing.IRequestReplyRouter>|SessionMode = SessionMode.Allowed<br /><br /> AsyncPattern = true|IReplyChannel-> IRequestChannel|  
|<xref:System.ServiceModel.Routing.IDuplexSessionRouter>|SessionMode=SessionMode.Required<br /><br /> CallbackContract=typeof(ISimplexSession)<br /><br /> AsyncPattern = true<br /><br /> IsOneWay = true<br /><br /> TransactionFlow(TransactionFlowOption.Allowed)|Идуплекссессиончаннел-> Идуплекссессиончаннел|  
  
## <a name="see-also"></a>См. также

- [Служба маршрутизации](routing-service.md)
- [Введение в маршрутизацию](routing-introduction.md)
