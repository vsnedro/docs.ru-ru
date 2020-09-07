---
ms.openlocfilehash: f61e5670334f4d3674fd0b008d1a476b14c7ba4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496580"
---
### <a name="calling-attributegetcustomattributes-on-an-indexer-property-no-longer-throws-ambiguousmatchexception-if-the-ambiguity-can-be-resolved-by-indexs-type"></a><span data-ttu-id="96ef8-101">Вызов Attribute.GetCustomAttributes в свойстве индексатора больше не вызывает исключение AmbiguousMatchException, если тип индекса может разрешить неоднозначность</span><span class="sxs-lookup"><span data-stu-id="96ef8-101">Calling Attribute.GetCustomAttributes on an indexer property no longer throws AmbiguousMatchException if the ambiguity can be resolved by index's type</span></span>

#### <a name="details"></a><span data-ttu-id="96ef8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="96ef8-102">Details</span></span>

<span data-ttu-id="96ef8-103">В версиях .NET Framework, более ранних, чем 4.6, вызов <code>GetCustomAttribute(s)</code> в свойстве индексатора, которое отличалось от другого свойства только по типу индекса, приведет к <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="96ef8-103">Prior to the .NET Framework 4.6, calling <code>GetCustomAttribute(s)</code> on an indexer property which differed from another property only by the type of the index would result in an <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>.</span></span> <span data-ttu-id="96ef8-104">Начиная с .NET Framework 4.6, атрибуты свойства возвращаются правильно.</span><span class="sxs-lookup"><span data-stu-id="96ef8-104">Beginning in the .NET Framework 4.6, the property's attributes will be correctly returned.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96ef8-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="96ef8-105">Suggestion</span></span>

<span data-ttu-id="96ef8-106">Имейте в виду, что теперь GetCustomAttribute(s) будут использоваться чаще.</span><span class="sxs-lookup"><span data-stu-id="96ef8-106">Be aware that GetCustomAttribute(s) will work more frequently now.</span></span> <span data-ttu-id="96ef8-107">Если приложение ранее зависело от <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, теперь для явного поиска нескольких индексаторов следует использовать отражение.</span><span class="sxs-lookup"><span data-stu-id="96ef8-107">If an app was previously relying on the <xref:System.Reflection.AmbiguousMatchException?displayProperty=fullName>, reflection should now be used to explicitly look for multiple indexers, instead.</span></span>

| <span data-ttu-id="96ef8-108">name</span><span class="sxs-lookup"><span data-stu-id="96ef8-108">Name</span></span>    | <span data-ttu-id="96ef8-109">Значение</span><span class="sxs-lookup"><span data-stu-id="96ef8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96ef8-110">Область</span><span class="sxs-lookup"><span data-stu-id="96ef8-110">Scope</span></span>   |<span data-ttu-id="96ef8-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="96ef8-111">Edge</span></span>|
|<span data-ttu-id="96ef8-112">Version</span><span class="sxs-lookup"><span data-stu-id="96ef8-112">Version</span></span>|<span data-ttu-id="96ef8-113">4.6</span><span class="sxs-lookup"><span data-stu-id="96ef8-113">4.6</span></span>|
|<span data-ttu-id="96ef8-114">Type</span><span class="sxs-lookup"><span data-stu-id="96ef8-114">Type</span></span>|<span data-ttu-id="96ef8-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="96ef8-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="96ef8-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="96ef8-116">Affected APIs</span></span>

- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttribute%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo)?displayProperty=nameWithType>
- <xref:System.Reflection.CustomAttributeExtensions.GetCustomAttributes%60%601(System.Reflection.MemberInfo,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Attribute.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttribute``1(System.Reflection.MemberInfo,System.Boolean)``
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Boolean)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type)`
- `M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes(System.Reflection.MemberInfo,System.Type,System.Boolean)`
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo)``
- ``M:System.Reflection.CustomAttributeExtensions.GetCustomAttributes``1(System.Reflection.MemberInfo,System.Boolean)``

-->
