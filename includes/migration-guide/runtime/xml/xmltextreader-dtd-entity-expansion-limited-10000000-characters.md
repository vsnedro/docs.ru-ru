---
ms.openlocfilehash: e56d896f093d6cd28ed0d6640ba154e5d4593c6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496095"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="099ab-101">Развертывание сущностей DTD XmlTextReader не может превышать 10 000 000 символов</span><span class="sxs-lookup"><span data-stu-id="099ab-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="099ab-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="099ab-102">Details</span></span>

<span data-ttu-id="099ab-103">Развертывание сущностей DTD теперь не может превышать 10 000 000 символов.</span><span class="sxs-lookup"><span data-stu-id="099ab-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="099ab-104">Загрузка XML-файлов без развертывания сущностей DTD или с ограниченным развертыванием сущностей DTD не изменяется.</span><span class="sxs-lookup"><span data-stu-id="099ab-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="099ab-105">Файлы с сущностями DTD, которые развертываются до более чем 10 000 000 символов, не загружаются и теперь вызывают исключение.</span><span class="sxs-lookup"><span data-stu-id="099ab-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="099ab-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="099ab-106">Suggestion</span></span>

<span data-ttu-id="099ab-107">Если ограничение развертывания сущностей DTD существенно ниже 10 000 000, значение может быть переопределено с помощью свойства <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>.</span><span class="sxs-lookup"><span data-stu-id="099ab-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="099ab-108"><xref:System.Xml.XmlReaderSettings?displayProperty=fullName> с соответствующим значением <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> может передаваться в <code>XmlReader.Create</code>, который принимает <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (т. е. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span><span class="sxs-lookup"><span data-stu-id="099ab-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="099ab-109">name</span><span class="sxs-lookup"><span data-stu-id="099ab-109">Name</span></span>    | <span data-ttu-id="099ab-110">Значение</span><span class="sxs-lookup"><span data-stu-id="099ab-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="099ab-111">Область</span><span class="sxs-lookup"><span data-stu-id="099ab-111">Scope</span></span>   |<span data-ttu-id="099ab-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="099ab-112">Edge</span></span>|
|<span data-ttu-id="099ab-113">Version</span><span class="sxs-lookup"><span data-stu-id="099ab-113">Version</span></span>|<span data-ttu-id="099ab-114">4.5</span><span class="sxs-lookup"><span data-stu-id="099ab-114">4.5</span></span>|
|<span data-ttu-id="099ab-115">Type</span><span class="sxs-lookup"><span data-stu-id="099ab-115">Type</span></span>|<span data-ttu-id="099ab-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="099ab-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="099ab-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="099ab-117">Affected APIs</span></span>

- <xref:System.Xml.XmlTextReader?displayProperty=nameWithType>
- <xref:System.Xml.XmlTextReader.%23ctor>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)>

<!--

#### Affected APIs

- `T:System.Xml.XmlTextReader`
- `M:System.Xml.XmlTextReader.#ctor`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.Xml.XmlNameTable)`

-->
