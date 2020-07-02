---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620159"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="e9ad6-101">Событие Page.LoadComplete больше не заставляет элемент управления System.Web.UI.WebControls.EntityDataSource вызывать привязку данных</span><span class="sxs-lookup"><span data-stu-id="e9ad6-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="e9ad6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="e9ad6-102">Details</span></span>

<span data-ttu-id="e9ad6-103">Событие <xref:System.Web.UI.Page.LoadComplete> больше не заставляет элемент управления <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> вызывать привязку данных для изменений в параметрах создания/обновления/удаления.</span><span class="sxs-lookup"><span data-stu-id="e9ad6-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="e9ad6-104">Это изменение исключает лишнее обращение к базе данных, не допускает сброса значений элементов управления и позволяет получить поведение, согласованное с другими элементами управления данными, такими как <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> и <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e9ad6-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="e9ad6-105">Это изменение дает другое поведение в том маловероятном случае, когда в приложении предполагается вызов привязки данных в событии <xref:System.Web.UI.Page.LoadComplete>.</span><span class="sxs-lookup"><span data-stu-id="e9ad6-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e9ad6-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="e9ad6-106">Suggestion</span></span>

<span data-ttu-id="e9ad6-107">Если есть необходимость в привязке данных, вручную вызовите ее в событии, которое возникает раньше в обратной передаче.</span><span class="sxs-lookup"><span data-stu-id="e9ad6-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="e9ad6-108">name</span><span class="sxs-lookup"><span data-stu-id="e9ad6-108">Name</span></span>    | <span data-ttu-id="e9ad6-109">Значение</span><span class="sxs-lookup"><span data-stu-id="e9ad6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e9ad6-110">Область</span><span class="sxs-lookup"><span data-stu-id="e9ad6-110">Scope</span></span>   |<span data-ttu-id="e9ad6-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e9ad6-111">Edge</span></span>|
|<span data-ttu-id="e9ad6-112">Version</span><span class="sxs-lookup"><span data-stu-id="e9ad6-112">Version</span></span>|<span data-ttu-id="e9ad6-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e9ad6-113">4.5</span></span>|
|<span data-ttu-id="e9ad6-114">Type</span><span class="sxs-lookup"><span data-stu-id="e9ad6-114">Type</span></span>|<span data-ttu-id="e9ad6-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e9ad6-115">Runtime</span></span>|
