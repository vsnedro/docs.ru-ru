---
title: 'ICorProfilerInfo10:: Рекуестрежитвисинлинерс'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e3d5a09730cb8e477bd506749017a403acff1696
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540571"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>Метод ICorProfilerInfo10:: Рекуестрежитвисинлинерс

Режитс запрошенные методы, а также любые запрашиваются методы.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

## <a name="parameters"></a>Параметры

- `dwRejitFlags`

  \[in] битовая маска [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[в] число функций для повторной компиляции.

- `moduleIds`

  \[в] задает `moduleId` часть `module` пар (, `methodDef` ), определяющих функции для повторной компиляции.

- `methodIds`

  \[в] задает `methodId` часть `module` пар (, `methodDef` ), определяющих функции для повторной компиляции.

## <a name="remarks"></a>Примечания

[Рекуестрежит](icorprofilerinfo4-requestrejit-method.md) не выполняет отслеживание встроенных методов. Профилировщик ожидал блокировать встраивание или отслеживание встраивания, а также вызов `RequestReJIT` всех строк, чтобы гарантировать, что каждый экземпляр встроенного метода был режиттед. Это создает проблему с ReJIT при присоединении, так как профилировщик отсутствует для мониторинга встраивания. Этот метод может быть вызван, чтобы гарантировать, что полный набор Режиттед также будет недоступен.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
