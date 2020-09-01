---
description: Справочник по C#. Оператор throw
title: Справочник по C#. Оператор throw
ms.date: 03/02/2015
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
ms.openlocfilehash: 4cad4810b89f976f92ce576917feb2398acce636
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142041"
---
# <a name="throw-c-reference"></a><span data-ttu-id="816ed-103">throw (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="816ed-103">throw (C# Reference)</span></span>

<span data-ttu-id="816ed-104">Сообщает о возникновении исключения во время выполнения программы.</span><span class="sxs-lookup"><span data-stu-id="816ed-104">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="816ed-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="816ed-105">Remarks</span></span>

<span data-ttu-id="816ed-106">Синтаксис `throw` выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="816ed-106">The syntax of `throw` is:</span></span>

```csharp
throw [e];
```

<span data-ttu-id="816ed-107">где `e` — это экземпляр класса, производного от <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="816ed-107">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="816ed-108">В следующем примере используется оператор `throw` для создания <xref:System.IndexOutOfRangeException>, если аргумент, переданный в метод с именем `GetNumber`, не соответствует допустимому индексу внутреннего массива.</span><span class="sxs-lookup"><span data-stu-id="816ed-108">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]

<span data-ttu-id="816ed-109">Затем вызывающие объекты метода используют блок `try-catch` или `try-catch-finally` для обработки исключения.</span><span class="sxs-lookup"><span data-stu-id="816ed-109">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="816ed-110">В следующем примере показана обработка исключения, созданного методом `GetNumber`.</span><span class="sxs-lookup"><span data-stu-id="816ed-110">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](~/samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]

## <a name="re-throwing-an-exception"></a><span data-ttu-id="816ed-111">Повторный вызов исключения</span><span class="sxs-lookup"><span data-stu-id="816ed-111">Re-throwing an exception</span></span>

<span data-ttu-id="816ed-112">`throw` можно также использовать в блоке `catch` для повторного создания исключения, обрабатываемого в блоке `catch`.</span><span class="sxs-lookup"><span data-stu-id="816ed-112">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="816ed-113">В этом случае оператор `throw` не принимает операнд исключения.</span><span class="sxs-lookup"><span data-stu-id="816ed-113">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="816ed-114">Это наиболее полезно, когда метод передает аргумент от вызывающего объекта в другой метод библиотеки, а метод библиотеки создает исключение, которое должно быть передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="816ed-114">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="816ed-115">Например, в следующем примере повторно создается исключение <xref:System.NullReferenceException>, возникающее при попытке получить первый символ неинициализированной строки.</span><span class="sxs-lookup"><span data-stu-id="816ed-115">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span>

[!code-csharp[csrefKeyword#3](~/samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]

> [!IMPORTANT]
> <span data-ttu-id="816ed-116">Можно также использовать синтаксис `throw e` в блоке `catch`, чтобы создать исключение, которое будет передано вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="816ed-116">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="816ed-117">В этом случае трассировка стека исходного исключения, которое доступно из свойства <xref:System.Exception.StackTrace>, не сохраняется.</span><span class="sxs-lookup"><span data-stu-id="816ed-117">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>

## <a name="the-throw-expression"></a><span data-ttu-id="816ed-118">Выражение `throw`</span><span class="sxs-lookup"><span data-stu-id="816ed-118">The `throw` expression</span></span>

<span data-ttu-id="816ed-119">Начиная с C# 7.0 `throw` можно использовать в качестве выражения, а также как оператор.</span><span class="sxs-lookup"><span data-stu-id="816ed-119">Starting with C# 7.0, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="816ed-120">Это позволяет вызывать исключения в контекстах, которые ранее не поддерживались.</span><span class="sxs-lookup"><span data-stu-id="816ed-120">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="816ed-121">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="816ed-121">These include:</span></span>

- <span data-ttu-id="816ed-122">[Условный оператор](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="816ed-122">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="816ed-123">В следующем примере используется исключение `throw` для создания <xref:System.ArgumentException>, если методу передается массив пустых строк.</span><span class="sxs-lookup"><span data-stu-id="816ed-123">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="816ed-124">До выхода C# 7.0 эта логика должна была отображаться в операторе `if`/`else`.</span><span class="sxs-lookup"><span data-stu-id="816ed-124">Before C# 7.0, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](~/samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]

- <span data-ttu-id="816ed-125">[Оператор объединения с NULL](../operators/null-coalescing-operator.md).</span><span class="sxs-lookup"><span data-stu-id="816ed-125">[the null-coalescing operator](../operators/null-coalescing-operator.md).</span></span> <span data-ttu-id="816ed-126">В следующем примере выражение `throw` используется с оператором, принимающим значение NULL, для создания исключения, если строка, назначенная свойству `Name` является `null`.</span><span class="sxs-lookup"><span data-stu-id="816ed-126">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>

   [!code-csharp[csrefKeyword#5](~/samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]

- <span data-ttu-id="816ed-127">Метод или [лямбда](../operators/lambda-expressions.md), воплощающие выражение.</span><span class="sxs-lookup"><span data-stu-id="816ed-127">an expression-bodied [lambda](../operators/lambda-expressions.md) or method.</span></span> <span data-ttu-id="816ed-128">В следующем примере показан метод, воплощающий выражение, который создает <xref:System.InvalidCastException>, так как преобразование в значение <xref:System.DateTime> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="816ed-128">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>

   [!code-csharp[csrefKeyword#6](~/samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="816ed-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="816ed-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="816ed-130">См. также</span><span class="sxs-lookup"><span data-stu-id="816ed-130">See also</span></span>

- [<span data-ttu-id="816ed-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="816ed-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="816ed-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="816ed-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="816ed-133">try-catch</span><span class="sxs-lookup"><span data-stu-id="816ed-133">try-catch</span></span>](try-catch.md)
- [<span data-ttu-id="816ed-134">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="816ed-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="816ed-135">Практическое руководство. Явное создание исключений</span><span class="sxs-lookup"><span data-stu-id="816ed-135">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
