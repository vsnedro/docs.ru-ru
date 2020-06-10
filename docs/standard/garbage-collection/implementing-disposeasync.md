---
title: Реализация метода DisposeAsync
description: ''
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: c4f541d5a4f5b5fd31b344a299789d86cd78424c
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84311002"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="f034a-102">Реализация метода DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="f034a-102">Implement a DisposeAsync method</span></span>

<span data-ttu-id="f034a-103">Интерфейс <xref:System.IAsyncDisposable?displayProperty=nameWithType> впервые появился в составе C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="f034a-103">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="f034a-104">Метод <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> реализуется, когда нужно выполнить очистку ресурса. Для этих целей также [реализуется метод Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="f034a-104">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="f034a-105">Но одно из ключевых различий заключается в том, что эта реализация позволяет выполнять асинхронные операции очистки.</span><span class="sxs-lookup"><span data-stu-id="f034a-105">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="f034a-106">Метод <xref:System.IAsyncDisposable.DisposeAsync> возвращает значение <xref:System.Threading.Tasks.ValueTask>, представляющее асинхронную операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="f034a-106">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="f034a-107">Обычно при реализации интерфейса <xref:System.IAsyncDisposable> классы также будут реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="f034a-107">It is typical that when implementing the <xref:System.IAsyncDisposable> interface, classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="f034a-108">Хороший шаблон реализации интерфейса <xref:System.IAsyncDisposable> должен быть подготовлен либо для синхронного, либо для асинхронного удаления.</span><span class="sxs-lookup"><span data-stu-id="f034a-108">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="f034a-109">Все рекомендации по реализации шаблона освобождения относятся к реализации асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="f034a-109">All of the guidance for implementing the dispose pattern applies to the asynchronous implementation.</span></span> <span data-ttu-id="f034a-110">В этой статье предполагается, что вы уже знаете, как [реализовать метод Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="f034a-110">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="f034a-111">DisposeAsync() и DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="f034a-111">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="f034a-112">Интерфейс <xref:System.IAsyncDisposable> объявляет единственный метод без параметров — <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="f034a-112">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="f034a-113">Любой незапечатанный класс должен иметь дополнительный метод `DisposeAsyncCore()`, который также возвращает <xref:System.Threading.Tasks.ValueTask>.</span><span class="sxs-lookup"><span data-stu-id="f034a-113">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="f034a-114">Реализация метода <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> с атрибутом `public` без параметров.</span><span class="sxs-lookup"><span data-stu-id="f034a-114">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="f034a-115">Метод `protected virtual ValueTask DisposeAsyncCore()` со следующей сигнатурой:</span><span class="sxs-lookup"><span data-stu-id="f034a-115">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

<span data-ttu-id="f034a-116">Метод `DisposeAsyncCore()` имеет атрибут `virtual`, чтобы производные классы могли определять дополнительную очистку в своих переопределениях.</span><span class="sxs-lookup"><span data-stu-id="f034a-116">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

### <a name="the-disposeasync-method"></a><span data-ttu-id="f034a-117">Метод DisposeAsync()</span><span class="sxs-lookup"><span data-stu-id="f034a-117">The DisposeAsync() method</span></span>

<span data-ttu-id="f034a-118">Метод `DisposeAsync()` с атрибутом `public` без параметров вызывается неявно в инструкции `await using`, и его назначение состоит в том, чтобы освободить неуправляемые ресурсы, выполнить общую очистку и указать, что метод завершения, если он задан, не нужно выполнять.</span><span class="sxs-lookup"><span data-stu-id="f034a-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, needn't run.</span></span> <span data-ttu-id="f034a-119">Освобождение памяти, связанной с управляемым объектом, всегда оставляется [сборщику мусора](index.md).</span><span class="sxs-lookup"><span data-stu-id="f034a-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="f034a-120">Он имеет стандартную реализацию:</span><span class="sxs-lookup"><span data-stu-id="f034a-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="f034a-121">Основным отличием шаблона асинхронного освобождения от шаблона освобождения является то, что когда из метода <xref:System.IAsyncDisposable.DisposeAsync> выполняется вызов метода перегрузки `Dispose(bool)`, в качестве аргумента передается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f034a-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="f034a-122">В то же время при реализации метода <xref:System.IDisposable.Dispose?displayProperty=nameWithType> вместо этого передается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f034a-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="f034a-123">Это помогает обеспечить функциональную эквивалентность с шаблоном синхронного освобождения, а также гарантирует, что пути кода метода завершения по-прежнему вызываются.</span><span class="sxs-lookup"><span data-stu-id="f034a-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="f034a-124">Другими словами, метод `DisposeAsyncCore()` будет освобождать управляемые ресурсы асинхронно, поэтому вы не захотите, чтобы они также освобождались и синхронно.</span><span class="sxs-lookup"><span data-stu-id="f034a-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="f034a-125">Следовательно, вызывайте `Dispose(false)` вместо `Dispose(true)`.</span><span class="sxs-lookup"><span data-stu-id="f034a-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="f034a-126">Реализация шаблона асинхронного освобождения</span><span class="sxs-lookup"><span data-stu-id="f034a-126">Implement the async dispose pattern</span></span>

<span data-ttu-id="f034a-127">Все незапечатанные классы должны рассматриваться как потенциальные базовые классы, так как они поддерживают наследование.</span><span class="sxs-lookup"><span data-stu-id="f034a-127">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="f034a-128">При реализации шаблона асинхронного освобождения для любого потенциального базового класса вы должны предоставить метод `protected virtual ValueTask DisposeAsyncCore()`.</span><span class="sxs-lookup"><span data-stu-id="f034a-128">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="f034a-129">Ниже приведен пример реализации шаблона асинхронного освобождения, в котором используется <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f034a-129">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="f034a-130">В предыдущем примере использовался <xref:System.Text.Json.Utf8JsonWriter>. Дополнительные сведения по `System.Text.Json` см. в разделе [Миграция от Newtonsoft.Json к System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="f034a-130">The previous example used the <xref:System.Text.Json.Utf8JsonWriter>, for more information on `System.Text.Json`, see, [migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="f034a-131">Использование интерфейса асинхронного высвобождения</span><span class="sxs-lookup"><span data-stu-id="f034a-131">Using async disposable</span></span>

<span data-ttu-id="f034a-132">Чтобы правильно использовать объект, который реализует интерфейс <xref:System.IAsyncDisposable>, следует использовать ключевые слова [await](../../csharp/language-reference/operators/await.md) и [using](../../csharp/language-reference/keywords/using.md) вместе.</span><span class="sxs-lookup"><span data-stu-id="f034a-132">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using.md) keywords together.</span></span> <span data-ttu-id="f034a-133">Рассмотрим следующий пример. В нем создается экземпляр класса `ExampleAsyncDisposable`, который затем заключается в инструкцию `await using`.</span><span class="sxs-lookup"><span data-stu-id="f034a-133">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated, then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="f034a-134">Для настройки порядка маршалирования продолжения задачи в ее исходном контексте или в планировщике используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> интерфейса <xref:System.IAsyncDisposable>.</span><span class="sxs-lookup"><span data-stu-id="f034a-134">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="f034a-135">Дополнительные сведения о методе `ConfigureAwait` см. в разделе [Вопросы и ответы по ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="f034a-135">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="f034a-136">В ситуациях, когда использование `ConfigureAwait` не требуется, можно упростить инструкцию `await using` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f034a-136">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="f034a-137">Более того, ее можно написать так, чтобы неявно использовалась область [объявления using](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="f034a-137">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="f034a-138">Стекированные объявления using</span><span class="sxs-lookup"><span data-stu-id="f034a-138">Stacked usings</span></span>

<span data-ttu-id="f034a-139">Когда вы создаете и используете несколько объектов, реализующих <xref:System.IAsyncDisposable>, стекирование операторов `using` в ошибочных условиях может предотвратить вызовы <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="f034a-139">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="f034a-140">Чтобы предотвратить потенциальную проблему, вы должны избегать стекирования и придерживаться следующего примера шаблона:</span><span class="sxs-lookup"><span data-stu-id="f034a-140">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="f034a-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f034a-141">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
