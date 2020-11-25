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
ms.openlocfilehash: c86b65e136869603f93253678108b2ffa9d388e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730075"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="12084-102">Указатель функции LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="12084-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="12084-103">Указывает на функцию, которая уведомляет узел о начале выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="12084-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="12084-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="12084-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12084-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12084-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12084-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="12084-106">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="12084-107">окне Указатель на код, который начал выполнять.</span><span class="sxs-lookup"><span data-stu-id="12084-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12084-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="12084-108">Remarks</span></span>  

 <span data-ttu-id="12084-109">Функция, к которой `LPTHREAD_START_ROUTINE` points является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="12084-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12084-110">Требования</span><span class="sxs-lookup"><span data-stu-id="12084-110">Requirements</span></span>  

 <span data-ttu-id="12084-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12084-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12084-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="12084-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12084-113">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="12084-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="12084-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12084-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12084-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12084-115">See also</span></span>

- [<span data-ttu-id="12084-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="12084-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
