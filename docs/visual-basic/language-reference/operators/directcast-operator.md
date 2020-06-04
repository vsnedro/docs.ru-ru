---
title: Оператор DirectCast
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 96cb2082d59373deb34d6894270205b7c1045850
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371522"
---
# <a name="directcast-operator-visual-basic"></a>Оператор DirectCast (Visual Basic)
Вводит операцию преобразования типов на основе наследования или реализации.  
  
## <a name="remarks"></a>Комментарии  
 `DirectCast`не использует подпрограммы вспомогательной среды выполнения Visual Basic для преобразования, поэтому она может обеспечить более высокую производительность, чем `CType` при преобразовании в тип данных и из него `Object` .  
  
 Используйте `DirectCast` ключевое слово, аналогичное тому, как используется [Функция CType](../functions/ctype-function.md) и ключевое слово [оператора TryCast](trycast-operator.md) . Укажите выражение в качестве первого аргумента и тип, чтобы преобразовать его в качестве второго аргумента. `DirectCast`требует отношения наследования или реализации между типами данных двух аргументов. Это означает, что один тип должен наследовать или реализовывать другой.  
  
## <a name="errors-and-failures"></a>Ошибки и сбои  
 `DirectCast`выдает ошибку компилятора, если обнаруживается, что связь наследования или реализации не существует. Но отсутствие ошибки компилятора не гарантирует успешного преобразования. Если требуемое преобразование является узким, оно может привести к сбою во время выполнения. Если это происходит, среда выполнения выдает <xref:System.InvalidCastException> ошибку.  
  
## <a name="conversion-keywords"></a>Ключевые слова преобразований  
 Ниже приведены сравнения ключевых слов преобразования типов.  
  
|Ключевое слово|Типы данных|Отношение аргумента|Сбой во время выполнения|  
|---|---|---|---|  
|[CType Function](../functions/ctype-function.md)|Любые типы данных|Для двух типов данных должно быть определено расширяющее или суженное преобразование.|Создает<xref:System.InvalidCastException>|  
|`DirectCast`|Любые типы данных|Один тип должен наследовать или реализовывать другой тип|Создает<xref:System.InvalidCastException>|  
|[Оператор TryCast](trycast-operator.md)|Только ссылочные типы|Один тип должен наследовать или реализовывать другой тип|[Ничего не](../nothing.md) возвращает|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируются два применения `DirectCast` , один из которых завершается сбоем во время выполнения и один успешно.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 В предыдущем примере типом времени выполнения `q` является `Double` . `CType`выполнено, так как `Double` может быть преобразовано в `Integer` . Однако первый `DirectCast` сбой во время выполнения, так как тип времени выполнения `Double` не имеет отношения наследования с `Integer` , даже если существует преобразование. Вторая `DirectCast` успешна, так как она преобразует тип <xref:System.Windows.Forms.Form> в тип <xref:System.Windows.Forms.Control> , от которого <xref:System.Windows.Forms.Form> наследует.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Явные и неявные преобразования](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
