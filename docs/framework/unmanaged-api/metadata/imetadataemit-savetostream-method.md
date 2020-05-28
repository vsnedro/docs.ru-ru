---
title: Метод IMetaDataEmit::SaveToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 87e00a69643b6bc403188fb0fdb6f9e3f3d82115
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003884"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="40cda-102">Метод IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="40cda-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="40cda-103">Сохраняет все метаданные в текущей области в указанном `IStream` .</span><span class="sxs-lookup"><span data-stu-id="40cda-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40cda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40cda-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40cda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40cda-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="40cda-106">окне Доступный для записи поток для сохранения.</span><span class="sxs-lookup"><span data-stu-id="40cda-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="40cda-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="40cda-107">[in] Reserved.</span></span> <span data-ttu-id="40cda-108">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="40cda-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40cda-109">Требования</span><span class="sxs-lookup"><span data-stu-id="40cda-109">Requirements</span></span>  
 <span data-ttu-id="40cda-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40cda-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40cda-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="40cda-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40cda-112">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40cda-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40cda-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40cda-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40cda-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="40cda-114">See also</span></span>

- [<span data-ttu-id="40cda-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="40cda-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="40cda-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="40cda-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
