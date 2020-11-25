---
title: Метод ICorDebugModule2::GetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
ms.openlocfilehash: c443fba711a3d122ed5f8f1566a220c79211631e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709691"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="9f7e8-102">Метод ICorDebugModule2::GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9f7e8-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>

<span data-ttu-id="9f7e8-103">Возвращает флаги, управляющие JIT-компиляцией этого ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="9f7e8-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f7e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f7e8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f7e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f7e8-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="9f7e8-106">заполняет Указатель на значение перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , которое управляет JIT-компиляцией.</span><span class="sxs-lookup"><span data-stu-id="9f7e8-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f7e8-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9f7e8-107">Requirements</span></span>  

 <span data-ttu-id="9f7e8-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f7e8-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f7e8-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f7e8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f7e8-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f7e8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f7e8-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f7e8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
