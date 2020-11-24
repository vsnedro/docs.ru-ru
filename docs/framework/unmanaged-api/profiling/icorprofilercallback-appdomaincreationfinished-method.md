---
title: Метод ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
ms.openlocfilehash: 688b9975cc68463de066e5225c6ab1e04cbb5337
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685385"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a>Метод ICorProfilerCallback::AppDomainCreationFinished

Уведомляет профилировщик о том, что домен приложения создан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a>Параметры

- `appDomainId`

  \[в] определяет домен, который был создан.

- `hrStatus`

  \[в] значение HRESULT, указывающее, успешно ли создана область приложения.

## <a name="remarks"></a>Комментарии  

 Идентификатор приложения не является допустимым для запроса информации до `AppDomainCreationFinished` вызова метода.  
  
 Некоторые части загрузки домена приложения могут продолжаться после `AppDomainCreationFinished` обратного вызова. Ошибка HRESULT в `hrStatus` указывает на сбой. Однако значение HRESULT в случае успеха в `hrStatus` указывает, что первая часть создания домена приложения успешно выполнена.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
