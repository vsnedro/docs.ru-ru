---
title: 'ICorProfilerInfo10:: Енумератеобжектреференцес'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: a276ecfe65ed9752f39ed68a36e8e17a24255508
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558320"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a>Метод ICorProfilerInfo10:: Енумератеобжектреференцес

При наличии ObjectID, callback и Клиентдата перечисляет ссылки на все объекты (если таковые имеются).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a>Параметры

- `objectId`

  \[в] объект для перечисления ссылок.

- `callback`

  \[in] функция, которая будет вызываться со ссылками на объект.

- `clientData`

  \[in] данные, предоставленные профилировщиком, передаются в `callback` функцию.

## <a name="remarks"></a>Примечания

`EnumerateObjectReferences`Метод аналогичен [ObjectReferences](icorprofilercallback-objectreferences-method.md), за исключением того, что он просматривает ссылки по запросу для профилировщика вместо предварительного выделения массива для хранения ссылок.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo10](icorprofilerinfo10-interface.md)
