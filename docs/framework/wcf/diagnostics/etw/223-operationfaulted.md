---
description: 'Дополнительные сведения: 223-Оператионфаултед'
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: e4155516e07568d4ee4ca76d63754ec4171e1064
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794290"
---
# <a name="223---operationfaulted"></a>223 - OperationFaulted

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|223|  
|Keywords|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие вызывается в том случае, если при вызове `OperationInvoker` модели службы по умолчанию обнаружено исключение, производное от `FaultException`.  
  
## <a name="message"></a>Сообщение  

 Метод «%1» вызывал исключение FaultException после того, как был вызван OperationInvoker. Длительность вызова метода составила «%2» мс.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|MethodName|`xs:string`|Имя CLR метода, который был вызван `OperationInvoker`.|  
|Длительность|`xs:long`|Время в миллисекундах, которое потребовалось `OperationInvoker`, чтобы вызвать метод.|  
|HostReference|`xs:string`|Для служб, размещенных на веб-узле, это поле является уникальным идентификатором службы в веб-иерархии. Его формат определяется как "имя веб-сайта виртуальный путь к приложению&#124;виртуальный путь службы&#124;ServiceName". Пример: "Default Web site/Калкулатораппликатион&#124;/Калкулаторсервице.СВК&#124;CalculatorService".|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
