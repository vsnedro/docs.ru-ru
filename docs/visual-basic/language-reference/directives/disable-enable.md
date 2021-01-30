---
title: Включение и отключение директив
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: 3104b25c903465f3a650304f477b25a74591c8ba
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217242"
---
# <a name="disable-and-enable-directives-visual-basic"></a>Директивы #Disable и #Enable (Visual Basic)

`#Disable` `#Enable` Директивы и являются Visual Basic директивами компилятора исходного кода. Они используются для отключения и повторного включения конкретных предупреждений для регионов кода.

```vb
' Suppress warning about no awaits in this method.
#Disable Warning BC42356
    Async Function TestAsync() As Task
        Console.WriteLine("testing")
    End Function
#Enable Warning BC42356
```

Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.

## <a name="see-also"></a>См. также

- [Справочник по языку Visual Basic](../index.md)
- [Отключение предупреждений анализа кода](../../../fundamentals/code-analysis/suppress-warnings.md)
