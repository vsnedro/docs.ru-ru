---
title: Практическое руководство. Создание пользовательских исключений
description: Узнайте, как создавать пользовательские исключения, которые являются альтернативой иерархии классов исключений, производных от базового класса Exception в .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
ms.openlocfilehash: b0a8549c9bacf322a0685c7b505185ab1d1101f6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828131"
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="f63b9-103">Создание пользовательских исключений</span><span class="sxs-lookup"><span data-stu-id="f63b9-103">How to create user-defined exceptions</span></span>

<span data-ttu-id="f63b9-104">Платформа .NET предоставляет иерархию классов исключений, производных от базового класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="f63b9-104">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="f63b9-105">Тем не менее, если ни одно из стандартных исключений не подходит, можно создать собственные классы исключений путем наследования от класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="f63b9-105">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="f63b9-106">При создании собственных исключений заканчивайте имя класса пользовательского исключения словом Exception и реализуйте три общих конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f63b9-106">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception", and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="f63b9-107">В примере определяется новый класс исключений `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="f63b9-107">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="f63b9-108">Этот класс является производным от <xref:System.Exception> и включает три конструктора.</span><span class="sxs-lookup"><span data-stu-id="f63b9-108">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="f63b9-109">В ситуациях, когда используется удаленное взаимодействие, необходимо убедиться, что метаданные для пользовательского исключения доступны на сервере (вызываемый объект) и для клиента (прокси-объект или вызывающий объект).</span><span class="sxs-lookup"><span data-stu-id="f63b9-109">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="f63b9-110">Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="f63b9-110">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f63b9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f63b9-111">See also</span></span>

- [<span data-ttu-id="f63b9-112">Исключения</span><span class="sxs-lookup"><span data-stu-id="f63b9-112">Exceptions</span></span>](index.md)
