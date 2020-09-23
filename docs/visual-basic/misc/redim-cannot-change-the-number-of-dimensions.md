---
title: ReDim не может изменять размерность
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077375"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim не может изменять размерность

Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива. Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## <a name="see-also"></a>См. также

- [Массивы в Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Размеры массива в Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Оператор reDim](../language-reference/statements/redim-statement.md)
- [Оператор Dim](../language-reference/statements/dim-statement.md)
