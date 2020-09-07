---
ms.openlocfilehash: 5c8ea3565fbe599dd53a71ba8bd339704f7d7f8a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496526"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="fa23e-101">Критические изменения в SignedXml и EncryptedXml</span><span class="sxs-lookup"><span data-stu-id="fa23e-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="fa23e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="fa23e-102">Details</span></span>

<span data-ttu-id="fa23e-103">Исправления системы безопасности в .NET Framework 4.6.2 для <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> привели к различиям в поведении во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fa23e-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="fa23e-104">Например:</span><span class="sxs-lookup"><span data-stu-id="fa23e-104">For example,</span></span><ul><li><span data-ttu-id="fa23e-105">Если документ содержит несколько элементов с одинаковым атрибутом <code>id</code>, один из которых является целевым корнем подписи, такой документ будет считаться недействительным.</span><span class="sxs-lookup"><span data-stu-id="fa23e-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="fa23e-106">Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XPath в ссылках.</span><span class="sxs-lookup"><span data-stu-id="fa23e-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="fa23e-107">Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XSLT в ссылках.</span><span class="sxs-lookup"><span data-stu-id="fa23e-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="fa23e-108">Любая программа, использующая удаленные с внешнего ресурса подписи, не сможет сделать это.</span><span class="sxs-lookup"><span data-stu-id="fa23e-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="fa23e-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="fa23e-109">Suggestion</span></span>

<span data-ttu-id="fa23e-110">Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform> типы, поскольку получатель документа не всегда сможет обработать его.</span><span class="sxs-lookup"><span data-stu-id="fa23e-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="fa23e-111">Имя</span><span class="sxs-lookup"><span data-stu-id="fa23e-111">Name</span></span>    | <span data-ttu-id="fa23e-112">Значение</span><span class="sxs-lookup"><span data-stu-id="fa23e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fa23e-113">Область</span><span class="sxs-lookup"><span data-stu-id="fa23e-113">Scope</span></span>   |<span data-ttu-id="fa23e-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="fa23e-114">Minor</span></span>|
|<span data-ttu-id="fa23e-115">Version</span><span class="sxs-lookup"><span data-stu-id="fa23e-115">Version</span></span>|<span data-ttu-id="fa23e-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="fa23e-116">4.6.2</span></span>|
|<span data-ttu-id="fa23e-117">Type</span><span class="sxs-lookup"><span data-stu-id="fa23e-117">Type</span></span>|<span data-ttu-id="fa23e-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="fa23e-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fa23e-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="fa23e-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.Xml.Transform`
- `T:System.Security.Cryptography.Xml.XmlDsigXPathTransform`
- `T:System.Security.Cryptography.Xml.XmlDsigXsltTransform`

-->
