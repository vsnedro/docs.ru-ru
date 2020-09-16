---
title: 'ICorProfilerInfo10:: Исфрозенобжект'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3755260b885768de6b5b2d6342c0ad590a95caff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548674"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a>Метод ICorProfilerInfo10:: Исфрозенобжект

Определяет, находится ли объект в сегменте, доступном только для чтения.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a>Параметры

- `objectId`

  \[в] объект для проверки.

- `pbFrozen`

  \[out] значение `BOOL` , указывающее, находится ли объект в сегменте, доступном только для чтения.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
