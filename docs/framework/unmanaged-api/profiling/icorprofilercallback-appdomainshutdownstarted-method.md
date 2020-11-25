---
title: Метод ICorProfilerCallback::AppDomainShutdownStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: cb0b763059c787b8f3e93e6c46b0e7fb2f8f8b2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718466"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a>Метод ICorProfilerCallback::AppDomainShutdownStarted

Уведомляет профилировщик о том, что домен приложения выгружается из процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a>Параметры

- `appDomainId`

  \[в] определяет домен, в котором хранятся сборки приложения.

## <a name="remarks"></a>Комментарии  

 Значение недопустимо `appDomainId` для любого запроса информации после `AppDomainShutdownStarted` возврата метода — это последний шанс профилировщика получить сведения об этом домене приложения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
