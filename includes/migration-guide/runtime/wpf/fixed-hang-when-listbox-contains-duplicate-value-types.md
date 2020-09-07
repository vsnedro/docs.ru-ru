---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496137"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a><span data-ttu-id="eebc6-101">Исправлено зависание, если ListBox содержит повторяющиеся типы значений</span><span class="sxs-lookup"><span data-stu-id="eebc6-101">Fixed a hang when ListBox contains duplicate value-types</span></span>

#### <a name="details"></a><span data-ttu-id="eebc6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="eebc6-102">Details</span></span>

<span data-ttu-id="eebc6-103">Устранена проблема, при которой виртуализация <xref:System.Windows.Controls.ItemsControl> приводила к зависанию при прокрутке, когда коллекция элементов содержит повторяющиеся объекты типов значений.</span><span class="sxs-lookup"><span data-stu-id="eebc6-103">Fixed a problem where a virtualizing<xref:System.Windows.Controls.ItemsControl> can hang during scrolling when its Items collection contains duplicate value-typed objects.</span></span>

| <span data-ttu-id="eebc6-104">name</span><span class="sxs-lookup"><span data-stu-id="eebc6-104">Name</span></span>    | <span data-ttu-id="eebc6-105">Значение</span><span class="sxs-lookup"><span data-stu-id="eebc6-105">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eebc6-106">Область</span><span class="sxs-lookup"><span data-stu-id="eebc6-106">Scope</span></span>   |<span data-ttu-id="eebc6-107">Значительно</span><span class="sxs-lookup"><span data-stu-id="eebc6-107">Major</span></span>|
|<span data-ttu-id="eebc6-108">Version</span><span class="sxs-lookup"><span data-stu-id="eebc6-108">Version</span></span>|<span data-ttu-id="eebc6-109">4.8</span><span class="sxs-lookup"><span data-stu-id="eebc6-109">4.8</span></span>|
|<span data-ttu-id="eebc6-110">Type</span><span class="sxs-lookup"><span data-stu-id="eebc6-110">Type</span></span>|<span data-ttu-id="eebc6-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="eebc6-111">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="eebc6-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="eebc6-112">Affected APIs</span></span>

<span data-ttu-id="eebc6-113">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="eebc6-113">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
