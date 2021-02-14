---
description: 'Дополнительные сведения: "ReDim" не может изменить число измерений'
title: ReDim не может изменять размерность
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 4552dd6b1cce54813b57e5b8c76a3580b81b8def
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454642"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a>ReDim не может изменять размерность

Предпринята попытка использования оператора `ReDim` для изменения ранга (размерности) массива. Оператор`ReDim` может изменять размер одного или нескольких измерений массива, который уже был формально объявлен, но он не может изменить ранг массива.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Убедитесь, что требуется изменить ранг, а не размеры массива, и по возможности используйте `Dim` для объявления нового массива с нужным рангом.  
  
## <a name="see-also"></a>См. также раздел

- [Массивы в Visual Basic](../programming-guide/language-features/arrays/index.md)
- [Размеры массива в Visual Basic](../programming-guide/language-features/arrays/array-dimensions.md)
- [Оператор reDim](../language-reference/statements/redim-statement.md)
- [Оператор Dim](../language-reference/statements/dim-statement.md)
