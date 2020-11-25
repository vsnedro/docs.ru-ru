---
title: Метод ITypeNameFactory::GetTypeNameBuilder
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.GetTypeNameBuilder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeNameBuilder
helpviewer_keywords:
- ITypeNameFactory::GetTypeNameBuilder method [.NET Framework hosting]
- GetTypeNameBuilder method [.NET Framework hosting]
ms.assetid: c682f744-996e-43c7-a9ea-c57cbc755398
topic_type:
- apiref
ms.openlocfilehash: 67e5e66ae88cfcc777d631268ed555bcb4eb31b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728749"
---
# <a name="itypenamefactorygettypenamebuilder-method"></a><span data-ttu-id="2836b-102">Метод ITypeNameFactory::GetTypeNameBuilder</span><span class="sxs-lookup"><span data-stu-id="2836b-102">ITypeNameFactory::GetTypeNameBuilder Method</span></span>

<span data-ttu-id="2836b-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="2836b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2836b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2836b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeNameBuilder (  
    [out, retval] ITypeNameBuilder** ppTypeBuilder  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2836b-105">Требования</span><span class="sxs-lookup"><span data-stu-id="2836b-105">Requirements</span></span>  

 <span data-ttu-id="2836b-106">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2836b-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2836b-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2836b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2836b-108">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2836b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2836b-109">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2836b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2836b-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2836b-110">See also</span></span>

- [<span data-ttu-id="2836b-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="2836b-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
