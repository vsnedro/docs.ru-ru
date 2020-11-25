---
title: Метод ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 1713623fa575bea6df649106b37212f7aeaee6db
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723471"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="ce23d-102">Метод ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="ce23d-102">ICorDebug::DebugActiveProcess Method</span></span>

<span data-ttu-id="ce23d-103">Присоединяет отладчик к существующему процессу.</span><span class="sxs-lookup"><span data-stu-id="ce23d-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce23d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce23d-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce23d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce23d-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="ce23d-106">окне Идентификатор процесса, к которому должен быть присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="ce23d-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="ce23d-107">окне Логическое значение, которое устанавливается в, `true` Если отладчик должен вести себя в качестве отладчика Win32 для процесса и отправляют неуправляемые обратные вызовы. в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="ce23d-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="ce23d-108">заполняет Указатель на адрес объекта "ICorDebugProcess", который представляет процесс, к которому присоединен отладчик.</span><span class="sxs-lookup"><span data-stu-id="ce23d-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce23d-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ce23d-109">Remarks</span></span>  

 <span data-ttu-id="ce23d-110">Отладка взаимодействия не поддерживается на платформах Win9x и на платформе, отличной от x86, например на платформах на основе IA-64 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="ce23d-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce23d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ce23d-111">Requirements</span></span>  

 <span data-ttu-id="ce23d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce23d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce23d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce23d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce23d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce23d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce23d-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce23d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce23d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce23d-116">See also</span></span>

- [<span data-ttu-id="ce23d-117">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="ce23d-117">ICorDebug Interface</span></span>](icordebug-interface.md)
