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
ms.openlocfilehash: 8e7ca6c9c43c4f507d235c879498b2e831c6eba9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272544"
---
# <a name="invalidiunknown-mda"></a>Помощник по отладке управляемого кода invalidIUnknown

Помощник по отладке управляемого кода (MDA) `invalidIUnknown` активируется, когда недопустимый указатель `IUnknown` передается в управляемый код из машинного кода. `IUnknown` не удалось возвратить успех при запросе для интерфейса `IUnknown`.  
  
## <a name="symptoms"></a>Симптомы  

 Непредвиденная ошибка при маршалинге указателя интерфейса СОМ во время маршалинга аргумента.  
  
## <a name="cause"></a>Причина:  

 Неверная реализация `QueryInterface` в интерфейсе COM, переданном в среду CLR.  
  
## <a name="resolution"></a>Разрешение  

 Исправьте реализацию `QueryInterface`.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  

 Описание ошибки.  
  
## <a name="configuration"></a>Конфигурация  
  
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
