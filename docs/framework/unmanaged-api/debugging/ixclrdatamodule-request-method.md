---
description: 'Дополнительные сведения о методе: Иксклрдатамодуле:: Request'
title: 'Метод Иксклрдатамодуле:: Request'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 96f4153c58a228cfb22a5cd25a53b6e60fc4dfd1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800738"
---
# <a name="ixclrdatamodulerequest-method"></a>Метод Иксклрдатамодуле:: Request

Запросы на заполнение буфера данными модуля.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a>Параметры

`reqCode`\
окне Тип запроса для отправки.

`inBufferSize`\
[in] размер входного буфера, который должен быть передан.

`inBuffer`\
[in, size_is (Инбуфферсизе)] Указатель буфера для необработанных данных, отправляемых в запросе.

`outBufferSize`\
окне Размер выходного буфера.

`outBuffer`\
[out, size_is (Аутбуфферсизе)] Указатель буфера, используемый для хранения ответа на запрос.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту 37th таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).
**Заголовок:** Нет **библиотеки:** нет **платформа .NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)
