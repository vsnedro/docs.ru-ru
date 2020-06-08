---
title: Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type:
- apiref
ms.openlocfilehash: 702c5f9f2bc08c824bdc0607741a6afd65a3e89b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497261"
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
Возвращает объект `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любых аргументов типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, в котором находится тип.  
  
 `typeDef`  
 окне `mdTypeDef`Токен метаданных, ссылающийся на тип.  
  
 `cTypeArgs`  
 окне Число параметров типа для данного типа. Для типов, не являющихся универсальными, это значение должно быть равно нулю.  
  
 `typeArgs`  
 окне Массив `ClassID` значений, каждый из которых является аргументом типа. Значение `typeArgs` может быть равно null, если `cTypeArgs` имеет значение 0.  
  
 `pClassID`  
 заполняет Указатель на объект `ClassID` указанного типа.  
  
## <a name="remarks"></a>Примечания  
 Вызов `GetClassFromTokenAndTypeArgs` метода с помощью `mdTypeRef` вместо `mdTypeDef` токена метаданных может иметь непредсказуемые результаты; вызывающие объекты должны разрешить объект `mdTypeRef` в `mdTypeDef` при передаче.  
  
 Если тип еще не загружен, вызов инициирует `GetClassFromTokenAndTypeArgs` загрузку, что является опасной операцией во многих контекстах. Например, вызов этого метода во время загрузки модулей или других типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.  
  
 Как правило, использование параметра `GetClassFromTokenAndTypeArgs` не рекомендуется. Если профилировщики заинтересованы в событиях для определенного типа, они должны хранить и для `ModuleID` `mdTypeDef` этого типа, а также использовать [ICorProfilerInfo2:: GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md) для проверки того `ClassID` , относится ли данный тип к требуемому типу.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
