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
ms.openlocfilehash: e33029e8244fdfa180a79aa4a5b05b07f594d928
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860907"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="bb199-102">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="bb199-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="bb199-103">Предоставляет интерфейсы для публикации сведений о доменах приложений и процессах.</span><span class="sxs-lookup"><span data-stu-id="bb199-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb199-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb199-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="bb199-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="bb199-105">Interfaces</span></span>  
  
|<span data-ttu-id="bb199-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="bb199-106">Interface</span></span>|<span data-ttu-id="bb199-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bb199-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="bb199-108">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="bb199-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="bb199-109">Предоставляет методы для публикации сведений о процессах и доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="bb199-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="bb199-110">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="bb199-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="bb199-111">Представляет и предоставляет сведения о домене приложения в процессе.</span><span class="sxs-lookup"><span data-stu-id="bb199-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="bb199-112">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="bb199-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="bb199-113">Предоставляет методы, которые проходят через коллекцию доменов приложений, которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="bb199-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="bb199-114">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="bb199-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="bb199-115">Представляет процесс, выполняющийся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bb199-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="bb199-116">Интерфейс ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="bb199-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="bb199-117">Предоставляет методы, которые проходят по коллекции процессов, выполняющихся на компьютере.</span><span class="sxs-lookup"><span data-stu-id="bb199-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb199-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb199-118">Remarks</span></span>  
 <span data-ttu-id="bb199-119">Типичный сценарий публикации включает в себя разработчика, желающего отлаживать управляемый код, выполняющийся на компьютере в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="bb199-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="bb199-120">Среда размещения может запускать несколько доменов приложений в рамках одного процесса.</span><span class="sxs-lookup"><span data-stu-id="bb199-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="bb199-121">Разработчику хотелось бы использовать графический пользовательский интерфейс или другие средства для перечисления всех процессов, запущенных на компьютере, и выбрать конкретный процесс.</span><span class="sxs-lookup"><span data-stu-id="bb199-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="bb199-122">Список должен включать все домены приложений в процессах, выполняющих управляемый код.</span><span class="sxs-lookup"><span data-stu-id="bb199-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="bb199-123">Затем разработчик может определить конкретный домен приложения и подключить к этому домену отладчик.</span><span class="sxs-lookup"><span data-stu-id="bb199-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb199-124">Требования</span><span class="sxs-lookup"><span data-stu-id="bb199-124">Requirements</span></span>  
 <span data-ttu-id="bb199-125">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb199-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb199-126">**Заголовок:** Корпуб. idl</span><span class="sxs-lookup"><span data-stu-id="bb199-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="bb199-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb199-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb199-128">**.NET Framework версии:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb199-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb199-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bb199-129">See also</span></span>

- [<span data-ttu-id="bb199-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="bb199-130">Debugging</span></span>](index.md)
