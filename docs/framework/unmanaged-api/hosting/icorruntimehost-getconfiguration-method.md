---
description: 'Дополнительные сведения о методе: ICorRuntimeHost:: метода конфигурации'
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
ms.openlocfilehash: d3e3f065c3957fb29daa11ed7c46858a53865c91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784838"
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
  
## <a name="remarks"></a>Remarks  

 Прежде чем инициализировать среду CLR, ее необходимо настроить. в противном случае `GetConfiguration` метод возвращает значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
