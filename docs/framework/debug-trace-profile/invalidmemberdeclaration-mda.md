---
title: Помощник по отладке управляемого кода invalidMemberDeclaration
description: Ознакомьтесь с помощником по отладке управляемого кода Инвалидмембердекларатион, который вызывается, если ошибка HRESULT возвращается в COM без вызова управляемого метода.
ms.date: 03/30/2017
helpviewer_keywords:
- invalid member declaration
- InvalidMemberDeclaration MDA
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: a84dd9a3-d6cf-4824-989a-ecbbf443eeb4
ms.openlocfilehash: c8d6c69fc6eb4f5f690b02809fdc492da675c3b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272557"
---
# <a name="invalidmemberdeclaration-mda"></a>Помощник по отладке управляемого кода invalidMemberDeclaration

Помощник по отладке (MDA) управляемого кода `invalidMemberDeclaration` активируется для сообщения об ошибке, которая возникает при определении способа маршалинга параметров члена, вызываемого из COM.  
  
## <a name="symptoms"></a>Симптомы  

 Значение HRESULT, свидетельствующее об ошибке, возвращается в COM без вызова управляемого метода.  
  
## <a name="cause"></a>Причина:  

 Наиболее вероятная причина — несовместимый атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> в одном из параметров.  
  
## <a name="resolution"></a>Разрешение  

 Укажите допустимые атрибуты <xref:System.Runtime.InteropServices.MarshalAsAttribute> в параметрах.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  

 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Выходные данные  

 Информационное сообщение с именем члена, именем типа и сообщением об ошибке.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidMemberDeclaration/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством управляемых помощников по отладке](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
