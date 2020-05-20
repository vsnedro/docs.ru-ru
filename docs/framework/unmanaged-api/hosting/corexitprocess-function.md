---
title: Функция CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: a60805e1fd78cb14835957a7afc14fe279cb20fb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616571"
---
# <a name="corexitprocess-function"></a><span data-ttu-id="b200e-102">Функция CorExitProcess</span><span class="sxs-lookup"><span data-stu-id="b200e-102">CorExitProcess Function</span></span>
<span data-ttu-id="b200e-103">Завершает текущий неуправляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="b200e-103">Shuts down the current unmanaged process.</span></span>  
  
 <span data-ttu-id="b200e-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b200e-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="b200e-105">Используйте вместо этого метод [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b200e-105">Use the [ICLRMetaHost::ExitProcess](iclrmetahost-exitprocess-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b200e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b200e-106">Syntax</span></span>  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b200e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b200e-107">Parameters</span></span>  
 `exitCode`  
 <span data-ttu-id="b200e-108">Целое число, указывающее код завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="b200e-108">An integer that specifies the process exit code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b200e-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b200e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b200e-110">Начиная с .NET Framework 4, `CorExitProcess` завершает каждую запущенную среду выполнения в процессе, а не только среду выполнения, к которой привязаны API прежних версий.</span><span class="sxs-lookup"><span data-stu-id="b200e-110">Beginning with the .NET Framework 4, `CorExitProcess` exits every started runtime in the process, not just the runtime to which the legacy APIs have been bound.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b200e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b200e-111">Requirements</span></span>  
 <span data-ttu-id="b200e-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b200e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b200e-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b200e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b200e-114">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b200e-114">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b200e-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b200e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b200e-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b200e-116">See also</span></span>

- [<span data-ttu-id="b200e-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b200e-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
