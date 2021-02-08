---
description: 'Дополнительные сведения: 217-Клиентоператионпрепаред'
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: eab6a9a654e6e48a8831f238cdf3a3bf7a9f62d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794355"
---
# <a name="217---clientoperationprepared"></a>217 - ClientOperationPrepared

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|217|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается клиентом непосредственно перед отправкой операции службе.  
  
## <a name="message"></a>Сообщение  

 Клиент выполняет действие «%1», связанное с контрактом «%2». Сообщение будет отправлено «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|`xs:string`|Заголовок действия SOAP исходящего сообщения.|  
|Contract Name|`xs:string`|Имя контракта. Пример: ICalculator.|  
|Назначение|`xs:string`|Адрес конечной точки службы, которой отправляется сообщение.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
