---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496407"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="944c8-101">Теперь WF сериализует Expressions.Literal&lt;T&gt; DateTimes по-другому (нарушает работу пользовательских средств синтаксического анализа XAML)</span><span class="sxs-lookup"><span data-stu-id="944c8-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="944c8-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="944c8-102">Details</span></span>

<span data-ttu-id="944c8-103">Связанный объект <xref:System.Windows.Markup.ValueSerializer> преобразует объект <xref:System.DateTime?displayProperty=fullName> или <xref:System.DateTimeOffset?displayProperty=fullName>, компоненты Second и <xref:System.DateTime.Millisecond?displayProperty=fullName> которого не равны нулю и (для значения <xref:System.DateTime?displayProperty=fullName>) свойство <xref:System.DateTime.Kind> которого не равно Unspecified, в синтаксис элемента свойства вместо строки.</span><span class="sxs-lookup"><span data-stu-id="944c8-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="944c8-104">Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=fullName> и <xref:System.DateTimeOffset?displayProperty=fullName> в оба конца.</span><span class="sxs-lookup"><span data-stu-id="944c8-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="944c8-105">Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="944c8-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="944c8-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="944c8-106">Suggestion</span></span>

<span data-ttu-id="944c8-107">Это изменение позволяет передавать значения <xref:System.DateTime?displayProperty=fullName> и <xref:System.DateTimeOffset?displayProperty=fullName> в оба конца.</span><span class="sxs-lookup"><span data-stu-id="944c8-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="944c8-108">Пользовательские средства синтаксического анализа XAML, в которых предполагается, что входные данные XAML имеют синтаксис атрибутов, не будут работать правильно.</span><span class="sxs-lookup"><span data-stu-id="944c8-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="944c8-109">name</span><span class="sxs-lookup"><span data-stu-id="944c8-109">Name</span></span>    | <span data-ttu-id="944c8-110">Значение</span><span class="sxs-lookup"><span data-stu-id="944c8-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="944c8-111">Область</span><span class="sxs-lookup"><span data-stu-id="944c8-111">Scope</span></span>   |<span data-ttu-id="944c8-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="944c8-112">Edge</span></span>|
|<span data-ttu-id="944c8-113">Version</span><span class="sxs-lookup"><span data-stu-id="944c8-113">Version</span></span>|<span data-ttu-id="944c8-114">4.5</span><span class="sxs-lookup"><span data-stu-id="944c8-114">4.5</span></span>|
|<span data-ttu-id="944c8-115">Type</span><span class="sxs-lookup"><span data-stu-id="944c8-115">Type</span></span>|<span data-ttu-id="944c8-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="944c8-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="944c8-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="944c8-117">Affected APIs</span></span>

<span data-ttu-id="944c8-118">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="944c8-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
