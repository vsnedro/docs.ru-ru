---
description: 'Дополнительные сведения: числовые и операторы сравнения'
title: Числовые операторы и операторы сравнения
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 5b17f19769436ac4e575ac974668eadc3b17b8f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695532"
---
# <a name="numeric-and-comparison-operators"></a>Числовые операторы и операторы сравнения

Арифметические операторы и операторы сравнения работают в среде (CLR) соответствующим образом, за исключением следующих моментов.

- SQL не поддерживает оператор modulus для чисел с плавающей запятой.

- SQL не поддерживает непроверяемые арифметические операции.

- Операторы инкремента или декремента вызывают побочные эффекты, если используются в выражениях, которые не могут быть реплицированы в SQL и поэтому не поддерживаются.

## <a name="supported-operators"></a>Поддерживаемые операторы

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает следующие операторы.

- Основные арифметические операторы

  - `+`

  - `-` (вычитание)

  - `*`

  - `/`

  - Оператор целочисленного деления Visual Basic (`\`)

  - `%` (Visual Basic `Mod`)

  - `<<`

  - `>>`

  - `-` (унарное отрицание)

- Основные операторы сравнения

  - Visual Basic `=` и C# `==`

  - Visual Basic `<>` и C# `!=`

  - Visual Basic `Is/IsNot`

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>См. также

- [Типы данных и функции](data-types-and-functions.md)
- [Операторы в C#](../../../../../csharp/language-reference/operators/index.md)
- [Операторы](../../../../../visual-basic/language-reference/operators/index.md)
