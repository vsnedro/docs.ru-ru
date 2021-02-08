---
description: 'Дополнительные сведения: директивы #Disable и #Enable (Visual Basic)'
title: Включение и отключение директив
ms.date: 01/28/2021
helpviewer_keywords:
- directives, enable
- directives, disable
- disable directive
ms.openlocfilehash: d600cc959639a3f70bca5678fbc81aae0806c9cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797267"
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
