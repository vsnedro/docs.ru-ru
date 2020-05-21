---
title: Метод ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
ms.openlocfilehash: 8b6593ad995872f0e0014b1e8bcd8a4b576bbeaf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762436"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="ce37d-102">Метод ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="ce37d-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="ce37d-103">Указывает службам отладки, что определенному потоку должен быть разрешено продолжать выполнение, пока отладчик не остановит работу приложения во время управляемых или неуправляемых сценариев отладки.</span><span class="sxs-lookup"><span data-stu-id="ce37d-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce37d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce37d-104">Syntax</span></span>  
  
```cpp  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce37d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce37d-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="ce37d-106">окне Идентификатор потока, который должен быть разрешен для продолжения выполнения.</span><span class="sxs-lookup"><span data-stu-id="ce37d-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce37d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="ce37d-107">Remarks</span></span>  
 <span data-ttu-id="ce37d-108">Указанный поток не может выполнять управляемый код или вводить среду выполнения каким бы то ни было образом.</span><span class="sxs-lookup"><span data-stu-id="ce37d-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="ce37d-109">Примером такого потока может быть внутрипроцессный поток для поддержки устаревших отладчиков скриптов.</span><span class="sxs-lookup"><span data-stu-id="ce37d-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce37d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ce37d-110">Requirements</span></span>  
 <span data-ttu-id="ce37d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce37d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce37d-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ce37d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce37d-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ce37d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce37d-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce37d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce37d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ce37d-115">See also</span></span>

- [<span data-ttu-id="ce37d-116">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ce37d-116">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
