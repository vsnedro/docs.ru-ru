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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616740"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="e97c5-102">Компонентный класс ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="e97c5-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="e97c5-103">Предоставляет интерфейсы для управления упаковкой указателей интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e97c5-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e97c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e97c5-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="e97c5-105">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e97c5-105">Interfaces</span></span>  
  
|<span data-ttu-id="e97c5-106">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="e97c5-106">Interface</span></span>|<span data-ttu-id="e97c5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e97c5-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="e97c5-108">Предоставляет методы для создания, инициализации и управления прокси-сервером в клиентском процессе.</span><span class="sxs-lookup"><span data-stu-id="e97c5-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e97c5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e97c5-109">Requirements</span></span>  
 <span data-ttu-id="e97c5-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e97c5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e97c5-111">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="e97c5-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e97c5-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e97c5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e97c5-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e97c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97c5-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e97c5-114">See also</span></span>

- [<span data-ttu-id="e97c5-115">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="e97c5-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
