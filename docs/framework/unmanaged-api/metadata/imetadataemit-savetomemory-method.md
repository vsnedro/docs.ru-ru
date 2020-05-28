---
title: Метод IMetaDataEmit::SaveToMemory
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: ccf82531eb1f78bcfc6762d10d53ffee59f30ad8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003965"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="1b32c-102">Метод IMetaDataEmit::SaveToMemory</span><span class="sxs-lookup"><span data-stu-id="1b32c-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="1b32c-103">Сохраняет все метаданные в текущей области в указанную область памяти.</span><span class="sxs-lookup"><span data-stu-id="1b32c-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b32c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b32c-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b32c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b32c-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="1b32c-106">заполняет Адрес, с которого начинается запись метаданных.</span><span class="sxs-lookup"><span data-stu-id="1b32c-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="1b32c-107">окне Размер выделенной памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="1b32c-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b32c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1b32c-108">Requirements</span></span>  
 <span data-ttu-id="1b32c-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b32c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b32c-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1b32c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b32c-111">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b32c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b32c-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b32c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b32c-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1b32c-113">See also</span></span>

- [<span data-ttu-id="1b32c-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1b32c-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1b32c-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1b32c-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
