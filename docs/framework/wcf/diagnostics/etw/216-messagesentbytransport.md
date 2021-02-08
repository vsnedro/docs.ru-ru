---
description: 'Дополнительные сведения: 216-Мессажесентбитранспорт'
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: 34c10fbbf61adde102641cb44db6645ea648a646
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794381"
---
# <a name="216---messagesentbytransport"></a>216 - MessageSentByTransport

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|216|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие возникает при отправке сообщения транспортом на основе TCP. Обратите внимание, что в рамках одной операции между клиентом и службой может быть передано несколько сообщений уровня транспорта. Это может быть вызвано особенностями инфраструктуры (и требования безопасности - хороший пример). Таким образом, количество выдаваемых событий **мессажесентбитранспорт** зависит от привязки службы и ее конфигурации.  
  
## <a name="message"></a>Сообщение  

 Транспорт отправил сообщение «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|DestinationAddress|`xs:string`|Адрес, на который было отправлено сообщение запроса.|  
|HostReference|xs:string|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
