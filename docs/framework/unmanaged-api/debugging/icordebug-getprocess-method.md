---
title: Метод ICorDebug::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: 46c2b444984c5a0062f1cfbc0cd29dbe409b16fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723445"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="b9fa6-102">Метод ICorDebug::GetProcess</span><span class="sxs-lookup"><span data-stu-id="b9fa6-102">ICorDebug::GetProcess Method</span></span>

<span data-ttu-id="b9fa6-103">Возвращает указатель на экземпляр "ICorDebugProcess" для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="b9fa6-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9fa6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9fa6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9fa6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9fa6-105">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="b9fa6-106">окне Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="b9fa6-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b9fa6-107">заполняет Указатель на адрес `ICorDebugProcess` экземпляра для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="b9fa6-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9fa6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b9fa6-108">Requirements</span></span>  

 <span data-ttu-id="b9fa6-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9fa6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9fa6-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9fa6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9fa6-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9fa6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9fa6-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fa6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fa6-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b9fa6-113">See also</span></span>

- [<span data-ttu-id="b9fa6-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="b9fa6-114">ICorDebug Interface</span></span>](icordebug-interface.md)
