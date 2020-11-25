---
title: Метод ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: a45f613b7547e2e80abdbd8ac85cb0b2b6a499e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716893"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="9cc36-102">Метод ICorPublish::GetProcess</span><span class="sxs-lookup"><span data-stu-id="9cc36-102">ICorPublish::GetProcess Method</span></span>

<span data-ttu-id="9cc36-103">Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="9cc36-103">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc36-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cc36-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cc36-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cc36-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="9cc36-106">окне Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="9cc36-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9cc36-107">заполняет Указатель на адрес `ICorPublishProcess` экземпляра, который представляет процесс.</span><span class="sxs-lookup"><span data-stu-id="9cc36-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cc36-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9cc36-108">Remarks</span></span>  

 <span data-ttu-id="9cc36-109">`GetProcess` завершается ошибкой, если процесс не существует или не является управляемым процессом, который может быть отлажен текущим пользователем.</span><span class="sxs-lookup"><span data-stu-id="9cc36-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc36-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9cc36-110">Requirements</span></span>  

 <span data-ttu-id="9cc36-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc36-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc36-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="9cc36-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9cc36-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cc36-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cc36-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc36-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc36-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9cc36-115">See also</span></span>

- [<span data-ttu-id="9cc36-116">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="9cc36-116">ICorPublish Interface</span></span>](icorpublish-interface.md)
