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
ms.openlocfilehash: 41d049c931091d2cc0b41bd1e9d74b3c15d7878d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679264"
---
# <a name="iclrassemblyidentitymanager-interface"></a><span data-ttu-id="40ca9-102">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="40ca9-102">ICLRAssemblyIdentityManager Interface</span></span>

<span data-ttu-id="40ca9-103">Предоставляет методы, поддерживающие взаимодействие между узлом и общеязыковой средой выполнения (CLR) о сборках.</span><span class="sxs-lookup"><span data-stu-id="40ca9-103">Provides methods that support communication between the host and the common language runtime (CLR) about assemblies.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40ca9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="40ca9-104">Methods</span></span>  
  
|<span data-ttu-id="40ca9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="40ca9-105">Method</span></span>|<span data-ttu-id="40ca9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="40ca9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40ca9-107">Метод GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="40ca9-107">GetBindingIdentityFromFile Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|<span data-ttu-id="40ca9-108">Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="40ca9-108">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="40ca9-109">Метод GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="40ca9-109">GetBindingIdentityFromStream Method</span></span>](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|<span data-ttu-id="40ca9-110">Возвращает канонические данные удостоверений сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="40ca9-110">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="40ca9-111">Метод GetCLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="40ca9-111">GetCLRAssemblyReferenceList Method</span></span>](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|<span data-ttu-id="40ca9-112">Возвращает экземпляр [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) из заданного списка частичных идентификаторов сборки.</span><span class="sxs-lookup"><span data-stu-id="40ca9-112">Gets an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>|  
|[<span data-ttu-id="40ca9-113">Метод GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="40ca9-113">GetProbingAssembliesFromReference Method</span></span>](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|<span data-ttu-id="40ca9-114">Возвращает перечислитель [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) для удостоверений сборок, на которые ссылается сборка с указанным удостоверением.</span><span class="sxs-lookup"><span data-stu-id="40ca9-114">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity.</span></span>|  
|[<span data-ttu-id="40ca9-115">Метод GetReferencedAssembliesFromFile</span><span class="sxs-lookup"><span data-stu-id="40ca9-115">GetReferencedAssembliesFromFile Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|<span data-ttu-id="40ca9-116">Возвращает экземпляр [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) , содержащий список сборок, на которые ссылается сборка по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="40ca9-116">Gets an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>|  
|[<span data-ttu-id="40ca9-117">Метод GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="40ca9-117">GetReferencedAssembliesFromStream Method</span></span>](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|<span data-ttu-id="40ca9-118">Возвращает указатель на `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборок, на которые ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="40ca9-118">Gets a pointer to an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>|  
|[<span data-ttu-id="40ca9-119">Метод IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="40ca9-119">IsStronglyNamed Method</span></span>](iclrassemblyidentitymanager-isstronglynamed-method.md)|<span data-ttu-id="40ca9-120">Возвращает значение, указывающее, является ли указанная сборка строго именованной.</span><span class="sxs-lookup"><span data-stu-id="40ca9-120">Gets a value that indicates whether the specified assembly is strongly named.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40ca9-121">Комментарии</span><span class="sxs-lookup"><span data-stu-id="40ca9-121">Remarks</span></span>  

 <span data-ttu-id="40ca9-122">Используйте `ICLRAssemblyIdentityManager` для получения экземпляров `ICLRAssemblyReferenceList` и для перечисления идентификаторов сборок.</span><span class="sxs-lookup"><span data-stu-id="40ca9-122">Use `ICLRAssemblyIdentityManager` to get instances of `ICLRAssemblyReferenceList` and to enumerate assembly identities.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40ca9-123">Требования</span><span class="sxs-lookup"><span data-stu-id="40ca9-123">Requirements</span></span>  

 <span data-ttu-id="40ca9-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40ca9-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ca9-125">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40ca9-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40ca9-126">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40ca9-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40ca9-127">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40ca9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ca9-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40ca9-128">See also</span></span>

- [<span data-ttu-id="40ca9-129">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="40ca9-129">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="40ca9-130">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="40ca9-130">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="40ca9-131">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="40ca9-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
