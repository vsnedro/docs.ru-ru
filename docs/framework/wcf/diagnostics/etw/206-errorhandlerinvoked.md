---
description: 'Дополнительные сведения: 206-Еррорхандлеринвокед'
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: addbcbdea25c7f8e7515b743e98e426476fa0b28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783785"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|206|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается после того, как обработчик `ErrorHandler` начинает обрабатывать исключение, возникшее в операции службы.  
  
## <a name="message"></a>Сообщение  

 Диспетчер вызвал ErrorHandler типа "%1" с исключением типа "%3". ErrorHandled == '%2'.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|Имя CLR FullName типа вызванного инспектора `ErrorHandler`.|  
|Обработанные|`xs:unsignedByte`|Значение `true`, если обработчик ошибок обработал ошибку, в противном случае значение `false`.|  
|ExceptionTypeName|`xs:string`|Имя CLR FullName обрабатываемого исключения.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
