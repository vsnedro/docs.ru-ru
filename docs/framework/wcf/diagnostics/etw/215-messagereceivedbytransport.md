---
description: 'Дополнительные сведения: 215-Мессажерецеиведбитранспорт'
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: e9645cfc8c4013f8891cb645db7df35477a57412
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794368"
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|215|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие происходит, когда транспорт на основе TCP получает сообщение. Обратите внимание, что на транспортном уровне для одной операции между клиентом и службой может быть передано несколько сообщений. Это может зависеть от инфраструктуры, и требования безопасности - хороший пример. Следовательно, количество создаваемых событий `MessageReceivedByTransport` может отличаться в зависимости от привязки службы и ее настроек.  
  
> [!NOTE]
> Это событие не создается для односторонних транспортов.  
  
## <a name="message"></a>Сообщение  

 Диспетчер получил сообщение от «%1».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Listen Address|`xs:string`|Адрес, получивший сообщение.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
