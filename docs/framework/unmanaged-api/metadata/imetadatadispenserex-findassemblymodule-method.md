---
title: Метод IMetaDataDispenserEx::FindAssemblyModule
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
ms.openlocfilehash: 5bc622c013e62fa9c03476cc5927133682020426
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700617"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="0d75d-102">Метод IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="0d75d-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>

<span data-ttu-id="0d75d-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="0d75d-103">This method is not implemented.</span></span> <span data-ttu-id="0d75d-104">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0d75d-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d75d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d75d-105">Syntax</span></span>  
  
```cpp  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d75d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d75d-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="0d75d-107">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="0d75d-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="0d75d-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="0d75d-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="0d75d-109">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="0d75d-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="0d75d-110">окне Имя модуля.</span><span class="sxs-lookup"><span data-stu-id="0d75d-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="0d75d-111">окне Найденная сборка.</span><span class="sxs-lookup"><span data-stu-id="0d75d-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="0d75d-112">заполняет Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="0d75d-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0d75d-113">окне Размер (в байтах) `szName` .</span><span class="sxs-lookup"><span data-stu-id="0d75d-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="0d75d-114">заполняет Число символов, фактически возвращаемых в `szName` .</span><span class="sxs-lookup"><span data-stu-id="0d75d-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d75d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0d75d-115">Requirements</span></span>  

 <span data-ttu-id="0d75d-116">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d75d-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d75d-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="0d75d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d75d-118">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d75d-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d75d-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d75d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d75d-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d75d-120">See also</span></span>

- [<span data-ttu-id="0d75d-121">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="0d75d-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="0d75d-122">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="0d75d-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
