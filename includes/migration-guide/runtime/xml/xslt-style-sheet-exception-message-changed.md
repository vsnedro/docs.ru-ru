---
ms.openlocfilehash: d33d75b4c2d9bc18844f66f1fcca1e2efc6f1eee
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497937"
---
### <a name="xslt-style-sheet-exception-message-changed"></a><span data-ttu-id="2782b-101">Изменено сообщение об исключении таблицы стилей XSLT</span><span class="sxs-lookup"><span data-stu-id="2782b-101">XSLT style sheet exception message changed</span></span>

#### <a name="details"></a><span data-ttu-id="2782b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2782b-102">Details</span></span>

<span data-ttu-id="2782b-103">В .NET Framework 4.5 текст сообщения об ошибке, вызванной тем, что XSLT-файл является слишком сложным, выглядит так: &quot;Слишком сложная таблица стилей&quot;. В предыдущих версиях сообщение об ошибке имело вид &quot;Ошибка компиляции XSLT&quot;. Код приложений, который зависит от текста сообщения об ошибке, больше не будет работать.</span><span class="sxs-lookup"><span data-stu-id="2782b-103">In the .NET Framework 4.5, the text of the error message when an XSLT file is too complex is &quot;The style sheet is too complex.&quot; In previous versions, the error message was &quot;XSLT compile error.&quot; Application code that depends on the text of the error message will no longer work.</span></span> <span data-ttu-id="2782b-104">Однако типы исключений остаются теми же, поэтому это изменение не должно иметь никаких реальных последствий.</span><span class="sxs-lookup"><span data-stu-id="2782b-104">However, the exception types remain the same, so this change should have no real impact.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2782b-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="2782b-105">Suggestion</span></span>

<span data-ttu-id="2782b-106">Обновите код приложения, зависящий от сообщения об исключении из этого условия ошибки, для ожидания нового сообщения или (что еще лучше) обновите код так, чтобы он зависел только от типа исключения (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), который не изменился.</span><span class="sxs-lookup"><span data-stu-id="2782b-106">Update any app code depending on the exception message from this error condition to expect the new message, or (even better) update the code to depend only on the exception type (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>), which has not changed.</span></span>

| <span data-ttu-id="2782b-107">name</span><span class="sxs-lookup"><span data-stu-id="2782b-107">Name</span></span>    | <span data-ttu-id="2782b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="2782b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2782b-109">Область</span><span class="sxs-lookup"><span data-stu-id="2782b-109">Scope</span></span>   |<span data-ttu-id="2782b-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="2782b-110">Edge</span></span>|
|<span data-ttu-id="2782b-111">Version</span><span class="sxs-lookup"><span data-stu-id="2782b-111">Version</span></span>|<span data-ttu-id="2782b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="2782b-112">4.5</span></span>|
|<span data-ttu-id="2782b-113">Type</span><span class="sxs-lookup"><span data-stu-id="2782b-113">Type</span></span>|<span data-ttu-id="2782b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2782b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2782b-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2782b-115">Affected APIs</span></span>

- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>
- <xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`
- `M:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)`

-->
