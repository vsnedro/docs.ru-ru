---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496156"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="4e4f5-101">BinaryFormatter может не находить тип в контексте LoadFrom</span><span class="sxs-lookup"><span data-stu-id="4e4f5-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

#### <a name="details"></a><span data-ttu-id="4e4f5-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4e4f5-102">Details</span></span>

<span data-ttu-id="4e4f5-103">Начиная с .NET Framework 4.5 ряд изменений <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> может привести к различиям в десериализации при использовании <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> для десериализации типов, загруженных в контекст LoadFrom.</span><span class="sxs-lookup"><span data-stu-id="4e4f5-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="4e4f5-104">Эти изменения связаны с тем, что <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> теперь иначе загружает тип. Это приводит к другому поведению, когда <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> пытается выполнить десериализацию в этот тип позднее.</span><span class="sxs-lookup"><span data-stu-id="4e4f5-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="4e4f5-105">Модуль привязки сериализации по умолчанию не выполняет автоматический поиск контекста LoadFrom, хотя это могло работать в некоторых случаях при старом поведении XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="4e4f5-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="4e4f5-106">В связи с изменениями, когда этот тип загружается из сборки, загруженной в другом контексте, может возникнуть исключение <xref:System.IO.FileNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4e4f5-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=fullName> may be thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4e4f5-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="4e4f5-107">Suggestion</span></span>

<span data-ttu-id="4e4f5-108">Если это исключение возникает, в свойстве <code>Binder</code><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> можно задать пользовательский модуль привязки, который найдет правильный тип.</span><span class="sxs-lookup"><span data-stu-id="4e4f5-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> can be set to a custom binder that will find the correct type.</span></span><pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="4e4f5-109">А затем пользовательский модуль привязки:</span><span class="sxs-lookup"><span data-stu-id="4e4f5-109">And then the custom binder:</span></span><pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="4e4f5-110">name</span><span class="sxs-lookup"><span data-stu-id="4e4f5-110">Name</span></span>    | <span data-ttu-id="4e4f5-111">Значение</span><span class="sxs-lookup"><span data-stu-id="4e4f5-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4e4f5-112">Область</span><span class="sxs-lookup"><span data-stu-id="4e4f5-112">Scope</span></span>   |<span data-ttu-id="4e4f5-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="4e4f5-113">Edge</span></span>|
|<span data-ttu-id="4e4f5-114">Version</span><span class="sxs-lookup"><span data-stu-id="4e4f5-114">Version</span></span>|<span data-ttu-id="4e4f5-115">4.5</span><span class="sxs-lookup"><span data-stu-id="4e4f5-115">4.5</span></span>|
|<span data-ttu-id="4e4f5-116">Type</span><span class="sxs-lookup"><span data-stu-id="4e4f5-116">Type</span></span>|<span data-ttu-id="4e4f5-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4e4f5-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4e4f5-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4e4f5-118">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
