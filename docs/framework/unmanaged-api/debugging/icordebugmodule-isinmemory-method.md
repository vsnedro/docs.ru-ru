---
title: Метод ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709821"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="8a15d-102">Метод ICorDebugModule::IsInMemory</span><span class="sxs-lookup"><span data-stu-id="8a15d-102">ICorDebugModule::IsInMemory Method</span></span>

<span data-ttu-id="8a15d-103">Возвращает значение, указывающее, существует ли этот модуль только в памяти.</span><span class="sxs-lookup"><span data-stu-id="8a15d-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a15d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a15d-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a15d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a15d-105">Parameters</span></span>  

 `pInMemory`  
 <span data-ttu-id="8a15d-106">[out] `true` значение, если этот модуль существует только в памяти; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="8a15d-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a15d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8a15d-107">Remarks</span></span>  

 <span data-ttu-id="8a15d-108">Среда CLR поддерживает загрузку модулей из необработанных потоков байтов.</span><span class="sxs-lookup"><span data-stu-id="8a15d-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="8a15d-109">Такие модули называются *модулями в памяти* и не существуют на диске.</span><span class="sxs-lookup"><span data-stu-id="8a15d-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a15d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8a15d-110">Requirements</span></span>  

 <span data-ttu-id="8a15d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a15d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a15d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a15d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a15d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a15d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a15d-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a15d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a15d-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a15d-115">See also</span></span>
