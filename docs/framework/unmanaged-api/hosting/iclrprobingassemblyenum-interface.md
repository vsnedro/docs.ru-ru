---
title: Интерфейс ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703372"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="92ce6-102">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="92ce6-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="92ce6-103">Предоставляет методы, позволяющие узлу получить идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создавать или понимать это удостоверение.</span><span class="sxs-lookup"><span data-stu-id="92ce6-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92ce6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="92ce6-104">Methods</span></span>  
  
|<span data-ttu-id="92ce6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="92ce6-105">Method</span></span>|<span data-ttu-id="92ce6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="92ce6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92ce6-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="92ce6-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="92ce6-108">Возвращает удостоверение сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="92ce6-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92ce6-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="92ce6-109">Remarks</span></span>  
 <span data-ttu-id="92ce6-110">Методы, такие как [ICLRAssemblyIdentityManager:: жетпробингассемблиесфромреференце](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , возвращают `ICLRProbingAssemblyEnum` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="92ce6-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92ce6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="92ce6-111">Requirements</span></span>  
 <span data-ttu-id="92ce6-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92ce6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92ce6-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="92ce6-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92ce6-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="92ce6-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92ce6-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92ce6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ce6-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="92ce6-116">See also</span></span>

- [<span data-ttu-id="92ce6-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="92ce6-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="92ce6-118">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="92ce6-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="92ce6-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="92ce6-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
