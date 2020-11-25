---
title: Интерфейс ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
ms.openlocfilehash: cd6c5726b9a938d04cf4eb018ec9851c81d9c745
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697068"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="cd61f-102">Интерфейс ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="cd61f-102">ICorDebugStringValue Interface</span></span>

<span data-ttu-id="cd61f-103">Подкласс ICorDebugHeapValue, который применяется к строковым значениям.</span><span class="sxs-lookup"><span data-stu-id="cd61f-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd61f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cd61f-104">Methods</span></span>  
  
|<span data-ttu-id="cd61f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cd61f-105">Method</span></span>|<span data-ttu-id="cd61f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cd61f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd61f-107">Метод GetLength</span><span class="sxs-lookup"><span data-stu-id="cd61f-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="cd61f-108">Возвращает число символов в строке, на которую ссылается this `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="cd61f-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="cd61f-109">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="cd61f-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="cd61f-110">Возвращает строку, на которую ссылается this `ICorDebugStringValue` .</span><span class="sxs-lookup"><span data-stu-id="cd61f-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd61f-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="cd61f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd61f-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cd61f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd61f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cd61f-113">Requirements</span></span>  

 <span data-ttu-id="cd61f-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd61f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd61f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd61f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd61f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd61f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd61f-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd61f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd61f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cd61f-118">See also</span></span>

- [<span data-ttu-id="cd61f-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cd61f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
