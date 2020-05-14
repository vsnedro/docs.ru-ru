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
ms.openlocfilehash: a48e20413f466e25a9145e9dbf1ba93d90155770
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397033"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="2b085-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="2b085-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="2b085-103">Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="2b085-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b085-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2b085-104">Methods</span></span>  
  
|<span data-ttu-id="2b085-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2b085-105">Method</span></span>|<span data-ttu-id="2b085-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2b085-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b085-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="2b085-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="2b085-108">Возвращает указанное количество `ICorPublishAppDomain` экземпляров из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2b085-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b085-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b085-109">Remarks</span></span>  
 <span data-ttu-id="2b085-110">`ICorPublishAppDomainEnum`Интерфейс реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2b085-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b085-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2b085-111">Requirements</span></span>  
 <span data-ttu-id="2b085-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b085-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b085-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="2b085-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2b085-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b085-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b085-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b085-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b085-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="2b085-116">See also</span></span>

- [<span data-ttu-id="2b085-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2b085-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2b085-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="2b085-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
