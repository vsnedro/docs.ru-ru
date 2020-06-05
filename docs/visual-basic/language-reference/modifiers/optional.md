---
title: Необязательно
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: c46d06dba61158d7362d736731161be306af3f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392149"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)

Указывает, что аргумент процедуры может быть пропущен при вызове процедуры.

## <a name="remarks"></a>Комментарии

Для каждого необязательного параметра необходимо указать константное выражение в качестве значения по умолчанию для этого параметра. Если результат вычисления выражения равен [Nothing](../nothing.md), в качестве значения по умолчанию для параметра используется значение по умолчанию типа данных value.

Если список параметров содержит необязательный параметр, то каждый параметр, следующий за ним, также должен быть необязательным.

Модификатор `Optional` можно использовать в следующих контекстах:

- [Declare Statement](../statements/declare-statement.md)

- [Оператор Function](../statements/function-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Оператор Sub](../statements/sub-statement.md)

> [!NOTE]
> При вызове процедуры с необязательными параметрами или без них можно передавать аргументы по положению или по имени. Дополнительные сведения см. в разделе [Передача аргументов по положению и по имени](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).

> [!NOTE]
> Можно также определить процедуру с необязательными параметрами с помощью перегрузки. Если имеется один необязательный параметр, можно определить две перегруженные версии процедуры, одна из которых принимает параметр, а другая — нет. Дополнительные сведения см. в разделе [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).

## <a name="example"></a>Пример

В следующем примере определяется процедура, имеющая необязательный параметр.

```vb
Public Function FindMatches(ByRef values As List(Of String),
                            ByVal searchString As String,
                            Optional ByVal matchCase As Boolean = False) As List(Of String)

    Dim results As IEnumerable(Of String)

    If matchCase Then
        results = From v In values
                  Where v.Contains(searchString)
    Else
        results = From v In values
                  Where UCase(v).Contains(UCase(searchString))
    End If

    Return results.ToList()
End Function
```

## <a name="example"></a>Пример

В следующем примере показано, как вызвать процедуру с аргументами, передаваемыми по положению, и с аргументами, передаваемыми по имени. Процедура имеет два необязательных параметра.

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a>См. также раздел

- [Список параметров](../statements/parameter-list.md)
- [Необязательные параметры](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Ключевые слова](../keywords/index.md)
