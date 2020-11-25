---
title: Интерфейс ICorProfilerInfo9
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 3d1cdfa56e6bb20f08370aa76b87d516f7b51cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732961"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="def8a-102">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="def8a-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="def8a-103">Подкласс [ICorProfilerInfo8](icorprofilerinfo8-interface.md) , предоставляющий методы для запроса сведений о функциях с несколькими версиями машинного кода.</span><span class="sxs-lookup"><span data-stu-id="def8a-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="def8a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="def8a-104">Methods</span></span>  

| <span data-ttu-id="def8a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="def8a-105">Method</span></span>|<span data-ttu-id="def8a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="def8a-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="def8a-107">Метод GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="def8a-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="def8a-108">При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.</span><span class="sxs-lookup"><span data-stu-id="def8a-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="def8a-109">Метод GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="def8a-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="def8a-110">С учетом начального адреса машинного кода возвращает сведения о сопоставлении IL для этой откомпилированной версии кода.</span><span class="sxs-lookup"><span data-stu-id="def8a-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="def8a-111">Метод GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="def8a-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="def8a-112">При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.</span><span class="sxs-lookup"><span data-stu-id="def8a-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="def8a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="def8a-113">Requirements</span></span>  

<span data-ttu-id="def8a-114">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="def8a-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="def8a-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="def8a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="def8a-116">**Версии .NET:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def8a-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="def8a-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="def8a-117">See also</span></span>

- [<span data-ttu-id="def8a-118">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="def8a-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
