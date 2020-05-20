---
title: Метод ICLRAssemblyIdentityManager::IsStronglyNamed
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
ms.openlocfilehash: d388f366671f50c3dcb3bd9d387300dd1bbb168f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615908"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="aaaf4-102">Метод ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="aaaf4-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="aaaf4-103">Возвращает значение, указывающее, является ли указанная сборка строго именованной.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaaf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaaf4-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaaf4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aaaf4-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="aaaf4-106">окне Непрозрачные канонические данные идентификации сборки для оценки.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="aaaf4-107">[out] `true` , если сборка, на которую ссылается `pwzAssemblyIdentity` параметр, имеет строгое имя; в противном случае — значение `false` .</span><span class="sxs-lookup"><span data-stu-id="aaaf4-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aaaf4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aaaf4-108">Return Value</span></span>  
  
|<span data-ttu-id="aaaf4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aaaf4-109">HRESULT</span></span>|<span data-ttu-id="aaaf4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="aaaf4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aaaf4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aaaf4-111">S_OK</span></span>|<span data-ttu-id="aaaf4-112">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="aaaf4-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aaaf4-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aaaf4-114">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aaaf4-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aaaf4-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aaaf4-116">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-116">The call timed out.</span></span>|  
|<span data-ttu-id="aaaf4-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aaaf4-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aaaf4-118">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aaaf4-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aaaf4-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aaaf4-120">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aaaf4-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aaaf4-121">E_FAIL</span></span>|<span data-ttu-id="aaaf4-122">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aaaf4-123">Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aaaf4-124">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aaaf4-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aaaf4-125">Требования</span><span class="sxs-lookup"><span data-stu-id="aaaf4-125">Requirements</span></span>  
 <span data-ttu-id="aaaf4-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaaf4-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaaf4-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aaaf4-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aaaf4-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aaaf4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aaaf4-129">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaaf4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaaf4-130">См. также статью</span><span class="sxs-lookup"><span data-stu-id="aaaf4-130">See also</span></span>

- [<span data-ttu-id="aaaf4-131">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="aaaf4-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
