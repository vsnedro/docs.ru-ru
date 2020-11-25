---
title: Интерфейс ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 3ff4efe8b3e2932da7f65246bf4ad614a4dd86cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694416"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="df50f-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="df50f-102">ICorPublish Interface</span></span>

<span data-ttu-id="df50f-103">Служит общим интерфейсом для публикации сведений о процессах и сведениях о доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="df50f-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="df50f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="df50f-104">Methods</span></span>  
  
|<span data-ttu-id="df50f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="df50f-105">Method</span></span>|<span data-ttu-id="df50f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="df50f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="df50f-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="df50f-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="df50f-108">Возвращает экземпляр [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , содержащий управляемые процессы, запущенные на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="df50f-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="df50f-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="df50f-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="df50f-110">Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="df50f-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df50f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="df50f-111">Requirements</span></span>  

 <span data-ttu-id="df50f-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df50f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df50f-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="df50f-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="df50f-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df50f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df50f-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df50f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df50f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="df50f-116">See also</span></span>

- [<span data-ttu-id="df50f-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="df50f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="df50f-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="df50f-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
