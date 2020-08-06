---
title: Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally
description: Сведения о выполнении кода очистки с использованием оператора finally. Операторы finally гарантируют, что все необходимые очистки объектов происходят немедленно.
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 148c1f9fba67659a07c667bb15619d6f3f7c3b2f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302026"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="c815f-104">Руководство по программированию на C#. Выполнение кода очистки с использованием блока finally</span><span class="sxs-lookup"><span data-stu-id="c815f-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>
<span data-ttu-id="c815f-105">Оператор `finally` позволяет гарантировать, что необходимая очистка объектов, как правило, объектов, занимающих внешние ресурсы, возникает немедленно, даже при создании исключения.</span><span class="sxs-lookup"><span data-stu-id="c815f-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="c815f-106">Примером подобной очистки является вызов <xref:System.IO.Stream.Close%2A> для <xref:System.IO.FileStream> сразу после использования вместо ожидания сборки мусора, выполняемой для объекта средой CLR, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c815f-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="c815f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c815f-107">Example</span></span>  
 <span data-ttu-id="c815f-108">Чтобы преобразовать предыдущий код в оператор `try-catch-finally`, код очистки отделяется от рабочего кода следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c815f-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="c815f-109">Так как исключение может возникнуть в любой момент в блоке `try` до вызова `OpenWrite()`, или может произойти сбой самого вызова `OpenWrite()`, мы не можем гарантировать, что файл будет открыт при попытке закрыть его.</span><span class="sxs-lookup"><span data-stu-id="c815f-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="c815f-110">Блок `finally` добавляет проверку того, что объект <xref:System.IO.FileStream> имеет отличное от `null` значение, прежде чем будет вызван метод <xref:System.IO.Stream.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="c815f-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="c815f-111">Без проверки `null` блок `finally` может создавать собственное исключение <xref:System.NullReferenceException>, однако создания исключений в блоках `finally` следует по возможности избегать.</span><span class="sxs-lookup"><span data-stu-id="c815f-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="c815f-112">Подключение к базе данных — еще один подходящий кандидат для заключения в блок `finally`.</span><span class="sxs-lookup"><span data-stu-id="c815f-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="c815f-113">Так как количество разрешенных подключений к серверу базы данных иногда ограничено, закрывать подключения к базе данных рекомендуется как можно быстрее.</span><span class="sxs-lookup"><span data-stu-id="c815f-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="c815f-114">Если перед закрытием подключения возникает исключение, это еще один случай, когда использование блока `finally` предпочтительнее, чем ожидание сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c815f-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c815f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c815f-115">See also</span></span>

- [<span data-ttu-id="c815f-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c815f-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c815f-117">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="c815f-117">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="c815f-118">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="c815f-118">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="c815f-119">Оператор using</span><span class="sxs-lookup"><span data-stu-id="c815f-119">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="c815f-120">try-catch</span><span class="sxs-lookup"><span data-stu-id="c815f-120">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="c815f-121">try-finally</span><span class="sxs-lookup"><span data-stu-id="c815f-121">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="c815f-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="c815f-122">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
