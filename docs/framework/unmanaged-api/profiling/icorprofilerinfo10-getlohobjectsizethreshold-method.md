---
title: 'ICorProfilerInfo10:: Жетлохобжектсизесрешолд'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 280f0a401f87f81e1ef9d4a2c85c06599442b5ec
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543950"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a>Метод ICorProfilerInfo10:: Жетлохобжектсизесрешолд

Возвращает значение заданного порога кучи больших объектов (LOH).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

## <a name="parameters"></a>Параметры

- `pThreshold`

  \[out] пороговое значение кучи больших объектов в байтах.

## <a name="remarks"></a>Примечания

Объекты, превышающие пороговое значение кучи больших объектов, будут выделены в куче больших объектов. Начиная с .NET Core 3,0, порог кучи больших объектов можно настроить, он `pThreshold` будет содержать пороговое значение активной кучи больших объектов в байтах.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
