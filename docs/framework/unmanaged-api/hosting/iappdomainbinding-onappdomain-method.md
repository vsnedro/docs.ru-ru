---
description: 'Дополнительные сведения о методе: Иаппдомаинбиндинг:: onappdomain'
title: Метод IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: de7f37152261a6fe829026607cf135f3ea0b4a84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760606"
---
# <a name="iappdomainbindingonappdomain-method"></a>Метод IAppDomainBinding::OnAppDomain

Вызывается средой CLR для уведомления узла о создании домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppdomain`  
 окне Указатель на объект интерфейса [IUnknown](/cpp/atl/iunknown) , представляющий новый домен приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAppDomainBinding](iappdomainbinding-interface.md)
