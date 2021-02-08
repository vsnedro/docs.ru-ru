---
description: 'Дополнительные сведения о методе: ICorProfilerInfo2:: Жетфунктионфромтокенандтипеаргс'
title: Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 4b4bb8631a5f33c939666af68226b19d2e4d666d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799041"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>Метод ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs

Возвращает объект `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleID`  
 окне Идентификатор модуля, в котором находится функция.  
  
 `funcDef`  
 окне `mdMethodDef` Токен метаданных, ссылающийся на функцию.  
  
 `classId`  
 окне Идентификатор содержащего класса функции.  
  
 `cTypeArgs`  
 окне Число параметров типа для данной функции. Для неуниверсальных функций это значение должно быть равно нулю.  
  
 `typeArgs`  
 окне Массив `ClassID` значений, каждый из которых является аргументом функции. Значение `typeArgs` может быть равно null, если `cTypeArgs` имеет значение 0.  
  
 `pFunctionID`  
 заполняет Указатель на объект `FunctionID` указанной функции.  
  
## <a name="remarks"></a>Remarks  

 Вызов `GetFunctionFromTokenAndTypeArgs` метода с `mdMethodRef` метаданными вместо `mdMethodDef` токена метаданных может иметь непредсказуемые результаты. Вызывающие объекты должны разрешить объект `mdMethodRef` в `mdMethodDef` при передаче.  
  
 Если функция еще не загружена, вызов `GetFunctionFromTokenAndTypeArgs` приведет к возникновению загрузки, что является опасной операцией во многих контекстах. Например, вызов этого метода во время загрузки модулей или типов может привести к бесконечному циклу, так как среда выполнения пытается циклически загружать вещи.  
  
 Как правило, использование параметра `GetFunctionFromTokenAndTypeArgs` не рекомендуется. Если профилировщики заинтересованы в событиях для определенной функции, они должны хранить и для `ModuleID` `mdMethodDef` этой функции, а также использовать [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) для проверки того, является ли заданная `FunctionID` функция требуемой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
