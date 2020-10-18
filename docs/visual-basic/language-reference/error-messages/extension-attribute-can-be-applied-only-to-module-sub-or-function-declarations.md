---
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: bd4d14721b93800831dbce897535b4f5956fe9c7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160754"
---
# <a name="bc36550-extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>BC36550: атрибут "Extension" может применяться только к объявлениям "Module", "подразделировать" или "Function"

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

## <a name="see-also"></a>См. также

- [Обзор атрибутов](../../programming-guide/concepts/attributes/index.md)
- [Методы расширения](../../programming-guide/language-features/procedures/extension-methods.md)
- [Оператор Module](../statements/module-statement.md)
