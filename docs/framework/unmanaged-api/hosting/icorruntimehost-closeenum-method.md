---
title: Метод ICorRuntimeHost::CloseEnum
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CloseEnum
helpviewer_keywords:
- CloseEnum method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::CloseEnum method [.NET Framework hosting]
ms.assetid: f7ce7e8c-0a3e-4587-a180-063e2b85940e
topic_type:
- apiref
ms.openlocfilehash: a5a86df3ac1f50ca624490ad80a6fed903433436
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762374"
---
# <a name="icorruntimehostcloseenum-method"></a><span data-ttu-id="6b07e-102">Метод ICorRuntimeHost::CloseEnum</span><span class="sxs-lookup"><span data-stu-id="6b07e-102">ICorRuntimeHost::CloseEnum Method</span></span>
<span data-ttu-id="6b07e-103">Сбрасывает перечислитель домена обратно в начало списка доменов.</span><span class="sxs-lookup"><span data-stu-id="6b07e-103">Resets a domain enumerator back to the beginning of the domain list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b07e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b07e-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum (  
    [in] HCORENUM hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b07e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b07e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6b07e-106">окне Перечислитель для сброса.</span><span class="sxs-lookup"><span data-stu-id="6b07e-106">[in] The enumerator to reset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b07e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6b07e-107">Return Value</span></span>  
  
|<span data-ttu-id="6b07e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b07e-108">HRESULT</span></span>|<span data-ttu-id="6b07e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6b07e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b07e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b07e-110">S_OK</span></span>|<span data-ttu-id="6b07e-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6b07e-111">The operation was successful.</span></span>|  
|<span data-ttu-id="6b07e-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6b07e-112">S_FALSE</span></span>|<span data-ttu-id="6b07e-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="6b07e-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6b07e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6b07e-114">E_FAIL</span></span>|<span data-ttu-id="6b07e-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6b07e-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6b07e-116">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6b07e-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6b07e-117">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6b07e-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6b07e-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6b07e-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6b07e-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6b07e-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b07e-120">Требования</span><span class="sxs-lookup"><span data-stu-id="6b07e-120">Requirements</span></span>  
 <span data-ttu-id="6b07e-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b07e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b07e-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6b07e-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b07e-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b07e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b07e-124">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="6b07e-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b07e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6b07e-125">See also</span></span>

- [<span data-ttu-id="6b07e-126">Функция CorBindToRuntimeEx</span><span class="sxs-lookup"><span data-stu-id="6b07e-126">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="6b07e-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6b07e-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
