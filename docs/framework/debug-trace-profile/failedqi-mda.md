---
title: Помощник по отладке управляемого кода failedQI
description: Ознакомьтесь с помощником по отладке управляемого кода (MDA) Фаиледки в .NET, который может быть активирован при сбое приведения или вызове COM из вызываемой оболочки времени выполнения (RCW).
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: 2d7f14c67d47e58bcb88eab4621df63d7c598a7a
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415944"
---
# <a name="failedqi-mda"></a>Помощник по отладке управляемого кода failedQI
Помощник по отладке управляемого кода (MDA) `failedQI` активируется, когда среда выполнения вызывает `QueryInterface`в указателе интерфейса СОМ от имени вызываемой оболочки времени выполнения (RCW), и вызов `QueryInterface` завершается с ошибкой.  
  
## <a name="symptoms"></a>Симптомы  
 Произошел сбой приведения в RCW, или вызов COM из RCW неожиданно завершается ошибкой.  
  
## <a name="cause"></a>Причина  
  
- Вызов выполняется из неправильного контекста.  
  
- Зарегистрированному прокси-серверу не удается выполнить вызов `QueryInterface`, поскольку вызов выполнялся из неправильного контекста.  
  
- Прокси-сервер, принадлежащий OLE, возвратил значение HRESULT, указывающее на сбой.  
  
## <a name="resolution"></a>Решение  
 Правила COM см. в документации MSDN.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Если вызов `QueryInterface` завершается с ошибкой, контекст переключается и предпринимается попытка повторно выполнить вызов `QueryInterface`, чтобы увидеть, не использовался ли при сбое неправильный контекст.  
  
## <a name="output"></a>Вывод  
 Управляемое имя интерфейса, идентификатор GUID интерфейса и значение HRESULT ошибки.  
  
## <a name="configuration"></a>Параметр Configuration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
