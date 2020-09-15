---
ms.openlocfilehash: 863e7035827537e0f943af05c2f0232029b99db8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617271"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="3550b-101">Версия Entity Framework должна соответствовать версии .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3550b-101">Entity Framework version must match the .NET Framework version</span></span>

#### <a name="details"></a><span data-ttu-id="3550b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="3550b-102">Details</span></span>

<span data-ttu-id="3550b-103">Версия Entity Framework (EF) должна соответствовать версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3550b-103">The Entity Framework (EF) version should be matched with the .NET Framework version.</span></span> <span data-ttu-id="3550b-104">Для .NET Framework 4.5 рекомендуется Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="3550b-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="3550b-105">Существуют некоторые известные проблемы с EF 4.x в проекте .NET Framework 4.5, связанные с <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="3550b-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="3550b-106">В .NET Framework 4.5 они были перемещены в другую сборку, поэтому существуют проблемы с выбором заметок для использования.</span><span class="sxs-lookup"><span data-stu-id="3550b-106">In .NET Framework 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3550b-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="3550b-107">Suggestion</span></span>

<span data-ttu-id="3550b-108">Обновление до версии Entity Framework 5 для .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3550b-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>

| <span data-ttu-id="3550b-109">name</span><span class="sxs-lookup"><span data-stu-id="3550b-109">Name</span></span>    | <span data-ttu-id="3550b-110">Значение</span><span class="sxs-lookup"><span data-stu-id="3550b-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3550b-111">Область</span><span class="sxs-lookup"><span data-stu-id="3550b-111">Scope</span></span>   | <span data-ttu-id="3550b-112">Значительно</span><span class="sxs-lookup"><span data-stu-id="3550b-112">Major</span></span>       |
| <span data-ttu-id="3550b-113">Version</span><span class="sxs-lookup"><span data-stu-id="3550b-113">Version</span></span> | <span data-ttu-id="3550b-114">4.5</span><span class="sxs-lookup"><span data-stu-id="3550b-114">4.5</span></span>         |
| <span data-ttu-id="3550b-115">Type</span><span class="sxs-lookup"><span data-stu-id="3550b-115">Type</span></span>    | <span data-ttu-id="3550b-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="3550b-116">Retargeting</span></span> |
