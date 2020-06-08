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
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504021"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="f07d4-102">Метод ICLRRuntimeInfo::SetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="f07d4-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="f07d4-103">Задает флаги запуска и файл конфигурации узла, который будет использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f07d4-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="f07d4-104">Этот метод заменяет использование `startupFlags` параметра в функциях [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f07d4-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07d4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f07d4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f07d4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f07d4-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="f07d4-107">окне Заданные флаги запуска узла.</span><span class="sxs-lookup"><span data-stu-id="f07d4-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="f07d4-108">Используйте те же флаги, что и для функций [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f07d4-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="f07d4-109">окне Путь к каталогу устанавливаемого файла конфигурации узла.</span><span class="sxs-lookup"><span data-stu-id="f07d4-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f07d4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f07d4-110">Return Value</span></span>  
 <span data-ttu-id="f07d4-111">Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f07d4-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f07d4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f07d4-112">HRESULT</span></span>|<span data-ttu-id="f07d4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f07d4-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f07d4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f07d4-114">S_OK</span></span>|<span data-ttu-id="f07d4-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f07d4-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f07d4-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="f07d4-116">Remarks</span></span>  
 <span data-ttu-id="f07d4-117">Многопоточный узел должен синхронизировать вызовы этого метода.</span><span class="sxs-lookup"><span data-stu-id="f07d4-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="f07d4-118">В противном случае поток A может вызвать `SetStartupFlags` метод после того, как поток б завершит вызов `SetStartupFlags` и до того, как поток b запустит среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f07d4-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07d4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="f07d4-119">Requirements</span></span>  
 <span data-ttu-id="f07d4-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f07d4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f07d4-121">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="f07d4-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f07d4-122">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f07d4-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f07d4-123">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f07d4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07d4-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f07d4-124">See also</span></span>

- [<span data-ttu-id="f07d4-125">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f07d4-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f07d4-126">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f07d4-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f07d4-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="f07d4-127">Hosting</span></span>](index.md)
