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
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720650"
---
# <a name="icorruntimehostgetconfiguration-method"></a>Метод ICorRuntimeHost::GetConfiguration

Возвращает объект, позволяющий основному приложению указывать конфигурацию обратного вызова среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pConfiguration`  
 заполняет Указатель на адрес объекта [ICorConfiguration](icorconfiguration-interface.md) , который может использоваться для настройки среды CLR.  
  
## <a name="remarks"></a>Комментарии  

 Прежде чем инициализировать среду CLR, ее необходимо настроить. в противном случае `GetConfiguration` метод возвращает значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
