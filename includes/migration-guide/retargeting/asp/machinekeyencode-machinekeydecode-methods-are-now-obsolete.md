---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617265"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="a6447-101">Методы MachineKey.Encode и MachineKey.Decode устарели</span><span class="sxs-lookup"><span data-stu-id="a6447-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="a6447-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="a6447-102">Details</span></span>

<span data-ttu-id="a6447-103">В настоящее время эти методы считаются устаревшими.</span><span class="sxs-lookup"><span data-stu-id="a6447-103">These methods are now obsolete.</span></span> <span data-ttu-id="a6447-104">При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.</span><span class="sxs-lookup"><span data-stu-id="a6447-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a6447-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="a6447-105">Suggestion</span></span>

<span data-ttu-id="a6447-106">Взамен рекомендуется использовать <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> и <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="a6447-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="a6447-107">Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="a6447-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="a6447-108">Интерфейсы API по-прежнему поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a6447-108">The APIs are still supported.</span></span>

| <span data-ttu-id="a6447-109">name</span><span class="sxs-lookup"><span data-stu-id="a6447-109">Name</span></span>    | <span data-ttu-id="a6447-110">Значение</span><span class="sxs-lookup"><span data-stu-id="a6447-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a6447-111">Область</span><span class="sxs-lookup"><span data-stu-id="a6447-111">Scope</span></span>   | <span data-ttu-id="a6447-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="a6447-112">Minor</span></span>       |
| <span data-ttu-id="a6447-113">Version</span><span class="sxs-lookup"><span data-stu-id="a6447-113">Version</span></span> | <span data-ttu-id="a6447-114">4.5</span><span class="sxs-lookup"><span data-stu-id="a6447-114">4.5</span></span>         |
| <span data-ttu-id="a6447-115">Type</span><span class="sxs-lookup"><span data-stu-id="a6447-115">Type</span></span>    | <span data-ttu-id="a6447-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="a6447-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a6447-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a6447-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
