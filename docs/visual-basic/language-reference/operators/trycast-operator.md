---
title: Оператор TryCast
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: 8f0d4f612cd5a96e0b0ab7305c41e00790613cc8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406395"
---
# <a name="trycast-operator-visual-basic"></a>Оператор TryCast (Visual Basic)
Вводит операцию преобразования типа, которая не создает исключение.  
  
## <a name="remarks"></a>Комментарии  
 Если попытка преобразования завершается неудачно `CType` и возникает `DirectCast` <xref:System.InvalidCastException> ошибка. Это может негативно сказаться на производительности приложения. `TryCast`[не возвращает ничего](../nothing.md), поэтому вместо того, чтобы выполнять обработку возможного исключения, необходимо только проверить возвращаемый результат для `Nothing` .  
  
 `TryCast`Ключевое слово используется точно так же, как при использовании [функции CType](../functions/ctype-function.md) и ключевого слова [DirectCast operator](directcast-operator.md) . Укажите выражение в качестве первого аргумента и тип, чтобы преобразовать его в качестве второго аргумента. `TryCast`работает только со ссылочными типами, такими как классы и интерфейсы. Для этого требуется отношение наследования или реализации между двумя типами. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `TryCast`выдает ошибку компилятора, если обнаруживается, что связь наследования или реализации не существует. Но отсутствие ошибки компилятора не гарантирует успешного преобразования. Если требуемое преобразование является узким, оно может привести к сбою во время выполнения. Если это происходит, `TryCast` возвращает [Nothing](../nothing.md).  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Ниже приведены сравнения ключевых слов преобразования типов.  
  
|Ключевое слово|Типы данных|Отношение аргумента|Сбой во время выполнения|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Любые типы данных|Для двух типов данных должно быть определено расширяющее или суженное преобразование.|Создает<xref:System.InvalidCastException>|  
|[Оператор DirectCast](directcast-operator.md)|Любые типы данных|Один тип должен наследовать или реализовывать другой тип|Создает<xref:System.InvalidCastException>|  
|`TryCast`|Только ссылочные типы|Один тип должен наследовать или реализовывать другой тип|[Ничего не](../nothing.md) возвращает|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `TryCast`.  
  
 [!code-vb[VbVbalrKeywords#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>См. также раздел

- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
