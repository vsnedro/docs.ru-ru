---
title: Метод ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: 8020db491c3b66be38a9f6cbcb7551721859dcd5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723120"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="e7fd3-102">Метод ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="e7fd3-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>

<span data-ttu-id="e7fd3-103">Задает флаги запуска и файл конфигурации узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="e7fd3-104">Этот метод заменяет использование `startupFlags` параметра в функциях [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e7fd3-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7fd3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7fd3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7fd3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7fd3-106">Parameters</span></span>  

 `dwStartupFlags`  
 <span data-ttu-id="e7fd3-107">окне Заданные флаги запуска узла.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="e7fd3-108">Используйте те же флаги, что и для функций [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e7fd3-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="e7fd3-109">окне Путь к каталогу устанавливаемого файла конфигурации узла.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7fd3-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7fd3-110">Return Value</span></span>  

 <span data-ttu-id="e7fd3-111">Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e7fd3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7fd3-112">HRESULT</span></span>|<span data-ttu-id="e7fd3-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="e7fd3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7fd3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7fd3-114">S_OK</span></span>|<span data-ttu-id="e7fd3-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7fd3-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e7fd3-116">Remarks</span></span>  

 <span data-ttu-id="e7fd3-117">Многопоточный узел должен синхронизировать вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="e7fd3-118">В противном случае поток A может вызвать `SetStartupFlags` метод после того, как поток б завершит вызов `SetStartupFlags` и до того, как поток b запустит среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7fd3-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7fd3-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e7fd3-119">Requirements</span></span>  

 <span data-ttu-id="e7fd3-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7fd3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7fd3-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e7fd3-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e7fd3-122">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7fd3-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7fd3-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7fd3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7fd3-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e7fd3-124">See also</span></span>

- [<span data-ttu-id="e7fd3-125">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e7fd3-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="e7fd3-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e7fd3-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e7fd3-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="e7fd3-127">Hosting</span></span>](index.md)
