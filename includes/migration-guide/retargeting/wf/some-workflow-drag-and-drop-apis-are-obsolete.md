---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617291"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="65d49-101">Некоторые API-интерфейсы перетаскивания в WorkFlow являются устаревшими</span><span class="sxs-lookup"><span data-stu-id="65d49-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="65d49-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="65d49-102">Details</span></span>

<span data-ttu-id="65d49-103">Этот API перетаскивания рабочего процесса является устаревшим и будет вызывать предупреждения компилятора, если приложение перестроено на версии 4.5.</span><span class="sxs-lookup"><span data-stu-id="65d49-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="65d49-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="65d49-104">Suggestion</span></span>

<span data-ttu-id="65d49-105">Следует использовать новые API <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName>, которые поддерживают операции с несколькими объектами.</span><span class="sxs-lookup"><span data-stu-id="65d49-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="65d49-106">Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версией компилятора.</span><span class="sxs-lookup"><span data-stu-id="65d49-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="65d49-107">Интерфейсы API по-прежнему поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="65d49-107">The APIs are still supported.</span></span>

| <span data-ttu-id="65d49-108">name</span><span class="sxs-lookup"><span data-stu-id="65d49-108">Name</span></span>    | <span data-ttu-id="65d49-109">Значение</span><span class="sxs-lookup"><span data-stu-id="65d49-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65d49-110">Область</span><span class="sxs-lookup"><span data-stu-id="65d49-110">Scope</span></span>   | <span data-ttu-id="65d49-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="65d49-111">Minor</span></span>       |
| <span data-ttu-id="65d49-112">Version</span><span class="sxs-lookup"><span data-stu-id="65d49-112">Version</span></span> | <span data-ttu-id="65d49-113">4.5</span><span class="sxs-lookup"><span data-stu-id="65d49-113">4.5</span></span>         |
| <span data-ttu-id="65d49-114">Type</span><span class="sxs-lookup"><span data-stu-id="65d49-114">Type</span></span>    | <span data-ttu-id="65d49-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="65d49-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="65d49-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="65d49-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
