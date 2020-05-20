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
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616157"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="3bffe-102">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="3bffe-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="3bffe-103">Указывает на функцию, которая вызывается средой CLR для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="3bffe-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="3bffe-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3bffe-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bffe-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bffe-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bffe-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bffe-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="3bffe-107">окне Указатель на непрозрачную память, выделенную вызывающим объектом, содержащую управляемый код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3bffe-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="3bffe-108">Выделение и время существования этой памяти управляются вызывающим объектом (то есть средой CLR).</span><span class="sxs-lookup"><span data-stu-id="3bffe-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="3bffe-109">Это не управляемая средой CLR память в куче.</span><span class="sxs-lookup"><span data-stu-id="3bffe-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bffe-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3bffe-110">Requirements</span></span>  
 <span data-ttu-id="3bffe-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bffe-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bffe-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3bffe-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bffe-113">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="3bffe-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="3bffe-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bffe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bffe-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3bffe-115">See also</span></span>

- [<span data-ttu-id="3bffe-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3bffe-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
