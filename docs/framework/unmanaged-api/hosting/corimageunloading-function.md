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
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723159"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="254c7-102">Функция _CorImageUnloading</span><span class="sxs-lookup"><span data-stu-id="254c7-102">_CorImageUnloading Function</span></span>

<span data-ttu-id="254c7-103">Уведомляет загрузчик об выгрузке образов управляемого модуля.</span><span class="sxs-lookup"><span data-stu-id="254c7-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="254c7-104">Эта функция не реализована.</span><span class="sxs-lookup"><span data-stu-id="254c7-104">This function is not implemented.</span></span> <span data-ttu-id="254c7-105">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="254c7-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="254c7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="254c7-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="254c7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="254c7-107">Parameters</span></span>  

 `ImageBase`  
 <span data-ttu-id="254c7-108">окне Указатель на начальное расположение изображения для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="254c7-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="254c7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="254c7-109">Requirements</span></span>  

 <span data-ttu-id="254c7-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="254c7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="254c7-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="254c7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="254c7-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="254c7-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="254c7-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="254c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254c7-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="254c7-114">See also</span></span>

- [<span data-ttu-id="254c7-115">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="254c7-115">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
