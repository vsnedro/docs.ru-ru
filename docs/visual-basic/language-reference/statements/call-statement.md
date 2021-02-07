---
description: 'Дополнительные сведения о вызываемом операторе: Call (Visual Basic)'
title: Оператор Call
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 70e6c109621c3710ad9476a952e9c384a142ba3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674016"
---
# <a name="call-statement-visual-basic"></a>Оператор Call (Visual Basic)

Передает управление в `Function` процедуру, `Sub` или в библиотеку динамической КОМПОНОВКИ (DLL).  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Компоненты  

|||
|---|---|
|`procedureName`|Обязательный элемент. Имя вызываемой процедуры.|
|`argumentList`|Необязательный элемент. Список переменных или выражений, представляющих аргументы, которые передаются в процедуру при ее вызове. Несколько аргументов разделяются запятыми. Если включить `argumentList` , необходимо заключить его в круглые скобки.|
|||
  
## <a name="remarks"></a>Remarks

 `Call`При вызове процедуры можно использовать ключевое слово. Для большинства вызовов процедур использовать это ключевое слово не обязательно.

 Обычно используется `Call` ключевое слово, если вызванное выражение не начинается с идентификатора. Использование `Call` ключевого слова для других целей не рекомендуется.

 Если процедура возвращает значение, `Call` инструкция отклоняет ее.

## <a name="example"></a>Пример

 В следующем коде показаны два примера, где `Call` ключевое слово требуется для вызова процедуры. В обоих примерах вызванное выражение не начинается с идентификатора.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>См. также

- [Оператор Function](function-statement.md)
- [Оператор Sub](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Лямбда-выражения](../../programming-guide/language-features/procedures/lambda-expressions.md)
