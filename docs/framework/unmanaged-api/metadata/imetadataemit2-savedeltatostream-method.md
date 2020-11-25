---
title: Метод IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: dad916d74c4e754d8fd3ffb62024e49617f5de05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702025"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="ce244-102">Метод IMetaDataEmit2::SaveDeltaToStream</span><span class="sxs-lookup"><span data-stu-id="ce244-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>

<span data-ttu-id="ce244-103">Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный поток.</span><span class="sxs-lookup"><span data-stu-id="ce244-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce244-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce244-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce244-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce244-105">Parameters</span></span>  

 `pIStream`  
 <span data-ttu-id="ce244-106">окне Указатель интерфейса на поток, доступный для записи, в который необходимо сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="ce244-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="ce244-107">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="ce244-107">[in] Reserved.</span></span> <span data-ttu-id="ce244-108">Это значение должно быть равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ce244-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce244-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ce244-109">Requirements</span></span>  

 <span data-ttu-id="ce244-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce244-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce244-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ce244-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce244-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce244-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce244-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce244-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce244-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce244-114">See also</span></span>

- [<span data-ttu-id="ce244-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ce244-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="ce244-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ce244-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
