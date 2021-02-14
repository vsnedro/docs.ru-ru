---
description: 'Дополнительные сведения: ReDim может изменять только крайнее правое измерение'
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 6816e5b2e9c7c079b78ce53e168f46b337831512
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454694"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a>"ReDim" может изменять только крайнее правое измерение

В операторе `ReDim` ключевое слово `Preserve` используется для изменения измерения массива, которое не является его последним измерением. При использовании `Preserve`можно изменять размер только последнего измерения массива. Для всех других измерений необходимо указать тот же размер, что и для существующего массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите ключевое слово `Preserve` .  
  
## <a name="see-also"></a>См. также раздел

- [Массивы в Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Размеры массива в Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Оператор reDim](../language-reference/statements/redim-statement.md)
- [Оператор Dim](../language-reference/statements/dim-statement.md)
