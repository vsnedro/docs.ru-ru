---
title: Метод ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 12b4b897f9dc51175037d39c0368b6ce59fefefb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498483"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="f39e8-102">Метод ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="f39e8-102">ICorProfilerInfo::GetClassFromToken Method</span></span>
<span data-ttu-id="f39e8-103">Возвращает идентификатор класса по заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="f39e8-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="f39e8-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="f39e8-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f39e8-105">Вместо этого используйте [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f39e8-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f39e8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f39e8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f39e8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f39e8-107">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f39e8-108">окне Идентификатор модуля, содержащего класс.</span><span class="sxs-lookup"><span data-stu-id="f39e8-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="f39e8-109">окне `mdTypeDef`Токен метаданных, ссылающийся на класс.</span><span class="sxs-lookup"><span data-stu-id="f39e8-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="f39e8-110">заполняет Указатель на идентификатор класса.</span><span class="sxs-lookup"><span data-stu-id="f39e8-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f39e8-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f39e8-111">Remarks</span></span>  
 <span data-ttu-id="f39e8-112">Этот метод устарел; Вместо этого используйте `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="f39e8-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f39e8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f39e8-113">Requirements</span></span>  
 <span data-ttu-id="f39e8-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f39e8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f39e8-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f39e8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f39e8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f39e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f39e8-117">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="f39e8-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f39e8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f39e8-118">See also</span></span>

- [<span data-ttu-id="f39e8-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f39e8-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
