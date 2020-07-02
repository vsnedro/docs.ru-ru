---
ms.openlocfilehash: 6d804dd335cb18d5febc2ca5f794af92963bece1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620720"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a><span data-ttu-id="db54b-101">При щелчке правой кнопкой мыши на заголовке строки WPF DataGrid изменяется выделение DataGrid</span><span class="sxs-lookup"><span data-stu-id="db54b-101">Right clicking on a WPF DataGrid row header changes the DataGrid selection</span></span>

#### <a name="details"></a><span data-ttu-id="db54b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="db54b-102">Details</span></span>

<span data-ttu-id="db54b-103">Если щелкнуть правой кнопкой мыши выделенный заголовок строки <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> при наличии нескольких выделенных строк, выделение <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> изменится таким образом, что будет выделена только эта строка.</span><span class="sxs-lookup"><span data-stu-id="db54b-103">Right-clicking a selected <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> row header while multiple rows are selected results in the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s selection changing to only that row.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="db54b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="db54b-104">Suggestion</span></span>

<span data-ttu-id="db54b-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="db54b-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="db54b-106">name</span><span class="sxs-lookup"><span data-stu-id="db54b-106">Name</span></span>    | <span data-ttu-id="db54b-107">Значение</span><span class="sxs-lookup"><span data-stu-id="db54b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="db54b-108">Область</span><span class="sxs-lookup"><span data-stu-id="db54b-108">Scope</span></span>   |<span data-ttu-id="db54b-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="db54b-109">Edge</span></span>|
|<span data-ttu-id="db54b-110">Version</span><span class="sxs-lookup"><span data-stu-id="db54b-110">Version</span></span>|<span data-ttu-id="db54b-111">4.5</span><span class="sxs-lookup"><span data-stu-id="db54b-111">4.5</span></span>|
|<span data-ttu-id="db54b-112">Type</span><span class="sxs-lookup"><span data-stu-id="db54b-112">Type</span></span>|<span data-ttu-id="db54b-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="db54b-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="db54b-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="db54b-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.%23ctor></li></ul>|
