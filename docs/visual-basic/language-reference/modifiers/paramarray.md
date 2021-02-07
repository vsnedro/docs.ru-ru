---
description: 'Дополнительные сведения о: ParamArray (Visual Basic)'
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 064bad8a558308ee3361c11d07020e0e3bf40c13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730399"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)

Указывает, что параметр процедуры принимает необязательный массив элементов указанного типа. `ParamArray` может использоваться только в последнем параметре списка параметров.  
  
## <a name="remarks"></a>Remarks  

 `ParamArray` позволяет передавать процедуре произвольное число аргументов. `ParamArray`Параметр всегда объявляется с помощью [ByVal](byval.md).  
  
 Можно указать один или несколько аргументов для параметра, `ParamArray` передав массив соответствующего типа данных, список значений с разделителями-запятыми или ничего вообще. Дополнительные сведения см. в разделе «вызов ParamArray» в [массивах параметров](../../programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Всякий раз при работе с массивом, который может быть неограниченным большим, существует риск перегрузки внутренней емкости приложения. Если вы принимаете массив параметров из вызывающего кода, следует проверить его длину и предпринять соответствующие шаги, если оно слишком велико для вашего приложения.  
  
 Модификатор `ParamArray` можно использовать в следующих контекстах:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Оператор Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Оператор Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Ключевые слова](../keywords/index.md)
- [Массивы параметров](../../programming-guide/language-features/procedures/parameter-arrays.md)
