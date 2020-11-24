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
ms.openlocfilehash: a75235cd0ac0e55412f0ba58881796e3ebc801f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679244"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="53f17-102">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="53f17-102">ICLRAssemblyReferenceList Interface</span></span>

<span data-ttu-id="53f17-103">Управляет списком сборок, загружаемых средой CLR, а не узлом.</span><span class="sxs-lookup"><span data-stu-id="53f17-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53f17-104">Методы</span><span class="sxs-lookup"><span data-stu-id="53f17-104">Methods</span></span>  
  
|<span data-ttu-id="53f17-105">Метод</span><span class="sxs-lookup"><span data-stu-id="53f17-105">Method</span></span>|<span data-ttu-id="53f17-106">Описание</span><span class="sxs-lookup"><span data-stu-id="53f17-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53f17-107">Метод IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="53f17-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="53f17-108">Возвращает значение, указывающее, ссылается ли указанный указатель на сборку в списке.</span><span class="sxs-lookup"><span data-stu-id="53f17-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="53f17-109">Метод IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="53f17-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="53f17-110">Возвращает значение, указывающее, совпадает ли заданное имя с именем сборки в списке.</span><span class="sxs-lookup"><span data-stu-id="53f17-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53f17-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="53f17-111">Remarks</span></span>  

 <span data-ttu-id="53f17-112">Вызовите метод [ICLRAssemblyIdentityManager:: getclrassemblyreferencelist-](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) , чтобы получить указатель на экземпляр `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="53f17-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f17-113">Требования</span><span class="sxs-lookup"><span data-stu-id="53f17-113">Requirements</span></span>  

 <span data-ttu-id="53f17-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53f17-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f17-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="53f17-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53f17-116">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53f17-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53f17-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53f17-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f17-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="53f17-118">See also</span></span>

- [<span data-ttu-id="53f17-119">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="53f17-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="53f17-120">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="53f17-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="53f17-121">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="53f17-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
