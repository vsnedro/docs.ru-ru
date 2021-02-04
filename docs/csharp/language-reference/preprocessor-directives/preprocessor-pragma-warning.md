---
description: '#Справочник по C#. #pragma warning'
title: '#Справочник по C#. #pragma warning'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 16582a74bd34f2c0d89950280f1d5fde25435eea
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2021
ms.locfileid: "99215996"
---
# <a name="pragma-warning-c-reference"></a>#pragma warning (Справочник по C#)

`#pragma warning` может включать или отключать определенные предупреждения.

## <a name="syntax"></a>Синтаксис

```csharp
#pragma warning disable warning-list
#pragma warning restore warning-list
```

## <a name="parameters"></a>Параметры

 `warning-list` Список номеров предупреждений с разделителем-запятой. Префикс CS является необязательным.

 Если номера предупреждений не указаны, `disable` отключает все предупреждения, а `restore` включает все предупреждения.

> [!NOTE]
> Чтобы найти номера предупреждений в Visual Studio, выполните сборку проекта, а затем поиск номеров предупреждений в окне **Вывод**.

## <a name="example"></a>Пример

```csharp
// pragma_warning.cs
using System;

#pragma warning disable 414, CS3021
[CLSCompliant(false)]
public class C
{
    int i = 1;
    static void Main()
    {
    }
}
#pragma warning restore CS3021
[CLSCompliant(false)]  // CS3021
public class D
{
    int i = 1;
    public static void F()
    {
    }
}
```

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
- [Ошибки компилятора C#](../compiler-messages/index.md)
- [Отключение предупреждений анализа кода](../../../fundamentals/code-analysis/suppress-warnings.md)
