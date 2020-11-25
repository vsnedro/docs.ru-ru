---
title: Метод ICorProfilerInfo::GetFunctionInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: 6aaa02d72dd10fe72d773246d55216143786dabb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722548"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="ad93c-102">Метод ICorProfilerInfo::GetFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="ad93c-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>

<span data-ttu-id="ad93c-103">Возвращает родительский класс и токен метаданных для указанной функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad93c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad93c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad93c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad93c-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="ad93c-106">окне Идентификатор функции, для которой необходимо получить родительский класс и маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="ad93c-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="ad93c-107">[выходной] Указатель на родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ad93c-108">[выходной] Указатель на модуль, в котором определен родительский класс функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="ad93c-109">[выходной] Указатель на токен метаданных функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad93c-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ad93c-110">Remarks</span></span>  

 <span data-ttu-id="ad93c-111">Чтобы получить интерфейс метаданных для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ad93c-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="ad93c-112">Токен метаданных, возвращенный в расположение, на которое ссылается `pToken`, можно впоследствии использовать для доступа к метаданным функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="ad93c-113">`ClassID`Функция в универсальном классе может быть недоступна без более контекстной информации об использовании функции.</span><span class="sxs-lookup"><span data-stu-id="ad93c-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="ad93c-114">В этом случае `pClassId` будет иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="ad93c-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="ad93c-115">Для предоставления большего контекста в коде профилировщика следует использовать [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) со значением COR_PRF_FRAME_INFO.</span><span class="sxs-lookup"><span data-stu-id="ad93c-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad93c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ad93c-116">Requirements</span></span>  

 <span data-ttu-id="ad93c-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad93c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad93c-118">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad93c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad93c-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad93c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad93c-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad93c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad93c-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ad93c-121">See also</span></span>

- [<span data-ttu-id="ad93c-122">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="ad93c-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
