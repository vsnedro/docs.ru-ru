---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: 9b8f49c498699a8f7d1c4b329e82258501aa0c47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363102"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Атрибут Extension может быть применен только к объявлениям Module, Sub или Function

Единственным способом расширения типа данных в Visual Basic является определение метода расширения внутри стандартного модуля. Метод расширения может быть `Sub` процедурой или `Function` процедурой. Все методы расширения должны быть помечены атрибутом расширения, `<Extension()>` из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен. При необходимости модуль, содержащий метод расширения, может быть помечен таким же образом. Использование атрибута расширения другим образом не допускается.

**Идентификатор ошибки:** BC36550

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите атрибут расширения.

- Перепроектирование расширения как метода, определенного во внешнем модуле.

## <a name="example"></a>Пример

В следующем примере определяется `Print` метод для `String` типа данных.

```vb
Imports StringUtility
Imports System.Runtime.CompilerServices
Namespace StringUtility
    <Extension()>
    Module StringExtensions
        <Extension()>
        Public Sub Print (ByVal str As String)
            Console.WriteLine(str)
        End Sub
    End Module
End Namespace
```

## <a name="see-also"></a>См. также раздел

- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
- [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md)
- [Оператор Module](../statements/module-statement.md)
