---
description: 'Дополнительные сведения о методе: ICorDebugCode2:: Жеткодечункс'
title: Метод ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
ms.openlocfilehash: 371d077466ff2390293d9d4e320d4c95a992fe54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764974"
---
# <a name="icordebugcode2getcodechunks-method"></a>Метод ICorDebugCode2::GetCodeChunks

Возвращает фрагменты кода, из которого состоит этот объект кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a>Параметры

`cbufSize`  
окне Размер `chunks` массива.

`pcnumChunks`  
заполняет Количество блоков, возвращаемых в `chunks` массиве.

`chunks`  
заполняет Массив структур "Кодечункинфо", каждый из которых представляет отдельный фрагмент кода. Если значение `cbufSize` равно 0, этот параметр может принимать значение null.

## <a name="remarks"></a>Remarks

Фрагменты кода никогда не перекрываются, и они будут следовать порядку, в котором они были сцеплены с помощью [ICorDebugCode:: Code](icordebugcode-getcode-method.md). Объект кода на языке MSIL в платформа .NET Framework версии 2,0 будет состоять из одного фрагмента кода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
