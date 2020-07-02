---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620672"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="fa815-101">Элементы управления Managed Browser в .NET Framework 1.1 и 2.0 заблокированы</span><span class="sxs-lookup"><span data-stu-id="fa815-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="fa815-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="fa815-102">Details</span></span>

<span data-ttu-id="fa815-103">Размещение этих элементов управления в Internet Explorer блокируется.</span><span class="sxs-lookup"><span data-stu-id="fa815-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fa815-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="fa815-104">Suggestion</span></span>

<span data-ttu-id="fa815-105">Internet Explorer не сможет запустить приложение, в котором используются управляемые элементы управления, размещенные в браузере.</span><span class="sxs-lookup"><span data-stu-id="fa815-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="fa815-106">Прежнее поведение можно восстановить путем установки параметру EnableIEHosting подраздела реестра <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> значения <code>1</code> для систем x86 и для 32-разрядных процессов в системах x64, а также путем установки параметру <code>EnableIEHosting</code> подраздела реестра <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> значения <code>1</code> для 64-разрядных процессов в системах x64.</span><span class="sxs-lookup"><span data-stu-id="fa815-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="fa815-107">name</span><span class="sxs-lookup"><span data-stu-id="fa815-107">Name</span></span>    | <span data-ttu-id="fa815-108">Значение</span><span class="sxs-lookup"><span data-stu-id="fa815-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fa815-109">Область</span><span class="sxs-lookup"><span data-stu-id="fa815-109">Scope</span></span>   |<span data-ttu-id="fa815-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="fa815-110">Minor</span></span>|
|<span data-ttu-id="fa815-111">Version</span><span class="sxs-lookup"><span data-stu-id="fa815-111">Version</span></span>|<span data-ttu-id="fa815-112">4.5</span><span class="sxs-lookup"><span data-stu-id="fa815-112">4.5</span></span>|
|<span data-ttu-id="fa815-113">Type</span><span class="sxs-lookup"><span data-stu-id="fa815-113">Type</span></span>|<span data-ttu-id="fa815-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="fa815-114">Runtime</span></span>|
