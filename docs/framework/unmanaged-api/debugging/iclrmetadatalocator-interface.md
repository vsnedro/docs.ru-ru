---
title: Интерфейс ICLRMetadataLocator
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
ms.openlocfilehash: 69c52c13a4a0aca5094274de969ebed6e09651b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723510"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="64339-102">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="64339-102">ICLRMetadataLocator Interface</span></span>

<span data-ttu-id="64339-103">Используется уровнем служб доступа к данным для определения местоположения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="64339-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64339-104">Методы</span><span class="sxs-lookup"><span data-stu-id="64339-104">Methods</span></span>  
  
|<span data-ttu-id="64339-105">Метод</span><span class="sxs-lookup"><span data-stu-id="64339-105">Method</span></span>|<span data-ttu-id="64339-106">Описание</span><span class="sxs-lookup"><span data-stu-id="64339-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64339-107">Метод Metadata</span><span class="sxs-lookup"><span data-stu-id="64339-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="64339-108">Извлекает метаданные изображения из целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="64339-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64339-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="64339-109">Remarks</span></span>  

 <span data-ttu-id="64339-110">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="64339-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="64339-111">Например, реализация для активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="64339-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64339-112">Требования</span><span class="sxs-lookup"><span data-stu-id="64339-112">Requirements</span></span>  

 <span data-ttu-id="64339-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64339-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64339-114">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="64339-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="64339-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64339-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64339-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64339-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64339-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="64339-117">See also</span></span>

- [<span data-ttu-id="64339-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="64339-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
