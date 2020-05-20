---
title: Интерфейс ICLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615882"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="9c49a-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="9c49a-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="9c49a-103">Управляет списком сборок, загружаемых средой CLR, а не узлом.</span><span class="sxs-lookup"><span data-stu-id="9c49a-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c49a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9c49a-104">Methods</span></span>  
  
|<span data-ttu-id="9c49a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9c49a-105">Method</span></span>|<span data-ttu-id="9c49a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9c49a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c49a-107">Метод IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="9c49a-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="9c49a-108">Возвращает значение, указывающее, ссылается ли указанный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="9c49a-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="9c49a-109">Метод IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="9c49a-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="9c49a-110">Возвращает значение, указывающее, совпадает ли заданное имя с именем сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="9c49a-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c49a-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9c49a-111">Remarks</span></span>  
 <span data-ttu-id="9c49a-112">Вызовите метод [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist-](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , чтобы получить указатель на экземпляр `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="9c49a-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c49a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9c49a-113">Requirements</span></span>  
 <span data-ttu-id="9c49a-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c49a-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c49a-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9c49a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c49a-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c49a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c49a-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c49a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c49a-118">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9c49a-118">See also</span></span>

- [<span data-ttu-id="9c49a-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9c49a-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9c49a-120">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="9c49a-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="9c49a-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9c49a-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
