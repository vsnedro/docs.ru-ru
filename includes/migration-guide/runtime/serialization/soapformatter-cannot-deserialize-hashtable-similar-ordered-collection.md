---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620660"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="58f04-101">Классу SoapFormatter не удается выполнить десериализацию хэш-таблицы и подобных упорядоченных объектов коллекции</span><span class="sxs-lookup"><span data-stu-id="58f04-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="58f04-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="58f04-102">Details</span></span>

<span data-ttu-id="58f04-103">Класс <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> не гарантирует, что объекты, сериализованные в одной версии .NET Framework, будут успешно десериализованы в другой версии платформы.</span><span class="sxs-lookup"><span data-stu-id="58f04-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="58f04-104">В частности, в некоторые упорядоченные коллекции (например, <xref:System.Collections.Hashtable?displayProperty=fullName>) добавлены элементы в версиях с 4.0 по 4.5, поэтому объекты этих типов не могут быть десериализованы в .NET Framework 4.0, если бы они были сериализованы в .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="58f04-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="58f04-105">Обратите внимание, что если сериализованные данные сериализуются и десериализуются в одной версии .NET Framework, проблемы не возникают.</span><span class="sxs-lookup"><span data-stu-id="58f04-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="58f04-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="58f04-106">Suggestion</span></span>

<span data-ttu-id="58f04-107">Чтобы обеспечить поддержку изменений в .NET Framework, сериализацию <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> следует заменить на сериализацию <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> или <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="58f04-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="58f04-108">name</span><span class="sxs-lookup"><span data-stu-id="58f04-108">Name</span></span>    | <span data-ttu-id="58f04-109">Значение</span><span class="sxs-lookup"><span data-stu-id="58f04-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="58f04-110">Область</span><span class="sxs-lookup"><span data-stu-id="58f04-110">Scope</span></span>   |<span data-ttu-id="58f04-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="58f04-111">Minor</span></span>|
|<span data-ttu-id="58f04-112">Version</span><span class="sxs-lookup"><span data-stu-id="58f04-112">Version</span></span>|<span data-ttu-id="58f04-113">4.5</span><span class="sxs-lookup"><span data-stu-id="58f04-113">4.5</span></span>|
|<span data-ttu-id="58f04-114">Type</span><span class="sxs-lookup"><span data-stu-id="58f04-114">Type</span></span>|<span data-ttu-id="58f04-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="58f04-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="58f04-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="58f04-116">Affected APIs</span></span>

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
