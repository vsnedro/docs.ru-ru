---
title: Интерфейс ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 5b5a901bef779948467cfcc3d71a1fcd057c1aeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693714"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="3b6e4-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="3b6e4-102">ICorPublishAppDomainEnum Interface</span></span>

<span data-ttu-id="3b6e4-103">Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b6e4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3b6e4-104">Methods</span></span>  
  
|<span data-ttu-id="3b6e4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3b6e4-105">Method</span></span>|<span data-ttu-id="3b6e4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3b6e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b6e4-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="3b6e4-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="3b6e4-108">Возвращает указанное количество `ICorPublishAppDomain` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b6e4-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="3b6e4-109">Remarks</span></span>  

 <span data-ttu-id="3b6e4-110">`ICorPublishAppDomainEnum`Интерфейс реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3b6e4-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b6e4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3b6e4-111">Requirements</span></span>  

 <span data-ttu-id="3b6e4-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b6e4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b6e4-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="3b6e4-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3b6e4-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b6e4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b6e4-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b6e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b6e4-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b6e4-116">See also</span></span>

- [<span data-ttu-id="3b6e4-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3b6e4-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3b6e4-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="3b6e4-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
