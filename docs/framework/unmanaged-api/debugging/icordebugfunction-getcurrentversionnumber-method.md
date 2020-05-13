---
title: Метод ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
ms.openlocfilehash: b47580022b98ea02584a94b3f74b3fd1c276f297
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212910"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="194ef-102">Метод ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="194ef-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="194ef-103">Возвращает номер версии последнего изменения, внесенного в функцию, представленную этим объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="194ef-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="194ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="194ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="194ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="194ef-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="194ef-106">заполняет Указатель на целочисленное значение, которое является номером версии последнего изменения, внесенного в эту функцию.</span><span class="sxs-lookup"><span data-stu-id="194ef-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="194ef-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="194ef-107">Remarks</span></span>  
 <span data-ttu-id="194ef-108">Номер версии последнего изменения, внесенного в эту функцию, может быть больше номера версии самой функции.</span><span class="sxs-lookup"><span data-stu-id="194ef-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="194ef-109">Для получения номера версии функции используйте метод [ICorDebugFunction2:: жетверсионнумбер](icordebugfunction2-getversionnumber-method.md) или метод [ICorDebugCode:: жетверсионнумбер](icordebugcode-getversionnumber-method.md) .</span><span class="sxs-lookup"><span data-stu-id="194ef-109">Use either the [ICorDebugFunction2::GetVersionNumber](icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="194ef-110">Требования</span><span class="sxs-lookup"><span data-stu-id="194ef-110">Requirements</span></span>  
 <span data-ttu-id="194ef-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="194ef-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="194ef-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="194ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="194ef-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="194ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="194ef-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="194ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
