---
title: Использование отслеживания для устранения неполадок приложений
ms.date: 03/30/2017
ms.assetid: 8851adde-c3c2-4391-9523-d8eb831490af
ms.openlocfilehash: fc9427d0c06ed67ea69669cab2aae64f39f7c10c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551292"
---
# <a name="using-tracking-to-troubleshoot-applications"></a>Использование отслеживания для устранения неполадок приложений
Windows Workflow Foundation (WF) позволяет отслеживанию сведений, связанных с рабочим процессом, чтобы предоставить подробные сведения о выполнении Windows Workflow Foundation приложения или службы. Узлы Windows Workflow Foundation могут собирать события рабочего процесса во время выполнения экземпляра рабочего процесса. Если рабочий процесс создает ошибки или исключения, можно использовать сведения об отслеживании Windows Workflow Foundation для устранения неполадок обработки.  
  
## <a name="troubleshooting-a-wf-using-wf-tracking"></a>Устранение неполадок WF с помощью отслеживания WF  
 Чтобы обнаружить ошибки в процессе обработки Windows Workflow Foundation действия, можно включить отслеживание с помощью профиля отслеживания, который запрашивает <xref:System.Activities.Tracking.ActivityStateRecord> состояние с ошибкой. Соответствующий запрос задан в следующем коде.  
  
```xml  
<activityStateQueries>  
              <activityStateQuery activityName="*">  
                <states>  
                  <state name="Faulted" />  
                </states>  
              </activityStateQuery>  
 </activityStateQueries>  
```  
  
 Если ошибка передается и обрабатывается в обработчике ошибок (например, в действии <xref:System.Activities.Statements.TryCatch>), это можно обнаружить с помощью записи <xref:System.Activities.Tracking.FaultPropagationRecord>. Запись <xref:System.Activities.Tracking.FaultPropagationRecord> указывает исходное действие, вызвавшее ошибку, и имя обработчика ошибок. <xref:System.Activities.Tracking.FaultPropagationRecord>Содержит сведения об ошибке в виде стека исключений для ошибки. Запрос для подписки на объект <xref:System.Activities.Tracking.FaultPropagationRecord> показан в следующем примере.  
  
```xml  
<faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
 </faultPropagationQueries>  
```  
  
 Если ошибка не обрабатывается в рабочем процессе, это создает необработанное исключение в экземпляре рабочего процесса, и работа экземпляра рабочего процесса прерывается. Для получения сведений о необработанном исключении профиль отслеживания должен запросить запись экземпляра рабочего процесса с состоянием `state name="UnhandledException"`, как указано в следующем примере.  
  
```xml  
<workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="UnhandledException" />  
                </states>  
              </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
 Когда экземпляр рабочего процесса обнаруживает необработанное исключение, <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord> объект создается, если включено отслеживание Windows Workflow Foundation.  
  
 Эта запись отслеживания содержит сведения об ошибке в виде стека исключений. Он содержит подробные сведения об источнике ошибки (например, о действии), вызвавшем сбой, и привело к необработанному исключению. Чтобы подписываться на события сбоя из Windows Workflow Foundation, включите отслеживание, добавив участника отслеживания. Настройте участника с профилем отслеживания, запрашивающим запись `ActivityStateQuery (state="Faulted")`, <xref:System.Activities.Tracking.FaultPropagationRecord> и `WorkflowInstanceQuery (state="UnhandledException")`.  
  
 Если отслеживание включено с использованием участника отслеживания ETW, события ошибок создаются в сеансе ETW. События можно просмотреть с помощью средства «Просмотр событий». Его можно найти в разделе **журналы приложений и служб Просмотр событий >. >Microsoft->Windows->сервер приложений — приложения** в канале аналитики.  
  
## <a name="see-also"></a>См. также

- [Мониторинг Windows Server App Fabric](/previous-versions/appfabric/ee677251(v=azure.10))
- [Мониторинг приложений с помощью App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))
