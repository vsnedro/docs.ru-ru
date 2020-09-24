---
title: Реализация метода DisposeAsync
description: Узнайте, как реализовать методы DisposeAsync и DisposeAsyncCore для выполнения асинхронной очистки ресурсов.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 6ddfd860571d883e20fdb18985fe2bc2d9477dec
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720287"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="e2978-103">Реализация метода DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="e2978-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="e2978-104">Интерфейс <xref:System.IAsyncDisposable?displayProperty=nameWithType> впервые появился в составе C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="e2978-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="e2978-105">Метод <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> реализуется, когда нужно выполнить очистку ресурса. Для этих целей также [реализуется метод Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="e2978-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="e2978-106">Но одно из ключевых различий заключается в том, что эта реализация позволяет выполнять асинхронные операции очистки.</span><span class="sxs-lookup"><span data-stu-id="e2978-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="e2978-107">Метод <xref:System.IAsyncDisposable.DisposeAsync> возвращает значение <xref:System.Threading.Tasks.ValueTask>, представляющее асинхронную операцию удаления.</span><span class="sxs-lookup"><span data-stu-id="e2978-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="e2978-108">Обычно при реализации интерфейса <xref:System.IAsyncDisposable> такие классы будут реализовывать интерфейс <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="e2978-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="e2978-109">Хороший шаблон реализации интерфейса <xref:System.IAsyncDisposable> должен быть подготовлен либо для синхронного, либо для асинхронного удаления.</span><span class="sxs-lookup"><span data-stu-id="e2978-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous or asynchronous dispose.</span></span> <span data-ttu-id="e2978-110">Все рекомендации по реализации шаблона освобождения относятся и к реализации асинхронной операции.</span><span class="sxs-lookup"><span data-stu-id="e2978-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="e2978-111">В этой статье предполагается, что вы уже знаете, как [реализовать метод Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="e2978-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="e2978-112">DisposeAsync() и DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="e2978-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="e2978-113">Интерфейс <xref:System.IAsyncDisposable> объявляет единственный метод без параметров — <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="e2978-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="e2978-114">Любой незапечатанный класс должен иметь дополнительный метод `DisposeAsyncCore()`, который также возвращает <xref:System.Threading.Tasks.ValueTask>.</span><span class="sxs-lookup"><span data-stu-id="e2978-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="e2978-115">Реализация метода <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> с атрибутом `public` без параметров.</span><span class="sxs-lookup"><span data-stu-id="e2978-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="e2978-116">Метод `protected virtual ValueTask DisposeAsyncCore()` со следующей сигнатурой:</span><span class="sxs-lookup"><span data-stu-id="e2978-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="e2978-117">Метод DisposeAsync()</span><span class="sxs-lookup"><span data-stu-id="e2978-117">The DisposeAsync() method</span></span>

<span data-ttu-id="e2978-118">Метод `DisposeAsync()` с атрибутом `public` без параметров вызывается неявно в инструкции `await using`, и его назначение состоит в том, чтобы освободить неуправляемые ресурсы, выполнить общую очистку и указать, что метод завершения, если он задан, не нужно выполнять.</span><span class="sxs-lookup"><span data-stu-id="e2978-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="e2978-119">Освобождение памяти, связанной с управляемым объектом, всегда оставляется [сборщику мусора](index.md).</span><span class="sxs-lookup"><span data-stu-id="e2978-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="e2978-120">Он имеет стандартную реализацию:</span><span class="sxs-lookup"><span data-stu-id="e2978-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="e2978-121">Основным отличием шаблона асинхронного освобождения от шаблона освобождения является то, что когда из метода <xref:System.IAsyncDisposable.DisposeAsync> выполняется вызов метода перегрузки `Dispose(bool)`, в качестве аргумента передается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e2978-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="e2978-122">В то же время при реализации метода <xref:System.IDisposable.Dispose?displayProperty=nameWithType> вместо него передается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e2978-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however, `true` is passed instead.</span></span> <span data-ttu-id="e2978-123">Это помогает обеспечить функциональную эквивалентность с шаблоном синхронного освобождения, а также гарантирует, что пути кода метода завершения по-прежнему вызываются.</span><span class="sxs-lookup"><span data-stu-id="e2978-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="e2978-124">Другими словами, метод `DisposeAsyncCore()` будет освобождать управляемые ресурсы асинхронно, поэтому вы не захотите, чтобы они также освобождались и синхронно.</span><span class="sxs-lookup"><span data-stu-id="e2978-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="e2978-125">Следовательно, вызывайте `Dispose(false)` вместо `Dispose(true)`.</span><span class="sxs-lookup"><span data-stu-id="e2978-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="e2978-126">Метод DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="e2978-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="e2978-127">Метод `DisposeAsyncCore()` предназначен для выполнения асинхронной очистки управляемых ресурсов или для каскадных вызовов `DisposeAsync()`.</span><span class="sxs-lookup"><span data-stu-id="e2978-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="e2978-128">Он инкапсулирует общие асинхронные операции очистки, когда подкласс наследует базовый класс, который является реализацией <xref:System.IAsyncDisposable>.</span><span class="sxs-lookup"><span data-stu-id="e2978-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="e2978-129">Метод `DisposeAsyncCore()` имеет атрибут `virtual`, чтобы производные классы могли определять дополнительную очистку в своих переопределениях.</span><span class="sxs-lookup"><span data-stu-id="e2978-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="e2978-130">Если реализация <xref:System.IAsyncDisposable> — `sealed`, то метод `DisposeAsyncCore()` не требуется, а асинхронная очистка может выполняться непосредственно в методе <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2978-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="e2978-131">Реализация шаблона асинхронного освобождения</span><span class="sxs-lookup"><span data-stu-id="e2978-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="e2978-132">Все незапечатанные классы должны рассматриваться как потенциальные базовые классы, так как они поддерживают наследование.</span><span class="sxs-lookup"><span data-stu-id="e2978-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="e2978-133">При реализации шаблона асинхронного освобождения для любого потенциального базового класса вы должны предоставить метод `protected virtual ValueTask DisposeAsyncCore()`.</span><span class="sxs-lookup"><span data-stu-id="e2978-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="e2978-134">Ниже приведен пример реализации шаблона асинхронного освобождения, в котором используется <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e2978-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="e2978-135">В предшествующем примере используется <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="e2978-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="e2978-136">Дополнительные сведения о `System.Text.Json` см. в статье [Как выполнить миграцию с Newtonsoft.Json на System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="e2978-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="implement-both-dispose-and-async-dispose-patterns"></a><span data-ttu-id="e2978-137">Реализация шаблонов освобождения и асинхронного освобождения</span><span class="sxs-lookup"><span data-stu-id="e2978-137">Implement both dispose and async dispose patterns</span></span>

<span data-ttu-id="e2978-138">Может потребоваться реализовать оба интерфейса <xref:System.IDisposable> и <xref:System.IAsyncDisposable>, особенно если область класса содержит экземпляры этих реализаций.</span><span class="sxs-lookup"><span data-stu-id="e2978-138">You may need to implement both the <xref:System.IDisposable> and <xref:System.IAsyncDisposable> interfaces, especially when your class scope contains instances of these implementations.</span></span> <span data-ttu-id="e2978-139">Это гарантирует правильную каскадную очистку вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2978-139">Doing so ensures that you can properly cascade clean up calls.</span></span> <span data-ttu-id="e2978-140">Ниже приведен пример класса, который реализует оба интерфейса и демонстрирует соответствующие рекомендации по очистке.</span><span class="sxs-lookup"><span data-stu-id="e2978-140">Here is an example class that implements both interfaces and demonstrates the proper guidance for cleanup.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

<span data-ttu-id="e2978-141">Реализации <xref:System.IDisposable.Dispose?displayProperty=nameWithType> и <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> являются простым шаблонным кодом.</span><span class="sxs-lookup"><span data-stu-id="e2978-141">The <xref:System.IDisposable.Dispose?displayProperty=nameWithType> and <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementations are both simple boilerplate code.</span></span>

<span data-ttu-id="e2978-142">В методе перегрузки `Dispose(bool)` экземпляр <xref:System.IDisposable> условно удаляется, если он не `null`.</span><span class="sxs-lookup"><span data-stu-id="e2978-142">In the `Dispose(bool)` overload method, the <xref:System.IDisposable> instance is conditionally disposed of if it is not `null`.</span></span> <span data-ttu-id="e2978-143">Экземпляр <xref:System.IAsyncDisposable> приводится к типу <xref:System.IDisposable> и, если он не имеет значения `null`, он также удаляется.</span><span class="sxs-lookup"><span data-stu-id="e2978-143">The <xref:System.IAsyncDisposable> instance is cast as <xref:System.IDisposable>, and if it is also not `null`, it is disposed of as well.</span></span> <span data-ttu-id="e2978-144">Затем оба экземпляра назначаются `null`.</span><span class="sxs-lookup"><span data-stu-id="e2978-144">Both instances are then assigned to `null`.</span></span>

<span data-ttu-id="e2978-145">В методе `DisposeAsyncCore()` используется один и тот же логический подход.</span><span class="sxs-lookup"><span data-stu-id="e2978-145">With the `DisposeAsyncCore()` method, the same logical approach is followed.</span></span> <span data-ttu-id="e2978-146">Если экземпляр <xref:System.IAsyncDisposable> не является `null`, то будет ожидаться его вызов `DisposeAsync().ConfigureAwait(false)`.</span><span class="sxs-lookup"><span data-stu-id="e2978-146">If the <xref:System.IAsyncDisposable> instance is not `null`, its call to `DisposeAsync().ConfigureAwait(false)` is awaited.</span></span> <span data-ttu-id="e2978-147">Если экземпляр <xref:System.IDisposable> также является реализацией <xref:System.IAsyncDisposable>, он также освобождается асинхронно.</span><span class="sxs-lookup"><span data-stu-id="e2978-147">If the <xref:System.IDisposable> instance is also an implementation of <xref:System.IAsyncDisposable>, it's also disposed of asynchronously.</span></span> <span data-ttu-id="e2978-148">Затем оба экземпляра назначаются `null`.</span><span class="sxs-lookup"><span data-stu-id="e2978-148">Both instances are then assigned to `null`.</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="e2978-149">Использование интерфейса асинхронного высвобождения</span><span class="sxs-lookup"><span data-stu-id="e2978-149">Using async disposable</span></span>

<span data-ttu-id="e2978-150">Чтобы правильно использовать объект, который реализует интерфейс <xref:System.IAsyncDisposable>, следует использовать ключевые слова [await](../../csharp/language-reference/operators/await.md) и [using](../../csharp/language-reference/keywords/using-statement.md) вместе.</span><span class="sxs-lookup"><span data-stu-id="e2978-150">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md) and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="e2978-151">Рассмотрим следующий пример. В нем создается экземпляр класса `ExampleAsyncDisposable`, который затем заключается в инструкцию `await using`.</span><span class="sxs-lookup"><span data-stu-id="e2978-151">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="e2978-152">Для настройки порядка маршалирования продолжения задачи в ее исходном контексте или в планировщике используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> интерфейса <xref:System.IAsyncDisposable>.</span><span class="sxs-lookup"><span data-stu-id="e2978-152">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="e2978-153">Дополнительные сведения о методе `ConfigureAwait` см. в разделе [Вопросы и ответы по ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="e2978-153">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="e2978-154">В ситуациях, когда использование `ConfigureAwait` не требуется, можно упростить инструкцию `await using` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e2978-154">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="e2978-155">Более того, ее можно написать так, чтобы неявно использовалась область [объявления using](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="e2978-155">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="e2978-156">Стекированные объявления using</span><span class="sxs-lookup"><span data-stu-id="e2978-156">Stacked usings</span></span>

<span data-ttu-id="e2978-157">Когда вы создаете и используете несколько объектов, реализующих <xref:System.IAsyncDisposable>, стекирование операторов `using` в ошибочных условиях может предотвратить вызовы <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="e2978-157">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="e2978-158">Чтобы предотвратить потенциальную проблему, вы должны избегать стекирования и придерживаться следующего примера шаблона:</span><span class="sxs-lookup"><span data-stu-id="e2978-158">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="e2978-159">См. также</span><span class="sxs-lookup"><span data-stu-id="e2978-159">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
