---
ms.openlocfilehash: b6cb7c4b479551ff4563998f310ff518d935f48a
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656353"
---
### <a name="datagridview-related-apis-now-throw-invalidoperationexception"></a><span data-ttu-id="ee329-101">API, связанные с DataGridView, теперь вызывают исключение InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="ee329-101">DataGridView-related APIs now throw InvalidOperationException</span></span>

<span data-ttu-id="ee329-102">Некоторые API, связанные с <xref:System.Windows.Forms.DataGridView>, теперь вызывают <xref:System.InvalidOperationException>, если значение объекта <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> — `null`.</span><span class="sxs-lookup"><span data-stu-id="ee329-102">Some APIs related to <xref:System.Windows.Forms.DataGridView> now throw an <xref:System.InvalidOperationException> if the object's <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner?displayProperty=nameWithType> value is `null`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ee329-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="ee329-103">Change description</span></span>

<span data-ttu-id="ee329-104">В предыдущих версиях .NET затронутые API выдают <xref:System.NullReferenceException> при вызове, а значение <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> — `null`.</span><span class="sxs-lookup"><span data-stu-id="ee329-104">In previous .NET versions, the affected APIs throw a <xref:System.NullReferenceException> when they are invoked and the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null`.</span></span> <span data-ttu-id="ee329-105">Начиная с .NET 5.0 эти API создают <xref:System.InvalidOperationException>, а не <xref:System.NullReferenceException>, если при вызове значение <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> — `null`.</span><span class="sxs-lookup"><span data-stu-id="ee329-105">Starting in .NET 5.0, these APIs throw an <xref:System.InvalidOperationException> instead of a <xref:System.NullReferenceException> if the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> value is `null` when they are invoked.</span></span>

<span data-ttu-id="ee329-106">Вызов <xref:System.InvalidOperationException> соответствует поведению среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="ee329-106">Throwing an <xref:System.InvalidOperationException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="ee329-107">Это также улучшает процесс отладки, четко указывая недопустимое свойство.</span><span class="sxs-lookup"><span data-stu-id="ee329-107">It also improves the debugging experience by clearly communicating the invalid property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ee329-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ee329-108">Version introduced</span></span>

<span data-ttu-id="ee329-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ee329-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="ee329-110">Recommended action</span></span>

<span data-ttu-id="ee329-111">Проверьте код и при необходимости обновите его, чтобы не допустить создания затрагиваемых типов с помощью свойства <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> как `null`.</span><span class="sxs-lookup"><span data-stu-id="ee329-111">Review your code and, if necessary, update it to prevent constructing the affected types with the <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> property as `null`.</span></span>

#### <a name="category"></a><span data-ttu-id="ee329-112">Категория</span><span class="sxs-lookup"><span data-stu-id="ee329-112">Category</span></span>

<span data-ttu-id="ee329-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee329-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ee329-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ee329-114">Affected APIs</span></span>

<span data-ttu-id="ee329-115">В следующей таблице перечислены затронутые свойства и параметры.</span><span class="sxs-lookup"><span data-stu-id="ee329-115">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="ee329-116">Затронутый метод или свойство</span><span class="sxs-lookup"><span data-stu-id="ee329-116">Affected method or property</span></span> | <span data-ttu-id="ee329-117">Проверенное свойство</span><span class="sxs-lookup"><span data-stu-id="ee329-117">Validated property</span></span> | <span data-ttu-id="ee329-118">Добавлено в версии</span><span class="sxs-lookup"><span data-stu-id="ee329-118">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-119">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-119">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-120">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-120">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-121">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-121">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-122">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-122">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-123">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-123">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-124">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-124">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-125">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-125">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-126">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-126">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-127">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-127">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-128">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-128">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-129">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-129">5.0</span></span> |
> | <xref:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction?displayProperty=nameWithType> | <xref:System.Windows.Forms.DataGridViewCell.DataGridViewCellAccessibleObject.Owner> | <span data-ttu-id="ee329-130">5.0</span><span class="sxs-lookup"><span data-stu-id="ee329-130">5.0</span></span> |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DataGridViewButtonCell.DataGridViewButtonCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.State`
- `M:System.Windows.Forms.DataGridViewCheckBoxCell.DataGridViewCheckBoxCellAccessibleObject.DoDefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Bounds`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DefaultAction`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Name`
- `P:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Parent`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewColumnHeaderCell.DataGridViewColumnHeaderCellAccessibleObject.Navigate(System.Windows.Forms.AccessibleNavigation)`
- `M:System.Windows.Forms.DataGridViewImageCell.DataGridViewImageCellAccessibleObject.DoDefaultAction`
- `M:System.Windows.Forms.DataGridViewLinkCell.DataGridViewLinkCellAccessibleObject.DoDefaultAction`

-->
