---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Житинлининг'
title: Метод ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
ms.openlocfilehash: 2bd6c48180b9484ef90b6afb505c8171aff57aa4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705646"
---
# <a name="icorprofilercallbackjitinlining-method"></a>Метод ICorProfilerCallback::JITInlining

Уведомляет профилировщик о том, что JIT-компилятор собирается вставить функцию в строку с другой функцией.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Параметры  

 `callerId`  
 окне Идентификатор функции, в которую `calleeId` будет вставлена функция.  
  
 `calleeId`  
 окне Идентификатор вставляемой функции.  
  
 `pfShouldInline`  
 [out] `true` значение, чтобы разрешить вставку; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 Профилировщик может задать `pfShouldInline` для значение `false` , чтобы предотвратить `calleeId` вставку функции в `callerId` функцию. Кроме того, профилировщик может глобально отключить встроенную вставку, используя значение COR_PRF_DISABLE_INLINING перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 Встроенные функции не вызывают события для входа или вставки. Таким образом, профилировщик должен установить в значение, чтобы `pfShouldInline` `false` получить точную граф вызовов. Установка `pfShouldInline` значения `false` влияет на производительность, так как встроенная вставка обычно увеличивает скорость и сокращает число отдельных событий JIT-компиляции для метода inserted.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
