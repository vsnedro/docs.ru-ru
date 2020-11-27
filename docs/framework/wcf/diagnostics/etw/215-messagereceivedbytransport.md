---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: 2f247e751a0690f13d059eff29d633c6d047775d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279081"
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|215|  
|Keywords|Troubleshooting, ServiceModel|  
|Level|Сведения|  
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
