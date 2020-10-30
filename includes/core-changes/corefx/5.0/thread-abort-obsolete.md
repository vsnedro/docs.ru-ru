---
ms.openlocfilehash: ee67b32b093ebd42f8ac685b34b12f2f6833be86
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92332937"
---
### <a name="threadabort-is-obsolete"></a><span data-ttu-id="f6a50-101">Thread.Abort устарел</span><span class="sxs-lookup"><span data-stu-id="f6a50-101">Thread.Abort is obsolete</span></span>

<span data-ttu-id="f6a50-102">API <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="f6a50-102">The <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> APIs are obsolete.</span></span> <span data-ttu-id="f6a50-103">В проектах, предназначенных для .NET 5.0 или более поздней версии, можно столкнуться с предупреждениями во время компиляции `SYSLIB0006` при вызове этих методов.</span><span class="sxs-lookup"><span data-stu-id="f6a50-103">Projects that target .NET 5.0 or a later version will encounter compile-time warning `SYSLIB0006` if these methods are called.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f6a50-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="f6a50-104">Change description</span></span>

<span data-ttu-id="f6a50-105">Ранее вызовы <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> не создавали предупреждения во время компиляции, однако метод вызывал <xref:System.PlatformNotSupportedException> во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f6a50-105">Previously, calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> did not produce compile-time warnings, however, the method did throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="f6a50-106">Начиная с .NET 5.0 <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> помечен как устаревший с отображением соответствующего предупреждения.</span><span class="sxs-lookup"><span data-stu-id="f6a50-106">Starting in .NET 5.0, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is marked obsolete as warning.</span></span> <span data-ttu-id="f6a50-107">При вызове этого метода выдается предупреждение компилятора `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="f6a50-107">Calling this method produces compiler warning `SYSLIB0006`.</span></span> <span data-ttu-id="f6a50-108">Реализация метода остается неизменной, и по-прежнему возникнет исключение <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="f6a50-108">The implementation of the method is unchanged, and it continues to throw a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f6a50-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="f6a50-109">Reason for change</span></span>

<span data-ttu-id="f6a50-110">Учитывая, что <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> всегда создает <xref:System.PlatformNotSupportedException> для всех реализаций .NET, кроме .NET Framework, был добавлен в метод <xref:System.ObsoleteAttribute>, чтобы привлечь внимание к местам, где он вызывается.</span><span class="sxs-lookup"><span data-stu-id="f6a50-110">Given that <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> always throws a <xref:System.PlatformNotSupportedException> on all .NET implementations except .NET Framework, <xref:System.ObsoleteAttribute> was added to the method to draw attention to places where it's called.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f6a50-111">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="f6a50-111">Version introduced</span></span>

<span data-ttu-id="f6a50-112">5.0 RC 1</span><span class="sxs-lookup"><span data-stu-id="f6a50-112">5.0 RC 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f6a50-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="f6a50-113">Recommended action</span></span>

- <span data-ttu-id="f6a50-114">Используйте <xref:System.Threading.CancellationToken>, чтобы прервать обработку единицы работы вместо вызова <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6a50-114">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f6a50-115">В следующем примере демонстрируется применение <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="f6a50-115">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  <span data-ttu-id="f6a50-116">Подробные сведения см. в статье [Отмена в управляемых потоках](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="f6a50-116">For more information, see [Cancellation in managed threads](../../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>

- <span data-ttu-id="f6a50-117">Чтобы отключить предупреждение во время компиляции, отключите код предупреждения `SYSLIB0006`.</span><span class="sxs-lookup"><span data-stu-id="f6a50-117">To suppress the compile-time warning, suppress warning code `SYSLIB0006`.</span></span> <span data-ttu-id="f6a50-118">Код предупреждения относится только к <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, и подавление не влияет на другие предупреждения об устаревании в коде.</span><span class="sxs-lookup"><span data-stu-id="f6a50-118">The warning code is specific to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> and suppressing it doesn't suppress other obsoletion warnings in your code.</span></span> <span data-ttu-id="f6a50-119">Однако рекомендуется удалить вызовы <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> вместо того, чтобы подавлять предупреждение.</span><span class="sxs-lookup"><span data-stu-id="f6a50-119">However, we recommend that you remove calls to <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> instead of suppressing the warning.</span></span>

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  <span data-ttu-id="f6a50-120">Предупреждение можно также отключить в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f6a50-120">You can also suppress the warning in the project file.</span></span>

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="f6a50-121">Категория</span><span class="sxs-lookup"><span data-stu-id="f6a50-121">Category</span></span>

- <span data-ttu-id="f6a50-122">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="f6a50-122">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f6a50-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f6a50-123">Affected APIs</span></span>

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
