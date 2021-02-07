---
description: 'Дополнительные сведения о методе: Икордебугкодинум:: Next'
title: Метод ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
ms.openlocfilehash: 51d46718891ce3df537c675175eacc4e33b92f79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764779"
---
# <a name="icordebugcodeenumnext-method"></a>Метод ICorDebugCodeEnum::Next

Возвращает указанное число экземпляров ICorDebugCode из перечисления, начиная с текущей позиции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a>Параметры

`celt`  
окне Число `ICorDebugCode` извлекаемых экземпляров.

`values`  
заполняет Массив указателей, каждый из которых указывает на `ICorDebugCode` объект.

`pceltFetched`  
заполняет Указатель на число `ICorDebugCode` фактически возвращенных экземпляров. Это значение может быть равно NULL `celt` , если равно единице.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
