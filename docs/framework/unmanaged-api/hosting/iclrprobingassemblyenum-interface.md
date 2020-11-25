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
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728931"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="ec6b5-102">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ec6b5-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="ec6b5-103">Предоставляет методы, позволяющие узлу получить идентификаторы проверки сборки с помощью сведений об удостоверении сборки, которые являются внутренними для среды CLR, без необходимости создавать или понимать это удостоверение.</span><span class="sxs-lookup"><span data-stu-id="ec6b5-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec6b5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ec6b5-104">Methods</span></span>  
  
|<span data-ttu-id="ec6b5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ec6b5-105">Method</span></span>|<span data-ttu-id="ec6b5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ec6b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec6b5-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="ec6b5-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="ec6b5-108">Возвращает удостоверение сборки по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="ec6b5-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec6b5-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ec6b5-109">Remarks</span></span>  

 <span data-ttu-id="ec6b5-110">Методы, такие как [ICLRAssemblyIdentityManager:: жетпробингассемблиесфромреференце](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , возвращают `ICLRProbingAssemblyEnum` экземпляр.</span><span class="sxs-lookup"><span data-stu-id="ec6b5-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec6b5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ec6b5-111">Requirements</span></span>  

 <span data-ttu-id="ec6b5-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec6b5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec6b5-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ec6b5-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec6b5-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec6b5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec6b5-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec6b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec6b5-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ec6b5-116">See also</span></span>

- [<span data-ttu-id="ec6b5-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ec6b5-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ec6b5-118">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ec6b5-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ec6b5-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="ec6b5-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
