---
title: Интерфейс ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
ms.openlocfilehash: 492d4b727ce507340fec47d30a791aa49d0cecb6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693350"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="37236-102">Интерфейс ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="37236-102">ICorPublishEnum Interface</span></span>

<span data-ttu-id="37236-103">Служит абстрактным базовым интерфейсом для перечислителей, используемых в публикации сведений о процессах и доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="37236-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37236-104">Методы</span><span class="sxs-lookup"><span data-stu-id="37236-104">Methods</span></span>  
  
|<span data-ttu-id="37236-105">Метод</span><span class="sxs-lookup"><span data-stu-id="37236-105">Method</span></span>|<span data-ttu-id="37236-106">Описание</span><span class="sxs-lookup"><span data-stu-id="37236-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37236-107">Метод Clone</span><span class="sxs-lookup"><span data-stu-id="37236-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="37236-108">Создает копию данного объекта `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="37236-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="37236-109">Метод GetCount</span><span class="sxs-lookup"><span data-stu-id="37236-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="37236-110">Возвращает число элементов в перечислении.</span><span class="sxs-lookup"><span data-stu-id="37236-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="37236-111">Метод Reset</span><span class="sxs-lookup"><span data-stu-id="37236-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="37236-112">Перемещает курсор в начало перечисления.</span><span class="sxs-lookup"><span data-stu-id="37236-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="37236-113">Метод Skip</span><span class="sxs-lookup"><span data-stu-id="37236-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="37236-114">Перемещает курсор вперед в перечислении на указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="37236-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37236-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="37236-115">Remarks</span></span>  

 <span data-ttu-id="37236-116">Следующие перечислители являются производными от `ICorPublishEnum` :</span><span class="sxs-lookup"><span data-stu-id="37236-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="37236-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="37236-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="37236-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="37236-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="37236-119">Требования</span><span class="sxs-lookup"><span data-stu-id="37236-119">Requirements</span></span>  

 <span data-ttu-id="37236-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37236-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37236-121">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="37236-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="37236-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37236-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37236-123">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37236-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37236-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="37236-124">See also</span></span>

- [<span data-ttu-id="37236-125">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="37236-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="37236-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="37236-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
