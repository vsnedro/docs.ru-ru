---
description: 'Дополнительные сведения: 225-Трацекоррелатионкэйс'
title: 225 - TraceCorrelationKeys
ms.date: 03/30/2017
ms.assetid: d9083aaf-3816-4c1c-bae0-2d7f49628345
ms.openlocfilehash: c5fdb9305815cdc4df6bbae3e54209d2b5cffd9d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778117"
---
# <a name="225---tracecorrelationkeys"></a>225 - TraceCorrelationKeys

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|225|  
|Keywords|Troubleshooting, ServiceModel|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие создается, если в качестве службы рабочего процесса используется корреляция на основе содержимого. Оно содержит ключи, применяемые для корреляции сообщения с экземпляром.  
  
## <a name="message"></a>Сообщение  

 Вычисленный ключ корреляции «%1» с использованием значений «%2» в родительской области «%3».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Instance Key|`xs:GUID`|Ключ, созданный из значений корреляции.|  
|Значения|`xs:string`|Значения, использованные для вычисления ключа экземпляра корреляции.|  
|Parent Scope|`xs:string`||  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле служит уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
