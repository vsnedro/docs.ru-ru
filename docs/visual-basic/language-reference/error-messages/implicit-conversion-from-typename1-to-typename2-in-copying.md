---
title: Неявное приведение <typename1> к <typename2> при копировании значения параметра <parametername>, объявленного как ByRef, обратно в соответствующий аргумент.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: fced95fe24d42d4af2118706bcaf3337429fea91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873996"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a>Неявное приведение \<typename1> к \<typename2> при копировании значения параметра \<parametername>, объявленного как ByRef, обратно в соответствующий аргумент.

Процедура вызывается с аргументом [ByRef](../modifiers/byref.md) , отличным от типа соответствующего параметра.  
  
 При передаче аргумента `ByRef` Visual Basic иногда копирует значение аргумента в локальную переменную в процедуре вместо передачи ссылки. В этом случае, когда процедура возвращает, Visual Basic необходимо скопировать значение локальной переменной обратно в аргумент в вызывающем коде.  
  
 Если значение аргумента `ByRef` копируется в процедуру, а аргумент и параметр имеют один и тот же тип, то преобразование не требуется. Но если типы различаются, Visual Basic должны быть преобразованы в обоих направлениях. Поскольку нельзя использовать `CType` или любые другие ключевые слова преобразования в аргументе или параметре процедуры, такое преобразование всегда является неявным.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC41999  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- По возможности используйте аргумент вызова того же типа, что и параметр процедуры, поэтому Visual Basic не требуется выполнять преобразование.  
  
- Если необходимо вызвать процедуру с аргументом, тип которого отличается от типа параметра, но не требуется возвращать значение в аргумент вызова, то определите параметр как [ByVal](../modifiers/byval.md) , а не `ByRef`.  
  
## <a name="see-also"></a>См. также

- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Параметры и аргументы процедуры](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Передача аргументов по значению и по ссылке](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Явные и неявные преобразования](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
