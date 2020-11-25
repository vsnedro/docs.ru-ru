---
title: Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: df0b2d96963ad03e04bd8770d8a8078c6c20b8ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728873"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="ace3a-102">Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="ace3a-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>

<span data-ttu-id="ace3a-103">Вызывает указанный метод указанного типа в указанной управляемой сборке.</span><span class="sxs-lookup"><span data-stu-id="ace3a-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ace3a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ace3a-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ace3a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ace3a-105">Parameters</span></span>  

 `pwzAssemblyPath`  
 <span data-ttu-id="ace3a-106">окне Путь к элементу <xref:System.Reflection.Assembly> , который определяет <xref:System.Type> метод, для которого нужно вызвать.</span><span class="sxs-lookup"><span data-stu-id="ace3a-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="ace3a-107">окне Имя объекта <xref:System.Type> , определяющего вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="ace3a-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="ace3a-108">окне Имя вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="ace3a-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="ace3a-109">окне Строковый параметр для передачи в метод.</span><span class="sxs-lookup"><span data-stu-id="ace3a-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="ace3a-110">заполняет Целочисленное значение, возвращаемое вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="ace3a-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ace3a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ace3a-111">Return Value</span></span>  
  
|<span data-ttu-id="ace3a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ace3a-112">HRESULT</span></span>|<span data-ttu-id="ace3a-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="ace3a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ace3a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ace3a-114">S_OK</span></span>|<span data-ttu-id="ace3a-115">`ExecuteInDefaultAppDomain` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="ace3a-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="ace3a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ace3a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ace3a-117">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ace3a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ace3a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ace3a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ace3a-119">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="ace3a-119">The call timed out.</span></span>|  
|<span data-ttu-id="ace3a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ace3a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ace3a-121">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="ace3a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ace3a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ace3a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ace3a-123">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="ace3a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ace3a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ace3a-124">E_FAIL</span></span>|<span data-ttu-id="ace3a-125">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ace3a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ace3a-126">Если метод возвращает E_FAIL, список отзыва сертификатов больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ace3a-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="ace3a-127">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ace3a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ace3a-128">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ace3a-128">Remarks</span></span>  

 <span data-ttu-id="ace3a-129">Вызванный метод должен иметь следующую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="ace3a-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="ace3a-130">где `pwzMethodName` представляет имя вызванного метода и `pwzArgument` представляет строковое значение, передаваемое в качестве параметра этому методу.</span><span class="sxs-lookup"><span data-stu-id="ace3a-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="ace3a-131">Если значение HRESULT установлено в S_OK, то для параметра задается `pReturnValue` целочисленное значение, возвращаемое вызванным методом.</span><span class="sxs-lookup"><span data-stu-id="ace3a-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="ace3a-132">В противном случае `pReturnValue` значение не задано.</span><span class="sxs-lookup"><span data-stu-id="ace3a-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ace3a-133">Требования</span><span class="sxs-lookup"><span data-stu-id="ace3a-133">Requirements</span></span>  

 <span data-ttu-id="ace3a-134">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ace3a-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ace3a-135">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ace3a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ace3a-136">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ace3a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ace3a-137">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ace3a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace3a-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ace3a-138">See also</span></span>

- [<span data-ttu-id="ace3a-139">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ace3a-139">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
