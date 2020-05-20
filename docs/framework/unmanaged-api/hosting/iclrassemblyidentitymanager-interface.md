---
title: Интерфейс ICLRAssemblyIdentityManager
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: f06c8228d5eb850c0d5ff94d12be03d7fb75023b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615921"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="81ee0-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="81ee0-102">ICLRAssemblyIdentityManager Interface</span></span>
<span data-ttu-id="81ee0-103">Предоставляет методы, поддерживающие взаимодействие между узлом и общеязыковой средой выполнения (CLR) о сборках.</span><span class="sxs-lookup"><span data-stu-id="81ee0-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81ee0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="81ee0-104">Methods</span></span>  
  
|<span data-ttu-id="81ee0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="81ee0-105">Method</span></span>|<span data-ttu-id="81ee0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="81ee0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81ee0-107">Метод GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="81ee0-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="81ee0-108">Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="81ee0-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="81ee0-109">Метод GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="81ee0-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="81ee0-110">Возвращает канонические данные удостоверений сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="81ee0-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="81ee0-111">Метод GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="81ee0-111">GetCLRAssemblyReferenceList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="81ee0-112">Возвращает экземпляр [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) из заданного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="81ee0-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="81ee0-113">Метод GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="81ee0-113">GetProbingAssembliesFromReference Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="81ee0-114">Возвращает перечислитель [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) для удостоверений сборок, на которые ссылается сборка с указанным удостоверением.</span><span class="sxs-lookup"><span data-stu-id="81ee0-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="81ee0-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="81ee0-115">GetReferencedAssembliesFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="81ee0-116">Возвращает экземпляр [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , содержащий список сборок, на которые ссылается сборка по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="81ee0-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="81ee0-117">Метод GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="81ee0-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="81ee0-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборок, на которые ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="81ee0-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="81ee0-119">Метод IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="81ee0-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="81ee0-120">Возвращает значение, указывающее, является ли указанная сборка строго именованной.</span><span class="sxs-lookup"><span data-stu-id="81ee0-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81ee0-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="81ee0-121">Remarks</span></span>  
 <span data-ttu-id="81ee0-122">Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и для перечисления идентификаторов сборок.</span><span class="sxs-lookup"><span data-stu-id="81ee0-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ee0-123">Требования</span><span class="sxs-lookup"><span data-stu-id="81ee0-123">Requirements</span></span>  
 <span data-ttu-id="81ee0-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81ee0-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ee0-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81ee0-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81ee0-126">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81ee0-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81ee0-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ee0-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ee0-128">См. также статью</span><span class="sxs-lookup"><span data-stu-id="81ee0-128">See also</span></span>

- [<span data-ttu-id="81ee0-129">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="81ee0-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="81ee0-130">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="81ee0-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="81ee0-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="81ee0-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
