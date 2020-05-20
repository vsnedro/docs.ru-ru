---
title: Метод ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7fa02c4c79da118543117aada7d1b9cca09c4cae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703401"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="fbdb9-102">Метод ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="fbdb9-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="fbdb9-103">Задает поведение среды CLR при возникновении необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbdb9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbdb9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbdb9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbdb9-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="fbdb9-106">окне Одно из значений [еклрунхандледексцептион](eclrunhandledexception-enumeration.md) , указывающее, задано ли поведение средой CLR или узлом.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbdb9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fbdb9-107">Return Value</span></span>  
  
|<span data-ttu-id="fbdb9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbdb9-108">HRESULT</span></span>|<span data-ttu-id="fbdb9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fbdb9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbdb9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbdb9-110">S_OK</span></span>|<span data-ttu-id="fbdb9-111">`SetUnhandledExceptionPolicy`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="fbdb9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbdb9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbdb9-113">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fbdb9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fbdb9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fbdb9-115">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-115">The call timed out.</span></span>|  
|<span data-ttu-id="fbdb9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fbdb9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fbdb9-117">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fbdb9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fbdb9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fbdb9-119">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fbdb9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbdb9-120">E_FAIL</span></span>|<span data-ttu-id="fbdb9-121">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fbdb9-122">После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fbdb9-123">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbdb9-124">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fbdb9-124">Remarks</span></span>  
 <span data-ttu-id="fbdb9-125">По умолчанию CLR является окончательным обработчиком для всех необработанных исключений, и его поведение по умолчанию заключается в том, чтобы разорвать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="fbdb9-126">Узел может изменить это поведение, задав `policy` значение ехостдетерминедполици.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="fbdb9-127">Это значение позволяет ведущему приложению реализовать собственное поведение по умолчанию, как в предыдущих версиях среды CLR.</span><span class="sxs-lookup"><span data-stu-id="fbdb9-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbdb9-128">Требования</span><span class="sxs-lookup"><span data-stu-id="fbdb9-128">Requirements</span></span>  
 <span data-ttu-id="fbdb9-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbdb9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbdb9-130">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fbdb9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbdb9-131">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fbdb9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbdb9-132">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbdb9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbdb9-133">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="fbdb9-133">See also</span></span>

- [<span data-ttu-id="fbdb9-134">Перечисление EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="fbdb9-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="fbdb9-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fbdb9-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="fbdb9-136">Интерфейс ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="fbdb9-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="fbdb9-137">Интерфейс IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="fbdb9-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
