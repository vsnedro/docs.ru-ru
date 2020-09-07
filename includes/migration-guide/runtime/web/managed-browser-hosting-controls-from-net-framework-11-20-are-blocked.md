---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496612"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="52a2b-101">Элементы управления Managed Browser в .NET Framework 1.1 и 2.0 заблокированы</span><span class="sxs-lookup"><span data-stu-id="52a2b-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="52a2b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="52a2b-102">Details</span></span>

<span data-ttu-id="52a2b-103">Размещение этих элементов управления в Internet Explorer блокируется.</span><span class="sxs-lookup"><span data-stu-id="52a2b-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="52a2b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="52a2b-104">Suggestion</span></span>

<span data-ttu-id="52a2b-105">Internet Explorer не сможет запустить приложение, в котором используются управляемые элементы управления, размещенные в браузере.</span><span class="sxs-lookup"><span data-stu-id="52a2b-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="52a2b-106">Прежнее поведение можно восстановить путем установки параметру EnableIEHosting подраздела реестра <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> значения <code>1</code> для систем x86 и для 32-разрядных процессов в системах x64, а также путем установки параметру <code>EnableIEHosting</code> подраздела реестра <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> значения <code>1</code> для 64-разрядных процессов в системах x64.</span><span class="sxs-lookup"><span data-stu-id="52a2b-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="52a2b-107">name</span><span class="sxs-lookup"><span data-stu-id="52a2b-107">Name</span></span>    | <span data-ttu-id="52a2b-108">Значение</span><span class="sxs-lookup"><span data-stu-id="52a2b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="52a2b-109">Область</span><span class="sxs-lookup"><span data-stu-id="52a2b-109">Scope</span></span>   |<span data-ttu-id="52a2b-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="52a2b-110">Minor</span></span>|
|<span data-ttu-id="52a2b-111">Version</span><span class="sxs-lookup"><span data-stu-id="52a2b-111">Version</span></span>|<span data-ttu-id="52a2b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="52a2b-112">4.5</span></span>|
|<span data-ttu-id="52a2b-113">Type</span><span class="sxs-lookup"><span data-stu-id="52a2b-113">Type</span></span>|<span data-ttu-id="52a2b-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="52a2b-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="52a2b-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="52a2b-115">Affected APIs</span></span>

<span data-ttu-id="52a2b-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="52a2b-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
