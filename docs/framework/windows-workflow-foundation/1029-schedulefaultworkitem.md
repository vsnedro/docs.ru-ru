---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: 5c109607b2d353d3d4a5a693f29ab66bb76c8398
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275093"
---
# <a name="1029---schedulefaultworkitem"></a>1029 - ScheduleFaultWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1029|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что FaultWorkItem было предназначено.  
  
## <a name="message"></a>Сообщение  

 Фаултворкитем был запланирован для действия "%1", DisplayName: "%2", InstanceId: "%3".  Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Имя типа действия с ошибкой.|  
|FaultActivityDisplayName|xs:string|Отображаемое имя действия с ошибкой.|  
|FaultActivityInstanceId|xs:string|Идентификатор экземпляра действия с ошибкой.|  
|ExceptionActivity|xs:string|Имя типа действия, вызвавшего исключение.|  
|ExceptionActivityDisplayName|xs:string|Отображаемое имя действия, вызвавшего исключение.|  
|ExceptionActivityInstanceId|xs:string|Идентификатор экземпляра действия, вызвавшего исключение.|  
|Исключение|xs:string|Сведения об исключении|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
