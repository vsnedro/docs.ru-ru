---
ms.openlocfilehash: a3ba42868577ac20ea2e082f90fc4973a1bfe108
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622379"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="3c952-101">В локализованных сборках для RibbonGroup устанавливается прозрачный фон</span><span class="sxs-lookup"><span data-stu-id="3c952-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="3c952-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3c952-102">Details</span></span>

<span data-ttu-id="3c952-103">Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3c952-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="3c952-104">Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, благодаря чему гарантируется выбор правильной кисти.</span><span class="sxs-lookup"><span data-stu-id="3c952-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3c952-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="3c952-105">Suggestion</span></span>

<span data-ttu-id="3c952-106">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="3c952-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="3c952-107">name</span><span class="sxs-lookup"><span data-stu-id="3c952-107">Name</span></span>    | <span data-ttu-id="3c952-108">Значение</span><span class="sxs-lookup"><span data-stu-id="3c952-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3c952-109">Область</span><span class="sxs-lookup"><span data-stu-id="3c952-109">Scope</span></span>   |<span data-ttu-id="3c952-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="3c952-110">Edge</span></span>|
|<span data-ttu-id="3c952-111">Version</span><span class="sxs-lookup"><span data-stu-id="3c952-111">Version</span></span>|<span data-ttu-id="3c952-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3c952-112">4.6.2</span></span>|
|<span data-ttu-id="3c952-113">Type</span><span class="sxs-lookup"><span data-stu-id="3c952-113">Type</span></span>|<span data-ttu-id="3c952-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3c952-114">Runtime</span></span>|
