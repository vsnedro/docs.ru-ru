---
title: Помощник по отладке управляемого кода dllMainReturnsFalse
description: Ознакомьтесь с помощником по отладке управляемого кода Дллмаинретурнсфалсе в .NET. Этот MDA активируется при сбое инициализации DLL.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), DllMain returns false
- DllMainReturnsFalse MDA
- DllMain function
- MDAs (managed debugging assistants), DllMain returns false
ms.assetid: e2abdd04-f571-4b97-8c16-2221b8588429
ms.openlocfilehash: 83f38c4918c1354477627b70a62e60cbdc7de275
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273520"
---
# <a name="dllmainreturnsfalse-mda"></a>Помощник по отладке управляемого кода dllMainReturnsFalse

Помощник по отладке управляемого кода `dllMainReturnsFalse` (MDA) активируется в том случае, если управляемая функция `DllMain` в пользовательской сборке вызывается с причиной DLL_PROCESS_ATTACH и возвращает значение FALSE.  
  
## <a name="symptoms"></a>Симптомы  

 Функция `DllMain` возвращает значение FALSE, свидетельствующее о сбое при ее выполнении. Это может привести к возникновению неопределенных проблем, поскольку функции `DllMain` обычно содержат важный код инициализации.  
  
## <a name="cause"></a>Причина:  

 Функция `DllMain` вызывается с причиной DLL_PROCESS_ATTACH для инициализации библиотеки DLL при загрузке. Если она возвращает значение FALSE, значит инициализация библиотеки DLL завершилась сбоем.  
  
## <a name="resolution"></a>Разрешение  

 Проанализируйте код функции `DllMain` для указанной библиотеки DLL и определите причину сбоя при инициализации.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR. Он только выводит данные о возвращаемом значении для `DllMain`.  
  
## <a name="output"></a>Выходные данные  

 Сообщение, указывающее, что функция `DllMain` была вызвана с причиной DLL_PROCESS_ATTACH и вернула значение FALSE. Обратите внимание, что этот помощник по отладке кода вызывается только в том случае, если в управляемом коде реализована функция `DllMain`.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dllMainReturnsFalse />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
