---
title: Fusion-интерфейсы
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 59e34a39bada1dcf5e66a0c5b92a7fcbfb41d884
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711693"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="7d1b6-102">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7d1b6-102">Fusion Interfaces</span></span>

<span data-ttu-id="7d1b6-103">В этом разделе описываются неуправляемые интерфейсы, используемые API Fusion для доступа к свойствам ресурсов приложения и для размещения правильных версий этих ресурсов для приложения.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d1b6-104">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7d1b6-104">In This Section</span></span>  

 [<span data-ttu-id="7d1b6-105">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="7d1b6-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="7d1b6-106">Предоставляет методы, создающие и сравнивающие ключи для удостоверений приложений и ссылок.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="7d1b6-107">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="7d1b6-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="7d1b6-108">Предоставляет представление глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7d1b6-109">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="7d1b6-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="7d1b6-110">Представляет отдельную сборку в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7d1b6-111">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="7d1b6-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="7d1b6-112">Представляет перечислитель для массива `IAssemblyName` объектов.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="7d1b6-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="7d1b6-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="7d1b6-114">Предоставляет методы для описания и работы с уникальным удостоверением сборки.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="7d1b6-115">Интерфейс IDefinitionAppId</span><span class="sxs-lookup"><span data-stu-id="7d1b6-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="7d1b6-116">Представляет уникальный идентификатор для кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7d1b6-117">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7d1b6-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="7d1b6-118">Представляет уникальную сигнатуру кода, определяющего приложение в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7d1b6-119">Интерфейс IEnumDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="7d1b6-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="7d1b6-120">Служит в качестве перечислителя для коллекции `IDefinitionIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="7d1b6-121">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="7d1b6-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="7d1b6-122">Служит в качестве перечислителя для атрибутов объекта Code в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="7d1b6-123">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="7d1b6-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="7d1b6-124">Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="7d1b6-125">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="7d1b6-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="7d1b6-126">Управляет ключами удостоверений для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="7d1b6-127">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="7d1b6-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="7d1b6-128">Представляет перечислитель для сборок, на которые имеются ссылки, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7d1b6-129">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="7d1b6-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="7d1b6-130">Представляет элемент, установленный в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="7d1b6-131">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="7d1b6-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="7d1b6-132">Представляет ссылку на уникальный идентификатор приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="7d1b6-133">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="7d1b6-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="7d1b6-134">Представляет ссылку на уникальную сигнатуру объекта кода.</span><span class="sxs-lookup"><span data-stu-id="7d1b6-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7d1b6-135">Справочник</span><span class="sxs-lookup"><span data-stu-id="7d1b6-135">Reference</span></span>  

 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="7d1b6-136">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7d1b6-136">Related Sections</span></span>  

 [<span data-ttu-id="7d1b6-137">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="7d1b6-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="7d1b6-138">Перечисления Fusion</span><span class="sxs-lookup"><span data-stu-id="7d1b6-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="7d1b6-139">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="7d1b6-139">Fusion Structures</span></span>](fusion-structures.md)
