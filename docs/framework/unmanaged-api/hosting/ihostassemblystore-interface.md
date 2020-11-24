---
title: Интерфейс IHostAssemblyStore
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
ms.openlocfilehash: 4b2fed963d2d0ebec54e5f7a4d95cba26c1bac1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680957"
---
# <a name="ihostassemblystore-interface"></a><span data-ttu-id="1aa72-102">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="1aa72-102">IHostAssemblyStore Interface</span></span>

<span data-ttu-id="1aa72-103">Предоставляет методы, позволяющие узлу загружать сборки и модули независимо от общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="1aa72-103">Provides methods that allow a host to load assemblies and modules independently of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1aa72-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1aa72-104">Methods</span></span>  
  
|<span data-ttu-id="1aa72-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1aa72-105">Method</span></span>|<span data-ttu-id="1aa72-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1aa72-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1aa72-107">Метод ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="1aa72-107">ProvideAssembly Method</span></span>](ihostassemblystore-provideassembly-method.md)|<span data-ttu-id="1aa72-108">Возвращает ссылку на сборку, на которую не ссылается [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , возвращенную из вызова [IHostAssemblyManager:: GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="1aa72-108">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) returned from a call to [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span>|  
|[<span data-ttu-id="1aa72-109">Метод ProvideModule</span><span class="sxs-lookup"><span data-stu-id="1aa72-109">ProvideModule Method</span></span>](ihostassemblystore-providemodule-method.md)|<span data-ttu-id="1aa72-110">Разрешает модуль в сборке или в связанном (не внедренном) файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1aa72-110">Resolves a module within an assembly or a linked (not embedded) resource file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa72-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1aa72-111">Remarks</span></span>  

 <span data-ttu-id="1aa72-112">`IHostAssemblyStore` Предоставляет узлу способ эффективного загрузки сборок на основе удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="1aa72-112">`IHostAssemblyStore` provides a way for a host to load assemblies efficiently based on assembly identity.</span></span> <span data-ttu-id="1aa72-113">Узел загружает сборки, возвращая `IStream` экземпляры, которые указывают непосредственно в байтах.</span><span class="sxs-lookup"><span data-stu-id="1aa72-113">The host loads assemblies by returning `IStream` instances that point directly at the bytes.</span></span>  
  
 <span data-ttu-id="1aa72-114">Среда CLR определяет, реализован ли узел `IHostAssemblyStore` путем вызова `IHostAssemblyManager::GetNonHostAssemblyStores` после инициализации.</span><span class="sxs-lookup"><span data-stu-id="1aa72-114">The CLR determines whether a host has implemented `IHostAssemblyStore` by calling `IHostAssemblyManager::GetNonHostAssemblyStores` upon initialization.</span></span> <span data-ttu-id="1aa72-115">Это позволяет узлу, например, управлять привязкой к пользовательским сборкам, а также использовать среду выполнения для привязки к .NET Framework сборкам.</span><span class="sxs-lookup"><span data-stu-id="1aa72-115">This allows the host, for example, to control binding to user assemblies, but to rely on the runtime to bind to .NET Framework assemblies.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1aa72-116">При предоставлении реализации `IHostAssemblyStore` узел определяет его цель для разрешения всех сборок, на которые не ссылается объект, `ICLRAssemblyReferenceList` возвращенный из `IHostAssemblyManager::GetNonHostStoreAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="1aa72-116">In providing an implementation of `IHostAssemblyStore`, the host specifies its intent to resolve all assemblies that are not referenced by the `ICLRAssemblyReferenceList` returned from `IHostAssemblyManager::GetNonHostStoreAssemblies`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1aa72-117">.NET Framework версии 2,0 не позволяет узлу загружать машинный образ сборки, как это предоставляется программой [генератора образов в машинном код (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) .</span><span class="sxs-lookup"><span data-stu-id="1aa72-117">The .NET Framework version 2.0 does not provide a way for the host to load the native image of an assembly, as provided by the [Native Image Generator (Ngen.exe)](../../tools/ngen-exe-native-image-generator.md) utility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa72-118">Требования</span><span class="sxs-lookup"><span data-stu-id="1aa72-118">Requirements</span></span>  

 <span data-ttu-id="1aa72-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa72-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa72-120">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1aa72-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1aa72-121">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1aa72-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aa72-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa72-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa72-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1aa72-123">See also</span></span>

- [<span data-ttu-id="1aa72-124">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="1aa72-124">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1aa72-125">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="1aa72-125">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="1aa72-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="1aa72-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
