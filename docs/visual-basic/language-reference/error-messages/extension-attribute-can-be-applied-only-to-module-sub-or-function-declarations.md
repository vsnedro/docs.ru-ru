---
description: 'Дополнительные сведения о: BC36550: атрибут "Extension" может применяться только к объявлениям "Module", "подразделировать" или "Function"'
title: Атрибут Extension может быть применен только к объявлениям Module, Sub или Function
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: f0c87de34238974229bc572a0f634a16e8cc78d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796318"
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
