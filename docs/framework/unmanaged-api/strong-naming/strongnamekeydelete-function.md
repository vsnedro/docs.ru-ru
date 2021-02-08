---
description: Дополнительные сведения о функции StrongNameKeyDelete
title: Функция StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
ms.openlocfilehash: 9314d961f79e673925125c2362308f9ab4533e75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781211"
---
# <a name="strongnamekeydelete-function"></a>Функция StrongNameKeyDelete

Удаляет указанный контейнер ключей.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Параметры

`wszKeyContainer`\
окне Имя удаляемого контейнера ключей.

## <a name="return-value"></a>Возвращаемое значение

`true` При успешном завершении; в противном случае — `false` .

## <a name="remarks"></a>Remarks

Используйте функцию [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пары открытого и закрытого ключей в контейнер.

Если `StrongNameKeyDelete` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** StrongName. h

**Библиотека:** Включается в качестве ресурса в MsCorEE.dll

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
