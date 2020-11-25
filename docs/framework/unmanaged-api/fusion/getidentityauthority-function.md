---
title: Функция GetIdentityAuthority
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
ms.openlocfilehash: e9631211993afbfe968c7122828251746f15c3f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732134"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="f041b-102">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="f041b-102">GetIdentityAuthority Function</span></span>

<span data-ttu-id="f041b-103">Возвращает указатель на экземпляр [IIdentityAuthority](iidentityauthority-interface.md) , который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="f041b-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f041b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f041b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f041b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f041b-105">Parameters</span></span>  

 `ppIIdentityAuthority`  
 <span data-ttu-id="f041b-106">заполняет Возвращаемый `IIdentityAuthority` указатель.</span><span class="sxs-lookup"><span data-stu-id="f041b-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f041b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f041b-107">Requirements</span></span>  

 <span data-ttu-id="f041b-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f041b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f041b-109">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="f041b-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f041b-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f041b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f041b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f041b-111">See also</span></span>

- [<span data-ttu-id="f041b-112">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="f041b-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="f041b-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="f041b-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
