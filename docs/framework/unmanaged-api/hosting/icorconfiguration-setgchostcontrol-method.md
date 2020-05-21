---
title: Метод ICorConfiguration::SetGCHostControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: e648b36a2b276d9335eefaf71b57ad76f9fe0def
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762387"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="a154b-102">Метод ICorConfiguration::SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="a154b-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="a154b-103">Задает интерфейс обратного вызова, используемый сборщиком мусора для запроса изменения ограничения виртуальной памяти на узле.</span><span class="sxs-lookup"><span data-stu-id="a154b-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a154b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a154b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a154b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a154b-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="a154b-106">окне Указатель на объект [игчостконтрол](igchostcontrol-interface.md) , который позволяет сборщику мусора запрашивать у узла изменение ограничений виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="a154b-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a154b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a154b-107">Requirements</span></span>  
 <span data-ttu-id="a154b-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a154b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a154b-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a154b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a154b-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a154b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a154b-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a154b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a154b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a154b-112">See also</span></span>

- [<span data-ttu-id="a154b-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="a154b-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
