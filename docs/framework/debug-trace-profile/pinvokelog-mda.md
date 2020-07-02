---
title: Помощник по отладке управляемого кода pInvokeLog
description: Изучите помощник по отладке управляемого кода Пинвокелог (MDA), который активируется для каждой уникальной сигнатуры вызова платформы, используемой во время выполнения в .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: 05af4e17a91f7c0d8f3576a86d3d784ef6666aed
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803694"
---
# <a name="pinvokelog-mda"></a>Помощник по отладке управляемого кода pInvokeLog
Помощник по отладке управляемого кода `pInvokeLog` активируется для каждой уникальной сигнатуры вызова неуправляемого кода во время выполнения.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 Сообщение, указывающее на сигнатуру вызова неуправляемого кода во время выполнения.  
  
## <a name="configuration"></a>Параметр Configuration  
 Каждый совпадающий элемент фильтрует DLL-файлы, к которым выполняются вызовы неуправляемого кода.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Использование неуправляемых функций DLL](../interop/consuming-unmanaged-dll-functions.md)
