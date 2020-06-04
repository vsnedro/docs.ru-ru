---
title: "\"ReDim\" может изменять только крайнее правое измерение"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 8e42e0df7b97fb96f468ce37dd4cfc52fad8c596
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358300"
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
