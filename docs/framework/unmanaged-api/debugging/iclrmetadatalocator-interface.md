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
ms.openlocfilehash: 734f8eaa7c520bbf1ad1208ece42751e967a208a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859719"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="cb715-102">Интерфейс ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="cb715-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="cb715-103">Используется уровнем служб доступа к данным для определения местоположения метаданных сборок в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="cb715-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb715-104">Методы</span><span class="sxs-lookup"><span data-stu-id="cb715-104">Methods</span></span>  
  
|<span data-ttu-id="cb715-105">Метод</span><span class="sxs-lookup"><span data-stu-id="cb715-105">Method</span></span>|<span data-ttu-id="cb715-106">Описание</span><span class="sxs-lookup"><span data-stu-id="cb715-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb715-107">Метод Metadata</span><span class="sxs-lookup"><span data-stu-id="cb715-107">GetMetadata Method</span></span>](iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="cb715-108">Извлекает метаданные изображения из целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="cb715-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb715-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb715-109">Remarks</span></span>  
 <span data-ttu-id="cb715-110">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="cb715-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="cb715-111">Например, реализация для активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="cb715-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb715-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cb715-112">Requirements</span></span>  
 <span data-ttu-id="cb715-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb715-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb715-114">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="cb715-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cb715-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb715-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb715-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb715-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb715-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cb715-117">See also</span></span>

- [<span data-ttu-id="cb715-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cb715-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
