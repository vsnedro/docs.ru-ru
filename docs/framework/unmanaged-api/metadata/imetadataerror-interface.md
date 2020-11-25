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
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701930"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="4c61f-102">Интерфейс IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="4c61f-102">IMetaDataError Interface</span></span>

<span data-ttu-id="4c61f-103">Предоставляет механизм обратного вызова для сообщения об ошибках во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="4c61f-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c61f-104">`IMetaDataError`Интерфейс должен быть реализован клиентом.</span><span class="sxs-lookup"><span data-stu-id="4c61f-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c61f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4c61f-105">Methods</span></span>  
  
|<span data-ttu-id="4c61f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4c61f-106">Method</span></span>|<span data-ttu-id="4c61f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4c61f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c61f-108">Метод OnError</span><span class="sxs-lookup"><span data-stu-id="4c61f-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="4c61f-109">Предоставляет уведомление об ошибках, возникающих во время слияния метаданных.</span><span class="sxs-lookup"><span data-stu-id="4c61f-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c61f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4c61f-110">Requirements</span></span>  

 <span data-ttu-id="4c61f-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c61f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c61f-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4c61f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c61f-113">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c61f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4c61f-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c61f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c61f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c61f-115">See also</span></span>

- [<span data-ttu-id="4c61f-116">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="4c61f-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
