---
title: Интерфейс ICLRReferenceAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
ms.openlocfilehash: 9797c419251127ef07a8c2bee22132c3c2b82e36
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703329"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="d6df4-102">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="d6df4-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="d6df4-103">Предоставляет методы, позволяющие основному приложению манипулировать набором сборок, на которые ссылается файл или поток, с помощью данных идентификации сборок, которые являются внутренними для среды CLR, не требуя создания или понимания этих удостоверений.</span><span class="sxs-lookup"><span data-stu-id="d6df4-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d6df4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d6df4-104">Methods</span></span>  
  
|<span data-ttu-id="d6df4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d6df4-105">Method</span></span>|<span data-ttu-id="d6df4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d6df4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d6df4-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="d6df4-107">Get Method</span></span>](iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="d6df4-108">Возвращает удостоверение сборки по заданному индексу.</span><span class="sxs-lookup"><span data-stu-id="d6df4-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6df4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d6df4-109">Requirements</span></span>  
 <span data-ttu-id="d6df4-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6df4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6df4-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d6df4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6df4-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d6df4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6df4-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6df4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6df4-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d6df4-114">See also</span></span>

- [<span data-ttu-id="d6df4-115">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="d6df4-115">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d6df4-116">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d6df4-116">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d6df4-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d6df4-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
