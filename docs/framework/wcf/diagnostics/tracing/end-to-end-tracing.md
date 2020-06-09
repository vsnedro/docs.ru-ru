---
title: Сквозная трассировка
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: fc8fc448bdcf94ab25349f6b34961a34e5ed2a5a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598584"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="93b00-102">Сквозная трассировка</span><span class="sxs-lookup"><span data-stu-id="93b00-102">End-to-End Tracing</span></span>
<span data-ttu-id="93b00-103">Трассировка "до конца" (E2E) позволяет разработчикам следовать за выполнением кода в инфраструктуре Windows Communication Foundation (WCF), чтобы определить причину сбоя пути кода или предоставить подробную трассировку для планирования емкости и анализа производительности.</span><span class="sxs-lookup"><span data-stu-id="93b00-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="93b00-104">Windows Communication Foundation (WCF) предоставляет три механизма корреляции, помогающие диагностировать причину ошибки: действия, передачи и распространения.</span><span class="sxs-lookup"><span data-stu-id="93b00-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="93b00-105">В разделе Сценарии сквозной [трассировки](end-to-end-tracing-scenarios.md) приведен список комплексных сценариев трассировки, а также соответствующие действия и структура трассировки.</span><span class="sxs-lookup"><span data-stu-id="93b00-105">See [End-To-End Tracing Scenarios](end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93b00-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="93b00-106">In This Section</span></span>  
 <span data-ttu-id="93b00-107">[Действие](activity.md): описывает трассировки действий в модели трассировки Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="93b00-107">[Activity](activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="93b00-108">[Перемещение](transfer.md). описывает перемещение в модели трассировки Windows Communication Foundation (WCF) и использование функции перемещения для корреляции действий в конечных точках.</span><span class="sxs-lookup"><span data-stu-id="93b00-108">[Transfer](transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="93b00-109">[Распространение](propagation.md). описывает распространение действий в модели трассировки Windows Communication Foundation (WCF) и использование распространения для корреляции действий между конечными точками.</span><span class="sxs-lookup"><span data-stu-id="93b00-109">[Propagation](propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="93b00-110">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="93b00-110">Trace Type Summary</span></span>](trace-type-summary.md)  
  
 <span data-ttu-id="93b00-111">Краткий обзор всех типов трассировок действий</span><span class="sxs-lookup"><span data-stu-id="93b00-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b00-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="93b00-112">See also</span></span>

- [<span data-ttu-id="93b00-113">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="93b00-113">Configuring Tracing</span></span>](configuring-tracing.md)
- [<span data-ttu-id="93b00-114">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="93b00-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="93b00-115">Сценарии сквозной трассировки</span><span class="sxs-lookup"><span data-stu-id="93b00-115">End-To-End Tracing Scenarios</span></span>](end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="93b00-116">Программа Service Trace Viewer (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="93b00-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../service-trace-viewer-tool-svctraceviewer-exe.md)
