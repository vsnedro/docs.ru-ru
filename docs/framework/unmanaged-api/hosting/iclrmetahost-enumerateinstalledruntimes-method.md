---
title: Метод ICLRMetaHost::EnumerateInstalledRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: c99607bfe5fda01eb1abfd7771cb3907ddabeec5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703772"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="ab35c-102">Метод ICLRMetaHost::EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="ab35c-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="ab35c-103">Возвращает перечисление, которое содержит допустимый интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой версии среды CLR, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab35c-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab35c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab35c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab35c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab35c-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="ab35c-106">заполняет Перечисление интерфейсов [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующих каждой версии среды CLR, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ab35c-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab35c-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab35c-107">Return Value</span></span>  
 <span data-ttu-id="ab35c-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="ab35c-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab35c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab35c-109">HRESULT</span></span>|<span data-ttu-id="ab35c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="ab35c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab35c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab35c-111">S_OK</span></span>|<span data-ttu-id="ab35c-112">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ab35c-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="ab35c-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ab35c-113">E_POINTER</span></span>|<span data-ttu-id="ab35c-114">Параметр `ppEnumerator` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="ab35c-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab35c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ab35c-115">Requirements</span></span>  
 <span data-ttu-id="ab35c-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab35c-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab35c-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="ab35c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab35c-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab35c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab35c-119">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab35c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab35c-120">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ab35c-120">See also</span></span>

- [<span data-ttu-id="ab35c-121">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="ab35c-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="ab35c-122">Размещение</span><span class="sxs-lookup"><span data-stu-id="ab35c-122">Hosting</span></span>](index.md)
