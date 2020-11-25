---
title: Метод IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722015"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="8d0d6-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="8d0d6-102">IMetaDataEmit::Merge Method</span></span>

<span data-ttu-id="8d0d6-103">Добавляет указанную импортированную область в список объединяемых областей.</span><span class="sxs-lookup"><span data-stu-id="8d0d6-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d0d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d0d6-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d0d6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d0d6-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="8d0d6-106">окне Указатель на объект [IMetaDataImport](imetadataimport-interface.md) , определяющий импортируемую область для слияния.</span><span class="sxs-lookup"><span data-stu-id="8d0d6-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="8d0d6-107">окне Указатель на объект [IMapToken](imaptoken-interface.md) , указывающий повторное отображение токена.</span><span class="sxs-lookup"><span data-stu-id="8d0d6-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="8d0d6-108">окне Указатель на объект [IUnknown](/cpp/atl/iunknown) , указывающий ошибки.</span><span class="sxs-lookup"><span data-stu-id="8d0d6-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d0d6-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8d0d6-109">Remarks</span></span>  

 <span data-ttu-id="8d0d6-110">Вызовите метод [IMetaDataEmit:: мержеенд](imetadataemit-mergeend-method.md) , чтобы активировать слияние метаданных в одну область.</span><span class="sxs-lookup"><span data-stu-id="8d0d6-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0d6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8d0d6-111">Requirements</span></span>  

 <span data-ttu-id="8d0d6-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d0d6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d0d6-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8d0d6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d0d6-114">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d0d6-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d0d6-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d0d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0d6-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d0d6-116">See also</span></span>

- [<span data-ttu-id="8d0d6-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="8d0d6-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8d0d6-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="8d0d6-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
