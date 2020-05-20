---
title: Интерфейс ICLRDomainManager
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615713"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="6e9eb-102">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="6e9eb-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="6e9eb-103">Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.</span><span class="sxs-lookup"><span data-stu-id="6e9eb-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e9eb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6e9eb-104">Methods</span></span>  
  
|<span data-ttu-id="6e9eb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6e9eb-105">Method</span></span>|<span data-ttu-id="6e9eb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6e9eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e9eb-107">Метод SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="6e9eb-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="6e9eb-108">Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e9eb-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="6e9eb-109">Метод SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="6e9eb-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="6e9eb-110">Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6e9eb-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e9eb-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6e9eb-111">Remarks</span></span>  
 <span data-ttu-id="6e9eb-112">Чтобы получить экземпляр этого интерфейса, вызовите метод [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) с типом менеджера IID `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="6e9eb-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e9eb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6e9eb-113">Requirements</span></span>  
 <span data-ttu-id="6e9eb-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e9eb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e9eb-115">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="6e9eb-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6e9eb-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6e9eb-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e9eb-117">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e9eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9eb-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6e9eb-118">See also</span></span>

- [<span data-ttu-id="6e9eb-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6e9eb-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="6e9eb-120">Размещение</span><span class="sxs-lookup"><span data-stu-id="6e9eb-120">Hosting</span></span>](index.md)
