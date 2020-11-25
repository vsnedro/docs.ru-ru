---
title: Метод ITypeName::GetNames
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
ms.openlocfilehash: 91e73f8e3d2e3c372d3fe1c4fd4fccf6ff67b363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727813"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="305ff-102">Метод ITypeName::GetNames</span><span class="sxs-lookup"><span data-stu-id="305ff-102">ITypeName::GetNames Method</span></span>

<span data-ttu-id="305ff-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="305ff-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="305ff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="305ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="305ff-105">Требования</span><span class="sxs-lookup"><span data-stu-id="305ff-105">Requirements</span></span>  

 <span data-ttu-id="305ff-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="305ff-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="305ff-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="305ff-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="305ff-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="305ff-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="305ff-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="305ff-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305ff-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="305ff-110">See also</span></span>

- [<span data-ttu-id="305ff-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="305ff-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
