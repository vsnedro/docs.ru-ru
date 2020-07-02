---
ms.openlocfilehash: 13d3799aeede86b01aa81ce1cd69b3c4c22311ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620714"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="c4800-101">Ограничение отмены по умолчанию для текстового поля WPF равно 100</span><span class="sxs-lookup"><span data-stu-id="c4800-101">WPF TextBox defaults to undo limit of 100</span></span>

#### <a name="details"></a><span data-ttu-id="c4800-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c4800-102">Details</span></span>

<span data-ttu-id="c4800-103">В .NET Framework 4.5 ограничение отмены по умолчанию для текстового поля WPF равно 100 (в отличие от неограниченного в .NET Framework 4.0)</span><span class="sxs-lookup"><span data-stu-id="c4800-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c4800-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="c4800-104">Suggestion</span></span>

<span data-ttu-id="c4800-105">Если ограничение отмены, равное 100, слишком низкое, ограничение можно задать явным образом с помощью свойства <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span><span class="sxs-lookup"><span data-stu-id="c4800-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>

| <span data-ttu-id="c4800-106">name</span><span class="sxs-lookup"><span data-stu-id="c4800-106">Name</span></span>    | <span data-ttu-id="c4800-107">Значение</span><span class="sxs-lookup"><span data-stu-id="c4800-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c4800-108">Область</span><span class="sxs-lookup"><span data-stu-id="c4800-108">Scope</span></span>   |<span data-ttu-id="c4800-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c4800-109">Edge</span></span>|
|<span data-ttu-id="c4800-110">Version</span><span class="sxs-lookup"><span data-stu-id="c4800-110">Version</span></span>|<span data-ttu-id="c4800-111">4.5</span><span class="sxs-lookup"><span data-stu-id="c4800-111">4.5</span></span>|
|<span data-ttu-id="c4800-112">Type</span><span class="sxs-lookup"><span data-stu-id="c4800-112">Type</span></span>|<span data-ttu-id="c4800-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c4800-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c4800-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c4800-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
