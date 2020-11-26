---
title: exceptionSwallowedOnCallFromCom MDA
description: Ознакомьтесь с помощником по отладке управляемого кода Ексцептионсвалловедонкаллфромком в .NET. Этот MDA имеет место при возникновении исключения, но нет хорошего способа сообщить о нем.
ms.date: 03/30/2017
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
ms.openlocfilehash: 11daccb4d1e757bf2fae25858d706eee5921c509
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244357"
---
# <a name="exceptionswallowedoncallfromcom-mda"></a>exceptionSwallowedOnCallFromCom MDA

Помощник отладки управляемого кода (MDA) `exceptionSwallowedOnCallFromCOM` активируется при возникновении исключения из кода среды CLR, вызываемого из COM посредством метода, который не имеет неуправляемого типа возвращаемого значения HRESULT.  
  
## <a name="symptoms"></a>Симптомы  

 Вызов управляемого компонента из COM возвращает значение FALSE или 0. Кроме того, если метод имеет тип возвращаемого значения void, указание на возникновение исключения во время выполнения метода может отсутствовать. В этом случае исключение будет перехвачено без предупреждения и возвращено вызывающему объекту COM.  
  
## <a name="cause"></a>Причина:  

 Возникло исключение, однако не существует приемлемого способа сообщить об этом.  
  
## <a name="resolution"></a>Разрешение  

 Сведения приведены исключительно для справки и необязательно указывают на наличие ошибки.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR. Он только выводит данные об исключениях, перехваченных без предупреждения.  
  
## <a name="output"></a>Выходные данные  

 Информационное сообщение с именем метода, именем типа и указанием на исключение.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
