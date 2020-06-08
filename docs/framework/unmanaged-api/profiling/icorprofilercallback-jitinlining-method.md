---
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
ms.openlocfilehash: 13ce44c9c7a04b870278bc8926dd9fe5daf10bc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500017"
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
  
## <a name="remarks"></a>Примечания  
 Профилировщик может задать `pfShouldInline` для значение `false` , чтобы предотвратить `calleeId` вставку функции в `callerId` функцию. Кроме того, профилировщик может глобально отключить встроенную вставку, используя значение COR_PRF_DISABLE_INLINING перечисления [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .  
  
 Встроенные функции не вызывают события для входа или вставки. Таким образом, профилировщик должен установить в значение, чтобы `pfShouldInline` `false` получить точную граф вызовов. Установка `pfShouldInline` значения `false` влияет на производительность, так как встроенная вставка обычно увеличивает скорость и сокращает число отдельных событий JIT-компиляции для метода inserted.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
