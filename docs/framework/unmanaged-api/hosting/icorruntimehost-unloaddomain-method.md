---
title: Метод ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: 558b6e4c6ac369e33be3d45b7241e8b11db8bfae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760398"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="71237-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="71237-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="71237-103">Выгружает указанный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="71237-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71237-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71237-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71237-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71237-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="71237-106">окне Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен для выгрузки.</span><span class="sxs-lookup"><span data-stu-id="71237-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71237-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="71237-107">Return Value</span></span>  
  
|<span data-ttu-id="71237-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71237-108">HRESULT</span></span>|<span data-ttu-id="71237-109">Описание</span><span class="sxs-lookup"><span data-stu-id="71237-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71237-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71237-110">S_OK</span></span>|<span data-ttu-id="71237-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="71237-111">The operation was successful.</span></span>|  
|<span data-ttu-id="71237-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="71237-112">S_FALSE</span></span>|<span data-ttu-id="71237-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="71237-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="71237-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71237-114">E_FAIL</span></span>|<span data-ttu-id="71237-115">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="71237-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="71237-116">Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="71237-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="71237-117">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71237-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71237-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71237-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71237-119">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="71237-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71237-120">Требования</span><span class="sxs-lookup"><span data-stu-id="71237-120">Requirements</span></span>  
 <span data-ttu-id="71237-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71237-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71237-122">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71237-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71237-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71237-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71237-124">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="71237-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71237-125">См. также</span><span class="sxs-lookup"><span data-stu-id="71237-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="71237-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="71237-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
