---
title: Метод ICorDebugEval::NewObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: d41216eb7da57d29d67ce17372f746328204649e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976178"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="e0454-102">Метод ICorDebugEval::NewObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="e0454-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="e0454-103">Выделяет новый экземпляр объекта указанного типа без попытки вызова метода конструктора.</span><span class="sxs-lookup"><span data-stu-id="e0454-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="e0454-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e0454-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e0454-105">Вместо этого используйте [ICorDebugEval2:: невпараметеризедобжектноконструктор](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0454-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0454-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0454-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0454-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0454-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="e0454-108">окне Указатель на объект ICorDebugClass, представляющий тип объекта, для которого создается экземпляр.</span><span class="sxs-lookup"><span data-stu-id="e0454-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0454-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e0454-109">Requirements</span></span>  
 <span data-ttu-id="e0454-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0454-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0454-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0454-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0454-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0454-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0454-113">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e0454-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0454-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0454-114">See also</span></span>

- [<span data-ttu-id="e0454-115">Метод NewParameterizedObjectNoConstructor</span><span class="sxs-lookup"><span data-stu-id="e0454-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
