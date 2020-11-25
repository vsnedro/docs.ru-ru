---
title: Интерфейс ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714163"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="7bafb-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="7bafb-102">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="7bafb-103">Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.</span><span class="sxs-lookup"><span data-stu-id="7bafb-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bafb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7bafb-104">Methods</span></span>  
  
|<span data-ttu-id="7bafb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7bafb-105">Method</span></span>|<span data-ttu-id="7bafb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7bafb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bafb-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="7bafb-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="7bafb-108">Гарантирует, что некоторые редкие состояния гонки, которые могут вызвать неустранимые ошибки среды CLR, никогда не будут возникать.</span><span class="sxs-lookup"><span data-stu-id="7bafb-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="7bafb-109">Метод SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="7bafb-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="7bafb-110">Указывает категории управляемых типов и членов, выполнение которых должно быть заблокировано в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="7bafb-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7bafb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7bafb-111">Requirements</span></span>  

 <span data-ttu-id="7bafb-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bafb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bafb-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7bafb-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bafb-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bafb-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bafb-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bafb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bafb-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7bafb-116">See also</span></span>

- [<span data-ttu-id="7bafb-117">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="7bafb-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="7bafb-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7bafb-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
