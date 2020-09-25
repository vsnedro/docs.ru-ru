---
title: Использование заметок в запросах
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 3dd5d19cc303314386ae62ba67f7eec978f6d80b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185370"
---
# <a name="using-annotation-in-queries"></a>Использование заметок в запросах

Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения. Например, может потребоваться, чтобы несколько записей отслеживания в нескольких рабочих процессах были помечены как "почтовый сервер" = = "почта Server1". Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.  
  
## <a name="adding-annotations"></a>Добавление заметок  

 В следующем примере показано, как добавить заметку к запросу отслеживания.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
> Эти элементы запроса могут быть использованы для создания профиля отслеживания. Профиль отслеживания можно создать в коде или в файле конфигурации.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Отслеживание и трассировка рабочих процессов](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md)
