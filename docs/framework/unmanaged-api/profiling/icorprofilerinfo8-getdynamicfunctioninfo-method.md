---
title: 'ICorProfilerInfo8:: Жетдинамикфунктионинфо'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: eaf33f3b0de7a18e400cd16d29c046784e2e190f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495324"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>Метод ICorProfilerInfo8:: Жетдинамикфунктионинфо

Извлекает сведения о динамических методах.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a>Параметры

- `functionId`

  \[in] идентификатор функции, для которой требуется получить сведения.

- `moduleId`

  \[in] указатель на модуль, в котором определен родительский класс функции.

- `ppvSig`

  \[out] указатель на сигнатуру для функции.

- `pbSig`

  \[out] указатель на число байтов для сигнатуры функции.

- `cchName`

  \[in] максимальный размер `wszName` массива.

- `pcchName`

  \[out] число символов в `wszName` массиве.

- `wszName`

  \[out] массив, `WCHAR` представляющий собой имя функции, если она существует.

## <a name="remarks"></a>Примечания

Некоторые методы, такие как заглушки IL или LCG, не имеют связанных метаданных, которые можно извлечь с помощью интерфейсов API [IMetaDataImport](../metadata/imetadataimport-interface.md) и [IMetaDataImport2](../metadata/imetadataimport2-interface.md) . Такие методы могут быть обнаружены профилировщиками с помощью указателей инструкций или путем прослушивания [ICorProfilerCallback8::D инамикмесоджиткомпилатионстартед](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).

Этот API можно использовать для получения сведений о динамических методах, включая понятное имя, если оно доступно.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo8](icorprofilerinfo8-interface.md)
