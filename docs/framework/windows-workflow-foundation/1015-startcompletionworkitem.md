---
description: 'Дополнительные сведения: 1015-Старткомплетионворкитем'
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6c79a02b144aa1176eb1cb334c8430c8f0babc3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792925"
---
# <a name="1015---startcompletionworkitem"></a>1015 - StartCompletionWorkItem

## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1015|  
|Keywords|WFRuntime|  
|Level|Подробный|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  

 Указывает, что выполнение CompletionWorkItem начинается.  
  
## <a name="message"></a>Сообщение  

 Начато выполнение CompletionWorkItem для родительского действия «%1», DisplayName «%2», InstanceId «%3». Завершено действие «%4», DisplayName «%5», InstanceId «%6».  
  
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
