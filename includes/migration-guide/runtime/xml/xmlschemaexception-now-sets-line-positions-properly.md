---
ms.openlocfilehash: 04d1c1162dc79bbcb0578c6661466f4d58a57acc
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496301"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="22d9a-101">Свойство XmlSchemaException теперь правильно задает позиции строк</span><span class="sxs-lookup"><span data-stu-id="22d9a-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="22d9a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="22d9a-102">Details</span></span>

<span data-ttu-id="22d9a-103">Если значение <xref:System.Xml.Linq.LoadOptions.SetLineInfo> передается методу Load и возникает ошибка проверки, свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> теперь содержат сведения о строке.</span><span class="sxs-lookup"><span data-stu-id="22d9a-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="22d9a-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="22d9a-104">Suggestion</span></span>

<span data-ttu-id="22d9a-105">Код обработки исключений, который предполагает, что свойства <xref:System.Xml.Schema.XmlSchemaException.LineNumber> и <xref:System.Xml.Schema.XmlSchemaException.LinePosition> не будут задаваться, необходимо обновить, поскольку эти свойства теперь задаются правильно при использовании SetLineInfo во время загрузки XML.</span><span class="sxs-lookup"><span data-stu-id="22d9a-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="22d9a-106">name</span><span class="sxs-lookup"><span data-stu-id="22d9a-106">Name</span></span>    | <span data-ttu-id="22d9a-107">Значение</span><span class="sxs-lookup"><span data-stu-id="22d9a-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="22d9a-108">Область</span><span class="sxs-lookup"><span data-stu-id="22d9a-108">Scope</span></span>   |<span data-ttu-id="22d9a-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="22d9a-109">Edge</span></span>|
|<span data-ttu-id="22d9a-110">Version</span><span class="sxs-lookup"><span data-stu-id="22d9a-110">Version</span></span>|<span data-ttu-id="22d9a-111">4.5</span><span class="sxs-lookup"><span data-stu-id="22d9a-111">4.5</span></span>|
|<span data-ttu-id="22d9a-112">Type</span><span class="sxs-lookup"><span data-stu-id="22d9a-112">Type</span></span>|<span data-ttu-id="22d9a-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="22d9a-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="22d9a-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="22d9a-114">Affected APIs</span></span>

- <xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Xml.Linq.LoadOptions.SetLineInfo`

-->
