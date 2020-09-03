---
description: '#error. Справочник по C#'
title: '#error. Справочник по C#'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138102"
---
# <a name="error-c-reference"></a>#error (справочник по C#)

`#error` позволяет создать определяемую пользователем ошибку [CS1029](../compiler-messages/cs1029.md) из определенного места в коде. Пример:

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> Компилятор обрабатывает `#error version` особым образом и сообщает об ошибке компилятора CS8304 с сообщением, содержащим используемые версии компилятора и языка.

## <a name="remarks"></a>Remarks

Как правило, `#error` применяется в условной директиве.

Кроме того, с помощью директивы [#warning](./preprocessor-warning.md) можно создать определяемое пользователем предупреждение.

## <a name="example"></a>Пример

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
