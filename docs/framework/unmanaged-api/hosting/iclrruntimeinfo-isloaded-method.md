---
title: Метод ICLRRuntimeInfo::IsLoaded
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 3275a69683a312340f35841815685066def10b23
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762530"
---
# <a name="iclrruntimeinfoisloaded-method"></a>Метод ICLRRuntimeInfo::IsLoaded
Указывает, загружается ли в процесс общеязыковая среда выполнения (CLR), связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) . Среду выполнения можно загрузить без запуска.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a>Параметры  
 `hndProcess`  
 окне Обработчик процесса.  
  
 `pbLoaded`  
 [out] `true` значение, если среда CLR загружена в процесс; в противном случае — `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pbLoaded` имеет значение NULL.|  
  
## <a name="remarks"></a>Комментарии  
 Этот метод обеспечивает обратную совместимость со следующими функциями и интерфейсами:  
  
- Интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) (в API размещения .NET Framework версии 1).  
  
- Интерфейс [ICLRRuntimeHost](iclrruntimehost-interface.md) (в API размещения .NET Framework 2,0).  
  
- Устаревшие `CorBindTo*` функции (см. раздел [нерекомендуемые функции размещения CLR](deprecated-clr-hosting-functions.md) в API размещения .NET Framework 2,0).  
  
 Узел может вызвать одну из устаревших `CorBindTo*` функций, например функцию [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) , для создания экземпляра конкретной версии среды CLR. Затем узел может вызвать метод [ICLRMetaHost::-Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) и указать тот же номер версии для получения интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Если узел затем вызывает `IsLoaded` метод для возвращенного интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , `pbLoaded` возвращает `true` ; в противном случае возвращается значение `false` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)
