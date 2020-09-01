---
description: Справочник по C#. volatile
title: Справочник по C#. volatile
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: bb89e99e8e28ff1e263817f498619dbfae700a50
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141703"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="9b034-103">volatile (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="9b034-103">volatile (C# Reference)</span></span>

<span data-ttu-id="9b034-104">Ключевое слово `volatile` означает, что поле может изменить несколько потоков, выполняемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="9b034-104">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="9b034-105">Компилятор, среда выполнения или даже аппаратное обеспечение могут изменять порядок операций чтения и записи в расположения в памяти для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="9b034-105">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="9b034-106">К полям, которые объявлены как `volatile`, такие оптимизации не применяются.</span><span class="sxs-lookup"><span data-stu-id="9b034-106">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="9b034-107">Добавление модификатора `volatile` гарантирует, что все потоки будут видеть временные записи, выполняемые другим потоком, в порядке их выполнения.</span><span class="sxs-lookup"><span data-stu-id="9b034-107">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="9b034-108">Нет никакой гарантии единого общего прядка временных записей во всех потоках выполнения.</span><span class="sxs-lookup"><span data-stu-id="9b034-108">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="9b034-109">Ключевое слово `volatile` может применяться к полям следующих типов:</span><span class="sxs-lookup"><span data-stu-id="9b034-109">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="9b034-110">Ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="9b034-110">Reference types.</span></span>
- <span data-ttu-id="9b034-111">Типы указателей (в небезопасном контексте).</span><span class="sxs-lookup"><span data-stu-id="9b034-111">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="9b034-112">Несмотря на то, что сам указатель может быть изменяемым, объект, на который он указывает, должен быть постоянным.</span><span class="sxs-lookup"><span data-stu-id="9b034-112">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="9b034-113">Другими словами, объявить указатель на изменяемый объект невозможно.</span><span class="sxs-lookup"><span data-stu-id="9b034-113">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="9b034-114">Простые типы, например `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` и `bool`.</span><span class="sxs-lookup"><span data-stu-id="9b034-114">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="9b034-115">Тип `enum` с одним из следующих базовых типов: `byte`, `sbyte`, `short`, `ushort`, `int` или `uint`.</span><span class="sxs-lookup"><span data-stu-id="9b034-115">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="9b034-116">Параметры универсального типа называются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="9b034-116">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="9b034-117"><xref:System.IntPtr> и <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="9b034-117"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="9b034-118">Другие типы, включая `double` и `long`, нельзя снабдить модификатором `volatile`, потому что для них не гарантируется атомарность операций чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="9b034-118">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="9b034-119">Чтобы защитить многопотоковый доступ к полям таких типов, используйте члены класса <xref:System.Threading.Interlocked> или защиту доступа с помощью инструкции [`lock`](lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9b034-119">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="9b034-120">Ключевое слово `volatile` можно применять только к полям `class` или `struct`.</span><span class="sxs-lookup"><span data-stu-id="9b034-120">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="9b034-121">Локальные переменные не могут объявляться как `volatile`.</span><span class="sxs-lookup"><span data-stu-id="9b034-121">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="9b034-122">Пример</span><span class="sxs-lookup"><span data-stu-id="9b034-122">Example</span></span>

<span data-ttu-id="9b034-123">В следующем примере показано, как объявить переменную поля открытого типа `volatile`.</span><span class="sxs-lookup"><span data-stu-id="9b034-123">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="9b034-124">Следующий пример демонстрирует создание вспомогательного или рабочего потока и его применение для выполнения обработки параллельно с обработкой основного потока.</span><span class="sxs-lookup"><span data-stu-id="9b034-124">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="9b034-125">Дополнительные сведения о многопоточности см. в разделе [Управляемая поточность](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="9b034-125">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="9b034-126">Добавив модификатор `volatile` к объявлению `_shouldStop`, вы всегда получите одинаковые результаты (как показано в приведенном выше фрагменте кода).</span><span class="sxs-lookup"><span data-stu-id="9b034-126">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="9b034-127">Но если член `_shouldStop` не имеет этого модификатора, поведение будет непредсказуемым.</span><span class="sxs-lookup"><span data-stu-id="9b034-127">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="9b034-128">Метод `DoWork` может оптимизировать доступ к членам, что приведет к чтению устаревших данных.</span><span class="sxs-lookup"><span data-stu-id="9b034-128">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="9b034-129">В условиях многопоточного программирования невозможно прогнозировать число операций чтения устаревших данных.</span><span class="sxs-lookup"><span data-stu-id="9b034-129">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="9b034-130">При каждом запуске программы результаты могут отличаться.</span><span class="sxs-lookup"><span data-stu-id="9b034-130">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9b034-131">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="9b034-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9b034-132">См. также</span><span class="sxs-lookup"><span data-stu-id="9b034-132">See also</span></span>

- [<span data-ttu-id="9b034-133">Спецификация языка C#: ключевое слово volatile</span><span class="sxs-lookup"><span data-stu-id="9b034-133">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="9b034-134">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="9b034-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9b034-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9b034-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9b034-136">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="9b034-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="9b034-137">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="9b034-137">Modifiers</span></span>](index.md)
- [<span data-ttu-id="9b034-138">Оператор lock</span><span class="sxs-lookup"><span data-stu-id="9b034-138">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
