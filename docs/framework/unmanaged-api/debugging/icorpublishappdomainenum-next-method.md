---
title: Метод ICorPublishAppDomainEnum::Next
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: c5ac38005410ae6ed9c2f4160e926987791ad604
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421219"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="e1fcc-102">Метод ICorPublishAppDomainEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e1fcc-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="e1fcc-103">Возвращает указанное количество доменов приложений, которые в данный момент существуют в процессе, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="e1fcc-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fcc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1fcc-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1fcc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1fcc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e1fcc-106">окне Число извлекаемых элементов.</span><span class="sxs-lookup"><span data-stu-id="e1fcc-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="e1fcc-107">заполняет Указатель на массив полученных объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , каждый из которых представляет домен приложения.</span><span class="sxs-lookup"><span data-stu-id="e1fcc-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e1fcc-108">заполняет Указатель на число фактически возвращенных доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="e1fcc-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="e1fcc-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="e1fcc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1fcc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e1fcc-110">Requirements</span></span>  
 <span data-ttu-id="e1fcc-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1fcc-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1fcc-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="e1fcc-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e1fcc-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1fcc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1fcc-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1fcc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1fcc-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e1fcc-115">See also</span></span>

- [<span data-ttu-id="e1fcc-116">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="e1fcc-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
