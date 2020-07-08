---
title: Помощник по отладке управляемого кода invalidIUnknown
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидиункновн (MDA), который активируется при передаче недействительного указателя IUnknown в управляемый код из машинного кода.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid IUnknown pointer
- InvalidIUnknown MDA
- invalid IUnknown pointers
- IUnknown pointers
- managed debugging assistants (MDAs), invalid IUnknown pointer
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
ms.openlocfilehash: 65d704463ed746390ff1710b590bf080013bf53d
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051731"
---
# <a name="invalidiunknown-mda"></a>Помощник по отладке управляемого кода invalidIUnknown
Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода. `IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.  
  
## <a name="symptoms"></a>Симптомы  
 Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.  
  
## <a name="cause"></a>Причина:  
 Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.  
  
## <a name="resolution"></a>Решение  
 Исправьте реализацию `QueryInterface`.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  
 Описание ошибки.  
  
## <a name="configuration"></a>Параметр Configuration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
