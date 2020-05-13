---
title: Метод ICorDebugRegisterSet::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378281"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="2e6ee-102">Метод ICorDebugRegisterSet::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="2e6ee-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="2e6ee-103">Возвращает контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="2e6ee-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e6ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e6ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e6ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e6ee-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="2e6ee-106">окне Размер массива в байтах `context` .</span><span class="sxs-lookup"><span data-stu-id="2e6ee-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="2e6ee-107">[вход, выход] Массив байтов, образующих `CONTEXT` структуру Win32 для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="2e6ee-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e6ee-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e6ee-108">Remarks</span></span>  
 <span data-ttu-id="2e6ee-109">Отладчик должен вызвать эту функцию вместо `GetThreadContext` функции Win32, так как поток может находиться в состоянии "перехвачено", в котором его контекст был временно изменен.</span><span class="sxs-lookup"><span data-stu-id="2e6ee-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="2e6ee-110">Возвращаемые данные представляют собой `CONTEXT` структуру Win32 для текущей платформы.</span><span class="sxs-lookup"><span data-stu-id="2e6ee-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="2e6ee-111">Для неконечных кадров клиенты должны проверить, какие регистры являются допустимыми с помощью [ICorDebugRegisterSet:: жетрегистерсаваилабле](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="2e6ee-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e6ee-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2e6ee-112">Requirements</span></span>  
 <span data-ttu-id="2e6ee-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e6ee-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6ee-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e6ee-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e6ee-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e6ee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e6ee-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e6ee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6ee-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2e6ee-117">See also</span></span>

- [<span data-ttu-id="2e6ee-118">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="2e6ee-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="2e6ee-119">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="2e6ee-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
