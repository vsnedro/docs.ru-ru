---
title: Указатель функции LPTHREAD_START_ROUTINE
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
ms.openlocfilehash: 84cdb42b11ad70f54f21ae36ca2734dc794d06d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008473"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="f0f35-102">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="f0f35-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="f0f35-103">Указывает на функцию, которая уведомляет узел о начале выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="f0f35-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="f0f35-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f0f35-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f35-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0f35-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f35-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0f35-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="f0f35-107">окне Указатель на код, который начал выполнять.</span><span class="sxs-lookup"><span data-stu-id="f0f35-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f35-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0f35-108">Remarks</span></span>  
 <span data-ttu-id="f0f35-109">Функция, к которой `LPTHREAD_START_ROUTINE` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="f0f35-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f35-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f0f35-110">Requirements</span></span>  
 <span data-ttu-id="f0f35-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0f35-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f35-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0f35-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0f35-113">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="f0f35-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f0f35-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f35-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f35-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f0f35-115">See also</span></span>

- [<span data-ttu-id="f0f35-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f0f35-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
