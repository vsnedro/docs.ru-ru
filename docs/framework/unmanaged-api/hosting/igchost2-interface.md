---
title: Интерфейс IGCHost2
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 976673a0caab4e041cc80e5536544c195fcf692a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805182"
---
# <a name="igchost2-interface"></a><span data-ttu-id="9bd30-102">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="9bd30-102">IGCHost2 Interface</span></span>
<span data-ttu-id="9bd30-103">Предоставляет методы для получения сведений о системе сборки мусора и для управления некоторыми аспектами сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="9bd30-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bd30-104">Для новой разработки рекомендуется вместо этого использовать интерфейс [ICLRGCManager2](iclrgcmanager2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9bd30-104">For new development, we recommend that you use the [ICLRGCManager2](iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9bd30-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9bd30-105">Methods</span></span>  
  
|<span data-ttu-id="9bd30-106">Метод</span><span class="sxs-lookup"><span data-stu-id="9bd30-106">Method</span></span>|<span data-ttu-id="9bd30-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9bd30-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bd30-108">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="9bd30-108">SetGCStartupLimitsEx Method</span></span>](igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="9bd30-109">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="9bd30-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="9bd30-110">Включает поколение 0 и размеры сегментов, превышающие `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="9bd30-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9bd30-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9bd30-111">Requirements</span></span>  
 <span data-ttu-id="9bd30-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bd30-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bd30-113">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="9bd30-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9bd30-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9bd30-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bd30-115">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bd30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bd30-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="9bd30-116">See also</span></span>

- [<span data-ttu-id="9bd30-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9bd30-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="9bd30-118">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9bd30-118">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="9bd30-119">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9bd30-119">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
