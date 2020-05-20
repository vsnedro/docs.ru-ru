---
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421076"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="9df87-102">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="9df87-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="9df87-103">Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9df87-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9df87-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9df87-104">Methods</span></span>  
  
|<span data-ttu-id="9df87-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9df87-105">Method</span></span>|<span data-ttu-id="9df87-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9df87-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9df87-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="9df87-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="9df87-108">Возвращает указанное количество `ICorPublishProcess` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="9df87-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9df87-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9df87-109">Remarks</span></span>  
 <span data-ttu-id="9df87-110">`ICorPublishProcessEnum`Интерфейс реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9df87-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="9df87-111">`ICorPublishProcessEnum`Экземпляр создается методом [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9df87-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="9df87-112">Обход коллекции `ICorPublishProcess` объектов основан на условиях фильтрации, заданных на момент `ICorPublishProcessEnum` создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9df87-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9df87-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9df87-113">Requirements</span></span>  
 <span data-ttu-id="9df87-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9df87-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9df87-115">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="9df87-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9df87-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9df87-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9df87-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df87-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df87-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9df87-118">See also</span></span>

- [<span data-ttu-id="9df87-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9df87-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9df87-120">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="9df87-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
