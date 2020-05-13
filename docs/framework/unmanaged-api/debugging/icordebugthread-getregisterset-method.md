---
title: Метод ICorDebugThread::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 606453424d34dcb22716c308d210fb257d1c37a7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378867"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="176aa-102">Метод ICorDebugThread::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="176aa-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="176aa-103">Возвращает указатель интерфейса на набор регистров, связанный с активной частью этого объекта ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="176aa-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="176aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="176aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="176aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="176aa-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="176aa-106">заполняет Указатель на адрес объекта интерфейса [ICorDebugRegisterSet](icordebugregisterset-interface.md) , представляющий набор регистров для активной части этого потока.</span><span class="sxs-lookup"><span data-stu-id="176aa-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="176aa-107">Требования</span><span class="sxs-lookup"><span data-stu-id="176aa-107">Requirements</span></span>  
 <span data-ttu-id="176aa-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="176aa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="176aa-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="176aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="176aa-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="176aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="176aa-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="176aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
