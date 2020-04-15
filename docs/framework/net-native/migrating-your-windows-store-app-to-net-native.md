---
title: Миграция приложения для магазина Windows в машинный код .NET
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 987669fc51eeaf7e3bdef3e91a2f1ce23164a055
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389706"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a><span data-ttu-id="f3726-102">Перенести приложение Магазина Windows в .NET Native</span><span class="sxs-lookup"><span data-stu-id="f3726-102">Migrate Your Windows Store App to .NET Native</span></span>

<span data-ttu-id="f3726-103">.NET Native обеспечивает статическую компиляцию приложений в Магазине Windows или на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="f3726-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="f3726-104">В отличие от динамической компиляции, выполняемой JIT-компилятором для приложений магазина Windows или [Генератором машинных образов (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) на устройстве.</span><span class="sxs-lookup"><span data-stu-id="f3726-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="f3726-105">Несмотря на различия, .NET Native пытается сохранить совместимость с [.NET для приложений Магазина Windows.](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)</span><span class="sxs-lookup"><span data-stu-id="f3726-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29).</span></span> <span data-ttu-id="f3726-106">По большей части, вещи, которые работают на .NET для приложений Магазина Windows также работают с .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="f3726-107">Тем не менее в некоторых случаях могут произойти изменения поведения.</span><span class="sxs-lookup"><span data-stu-id="f3726-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="f3726-108">В этом документе обсуждаются эти различия между стандартными .NET для приложений Магазина Windows и .NET Native в следующих областях:</span><span class="sxs-lookup"><span data-stu-id="f3726-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>

- [<span data-ttu-id="f3726-109">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f3726-109">General runtime differences</span></span>](#Runtime)

- [<span data-ttu-id="f3726-110">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="f3726-110">Dynamic programming differences</span></span>](#Dynamic)

- [<span data-ttu-id="f3726-111">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="f3726-111">Other reflection-related differences</span></span>](#Reflection)

- [<span data-ttu-id="f3726-112">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f3726-112">Unsupported scenarios and APIs</span></span>](#Unsupported)

- [<span data-ttu-id="f3726-113">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3726-113">Visual Studio differences</span></span>](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a><span data-ttu-id="f3726-114">Общие различия среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f3726-114">General runtime differences</span></span>

- <span data-ttu-id="f3726-115">Исключения, такие <xref:System.TypeLoadException>как, которые брошены компилятором JIT, когда приложение работает на общем языке времени выполнения (CLR), как правило, приводят к ошибкам времени компиляции при обработке .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>

- <span data-ttu-id="f3726-116">Не вызывайте метод <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> из потока пользовательского интерфейса приложения.</span><span class="sxs-lookup"><span data-stu-id="f3726-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="f3726-117">Это может привести к тупику на .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-117">This can result in a deadlock on .NET Native.</span></span>

- <span data-ttu-id="f3726-118">Не полагайтесь на порядок вызова конструктора статического класса.</span><span class="sxs-lookup"><span data-stu-id="f3726-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="f3726-119">В .NET Native порядок вызова отличается от заказа на стандартное время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3726-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="f3726-120">(Даже со стандартной средой выполнения, не следует рассчитывать на порядок выполнения конструкторов статических классов.)</span><span class="sxs-lookup"><span data-stu-id="f3726-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>

- <span data-ttu-id="f3726-121">Бесконечный цикл без вызовов (например, `while(true);`) на любом потоке может привести к остановке приложения.</span><span class="sxs-lookup"><span data-stu-id="f3726-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="f3726-122">Аналогичным образом, большие или бесконечные ожидания могут также привести приложение к остановке.</span><span class="sxs-lookup"><span data-stu-id="f3726-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>

- <span data-ttu-id="f3726-123">Некоторые общие циклы инициализации не выбрасывают исключений в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="f3726-124">Например, следующий код создает исключение <xref:System.TypeLoadException> исключений в стандартной среде CLR.</span><span class="sxs-lookup"><span data-stu-id="f3726-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="f3726-125">В .NET Родные, это не так.</span><span class="sxs-lookup"><span data-stu-id="f3726-125">In .NET Native, it doesn't.</span></span>

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- <span data-ttu-id="f3726-126">В некоторых случаях .NET Native предоставляет различные реализации библиотек класса .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3726-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="f3726-127">Объект, возвращенный из метода, всегда будет реализовать члены возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="f3726-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="f3726-128">Тем не менее, поскольку его резервная реализация отличается, может оказаться невозможным привести его к тому же набору типов, как это можно было бы сделать на платформах .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3726-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="f3726-129">Например, в некоторых случаях может оказаться невозможным привести объект интерфейса <xref:System.Collections.Generic.IEnumerable%601> , возвращенный такими методами как <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> или <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> , к `T[]`.</span><span class="sxs-lookup"><span data-stu-id="f3726-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>

- <span data-ttu-id="f3726-130">Кэш WinInet не включен по умолчанию в приложениях .NET для Windows Store, но он находится на .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="f3726-131">Это повышает производительность, но сказывается на рабочем наборе.</span><span class="sxs-lookup"><span data-stu-id="f3726-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="f3726-132">Не требуется никаких действий разработчика.</span><span class="sxs-lookup"><span data-stu-id="f3726-132">No developer action is necessary.</span></span>

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a><span data-ttu-id="f3726-133">Различия динамического программирования</span><span class="sxs-lookup"><span data-stu-id="f3726-133">Dynamic programming differences</span></span>

<span data-ttu-id="f3726-134">.NET Native статично связывает код из рамочного .NET, чтобы сделать код приложения локальным для максимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="f3726-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="f3726-135">Тем не менее, двоичные размеры должны оставаться небольшими, поэтому не удается подключить всю платформу .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3726-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="f3726-136">Компилятор .NET Native устраняет это ограничение, используя уменьшение зависимости, которое удаляет ссылки на неиспользованный код.</span><span class="sxs-lookup"><span data-stu-id="f3726-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="f3726-137">Однако .NET Native может не поддерживать или генерировать некоторую информацию типа и код, когда эта информация не может быть выведена статически во время компиляции, но вместо этого получается динамически во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3726-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>

<span data-ttu-id="f3726-138">.NET Native действительно позволяет анализировать и динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="f3726-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="f3726-139">При этом, не все типы могут быть помечены для отражения, так как это сделает размер созданного кода слишком большим (особенно потому, что поддерживается отражение на общедоступных API в платформе .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="f3726-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="f3726-140">Компилятор .NET Native делает разумный выбор о том, какие типы должны поддерживать отражение, и сохраняет метаданные и генерирует код только для этих типов.</span><span class="sxs-lookup"><span data-stu-id="f3726-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>

<span data-ttu-id="f3726-141">Например, привязка данных требует, чтобы приложение обеспечивало сопоставление имен свойств с функциями.</span><span class="sxs-lookup"><span data-stu-id="f3726-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="f3726-142">В приложениях .NET для магазина Windows среда CLR автоматически использует отражение для обеспечения этой возможности для управляемых и общедоступных собственных типов.</span><span class="sxs-lookup"><span data-stu-id="f3726-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="f3726-143">В .NET Native компилятор автоматически включает метаданные для типов, к которым вы связываете данные.</span><span class="sxs-lookup"><span data-stu-id="f3726-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>

<span data-ttu-id="f3726-144">Компилятор .NET Native также может обрабатывать <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.Dictionary%602>широко используемые типы, такие как и , которые работают, не требуя никаких подсказок или директив.</span><span class="sxs-lookup"><span data-stu-id="f3726-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="f3726-145">Ключевое слово [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) также поддерживается в заданных пределах.</span><span class="sxs-lookup"><span data-stu-id="f3726-145">The [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) keyword is also supported within certain limits.</span></span>

> [!NOTE]
> <span data-ttu-id="f3726-146">При переносе приложения на .NET Native следует тщательно протестировать все динамические пути кода.</span><span class="sxs-lookup"><span data-stu-id="f3726-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>

<span data-ttu-id="f3726-147">Конфигурация по умолчанию для .NET Native достаточна для большинства разработчиков, но некоторые разработчики могут захотеть доработать свои конфигурации с помощью файла директив ый (.rd.xml).</span><span class="sxs-lookup"><span data-stu-id="f3726-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="f3726-148">Кроме того, в некоторых случаях компилятор .NET Native не может определить, какие метаданные должны быть доступны для отражения, и полагается на подсказки, особенно в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f3726-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>

- <span data-ttu-id="f3726-149">Некоторые конструкции, такие как <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> и <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> не удается определить статически.</span><span class="sxs-lookup"><span data-stu-id="f3726-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>

- <span data-ttu-id="f3726-150">Поскольку компилятор не может определить экземпляры, универсальный тип, который требуется отразить на нем должен быть указан директивами среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3726-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="f3726-151">Это необходимо не только потому, что весь код должен быть включен, но так же и вследствие того, что отражение на универсальных типах могут образовывать бесконечный цикл (например, при вызове универсального метода для универсального типа).</span><span class="sxs-lookup"><span data-stu-id="f3726-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>

> [!NOTE]
> <span data-ttu-id="f3726-152">Директивы среды выполнения определяются в файле директив среды выполнения (. rd.xml).</span><span class="sxs-lookup"><span data-stu-id="f3726-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="f3726-153">Общие сведения об использовании этого файла см. в разделе [Приступая к работе](getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="f3726-153">For general information about using this file, see [Getting Started](getting-started-with-net-native.md).</span></span> <span data-ttu-id="f3726-154">Сведения о директивах среды выполнения см. в разделе [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f3726-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>

<span data-ttu-id="f3726-155">Native .NET также включает инструменты профилирования, которые помогают разработчику определить, какие типы за пределами набора по умолчанию должны поддерживать отражение.</span><span class="sxs-lookup"><span data-stu-id="f3726-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a><span data-ttu-id="f3726-156">Другие различия, связанным с отражением</span><span class="sxs-lookup"><span data-stu-id="f3726-156">Other reflection-related differences</span></span>

<span data-ttu-id="f3726-157">Существует ряд других индивидуальных различий в поведении между .NET для приложений Магазина Windows и .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>

<span data-ttu-id="f3726-158">В .NET Родной:</span><span class="sxs-lookup"><span data-stu-id="f3726-158">In .NET Native:</span></span>

- <span data-ttu-id="f3726-159">Отражение закрытых типов и членов в библиотеке классов платформы .NET Framework не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="f3726-160">Тем не менее, можно выполнить отражение на собственных закрытых типах и членах, а также типах и членах библиотек сторонних поставщиков.</span><span class="sxs-lookup"><span data-stu-id="f3726-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>

- <span data-ttu-id="f3726-161">Свойство <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> корректно возвращает `false` для объекта <xref:System.Reflection.ParameterInfo> , который представляет возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="f3726-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="f3726-162">В приложениях .NET для магазина Windows, будет возвращено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f3726-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="f3726-163">Промежуточный язык (IL) не поддерживает это непосредственно, и интерпретация выполняется языком.</span><span class="sxs-lookup"><span data-stu-id="f3726-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>

- <span data-ttu-id="f3726-164">Открытые члены на структурах <xref:System.RuntimeFieldHandle> и <xref:System.RuntimeMethodHandle> не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f3726-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="f3726-165">Эти типы поддерживаются только для LINQ, деревьев выражений и инициализации статического массива.</span><span class="sxs-lookup"><span data-stu-id="f3726-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>

- <span data-ttu-id="f3726-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> и <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> включают скрытые члены в базовых классах и поэтому могут переопределяться без явного переопределения.</span><span class="sxs-lookup"><span data-stu-id="f3726-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="f3726-167">Это также справедливо для других методов [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) .</span><span class="sxs-lookup"><span data-stu-id="f3726-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) methods.</span></span>

- <span data-ttu-id="f3726-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>и <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> не терпят неудачу, когда вы пытаетесь создать `byref` определенные комбинации (например, массив объектов).</span><span class="sxs-lookup"><span data-stu-id="f3726-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of `byref` objects).</span></span>

- <span data-ttu-id="f3726-169">Нельзя использовать отражение для вызова членов, которые содержат параметры указателя.</span><span class="sxs-lookup"><span data-stu-id="f3726-169">You can't use reflection to invoke members that have pointer parameters.</span></span>

- <span data-ttu-id="f3726-170">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="f3726-170">You can't use reflection to get or set a pointer field.</span></span>

- <span data-ttu-id="f3726-171">Когда количество аргументов неверно и тип одного из аргументов неверен, <xref:System.ArgumentException> .NET <xref:System.Reflection.TargetParameterCountException>Native бросает вместо .</span><span class="sxs-lookup"><span data-stu-id="f3726-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>

- <span data-ttu-id="f3726-172">Обычно двоичная сериализация исключений не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="f3726-173">В результате несериализуемые объекты могут быть добавлены к словарю <xref:System.Exception.Data%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3726-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="f3726-174">Неподдерживаемые сценарии и API-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="f3726-174">Unsupported scenarios and APIs</span></span>

<span data-ttu-id="f3726-175">В следующих разделах перечислены неподдерживаемые сценарии и интерфейсы API для общей разработки, взаимодействия и таких технологий, как HTTPClient и Windows Communication Foundation (WCF):</span><span class="sxs-lookup"><span data-stu-id="f3726-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>

- [<span data-ttu-id="f3726-176">Общая разработка</span><span class="sxs-lookup"><span data-stu-id="f3726-176">General development</span></span>](#General)

- [<span data-ttu-id="f3726-177">HTTPClient</span><span class="sxs-lookup"><span data-stu-id="f3726-177">HttpClient</span></span>](#HttpClient)

- [<span data-ttu-id="f3726-178">Interop</span><span class="sxs-lookup"><span data-stu-id="f3726-178">Interop</span></span>](#Interop)

- [<span data-ttu-id="f3726-179">Неподдерживаемые API</span><span class="sxs-lookup"><span data-stu-id="f3726-179">Unsupported APIs</span></span>](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a><span data-ttu-id="f3726-180">Различия общей разработки</span><span class="sxs-lookup"><span data-stu-id="f3726-180">General development differences</span></span>

<span data-ttu-id="f3726-181">**Типы значений**</span><span class="sxs-lookup"><span data-stu-id="f3726-181">**Value types**</span></span>

- <span data-ttu-id="f3726-182">При переопределении методов <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> и <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> для типа значения не вызывайте реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="f3726-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="f3726-183">В приложениях .NET для магазина Windows эти методы основаны на отражении.</span><span class="sxs-lookup"><span data-stu-id="f3726-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="f3726-184">Во время компиляции .NET Native генерирует реализацию, которая не полагается на отражение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3726-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="f3726-185">Это означает, что если вы не переопределить эти два метода, они будут работать, как ожидалось, потому что .NET Native генерирует реализацию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="f3726-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="f3726-186">Однако, переопределение этих методов с помощью вызова реализации базового класса приводит к возникновению исключения.</span><span class="sxs-lookup"><span data-stu-id="f3726-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>

- <span data-ttu-id="f3726-187">Типы значений размером более 1 мегабайт не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f3726-187">Value types larger than 1 megabyte aren't supported.</span></span>

- <span data-ttu-id="f3726-188">Типы значений не могут иметь беспараметрыный конструктор в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-188">Value types can't have a parameterless constructor in .NET Native.</span></span> <span data-ttu-id="f3726-189">(C и Visual Basic запрещают беспараметрыные конструкторы по типам значений.</span><span class="sxs-lookup"><span data-stu-id="f3726-189">(C# and Visual Basic prohibit parameterless constructors on value types.</span></span> <span data-ttu-id="f3726-190">Тем не менее их можно создать в IL.)</span><span class="sxs-lookup"><span data-stu-id="f3726-190">However, these can be created in IL.)</span></span>

<span data-ttu-id="f3726-191">**Массивы**</span><span class="sxs-lookup"><span data-stu-id="f3726-191">**Arrays**</span></span>

- <span data-ttu-id="f3726-192">Массивы с нижней границей, отличной от нуля, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f3726-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="f3726-193">Как правило, эти массивы создаются путем вызова перегрузки <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3726-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

- <span data-ttu-id="f3726-194">Динамическое создание многомерных массивов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="f3726-195">Такие массивы обычно создаются путем вызова перегрузки метода <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> , который включает в себя параметр `lengths` , или же путем вызова метода <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3726-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="f3726-196">Многомерные массивы, имеющие четыре или более измерений не поддерживаются; т.е. их значение свойства <xref:System.Array.Rank%2A?displayProperty=nameWithType> равно или больше четырех.</span><span class="sxs-lookup"><span data-stu-id="f3726-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="f3726-197">Вместо этого используйте [ступенчатые массивы](../../csharp/programming-guide/arrays/jagged-arrays.md) (массива массивов).</span><span class="sxs-lookup"><span data-stu-id="f3726-197">Use [jagged arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="f3726-198">Например `array[x,y,z]` является недопустимым, но `array[x][y][z]` нет.</span><span class="sxs-lookup"><span data-stu-id="f3726-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>

- <span data-ttu-id="f3726-199">Вариативность для многомерных массивов не поддерживается и вызывает исключение <xref:System.InvalidCastException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3726-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>

<span data-ttu-id="f3726-200">**Универсальные шаблоны**</span><span class="sxs-lookup"><span data-stu-id="f3726-200">**Generics**</span></span>

- <span data-ttu-id="f3726-201">Расширения бесконечного универсального типа приводят к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="f3726-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="f3726-202">Например, этот код вызывает ошибку при компиляции:</span><span class="sxs-lookup"><span data-stu-id="f3726-202">For example, this code fails to compile:</span></span>

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

<span data-ttu-id="f3726-203">**Указатели**</span><span class="sxs-lookup"><span data-stu-id="f3726-203">**Pointers**</span></span>

- <span data-ttu-id="f3726-204">Массивы указателей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-204">Arrays of pointers aren't supported.</span></span>

- <span data-ttu-id="f3726-205">Чтобы получить или задать поле указателя, нельзя использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="f3726-205">You can't use reflection to get or set a pointer field.</span></span>

<span data-ttu-id="f3726-206">**Сериализация**</span><span class="sxs-lookup"><span data-stu-id="f3726-206">**Serialization**</span></span>

<span data-ttu-id="f3726-207">Атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="f3726-208">Вместо этого используйте атрибут <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> .</span><span class="sxs-lookup"><span data-stu-id="f3726-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>

<span data-ttu-id="f3726-209">**Ресурсы**</span><span class="sxs-lookup"><span data-stu-id="f3726-209">**Resources**</span></span>

<span data-ttu-id="f3726-210">Использование локализованных ресурсов с классом <xref:System.Diagnostics.Tracing.EventSource> не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="f3726-211">Свойство <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> не определяет локализованные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="f3726-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>

<span data-ttu-id="f3726-212">**Делегаты**</span><span class="sxs-lookup"><span data-stu-id="f3726-212">**Delegates**</span></span>

<span data-ttu-id="f3726-213">`Delegate.BeginInvoke` и `Delegate.EndInvoke` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f3726-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>

<span data-ttu-id="f3726-214">**Различные интерфейсы API**</span><span class="sxs-lookup"><span data-stu-id="f3726-214">**Miscellaneous APIs**</span></span>

- <span data-ttu-id="f3726-215">Свойство [TypeInfo.GUID](xref:System.Type.GUID) выбрасывает <xref:System.PlatformNotSupportedException> исключение, если <xref:System.Runtime.InteropServices.GuidAttribute> атрибут не применяется к типу.</span><span class="sxs-lookup"><span data-stu-id="f3726-215">The [TypeInfo.GUID](xref:System.Type.GUID) property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="f3726-216">Идентификатор GUID используется в основном для поддержки модели COM.</span><span class="sxs-lookup"><span data-stu-id="f3726-216">The GUID is used primarily for COM support.</span></span>

- <span data-ttu-id="f3726-217">Метод <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> правильно разбирает строки, содержащие короткие даты в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="f3726-218">Тем не менее он не поддерживает совместимость с синтаксическим анализом изменений даты и времени, описанным в статьях базы знаний Microsoft: [KB2803771](https://support.microsoft.com/kb/2803771) и [KB2803755](https://support.microsoft.com/kb/2803755).</span><span class="sxs-lookup"><span data-stu-id="f3726-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>

- <span data-ttu-id="f3726-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")` правильно округляется в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="f3726-220">В некоторых версиях среды CLR, результирующая строка усекается вместо округления.</span><span class="sxs-lookup"><span data-stu-id="f3726-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a><span data-ttu-id="f3726-221">Различия HttpClient</span><span class="sxs-lookup"><span data-stu-id="f3726-221">HttpClient differences</span></span>

<span data-ttu-id="f3726-222">В .NET Native <xref:System.Net.Http.HttpClientHandler> класс внутренне использует WinINet <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> (через класс) вместо <xref:System.Net.WebRequest> <xref:System.Net.WebResponse> классов, используемых в стандартных приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="f3726-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="f3726-223">WinINet не поддерживает все параметры конфигурации, которые поддерживает класс <xref:System.Net.Http.HttpClientHandler> .</span><span class="sxs-lookup"><span data-stu-id="f3726-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="f3726-224">В результате имеем следующее:</span><span class="sxs-lookup"><span data-stu-id="f3726-224">As a result:</span></span>

- <span data-ttu-id="f3726-225">Некоторые из свойств возможностей по <xref:System.Net.Http.HttpClientHandler> возврату `false` на .NET Native, в то время как они возвращаются `true` в стандартных .NET для приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="f3726-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>

- <span data-ttu-id="f3726-226">Некоторые аксессуары `get` к свойствам конфигурации всегда возвращают фиксированное значение на .NET Native, которое отличается от настраиваемого значения по умолчанию в приложениях .NET для Windows Store.</span><span class="sxs-lookup"><span data-stu-id="f3726-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>

<span data-ttu-id="f3726-227">В следующих подразделах описаны некоторые дополнительные различия в поведении.</span><span class="sxs-lookup"><span data-stu-id="f3726-227">Some additional behavior differences are covered in the following subsections.</span></span>

<span data-ttu-id="f3726-228">**Прокси**</span><span class="sxs-lookup"><span data-stu-id="f3726-228">**Proxy**</span></span>

<span data-ttu-id="f3726-229">Класс <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> не поддерживает настройку или переопределение прокси на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="f3726-229">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="f3726-230">Это означает, что все запросы на .NET Native используют настроенный системой прокси-сервер или не сервер прокси- и не будет, в зависимости от стоимости <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="f3726-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="f3726-231">В приложениях .NET для магазина Windows, прокси-сервер определяется свойством <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3726-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="f3726-232">На языке .NET <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> Native установление значения, не `null` подавающее <xref:System.PlatformNotSupportedException> исключение.</span><span class="sxs-lookup"><span data-stu-id="f3726-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="f3726-233">Свойство <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> `false` возвращается на .NET Native, в то время как он возвращается `true` в стандартной рамочной системе .NET для приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="f3726-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>

<span data-ttu-id="f3726-234">**Автоматическое перенаправление**</span><span class="sxs-lookup"><span data-stu-id="f3726-234">**Automatic redirection**</span></span>

<span data-ttu-id="f3726-235">Класс <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> не позволяет настроить максимальное количество автоматических перенаправлений.</span><span class="sxs-lookup"><span data-stu-id="f3726-235">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="f3726-236">Значение свойства <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> равно 50 по умолчанию в стандартных приложениях .NET для магазина Windows и может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="f3726-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="f3726-237">На .NET Native значение этого свойства составляет 10, и попытка <xref:System.PlatformNotSupportedException> изменить его выбрасывает исключение.</span><span class="sxs-lookup"><span data-stu-id="f3726-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="f3726-238">Недвижимость <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> возвращается `false` на .NET Native, `true` в то время как она возвращается в .NET для приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="f3726-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>

<span data-ttu-id="f3726-239">**Автоматическая распаковка**</span><span class="sxs-lookup"><span data-stu-id="f3726-239">**Automatic decompression**</span></span>

<span data-ttu-id="f3726-240">Приложения .NET для магазина Windows позволяют задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> на <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>или <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="f3726-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="f3726-241">.NET Родные <xref:System.Net.DecompressionMethods.Deflate> поддерживает <xref:System.Net.DecompressionMethods.GZip>только <xref:System.Net.DecompressionMethods.None>вместе с , или .</span><span class="sxs-lookup"><span data-stu-id="f3726-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="f3726-242">При попытке задать свойство <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> только на <xref:System.Net.DecompressionMethods.Deflate> или <xref:System.Net.DecompressionMethods.GZip> происходит его автоматическое задание на оба <xref:System.Net.DecompressionMethods.Deflate> и <xref:System.Net.DecompressionMethods.GZip>.</span><span class="sxs-lookup"><span data-stu-id="f3726-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>

<span data-ttu-id="f3726-243">**Файлы cookie**</span><span class="sxs-lookup"><span data-stu-id="f3726-243">**Cookies**</span></span>

<span data-ttu-id="f3726-244">Обработка файлов cookie выполняется одновременно с <xref:System.Net.Http.HttpClient> и WinINet.</span><span class="sxs-lookup"><span data-stu-id="f3726-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="f3726-245">Файлы cookie из <xref:System.Net.CookieContainer> объединяются вместе файла cookie в кэше WinINet cookie.</span><span class="sxs-lookup"><span data-stu-id="f3726-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="f3726-246">Удаление файла cookie из <xref:System.Net.CookieContainer> запрещает <xref:System.Net.Http.HttpClient> отправлять файл cookie, но если файл cookie уже был просмотрен WinINet и файлы "cookie" не были удалены пользователем, WinINet отправляет его.</span><span class="sxs-lookup"><span data-stu-id="f3726-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="f3726-247">Не существует средств программного удаления файла cookie из WinINet с использованием API <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>или <xref:System.Net.CookieContainer> .</span><span class="sxs-lookup"><span data-stu-id="f3726-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="f3726-248">Задание свойства <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> на `false` вызывает только <xref:System.Net.Http.HttpClient> , чтобы остановить отправку файлов "cookie"; WinINet может по-прежнему включить свои файлы cookie в запрос.</span><span class="sxs-lookup"><span data-stu-id="f3726-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>

<span data-ttu-id="f3726-249">**Учетные данные**</span><span class="sxs-lookup"><span data-stu-id="f3726-249">**Credentials**</span></span>

<span data-ttu-id="f3726-250">В приложениях .NET для магазина Windows свойства <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> и <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> работают независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="f3726-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="f3726-251">Кроме того, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> принимает любой объект, реализующий интерфейс <xref:System.Net.ICredentials> .</span><span class="sxs-lookup"><span data-stu-id="f3726-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="f3726-252">В .NET Native <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> настройка `true` свойства <xref:System.Net.Http.HttpClientHandler.Credentials%2A> приводит `null`к тому, что свойство становится .</span><span class="sxs-lookup"><span data-stu-id="f3726-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="f3726-253">Кроме этого, свойство <xref:System.Net.Http.HttpClientHandler.Credentials%2A> может быть задано только в `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>или объект типа <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="f3726-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="f3726-254">Назначение любого другого объекта <xref:System.Net.ICredentials> , наиболее популярный из которых <xref:System.Net.CredentialCache>, свойству <xref:System.Net.Http.HttpClientHandler.Credentials%2A> вызывает исключение <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="f3726-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="f3726-255">**Другие неподдерживаемые и ненастраиваемые функции**</span><span class="sxs-lookup"><span data-stu-id="f3726-255">**Other unsupported or unconfigurable features**</span></span>

<span data-ttu-id="f3726-256">В .NET Родной:</span><span class="sxs-lookup"><span data-stu-id="f3726-256">In .NET Native:</span></span>

- <span data-ttu-id="f3726-257">Значение свойства <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> всегда <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="f3726-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="f3726-258">В приложения .NET для магазина Windows, по умолчанию используется <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="f3726-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>

- <span data-ttu-id="f3726-259">Свойство <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> не настраивается.</span><span class="sxs-lookup"><span data-stu-id="f3726-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>

- <span data-ttu-id="f3726-260">Свойство <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> всегда имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="f3726-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="f3726-261">В приложения .NET для магазина Windows, по умолчанию используется `false`.</span><span class="sxs-lookup"><span data-stu-id="f3726-261">In .NET for Windows Store apps, the default is `false`.</span></span>

- <span data-ttu-id="f3726-262">Заголовок `SetCookie2` в ответах игнорируется как устаревший.</span><span class="sxs-lookup"><span data-stu-id="f3726-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>

<a name="Interop"></a>
### <a name="interop-differences"></a><span data-ttu-id="f3726-263">Различия взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f3726-263">Interop differences</span></span>
 <span data-ttu-id="f3726-264">**Устаревшие интерфейсы API**</span><span class="sxs-lookup"><span data-stu-id="f3726-264">**Deprecated APIs**</span></span>

 <span data-ttu-id="f3726-265">Не рекомендуется использовать несколько редко применяемых API-интерфейсов для взаимодействия с управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="f3726-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="f3726-266">При использовании с .NET Native эти <xref:System.NotImplementedException> <xref:System.PlatformNotSupportedException> AI могут выбросить или за исключением или привести к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="f3726-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="f3726-267">В приложениях .NET для магазина Windows эти API-интерфейсы отмечены как устаревшие, хотя их вызов создает предупреждение компилятора, а не ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="f3726-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>

 <span data-ttu-id="f3726-268">Удручающие AIS `VARIANT` для маршалинга включают:</span><span class="sxs-lookup"><span data-stu-id="f3726-268">Deprecated APIs for `VARIANT` marshaling include:</span></span>

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <span data-ttu-id="f3726-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>поддерживается, но в некоторых сценариях, например, при использовании `byref` [iDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) или вариантов, он выбрасывает исключение.</span><span class="sxs-lookup"><span data-stu-id="f3726-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or `byref` variants.</span></span>

 <span data-ttu-id="f3726-270">Утомленные AI для поддержки [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) включают:</span><span class="sxs-lookup"><span data-stu-id="f3726-270">Deprecated APIs for [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support include:</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

<span data-ttu-id="f3726-271">Утомленные AIS для классических событий COM включают в себя:</span><span class="sxs-lookup"><span data-stu-id="f3726-271">Deprecated APIs for classic COM events include:</span></span>

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

<span data-ttu-id="f3726-272">Утомленные AIS <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> в интерфейсе, который не поддерживается в .NET Native, включают:</span><span class="sxs-lookup"><span data-stu-id="f3726-272">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native, include:</span></span>

- <span data-ttu-id="f3726-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="f3726-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="f3726-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="f3726-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="f3726-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="f3726-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

<span data-ttu-id="f3726-276">Другие неподдерживаемые функции интерпа включают в себя:</span><span class="sxs-lookup"><span data-stu-id="f3726-276">Other unsupported interop features include:</span></span>

- <span data-ttu-id="f3726-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="f3726-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="f3726-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (все члены)</span><span class="sxs-lookup"><span data-stu-id="f3726-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 <span data-ttu-id="f3726-279">Редко используемые apIs- маршалинг:</span><span class="sxs-lookup"><span data-stu-id="f3726-279">Rarely used marshaling APIs:</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 <span data-ttu-id="f3726-280">**Вызов неуправляемого кода и совместимость взаимодействия COM**</span><span class="sxs-lookup"><span data-stu-id="f3726-280">**Platform invoke and COM interop compatibility**</span></span>

 <span data-ttu-id="f3726-281">Большинство сценариев поддержки платформы и com interop по-прежнему поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-281">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="f3726-282">В частности, поддерживаются все взаимодействия с API среды выполнения Windows (WinRT) и весь необходимый маршалинг для среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="f3726-282">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="f3726-283">Это включает поддержку маршалинга:</span><span class="sxs-lookup"><span data-stu-id="f3726-283">This includes marshaling support for:</span></span>

- <span data-ttu-id="f3726-284">Массивы (включая <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="f3726-284">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>

- `BStr`

- <span data-ttu-id="f3726-285">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f3726-285">Delegates</span></span>

- <span data-ttu-id="f3726-286">Строки (Юникод, Ansi и HSTRING)</span><span class="sxs-lookup"><span data-stu-id="f3726-286">Strings (Unicode, Ansi, and HSTRING)</span></span>

- <span data-ttu-id="f3726-287">Структуры (`byref` и `byval`)</span><span class="sxs-lookup"><span data-stu-id="f3726-287">Structs (`byref` and `byval`)</span></span>

- <span data-ttu-id="f3726-288">Объединения</span><span class="sxs-lookup"><span data-stu-id="f3726-288">Unions</span></span>

- <span data-ttu-id="f3726-289">Дескрипторы Win32</span><span class="sxs-lookup"><span data-stu-id="f3726-289">Win32 handles</span></span>

- <span data-ttu-id="f3726-290">Все конструкции WinRT</span><span class="sxs-lookup"><span data-stu-id="f3726-290">All WinRT constructs</span></span>

- <span data-ttu-id="f3726-291">Частичная поддержка маршалинга типов variant.</span><span class="sxs-lookup"><span data-stu-id="f3726-291">Partial support for marshaling variant types.</span></span> <span data-ttu-id="f3726-292">Поддерживаются следующие конструкции:</span><span class="sxs-lookup"><span data-stu-id="f3726-292">The following are supported:</span></span>

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [<span data-ttu-id="f3726-293">Iunknown</span><span class="sxs-lookup"><span data-stu-id="f3726-293">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

<span data-ttu-id="f3726-294">Тем не менее, .NET Native не поддерживает следующее:</span><span class="sxs-lookup"><span data-stu-id="f3726-294">However, .NET Native doesn't support the following:</span></span>

- <span data-ttu-id="f3726-295">использование классических COM-событий</span><span class="sxs-lookup"><span data-stu-id="f3726-295">Using classic COM events</span></span>

- <span data-ttu-id="f3726-296">Реализация интерфейса <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> на управляемом типе</span><span class="sxs-lookup"><span data-stu-id="f3726-296">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>

- <span data-ttu-id="f3726-297">Реализация интерфейса [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) в управляемом типе через атрибут <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3726-297">Implementing the [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="f3726-298">Тем не менее, вы не `IDispatch`можете вызвать объекты `IDispatch`COM через, и управляемый объект не может реализовать.</span><span class="sxs-lookup"><span data-stu-id="f3726-298">However, you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>

<span data-ttu-id="f3726-299">Использование отражения для вызова метода неуправляемого кода не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f3726-299">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="f3726-300">Это ограничение можно обойти путем заключения вызова метода в другой метод, вместо этого используя вызов оболочки.</span><span class="sxs-lookup"><span data-stu-id="f3726-300">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="f3726-301">Другие отличия от API-интерфейсов приложений .NET для магазина Windows</span><span class="sxs-lookup"><span data-stu-id="f3726-301">Other differences from .NET APIs for Windows Store apps</span></span>

<span data-ttu-id="f3726-302">В этом разделе перечислены оставшиеся AA, которые не поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-302">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="f3726-303">Самый большой набор неподдерживаемых AI – это AI- компаний Фонда коммуникаций Windows (WCF).</span><span class="sxs-lookup"><span data-stu-id="f3726-303">The largest set of the unsupported APIs is the Windows Communication Foundation (WCF) APIs.</span></span>

<span data-ttu-id="f3726-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="f3726-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>

<span data-ttu-id="f3726-305">Типы в <xref:System.ComponentModel.DataAnnotations> <xref:System.ComponentModel.DataAnnotations.Schema> пространстве и пространстве имен не поддерживаются в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-305">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="f3726-306">К ним относятся следующие типы, которые присутствуют в .NET для приложений Магазина Windows для Windows 8:</span><span class="sxs-lookup"><span data-stu-id="f3726-306">These include the following types that are present in .NET for Windows Store apps for Windows 8:</span></span>

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 <span data-ttu-id="f3726-307">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="f3726-307">**Visual Basic**</span></span>

<span data-ttu-id="f3726-308">Visual Basic в настоящее время не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-308">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="f3726-309">Следующие типы <xref:Microsoft.VisualBasic> <xref:Microsoft.VisualBasic.CompilerServices> в пространстве имен недоступны в .NET Native:</span><span class="sxs-lookup"><span data-stu-id="f3726-309">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

<span data-ttu-id="f3726-310">**Контекст отражения (пространство имен System.Reflection.Context)**</span><span class="sxs-lookup"><span data-stu-id="f3726-310">**Reflection Context (System.Reflection.Context namespace)**</span></span>

<span data-ttu-id="f3726-311">Класс <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-311">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>

<span data-ttu-id="f3726-312">**Часы реального времени (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="f3726-312">**RTC (System.Net.Http.Rtc)**</span></span>

<span data-ttu-id="f3726-313">Класс `System.Net.Http.RtcRequestFactory` не поддерживается в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-313">The `System.Net.Http.RtcRequestFactory` class isn't supported in .NET Native.</span></span>

<span data-ttu-id="f3726-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="f3726-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>

<span data-ttu-id="f3726-315">Типы в [пространствах имен System.ServiceModel.'](xref:System.ServiceModel) не поддерживаются в языках .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f3726-315">The types in the [System.ServiceModel.\* namespaces](xref:System.ServiceModel) aren't supported in .NET Native.</span></span> <span data-ttu-id="f3726-316">К ним относятся следующие типы:</span><span class="sxs-lookup"><span data-stu-id="f3726-316">These include the following types:</span></span>

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a><span data-ttu-id="f3726-317">Различия в сериализаторах</span><span class="sxs-lookup"><span data-stu-id="f3726-317">Differences in serializers</span></span>

<span data-ttu-id="f3726-318">Существуют следующие различия, касающиеся сериализации и десериализации с классами <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="f3726-318">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>

- <span data-ttu-id="f3726-319">В .NET <xref:System.Runtime.Serialization.DataContractSerializer> Native <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> и не могут сериализировать или десеризировать производный класс с базовым классом, тип которого не является типом корневой сериализации.</span><span class="sxs-lookup"><span data-stu-id="f3726-319">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="f3726-320">Например, в следующем коде при сериализации или десериализации `Y` возникает ошибка:</span><span class="sxs-lookup"><span data-stu-id="f3726-320">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  <span data-ttu-id="f3726-321">Тип `InnerType` не известен сериализатору, так как члены базового класса не передаются во время сериализации.</span><span class="sxs-lookup"><span data-stu-id="f3726-321">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>

- <span data-ttu-id="f3726-322"><xref:System.Runtime.Serialization.DataContractSerializer> и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> не удается сериализовать класс или структуру, которая реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="f3726-322"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f3726-323">Например, не удается сериализовать или десериализовать следующие типы:</span><span class="sxs-lookup"><span data-stu-id="f3726-323">For example, the following types fail to serialize or deserialize:</span></span>

- <span data-ttu-id="f3726-324"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализовать следующие значения объекта, так как он не знает точный тип объекта для сериализации:</span><span class="sxs-lookup"><span data-stu-id="f3726-324"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>

- <span data-ttu-id="f3726-325"><xref:System.Xml.Serialization.XmlSerializer> не удается сериализация или десериализация, если тип сериализованного объекта <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="f3726-325"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>

- <span data-ttu-id="f3726-326">Все сериализаторам (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>и <xref:System.Xml.Serialization.XmlSerializer>) не удается создать код сериализации для типа <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> или типа, содержащего <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f3726-326">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="f3726-327">Вместо этого они отображают ошибки во время построения.</span><span class="sxs-lookup"><span data-stu-id="f3726-327">They display build-time errors instead.</span></span>

- <span data-ttu-id="f3726-328">Следующие конструкторы типов сериализации не обязательно работают, как должны:</span><span class="sxs-lookup"><span data-stu-id="f3726-328">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <span data-ttu-id="f3726-329"><xref:System.Xml.Serialization.XmlSerializer> не удается создать код для типа, который содержит методы, определенные любым из следующих атрибутов:</span><span class="sxs-lookup"><span data-stu-id="f3726-329"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <span data-ttu-id="f3726-330"><xref:System.Xml.Serialization.XmlSerializer> не поддерживает настраиваемый интерфейс сериализации <xref:System.Xml.Serialization.IXmlSerializable> .</span><span class="sxs-lookup"><span data-stu-id="f3726-330"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="f3726-331">Если имеется класс, реализующий этот интерфейс, <xref:System.Xml.Serialization.XmlSerializer> рассматривает тип, как тип объекта (POCO) простой старой среды CLR и сериализует только его открытые свойства.</span><span class="sxs-lookup"><span data-stu-id="f3726-331">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>

- <span data-ttu-id="f3726-332">Сериализация простого <xref:System.Exception> объекта не работает <xref:System.Runtime.Serialization.DataContractSerializer> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>хорошо с и .</span><span class="sxs-lookup"><span data-stu-id="f3726-332">Serializing a plain <xref:System.Exception> object doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<a name="VS"></a>

## <a name="visual-studio-differences"></a><span data-ttu-id="f3726-333">Различия в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3726-333">Visual Studio differences</span></span>

<span data-ttu-id="f3726-334">**Исключения и отладка**</span><span class="sxs-lookup"><span data-stu-id="f3726-334">**Exceptions and debugging**</span></span>

<span data-ttu-id="f3726-335">При запуске приложений, компилированных с помощью .NET Native в отладчике, исключения первого шанса включены для следующих типов исключений:</span><span class="sxs-lookup"><span data-stu-id="f3726-335">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

<span data-ttu-id="f3726-336">**Создание приложений**</span><span class="sxs-lookup"><span data-stu-id="f3726-336">**Building apps**</span></span>

<span data-ttu-id="f3726-337">Используйте средства построения x 86, которые используются по умолчанию в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f3726-337">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="f3726-338">Не рекомендуется использование средств AMD64 MSBuild, которые находятся в C:\Program Files (x86)\MSBuild\12.0\bin\amd64; Это может создать проблемы построения.</span><span class="sxs-lookup"><span data-stu-id="f3726-338">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>

<span data-ttu-id="f3726-339">**Профилировщики**</span><span class="sxs-lookup"><span data-stu-id="f3726-339">**Profilers**</span></span>

- <span data-ttu-id="f3726-340">Профилировщик ЦП в Visual Studio и профилировщик памяти XAML неправильно отображают «только мой код».</span><span class="sxs-lookup"><span data-stu-id="f3726-340">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>

- <span data-ttu-id="f3726-341">Профилировщик памяти XAML неточно отображает данные управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="f3726-341">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>

- <span data-ttu-id="f3726-342">Профилировщик ЦП неправильно идентифицирует модули и отображает имена функций с префиксами.</span><span class="sxs-lookup"><span data-stu-id="f3726-342">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>

<span data-ttu-id="f3726-343">**Проекты модульных тестов библиотеки**</span><span class="sxs-lookup"><span data-stu-id="f3726-343">**Unit Test Library projects**</span></span>

<span data-ttu-id="f3726-344">Включение .NET Native в библиотеку модульных тестов для проекта приложений Магазина Windows не поддерживается и приводит к неудаче проекта.</span><span class="sxs-lookup"><span data-stu-id="f3726-344">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3726-345">См. также</span><span class="sxs-lookup"><span data-stu-id="f3726-345">See also</span></span>

- [<span data-ttu-id="f3726-346">Начало работы</span><span class="sxs-lookup"><span data-stu-id="f3726-346">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="f3726-347">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="f3726-347">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="f3726-348">обзор приложений Магазина Windows .NET</span><span class="sxs-lookup"><span data-stu-id="f3726-348">.NET For Windows Store apps overview</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [<span data-ttu-id="f3726-349">Поддержка приложений для Магазина Windows и среды выполнения Windows в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f3726-349">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
