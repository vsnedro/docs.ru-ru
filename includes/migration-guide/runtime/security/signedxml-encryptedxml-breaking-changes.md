---
ms.openlocfilehash: 8cc4f2ba2923774ef4e4e6861a89a7797ca988e1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621203"
---
### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="3b10e-101">Критические изменения в SignedXml и EncryptedXml</span><span class="sxs-lookup"><span data-stu-id="3b10e-101">SignedXml and EncryptedXml Breaking Changes</span></span>

#### <a name="details"></a><span data-ttu-id="3b10e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3b10e-102">Details</span></span>

<span data-ttu-id="3b10e-103">Исправления системы безопасности в .NET Framework 4.6.2 для <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> привели к различиям в поведении во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3b10e-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName> lead to different run-time behaviors.</span></span> <span data-ttu-id="3b10e-104">Например:</span><span class="sxs-lookup"><span data-stu-id="3b10e-104">For example,</span></span><ul><li><span data-ttu-id="3b10e-105">Если документ содержит несколько элементов с одинаковым атрибутом <code>id</code>, один из которых является целевым корнем подписи, такой документ будет считаться недействительным.</span><span class="sxs-lookup"><span data-stu-id="3b10e-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="3b10e-106">Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XPath в ссылках.</span><span class="sxs-lookup"><span data-stu-id="3b10e-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="3b10e-107">Теперь недействительными считаются документы, использующие неканонические алгоритмы преобразования XSLT в ссылках.</span><span class="sxs-lookup"><span data-stu-id="3b10e-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="3b10e-108">Любая программа, использующая удаленные с внешнего ресурса подписи, не сможет сделать это.</span><span class="sxs-lookup"><span data-stu-id="3b10e-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="3b10e-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="3b10e-109">Suggestion</span></span>

<span data-ttu-id="3b10e-110">Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform> типы, поскольку получатель документа не всегда сможет обработать его.</span><span class="sxs-lookup"><span data-stu-id="3b10e-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>

| <span data-ttu-id="3b10e-111">name</span><span class="sxs-lookup"><span data-stu-id="3b10e-111">Name</span></span>    | <span data-ttu-id="3b10e-112">Значение</span><span class="sxs-lookup"><span data-stu-id="3b10e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3b10e-113">Область</span><span class="sxs-lookup"><span data-stu-id="3b10e-113">Scope</span></span>   |<span data-ttu-id="3b10e-114">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="3b10e-114">Minor</span></span>|
|<span data-ttu-id="3b10e-115">Version</span><span class="sxs-lookup"><span data-stu-id="3b10e-115">Version</span></span>|<span data-ttu-id="3b10e-116">4.6.2</span><span class="sxs-lookup"><span data-stu-id="3b10e-116">4.6.2</span></span>|
|<span data-ttu-id="3b10e-117">Type</span><span class="sxs-lookup"><span data-stu-id="3b10e-117">Type</span></span>|<span data-ttu-id="3b10e-118">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3b10e-118">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b10e-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3b10e-119">Affected APIs</span></span>

-<xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
