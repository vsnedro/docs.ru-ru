---
description: 'Дополнительные сведения о методе: метод icorprofilerinfo4:: Инитиализекуррентсреад'
title: Метод ICorProfilerInfo4::InitializeCurrentThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: a78816c736507a4a59da3ea1c75b078b54c34125
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781408"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a>Метод ICorProfilerInfo4::InitializeCurrentThread

Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a>Remarks  

 Рекомендуется вызывать `InitializeCurrentThread` в любом потоке, который будет вызывать API профилировщика при наличии приостановленных потоков. Этот метод обычно используется выборочными профилировщиками, которые создают собственный поток для вызова метода [ICorProfilerInfo2::D остаккснапшот](icorprofilerinfo2-dostacksnapshot-method.md) для выполнения проверки стека, пока целевой поток приостанавливается. Вызывая `InitializeCurrentThread` один раз, когда профилировщик сначала создает поток выборки, профилировщики могут гарантировать, что отложенная инициализация для каждого потока, которая в противном случае будет выполняться средой CLR во время первого вызова, `DoStackSnapshot` теперь может быть безопасно, когда никакие другие потоки не будут приостановлены.  
  
> [!NOTE]
> `InitializeCurrentThread` Выполняет инициализацию заранее для завершения задач, которые принимают блокировки и могут быть взаимоблокировками. Вызывайте `InitializeCurrentThread` , только если нет приостановленных потоков.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
