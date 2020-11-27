---
title: 'Метод Иксклрдатапроцесс:: Жетрунтименамебяддресс'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275570"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a>Метод Иксклрдатапроцесс:: Жетрунтименамебяддресс

Возвращает имя для заданного адреса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a>Параметры

`address`\
окне `CLRDATA_ADDRESS` Значение, представляющее адрес кода.

`flags`\
окне Задайте значение "0".

`bufLen`\
окне Длина буфера.

`namLen`\
заполняет Указатель на число возвращаемых символов.

`namBuf`\
[out, size_is ( `bufLen` )] входной буфер длины `bufLen` , в которой хранится имя среды выполнения.

`displacement`\
заполняет `CLRDATA_ADDRESS` Указатель на смещение кода возвращаемого символа.

## <a name="remarks"></a>Примечания

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует шестнадцатому слоту таблицы виртуального метода.

> [!NOTE]
> Если размер буфера не достаточен для имени, этот метод возвращает `S_FALSE` и задает `nameLen` требуемую длину буфера.

## <a name="requirements"></a>Требования

**Платформы:** См. [требования к системе](../../get-started/system-requirements.md)\
**Заголовок:** None
**Библиотека:** None
**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
