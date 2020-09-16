---
title: Устаревшие типы в Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: b0ec30d2778333537e781e6681927f7048b630ea
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543788"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Устаревшие типы в Windows Workflow Foundation
В .NET 4 команда разработки по рабочим процессам представила полностью новую подсистему рабочих процессов в пространстве имен <xref:System.Activities>. С выпуском бета-версии .NET 4,5 Мы помечаем большинство типов в "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> и "  <xref:System.Workflow.Runtime> пространства имен" как устаревшие.  
  
## <a name="obsolete-namespaces-and-tools"></a>Устаревшие пространства имен и средства  
 Следующие сборки содержат один и более открытых типов, которые станут устаревшими.  
  
- System.Workflow.Activities.dll  
  
- System.Workflow.ComponentModel.dll  
  
- System.Workflow.Runtime.dll  
  
- System.WorkflowServices.dll  
  
- Microsoft.Workflow.DebugController.dll  
  
- Microsoft.Workflow.Compiler.exe  
  
- Wfc.exe  
  
 В результате этого клиенты, использующие устаревшие API WF 3, увидят предупреждения при сборке с сообщением следующего вида:  
  
 **Предупреждение BC40000: X устарело: типы WF 3 являются устаревшими. Вместо этого используйте WF 4.** В одном из последующих выпусков (не в 4.5) типы будут удалены из .NET Framework, но временной промежуток до этого еще не определен. Текущий шаг позволяет донести наши планы до клиентов и дает им достаточно времени для перехода на новую модель WF4. Конечно, мы будем продолжать поддерживать эти типы WF 3 в [политике жизненного цикла служба поддержки Майкрософт](/lifecycle/). Существующие приложения WF3 будут работать без проблем в .NET 4,5, а Visual Studio 2012 будет поддерживать новые и существующие решения на основе WF3.  
  
 Основанные на правилах типы в пространстве имен <xref:System.Workflow.Activities.Rules>, не имеющие замены в WF 4.5, не устарели.  
  
 Клиенты, желающие перенести свои приложения в WF 4, смогут найти справку в [руководстве по миграции рабочего процесса 4](migration-guidance.md).
