---
title: Метод ICorDebugProcess::EnumerateAppDomains
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: 748a44075f7f73e54bab689bcb8865dee2b14946
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207840"
---
# <a name="icordebugprocessenumerateappdomains-method"></a><span data-ttu-id="8209f-102">Метод ICorDebugProcess::EnumerateAppDomains</span><span class="sxs-lookup"><span data-stu-id="8209f-102">ICorDebugProcess::EnumerateAppDomains Method</span></span>
<span data-ttu-id="8209f-103">Перечисляет все домены приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="8209f-103">Enumerates all the application domains in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8209f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8209f-104">Syntax</span></span>  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8209f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8209f-105">Parameters</span></span>  
 `ppAppDomains`  
 <span data-ttu-id="8209f-106">заполняет Указатель на адрес [икордебугаппдомаиненум](icordebugappdomainenum-interface.md) , который является перечислителем для доменов приложений в этом процессе.</span><span class="sxs-lookup"><span data-stu-id="8209f-106">[out] A pointer to the address of an [ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md) that is an enumerator for the application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8209f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8209f-107">Remarks</span></span>  
 <span data-ttu-id="8209f-108">Этот метод можно использовать перед обратным вызовом [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8209f-108">This method can be used before the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8209f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8209f-109">Requirements</span></span>  
 <span data-ttu-id="8209f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8209f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8209f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8209f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8209f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8209f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8209f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8209f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
