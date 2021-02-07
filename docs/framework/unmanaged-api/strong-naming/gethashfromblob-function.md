---
description: Дополнительные сведения о функции GetHashFromBlob
title: Функция GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
ms.openlocfilehash: dc5039e44440afa7a000bc61167faec0e5b6cc84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736613"
---
# <a name="gethashfromblob-function"></a>Функция GetHashFromBlob

Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Параметры

`pbBlob`\
окне Указатель на адрес блока памяти, который необходимо хэшировать.

`cchBlob`\
окне Длина блока памяти в байтах.

`piHashAlg`\
[вход, выход] Константа, указывающая хэш-алгоритм. Используйте нуль для алгоритма по умолчанию.

`pbHash`\
заполняет Возвращаемый буфер хэша.

`cchHash`\
окне Запрошенный максимальный размер `pbHash` .

`pchHash`\
заполняет Размер возвращаемого объекта (в байтах) `pbHash` .

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** StrongName. h

**Библиотека:** Включается в качестве ресурса в MsCorEE.dll

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
