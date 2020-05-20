---
title: Функция _CorImageUnloading
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: 585287f63f57f55e877c94684820833b6d1add60
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616543"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="dcbcb-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="dcbcb-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="dcbcb-103">Уведомляет загрузчик об выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="dcbcb-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-104">This function is not implemented.</span></span> <span data-ttu-id="dcbcb-105">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcbcb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcbcb-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcbcb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="dcbcb-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="dcbcb-108">окне Указатель на начальное расположение изображения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="dcbcb-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcbcb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dcbcb-109">Requirements</span></span>  
 <span data-ttu-id="dcbcb-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcbcb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcbcb-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="dcbcb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dcbcb-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dcbcb-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcbcb-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcbcb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbcb-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="dcbcb-114">See also</span></span>

- [<span data-ttu-id="dcbcb-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="dcbcb-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
