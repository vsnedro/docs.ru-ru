---
title: Метод ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 8513787f48ae89632816face386bbcda20555dac
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703887"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="4e234-102">Метод ICLRRuntimeInfo::GetDefaultStartupFlags</span><span class="sxs-lookup"><span data-stu-id="4e234-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="4e234-103">Возвращает флаги запуска и файл конфигурации узла, которые будут использоваться для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e234-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e234-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e234-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e234-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e234-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="4e234-106">заполняет Указатель на установленные в данный момент флаги запуска узла.</span><span class="sxs-lookup"><span data-stu-id="4e234-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="4e234-107">заполняет Указатель на путь к каталогу текущего файла конфигурации узла.</span><span class="sxs-lookup"><span data-stu-id="4e234-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="4e234-108">[вход, выход] Во входных данных — размер `pwzHostConfigFile` , чтобы избежать переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="4e234-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="4e234-109">Если `pwzHostConfigFile` имеет значение null, метод возвращает требуемый размер `pwzHostConfigFile` для предварительного выделения.</span><span class="sxs-lookup"><span data-stu-id="4e234-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e234-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e234-110">Return Value</span></span>  
 <span data-ttu-id="4e234-111">Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="4e234-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4e234-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e234-112">HRESULT</span></span>|<span data-ttu-id="4e234-113">Описание</span><span class="sxs-lookup"><span data-stu-id="4e234-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e234-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e234-114">S_OK</span></span>|<span data-ttu-id="4e234-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="4e234-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e234-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4e234-116">Remarks</span></span>  
 <span data-ttu-id="4e234-117">Этот метод возвращает значения флагов по умолчанию ( `STARTUP_CONCURRENT_GC` и `NULL` ) или значения, предоставленные предыдущим вызовом [метода ICLRRuntimeInfo:: сетдефаултстартупфлагс](iclrruntimeinfo-setdefaultstartupflags-method.md), или значения, заданные любыми `CorBind*` методами, если они привязаны к этой среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="4e234-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e234-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4e234-118">Requirements</span></span>  
 <span data-ttu-id="4e234-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e234-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e234-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="4e234-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4e234-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e234-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e234-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e234-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e234-123">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4e234-123">See also</span></span>

- [<span data-ttu-id="4e234-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="4e234-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4e234-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4e234-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="4e234-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="4e234-126">Hosting</span></span>](index.md)
