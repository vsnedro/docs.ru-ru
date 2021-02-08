---
description: 'Дополнительные сведения: 224-Мессажесроттлеатсевентиперцент'
title: 224 - MessageThrottleAtSeventyPercent
ms.date: 03/30/2017
ms.assetid: 82bbbfd7-10d2-41fd-805d-2443b0c1b96b
ms.openlocfilehash: 14c08371c5db7e6f7deb0a5851a1d24dfc94475e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794277"
---
# <a name="224---messagethrottleatseventypercent"></a>224 - MessageThrottleAtSeventyPercent

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|224|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 При превышении одного из основных ограничителей службы создается событие `MessageThrottleExceeded`. Если всплеск активности уменьшился и текущее значение ограничителя составляет 70 процентов от текущего предела, то создается это событие. Обратите внимание, что это событие создается только один раз при замедлении активности. Если текущее значение находится вблизи отметки 70 процентов (например, 70, 69, 70, 71, 69), то только первое значение 70 процентов приводит к созданию события. После возникновения события все последующие превышения предела регулирования приводят к возникновению события `MessageThrottleExceeded`.  
  
## <a name="message"></a>Сообщение  

 Предел ограничителя %1 из %2 находится на отметке 70%%.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Throttle Name|`xs:string`|Имя превышенного ограничителя. `MaxConcurrentCalls`, `MaxConcurrentInstances` либо `MaxConcurrentSessions`,|  
|Ограничение|`xs:long`|Заданный в данный момент предел ограничителя.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
