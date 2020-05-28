---
title: Метод IMetaDataDispenserEx::FindAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006198"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="658bf-102">Метод IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="658bf-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="658bf-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="658bf-103">This method is not implemented.</span></span> <span data-ttu-id="658bf-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="658bf-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="658bf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="658bf-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="658bf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="658bf-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="658bf-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="658bf-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="658bf-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="658bf-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="658bf-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="658bf-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="658bf-110">окне Найденная сборка.</span><span class="sxs-lookup"><span data-stu-id="658bf-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="658bf-111">заполняет Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="658bf-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="658bf-112">окне Размер (в байтах) `szName` .</span><span class="sxs-lookup"><span data-stu-id="658bf-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="658bf-113">заполняет Число символов, фактически возвращаемых в `szName` .</span><span class="sxs-lookup"><span data-stu-id="658bf-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="658bf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="658bf-114">Requirements</span></span>  
 <span data-ttu-id="658bf-115">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="658bf-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="658bf-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="658bf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="658bf-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="658bf-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="658bf-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="658bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="658bf-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="658bf-119">See also</span></span>

- [<span data-ttu-id="658bf-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="658bf-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="658bf-121">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="658bf-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
