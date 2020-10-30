---
ms.openlocfilehash: 959d8cb6d3e52916f6777054f3e9b327dc8edb4e
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434968"
---
### <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="38481-101">API глобального кэша сборок устарели</span><span class="sxs-lookup"><span data-stu-id="38481-101">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="38481-102">В .NET Core и .NET 5.0 и более поздних версий больше не используется концепция глобального кэша сборок, которая присутствует в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38481-102">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="38481-103">Таким образом, все API .NET Core и .NET 5 и более поздних версий, которые используют глобальный кэш сборок, либо завершают работу сбоем, либо не выполняют никаких действий.</span><span class="sxs-lookup"><span data-stu-id="38481-103">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="38481-104">Чтобы помочь разработчикам отказаться от этих API, некоторые связанные с глобальным кэшем сборок API были помечены как устаревшие и во время компиляции приводят к созданию предупреждения `SYSLIB0005`.</span><span class="sxs-lookup"><span data-stu-id="38481-104">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="38481-105">В последующей версии .NET эти API могут быть исключены.</span><span class="sxs-lookup"><span data-stu-id="38481-105">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="38481-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="38481-106">Change description</span></span>

<span data-ttu-id="38481-107">Следующие API помечены как устаревшие.</span><span class="sxs-lookup"><span data-stu-id="38481-107">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="38481-108">API</span><span class="sxs-lookup"><span data-stu-id="38481-108">API</span></span> | <span data-ttu-id="38481-109">Версия, в которой API помечен как устаревший...</span><span class="sxs-lookup"><span data-stu-id="38481-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="38481-110">5.0 (RC1)</span><span class="sxs-lookup"><span data-stu-id="38481-110">5.0 RC1</span></span> |

<span data-ttu-id="38481-111">В .NET Framework версий с 2.x по 4.x свойство <xref:System.Reflection.Assembly.GlobalAssemblyCache> возвращает `true`, если запрашиваемая сборка была загружена из глобального кэша сборок, и `false`, если она была загружена из другого места на диске.</span><span class="sxs-lookup"><span data-stu-id="38481-111">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="38481-112">В .NET Core версий с 2.x по 3.x свойство <xref:System.Reflection.Assembly.GlobalAssemblyCache> всегда возвращает `false`, указывая, что глобальный кэш сборок в .NET Core не существует.</span><span class="sxs-lookup"><span data-stu-id="38481-112">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="38481-113">В .NET 5.0 и более поздних версий свойство <xref:System.Reflection.Assembly.GlobalAssemblyCache> также возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="38481-113">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="38481-114">Тем не менее, метод получения для этого свойства также помечен как устаревший. Таким образом, вызывающие объекты информируются, что им не следует в дальнейшем использовать это свойство.</span><span class="sxs-lookup"><span data-stu-id="38481-114">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="38481-115">Библиотеки и приложения не должны использовать API <xref:System.Reflection.Assembly.GlobalAssemblyCache> для определения поведения во время выполнения, так как в .NET Core и .NET 5.0 и более поздних версий он всегда возвращает `false`.</span><span class="sxs-lookup"><span data-stu-id="38481-115">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="38481-116">Это изменение происходит только во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="38481-116">This is a compile-time only change.</span></span> <span data-ttu-id="38481-117">Относительно предыдущих версий .NET Core во время выполнения нет никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="38481-117">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="38481-118">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="38481-118">Reason for change</span></span>

<span data-ttu-id="38481-119">В .NET Core и .NET 5.0 более не используется концепция глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="38481-119">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="38481-120">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="38481-120">Version introduced</span></span>

<span data-ttu-id="38481-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="38481-121">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="38481-122">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="38481-122">Recommended action</span></span>

- <span data-ttu-id="38481-123">Если приложение запрашивает свойство <xref:System.Reflection.Assembly.GlobalAssemblyCache>, рассмотрите возможность удалить вызов.</span><span class="sxs-lookup"><span data-stu-id="38481-123">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="38481-124">Если вы используете значение <xref:System.Reflection.Assembly.GlobalAssemblyCache> для выбора между потоками сборки в глобальном кэше сборок и вне него во время выполнения, еще раз оцените, требуется ли такой поток по-прежнему в приложении .NET Core или .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="38481-124">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="38481-125">Если вам по-прежнему требуется вызывать устаревшие API, вы можете отключить предупреждение `SYSLIB0005` в коде.</span><span class="sxs-lookup"><span data-stu-id="38481-125">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="38481-126">Также вы можете отключить это предупреждение в файле проекта, что приведет к его отключению для всех исходных файлов в проекте.</span><span class="sxs-lookup"><span data-stu-id="38481-126">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="38481-127">В случае отключения `SYSLIB0005` будет отключено только предупреждение об устаревшем элементе <xref:System.Reflection.Assembly.GlobalAssemblyCache>.</span><span class="sxs-lookup"><span data-stu-id="38481-127">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="38481-128">Другие предупреждения не отключаются.</span><span class="sxs-lookup"><span data-stu-id="38481-128">It does not disable any other warnings.</span></span>

#### <a name="category"></a><span data-ttu-id="38481-129">Категория</span><span class="sxs-lookup"><span data-stu-id="38481-129">Category</span></span>

<span data-ttu-id="38481-130">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="38481-130">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="38481-131">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="38481-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
