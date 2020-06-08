---
title: Интерфейс IMetaDataError
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 46370da4e61dc90f2386170745da4f95ac7de63b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492776"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="a076c-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="a076c-102">IMetaDataError Interface</span></span>
<span data-ttu-id="a076c-103">Предоставляет механизм обратного вызова для сообщения об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="a076c-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a076c-104">`IMetaDataError`Интерфейс должен быть реализован клиентом.</span><span class="sxs-lookup"><span data-stu-id="a076c-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a076c-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a076c-105">Methods</span></span>  
  
|<span data-ttu-id="a076c-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a076c-106">Method</span></span>|<span data-ttu-id="a076c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a076c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a076c-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="a076c-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="a076c-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="a076c-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a076c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a076c-110">Requirements</span></span>  
 <span data-ttu-id="a076c-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a076c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a076c-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a076c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a076c-113">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a076c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a076c-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a076c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a076c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a076c-115">See also</span></span>

- [<span data-ttu-id="a076c-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="a076c-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
