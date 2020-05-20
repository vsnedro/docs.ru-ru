---
title: Интерфейс ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 3cf2a945607bf85a51dbec35342ff5ac46878bca
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703565"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="fc660-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="fc660-102">ICLRHostBindingPolicyManager Interface</span></span>
<span data-ttu-id="fc660-103">Предоставляет основному приложению методы для вычисления текущей политики привязки и обмена изменениями политики для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="fc660-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc660-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fc660-104">Methods</span></span>  
  
|<span data-ttu-id="fc660-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fc660-105">Method</span></span>|<span data-ttu-id="fc660-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fc660-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fc660-107">Метод EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="fc660-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="fc660-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="fc660-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="fc660-109">Метод ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="fc660-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="fc660-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="fc660-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc660-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fc660-111">Requirements</span></span>  
 <span data-ttu-id="fc660-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc660-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc660-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fc660-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc660-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fc660-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc660-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc660-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc660-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="fc660-116">See also</span></span>

- [<span data-ttu-id="fc660-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="fc660-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="fc660-118">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="fc660-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="fc660-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="fc660-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
