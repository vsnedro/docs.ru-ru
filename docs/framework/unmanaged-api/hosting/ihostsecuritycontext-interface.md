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
ms.openlocfilehash: f6e25bfe11880730f6f447ccc0406d716d185624
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501499"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="628e7-102">Интерфейс IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="628e7-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="628e7-103">Позволяет среде CLR поддерживать сведения о контексте безопасности, реализуемые узлом.</span><span class="sxs-lookup"><span data-stu-id="628e7-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="628e7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="628e7-104">Methods</span></span>  
  
|<span data-ttu-id="628e7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="628e7-105">Method</span></span>|<span data-ttu-id="628e7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="628e7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="628e7-107">Метод Capture</span><span class="sxs-lookup"><span data-stu-id="628e7-107">Capture Method</span></span>](ihostsecuritycontext-capture-method.md)|<span data-ttu-id="628e7-108">Возвращает клон `IHostSecurityContext` экземпляра, возвращенного из вызова [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="628e7-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="628e7-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="628e7-109">Remarks</span></span>  
 <span data-ttu-id="628e7-110">Узел может управлять доступом кода к маркерам потоков как средой CLR, так и кодом пользователя.</span><span class="sxs-lookup"><span data-stu-id="628e7-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="628e7-111">Он также может гарантировать, что полные сведения о контексте безопасности передаются по асинхронным операциям или кодовым точкам с ограниченным доступом к коду.</span><span class="sxs-lookup"><span data-stu-id="628e7-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="628e7-112">`IHostSecurityContext`инкапсулирует эти сведения о контексте безопасности, которые непрозрачны для среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="628e7-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="628e7-113">Среда выполнения захватывает эти сведения с помощью `Capture` и перемещает их между отправкой рабочего элемента пула потоков, выполнением метода завершения, а также конструкторами модулей и классов.</span><span class="sxs-lookup"><span data-stu-id="628e7-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="628e7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="628e7-114">Requirements</span></span>  
 <span data-ttu-id="628e7-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="628e7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="628e7-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="628e7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="628e7-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="628e7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="628e7-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="628e7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628e7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="628e7-119">See also</span></span>

- [<span data-ttu-id="628e7-120">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="628e7-120">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="628e7-121">Интерфейс IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="628e7-121">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="628e7-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="628e7-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
