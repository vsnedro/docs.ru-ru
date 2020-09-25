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
# <a name="using-annotation-in-queries"></a><span data-ttu-id="9ef6c-102">Использование заметок в запросах</span><span class="sxs-lookup"><span data-stu-id="9ef6c-102">Using Annotation in Queries</span></span>

<span data-ttu-id="9ef6c-103">Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.</span><span class="sxs-lookup"><span data-stu-id="9ef6c-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="9ef6c-104">Например, может потребоваться, чтобы несколько записей отслеживания в нескольких рабочих процессах были помечены как "почтовый сервер" = = "почта Server1".</span><span class="sxs-lookup"><span data-stu-id="9ef6c-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="9ef6c-105">Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="9ef6c-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="9ef6c-106">Добавление заметок</span><span class="sxs-lookup"><span data-stu-id="9ef6c-106">Adding Annotations</span></span>  

 <span data-ttu-id="9ef6c-107">В следующем примере показано, как добавить заметку к запросу отслеживания.</span><span class="sxs-lookup"><span data-stu-id="9ef6c-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="9ef6c-108">Эти элементы запроса могут быть использованы для создания профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="9ef6c-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="9ef6c-109">Профиль отслеживания можно создать в коде или в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9ef6c-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef6c-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ef6c-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [\<participants>](participants.md)
- [<span data-ttu-id="9ef6c-111">Отслеживание и трассировка рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9ef6c-111">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9ef6c-112">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="9ef6c-112">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
