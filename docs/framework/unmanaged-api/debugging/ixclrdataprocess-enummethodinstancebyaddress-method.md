---
description: 'Дополнительные сведения о методе: Иксклрдатапроцесс:: Енуммесодинстанцебяддресс'
title: 'Метод Иксклрдатапроцесс:: Енуммесодинстанцебяддресс'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a0d59956288e39be188628d10c63a52d09d17638
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800699"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a>Метод Иксклрдатапроцесс:: Енуммесодинстанцебяддресс

Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a>Параметры

`handle`\
окне Описатель для перечисления экземпляров методов.

`mod`\
заполняет Экземпляр перечисленного метода.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует слоту 29 таблицы виртуальных методов.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).
**Заголовок:** Нет **библиотеки:** нет **платформа .NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также

- [Перечисление Клрдатасаурцетипе](clrdatasourcetype-enumeration.md)
- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)
