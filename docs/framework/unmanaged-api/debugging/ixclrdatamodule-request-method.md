---
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
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420816"
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

## <a name="remarks"></a>Комментарии

Предоставленный метод является частью `IXCLRDataModule` интерфейса и соответствует слоту 37th таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).
**Заголовок:** Нет **библиотеки:** нет **.NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также статью

- [Отладка](index.md)
- [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)
