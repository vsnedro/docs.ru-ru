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
ms.openlocfilehash: 0e029aa848a6630ae00c834dd2b924dc4ebce537
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671776"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="98dec-102">Метод ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="98dec-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>

<span data-ttu-id="98dec-103">Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="98dec-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="98dec-104">Этот метод заменяет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="98dec-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="98dec-105">лоадстрингрк</span><span class="sxs-lookup"><span data-stu-id="98dec-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="98dec-106">лоадстрингрцекс</span><span class="sxs-lookup"><span data-stu-id="98dec-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="98dec-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98dec-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98dec-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="98dec-108">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="98dec-109">окне Значение HRESULT для преобразования.</span><span class="sxs-lookup"><span data-stu-id="98dec-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="98dec-110">заполняет Строка сообщения, связанная с данным значением HRESULT.</span><span class="sxs-lookup"><span data-stu-id="98dec-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="98dec-111">[вход, выход] Размер `pwzbuffer` во избежание переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="98dec-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="98dec-112">Если `pwzbuffer` параметр имеет значение null, `pcchBuffer` то предоставляет ожидаемый размер `pwzbuffer` для разрешения предварительного выделения.</span><span class="sxs-lookup"><span data-stu-id="98dec-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="98dec-113">окне Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="98dec-113">[in] The culture identifier.</span></span> <span data-ttu-id="98dec-114">Чтобы использовать язык и региональные параметры по умолчанию, необходимо указать значение-1.</span><span class="sxs-lookup"><span data-stu-id="98dec-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98dec-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="98dec-115">Return Value</span></span>  

 <span data-ttu-id="98dec-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="98dec-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="98dec-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98dec-117">HRESULT</span></span>|<span data-ttu-id="98dec-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="98dec-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98dec-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="98dec-119">S_OK</span></span>|<span data-ttu-id="98dec-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="98dec-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="98dec-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="98dec-121">E_POINTER</span></span>|<span data-ttu-id="98dec-122">Параметр `pcchBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="98dec-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="98dec-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="98dec-123">E_INVALIDARG</span></span>|<span data-ttu-id="98dec-124">Параметр `pwzBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="98dec-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98dec-125">Требования</span><span class="sxs-lookup"><span data-stu-id="98dec-125">Requirements</span></span>  

 <span data-ttu-id="98dec-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98dec-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98dec-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="98dec-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="98dec-128">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98dec-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98dec-129">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98dec-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dec-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="98dec-130">See also</span></span>

- [<span data-ttu-id="98dec-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="98dec-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="98dec-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="98dec-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="98dec-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="98dec-133">Hosting</span></span>](index.md)
