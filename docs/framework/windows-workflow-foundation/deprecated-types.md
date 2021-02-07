---
description: 'Подробнее: устаревшие типы в Windows Workflow Foundation'
title: Устаревшие типы в Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: a536f67708c5913040848df52f178dcc2a361f6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742437"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Устаревшие типы в Windows Workflow Foundation

В .NET 4 команда разработки по рабочим процессам представила полностью новую подсистему рабочих процессов в пространстве имен <xref:System.Activities>. При выпуске бета-версии платформа .NET Framework 4,5 Мы помечаем большинство типов в "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> и "  <xref:System.Workflow.Runtime> пространства имен" как устаревшие.

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

 **Предупреждение BC40000: X устарело: типы WF 3 являются устаревшими. Вместо этого используйте WF 4.** В одном из последующих выпусков (не в 4.5) типы будут удалены из .NET Framework, но временной промежуток до этого еще не определен. Текущий шаг позволяет донести наши планы до клиентов и дает им достаточно времени для перехода на новую модель WF4. Конечно, мы будем продолжать поддерживать эти типы WF 3 в [политике жизненного цикла служба поддержки Майкрософт](/lifecycle/). Существующие приложения WF3 будут выполняться без проблем в платформа .NET Framework 4,5, а Visual Studio 2012 будет поддерживать новые и существующие решения на основе WF3.

 Основанные на правилах типы в пространстве имен <xref:System.Workflow.Activities.Rules>, не имеющие замены в WF 4.5, не устарели.

 Клиенты, желающие перенести свои приложения в WF 4, смогут найти справку в [руководстве по миграции рабочего процесса 4](migration-guidance.md).
