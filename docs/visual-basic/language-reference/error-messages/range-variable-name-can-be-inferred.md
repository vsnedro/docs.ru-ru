---
description: 'Дополнительные сведения о: BC36599: имя переменной диапазона можно вывести только из простого или полного имени без аргументов'
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: b729b6786f9b7803a794b9a4e786d94fa41a57ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792067"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>BC36599: имя переменной диапазона может быть выведено только из простого или полного имени без аргументов

В запрос LINQ входит программный элемент, который принимает один или несколько аргументов. Компилятору не удается вывести переменную диапазона из этого программного элемента.

**Идентификатор ошибки:** BC36599

## <a name="to-correct-this-error"></a>Исправление ошибки

Укажите явное имя переменной для программного элемента, как показано в следующем коде:

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение SELECT](../queries/select-clause.md)
