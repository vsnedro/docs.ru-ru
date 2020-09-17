---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656352"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="2ab11-101">В приложениях WinForms и WPF используется Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="2ab11-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="2ab11-102">Приложения Windows Forms и Windows Presentation Framework (WPF) теперь используют пакет SDK для .NET (`Microsoft.NET.Sdk`) вместо .NET Core WinForms и пакета SDK WPF (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="2ab11-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="2ab11-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="2ab11-103">Change description</span></span>

<span data-ttu-id="2ab11-104">В предыдущих версиях .NET Core в приложениях WinForms и WPF использовался отдельный [пакет SDK проекта](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="2ab11-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="2ab11-105">Начиная с .NET 5.0 пакет SDK WinForms и WPF был объединен с пакетом SDK для .NET (`Microsoft.NET.Sdk`).</span><span class="sxs-lookup"><span data-stu-id="2ab11-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="2ab11-106">Кроме того, новые [моникеры целевой платформы (TFM)](../../../../docs/standard/frameworks.md) заменяют собой `netcoreapp` и `netstandard` в .NET 5.</span><span class="sxs-lookup"><span data-stu-id="2ab11-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="2ab11-107">В следующем примере показаны изменения, которые необходимо внести для файла проекта WPF при изменении целевой платформы на .NET 5.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="2ab11-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="2ab11-108">В предыдущих версиях .NET Core:</span><span class="sxs-lookup"><span data-stu-id="2ab11-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2ab11-109">В .NET 5.0 и более поздних версиях:</span><span class="sxs-lookup"><span data-stu-id="2ab11-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="2ab11-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="2ab11-110">Version introduced</span></span>

<span data-ttu-id="2ab11-111">Предварительная версия 8 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2ab11-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2ab11-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="2ab11-112">Recommended action</span></span>

<span data-ttu-id="2ab11-113">В файле проекта WPF или Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="2ab11-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="2ab11-114">Измените атрибут `Sdk` на `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="2ab11-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="2ab11-115">Установите для свойства `TargetFramework` значение `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="2ab11-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="2ab11-116">Категория</span><span class="sxs-lookup"><span data-stu-id="2ab11-116">Category</span></span>

- <span data-ttu-id="2ab11-117">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ab11-117">Windows Forms</span></span>
- <span data-ttu-id="2ab11-118">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="2ab11-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2ab11-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2ab11-119">Affected APIs</span></span>

<span data-ttu-id="2ab11-120">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="2ab11-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
