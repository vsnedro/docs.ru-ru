---
description: 'Дополнительные сведения о методе: ICorDebugEval:: CallFunction'
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
ms.openlocfilehash: c0978ab3bdffc83e3eb5e3a6553e7f374ab6d5da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694192"
---
# <a name="icordebugevalcallfunction-method"></a>Метод ICorDebugEval::CallFunction

Настраивает вызов указанной функции.

Этот метод является устаревшим в платформа .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: каллпараметеризедфунктион](icordebugeval2-callparameterizedfunction-method.md) .

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

Если функция является виртуальной, выполняет `CallFunction` виртуальную диспетчеризацию. Если функция находится в другом домене приложения, произойдет переход, если все аргументы также находятся в этом домене приложения.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:** 1,1, 1,0

## <a name="see-also"></a>См. также

- [Метод CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)
