---
title: Функция CLRCreateInstance
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
ms.openlocfilehash: 3c7a14f828e55310435a99693c1195f2f0dd40c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711680"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="d0357-102">Функция CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="d0357-102">CLRCreateInstance Function</span></span>

<span data-ttu-id="d0357-103">Предоставляет один из трех интерфейсов: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)или [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d0357-103">Provides one of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0357-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0357-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0357-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0357-105">Parameters</span></span>  

 `clsid`  
 <span data-ttu-id="d0357-106">окне Один из трех идентификаторов класса: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy или CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="d0357-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="d0357-107">окне Один из трех идентификаторов интерфейса (идентификаторов IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy или IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="d0357-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="d0357-108">заполняет Один из трех интерфейсов: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)или [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d0357-108">[out] One of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0357-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0357-109">Return Value</span></span>  

 <span data-ttu-id="d0357-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="d0357-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d0357-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0357-111">HRESULT</span></span>|<span data-ttu-id="d0357-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="d0357-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0357-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0357-113">S_OK</span></span>|<span data-ttu-id="d0357-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d0357-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d0357-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d0357-115">E_POINTER</span></span>|<span data-ttu-id="d0357-116">Параметр `ppInterface` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="d0357-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0357-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d0357-117">Remarks</span></span>  

 <span data-ttu-id="d0357-118">В следующей таблице приведены поддерживаемые сочетания для `clsid` и `riid` .</span><span class="sxs-lookup"><span data-stu-id="d0357-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="d0357-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="d0357-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="d0357-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="d0357-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="d0357-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="d0357-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="d0357-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="d0357-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="d0357-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="d0357-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="d0357-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="d0357-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="d0357-125">В следующем коде показано, как использовать `CLRCreateInstance` для получения всех трех интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="d0357-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d0357-126">Требования</span><span class="sxs-lookup"><span data-stu-id="d0357-126">Requirements</span></span>  

 <span data-ttu-id="d0357-127">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0357-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0357-128">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="d0357-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d0357-129">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0357-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0357-130">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0357-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0357-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0357-131">See also</span></span>

- [<span data-ttu-id="d0357-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="d0357-132">Hosting</span></span>](index.md)
