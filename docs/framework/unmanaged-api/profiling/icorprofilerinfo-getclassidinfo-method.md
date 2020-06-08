---
title: Метод ICorProfilerInfo::GetClassIDInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 4fbee938ae86b338f2beb0b48feeee46f144a4a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498509"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="963ff-102">Метод ICorProfilerInfo::GetClassIDInfo</span><span class="sxs-lookup"><span data-stu-id="963ff-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="963ff-103">Возвращает родительский модуль и маркер метаданных для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="963ff-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="963ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="963ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="963ff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="963ff-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="963ff-106">окне Идентификатор класса, для которого необходимо получить сведения.</span><span class="sxs-lookup"><span data-stu-id="963ff-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="963ff-107">заполняет Указатель на идентификатор родительского модуля класса.</span><span class="sxs-lookup"><span data-stu-id="963ff-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="963ff-108">заполняет Указатель на маркер метаданных для класса.</span><span class="sxs-lookup"><span data-stu-id="963ff-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="963ff-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="963ff-109">Remarks</span></span>  
 <span data-ttu-id="963ff-110">Чтобы получить интерфейс метаданных для заданного модуля, код профилировщика может вызвать метод [ICorProfilerInfo:: жетмодулеметадата](icorprofilerinfo-getmodulemetadata-method.md) .</span><span class="sxs-lookup"><span data-stu-id="963ff-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="963ff-111">Токен метаданных, возвращенный в расположение, на которое ссылается `pTypeDefToken`, можно впоследствии использовать для доступа к метаданным класса.</span><span class="sxs-lookup"><span data-stu-id="963ff-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="963ff-112">Чтобы получить дополнительные сведения для универсальных типов, используйте [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="963ff-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="963ff-113">Требования</span><span class="sxs-lookup"><span data-stu-id="963ff-113">Requirements</span></span>  
 <span data-ttu-id="963ff-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="963ff-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="963ff-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="963ff-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="963ff-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="963ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="963ff-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="963ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="963ff-118">См. также</span><span class="sxs-lookup"><span data-stu-id="963ff-118">See also</span></span>

- [<span data-ttu-id="963ff-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="963ff-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
