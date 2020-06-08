---
title: Функция StackSnapshotCallback
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: a0f5316900dedc6c8983f9e670f60767ed783a40
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493998"
---
# <a name="stacksnapshotcallback-function"></a>Функция StackSnapshotCallback
Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcId`  
 окне Если это значение равно нулю, этот обратный вызов предназначен для запуска неуправляемых кадров; в противном случае это идентификатор управляемой функции, и этот обратный вызов предназначен для управляемого фрейма.  
  
 `ip`  
 окне Значение указателя инструкций машинного кода в кадре.  
  
 `frameInfo`  
 окне `COR_PRF_FRAME_INFO`Значение, которое ссылается на сведения о кадре стека. Это значение допустимо для использования только во время этого обратного вызова.  
  
 `contextSize`  
 окне Размер `CONTEXT` структуры, на которую ссылается `context` параметр.  
  
 `context`  
 окне Указатель на `CONTEXT` структуру Win32, которая представляет состояние ЦП для данного кадра.  
  
 `context`Параметр допустим только в том случае, если был передан флаг COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot` .  
  
 `clientData`  
 окне Указатель на данные клиента, которые передаются непосредственно через `ICorProfilerInfo2::DoStackSnapshot` .  
  
## <a name="remarks"></a>Примечания  
 `StackSnapshotCallback`Функция реализуется модулем записи профилировщика. Необходимо ограничить сложность работы, выполненной в `StackSnapshotCallback` . Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме целевой поток может удерживать блокировки. Если код внутри `StackSnapshotCallback` требует одних и тех же блокировок, может возникнуть взаимоблокировка.  
  
 `ICorProfilerInfo2::DoStackSnapshot`Метод вызывает `StackSnapshotCallback` функцию один раз для каждого управляемого кадра или один раз для каждого запуска неуправляемых кадров. Если `StackSnapshotCallback` вызывается для запуска неуправляемых кадров, профилировщик может использовать контекст Register (на который ссылается `context` параметр) для выполнения собственного анализа неуправляемого стека. В этом случае `CONTEXT` Структура Win32 представляет состояние ЦП для последнего отправленного кадра в рамках выполнения неуправляемых кадров. Несмотря на то `CONTEXT` , что структура Win32 включает значения для всех регистров, следует полагаться только на значения регистра указателя стека, регистра указателя кадра, регистра указателя инструкций и неизменяемых (то есть сохраненных) целочисленных регистров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Глобальные статические функции профилирования](profiling-global-static-functions.md)
