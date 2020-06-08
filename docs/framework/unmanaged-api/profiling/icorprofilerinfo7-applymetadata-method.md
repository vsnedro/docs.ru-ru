---
title: 'Метод ICorProfilerInfo7:: ApplyMetaData'
ms.date: 02/15/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo7.ApplyMetaData
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: a1bfb649-4584-4d35-b3e6-8fe59b53992a
ms.openlocfilehash: c30206145d08a22af49c4a6a0dc83fd7382bcc06
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495513"
---
# <a name="icorprofilerinfo7applymetadata-method"></a>Метод ICorProfilerInfo7:: ApplyMetaData
[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]  
  
 Применяет метаданные, которые были недавно определены `IMetadataEmit::Define*` методами, к указанному модулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT ApplyMetaData(  
        [in] ModuleID moduleID  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleID`  
 окне Идентификатор модуля, метаданные которого были изменены.  
  
## <a name="remarks"></a>Примечания  
 Если изменения метаданных вносятся после обратного вызова [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , необходимо вызвать этот метод перед использованием новых метаданных.  
  
 `ApplyMetaData`поддерживает добавление только следующих типов метаданных:  
  
- `AssemblyRef`записи, которые создаются путем вызова метода [IMetaDataAssemblyEmit::D ефинеассемблиреф](../metadata/imetadataassemblyemit-defineassemblyref-method.md). метод.  
  
- `TypeRef`записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетиперефбинаме](../metadata/imetadataemit-definetyperefbyname-method.md) .  
  
- `TypeSpec`записи, которые создаются путем вызова метода [IMetaDataEmit:: жеттокенфромтипеспек](../metadata/imetadataemit-gettokenfromtypespec-method.md) .  
  
- `MemberRef`записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемемберреф](../metadata/imetadataemit-definememberref-method.md) .  
  
- `MemberSpec`записи, которые создаются путем вызова метода [IMetaDataEmit2::D ефинемесодспек](../metadata/imetadataemit2-definemethodspec-method.md) .  
  
- `UserString`записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинеусерстринг](../metadata/imetadataemit-defineuserstring-method.md) .  

Начиная с .NET Core 3,0, `ApplyMetaData` также поддерживает следующие типы:

- `TypeDef`записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинетипедеф](../metadata/imetadataemit-definetypedef-method.md) .

- `MethodDef`записи, которые создаются путем вызова метода [IMetaDataEmit::D ефинемесод](../metadata/imetadataemit-definemethod-method.md) . Однако добавление виртуальных методов в существующий тип не поддерживается. Виртуальные методы должны быть добавлены перед обратным вызовом [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo7](icorprofilerinfo7-interface.md)
