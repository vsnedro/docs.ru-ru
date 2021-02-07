---
description: Дополнительные сведения о функции _AxlGetIssuerPublicKeyHash
title: Функция _AxlGetIssuerPublicKeyHash
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
topic_type:
- apiref
ms.openlocfilehash: 586a072b33376a2fdade119fe3db0f48addfa3f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747365"
---
# <a name="_axlgetissuerpublickeyhash-function"></a>\_Функция Акслжетиссуерпубликкэйхаш

Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT _AxlGetIssuerPublicKeyHash (
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,
    [out] LPWSTR                *ppwszPublicKeyHash
);
```

## <a name="parameters"></a>Параметры

 `pChainContext`\
 [в] Большой двоичный объект открытого ключа CSP. См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `ppwszPublicKeyHash`\
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.

## <a name="return-value"></a>Возвращаемое значение

 `S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.

## <a name="requirements"></a>Требования

**Сборка**: clr.dll

## <a name="see-also"></a>См. также

- [Authenticode](index.md)
