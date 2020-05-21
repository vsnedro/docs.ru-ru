---
title: Метод ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762192"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="fe780-102">Метод ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="fe780-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="fe780-103">Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="fe780-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="fe780-104">Этот метод заменяет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="fe780-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="fe780-105">лоадстрингрк</span><span class="sxs-lookup"><span data-stu-id="fe780-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="fe780-106">лоадстрингрцекс</span><span class="sxs-lookup"><span data-stu-id="fe780-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="fe780-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe780-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe780-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe780-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="fe780-109">окне Значение HRESULT для преобразования.</span><span class="sxs-lookup"><span data-stu-id="fe780-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="fe780-110">заполняет Строка сообщения, связанная с данным значением HRESULT.</span><span class="sxs-lookup"><span data-stu-id="fe780-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="fe780-111">[вход, выход] Размер `pwzbuffer` во избежание переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="fe780-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="fe780-112">Если `pwzbuffer` параметр имеет значение null, `pcchBuffer` то предоставляет ожидаемый размер `pwzbuffer` для разрешения предварительного выделения.</span><span class="sxs-lookup"><span data-stu-id="fe780-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="fe780-113">окне Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="fe780-113">[in] The culture identifier.</span></span> <span data-ttu-id="fe780-114">Чтобы использовать язык и региональные параметры по умолчанию, необходимо указать значение-1.</span><span class="sxs-lookup"><span data-stu-id="fe780-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe780-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fe780-115">Return Value</span></span>  
 <span data-ttu-id="fe780-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="fe780-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fe780-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe780-117">HRESULT</span></span>|<span data-ttu-id="fe780-118">Описание</span><span class="sxs-lookup"><span data-stu-id="fe780-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe780-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe780-119">S_OK</span></span>|<span data-ttu-id="fe780-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="fe780-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="fe780-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fe780-121">E_POINTER</span></span>|<span data-ttu-id="fe780-122">Параметр `pcchBuffer` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="fe780-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="fe780-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fe780-123">E_INVALIDARG</span></span>|<span data-ttu-id="fe780-124">Параметр `pwzBuffer` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="fe780-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe780-125">Требования</span><span class="sxs-lookup"><span data-stu-id="fe780-125">Requirements</span></span>  
 <span data-ttu-id="fe780-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe780-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe780-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="fe780-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fe780-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe780-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe780-129">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe780-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe780-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fe780-130">See also</span></span>

- [<span data-ttu-id="fe780-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="fe780-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fe780-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="fe780-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fe780-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="fe780-133">Hosting</span></span>](index.md)
