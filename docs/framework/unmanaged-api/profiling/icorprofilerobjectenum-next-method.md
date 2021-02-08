---
description: 'Дополнительные сведения о методе: ICorProfilerObjectEnum:: Next'
title: Метод ICorProfilerObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: 7f61fa1d4e28043bf5eda95f67dde0d8e87d8c0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781419"
---
# <a name="icorprofilerobjectenumnext-method"></a>Метод ICorProfilerObjectEnum::Next

Возвращает указанное количество смежных объектов из последовательной коллекции объектов, начиная с текущей позиции перечислителя в последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `celt`  
 [in] Количество объектов, которые должны быть получены.  
  
 `objects`  
 заполняет Массив `ObjectID` значений, каждый из которых представляет извлеченный объект.  
  
 `pceltFetched`  
 [out] Указатель на число элементов, фактически извлеченных в массив `objects`.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)
