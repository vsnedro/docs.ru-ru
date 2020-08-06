---
title: Руководство по программированию на C#. Исключения, создаваемые компилятором
description: Сведения об исключениях, создаваемых компилятором. Просмотрите список автоматически создаваемых исключений и условия возникновения ошибок.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 1def83f72e83976ac672ec35169b4950a20ef54e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302065"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a><span data-ttu-id="408c2-104">Исключения, создаваемые компилятором (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="408c2-104">Compiler-Generated Exceptions (C# Programming Guide)</span></span>

<span data-ttu-id="408c2-105">Некоторые исключения создаются средой выполнения .NET автоматически в случае сбоя основных операций.</span><span class="sxs-lookup"><span data-stu-id="408c2-105">Some exceptions are thrown automatically by the .NET runtime when basic operations fail.</span></span> <span data-ttu-id="408c2-106">В следующей таблице перечислены эти исключения и условия возникновения ошибок.</span><span class="sxs-lookup"><span data-stu-id="408c2-106">These exceptions and their error conditions are listed in the following table.</span></span>  
  
|<span data-ttu-id="408c2-107">Исключение</span><span class="sxs-lookup"><span data-stu-id="408c2-107">Exception</span></span>|<span data-ttu-id="408c2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="408c2-108">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.ArithmeticException>|<span data-ttu-id="408c2-109">Базовый класс для исключений, которые возникают при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="408c2-109">A base class for exceptions that occur during arithmetic operations, such as <xref:System.DivideByZeroException> and <xref:System.OverflowException>.</span></span>|  
|<xref:System.ArrayTypeMismatchException>|<span data-ttu-id="408c2-110">Возникает, если массив не может сохранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.</span><span class="sxs-lookup"><span data-stu-id="408c2-110">Thrown when an array cannot store a given element because the actual type of the element is incompatible with the actual type of the array.</span></span>|  
|<xref:System.DivideByZeroException>|<span data-ttu-id="408c2-111">Возникает при попытке деления целого значения на ноль.</span><span class="sxs-lookup"><span data-stu-id="408c2-111">Thrown when an attempt is made to divide an integral value by zero.</span></span>|  
|<xref:System.IndexOutOfRangeException>|<span data-ttu-id="408c2-112">Возникает при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.</span><span class="sxs-lookup"><span data-stu-id="408c2-112">Thrown when an attempt is made to index an array when the index is less than zero or outside the bounds of the array.</span></span>|  
|<xref:System.InvalidCastException>|<span data-ttu-id="408c2-113">Возникает, если явное преобразование из базового типа в интерфейс или в производный тип завершается ошибкой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="408c2-113">Thrown when an explicit conversion from a base type to an interface or to a derived type fails at runtime.</span></span>|  
|<xref:System.NullReferenceException>|<span data-ttu-id="408c2-114">Возникает при попытке сослаться на объект, имеющий значение [null](../../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="408c2-114">Thrown when an attempt is made to reference an object whose value is [null](../../language-reference/keywords/null.md).</span></span>|  
|<xref:System.OutOfMemoryException>|<span data-ttu-id="408c2-115">Возникает, если попытка распределения памяти с помощью оператора [new](../../language-reference/operators/new-operator.md) завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="408c2-115">Thrown when an attempt to allocate memory using the [new](../../language-reference/operators/new-operator.md) operator fails.</span></span> <span data-ttu-id="408c2-116">Это означает, что ресурсы памяти, доступные для среды CLR, исчерпаны.</span><span class="sxs-lookup"><span data-stu-id="408c2-116">This indicates that the memory available to the common language runtime has been exhausted.</span></span>|  
|<xref:System.OverflowException>|<span data-ttu-id="408c2-117">Возникает при переполнении арифметической операции в контексте `checked`.</span><span class="sxs-lookup"><span data-stu-id="408c2-117">Thrown when an arithmetic operation in a `checked` context overflows.</span></span>|  
|<xref:System.StackOverflowException>|<span data-ttu-id="408c2-118">Возникает, когда чрезмерное количество ожидающих вызовов метода истощает стек выполнения; обычно это указывает на крайне глубокую или бесконечную рекурсию.</span><span class="sxs-lookup"><span data-stu-id="408c2-118">Thrown when the execution stack is exhausted by having too many pending method calls; usually indicates a very deep or infinite recursion.</span></span>|  
|<xref:System.TypeInitializationException>|<span data-ttu-id="408c2-119">Возникает, когда статический конструктор создает исключение, а совместимого предложения `catch` для его захвата нет.</span><span class="sxs-lookup"><span data-stu-id="408c2-119">Thrown when a static constructor throws an exception and no compatible `catch` clause exists to catch it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="408c2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="408c2-120">See also</span></span>

- [<span data-ttu-id="408c2-121">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="408c2-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="408c2-122">Исключения и обработка исключений</span><span class="sxs-lookup"><span data-stu-id="408c2-122">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="408c2-123">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="408c2-123">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="408c2-124">try-catch</span><span class="sxs-lookup"><span data-stu-id="408c2-124">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="408c2-125">try-finally</span><span class="sxs-lookup"><span data-stu-id="408c2-125">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="408c2-126">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="408c2-126">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
