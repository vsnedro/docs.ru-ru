---
title: Метод ICLRDebugManager::GetDacl
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
ms.openlocfilehash: 933edf734a0e02b4ac9c88d9f193277d963adada
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615804"
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="de662-102">Метод ICLRDebugManager::GetDacl</span><span class="sxs-lookup"><span data-stu-id="de662-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="de662-103">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="de662-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de662-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de662-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de662-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="de662-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="de662-106">заполняет Указатель интерфейса на список управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="de662-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de662-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="de662-107">Return Value</span></span>  
  
|<span data-ttu-id="de662-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de662-108">HRESULT</span></span>|<span data-ttu-id="de662-109">Описание</span><span class="sxs-lookup"><span data-stu-id="de662-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de662-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="de662-110">E_NOTIMPL</span></span>|<span data-ttu-id="de662-111">Метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="de662-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de662-112">Требования</span><span class="sxs-lookup"><span data-stu-id="de662-112">Requirements</span></span>  
 <span data-ttu-id="de662-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de662-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de662-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="de662-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de662-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="de662-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de662-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de662-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de662-117">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="de662-117">See also</span></span>

- [<span data-ttu-id="de662-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="de662-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="de662-119">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="de662-119">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="de662-120">Метод SetDacl</span><span class="sxs-lookup"><span data-stu-id="de662-120">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)
- [<span data-ttu-id="de662-121">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="de662-121">IHostControl Interface</span></span>](ihostcontrol-interface.md)
