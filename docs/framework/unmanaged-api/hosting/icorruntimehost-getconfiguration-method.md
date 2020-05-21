---
title: Метод ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 88abdbc62c8b27f48c5629afb99ab6e30ee67e00
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762270"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="94740-102">Метод ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="94740-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="94740-103">Возвращает объект, позволяющий основному приложению указывать конфигурацию обратного вызова среды CLR.</span><span class="sxs-lookup"><span data-stu-id="94740-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94740-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94740-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94740-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94740-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="94740-106">заполняет Указатель на адрес объекта [ICorConfiguration](icorconfiguration-interface.md) , который может использоваться для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="94740-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94740-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="94740-107">Remarks</span></span>  
 <span data-ttu-id="94740-108">Прежде чем инициализировать среду CLR, ее необходимо настроить. в противном случае `GetConfiguration` метод возвращает значение HRESULT, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="94740-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94740-109">Требования</span><span class="sxs-lookup"><span data-stu-id="94740-109">Requirements</span></span>  
 <span data-ttu-id="94740-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94740-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94740-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="94740-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94740-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="94740-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94740-113">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="94740-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94740-114">См. также</span><span class="sxs-lookup"><span data-stu-id="94740-114">See also</span></span>

- [<span data-ttu-id="94740-115">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="94740-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
