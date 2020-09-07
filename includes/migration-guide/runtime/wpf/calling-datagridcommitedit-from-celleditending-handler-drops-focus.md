---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496106"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="53e6b-101">Вызов метода DataGrid.CommitEdit из обработчика CellEditEnding удаляет фокус</span><span class="sxs-lookup"><span data-stu-id="53e6b-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="53e6b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="53e6b-102">Details</span></span>

<span data-ttu-id="53e6b-103">Вызов метода <xref:System.Windows.Controls.DataGrid.CommitEdit> из одного из обработчиков событий <xref:System.Windows.Controls.DataGrid?displayProperty=fullName><xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> приводит к потере фокуса для <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="53e6b-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="53e6b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="53e6b-104">Suggestion</span></span>

<span data-ttu-id="53e6b-105">Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53e6b-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="53e6b-106">Кроме того, ее можно избежать, явным образом повторно выбрав <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> после вызова <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="53e6b-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="53e6b-107">name</span><span class="sxs-lookup"><span data-stu-id="53e6b-107">Name</span></span>    | <span data-ttu-id="53e6b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="53e6b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="53e6b-109">Область</span><span class="sxs-lookup"><span data-stu-id="53e6b-109">Scope</span></span>   |<span data-ttu-id="53e6b-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="53e6b-110">Edge</span></span>|
|<span data-ttu-id="53e6b-111">Version</span><span class="sxs-lookup"><span data-stu-id="53e6b-111">Version</span></span>|<span data-ttu-id="53e6b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="53e6b-112">4.5</span></span>|
|<span data-ttu-id="53e6b-113">Type</span><span class="sxs-lookup"><span data-stu-id="53e6b-113">Type</span></span>|<span data-ttu-id="53e6b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="53e6b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="53e6b-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="53e6b-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
