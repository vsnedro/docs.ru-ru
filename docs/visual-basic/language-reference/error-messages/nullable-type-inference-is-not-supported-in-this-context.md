---
description: 'Дополнительные сведения о: BC36629: определение типа, допускающего значение null, не поддерживается в этом контексте'
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 915f964d55068f39b0468e2c47cc6e5538be1a6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795629"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a>BC36629: определение типа, допускающего значение null, не поддерживается в этом контексте

Типы значений и структуры могут быть объявлены как допускающие значение null.

```vb
Dim a? As Integer
Dim b As Integer?
```

 Однако нельзя использовать объявление Nullable в сочетании с выводом типа. Следующие примеры вызывают эту ошибку.

```vb
' Not valid.
' Dim c? = 10
' Dim d? = a
```

 **Идентификатор ошибки:** BC36629

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте `As` предложение, чтобы объявить переменную как тип значения, допускающего значение null.

## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
