---
title: Метод ICorDebugModule::GetBaseAddress
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetBaseAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetBaseAddress
helpviewer_keywords:
- GetBaseAddress method [.NET Framework debugging]
- ICorDebugModule::GetBaseAddress method [.NET Framework debugging]
ms.assetid: 26a82815-1982-4eb7-92d1-5c3d318d5be4
topic_type:
- apiref
ms.openlocfilehash: 9270afa1d8c8ddd74cfe6dd05e39c1480f5767e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206935"
---
# <a name="icordebugmodulegetbaseaddress-method"></a><span data-ttu-id="8a382-102">Метод ICorDebugModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="8a382-102">ICorDebugModule::GetBaseAddress Method</span></span>
<span data-ttu-id="8a382-103">Возвращает базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="8a382-103">Gets the base address of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a382-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a382-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
    [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a382-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a382-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="8a382-106">заполняет Значение типа `CORDB_ADDRESS` , указывающее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="8a382-106">[out] A `CORDB_ADDRESS` that specifies the base address of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a382-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a382-107">Remarks</span></span>  
 <span data-ttu-id="8a382-108">Если модуль является машинным образом (то есть, если модуль был создан генератором образов в машинном код, NGen. exe), его базовый адрес будет равен нулю.</span><span class="sxs-lookup"><span data-stu-id="8a382-108">If the module is a native image (that is, if the module was produced by the native image generator, NGen.exe), its base address will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a382-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8a382-109">Requirements</span></span>  
 <span data-ttu-id="8a382-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a382-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a382-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a382-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a382-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a382-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a382-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a382-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a382-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8a382-114">See also</span></span>
