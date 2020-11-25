---
title: Метод IMetaDataFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
ms.openlocfilehash: c942838fb62bf86c4054761f4e7f2ef0518b3d89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701816"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="3a545-102">Метод IMetaDataFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="3a545-102">IMetaDataFilter::MarkToken Method</span></span>

<span data-ttu-id="3a545-103">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="3a545-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a545-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a545-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a545-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3a545-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="3a545-106">окне Маркер, помечающий как обработанный.</span><span class="sxs-lookup"><span data-stu-id="3a545-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a545-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3a545-107">Requirements</span></span>  

 <span data-ttu-id="3a545-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a545-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a545-109">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3a545-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a545-110">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a545-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a545-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a545-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a545-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3a545-112">See also</span></span>

- [<span data-ttu-id="3a545-113">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="3a545-113">IMetaDataFilter Interface</span></span>](imetadatafilter-interface.md)
