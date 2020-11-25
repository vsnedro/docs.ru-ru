---
title: Метод IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: b4db3b115517f0a146aeab469f091008d31efc86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718232"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="f73a2-102">Метод IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="f73a2-102">IHostFilter::MarkToken Method</span></span>

<span data-ttu-id="f73a2-103">Указывает, что заданный маркер метаданных будет обработан.</span><span class="sxs-lookup"><span data-stu-id="f73a2-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f73a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f73a2-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f73a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f73a2-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="f73a2-106">окне Токен метаданных для обработки.</span><span class="sxs-lookup"><span data-stu-id="f73a2-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f73a2-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f73a2-107">Remarks</span></span>  

 <span data-ttu-id="f73a2-108">Как правило, требуется обработка маркера, если он находится в области действия метаданных.</span><span class="sxs-lookup"><span data-stu-id="f73a2-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="f73a2-109">`MarkToken`Метод передается в обработчик метаданных с помощью метода [IMetaDataEmit:: сесандлер](imetadataemit-sethandler-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f73a2-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f73a2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f73a2-110">Requirements</span></span>  

 <span data-ttu-id="f73a2-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f73a2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f73a2-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f73a2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f73a2-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f73a2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f73a2-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f73a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f73a2-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f73a2-115">See also</span></span>

- [<span data-ttu-id="f73a2-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="f73a2-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="f73a2-117">Интерфейс IHostFilter</span><span class="sxs-lookup"><span data-stu-id="f73a2-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
