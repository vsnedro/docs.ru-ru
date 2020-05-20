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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703840"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="3cbbb-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="3cbbb-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="3cbbb-103">Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.</span><span class="sxs-lookup"><span data-stu-id="3cbbb-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3cbbb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="3cbbb-104">Methods</span></span>  
  
|<span data-ttu-id="3cbbb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="3cbbb-105">Method</span></span>|<span data-ttu-id="3cbbb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="3cbbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3cbbb-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="3cbbb-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="3cbbb-108">Гарантирует, что некоторые редкие состояния гонки, которые могут вызвать неустранимые ошибки среды CLR, никогда не будут возникать.</span><span class="sxs-lookup"><span data-stu-id="3cbbb-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="3cbbb-109">Метод SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="3cbbb-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="3cbbb-110">Указывает категории управляемых типов и членов, выполнение которых должно быть заблокировано в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="3cbbb-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3cbbb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3cbbb-111">Requirements</span></span>  
 <span data-ttu-id="3cbbb-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cbbb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbbb-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3cbbb-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cbbb-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3cbbb-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3cbbb-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cbbb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbbb-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="3cbbb-116">See also</span></span>

- [<span data-ttu-id="3cbbb-117">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="3cbbb-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="3cbbb-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3cbbb-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
