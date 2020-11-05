---
title: Реализация метода DisposeAsync
description: Узнайте, как реализовать методы DisposeAsync и DisposeAsyncCore для выполнения асинхронной очистки ресурсов.
author: IEvangelist
ms.author: dapine
ms.date: 10/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 5aa82c507c22a4795f39267ac8f435599fb9cd92
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687725"
---
# <a name="implement-a-disposeasync-method"></a>Реализация метода DisposeAsync

Интерфейс <xref:System.IAsyncDisposable?displayProperty=nameWithType> впервые появился в составе C# 8.0. Метод <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> реализуется, когда нужно выполнить очистку ресурса. Для этих целей также [реализуется метод Dispose](implementing-dispose.md). Но одно из ключевых различий заключается в том, что эта реализация позволяет выполнять асинхронные операции очистки. Метод <xref:System.IAsyncDisposable.DisposeAsync> возвращает значение <xref:System.Threading.Tasks.ValueTask>, представляющее асинхронную операцию удаления.

Обычно при реализации интерфейса <xref:System.IAsyncDisposable> такие классы будут реализовывать интерфейс <xref:System.IDisposable>. Хороший шаблон реализации интерфейса <xref:System.IAsyncDisposable> должен быть подготовлен либо для синхронного, либо для асинхронного удаления. Все рекомендации по реализации шаблона освобождения относятся и к реализации асинхронной операции. В этой статье предполагается, что вы уже знаете, как [реализовать метод Dispose](implementing-dispose.md).

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() и DisposeAsyncCore()

Интерфейс <xref:System.IAsyncDisposable> объявляет единственный метод без параметров — <xref:System.IAsyncDisposable.DisposeAsync>. Любой незапечатанный класс должен иметь дополнительный метод `DisposeAsyncCore()`, который также возвращает <xref:System.Threading.Tasks.ValueTask>.

- Реализация метода <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> с атрибутом `public` без параметров.
- Метод `protected virtual ValueTask DisposeAsyncCore()` со следующей сигнатурой:

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a>Метод DisposeAsync()

Метод `DisposeAsync()` с атрибутом `public` без параметров вызывается неявно в инструкции `await using`, и его назначение состоит в том, чтобы освободить неуправляемые ресурсы, выполнить общую очистку и указать, что метод завершения, если он задан, не нужно выполнять. Освобождение памяти, связанной с управляемым объектом, всегда оставляется [сборщику мусора](index.md). Он имеет стандартную реализацию:

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
> Основным отличием шаблона асинхронного освобождения от шаблона освобождения является то, что когда из метода <xref:System.IAsyncDisposable.DisposeAsync> выполняется вызов метода перегрузки `Dispose(bool)`, в качестве аргумента передается значение `false`. В то же время при реализации метода <xref:System.IDisposable.Dispose?displayProperty=nameWithType> вместо него передается значение `true`. Это помогает обеспечить функциональную эквивалентность с шаблоном синхронного освобождения, а также гарантирует, что пути кода метода завершения по-прежнему вызываются. Другими словами, метод `DisposeAsyncCore()` будет освобождать управляемые ресурсы асинхронно, поэтому вы не захотите, чтобы они также освобождались и синхронно. Следовательно, вызывайте `Dispose(false)` вместо `Dispose(true)`.

### <a name="the-disposeasynccore-method"></a>Метод DisposeAsyncCore()

Метод `DisposeAsyncCore()` предназначен для выполнения асинхронной очистки управляемых ресурсов или для каскадных вызовов `DisposeAsync()`. Он инкапсулирует общие асинхронные операции очистки, когда подкласс наследует базовый класс, который является реализацией <xref:System.IAsyncDisposable>. Метод `DisposeAsyncCore()` имеет атрибут `virtual`, чтобы производные классы могли определять дополнительную очистку в своих переопределениях.

> [!TIP]
> Если реализация <xref:System.IAsyncDisposable> — `sealed`, то метод `DisposeAsyncCore()` не требуется, а асинхронная очистка может выполняться непосредственно в методе <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>.

## <a name="implement-the-async-dispose-pattern"></a>Реализация шаблона асинхронного освобождения

Все незапечатанные классы должны рассматриваться как потенциальные базовые классы, так как они поддерживают наследование. При реализации шаблона асинхронного освобождения для любого потенциального базового класса вы должны предоставить метод `protected virtual ValueTask DisposeAsyncCore()`. Ниже приведен пример реализации шаблона асинхронного освобождения, в котором используется <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

В предшествующем примере используется <xref:System.Text.Json.Utf8JsonWriter>. Дополнительные сведения о `System.Text.Json` см. в статье [Как выполнить миграцию с Newtonsoft.Json на System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="implement-both-dispose-and-async-dispose-patterns"></a>Реализация шаблонов освобождения и асинхронного освобождения

Может потребоваться реализовать оба интерфейса <xref:System.IDisposable> и <xref:System.IAsyncDisposable>, особенно если область класса содержит экземпляры этих реализаций. Это гарантирует правильную каскадную очистку вызовов. Ниже приведен пример класса, который реализует оба интерфейса и демонстрирует соответствующие рекомендации по очистке.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

Реализации <xref:System.IDisposable.Dispose?displayProperty=nameWithType> и <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> являются простым шаблонным кодом.

В методе перегрузки `Dispose(bool)` экземпляр <xref:System.IDisposable> условно удаляется, если он не `null`. Экземпляр <xref:System.IAsyncDisposable> приводится к типу <xref:System.IDisposable> и, если он не имеет значения `null`, он также удаляется. Затем оба экземпляра назначаются `null`.

В методе `DisposeAsyncCore()` используется один и тот же логический подход. Если экземпляр <xref:System.IAsyncDisposable> не является `null`, то будет ожидаться его вызов `DisposeAsync().ConfigureAwait(false)`. Если экземпляр <xref:System.IDisposable> также является реализацией <xref:System.IAsyncDisposable>, он также освобождается асинхронно. Затем оба экземпляра назначаются `null`.

## <a name="using-async-disposable"></a>Использование интерфейса асинхронного высвобождения

Чтобы правильно использовать объект, который реализует интерфейс <xref:System.IAsyncDisposable>, следует использовать ключевые слова [await](../../csharp/language-reference/operators/await.md) и [using](../../csharp/language-reference/keywords/using-statement.md) вместе. Рассмотрим следующий пример. В нем создается экземпляр класса `ExampleAsyncDisposable`, который затем заключается в инструкцию `await using`.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Для настройки порядка маршалирования продолжения задачи в ее исходном контексте или в планировщике используйте метод расширения <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> интерфейса <xref:System.IAsyncDisposable>. Дополнительные сведения о методе `ConfigureAwait` см. в разделе [Вопросы и ответы по ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

В ситуациях, когда использование `ConfigureAwait` не требуется, можно упростить инструкцию `await using` следующим образом:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Более того, ее можно написать так, чтобы неявно использовалась область [объявления using](../../csharp/whats-new/csharp-8.md#using-declarations).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Стекированные объявления using

Когда вы создаете и используете несколько объектов, реализующих <xref:System.IAsyncDisposable>, стекирование операторов `await using` с помощью <xref:System.Threading.Tasks.ValueTask.ConfigureAwait%2A> в ошибочных условиях может предотвратить вызовы <xref:System.IAsyncDisposable.DisposeAsync>. Чтобы метод <xref:System.IAsyncDisposable.DisposeAsync> вызывался всегда, следует избегать стекирования. В приведенных ниже трех примерах кода показаны допустимые шаблоны.

### <a name="acceptable-pattern-one"></a>Допустимый шаблон 1

:::code language="csharp" id="one" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

В предыдущем примере каждая асинхронная операция очистки явно ограничена блоком `await using`. Внешняя область определяется скобками. Так как `objOne` заключает `objTwo` в скобки, сначала удаляется `objTwo`, а затем `objOne`. У обоих экземпляров `IAsyncDisposable` методы <xref:System.IAsyncDisposable.DisposeAsync> имеют оператор await, благодаря чему выполняется асинхронная операция очистки. Вызовы вложены, а не стекированы.

### <a name="acceptable-pattern-two"></a>Допустимый шаблон 2

:::code language="csharp" id="two" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

В предыдущем примере каждая асинхронная операция очистки явно ограничена блоком `await using`. В конце каждого блока метод <xref:System.IAsyncDisposable.DisposeAsync> соответствующего экземпляра `IAsyncDisposable` имеет оператор await, благодаря чему выполняется асинхронная операция очистки. Вызовы являются последовательными, а не стекированы. В этом сценарии сначала удаляется `objOne`, а затем `objTwo`.

### <a name="acceptable-pattern-three"></a>Допустимый шаблон 3

:::code language="csharp" id="three" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

В предыдущем примере каждая асинхронная операция очистки явно ограничена телом содержащего метода. В конце внешнего блока экземпляры `IAsyncDisposable` выполняют асинхронные операции очистки. При этом они выполняются в порядке, обратном тому, в котором они были объявлены. Это означает, что `objTwo` удаляется перед `objOne`.

### <a name="unacceptable-pattern"></a>Недопустимый шаблон

Если в конструкторе `AnotherAsyncDisposable` возникает исключение, то `objOne` не удаляется надлежащим образом.

:::code language="csharp" id="dontdothis" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

> [!TIP]
> Избегайте такого шаблона, так как он может привести к непредвиденному поведению.

## <a name="see-also"></a>См. также

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
