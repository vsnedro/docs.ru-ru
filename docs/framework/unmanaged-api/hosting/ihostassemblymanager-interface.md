---
title: Интерфейс IHostAssemblyManager
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: a06e7f13b6de9450aa2a81f28f591c0a3ce8db0f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681006"
---
# <a name="ihostassemblymanager-interface"></a><span data-ttu-id="e1dba-102">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="e1dba-102">IHostAssemblyManager Interface</span></span>

<span data-ttu-id="e1dba-103">Предоставляет методы, позволяющие узлу указывать наборы сборок, которые должны быть загружены средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="e1dba-103">Provides methods that allow a host to specify sets of assemblies that should be loaded by the common language runtime (CLR) or by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1dba-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e1dba-104">Methods</span></span>  
  
|<span data-ttu-id="e1dba-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e1dba-105">Method</span></span>|<span data-ttu-id="e1dba-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e1dba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1dba-107">Метод GetAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="e1dba-107">GetAssemblyStore Method</span></span>](ihostassemblymanager-getassemblystore-method.md)|<span data-ttu-id="e1dba-108">Возвращает указатель интерфейса на объект [IHostAssemblyStore](ihostassemblystore-interface.md) , представляющий список сборок, загруженных узлом.</span><span class="sxs-lookup"><span data-stu-id="e1dba-108">Gets an interface pointer to an [IHostAssemblyStore](ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>|  
|[<span data-ttu-id="e1dba-109">Метод GetNonHostStoreAssemblies</span><span class="sxs-lookup"><span data-stu-id="e1dba-109">GetNonHostStoreAssemblies Method</span></span>](ihostassemblymanager-getnonhoststoreassemblies-method.md)|<span data-ttu-id="e1dba-110">Возвращает указатель интерфейса на объект [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , представляющий список сборок, которые узел загружает в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="e1dba-110">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the CLR to load.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1dba-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e1dba-111">Remarks</span></span>  

 <span data-ttu-id="e1dba-112">Узел не является обязательным для реализации `IHostAssemblyManager` или `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="e1dba-112">The host is not required to implement `IHostAssemblyManager` or `IHostAssemblyStore`.</span></span> <span data-ttu-id="e1dba-113">Если узел выполняет реализацию `IHostAssemblyManager` , он также должен реализовать `IHostAssemblyStore` .</span><span class="sxs-lookup"><span data-stu-id="e1dba-113">If the host does implement `IHostAssemblyManager`, it must also implement `IHostAssemblyStore`.</span></span>  
  
 <span data-ttu-id="e1dba-114">Среда выполнения запрашивает `IHostAssemblyManager` , вызывая [IHostControl:: жесостманажер](ihostcontrol-gethostmanager-method.md) при инициализации с `IID` IID_IHostAssemblyManager.</span><span class="sxs-lookup"><span data-stu-id="e1dba-114">The runtime queries for an `IHostAssemblyManager` by calling [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) upon initialization with an `IID` of IID_IHostAssemblyManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1dba-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e1dba-115">Requirements</span></span>  

 <span data-ttu-id="e1dba-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1dba-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1dba-117">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e1dba-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1dba-118">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1dba-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1dba-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1dba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1dba-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1dba-120">See also</span></span>

- [<span data-ttu-id="e1dba-121">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e1dba-121">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e1dba-122">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="e1dba-122">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="e1dba-123">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="e1dba-123">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="e1dba-124">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e1dba-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
