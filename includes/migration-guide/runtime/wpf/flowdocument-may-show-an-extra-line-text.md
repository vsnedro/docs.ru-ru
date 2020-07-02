---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620690"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a><span data-ttu-id="7cdf8-101">FlowDocument может отображать дополнительную строку текста</span><span class="sxs-lookup"><span data-stu-id="7cdf8-101">FlowDocument may show an extra line of text</span></span>

#### <a name="details"></a><span data-ttu-id="7cdf8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7cdf8-102">Details</span></span>

<span data-ttu-id="7cdf8-103">В некоторых случаях при работе с .NET Framework 4.5 в элементе <xref:System.Windows.Documents.FlowDocument> отображается лишняя строка текста по сравнению с выполнением в .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="7cdf8-103">In some cases, a <xref:System.Windows.Documents.FlowDocument> element will display an extra line of text when running on the .NET Framework 4.5 compared to how it displayed when run on the .NET Framework 4.0.</span></span> <span data-ttu-id="7cdf8-104">Случаи неправильного или неразборчивого отображения текста в связи с этим изменением не выявлены, однако эта проблема может привести к отображению текста, который ранее был опущен из представления <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="7cdf8-104">There are no known cases of the change causing any text to be displayed poorly or illegibly, but it could cause text to appear that previously was omitted from a <xref:System.Windows.Documents.FlowDocument>'s view.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7cdf8-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="7cdf8-105">Suggestion</span></span>

<span data-ttu-id="7cdf8-106">В некоторых случаях для восстановления исходного количества строк можно уменьшить значение свойства PageHeight на единицу.</span><span class="sxs-lookup"><span data-stu-id="7cdf8-106">In some cases, decreasing the display element's PageHeight property by one can restore the previous number of displayed lines.</span></span>

| <span data-ttu-id="7cdf8-107">name</span><span class="sxs-lookup"><span data-stu-id="7cdf8-107">Name</span></span>    | <span data-ttu-id="7cdf8-108">Значение</span><span class="sxs-lookup"><span data-stu-id="7cdf8-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7cdf8-109">Область</span><span class="sxs-lookup"><span data-stu-id="7cdf8-109">Scope</span></span>   |<span data-ttu-id="7cdf8-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7cdf8-110">Edge</span></span>|
|<span data-ttu-id="7cdf8-111">Version</span><span class="sxs-lookup"><span data-stu-id="7cdf8-111">Version</span></span>|<span data-ttu-id="7cdf8-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7cdf8-112">4.5</span></span>|
|<span data-ttu-id="7cdf8-113">Type</span><span class="sxs-lookup"><span data-stu-id="7cdf8-113">Type</span></span>|<span data-ttu-id="7cdf8-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7cdf8-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7cdf8-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7cdf8-115">Affected APIs</span></span>

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
