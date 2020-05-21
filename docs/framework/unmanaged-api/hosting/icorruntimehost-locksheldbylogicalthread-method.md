---
title: Метод ICorRuntimeHost::LocksHeldByLogicalThread
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 265ab5ae03b7b42c4f5f429df5d659d60e55f18e
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760723"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="42a7b-102">Метод ICorRuntimeHost::LocksHeldByLogicalThread</span><span class="sxs-lookup"><span data-stu-id="42a7b-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="42a7b-103">Возвращает число блокировок, удерживаемых текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="42a7b-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="42a7b-104">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="42a7b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a7b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42a7b-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a7b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="42a7b-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="42a7b-107">заполняет Указатель на число блокировок, удерживаемых текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="42a7b-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a7b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="42a7b-108">Requirements</span></span>  
 <span data-ttu-id="42a7b-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a7b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a7b-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42a7b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42a7b-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="42a7b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42a7b-112">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="42a7b-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a7b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="42a7b-113">See also</span></span>

- [<span data-ttu-id="42a7b-114">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="42a7b-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
