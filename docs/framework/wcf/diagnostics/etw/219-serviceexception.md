---
description: 'Дополнительные сведения: 219-ServiceException'
title: 219 - ServiceException
ms.date: 03/30/2017
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
ms.openlocfilehash: b2ac12d6c5c68517b085b39dd7d0f81c39db9ebd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794329"
---
# <a name="219---serviceexception"></a>219 - ServiceException

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|219|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Ошибка|  
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
