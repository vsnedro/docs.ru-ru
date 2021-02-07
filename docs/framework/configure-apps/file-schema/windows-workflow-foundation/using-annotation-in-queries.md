---
description: 'Дополнительные сведения о: использование аннотации в запросах'
title: Использование заметок в запросах
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 97423fe8ea7d90522a5f469adda5f645aa7e4485
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698028"
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
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [Отслеживание и трассировка рабочих процессов](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Профили отслеживания](../../../windows-workflow-foundation/tracking-profiles.md)
