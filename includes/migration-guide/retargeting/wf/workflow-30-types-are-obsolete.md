---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606444"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="19699-101">Типы WorkFlow 3.0 устарели</span><span class="sxs-lookup"><span data-stu-id="19699-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="19699-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="19699-102">Details</span></span>

<span data-ttu-id="19699-103">API-интерфейсы Windows Workflow Foundation (WWF) 3.0 (из пространства имен System.Workflow) теперь являются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="19699-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="19699-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="19699-104">Suggestion</span></span>

<span data-ttu-id="19699-105">Вместо них следует использовать новые интерфейсы API WWF 4.0 (в System.Activities).</span><span class="sxs-lookup"><span data-stu-id="19699-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="19699-106">Пример использования новых интерфейсов API можно найти [здесь](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), а дальнейшие рекомендации доступны [здесь](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span><span class="sxs-lookup"><span data-stu-id="19699-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="19699-107">Кроме того, поскольку API-интерфейсы WWF 3.0 по-прежнему поддерживаются, их можно использовать, а чтобы избежать вывода предупреждения во время построения, его можно подавить или воспользоваться более старой версией компилятора.</span><span class="sxs-lookup"><span data-stu-id="19699-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="19699-108">name</span><span class="sxs-lookup"><span data-stu-id="19699-108">Name</span></span>    | <span data-ttu-id="19699-109">Значение</span><span class="sxs-lookup"><span data-stu-id="19699-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="19699-110">Область</span><span class="sxs-lookup"><span data-stu-id="19699-110">Scope</span></span>   | <span data-ttu-id="19699-111">Значительно</span><span class="sxs-lookup"><span data-stu-id="19699-111">Major</span></span>       |
| <span data-ttu-id="19699-112">Version</span><span class="sxs-lookup"><span data-stu-id="19699-112">Version</span></span> | <span data-ttu-id="19699-113">4.5</span><span class="sxs-lookup"><span data-stu-id="19699-113">4.5</span></span>         |
| <span data-ttu-id="19699-114">Type</span><span class="sxs-lookup"><span data-stu-id="19699-114">Type</span></span>    | <span data-ttu-id="19699-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="19699-115">Retargeting</span></span> |
