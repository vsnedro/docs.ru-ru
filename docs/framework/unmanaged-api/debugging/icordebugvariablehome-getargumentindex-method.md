---
description: 'Дополнительные сведения о методе: ICorDebugVariableHome:: Жетаргументиндекс'
title: 'Метод ICorDebugVariableHome:: Жетаргументиндекс'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 827ef55d3e3509cbfbfc8213ef5b53fbe2e2220e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690045"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Метод ICorDebugVariableHome:: Жетаргументиндекс

Возвращает индекс аргумента функции.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Параметры

`pArgumentIndex`\
заполняет Указатель на индекс аргумента.

## <a name="return-value"></a>Возвращаемое значение

Метод возвращает следующие значения.

|Значение|Описание|
|-----------|-----------------|
|`S_OK`|Вызов метода вернул допустимый индекс аргумента.|
|`E_FAIL`|Текущий экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) представляет локальную переменную.|

## <a name="remarks"></a>Remarks

Индекс аргумента можно использовать для получения метаданных для этого аргумента.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
