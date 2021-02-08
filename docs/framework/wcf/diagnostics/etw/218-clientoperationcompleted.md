---
description: 'Дополнительные сведения: 218-Клиентоператионкомплетед'
title: 218 - ClientOperationCompleted
ms.date: 03/30/2017
ms.assetid: b069bced-7bb2-4e01-8227-e5dbda17af09
ms.openlocfilehash: 3719b77ce653c5177cf7b92901ecd51982504b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794342"
---
# <a name="218---clientoperationcompleted"></a>218 - ClientOperationCompleted

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|218|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается клиентом сразу после завершения операции. Для односторонних операций оно создается сразу после успешной отправки сообщения. Для операций типа «запрос-ответ» оно создается после получения ответа.  
  
## <a name="message"></a>Сообщение  

 Клиент завершил выполнение действия «%1», связанного с контрактом «%2». Сообщение было отправлено «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Действие|xs:string|Заголовок действия SOAP исходящего сообщения.|  
|Contract Name|`xs:string`|Имя контракта. Пример: ICalculator.|  
|Назначение|`xs:string`|Адрес конечной точки службы, которой было отправлено сообщение.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
