---
title: Компонентный класс ComCallUnmarshal
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731726"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="c6947-102">Компонентный класс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="c6947-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="c6947-103">Предоставляет интерфейсы для управления упаковкой указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c6947-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6947-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6947-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c6947-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="c6947-105">Interfaces</span></span>  
  
|<span data-ttu-id="c6947-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="c6947-106">Interface</span></span>|<span data-ttu-id="c6947-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c6947-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="c6947-108">Предоставляет методы для создания, инициализации и управления прокси-сервером в клиентском процессе.</span><span class="sxs-lookup"><span data-stu-id="c6947-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6947-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c6947-109">Requirements</span></span>  

 <span data-ttu-id="c6947-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6947-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6947-111">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="c6947-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c6947-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6947-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6947-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6947-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6947-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c6947-114">See also</span></span>

- [<span data-ttu-id="c6947-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="c6947-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
