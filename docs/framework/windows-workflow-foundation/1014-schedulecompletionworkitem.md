---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 7fd93683851c5a8c4ab253272c3f2129b3f0bb49
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275561"
---
# <a name="1014---schedulecompletionworkitem"></a>1014 - ScheduleCompletionWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1014|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что элемент CompletionWorkItem был запланирован.  
  
## <a name="message"></a>Сообщение  

 Комплетионворкитем был запланирован для родительского действия "%1", DisplayName: "%2", InstanceId: "%3".  Завершено действие «%4», DisplayName «%5», InstanceId «%6».  
  
## <a name="details"></a>Сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ParentActivity|xs:string|Имя типа родительского действия.|  
|ParentDisplayName|xs:string|Отображаемое имя родительского действия.|  
|ParentInstanceId|xs:string|Идентификатор экземпляра родительского действия.|  
|CompletedActivity|xs:string|Имя типа завершенного действия.|  
|CompletedActivityDisplayName|xs:string|Отображаемое имя завершенного действия.|  
|CompletedActivityInstanceId|xs:string|Идентификатор экземпляра завершенного действия.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
