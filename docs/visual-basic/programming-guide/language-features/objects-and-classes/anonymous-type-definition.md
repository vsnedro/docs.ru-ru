---
description: 'Дополнительные сведения: Определение анонимного типа (Visual Basic)'
title: Определение анонимного типа
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [Visual Basic], type definition
ms.assetid: 7a8a0ddc-55ba-4d67-869e-87a84d938bac
ms.openlocfilehash: 2e3f847f5f844e3ed6e036c26efc330a237d193f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436920"
---
# <a name="anonymous-type-definition-visual-basic"></a>Определение анонимного типа (Visual Basic)

В ответ на объявление экземпляра анонимного типа компилятор создает новое определение класса, которое содержит указанные свойства для типа.

## <a name="compiler-generated-code"></a>Код Compiler-Generated

Для следующего определения `product` компилятор создает новое определение класса, которое содержит свойства `Name` , `Price` и `OnHand` .

[!code-vb[VbVbalrAnonymousTypes#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#25)]

Определение класса содержит определения свойств, аналогичные приведенным ниже. Обратите внимание, что `Set` для ключевых свойств отсутствует метод. Значения ключевых свойств доступны только для чтения.

```vb
Public Class $Anonymous1
    Private _name As String
    Private _price As Double
    Private _onHand As Integer
     Public ReadOnly Property Name() As String
        Get
            Return _name
        End Get
    End Property

    Public ReadOnly Property Price() As Double
        Get
            Return _price
        End Get
    End Property

    Public Property OnHand() As Integer
        Get
            Return _onHand
        End Get
        Set(ByVal Value As Integer)
            _onHand = Value
        End Set
    End Property

End Class
```

Кроме того, анонимные определения типов содержат конструктор без параметров. Конструкторы, требующие параметров, не разрешены.

Если объявление анонимного типа содержит по крайней мере одно ключевое свойство, определение типа переопределяет три члена, наследуемые от <xref:System.Object> : <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> и <xref:System.Object.ToString%2A> . Если ключевые свойства не объявлены, <xref:System.Object.ToString%2A> то переопределяется только. Переопределения предоставляют следующие функциональные возможности:

- `Equals` Возвращает `True` значение, если два экземпляра анонимных типов являются одним и тем же экземпляром, или если они отвечают следующим условиям:

  - Они имеют одинаковое число свойств.

  - Свойства объявляются в том же порядке с одинаковыми именами и теми же выводимыми типами. При сравнении имен регистр не учитывается.

  - По крайней мере одно из свойств является ключевым свойством, а `Key` ключевое слово применяется к тем же свойствам.

  - Сравнение каждой соответствующей пары ключевых свойств возвращает `True` .

    Например, в следующих примерах функция `Equals` возвращает `True` только для `employee01` и `employee08` . Комментарий перед каждой строкой указывает причину, по которой новый экземпляр не соответствует `employee01` .

    [!code-vb[VbVbalrAnonymousTypes#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#24)]

- `GetHashcode` предоставляет соответствующим образом уникальный алгоритм GetHashCode. Алгоритм использует только ключевые свойства для вычисления хэш-кода.

- `ToString` Возвращает строку сцепленных значений свойств, как показано в следующем примере. Включены ключевые и неключевые свойства.

  [!code-vb[VbVbalrAnonymousTypes#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#29)]

Явно именованные свойства анонимного типа не могут конфликтовать с этими созданными методами. То есть нельзя использовать `.Equals` , `.GetHashCode` или `.ToString` для именования свойства.

Определения анонимных типов, включающие по крайней мере одно ключевое свойство, также реализуют <xref:System.IEquatable%601?displayProperty=nameWithType> интерфейс, где `T` — это тип анонимного типа.

> [!NOTE]
> Объявления анонимного типа создают один и тот же анонимный тип только в том случае, если они встречаются в одной сборке, их свойства имеют одинаковые имена и те же выводимые типы, свойства объявляются в том же порядке, а те же свойства помечаются как ключевые свойства.

## <a name="see-also"></a>См. также раздел

- [Анонимные типы](anonymous-types.md)
- [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
