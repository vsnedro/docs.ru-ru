---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616087"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="8f9fc-101">WorkflowDesigner.Load не удаляет свойство символа</span><span class="sxs-lookup"><span data-stu-id="8f9fc-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="8f9fc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8f9fc-102">Details</span></span>

<span data-ttu-id="8f9fc-103">При выборе целевой версии платформы .NET Framework 4.5 в конструкторе рабочих процессов и загрузке повторно размещаемого рабочего процесса 3.5 с помощью метода <xref:System.Activities.Presentation.WorkflowDesigner.Load> во время сохранения рабочего процесса создается исключение <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8f9fc-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8f9fc-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="8f9fc-104">Suggestion</span></span>

<span data-ttu-id="8f9fc-105">Эта ошибка возникает только при нацеливании на .NET Framework 4.5 в конструкторе рабочих процессов, поэтому ее можно устранить, установив `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` в 4.0 .NET Framework. Этой проблемы можно избежать, если использовать метод <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> для загрузки рабочего процесса вместо <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="8f9fc-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="8f9fc-106">name</span><span class="sxs-lookup"><span data-stu-id="8f9fc-106">Name</span></span>    | <span data-ttu-id="8f9fc-107">Значение</span><span class="sxs-lookup"><span data-stu-id="8f9fc-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8f9fc-108">Область</span><span class="sxs-lookup"><span data-stu-id="8f9fc-108">Scope</span></span>   | <span data-ttu-id="8f9fc-109">Значительно</span><span class="sxs-lookup"><span data-stu-id="8f9fc-109">Major</span></span>       |
| <span data-ttu-id="8f9fc-110">Version</span><span class="sxs-lookup"><span data-stu-id="8f9fc-110">Version</span></span> | <span data-ttu-id="8f9fc-111">4.5</span><span class="sxs-lookup"><span data-stu-id="8f9fc-111">4.5</span></span>         |
| <span data-ttu-id="8f9fc-112">Type</span><span class="sxs-lookup"><span data-stu-id="8f9fc-112">Type</span></span>    | <span data-ttu-id="8f9fc-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="8f9fc-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8f9fc-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8f9fc-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
