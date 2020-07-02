---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622380"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="0c684-101">DataGridCellsPanel.BringIndexIntoView создает исключение ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="0c684-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="0c684-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0c684-102">Details</span></span>

<span data-ttu-id="0c684-103">Метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов еще не определена.</span><span class="sxs-lookup"><span data-stu-id="0c684-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="0c684-104">Если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="0c684-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c684-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0c684-105">Suggestion</span></span>

<span data-ttu-id="0c684-106">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="0c684-106">Any one of the following:</span></span><ol><li><span data-ttu-id="0c684-107">Выполните обновление до .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="0c684-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="0c684-108">Установите последнее служебное исправление для .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="0c684-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="0c684-109">Избегать удаления столбцов до завершения асинхронного ответа на метод <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="0c684-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="0c684-110">name</span><span class="sxs-lookup"><span data-stu-id="0c684-110">Name</span></span>    | <span data-ttu-id="0c684-111">Значение</span><span class="sxs-lookup"><span data-stu-id="0c684-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c684-112">Область</span><span class="sxs-lookup"><span data-stu-id="0c684-112">Scope</span></span>   |<span data-ttu-id="0c684-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0c684-113">Edge</span></span>|
|<span data-ttu-id="0c684-114">Version</span><span class="sxs-lookup"><span data-stu-id="0c684-114">Version</span></span>|<span data-ttu-id="0c684-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="0c684-115">4.6.2</span></span>|
|<span data-ttu-id="0c684-116">Type</span><span class="sxs-lookup"><span data-stu-id="0c684-116">Type</span></span>|<span data-ttu-id="0c684-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0c684-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0c684-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0c684-118">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
