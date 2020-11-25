---
title: Структура COR_PRF_CODE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: b64e58a79f3dbe0c91b0c0cefc4a9d918c700cf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718635"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="a6714-102">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="a6714-102">COR_PRF_CODE_INFO Structure</span></span>

<span data-ttu-id="a6714-103">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="a6714-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6714-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6714-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="a6714-105">Члены</span><span class="sxs-lookup"><span data-stu-id="a6714-105">Members</span></span>  
  
|<span data-ttu-id="a6714-106">Член</span><span class="sxs-lookup"><span data-stu-id="a6714-106">Member</span></span>|<span data-ttu-id="a6714-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a6714-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="a6714-108">Начальный адрес непрерывного блока кода.</span><span class="sxs-lookup"><span data-stu-id="a6714-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="a6714-109">Размер блока.</span><span class="sxs-lookup"><span data-stu-id="a6714-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6714-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a6714-110">Requirements</span></span>  

 <span data-ttu-id="a6714-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6714-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6714-112">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="a6714-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a6714-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6714-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6714-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6714-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6714-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6714-115">See also</span></span>

- [<span data-ttu-id="a6714-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="a6714-116">Profiling Structures</span></span>](profiling-structures.md)
