---
title: Структура COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 7c7d447afcb5a8617aa92212f3325719d5f43bf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718622"
---
# <a name="cor_prf_assembly_reference_info-structure"></a><span data-ttu-id="0fe6b-102">Структура COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="0fe6b-102">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>

<span data-ttu-id="0fe6b-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="0fe6b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0fe6b-104">Обеспечивает среду CLR информацией о ссылке на сборку, которую ей следует учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-104">Provides the common language runtime with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe6b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fe6b-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0fe6b-106">Члены</span><span class="sxs-lookup"><span data-stu-id="0fe6b-106">Members</span></span>  
  
|<span data-ttu-id="0fe6b-107">Член</span><span class="sxs-lookup"><span data-stu-id="0fe6b-107">Member</span></span>|<span data-ttu-id="0fe6b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="0fe6b-108">Description</span></span>|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|<span data-ttu-id="0fe6b-109">Указатель на открытый ключ или маркер сборки.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-109">A pointer to the public key or token of the assembly.</span></span>|  
|`cbPublicKeyOrToken`|<span data-ttu-id="0fe6b-110">Количество байтов в открытом ключе или маркере.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-110">The number of bytes in the public key or token.</span></span>|  
|`szName`|<span data-ttu-id="0fe6b-111">Имя сборки, на которую дается ссылка.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-111">The name of the assembly that is referenced.</span></span>|  
|`pMetaData`|<span data-ttu-id="0fe6b-112">Указатель на метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-112">A pointer to the assembly's metadata.</span></span>|  
|`pbHashValue`|<span data-ttu-id="0fe6b-113">Указатель на хэшированный большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-113">A pointer to a hash binary large object (BLOB).</span></span>|  
|`cbHashValue`|<span data-ttu-id="0fe6b-114">Количество байтов в хэшированном BLOB.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-114">The number of bytes in the hash BLOB.</span></span>|  
|`dwAssemblyRefFlags`|<span data-ttu-id="0fe6b-115">Флаги сборки.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-115">The assembly's flags.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fe6b-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0fe6b-116">Remarks</span></span>  

 <span data-ttu-id="0fe6b-117">Структура `COR_PRF_EX_CLAUSE_INFO` заполняется профилировщиком при его объявлении дополнительных ссылок на сборку, которые среда CLR должна учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-117">The `COR_PRF_EX_CLAUSE_INFO` structure is populated by the profiler when it declares additional assembly references that the common language runtime should consider when performing an assembly reference closure walk.</span></span>  
  
 <span data-ttu-id="0fe6b-118">Если профилировщик регистрируется для метода обратного вызова [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , среда выполнения передает путь и имя загружаемой сборки вместе с указателем на объект интерфейса [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) для этого метода.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-118">If the profiler registers for the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback method, the runtime passes the path and name of the assembly to be loaded, along with a pointer to an [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object to that method.</span></span> <span data-ttu-id="0fe6b-119">Затем профилировщик может вызвать метод [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) с `COR_PRF_ASSEMBLY_REFERENCE_INFO` объектом для каждой целевой сборки, на которую планируется ссылаться из сборки, указанной в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0fe6b-119">The profiler can then call the [ICorProfilerAssemblyReferenceProvider::AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) method with a `COR_PRF_ASSEMBLY_REFERENCE_INFO` object for each target assembly it plans to reference from the assembly specified in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe6b-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0fe6b-120">Requirements</span></span>  

 <span data-ttu-id="0fe6b-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe6b-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fe6b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fe6b-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fe6b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fe6b-124">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe6b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe6b-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0fe6b-125">See also</span></span>

- [<span data-ttu-id="0fe6b-126">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="0fe6b-126">Profiling Structures</span></span>](profiling-structures.md)
- [<span data-ttu-id="0fe6b-127">Метод GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="0fe6b-127">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="0fe6b-128">Метод AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="0fe6b-128">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
