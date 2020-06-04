---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 52e5391fbcf30a4dada4d64a0e810c900ea85806
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409391"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Выведение типа Nullable не поддерживается в данном контексте
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
  
## <a name="see-also"></a>См. также раздел

- [Типы значений, допускающие значение null](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Вывод локального типа](../../programming-guide/language-features/variables/local-type-inference.md)
