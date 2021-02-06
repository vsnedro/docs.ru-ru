---
description: 'Дополнительные сведения о методе: ICLRMetaHost:: Рекуеструнтимелоадеднотификатион'
title: Метод ICLRMetaHost::RequestRuntimeLoadedNotification
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
ms.openlocfilehash: c385d2d845642605ad47944794f6274e8d472071
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637499"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a>Метод ICLRMetaHost::RequestRuntimeLoadedNotification

Предоставляет функцию обратного вызова, которая гарантированно будет вызываться при первой загрузке версии среды CLR, но еще не запущена. Этот метод заменяет функцию [локкклрверсион](lockclrversion-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
## <a name="parameters"></a>Параметры  

 `pCallbackFunction`  
 окне Функция обратного вызова, которая вызывается при загрузке новой среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pCallbackFunction` имеет значение null.|  
  
## <a name="remarks"></a>Remarks  

 Обратный вызов работает следующим образом:  
  
- Обратный вызов вызывается, только если среда выполнения загружается в первый раз.  
  
- Обратный вызов не вызывается для повторных загрузок одной и той же среды выполнения.  
  
- Для невходных загрузок среды выполнения вызовы функции обратного вызова сериализуются.  
  
 Функция обратного вызова имеет следующий прототип:  
  
```cpp  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 Прототипы функций обратного вызова имеют следующий вид:  
  
- `pfnCallbackThreadSet`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
- `pfnCallbackThreadUnset`:  
  
    ```cpp  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 Если узел намеревается загрузить или вызвать повторную загрузку другой среды выполнения, `pfnCallbackThreadSet` `pfnCallbackThreadUnset` Параметры и, предоставленные в функции обратного вызова, должны использоваться следующим образом:  
  
- `pfnCallbackThreadSet` должен вызываться потоком, который может вызвать загрузку среды выполнения до того, как будет предпринята такая нагрузка.  
  
- `pfnCallbackThreadUnset` должен вызываться, когда поток больше не будет вызывать такую нагрузку во время выполнения (и до возврата из начального обратного вызова).  
  
- `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` не являются недопустимыми для повторного входа.  
  
> [!NOTE]
> Ведущие приложения не должны вызывать `pfnCallbackThreadSet` и `pfnCallbackThreadUnset` вне области действия `pCallbackFunction` параметра.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)
- [Размещение](index.md)
