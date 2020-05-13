---
title: Интерфейс ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208724"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="f953c-102">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="f953c-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="f953c-103">Предоставляет сведения о сборке после слияния.</span><span class="sxs-lookup"><span data-stu-id="f953c-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f953c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f953c-104">Methods</span></span>  
  
|<span data-ttu-id="f953c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f953c-105">Method</span></span>|<span data-ttu-id="f953c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f953c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f953c-107">Метод GetCulture</span><span class="sxs-lookup"><span data-stu-id="f953c-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="f953c-108">Возвращает строку с названием языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="f953c-109">Метод GetIndex</span><span class="sxs-lookup"><span data-stu-id="f953c-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="f953c-110">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="f953c-111">Метод GetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f953c-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="f953c-112">Возвращает открытый ключ сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="f953c-113">Метод GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="f953c-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="f953c-114">Возвращает токен открытого ключа сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="f953c-115">Метод GetSimpleName</span><span class="sxs-lookup"><span data-stu-id="f953c-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="f953c-116">Получает простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="f953c-117">Метод GetVersion</span><span class="sxs-lookup"><span data-stu-id="f953c-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="f953c-118">Возвращает сведения о версии сборки.</span><span class="sxs-lookup"><span data-stu-id="f953c-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f953c-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="f953c-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f953c-120">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f953c-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f953c-121">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f953c-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f953c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="f953c-122">Requirements</span></span>  
 <span data-ttu-id="f953c-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f953c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f953c-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f953c-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f953c-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f953c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f953c-126">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f953c-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f953c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f953c-127">See also</span></span>

- [<span data-ttu-id="f953c-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f953c-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f953c-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="f953c-129">Debugging</span></span>](index.md)
