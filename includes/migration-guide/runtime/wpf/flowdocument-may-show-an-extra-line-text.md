---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497223"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="02d9d-101">FlowDocument может отображать дополнительную строку текста</span><span class="sxs-lookup"><span data-stu-id="02d9d-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="02d9d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="02d9d-102">Details</span></span>

<span data-ttu-id="02d9d-103">В некоторых случаях при работе с .NET Framework 4.5 в элементе <xref:System.Windows.Documents.FlowDocument> отображается лишняя строка текста по сравнению с выполнением в .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="02d9d-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="02d9d-104">Случаи неправильного или неразборчивого отображения текста в связи с этим изменением не выявлены, однако эта проблема может привести к отображению текста, который ранее был опущен из представления <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="02d9d-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="02d9d-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="02d9d-105">Suggestion</span></span>

<span data-ttu-id="02d9d-106">В некоторых случаях для восстановления исходного количества строк можно уменьшить значение свойства PageHeight на единицу.</span><span class="sxs-lookup"><span data-stu-id="02d9d-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="02d9d-107">name</span><span class="sxs-lookup"><span data-stu-id="02d9d-107">Name</span></span>    | <span data-ttu-id="02d9d-108">Значение</span><span class="sxs-lookup"><span data-stu-id="02d9d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="02d9d-109">Область</span><span class="sxs-lookup"><span data-stu-id="02d9d-109">Scope</span></span>   |<span data-ttu-id="02d9d-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="02d9d-110">Edge</span></span>|
|<span data-ttu-id="02d9d-111">Version</span><span class="sxs-lookup"><span data-stu-id="02d9d-111">Version</span></span>|<span data-ttu-id="02d9d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="02d9d-112">4.5</span></span>|
|<span data-ttu-id="02d9d-113">Type</span><span class="sxs-lookup"><span data-stu-id="02d9d-113">Type</span></span>|<span data-ttu-id="02d9d-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="02d9d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="02d9d-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="02d9d-115">Affected APIs</span></span>

- <xref:System.Windows.Documents.FlowDocument.%23ctor>
- <xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)>
- <xref:System.Windows.Controls.FlowDocumentReader.%23ctor>
- <xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor>
- <xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Documents.FlowDocument.#ctor`
- `M:System.Windows.Documents.FlowDocument.#ctor(System.Windows.Documents.Block)`
- `M:System.Windows.Controls.FlowDocumentReader.#ctor`
- `M:System.Windows.Controls.FlowDocumentPageViewer.#ctor`
- `M:System.Windows.Controls.Primitives.DocumentPageView.#ctor`

-->
