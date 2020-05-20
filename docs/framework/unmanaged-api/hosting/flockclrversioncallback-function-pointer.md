---
title: Указатель функции FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: af42de820b2d835e8ea137a2643a51678e382ff0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617286"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="d265e-102">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="d265e-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="d265e-103">Указывает на функцию, которая вызывается средой CLR для указания того, что инициализация запущена или завершена.</span><span class="sxs-lookup"><span data-stu-id="d265e-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="d265e-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d265e-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d265e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d265e-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="d265e-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="d265e-106">Remarks</span></span>  
 <span data-ttu-id="d265e-107">Эта функция реализуется узлом.</span><span class="sxs-lookup"><span data-stu-id="d265e-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d265e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="d265e-108">Requirements</span></span>  
 <span data-ttu-id="d265e-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d265e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d265e-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d265e-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d265e-111">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="d265e-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d265e-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d265e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d265e-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d265e-113">See also</span></span>

- [<span data-ttu-id="d265e-114">Функция LockClrVersion</span><span class="sxs-lookup"><span data-stu-id="d265e-114">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="d265e-115">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d265e-115">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
