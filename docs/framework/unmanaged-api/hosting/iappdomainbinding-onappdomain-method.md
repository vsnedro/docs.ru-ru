---
title: Метод IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: 65f6be8c12ce057422ad178c759affed170e44ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721719"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="9ef40-102">Метод IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="9ef40-102">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="9ef40-103">Вызывается средой CLR для уведомления узла о создании домена приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef40-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ef40-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ef40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9ef40-105">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="9ef40-106">окне Указатель на объект интерфейса [IUnknown](/cpp/atl/iunknown) , представляющий новый домен приложения.</span><span class="sxs-lookup"><span data-stu-id="9ef40-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ef40-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9ef40-107">Requirements</span></span>  

 <span data-ttu-id="9ef40-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ef40-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ef40-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ef40-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ef40-110">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ef40-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ef40-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef40-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef40-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9ef40-112">See also</span></span>

- [<span data-ttu-id="9ef40-113">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="9ef40-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
