---
title: Руководство по программированию на C#. Обработка исключений с помощью блока try-catch
description: Сведения об обработке исключений с помощью блока try-catch. Изучите пример кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: 556f4459f5d1f8b7a7419122b640c661e182a51c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178662"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Руководство по программированию на C#. Обработка исключений с помощью блока try-catch

Блок [try-catch-](../../language-reference/keywords/try-catch.md) предназначен для перехвата и обработки исключений, происходящих в исполняемом коде. Некоторые исключения могут обрабатываться в блоке `catch`, и проблема решается без повторного создания исключения. Но в большинстве случаев на этом этапе можно только проверить, что создано подходящее исключение.  
  
## <a name="example"></a>Пример  

 В этом примере <xref:System.IndexOutOfRangeException> не является наиболее подходящим исключением. Для данного метода больше подходит исключение <xref:System.ArgumentOutOfRangeException>, поскольку ошибка вызвана переданным методу аргументом `index`.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## <a name="comments"></a>Комментарии  

 Код, вызывающий исключение, находится в блоке `try`. Оператор `catch` добавляется сразу после него, чтобы обрабатывать исключение `IndexOutOfRangeException`, если оно происходит. Блок `catch` обрабатывает исключение `IndexOutOfRangeException` и вместо него вызывает более подходящее исключение `ArgumentOutOfRangeException`. Чтобы вызывающий объект получил максимально подробную информацию, рекомендуется указать исходное исключение в качестве значения <xref:System.Exception.InnerException%2A> нового исключения. Так как свойство <xref:System.Exception.InnerException%2A> доступно [только для чтения](../../properties.md#read-only), его значение необходимо присваивать только в конструкторе нового исключения.  
  
## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)
- [Исключения и обработка исключений](./index.md)
- [Обработка исключений](./exception-handling.md)
