---
title: Сквозная трассировка
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: a8c06b9e4f70321e6ef3756863390dc62c659557
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243954"
---
# <a name="end-to-end-tracing"></a>Сквозная трассировка

Трассировка "до конца" (E2E) позволяет разработчикам следовать за выполнением кода в инфраструктуре Windows Communication Foundation (WCF), чтобы определить причину сбоя пути кода или предоставить подробную трассировку для планирования емкости и анализа производительности. Windows Communication Foundation (WCF) предоставляет три механизма корреляции, помогающие диагностировать причину ошибки: действия, передачи и распространения.  
  
 В разделе Сценарии сквозной [трассировки](end-to-end-tracing-scenarios.md) приведен список комплексных сценариев трассировки, а также соответствующие действия и структура трассировки.  
  
## <a name="in-this-section"></a>в этом разделе  

 [Действие](activity.md): описывает трассировки действий в модели трассировки Windows Communication Foundation (WCF).  
  
 [Перемещение](transfer.md). описывает перемещение в модели трассировки Windows Communication Foundation (WCF) и использование функции перемещения для корреляции действий в конечных точках.  
  
 [Распространение](propagation.md). описывает распространение действий в модели трассировки Windows Communication Foundation (WCF) и использование распространения для корреляции действий между конечными точками.  
  
 [Сводка типов трассировок](trace-type-summary.md)  
  
 Краткий обзор всех типов трассировок действий  
  
## <a name="see-also"></a>См. также

- [Настройка трассировки](configuring-tracing.md)
- [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [Сценарии сквозной трассировки](end-to-end-tracing-scenarios.md)
- [Программа Service Trace Viewer (SvcTraceViewer.exe)](../../service-trace-viewer-tool-svctraceviewer-exe.md)
