---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373028"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде. Если модификатор не указан, по умолчанию используется значение ByVal.

> [!NOTE]
> Поскольку это значение по умолчанию, нет необходимости явно указывать `ByVal` ключевое слово в сигнатурах метода. Он, как правило, создает шум и часто ведет к нестандартному `ByRef` ключевому слову.

## <a name="remarks"></a>Комментарии
 Модификатор `ByVal` можно использовать в следующих контекстах:

 [Declare Statement](../statements/declare-statement.md)

 [Оператор Function](../statements/function-statement.md)
  
 [Operator Statement](../statements/operator-statement.md)
  
 [Property Statement](../statements/property-statement.md)
  
 [Оператор Sub](../statements/sub-statement.md)

## <a name="example"></a>Пример
 В следующем примере демонстрируется использование `ByVal` механизма передачи параметров с аргументом ссылочного типа. В примере аргумент — это `c1` экземпляр класса `Class1` . `ByVal`запрещает коду в процедурах изменять базовое значение ссылочного аргумента, `c1` , но не защищает доступные поля и свойства `c1` .

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>См. также раздел

- [Ключевые слова](../keywords/index.md)
- [Передача аргументов по значению и по ссылке](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
