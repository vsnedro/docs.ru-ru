---
title: Указатель функции WAITORTIMERCALLBACK
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
ms.openlocfilehash: ee5dd611888ec52e360ef45fab4c01e9c5b2d6bb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009457"
---
# <a name="waitortimercallback-function-pointer"></a><span data-ttu-id="b1e08-102">Указатель функции WAITORTIMERCALLBACK</span><span class="sxs-lookup"><span data-stu-id="b1e08-102">WAITORTIMERCALLBACK Function Pointer</span></span>
<span data-ttu-id="b1e08-103">Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания ( <xref:System.Threading.WaitHandle> ) либо получил сигнал, либо превысил время ожидания.</span><span class="sxs-lookup"><span data-stu-id="b1e08-103">Points to a function that notifies the host that a wait handle (<xref:System.Threading.WaitHandle>) has either been signaled or timed out.</span></span>  
  
 <span data-ttu-id="b1e08-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b1e08-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e08-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1e08-105">Syntax</span></span>  
  
```cpp  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1e08-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1e08-106">Parameters</span></span>  
 `lpParameter`  
 <span data-ttu-id="b1e08-107">окне Указатель на объект, содержащий сведения, определенные узлом.</span><span class="sxs-lookup"><span data-stu-id="b1e08-107">[in] A pointer to an object that contains information defined by the host.</span></span>  
  
 `TimerOrWaitFired`  
 <span data-ttu-id="b1e08-108">[входные] `true` значение, если истекло время ожидания дескриптора ожидания или `false` он был сигнальным.</span><span class="sxs-lookup"><span data-stu-id="b1e08-108">[in] `true` if the wait handle timed out, or `false` if it was signaled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1e08-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1e08-109">Remarks</span></span>  
 <span data-ttu-id="b1e08-110">Функция, к которой `WAITORTIMERCALLBACK` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="b1e08-110">The function to which `WAITORTIMERCALLBACK` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1e08-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b1e08-111">Requirements</span></span>  
 <span data-ttu-id="b1e08-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1e08-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e08-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b1e08-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1e08-114">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="b1e08-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="b1e08-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e08-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b1e08-116">See also</span></span>

- [<span data-ttu-id="b1e08-117">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b1e08-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
