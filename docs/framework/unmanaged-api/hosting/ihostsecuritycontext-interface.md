---
title: Интерфейс IHostSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
ms.openlocfilehash: bf8e725908177d9a15407b096f68cbcb947c7a01
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804152"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="c87d9-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c87d9-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="c87d9-103">Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.</span><span class="sxs-lookup"><span data-stu-id="c87d9-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c87d9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c87d9-104">Methods</span></span>  
  
|<span data-ttu-id="c87d9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c87d9-105">Method</span></span>|<span data-ttu-id="c87d9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c87d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c87d9-107">Метод Capture</span><span class="sxs-lookup"><span data-stu-id="c87d9-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="c87d9-108">Возвращает клон `IHostSecurityContext` экземпляра, возвращенного из вызова [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="c87d9-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c87d9-109">Замечания</span><span class="sxs-lookup"><span data-stu-id="c87d9-109">Remarks</span></span>  
 <span data-ttu-id="c87d9-110">Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя.</span><span class="sxs-lookup"><span data-stu-id="c87d9-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c87d9-111">Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду.</span><span class="sxs-lookup"><span data-stu-id="c87d9-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="c87d9-112">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="c87d9-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="c87d9-113">Среда выполнения захватывает эти сведения с помощью `Capture` и перемещает их между отправкой рабочего элемента пула потоков, выполнением метода завершения, а также конструкторами модулей и классов.</span><span class="sxs-lookup"><span data-stu-id="c87d9-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87d9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c87d9-114">Requirements</span></span>  
 <span data-ttu-id="c87d9-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c87d9-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c87d9-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c87d9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c87d9-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c87d9-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c87d9-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c87d9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87d9-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c87d9-119">See also</span></span>

- [<span data-ttu-id="c87d9-120">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="c87d9-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="c87d9-121">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c87d9-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="c87d9-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c87d9-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
