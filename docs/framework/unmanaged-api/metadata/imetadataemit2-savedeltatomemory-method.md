---
title: Метод IMetaDataEmit2::SaveDeltaToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: 8a6f11996425c92d9b0e3123ee2d3a064739454b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492765"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="7ac66-102">Метод IMetaDataEmit2::SaveDeltaToMemory</span><span class="sxs-lookup"><span data-stu-id="7ac66-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="7ac66-103">Сохраняет изменения из текущего сеанса "изменить и продолжить" в память.</span><span class="sxs-lookup"><span data-stu-id="7ac66-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ac66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ac66-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ac66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ac66-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="7ac66-106">заполняет Адрес, с которого начинается запись разностных метаданных.</span><span class="sxs-lookup"><span data-stu-id="7ac66-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="7ac66-107">окне Размер изменений.</span><span class="sxs-lookup"><span data-stu-id="7ac66-107">[in] The size of the changes.</span></span> <span data-ttu-id="7ac66-108">Чтобы определить размер, используйте [IMetaDataEmit2:: жетделтасавесизе](imetadataemit2-getdeltasavesize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7ac66-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ac66-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7ac66-109">Requirements</span></span>  
 <span data-ttu-id="7ac66-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ac66-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ac66-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7ac66-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ac66-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7ac66-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ac66-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ac66-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ac66-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7ac66-114">See also</span></span>

- [<span data-ttu-id="7ac66-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7ac66-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="7ac66-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7ac66-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
