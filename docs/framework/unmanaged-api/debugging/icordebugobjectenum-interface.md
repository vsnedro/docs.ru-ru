---
title: Интерфейс ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 0594caf53a889d51ea78e2ee9d6fff4d30f7cff2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205290"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="b3d48-102">Интерфейс ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="b3d48-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="b3d48-103">Реализует методы ICorDebugEnum и перечисляет массивы объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="b3d48-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3d48-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b3d48-104">Methods</span></span>  
  
|<span data-ttu-id="b3d48-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b3d48-105">Method</span></span>|<span data-ttu-id="b3d48-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b3d48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3d48-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b3d48-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="b3d48-108">Возвращает RVA указанного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b3d48-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3d48-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b3d48-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3d48-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b3d48-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3d48-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b3d48-111">Requirements</span></span>  
 <span data-ttu-id="b3d48-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3d48-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3d48-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3d48-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3d48-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3d48-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3d48-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3d48-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d48-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b3d48-116">See also</span></span>

- [<span data-ttu-id="b3d48-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b3d48-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
