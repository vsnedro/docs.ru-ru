---
ms.openlocfilehash: 6f22d6211ec9238fd1c7786643ca95db02bfca64
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497207"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="d1079-101">Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора</span><span class="sxs-lookup"><span data-stu-id="d1079-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="d1079-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d1079-102">Details</span></span>

<span data-ttu-id="d1079-103">Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="d1079-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="d1079-104">При попытке сериализации каталога MEF происходит вызов исключения.</span><span class="sxs-lookup"><span data-stu-id="d1079-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1079-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d1079-105">Suggestion</span></span>

<span data-ttu-id="d1079-106">Больше не следует использовать MEF для создания сериализатора.</span><span class="sxs-lookup"><span data-stu-id="d1079-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="d1079-107">name</span><span class="sxs-lookup"><span data-stu-id="d1079-107">Name</span></span>    | <span data-ttu-id="d1079-108">Значение</span><span class="sxs-lookup"><span data-stu-id="d1079-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1079-109">Область</span><span class="sxs-lookup"><span data-stu-id="d1079-109">Scope</span></span>   |<span data-ttu-id="d1079-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="d1079-110">Major</span></span>|
|<span data-ttu-id="d1079-111">Version</span><span class="sxs-lookup"><span data-stu-id="d1079-111">Version</span></span>|<span data-ttu-id="d1079-112">4.5</span><span class="sxs-lookup"><span data-stu-id="d1079-112">4.5</span></span>|
|<span data-ttu-id="d1079-113">Type</span><span class="sxs-lookup"><span data-stu-id="d1079-113">Type</span></span>|<span data-ttu-id="d1079-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d1079-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d1079-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d1079-115">Affected APIs</span></span>

<span data-ttu-id="d1079-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="d1079-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
