---
title: Реализация метода Dispose
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: a002e0d27dfe28795b28e6813c4f5d5b3e13cdaf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396908"
---
# <a name="implement-a-dispose-method"></a>Реализация метода Dispose

Реализация метода <xref:System.IDisposable.Dispose%2A> в основном используется для освобождения неуправляемых ресурсов, которые используются в коде. При работе с членами экземпляра, которые являются реализациями <xref:System.IDisposable>, обычно применяются каскадные вызовы <xref:System.IDisposable.Dispose%2A>. Существуют и другие причины для реализации <xref:System.IDisposable.Dispose%2A>, например отмена ранее выполненных действий. Так можно освободить выделенную память, удалить из коллекции добавленный элемент, сообщить об отмене запрошенной блокировки и т. д.

[Сборщик мусора .NET](index.md) не выделяет и не освобождает неуправляемую память. Шаблон освобождения объекта налагает определенные правила на время существования объекта. Шаблон освобождения используется для объектов, которые реализуют интерфейс <xref:System.IDisposable>, и часто встречается при взаимодействии с дескрипторами файлов и каналов, дескрипторами реестра, дескрипторами ожидания и указателями на блоки неуправляемой памяти. Это связано с тем, что сборщик мусора не может удалять неуправляемые объекты.

Чтобы обеспечить нормальную очистку таких ресурсов, метод <xref:System.IDisposable.Dispose%2A> должен быть идемпотентным, то есть поддерживать многократный вызов без создания исключений. Кроме того, последующие вызовы <xref:System.IDisposable.Dispose%2A> не должны выполнять никаких действий.

В приведенном для метода <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> примере показано, как сборка мусора может привести к выполнению метода завершения, в то время как по-прежнему будет использоваться неуправляемая ссылка на объект или его члены. Возможно, имеет смысл использовать <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType>, чтобы запретить сборку мусора для объекта с момента начала текущей процедуры до вызова этого метода.

## <a name="safe-handles"></a>Безопасные дескрипторы

Написание кода для метода завершения объекта является сложной задачей, которая может вызвать проблемы при неправильном выполнении. Поэтому вместо реализации метода завершения рекомендуется создавать объекты <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> — это абстрактный управляемый тип, выполняющий роль оболочки для <xref:System.IntPtr?displayProperty=nameWithType>, который идентифицирует неуправляемый ресурс. В среде Windows он может обозначать дескриптор, а в среде UNIX — дескриптор файла. Он обеспечивает всю логику, которая гарантирует, что при удалении `SafeHandle` или уничтожении всех ссылок на `SafeHandle` и завершении экземпляра `SafeHandle` ресурс будет освобожден один и только один раз.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> — это абстрактный базовый класс. Производные классы предоставляют определенные экземпляры для различных видов дескрипторов. Эти производные классы проверяют, какие значения <xref:System.IntPtr?displayProperty=nameWithType> считаются недопустимыми и как фактически освободить дескриптор. Например, класс <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> является производным от `SafeHandle`, выступает оболочкой для структур `IntPtrs`, которые определяют открытые дескрипторы файлов, а также переопределяет свой метод <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle?displayProperty=nameWithType> для его закрытия (через функцию `close` в UNIX или `CloseHandle` в Windows). Большинство API-интерфейсов в библиотеках .NET, которые создают неуправляемый ресурс, заключают его в `SafeHandle` и возвращают `SafeHandle` по мере необходимости, но не выдают необработанный указатель. В ситуациях, когда вы взаимодействуете с неуправляемым компонентом и получаете структуру `IntPtr` для неуправляемого ресурса, можно создать собственный тип `SafeHandle` в качестве оболочки структуры. В результате для некоторых типов, которые не являются `SafeHandle`, нужно реализовать методы завершения. Реализации шаблона освобождения чаще всего являются оболочками для других управляемых ресурсов, некоторые из которых могут быть `SafeHandle`.

Безопасные дескрипторы предоставляются следующими производными классами в пространстве имен <xref:Microsoft.Win32.SafeHandles>:

- Классы <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> и <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> — для файлов, файлов сопоставления памяти и каналов.
- Класс <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> — для представлений памяти.
- Классы <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> и <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> — для конструкций шифрования.
- Класс <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> — для разделов реестра.
- Класс <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> — для дескрипторов ожидания.

## <a name="dispose-and-disposebool"></a>Dispose() и Dispose(bool)

Интерфейс <xref:System.IDisposable> требует реализации одного метода <xref:System.IDisposable.Dispose%2A> без параметров. Кроме того, любой незапечатанный класс должен иметь дополнительный метод перегрузки `Dispose(bool)`, в котором реализуется следующее:

- невиртуальный (`public` в Visual Basic) метод <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> с атрибутом `NonInheritable` и без параметров;

- метод `Dispose` с атрибутом `protected virtual` (`Overridable` в Visual Basic) со следующей сигнатурой:

  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]

  > [!IMPORTANT]
  > Параметр `disposing` при вызове из метода завершения должен иметь значение `false`, а при вызове из метода <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> — значение `true`. Иными словами, при детерминированном вызове он будет иметь значение `true`, а при недетерминированном вызове — `false`.

### <a name="the-dispose-method"></a>Метод Dispose()

Поскольку невиртуальный (`public` в Visual Basic) метод `Dispose` с атрибутом `NonInheritable` без параметров вызывается объектом-получателем типа, его назначение состоит в том, чтобы освободить неуправляемые ресурсы и указать, что метод завершения, если он задан, не должен выполняться. Освобождение физической памяти, связанной с управляемым объектом, всегда оставляется [сборщику мусора](index.md). Он имеет стандартную реализацию:

[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]

Метод `Dispose` полностью выполняет очистку объектов, поэтому сборщику мусора не требуется вызывать переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Таким образом, вызов метода <xref:System.GC.SuppressFinalize%2A> не позволит сборщику мусора запустить метод завершения. Если тип не имеет метода завершения, вызов метода <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> не производит эффекта. Обратите внимание, что фактическая очистка выполняется в перегрузке метода `Dispose(bool)`.

### <a name="the-disposebool-method-overload"></a>Перегрузка метода Dispose(Boolean)

В этой перегрузке параметр `disposing` типа <xref:System.Boolean> указывает, откуда осуществляется вызов метода: из метода <xref:System.IDisposable.Dispose%2A> (значение `true`) или из метода завершения (значение `false`).

Тело метода состоит из двух блоков кода:

- Блок, который освобождает неуправляемые ресурсы. Этот блок выполняется вне зависимости от значения параметра `disposing`.
- Условный блок, который освобождает управляемые ресурсы. Этот блок выполняется, если параметр `disposing` имеет значение `true`. К управляемым ресурсам, которые он освобождает, могут относиться:

  - **Управляемые объекты, реализующие <xref:System.IDisposable>.** Условный блок может использоваться для вызова реализации <xref:System.IDisposable.Dispose%2A> (каскадное удаление). При использовании класса, производного от <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>, в качестве оболочки для неуправляемого ресурса необходимо вызвать реализацию <xref:System.Runtime.InteropServices.SafeHandle.Dispose?displayProperty=nameWithType>.

  - **Управляемые объекты, которые используют большие объемы памяти или дефицитные ресурсы**. Назначайте ссылки на большие управляемые объекты в `null`, чтобы они чаще оказывались недоступными. Это позволяет освободить их быстрее, чем при недетерминированном алгоритме удаления.

Если метод вызывается из метода завершения, должен выполняться только тот код, который освобождает неуправляемые ресурсы. Разработчик обязан следить, чтобы эта ветвь кода не взаимодействовала с управляемыми объектами, которые могли быть освобождены. Это важно, поскольку порядок, в котором сборщик мусора уничтожает управляемые объекты в процессе завершения, не детерминирован.

## <a name="cascade-dispose-calls"></a>Каскадные вызовы Dispose

Если класс имеет собственное поле или свойство, а его тип реализует <xref:System.IDisposable>, сам класс также обязан реализовывать <xref:System.IDisposable>. Класс, который создает экземпляр реализации <xref:System.IDisposable> и сохраняет его в качестве члена экземпляра, обязан самостоятельно очищать его. Это поможет гарантировать, что удаляемые ссылочные типы получат возможность выполнять очистку детерминированно с помощью метода <xref:System.IDisposable.Dispose%2A>. В нашем примере представлен класс `sealed` (или `NotInheritable` в Visual Basic).

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/disposable1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/disposable1.vb#1)]

## <a name="implement-the-dispose-pattern"></a>Реализация шаблона освобождения

Все незапечатанные классы (в Visual Basic это классы, не имеющие модификатора `NotInheritable`) должны считаться потенциальным базовым классом, так как они поддерживают наследование. При реализации шаблона освобождения для любого класса, который может быть базовым, необходимо обеспечить следующее:

- Реализация <xref:System.IDisposable.Dispose%2A>, которая вызывает метод `Dispose(bool)`.
- Метод `Dispose(bool)`, который выполняет фактическую очистку.
- Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Класс <xref:System.Runtime.InteropServices.SafeHandle> предоставляет метод завершения, поэтому вам не нужно создавать этот метод самостоятельно.

> [!IMPORTANT]
> Базовый класс может ссылаться только на управляемые объекты и реализовывать шаблон освобождения. В таких случаях метод завершения не нужен. Метод завершения нужен только в том случае, если используются прямые ссылки на неуправляемые ресурсы.

Вот общий шаблон реализации шаблона удаления для базового класса, который использует безопасный дескриптор.

[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]

> [!NOTE]
> В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.

Вот общий шаблон реализации шаблона удаления для базового класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>.

[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]

> [!TIP]
> В C# [метод завершения](../../csharp/programming-guide/classes-and-structs/destructors.md) создается путем переопределения метода <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. В Visual Basic для этого используется `Protected Overrides Sub Finalize()`.

## <a name="implement-the-dispose-pattern-for-a-derived-class"></a>Реализация шаблона освобождения для производного класса

Класс, производный от класса, реализующего интерфейс <xref:System.IDisposable>, не должен реализовывать интерфейс <xref:System.IDisposable>, поскольку реализация метода <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> базового класса наследуется производными классами. Вместо этого для очистки производного класса необходимо предоставить следующее:

- Метод `protected override void Dispose(bool)`, который переопределяет метод базового класса и выполняет фактическую очистку производного класса. Кроме того, этот метод должен вызывать метод `base.Dispose(bool)` базового класса (`MyBase.Dispose(bool)` в Visual Basic) и передавать состояние освобождения ресурса в качестве аргумента.
- Любой класс, производный от класса <xref:System.Runtime.InteropServices.SafeHandle>, который создает оболочку для неуправляемого ресурс (рекомендуется), или переопределенный метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>. Класс <xref:System.Runtime.InteropServices.SafeHandle> содержит метод завершения, что освобождает разработчика от необходимости создавать его вручную. Если есть метод завершения, он должен вызывать перегрузку `Dispose(bool)`, указывая аргумент `disposing` со значением `false`.

Вот общий шаблон реализации шаблона удаления для производного класса, который использует безопасный дескриптор:

[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]

> [!NOTE]
> В предыдущем примере используется объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для иллюстрации шаблона. Вместо него может использоваться любой объект, производный от <xref:System.Runtime.InteropServices.SafeHandle>. Обратите внимание, что в этом примере неправильно создаются экземпляры объекта <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>.

Вот общий шаблон реализации шаблона удаления для производного класса, который переопределяет метод <xref:System.Object.Finalize%2A?displayProperty=nameWithType>:

[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]

## <a name="implement-the-dispose-pattern-with-safe-handles"></a>Реализация шаблона освобождения с безопасными дескрипторами

В следующем примере показан шаблон удаления для базового класса `DisposableStreamResource`, который использует безопасный дескриптор для инкапсуляции неуправляемых ресурсов. Он определяет класс `DisposableStreamResource`, который использует <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для создания экземпляра объекта <xref:System.IO.Stream>, который представляет открытый файл. Кроме того, этот класс содержит одно свойство, `Size`, которое возвращает общее количество байтов в файловом потоке.

[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]

## <a name="implement-the-dispose-pattern-for-a-derived-class-with-safe-handles"></a>Реализация шаблона освобождения для производного класса с безопасными дескрипторами

В следующем примере показан шаблон удаления для производного класса `DisposableStreamResource2`, унаследованного от класса `DisposableStreamResource`, представленного в предыдущем примере. Класс добавляет дополнительный метод `WriteFileInfo` и использует объект <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> для создания экземпляра дескриптора записываемого файла.

[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]

## <a name="see-also"></a>См. также

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [Практическое руководство. Определение и использование классов и структур (C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
- [Шаблон ликвидации](implementing-dispose.md)
