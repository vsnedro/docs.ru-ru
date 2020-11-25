---
title: Функция GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724442"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="e047a-102">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="e047a-102">GetHistoryFileDirectory Function</span></span>

<span data-ttu-id="e047a-103">Возвращает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="e047a-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e047a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e047a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e047a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e047a-105">Parameters</span></span>  

 `wzDir`  
 <span data-ttu-id="e047a-106">заполняет Буфер для хранения пути к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="e047a-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="e047a-107">[вход, выход] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="e047a-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e047a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e047a-108">Return Value</span></span>  

 <span data-ttu-id="e047a-109">Этот метод возвращает коды стандартных ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="e047a-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="e047a-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="e047a-110">Return code</span></span>|<span data-ttu-id="e047a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e047a-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e047a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e047a-112">S_OK</span></span>|<span data-ttu-id="e047a-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e047a-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="e047a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e047a-114">E_INVALIDARG</span></span>|<span data-ttu-id="e047a-115">`wzDir` или `pdwSize` имеет значение null, или строка версии неверна.</span><span class="sxs-lookup"><span data-stu-id="e047a-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e047a-116">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e047a-116">Remarks</span></span>  

 <span data-ttu-id="e047a-117">При успешном завершении `pdwSize` аргументу присваивается длина строки пути.</span><span class="sxs-lookup"><span data-stu-id="e047a-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e047a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e047a-118">Requirements</span></span>  

 <span data-ttu-id="e047a-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e047a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e047a-120">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e047a-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e047a-121">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="e047a-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="e047a-122">Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e047a-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e047a-123">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e047a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e047a-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e047a-124">See also</span></span>

- [<span data-ttu-id="e047a-125">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="e047a-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="e047a-126">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="e047a-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="e047a-127">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="e047a-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
