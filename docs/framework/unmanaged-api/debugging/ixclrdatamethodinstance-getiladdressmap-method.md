---
description: 'Дополнительные сведения о методе: Иксклрдатамесодинстанце:: Жетиладдрессмап'
title: 'Метод Иксклрдатамесодинстанце:: Жетиладдрессмап'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: ddddf593c3c18f2b4cd1682b5d6f7c8ff1985ac6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800816"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a>Метод Иксклрдатамесодинстанце:: Жетиладдрессмап

Возвращает IL для сопоставления сведений о сопоставлении.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a>Параметры

`mapLen`\
окне Длина указанного массива сопоставлений.

`mapNeeded`\
заполняет Количество записей карт, необходимых методу.

`maps`\
[out, size_is (Маплен)] Массив для хранения записей сопоставлений.

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataMethodInstance` интерфейса и соответствует 15-слоту таблицы виртуального метода.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
**Заголовок:** None  
**Библиотека:** None  
**Платформа .NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
