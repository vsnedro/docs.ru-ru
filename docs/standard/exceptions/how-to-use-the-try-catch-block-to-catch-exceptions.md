---
title: Практическое руководство. использование блока try/catch для перехвата исключений
description: Включайте в блок try операторы, которые могут создавать исключение. Помещайте операторы для обработки исключений в один блок catch или несколько.
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 60ed213ea777fe35873fd1e67555b7506e3ca587
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768915"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a>Использование блока try/catch для перехвата исключений

Поместите все операторы кода, которые могут вызвать исключение, в блок `try`, а операторы, которые обрабатывают исключения, поместите в одном или нескольких блоках `catch` под блоком `try`. Каждый блок `catch` включает тип исключения и может содержать дополнительные инструкции, необходимые для обработки этого типа исключения.

В следующем примере <xref:System.IO.StreamReader> открывает файл с именем *data.txt* и извлекает строку из файла. Так как код может вызывать любое из трех исключений, он помещается в блок `try`. Три блока `catch` перехватывают исключения и обрабатывают их, отображая результаты в консоли.

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

Среда CLR перехватывает исключения, не обрабатываемые блоками `catch`. Если исключение перехватывается в среде CLR, в зависимости от конфигурации среды CLR может возникнуть один из следующих результатов:

- Откроется диалоговое окно **отладки**.
- Программа прекратит выполнение, и откроется диалоговое окно со сведениями об исключении.
- В [стандартном потоке вывода ошибок](xref:System.Console.Error) будет выведена ошибка.

> [!NOTE]
> Большая часть кода может создавать исключения, и некоторые исключения, например <xref:System.OutOfMemoryException>, могут вызываться самой средой CLR в любое время. Приложениям не требуется обрабатывать эти исключения, но вы должны помнить об этом при написании библиотек, предназначенных для других пользователей. Рекомендации о том, когда следует помещать код в блок `try`, см. в разделе [о лучших методиках обработки исключений](best-practices-for-exceptions.md).

## <a name="see-also"></a>См. также

- [Исключения](index.md)
- [Обработка ошибок ввода-вывода в .NET](../io/handling-io-errors.md)
