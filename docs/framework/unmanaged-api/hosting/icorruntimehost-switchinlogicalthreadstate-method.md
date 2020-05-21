---
title: Метод ICorRuntimeHost::SwitchInLogicalThreadState
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: d830635b911fa5d80382e432f283c455c41af7a8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762686"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="71a79-102">Метод ICorRuntimeHost::SwitchInLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="71a79-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="71a79-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="71a79-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71a79-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71a79-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71a79-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="71a79-106">окне Файл cookie, указывающий используемое волокно.</span><span class="sxs-lookup"><span data-stu-id="71a79-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71a79-107">Требования</span><span class="sxs-lookup"><span data-stu-id="71a79-107">Requirements</span></span>  
 <span data-ttu-id="71a79-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a79-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a79-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71a79-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71a79-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71a79-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71a79-111">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="71a79-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a79-112">См. также</span><span class="sxs-lookup"><span data-stu-id="71a79-112">See also</span></span>

- [<span data-ttu-id="71a79-113">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="71a79-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
