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
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725638"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="e88af-102">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e88af-102">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="e88af-103">Предоставляет основному приложению методы для вычисления текущей политики привязки и обмена изменениями политики для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="e88af-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e88af-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e88af-104">Methods</span></span>  
  
|<span data-ttu-id="e88af-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e88af-105">Method</span></span>|<span data-ttu-id="e88af-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e88af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e88af-107">Метод EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="e88af-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="e88af-108">Оценивает политику привязки от имени узла.</span><span class="sxs-lookup"><span data-stu-id="e88af-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="e88af-109">Метод ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="e88af-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="e88af-110">Изменяет политику привязки для указанной сборки и создает новую версию политики.</span><span class="sxs-lookup"><span data-stu-id="e88af-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e88af-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e88af-111">Requirements</span></span>  

 <span data-ttu-id="e88af-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e88af-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e88af-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e88af-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e88af-114">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e88af-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e88af-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e88af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88af-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e88af-116">See also</span></span>

- [<span data-ttu-id="e88af-117">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="e88af-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e88af-118">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="e88af-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="e88af-119">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e88af-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
