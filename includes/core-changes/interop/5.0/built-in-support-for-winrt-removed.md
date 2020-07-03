---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365661"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="48437-101">Из .NET удалена встроенная поддержка WinRT</span><span class="sxs-lookup"><span data-stu-id="48437-101">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="48437-102">Из .NET удалена встроенная поддержка использования [API-интерфейсов в среде выполнения Windows (WinRT)](/uwp/winrt-cref/winrt-type-system).</span><span class="sxs-lookup"><span data-stu-id="48437-102">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="48437-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="48437-103">Version introduced</span></span>

<span data-ttu-id="48437-104">5.0, предварительная версия 6</span><span class="sxs-lookup"><span data-stu-id="48437-104">5.0 Preview 6</span></span>

#### <a name="change-description"></a><span data-ttu-id="48437-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="48437-105">Change description</span></span>

<span data-ttu-id="48437-106">Ранее CoreCLR поддерживал использование [файлов метаданных Windows (WinMD)](/uwp/winrt-cref/winmd-files) для активации и использования типов WinRT.</span><span class="sxs-lookup"><span data-stu-id="48437-106">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="48437-107">Начиная с версии .NET 5.0 поддержка прямого использования файлов WinMD в CoreCLR прекращена.</span><span class="sxs-lookup"><span data-stu-id="48437-107">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="48437-108">При попытке добавить ссылку на неподдерживаемую сборку отображается <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="48437-108">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="48437-109">При активации класса WinRT отображается <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="48437-109">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="48437-110">Это критическое изменение добавлено по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="48437-110">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="48437-111">Таким образом, разрабатывать и совершенствовать WinRT можно отдельно от среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="48437-111">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="48437-112">Для симметрии с системами взаимодействия, которые предоставляются для других операционных систем, таких как iOS и Android.</span><span class="sxs-lookup"><span data-stu-id="48437-112">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="48437-113">Для использования преимуществ других функций .NET, таких как функции C#, компоновка промежуточного языка (IL) и компиляция перед выполнением.</span><span class="sxs-lookup"><span data-stu-id="48437-113">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="48437-114">Для упрощения базы кода в среде выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="48437-114">To simplify the .NET runtime codebase.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="48437-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="48437-115">Recommended action</span></span>

- <span data-ttu-id="48437-116">Удалите ссылки на [пакет Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) и замените их ссылками на [пакет Microsoft.Windows.SDK.NET](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span><span class="sxs-lookup"><span data-stu-id="48437-116">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) and replace them with references to the [Microsoft.Windows.SDK.NET package](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span></span>

- <span data-ttu-id="48437-117">Используйте цепочку инструментов [C#/WinRT](/windows/uwp/csharp-winrt/) для создания или настройки API-интерфейсов и типов WinRT в .NET 5.0 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="48437-117">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types in .NET 5.0 and later versions.</span></span>

#### <a name="category"></a><span data-ttu-id="48437-118">Категория</span><span class="sxs-lookup"><span data-stu-id="48437-118">Category</span></span>

<span data-ttu-id="48437-119">Interop</span><span class="sxs-lookup"><span data-stu-id="48437-119">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="48437-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="48437-120">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
