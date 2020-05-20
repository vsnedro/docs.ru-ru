---
title: Функция CoEEShutDownCOM
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 3eb8bffee9d30a89c39a900e600ebf171456b9f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616793"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="8f35a-102">Функция CoEEShutDownCOM</span><span class="sxs-lookup"><span data-stu-id="8f35a-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="8f35a-103">Заставляет общеязыковую среду выполнения (CLR) освобождать все указатели интерфейсов, содержащиеся внутри вызываемых оболочек времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="8f35a-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="8f35a-104">Это приведет к освобождению всех кэшей RCW.</span><span class="sxs-lookup"><span data-stu-id="8f35a-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="8f35a-105">Эта глобальная функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8f35a-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="8f35a-106">Вместо этого используйте точку входа для конкретной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="8f35a-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f35a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f35a-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8f35a-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f35a-108">Remarks</span></span>  
 <span data-ttu-id="8f35a-109">`CoEEShutDownCOM`Функция сначала освобождает все вызываемые оболочки RCW во всех контекстах и во всех кэшах, а затем удаляет все уведомления о разрыве, существующие в программе установки.</span><span class="sxs-lookup"><span data-stu-id="8f35a-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="8f35a-110">Выгрузка библиотек DLL не выполняется.</span><span class="sxs-lookup"><span data-stu-id="8f35a-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="8f35a-111">Эта функция влияет на все среды выполнения, загруженные в процесс.</span><span class="sxs-lookup"><span data-stu-id="8f35a-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="8f35a-112">Начиная с .NET Framework 4, вызовите точку входа для этой функции в конкретной среде выполнения, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="8f35a-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="8f35a-113">Чтобы получить точку входа, вызовите метод [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) и укажите "коишутдовнком".</span><span class="sxs-lookup"><span data-stu-id="8f35a-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f35a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8f35a-114">Requirements</span></span>  
 <span data-ttu-id="8f35a-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f35a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f35a-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="8f35a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f35a-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8f35a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f35a-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f35a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f35a-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="8f35a-119">See also</span></span>

- [<span data-ttu-id="8f35a-120">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="8f35a-120">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
