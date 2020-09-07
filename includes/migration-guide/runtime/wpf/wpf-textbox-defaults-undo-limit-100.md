---
ms.openlocfilehash: 9d960774161fc44810f90ca30f56eb98f98de3ff
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496907"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="80298-101">Ограничение отмены по умолчанию для текстового поля WPF равно 100</span><span class="sxs-lookup"><span data-stu-id="80298-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="80298-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="80298-102">Details</span></span>

<span data-ttu-id="80298-103">В .NET Framework 4.5 ограничение отмены по умолчанию для текстового поля WPF равно 100 (в отличие от неограниченного в .NET Framework 4.0)</span><span class="sxs-lookup"><span data-stu-id="80298-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80298-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="80298-104">Suggestion</span></span>

<span data-ttu-id="80298-105">Если ограничение отмены, равное 100, слишком низкое, ограничение можно задать явным образом с помощью свойства <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span><span class="sxs-lookup"><span data-stu-id="80298-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="80298-106">name</span><span class="sxs-lookup"><span data-stu-id="80298-106">Name</span></span>    | <span data-ttu-id="80298-107">Значение</span><span class="sxs-lookup"><span data-stu-id="80298-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80298-108">Область</span><span class="sxs-lookup"><span data-stu-id="80298-108">Scope</span></span>   |<span data-ttu-id="80298-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="80298-109">Edge</span></span>|
|<span data-ttu-id="80298-110">Version</span><span class="sxs-lookup"><span data-stu-id="80298-110">Version</span></span>|<span data-ttu-id="80298-111">4.5</span><span class="sxs-lookup"><span data-stu-id="80298-111">4.5</span></span>|
|<span data-ttu-id="80298-112">Type</span><span class="sxs-lookup"><span data-stu-id="80298-112">Type</span></span>|<span data-ttu-id="80298-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="80298-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="80298-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="80298-114">Affected APIs</span></span>

- <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.TextBox`

-->
