---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620733"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="f84fa-101">Изменено сообщение об исключении таблицы стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="f84fa-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="f84fa-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f84fa-102">Details</span></span>

<span data-ttu-id="f84fa-103">В .NET Framework 4.5 текст сообщения об ошибке, вызванной тем, что XSLT-файл является слишком сложным, выглядит так: &quot;Слишком сложная таблица стилей&quot;. В предыдущих версиях сообщение об ошибке имело вид &quot;Ошибка компиляции XSLT&quot;. Код приложений, который зависит от текста сообщения об ошибке, больше не будет работать.</span><span class="sxs-lookup"><span data-stu-id="f84fa-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="f84fa-104">Однако типы исключений остаются теми же, поэтому это изменение не должно иметь никаких реальных последствий.</span><span class="sxs-lookup"><span data-stu-id="f84fa-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f84fa-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="f84fa-105">Suggestion</span></span>

<span data-ttu-id="f84fa-106">Обновите код приложения, зависящий от сообщения об исключении из этого условия ошибки, для ожидания нового сообщения или (что еще лучше) обновите код так, чтобы он зависел только от типа исключения (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), который не изменился.</span><span class="sxs-lookup"><span data-stu-id="f84fa-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="f84fa-107">name</span><span class="sxs-lookup"><span data-stu-id="f84fa-107">Name</span></span>    | <span data-ttu-id="f84fa-108">Значение</span><span class="sxs-lookup"><span data-stu-id="f84fa-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f84fa-109">Область</span><span class="sxs-lookup"><span data-stu-id="f84fa-109">Scope</span></span>   |<span data-ttu-id="f84fa-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="f84fa-110">Edge</span></span>|
|<span data-ttu-id="f84fa-111">Version</span><span class="sxs-lookup"><span data-stu-id="f84fa-111">Version</span></span>|<span data-ttu-id="f84fa-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f84fa-112">4.5</span></span>|
|<span data-ttu-id="f84fa-113">Type</span><span class="sxs-lookup"><span data-stu-id="f84fa-113">Type</span></span>|<span data-ttu-id="f84fa-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f84fa-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f84fa-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f84fa-115">Affected APIs</span></span>

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
