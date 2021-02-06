---
description: 'Дополнительные сведения о методе: ICorProfilerInfo9:: Жетнативекодестартаддрессес'
title: 'ICorProfilerInfo9:: Жетнативекодестартаддрессес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 1ca686cef4a45ebb9e05190fa790ed5300c0d816
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646495"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>Метод ICorProfilerInfo9:: Жетнативекодестартаддрессес

При наличии кода functionId и Режитид перечисляются начальные адреса всех откомпилированных версий этого кода, которые в настоящее время существуют.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```

## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор функции, для которой должны возвращаться начальные адреса машинного кода.

- `reJitId`

  \[in] Идентификация JIT-повторно скомпилированной функции.

- `cCodeStartAddresses`

  \[in] максимальный размер `codeStartAddresses` массива.

- `pcCodeStartAddresses`

  \[out] количество доступных адресов.

- `codeStartAddresses`

  \[out] массив `UINT_PTR` , каждый из которых является начальным адресом для собственного тела для указанной функции.

## <a name="remarks"></a>Remarks

Если включена многоуровневая компиляция, функция может иметь более одного тела машинного кода.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo9](icorprofilerinfo9-interface.md)
