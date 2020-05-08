---
title: Метод ICorDebugAppDomain::EnumerateSteppers
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
ms.openlocfilehash: a46d1b4ebf84514a77e62a4108f6aa34cd2dd94e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895267"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="31be1-102">Метод ICorDebugAppDomain::EnumerateSteppers</span><span class="sxs-lookup"><span data-stu-id="31be1-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="31be1-103">Возвращает перечислитель для всех активных шагов в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="31be1-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31be1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31be1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31be1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="31be1-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="31be1-106">заполняет Указатель на адрес объекта Икордебугстепперенум, который является перечислителем для всех активных шагов в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="31be1-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31be1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="31be1-107">Requirements</span></span>  
 <span data-ttu-id="31be1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31be1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31be1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31be1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31be1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31be1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31be1-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31be1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
