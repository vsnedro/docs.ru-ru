---
ms.openlocfilehash: e1faee846627b22b88eb888d6241d47d8ea6ea06
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497395"
---
### <a name="right-clicking-on-a-wpf-datagrid-row-header-changes-the-datagrid-selection"></a><span data-ttu-id="cba39-101">При щелчке правой кнопкой мыши на заголовке строки WPF DataGrid изменяется выделение DataGrid</span><span class="sxs-lookup"><span data-stu-id="cba39-101">Right clicking on a WPF DataGrid row header changes the DataGrid selection</span></span>

#### <a name="details"></a><span data-ttu-id="cba39-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="cba39-102">Details</span></span>

<span data-ttu-id="cba39-103">Если щелкнуть правой кнопкой мыши выделенный заголовок строки <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> при наличии нескольких выделенных строк, выделение <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> изменится таким образом, что будет выделена только эта строка.</span><span class="sxs-lookup"><span data-stu-id="cba39-103">Right-clicking a selected <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> row header while multiple rows are selected results in the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s selection changing to only that row.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cba39-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="cba39-104">Suggestion</span></span>

<span data-ttu-id="cba39-105">Эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cba39-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="cba39-106">name</span><span class="sxs-lookup"><span data-stu-id="cba39-106">Name</span></span>    | <span data-ttu-id="cba39-107">Значение</span><span class="sxs-lookup"><span data-stu-id="cba39-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cba39-108">Область</span><span class="sxs-lookup"><span data-stu-id="cba39-108">Scope</span></span>   |<span data-ttu-id="cba39-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="cba39-109">Edge</span></span>|
|<span data-ttu-id="cba39-110">Version</span><span class="sxs-lookup"><span data-stu-id="cba39-110">Version</span></span>|<span data-ttu-id="cba39-111">4.5</span><span class="sxs-lookup"><span data-stu-id="cba39-111">4.5</span></span>|
|<span data-ttu-id="cba39-112">Type</span><span class="sxs-lookup"><span data-stu-id="cba39-112">Type</span></span>|<span data-ttu-id="cba39-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="cba39-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="cba39-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="cba39-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.#ctor`

-->
