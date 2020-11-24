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
ms.openlocfilehash: 3f8da08b96c47c90ecccae28dd1662a7abffaf1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688566"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="7158f-102">Метод IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="7158f-102">IMetaDataEmit::SaveToStream Method</span></span>

<span data-ttu-id="7158f-103">Сохраняет все метаданные в текущей области в указанном `IStream` .</span><span class="sxs-lookup"><span data-stu-id="7158f-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7158f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7158f-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7158f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7158f-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="7158f-106">окне Доступный для записи поток для сохранения.</span><span class="sxs-lookup"><span data-stu-id="7158f-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="7158f-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="7158f-107">[in] Reserved.</span></span> <span data-ttu-id="7158f-108">Должен равняться нулю.</span><span class="sxs-lookup"><span data-stu-id="7158f-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7158f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7158f-109">Requirements</span></span>  

 <span data-ttu-id="7158f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7158f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7158f-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7158f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7158f-112">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7158f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7158f-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7158f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7158f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7158f-114">See also</span></span>

- [<span data-ttu-id="7158f-115">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7158f-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7158f-116">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7158f-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
