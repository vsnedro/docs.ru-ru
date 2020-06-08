---
title: Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 7f1276e1adeece086ca7b6791eb6e870faf4d010
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502877"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a><span data-ttu-id="44d07-102">Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs</span><span class="sxs-lookup"><span data-stu-id="44d07-102">ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="44d07-103">Возвращает объект `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.</span><span class="sxs-lookup"><span data-stu-id="44d07-103">Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44d07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44d07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44d07-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="44d07-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="44d07-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `funcDef`  
 <span data-ttu-id="44d07-107">окне `mdMethodDef`Токен метаданных, ссылающийся на функцию.</span><span class="sxs-lookup"><span data-stu-id="44d07-107">[in] An `mdMethodDef` metadata token that references the function.</span></span>  
  
 `classId`  
 <span data-ttu-id="44d07-108">окне Идентификатор содержащего класса функции.</span><span class="sxs-lookup"><span data-stu-id="44d07-108">[in] The ID of the function's containing class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="44d07-109">окне Число параметров типа для данной функции.</span><span class="sxs-lookup"><span data-stu-id="44d07-109">[in] The number of type parameters for the given function.</span></span> <span data-ttu-id="44d07-110">Для неуниверсальных функций это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="44d07-110">This value must be zero for non-generic functions.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="44d07-111">окне Массив `ClassID` значений, каждый из которых является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="44d07-111">[in] An array of `ClassID` values, each of which is an argument of the function.</span></span> <span data-ttu-id="44d07-112">Значение `typeArgs` может быть равно null, если `cTypeArgs` имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="44d07-112">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pFunctionID`  
 <span data-ttu-id="44d07-113">заполняет Указатель на объект `FunctionID` указанной функции.</span><span class="sxs-lookup"><span data-stu-id="44d07-113">[out] A pointer to the `FunctionID` of the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d07-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="44d07-114">Remarks</span></span>  
 <span data-ttu-id="44d07-115">Вызов `GetFunctionFromTokenAndTypeArgs` метода с `mdMethodRef` метаданными вместо `mdMethodDef` токена метаданных может иметь непредсказуемые результаты.</span><span class="sxs-lookup"><span data-stu-id="44d07-115">Calling the `GetFunctionFromTokenAndTypeArgs` method with an `mdMethodRef` metadata instead of an `mdMethodDef` metadata token can have unpredictable results.</span></span> <span data-ttu-id="44d07-116">Вызывающие объекты должны разрешить объект `mdMethodRef` в `mdMethodDef` при передаче.</span><span class="sxs-lookup"><span data-stu-id="44d07-116">Callers should resolve the `mdMethodRef` to an `mdMethodDef` when passing it.</span></span>  
  
 <span data-ttu-id="44d07-117">Если функция еще не загружена, вызов `GetFunctionFromTokenAndTypeArgs` приведет к возникновению загрузки, что является опасной операцией во многих контекстах.</span><span class="sxs-lookup"><span data-stu-id="44d07-117">If the function is not already loaded, calling `GetFunctionFromTokenAndTypeArgs` will cause loading to occur, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="44d07-118">Например, вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.</span><span class="sxs-lookup"><span data-stu-id="44d07-118">For example, calling this method during loading of modules or types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="44d07-119">Как правило, использование параметра `GetFunctionFromTokenAndTypeArgs` не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="44d07-119">In general, use of `GetFunctionFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="44d07-120">Если профилировщики заинтересованы в событиях для определенной функции, они должны хранить и для `ModuleID` `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) для проверки того, является ли заданная `FunctionID` функция требуемой.</span><span class="sxs-lookup"><span data-stu-id="44d07-120">If profilers are interested in events for a particular function, they should store the `ModuleID` and `mdMethodDef` of that function, and use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) to check whether a given `FunctionID` is that of the desired function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d07-121">Требования</span><span class="sxs-lookup"><span data-stu-id="44d07-121">Requirements</span></span>  
 <span data-ttu-id="44d07-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44d07-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d07-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44d07-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44d07-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d07-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44d07-125">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d07-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44d07-126">См. также</span><span class="sxs-lookup"><span data-stu-id="44d07-126">See also</span></span>

- [<span data-ttu-id="44d07-127">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="44d07-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="44d07-128">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="44d07-128">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
