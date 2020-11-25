---
title: Интерфейс ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: cfa0950ca2ef4e969258c147b762fa95e52a82e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705824"
---
# <a name="icordebuggenericvalue-interface"></a><span data-ttu-id="51d56-102">Интерфейс ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="51d56-102">ICorDebugGenericValue Interface</span></span>

<span data-ttu-id="51d56-103">Подкласс "ICorDebugValue", который применяется ко всем значениям.</span><span class="sxs-lookup"><span data-stu-id="51d56-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="51d56-104">Этот интерфейс предоставляет для значения методы Get и Set.</span><span class="sxs-lookup"><span data-stu-id="51d56-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51d56-105">Методы</span><span class="sxs-lookup"><span data-stu-id="51d56-105">Methods</span></span>  
  
|<span data-ttu-id="51d56-106">Метод</span><span class="sxs-lookup"><span data-stu-id="51d56-106">Method</span></span>|<span data-ttu-id="51d56-107">Описание</span><span class="sxs-lookup"><span data-stu-id="51d56-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51d56-108">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="51d56-108">GetValue Method</span></span>](icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="51d56-109">Копирует значение в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="51d56-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="51d56-110">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="51d56-110">SetValue Method</span></span>](icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="51d56-111">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="51d56-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51d56-112">Комментарии</span><span class="sxs-lookup"><span data-stu-id="51d56-112">Remarks</span></span>  

 <span data-ttu-id="51d56-113">`ICorDebugGenericValue` является подинтерфейсом, так как он не является удаленным.</span><span class="sxs-lookup"><span data-stu-id="51d56-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="51d56-114">Для ссылочных типов значение является ссылкой, а не содержимым ссылки.</span><span class="sxs-lookup"><span data-stu-id="51d56-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="51d56-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="51d56-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51d56-116">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="51d56-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51d56-117">Требования</span><span class="sxs-lookup"><span data-stu-id="51d56-117">Requirements</span></span>  

 <span data-ttu-id="51d56-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51d56-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d56-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51d56-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51d56-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51d56-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51d56-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d56-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d56-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="51d56-122">See also</span></span>

- [<span data-ttu-id="51d56-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="51d56-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
