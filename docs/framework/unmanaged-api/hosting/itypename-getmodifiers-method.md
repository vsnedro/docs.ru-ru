---
title: Метод ITypeName::GetModifiers
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 64751032c017473ffd82248b310b14c087f74129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727839"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="cf2e5-102">Метод ITypeName::GetModifiers</span><span class="sxs-lookup"><span data-stu-id="cf2e5-102">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="cf2e5-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="cf2e5-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf2e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf2e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf2e5-105">Требования</span><span class="sxs-lookup"><span data-stu-id="cf2e5-105">Requirements</span></span>  

 <span data-ttu-id="cf2e5-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf2e5-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf2e5-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf2e5-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf2e5-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf2e5-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf2e5-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2e5-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf2e5-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cf2e5-110">See also</span></span>

- [<span data-ttu-id="cf2e5-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cf2e5-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
