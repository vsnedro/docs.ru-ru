---
title: Метод ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: a4d6dd0df9f38561ab5014d7ab65fde6793c9846
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729750"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="639e1-102">Метод ICorDebugEval::NewObject</span><span class="sxs-lookup"><span data-stu-id="639e1-102">ICorDebugEval::NewObject Method</span></span>

<span data-ttu-id="639e1-103">Выделяет новый экземпляр объекта и вызывает указанный метод конструктора.</span><span class="sxs-lookup"><span data-stu-id="639e1-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="639e1-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="639e1-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="639e1-105">Вместо этого используйте [ICorDebugEval2:: невпараметеризедобжект](icordebugeval2-newparameterizedobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="639e1-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639e1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="639e1-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="639e1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="639e1-107">Parameters</span></span>  

 `pConstructor`  
 <span data-ttu-id="639e1-108">окне Вызываемый конструктор.</span><span class="sxs-lookup"><span data-stu-id="639e1-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="639e1-109">[in] Размер массива `ppArgs`.</span><span class="sxs-lookup"><span data-stu-id="639e1-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="639e1-110">окне Массив объектов ICorDebugValue, каждый из которых представляет аргумент, передаваемый конструктору.</span><span class="sxs-lookup"><span data-stu-id="639e1-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639e1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="639e1-111">Requirements</span></span>  

 <span data-ttu-id="639e1-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639e1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639e1-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="639e1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="639e1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="639e1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="639e1-115">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="639e1-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639e1-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="639e1-116">See also</span></span>

- [<span data-ttu-id="639e1-117">Метод NewParameterizedObject</span><span class="sxs-lookup"><span data-stu-id="639e1-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
