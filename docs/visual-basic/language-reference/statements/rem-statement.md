---
title: Оператор REM
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 68c898145bd8845c657b6ebb8776a3a9027c359c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404269"
---
# <a name="rem-statement-visual-basic"></a>Оператор REM (Visual Basic)
Используется для включения пояснительных примечаний в исходный код программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Компоненты  
 `comment`  
 Необязательный элемент. Текст любого комментария, который требуется включить. Между `REM` ключевым словом и должен быть пробел `comment` .  
  
## <a name="remarks"></a>Комментарии  
 Оператор можно разместить `REM` только в строке или вставить в строку, следующую за другой инструкцией. `REM`Оператор должен быть последним оператором в строке. Если он соответствует другому оператору, он `REM` должен быть отделен от этого оператора пробелом.  
  
 Можно использовать одиночную кавычку ( `'` ) вместо `REM` . Это верно, если ваш комментарий следует другому оператору в той же строке или расподержаться только в строке.  
  
> [!NOTE]
> Нельзя продолжить выполнение `REM` инструкции с помощью последовательности продолжения строки ( `_` ). После начала комментария компилятор не проверяет символы на предмет особого значения. Для многострочного комментария используйте другую `REM` инструкцию или символ комментария ( `'` ) в каждой строке.  
  
## <a name="example"></a>Пример  
 В следующем примере показана `REM` инструкция, которая используется для включения пояснительных примечаний в программу. Он также показывает альтернативу использованию символа одинарной кавычки ( `'` ) вместо `REM` .  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [Комментарии в коде](../../programming-guide/program-structure/comments-in-code.md)
- [Практическое руководство. Разбиение и объединение инструкций в коде](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
