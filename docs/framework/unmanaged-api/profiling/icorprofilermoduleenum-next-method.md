---
title: Метод ICorProfilerModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 7a3ad94a4149d6ebb70e077926771e28d7f82779
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494843"
---
# <a name="icorprofilermoduleenumnext-method"></a>Метод ICorProfilerModuleEnum::Next
Возвращает заданное число смежных модулей из последовательной коллекции модулей начиная с текущей позиции перечислителя в последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
 [in] Количество модулей для извлечения.  
  
 `ids`  
 [out] Массив значений `ModuleID`, каждое из которых представляет полученный модуль.  
  
 `pceltFetched`  
 [out] Указатель на число элементов, фактически извлеченных в массив `ids`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Возвращенные элементы `celt`.|  
|S_FALSE|Было возвращено элементов менее, чем `celt`, что указывает, что перечисление завершено.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
