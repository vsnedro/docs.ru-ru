---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 6822757608429ca5f4ef9520ab7574d440b67b26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495260"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>Метод ICorProfilerInfo8:: GetFunctionFromIP3

Сопоставляет указатель инструкции управляемого кода с FunctionID. Этот метод работает как с динамическими, так и с нединамическими методами.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

## <a name="parameters"></a>Параметры

- `ip`

  \[in] указатель инструкций в управляемом коде.

- `pFunctionId`

  \[out] идентификатор функции.

- `pReJitId`

  \[out] удостоверение JIT-повторно скомпилированной версии функции.

## <a name="remarks"></a>Примечания

Этот метод работает как с динамическими, так и с нединамическими методами. Это надмножество [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), который работает только для функций с метаданными.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorProf.idl, CorProf.h

**Библиотека:** CorGuids.lib

**.NET Framework версии:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo8](icorprofilerinfo8-interface.md)
