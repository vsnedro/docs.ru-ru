---
title: Кокласс CorpubPublish
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: c73eab14bf6f9f9599bed79f4c5f85ed035c0518
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722353"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="a355d-102">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="a355d-102">CorpubPublish Coclass</span></span>

<span data-ttu-id="a355d-103">Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.</span><span class="sxs-lookup"><span data-stu-id="a355d-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a355d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a355d-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="a355d-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="a355d-105">Interfaces</span></span>  
  
|<span data-ttu-id="a355d-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="a355d-106">Interface</span></span>|<span data-ttu-id="a355d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a355d-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="a355d-108">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="a355d-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="a355d-109">Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="a355d-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="a355d-110">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="a355d-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="a355d-111">Представляет и предоставляет сведения о домене приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="a355d-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="a355d-112">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="a355d-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="a355d-113">Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="a355d-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="a355d-114">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="a355d-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="a355d-115">Представляет процесс, выполняющийся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a355d-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="a355d-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="a355d-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="a355d-117">Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a355d-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a355d-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a355d-118">Remarks</span></span>  

 <span data-ttu-id="a355d-119">Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="a355d-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="a355d-120">Среда размещения может запускать несколько доменов приложений в рамках одного процесса.</span><span class="sxs-lookup"><span data-stu-id="a355d-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="a355d-121">Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс.</span><span class="sxs-lookup"><span data-stu-id="a355d-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="a355d-122">Список должен включать все домены приложений в процессах, выполняющих управляемый код.</span><span class="sxs-lookup"><span data-stu-id="a355d-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="a355d-123">Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.</span><span class="sxs-lookup"><span data-stu-id="a355d-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a355d-124">Требования</span><span class="sxs-lookup"><span data-stu-id="a355d-124">Requirements</span></span>  

 <span data-ttu-id="a355d-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a355d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a355d-126">**Заголовок:** Корпуб. idl</span><span class="sxs-lookup"><span data-stu-id="a355d-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="a355d-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a355d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a355d-128">**.NET Framework версии:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a355d-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a355d-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a355d-129">See also</span></span>

- [<span data-ttu-id="a355d-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="a355d-130">Debugging</span></span>](index.md)
