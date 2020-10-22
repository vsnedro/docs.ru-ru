---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159497"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="b0f32-101">Значение TargetFramework изменено с netcoreapp на net</span><span class="sxs-lookup"><span data-stu-id="b0f32-101">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="b0f32-102">Значение свойства MSBuild `TargetFramework` изменено с `netcoreapp3.1` на `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="b0f32-102">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="b0f32-103">Это может привести к ошибкам в коде, который основан на анализе значения `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="b0f32-103">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b0f32-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b0f32-104">Version introduced</span></span>

<span data-ttu-id="b0f32-105">5.0</span><span class="sxs-lookup"><span data-stu-id="b0f32-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="b0f32-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b0f32-106">Change description</span></span>

<span data-ttu-id="b0f32-107">В версиях .NET Core с 1.0 по 3.1 значение свойства MSBuild `TargetFramework` начинается с `netcoreapp`, например `netcoreapp3.1` для приложений, предназначенных для платформы .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b0f32-107">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="b0f32-108">Начиная с версии .NET 5.0 это значение упрощено и начинается с `net`, например `net5.0` для .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="b0f32-108">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="b0f32-109">Дополнительные сведения см. в разделе [Будущее .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) и [Имена целевых платформ в .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="b0f32-109">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b0f32-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="b0f32-110">Reason for change</span></span>

- <span data-ttu-id="b0f32-111">Упрощает значение `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="b0f32-111">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="b0f32-112">Позволяет включать `TargetPlatform` в свойство `TargetFramework` в проектах.</span><span class="sxs-lookup"><span data-stu-id="b0f32-112">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b0f32-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b0f32-113">Recommended action</span></span>

<span data-ttu-id="b0f32-114">Если вы используете логику, в которой выполняется синтаксический анализ значения `TargetFramework`, необходимо обновить ее.</span><span class="sxs-lookup"><span data-stu-id="b0f32-114">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="b0f32-115">Например, в следующем условии MSBuild используется значение `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="b0f32-115">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="b0f32-116">В соответствии с этим требованием можно обновить код, чтобы сравнить идентификатор целевой платформы.</span><span class="sxs-lookup"><span data-stu-id="b0f32-116">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a><span data-ttu-id="b0f32-117">Категория</span><span class="sxs-lookup"><span data-stu-id="b0f32-117">Category</span></span>

<span data-ttu-id="b0f32-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="b0f32-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b0f32-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b0f32-119">Affected APIs</span></span>

<span data-ttu-id="b0f32-120">Н/Д</span><span class="sxs-lookup"><span data-stu-id="b0f32-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
