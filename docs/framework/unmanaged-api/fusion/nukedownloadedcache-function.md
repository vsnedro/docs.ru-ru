---
title: Функция NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 5ae0a887d666a150b717d495848c8a411d030a09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728580"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="8647c-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="8647c-102">NukeDownloadedCache Function</span></span>

<span data-ttu-id="8647c-103">Удаляет кэш загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="8647c-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8647c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8647c-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8647c-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8647c-105">Return Value</span></span>  

 <span data-ttu-id="8647c-106">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.</span><span class="sxs-lookup"><span data-stu-id="8647c-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8647c-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="8647c-107">Remarks</span></span>  

 <span data-ttu-id="8647c-108">Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="8647c-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8647c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8647c-109">Requirements</span></span>  

 <span data-ttu-id="8647c-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8647c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8647c-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8647c-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8647c-112">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="8647c-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="8647c-113">Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8647c-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="8647c-114">**.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8647c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8647c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8647c-115">See also</span></span>

- [<span data-ttu-id="8647c-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="8647c-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="8647c-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="8647c-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="8647c-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="8647c-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
