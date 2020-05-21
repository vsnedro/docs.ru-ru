---
title: Метод ICorRuntimeHost::Start
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: ccad76e1c8a49222d4f527f8b7b18d4e40ff8cae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760411"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="84e34-102">Метод ICorRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="84e34-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="84e34-103">Запускает среду CLR.</span><span class="sxs-lookup"><span data-stu-id="84e34-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84e34-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="84e34-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84e34-105">Return Value</span></span>  
  
|<span data-ttu-id="84e34-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84e34-106">HRESULT</span></span>|<span data-ttu-id="84e34-107">Описание</span><span class="sxs-lookup"><span data-stu-id="84e34-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84e34-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="84e34-108">S_OK</span></span>|<span data-ttu-id="84e34-109">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="84e34-109">The operation was successful.</span></span>|  
|<span data-ttu-id="84e34-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="84e34-110">S_FALSE</span></span>|<span data-ttu-id="84e34-111">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="84e34-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="84e34-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84e34-112">E_FAIL</span></span>|<span data-ttu-id="84e34-113">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="84e34-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="84e34-114">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="84e34-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="84e34-115">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84e34-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84e34-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84e34-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84e34-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="84e34-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84e34-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="84e34-118">Remarks</span></span>  
 <span data-ttu-id="84e34-119">Как правило, вызов метода не требуется `Start` , поскольку среда CLR запускается автоматически при первом запросе на выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="84e34-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e34-120">Требования</span><span class="sxs-lookup"><span data-stu-id="84e34-120">Requirements</span></span>  
 <span data-ttu-id="84e34-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e34-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e34-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84e34-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84e34-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84e34-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84e34-124">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="84e34-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e34-125">См. также</span><span class="sxs-lookup"><span data-stu-id="84e34-125">See also</span></span>

- [<span data-ttu-id="84e34-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="84e34-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
