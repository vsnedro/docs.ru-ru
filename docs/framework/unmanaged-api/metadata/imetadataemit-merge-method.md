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
ms.openlocfilehash: e7fe5cbe27c0771a71e4c03d14ab68ada7d0741a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004196"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="62c77-102">Метод IMetaDataEmit::Merge</span><span class="sxs-lookup"><span data-stu-id="62c77-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="62c77-103">Добавляет указанную импортированную область в список объединяемых областей.</span><span class="sxs-lookup"><span data-stu-id="62c77-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62c77-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62c77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62c77-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="62c77-106">окне Указатель на объект [IMetaDataImport](imetadataimport-interface.md) , определяющий импортируемую область для слияния.</span><span class="sxs-lookup"><span data-stu-id="62c77-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="62c77-107">окне Указатель на объект [IMapToken](imaptoken-interface.md) , указывающий повторное отображение токена.</span><span class="sxs-lookup"><span data-stu-id="62c77-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="62c77-108">окне Указатель на объект [IUnknown](/cpp/atl/iunknown) , указывающий ошибки.</span><span class="sxs-lookup"><span data-stu-id="62c77-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c77-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="62c77-109">Remarks</span></span>  
 <span data-ttu-id="62c77-110">Вызовите метод [IMetaDataEmit:: мержеенд](imetadataemit-mergeend-method.md) , чтобы активировать слияние метаданных в одну область.</span><span class="sxs-lookup"><span data-stu-id="62c77-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c77-111">Требования</span><span class="sxs-lookup"><span data-stu-id="62c77-111">Requirements</span></span>  
 <span data-ttu-id="62c77-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62c77-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c77-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="62c77-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62c77-114">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62c77-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62c77-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c77-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="62c77-116">See also</span></span>

- [<span data-ttu-id="62c77-117">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="62c77-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="62c77-118">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="62c77-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
