---
title: Перечисление ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
ms.openlocfilehash: 6c6fab627f21977e85f9885ca4b49a0276faa5ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732168"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="fdfdb-102">Перечисление ASM_CACHE_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fdfdb-102">ASM_CACHE_FLAGS Enumeration</span></span>

<span data-ttu-id="fdfdb-103">Указывает источник сборки, представленной [IAssemblyCacheItem](iassemblycacheitem-interface.md) в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfdb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdfdb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="fdfdb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="fdfdb-105">Members</span></span>  
  
|<span data-ttu-id="fdfdb-106">Член</span><span class="sxs-lookup"><span data-stu-id="fdfdb-106">Member</span></span>|<span data-ttu-id="fdfdb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fdfdb-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="fdfdb-108">Перечисляет кэш предварительно скомпилированных сборок с помощью Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="fdfdb-109">Перечисляет глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="fdfdb-110">Перечисляет сборки, скачанные по запросу или теневые копии.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="fdfdb-111">Указывает, что функция [жеткачепас](getcachepath-function.md) должна возвращать путь к глобальному кэшу сборок для общеязыковой среды выполнения (CLR) версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="fdfdb-112">Имеет смысл только в контексте вызова [жеткачепас](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="fdfdb-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="fdfdb-113">Указывает, что функция [жеткачепас](getcachepath-function.md) должна возвращать путь к глобальному кэшу сборок для CLR версии 4.</span><span class="sxs-lookup"><span data-stu-id="fdfdb-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="fdfdb-114">Имеет смысл только в контексте вызова [жеткачепас](getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="fdfdb-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fdfdb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="fdfdb-115">Requirements</span></span>  

 <span data-ttu-id="fdfdb-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdfdb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdfdb-117">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fdfdb-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fdfdb-118">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdfdb-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdfdb-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdfdb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfdb-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fdfdb-120">See also</span></span>

- [<span data-ttu-id="fdfdb-121">Функция GetCachePath</span><span class="sxs-lookup"><span data-stu-id="fdfdb-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="fdfdb-122">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="fdfdb-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="fdfdb-123">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="fdfdb-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
