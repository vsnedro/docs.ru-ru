---
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: 832ced406b6079fad8f4b9bea512a6d390bdcc0f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241945"
---
# <a name="219---serviceexception"></a>219 - ServiceException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|219|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Level|Ошибка|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается при обнаружении службой WCF необработанного исключения. В число необработанных входят исключения, возникшие во время активации, обработки сообщений и выполнения пользовательского кода.  
  
## <a name="message"></a>Сообщение  

 Во время обработки сообщения возникло необработанное исключение типа «%2». Полное исключение ToString: %1.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExceptionToString|`xs:string`|Результат вызова метода `ToString`() относительно исключения CLR.|  
|ExceptionTypeName|`xs:string`|Имя CLR FullName типа исключения.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
