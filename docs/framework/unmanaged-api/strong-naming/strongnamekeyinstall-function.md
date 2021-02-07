---
description: Дополнительные сведения о функции StrongNameKeyInstall
title: Функция StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 0a5d3971ac0927dda7066405adc01a5c80b7faca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670558"
---
# <a name="strongnamekeyinstall-function"></a>Функция StrongNameKeyInstall

Импортирует пару открытого и закрытого ключей в контейнер.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Параметры

`wszKeyContainer`\
окне Имя контейнера ключей. `wszKeyContainer` значение должно быть непустой строкой.

`pbKeyBlob`\
окне Пара двоичных ключей.

`cbKeyBlob`\
окне Размер (в байтах) `pbKeyBlob` .

## <a name="return-value"></a>Возвращаемое значение

`true` При успешном завершении; в противном случае — `false` .

## <a name="remarks"></a>Remarks

Чтобы удалить контейнер ключей, используйте функцию [StrongNameKeyDelete](strongnamekeydelete-function.md) .

Если `StrongNameKeyInstall` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** StrongName. h

**Библиотека:** Включается в качестве ресурса в MsCorEE.dll

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Метод StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
