---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6b155de0bb62f667ca76ec9454dec1466976a9b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400413"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов

В запрос LINQ входит программный элемент, который принимает один или несколько аргументов. Компилятору не удается вывести переменную диапазона из этого программного элемента.

**Идентификатор ошибки:** BC36599

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите явное имя переменной для программного элемента, как показано в следующем коде:

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение SELECT](../queries/select-clause.md)
