---
title: Метод ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703863"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="b236d-102">Метод ICLRRuntimeInfo::GetProcAddress</span><span class="sxs-lookup"><span data-stu-id="b236d-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="b236d-103">Возвращает адрес указанной функции, которая была экспортирована из среды CLR, связанной с этим интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="b236d-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="b236d-104">Этот метод заменяет функцию [жетреалпрокаддресс](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b236d-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b236d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b236d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b236d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b236d-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="b236d-107">окне Имя экспортированной функции.</span><span class="sxs-lookup"><span data-stu-id="b236d-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="b236d-108">заполняет Адрес экспортированной функции.</span><span class="sxs-lookup"><span data-stu-id="b236d-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b236d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b236d-109">Return Value</span></span>  
 <span data-ttu-id="b236d-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="b236d-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b236d-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b236d-111">HRESULT</span></span>|<span data-ttu-id="b236d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b236d-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b236d-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b236d-113">S_OK</span></span>|<span data-ttu-id="b236d-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b236d-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b236d-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b236d-115">E_POINTER</span></span>|<span data-ttu-id="b236d-116">`pszProcName` или `ppProc` равно null.</span><span class="sxs-lookup"><span data-stu-id="b236d-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="b236d-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b236d-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b236d-118">Указанная функция не является экспортированной функцией.</span><span class="sxs-lookup"><span data-stu-id="b236d-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b236d-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b236d-119">Remarks</span></span>  
 <span data-ttu-id="b236d-120">Этот метод приводит к тому, что среда CLR загружается, но не инициализируется.</span><span class="sxs-lookup"><span data-stu-id="b236d-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b236d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="b236d-121">Requirements</span></span>  
 <span data-ttu-id="b236d-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b236d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b236d-123">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="b236d-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b236d-124">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b236d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b236d-125">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b236d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b236d-126">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b236d-126">See also</span></span>

- [<span data-ttu-id="b236d-127">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b236d-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b236d-128">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b236d-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b236d-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="b236d-129">Hosting</span></span>](index.md)
