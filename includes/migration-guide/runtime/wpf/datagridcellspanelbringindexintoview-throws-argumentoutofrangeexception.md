---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497516"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="ac631-101">DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="ac631-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="ac631-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ac631-102">Details</span></span>

<span data-ttu-id="ac631-103">Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.</span><span class="sxs-lookup"><span data-stu-id="ac631-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="ac631-104">Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="ac631-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ac631-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ac631-105">Suggestion</span></span>

<span data-ttu-id="ac631-106">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="ac631-106">Any one of the following:</span></span><ol><li><span data-ttu-id="ac631-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ac631-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="ac631-108">Установите последнее служебное исправление для .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="ac631-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="ac631-109">Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="ac631-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="ac631-110">Имя</span><span class="sxs-lookup"><span data-stu-id="ac631-110">Name</span></span>    | <span data-ttu-id="ac631-111">Значение</span><span class="sxs-lookup"><span data-stu-id="ac631-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ac631-112">Область</span><span class="sxs-lookup"><span data-stu-id="ac631-112">Scope</span></span>   |<span data-ttu-id="ac631-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="ac631-113">Edge</span></span>|
|<span data-ttu-id="ac631-114">Version</span><span class="sxs-lookup"><span data-stu-id="ac631-114">Version</span></span>|<span data-ttu-id="ac631-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="ac631-115">4.6.2</span></span>|
|<span data-ttu-id="ac631-116">Type</span><span class="sxs-lookup"><span data-stu-id="ac631-116">Type</span></span>|<span data-ttu-id="ac631-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ac631-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ac631-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ac631-118">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
