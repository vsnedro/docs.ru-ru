---
title: Метод ICLRDebugManager::SetSymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetSymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetSymbolReadingPolicy
helpviewer_keywords:
- ICLRDebugManager, SetSymbolREadingPolicy method
- SetSymbolReadingPolicy method [.NET Framework hosting]
- ICLRDebugManager::SetSymbolReadingPolicy method [.NET Framework hosting]
ms.assetid: bd921fa2-d377-4d79-acfc-64c38d4dcae9
topic_type:
- apiref
ms.openlocfilehash: f037e902a9f573023022c81503ea3b987cf6d424
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615765"
---
# <a name="iclrdebugmanagersetsymbolreadingpolicy-method"></a><span data-ttu-id="ac17a-102">Метод ICLRDebugManager::SetSymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="ac17a-102">ICLRDebugManager::SetSymbolReadingPolicy Method</span></span>
<span data-ttu-id="ac17a-103">Задает политику чтения файлов базы данных программы (PDB).</span><span class="sxs-lookup"><span data-stu-id="ac17a-103">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="ac17a-104">Политика определяет, включаются ли в стеки вызовов сведения о номерах строк и файлах.</span><span class="sxs-lookup"><span data-stu-id="ac17a-104">The policy determines whether information about line numbers and files is included in call stacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac17a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac17a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymbolReadingPolicy (  
    [in] ESymbolReadingPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac17a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ac17a-106">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="ac17a-107">окне Член перечисления [есимболреадингполици](esymbolreadingpolicy-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ac17a-107">[in] A member of the [ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac17a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac17a-108">Return Value</span></span>  
  
|<span data-ttu-id="ac17a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac17a-109">HRESULT</span></span>|<span data-ttu-id="ac17a-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ac17a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac17a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac17a-111">S_OK</span></span>|<span data-ttu-id="ac17a-112">`SetSymbolReadingPolicy`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ac17a-112">`SetSymbolReadingPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="ac17a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac17a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac17a-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ac17a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac17a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac17a-115">E_FAIL</span></span>|<span data-ttu-id="ac17a-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac17a-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac17a-117">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ac17a-117">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac17a-118">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac17a-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac17a-119">Требования</span><span class="sxs-lookup"><span data-stu-id="ac17a-119">Requirements</span></span>  
 <span data-ttu-id="ac17a-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac17a-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac17a-121">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ac17a-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac17a-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ac17a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac17a-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac17a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac17a-124">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ac17a-124">See also</span></span>

- [<span data-ttu-id="ac17a-125">Интерфейс ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="ac17a-125">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
