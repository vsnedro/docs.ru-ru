---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679007"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="b72fb-101">Свойству OutputType задано значение WinExe для приложений WPF и WinForms</span><span class="sxs-lookup"><span data-stu-id="b72fb-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="b72fb-102">Свойству `OutputType` автоматически задано значение `WinExe` для приложений Windows Presentation Foundation (WPF) и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b72fb-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="b72fb-103">Если свойство `OutputType` имеет значение `WinExe`, окно консоли не открывается при выполнении приложения.</span><span class="sxs-lookup"><span data-stu-id="b72fb-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b72fb-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b72fb-104">Change description</span></span>

<span data-ttu-id="b72fb-105">В предыдущих версиях .NET используется значение, указанное для `OutputType` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b72fb-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="b72fb-106">Пример:</span><span class="sxs-lookup"><span data-stu-id="b72fb-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="b72fb-107">Начиная с .NET 5.0 свойству `OutputType` автоматически задается значение `WinExe` для приложений WPF и Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b72fb-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="b72fb-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="b72fb-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="b72fb-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b72fb-109">Reason for change</span></span>

<span data-ttu-id="b72fb-110">Предполагается, что большинство пользователей не хотят, чтобы окно консоли открывалось при выполнении приложения WPF или Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b72fb-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="b72fb-111">Кроме того, [поскольку теперь эти типы приложений используют пакет SDK для .NET](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) вместо пакета SDK для Windows Desktop, будет задано правильное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b72fb-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="b72fb-112">При добавлении поддержки для использования iOS и Android в качестве целевых платформ будет проще работать с несколькими платформами, если все они используют один и тот же тип выходных данных.</span><span class="sxs-lookup"><span data-stu-id="b72fb-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b72fb-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b72fb-113">Version introduced</span></span>

<span data-ttu-id="b72fb-114">Предварительная версия 8 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="b72fb-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b72fb-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b72fb-115">Recommended action</span></span>

<span data-ttu-id="b72fb-116">Никаких действий выполнять не требуется.</span><span class="sxs-lookup"><span data-stu-id="b72fb-116">No action is required in your part.</span></span> <span data-ttu-id="b72fb-117">Однако если вы хотите восстановить старое поведение, задайте свойству `DisableWinExeOutputInference` значение `true` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="b72fb-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="b72fb-118">Категория</span><span class="sxs-lookup"><span data-stu-id="b72fb-118">Category</span></span>

- <span data-ttu-id="b72fb-119">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b72fb-119">Windows Forms</span></span>
- <span data-ttu-id="b72fb-120">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="b72fb-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b72fb-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b72fb-121">Affected APIs</span></span>

<span data-ttu-id="b72fb-122">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="b72fb-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
