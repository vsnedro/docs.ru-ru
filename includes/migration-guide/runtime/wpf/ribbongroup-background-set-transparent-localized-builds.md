---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496693"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="25b79-101">В локализованных сборках для RibbonGroup устанавливается прозрачный фон</span><span class="sxs-lookup"><span data-stu-id="25b79-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="25b79-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="25b79-102">Details</span></span>

<span data-ttu-id="25b79-103">Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="25b79-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="25b79-104">Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, благодаря чему гарантируется выбор правильной кисти.</span><span class="sxs-lookup"><span data-stu-id="25b79-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="25b79-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="25b79-105">Suggestion</span></span>

<span data-ttu-id="25b79-106">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="25b79-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="25b79-107">name</span><span class="sxs-lookup"><span data-stu-id="25b79-107">Name</span></span>    | <span data-ttu-id="25b79-108">Значение</span><span class="sxs-lookup"><span data-stu-id="25b79-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="25b79-109">Область</span><span class="sxs-lookup"><span data-stu-id="25b79-109">Scope</span></span>   |<span data-ttu-id="25b79-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="25b79-110">Edge</span></span>|
|<span data-ttu-id="25b79-111">Version</span><span class="sxs-lookup"><span data-stu-id="25b79-111">Version</span></span>|<span data-ttu-id="25b79-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="25b79-112">4.6.2</span></span>|
|<span data-ttu-id="25b79-113">Type</span><span class="sxs-lookup"><span data-stu-id="25b79-113">Type</span></span>|<span data-ttu-id="25b79-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="25b79-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="25b79-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="25b79-115">Affected APIs</span></span>

<span data-ttu-id="25b79-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="25b79-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
