---
title: Метод ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: 558b6e4c6ac369e33be3d45b7241e8b11db8bfae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760398"
---
# <a name="icorruntimehostunloaddomain-method"></a>Метод ICorRuntimeHost::UnloadDomain
Выгружает указанный домен приложения из текущего процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 окне Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен для выгрузки.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Операция выполнена успешно.|  
|S_FALSE|Не удалось завершить операцию.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, общеязыковая среда выполнения (CLR) больше не может использоваться в процессе. Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версия .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
