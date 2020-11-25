---
title: Указатель функции FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
ms.openlocfilehash: 8b9c6bb41b7438b9764ac2a8a7fc1677bc08557a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733689"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="e246f-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="e246f-102">FExecuteInAppDomainCallback Function Pointer</span></span>

<span data-ttu-id="e246f-103">Указывает на функцию, которая вызывается средой CLR для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e246f-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="e246f-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e246f-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e246f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e246f-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e246f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e246f-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="e246f-107">окне Указатель на непрозрачную память, выделенную вызывающим объектом, содержащую управляемый код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="e246f-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="e246f-108">Выделение и время существования этой памяти управляются вызывающим объектом (то есть средой CLR).</span><span class="sxs-lookup"><span data-stu-id="e246f-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="e246f-109">Это не управляемая средой CLR память в куче.</span><span class="sxs-lookup"><span data-stu-id="e246f-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e246f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e246f-110">Requirements</span></span>  

 <span data-ttu-id="e246f-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e246f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e246f-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e246f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e246f-113">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e246f-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e246f-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e246f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e246f-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e246f-115">See also</span></span>

- [<span data-ttu-id="e246f-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e246f-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
