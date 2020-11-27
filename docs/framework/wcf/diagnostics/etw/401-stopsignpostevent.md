---
title: 401 - StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: e549a8aabd0a54022000515050cde19dc4f20dd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294070"
---
# <a name="401--stopsignpostevent"></a>401 - StopSignPostEvent

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|401|  
|Keywords|Устранение неполадок|  
|Level|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  

 Это событие отмечает окончание сквозного действия. В ней содержится имя действия.  
  
## <a name="message"></a>Сообщение  

 Граница действия.  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Расширенные данные|`xs:string`|Имя действия.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
