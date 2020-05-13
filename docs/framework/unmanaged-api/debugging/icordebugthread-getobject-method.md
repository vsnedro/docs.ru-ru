---
title: Метод ICorDebugThread::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetObject method [.NET Framework debugging]
ms.assetid: 1590febe-96c2-4046-97db-d81d81d67e01
topic_type:
- apiref
ms.openlocfilehash: 624469ca1ae4c96b4143f8768b4c5ff9c2601a2f
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378885"
---
# <a name="icordebugthreadgetobject-method"></a><span data-ttu-id="2fbfc-102">Метод ICorDebugThread::GetObject</span><span class="sxs-lookup"><span data-stu-id="2fbfc-102">ICorDebugThread::GetObject Method</span></span>
<span data-ttu-id="2fbfc-103">Возвращает указатель интерфейса на поток среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2fbfc-103">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fbfc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fbfc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fbfc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2fbfc-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="2fbfc-106">заполняет Указатель на адрес объекта интерфейса ICorDebugValue, который представляет поток среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2fbfc-106">[out] A pointer to the address of an ICorDebugValue interface object that represents the CLR thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fbfc-107">Требования</span><span class="sxs-lookup"><span data-stu-id="2fbfc-107">Requirements</span></span>  
 <span data-ttu-id="2fbfc-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fbfc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fbfc-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fbfc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fbfc-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fbfc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fbfc-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fbfc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fbfc-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2fbfc-112">See also</span></span>

- <xref:System.Threading.Thread>
