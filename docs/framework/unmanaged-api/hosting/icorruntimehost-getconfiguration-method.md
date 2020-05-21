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
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
