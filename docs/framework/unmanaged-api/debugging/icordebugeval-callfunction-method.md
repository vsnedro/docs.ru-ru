---
title: Метод ICorDebugEval::CallFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 1cf0080945ad78565fae3fedb454ceba7825cb4a
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976243"
---
# <a name="icordebugevalcallfunction-method"></a>Метод ICorDebugEval::CallFunction

Настраивает вызов указанной функции.

Этот метод является устаревшим в .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: каллпараметеризедфунктион](icordebugeval2-callparameterizedfunction-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Параметры

`pFunction`\
окне Указатель на объект ICorDebugFunction, указывающий вызываемую функцию.

`nArgs`\
окне Число аргументов для функции.

`ppArgs`\
окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, указывающий аргумент, передаваемый в функцию.

## <a name="remarks"></a>Remarks

Если функция является виртуальной, `CallFunction` выполняет виртуальную диспетчеризацию. Если функция находится в другом домене приложения, произойдет переход, если все аргументы также находятся в этом домене приложения.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**.NET Framework версии:** 1,1, 1,0

## <a name="see-also"></a>См. также раздел

- [Метод CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)
