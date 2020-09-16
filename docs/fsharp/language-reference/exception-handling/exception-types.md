---
title: Типы исключения
description: 'Узнайте, как определять и использовать типы исключений F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557233"
---
# <a name="exception-types"></a>Типы исключения

В F # существуют две категории исключений: типы исключений .NET и типы исключений F #. В этом разделе описывается определение и использование типов исключений F #.

## <a name="syntax"></a>Синтаксис

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Примечания

В предыдущем синтаксисе *Exception-Type* — это имя нового типа исключения F #, а *тип Argument —* тип аргумента, который может быть указан при вызове исключения этого типа. Можно указать несколько аргументов с помощью типа кортежа для *типа аргумента*.

Типичное определение исключения F # напоминает следующее.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Исключение этого типа можно создать с помощью `raise` функции, как показано ниже.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Тип исключения F # можно использовать непосредственно в фильтрах в `try...with` выражении, как показано в следующем примере.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Тип исключения, определяемый с помощью `exception` ключевого слова в F #, является новым типом, наследуемым от `System.Exception` .

## <a name="see-also"></a>См. также

- [Обработка исключений](index.md)
- [Исключения: функция `raise`](the-raise-function.md)
- [Иерархия исключений](../../../standard/exceptions/index.md)
