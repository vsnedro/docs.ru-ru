---
title: Функция GetAppIdAuthority
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: 5e731ac1c652b8b4505073a3a10463ae0ce21ac0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724498"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="0e640-102">Функция GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="0e640-102">GetAppIdAuthority Function</span></span>

<span data-ttu-id="0e640-103">Возвращает указатель на экземпляр [иаппидаусорити](iappidauthority-interface.md) , который управляет ключами для удостоверений приложений и ссылок.</span><span class="sxs-lookup"><span data-stu-id="0e640-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e640-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e640-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e640-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e640-105">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="0e640-106">заполняет Возвращаемый `IAppIdAuthority` указатель.</span><span class="sxs-lookup"><span data-stu-id="0e640-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e640-107">Требования</span><span class="sxs-lookup"><span data-stu-id="0e640-107">Requirements</span></span>  

 <span data-ttu-id="0e640-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e640-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e640-109">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="0e640-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0e640-110">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e640-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e640-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e640-111">See also</span></span>

- [<span data-ttu-id="0e640-112">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="0e640-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="0e640-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="0e640-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
