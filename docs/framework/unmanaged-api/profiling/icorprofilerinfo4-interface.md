---
title: Интерфейс ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: c3e623b0b5f8b49e043fe3a1aa8311558e573573
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682839"
---
# <a name="icorprofilerinfo4-interface"></a>Интерфейс ICorProfilerInfo4

Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах. . `ICorProfilerInfo4`Интерфейс является расширением других `ICorProfilerInfo` интерфейсов. Он предоставляет новые методы для поддержки повторной компиляции JIT, добавленной в .NET Framework 4,5.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)|Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.|  
|[Метод EnumThreads](icorprofilerinfo4-enumthreads-method.md)|Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.|  
|[Метод GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md)|Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.|  
|[Метод GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md)|Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией указанной функции.|  
|[Метод GetILToNativeMapping2](icorprofilerinfo4-getiltonativemapping2-method.md)|Возвращает карту из смещений MSIL к собственным смещениям для кода, содержащегося в JIT-повторно скомпилированной версии указанной функции.|  
|[Метод GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md)|Возвращает размер указанного объекта.|  
|[Метод GetReJITIDs](icorprofilerinfo4-getrejitids-method.md)|Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.|  
|[Метод InitializeCurrentThread](icorprofilerinfo4-initializecurrentthread-method.md)|Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.|  
|[Метод RequestReJIT](icorprofilerinfo4-requestrejit-method.md)|Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.|  
|[Метод RequestRevert](icorprofilerinfo4-requestrevert-method.md)|Восстанавливает исходные версии всех экземпляров указанных функций.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
