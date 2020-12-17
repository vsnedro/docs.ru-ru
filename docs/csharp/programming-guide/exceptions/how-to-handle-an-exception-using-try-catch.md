---
title: Руководство по программированию на C#. Обработка исключений с помощью блока try-catch
description: Сведения об обработке исключений с помощью блока try-catch. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: b6368660dbe037123f5bb6ce52502d4a94fcfc3a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110524"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Руководство по программированию на C#. Обработка исключений с помощью блока try-catch

Блок [try-catch-](../../language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде. Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного вызова исключения. Но в большинстве случаев на этом этапе можно только проверить, что вызывается подходящее исключение.

## <a name="example"></a>Пример

В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, так как ошибка вызывается аргументом `index`, который передает вызывающая функция.

:::code language="csharp" source="snippets/exceptions/ExampleTryCatch.cs" id="ExampleTryCatch":::

## <a name="comments"></a>Комментарии

Код, вызывающий исключение, находится в блоке `try`. Оператор `catch` добавляется сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит. Блок `catch` обрабатывает исключение `IndexOutOfRangeException` и вместо него вызывает более подходящее исключение `ArgumentOutOfRangeException`. Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения. Так как свойство <xref:System.Exception.InnerException%2A> доступно [только для чтения](../../properties.md#read-only), его значение необходимо присваивать только в конструкторе нового исключения.
