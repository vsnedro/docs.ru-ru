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
ms.openlocfilehash: e3031bf123ff9107b4cebc0723f1be0d423bdaec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721755"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="68354-102">Метод IApartmentCallback::DoCallback</span><span class="sxs-lookup"><span data-stu-id="68354-102">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="68354-103">Выполняет указанную функцию в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="68354-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68354-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68354-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68354-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="68354-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="68354-106">окне Указатель на функцию, которая должна быть выполнена в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="68354-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="68354-107">окне Указатель на аргумент функции.</span><span class="sxs-lookup"><span data-stu-id="68354-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68354-108">Требования</span><span class="sxs-lookup"><span data-stu-id="68354-108">Requirements</span></span>  

 <span data-ttu-id="68354-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68354-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68354-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="68354-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="68354-111">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68354-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68354-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68354-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68354-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="68354-113">See also</span></span>

- [<span data-ttu-id="68354-114">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="68354-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
