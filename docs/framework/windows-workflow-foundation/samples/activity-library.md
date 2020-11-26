---
title: Библиотека действий
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 1a0c289315d7181645573098916788f18493abb8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245713"
---
# <a name="activity-library"></a>Библиотека действий

Этот раздел содержит примеры, демонстрирующие Расширенные пользовательские действия в Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>в этом разделе

 [Настраиваемое действие SendMail](sendmail-custom-activity.md)  
 В этом примере описывается создание настраиваемого действия, которое является производным от <xref:System.Activities.AsyncCodeActivity>, для отправки почты с помощью SMTP для работы в приложении рабочего процесса.  
  
 [Параллельное действие ForEach с ограничением](throttled-parallel-foreach.md)  
 Демонстрирует, что действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach%601> за одним исключением, которое позволяет настроить фактор одновременности для ограничения количества одновременно выполняющихся ветвей.
  
 [Действия доступа к базе данных](database-access-activities.md)  
 Демонстрирует создание действий, которые позволяют обращаться к базам данных для получения или изменения информации и использовать [ADO.NET](../../data/adonet/index.md) для доступа к базе данных.  
  
 [Реализованное действие политики в .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Демонстрируется, как действие ExternalizedPolicy4 разрешает выполнение существующих Windows Workflow Foundation в объектах .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) непосредственно с помощью обработчика правил, который поставляется в WF 3,5.
  
 [Неуниверсальное действие ForEach](non-generic-foreach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ForEach%601>.  
  
 [Неуниверсальное действие ParallelForEach](non-generic-parallelforeach.md)  
 Показывает, как создать неуниверсальную версию действия <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Получение GetWorkflowInstanceId](get-workflowinstanceid.md)  
 Демонстрирует, как можно использовать пользовательское действие `GetWorkflowInstanceId` для возвращения идентификатора экземпляра рабочего процесса.
