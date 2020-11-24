---
title: Метод ICorPublishProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
ms.openlocfilehash: 9965a468f788efead0477bb7574ef3bf156fd869
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692479"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="c7a9f-102">Метод ICorPublishProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c7a9f-102">ICorPublishProcessEnum::Next Method</span></span>

<span data-ttu-id="c7a9f-103">Возвращает указанное количество процессов из коллекции, начиная с текущего положения курсора.</span><span class="sxs-lookup"><span data-stu-id="c7a9f-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a9f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7a9f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7a9f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7a9f-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c7a9f-106">окне Число процессов для извлечения.</span><span class="sxs-lookup"><span data-stu-id="c7a9f-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c7a9f-107">заполняет Указатель на массив полученных объектов [ICorPublishProcess](icorpublishprocess-interface.md) , каждый из которых представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="c7a9f-107">[out] A pointer to the array of retrieved [ICorPublishProcess](icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c7a9f-108">заполняет Указатель на число фактически возвращенных процессов.</span><span class="sxs-lookup"><span data-stu-id="c7a9f-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="c7a9f-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="c7a9f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a9f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c7a9f-110">Requirements</span></span>  

 <span data-ttu-id="c7a9f-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7a9f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7a9f-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="c7a9f-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c7a9f-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7a9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7a9f-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7a9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7a9f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7a9f-115">See also</span></span>

- [<span data-ttu-id="c7a9f-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c7a9f-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)
