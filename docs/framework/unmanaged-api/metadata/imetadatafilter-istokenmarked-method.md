---
title: Метод IMetaDataFilter::IsTokenMarked
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: eb0ebab0f4e05d81730d5beb2b5345e319e8e274
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492542"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="131d0-102">Метод IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="131d0-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="131d0-103">Возвращает значение, указывающее, помечен ли заданный маркер метаданных как обработанный.</span><span class="sxs-lookup"><span data-stu-id="131d0-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="131d0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="131d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="131d0-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="131d0-106">окне Токен для проверки на наличие метки обработки.</span><span class="sxs-lookup"><span data-stu-id="131d0-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="131d0-107">заполняет Значение, равное, если объект был `true` `tk` обработан; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="131d0-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="131d0-108">Требования</span><span class="sxs-lookup"><span data-stu-id="131d0-108">Requirements</span></span>  
 <span data-ttu-id="131d0-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131d0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131d0-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="131d0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="131d0-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="131d0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="131d0-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131d0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="131d0-113">See also</span></span>

- [<span data-ttu-id="131d0-114">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="131d0-114">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
