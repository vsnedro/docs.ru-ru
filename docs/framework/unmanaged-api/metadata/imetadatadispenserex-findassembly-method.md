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
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713396"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="ac0f6-102">Метод IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="ac0f6-102">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="ac0f6-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-103">This method is not implemented.</span></span> <span data-ttu-id="ac0f6-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac0f6-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ac0f6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac0f6-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="ac0f6-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="ac0f6-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="ac0f6-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ac0f6-110">окне Найденная сборка.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="ac0f6-111">заполняет Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="ac0f6-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ac0f6-112">окне Размер (в байтах) `szName` .</span><span class="sxs-lookup"><span data-stu-id="ac0f6-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="ac0f6-113">заполняет Число символов, фактически возвращаемых в `szName` .</span><span class="sxs-lookup"><span data-stu-id="ac0f6-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac0f6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ac0f6-114">Requirements</span></span>  

 <span data-ttu-id="ac0f6-115">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac0f6-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0f6-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ac0f6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac0f6-117">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac0f6-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac0f6-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0f6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0f6-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ac0f6-119">See also</span></span>

- [<span data-ttu-id="ac0f6-120">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="ac0f6-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="ac0f6-121">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="ac0f6-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
