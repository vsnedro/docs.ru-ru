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
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706753"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="325fe-102">Метод ICorProfilerInfo::GetClassFromToken</span><span class="sxs-lookup"><span data-stu-id="325fe-102">ICorProfilerInfo::GetClassFromToken Method</span></span>

<span data-ttu-id="325fe-103">Возвращает идентификатор класса по заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="325fe-103">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="325fe-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="325fe-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="325fe-105">Вместо этого используйте [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="325fe-105">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325fe-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="325fe-106">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325fe-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="325fe-107">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="325fe-108">окне Идентификатор модуля, содержащего класс.</span><span class="sxs-lookup"><span data-stu-id="325fe-108">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="325fe-109">окне `mdTypeDef` Токен метаданных, ссылающийся на класс.</span><span class="sxs-lookup"><span data-stu-id="325fe-109">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="325fe-110">заполняет Указатель на идентификатор класса.</span><span class="sxs-lookup"><span data-stu-id="325fe-110">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325fe-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="325fe-111">Remarks</span></span>  

 <span data-ttu-id="325fe-112">Этот метод устарел; Вместо этого используйте `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` для всех типов.</span><span class="sxs-lookup"><span data-stu-id="325fe-112">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325fe-113">Требования</span><span class="sxs-lookup"><span data-stu-id="325fe-113">Requirements</span></span>  

 <span data-ttu-id="325fe-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="325fe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="325fe-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="325fe-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="325fe-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="325fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="325fe-117">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="325fe-117">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325fe-118">См. также</span><span class="sxs-lookup"><span data-stu-id="325fe-118">See also</span></span>

- [<span data-ttu-id="325fe-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="325fe-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
