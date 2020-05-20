---
title: Метод IApartmentCallback::DoCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: 1a56c3ebe4b1c528f9c6555bdfbf1270a438410d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617117"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="1cd99-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="1cd99-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="1cd99-103">Выполняет указанную функцию в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="1cd99-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cd99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cd99-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cd99-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cd99-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="1cd99-106">окне Указатель на функцию, которая должна быть выполнена в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="1cd99-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="1cd99-107">окне Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="1cd99-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cd99-108">Требования</span><span class="sxs-lookup"><span data-stu-id="1cd99-108">Requirements</span></span>  
 <span data-ttu-id="1cd99-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cd99-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cd99-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1cd99-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1cd99-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1cd99-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cd99-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd99-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd99-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="1cd99-113">See also</span></span>

- [<span data-ttu-id="1cd99-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="1cd99-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
