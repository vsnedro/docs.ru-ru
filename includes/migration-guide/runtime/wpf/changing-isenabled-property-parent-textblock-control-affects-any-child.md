---
ms.openlocfilehash: 12a26030a9a336d887ae9d53994a9daf13356618
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496463"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="219cd-101">Изменение свойства IsEnabled для родительского объекта элемента управления TextBlock влияет на любые дочерние элементы управления</span><span class="sxs-lookup"><span data-stu-id="219cd-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

#### <a name="details"></a><span data-ttu-id="219cd-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="219cd-102">Details</span></span>

<span data-ttu-id="219cd-103">Начиная с версии .NET Framework 4.6.2, изменение свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> родительского объекта элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> влияет на любые дочерние элементы управления (например, гиперссылки и кнопки) элемента <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>. В .NET Framework 4.6.1 и более ранних версий элементы управления внутри элемента <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> не всегда отражали состояние свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> родительского объекта <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="219cd-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=fullName> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> parent.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="219cd-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="219cd-104">Suggestion</span></span>

<span data-ttu-id="219cd-105">Нет.</span><span class="sxs-lookup"><span data-stu-id="219cd-105">None.</span></span> <span data-ttu-id="219cd-106">Это изменение соответствует ожидаемому поведению для элементов управления, содержащихся внутри элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="219cd-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=fullName> control.</span></span>

| <span data-ttu-id="219cd-107">Имя</span><span class="sxs-lookup"><span data-stu-id="219cd-107">Name</span></span>    | <span data-ttu-id="219cd-108">Значение</span><span class="sxs-lookup"><span data-stu-id="219cd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="219cd-109">Область</span><span class="sxs-lookup"><span data-stu-id="219cd-109">Scope</span></span>   |<span data-ttu-id="219cd-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="219cd-110">Minor</span></span>|
|<span data-ttu-id="219cd-111">Version</span><span class="sxs-lookup"><span data-stu-id="219cd-111">Version</span></span>|<span data-ttu-id="219cd-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="219cd-112">4.6.2</span></span>|
|<span data-ttu-id="219cd-113">Type</span><span class="sxs-lookup"><span data-stu-id="219cd-113">Type</span></span>|<span data-ttu-id="219cd-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="219cd-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="219cd-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="219cd-115">Affected APIs</span></span>

- <xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.UIElement.IsEnabled`

-->
