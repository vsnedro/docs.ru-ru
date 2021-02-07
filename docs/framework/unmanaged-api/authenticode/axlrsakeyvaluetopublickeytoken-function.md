---
description: Дополнительные сведения о функции _AxlRSAKeyValueToPublicKeyToken
title: Функция _AxlRSAKeyValueToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
topic_type:
- apiref
ms.openlocfilehash: 01fc4cdc1d9985375748307ca2d7fff97191c908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747274"
---
# <a name="_axlrsakeyvaluetopublickeytoken-function"></a>\_Функция Акслрсакэйвалуетопубликкэйтокен

Преобразует модули и экспоненту в строгое имя маркера открытого ключа.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT _AxlRSAKeyValueToPublicKeyToken (
    [in]  PCRYPT_DATA_BLOB pModulusBlob,
    [in]  PCRYPT_DATA_BLOB pExponentBlob,
    [out] LPWSTR           *ppwszPublicKeyToken
);
```

## <a name="parameters"></a>Параметры

 `pModulusBlob`\
 окне Большой двоичный объект модуля в кодировке Base64 (из \<Modulus> элемента).  См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `pExponentBlob`\
 окне Большой двоичный объект экспоненты в кодировке Base64 (из \<Exponent> элемента). См. структуру [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) .

 `ppwszPublicKeyToken`\
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного маркера открытого ключа.

## <a name="return-value"></a>Возвращаемое значение

 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.

## <a name="requirements"></a>Требования

**Сборка**: clr.dll

## <a name="see-also"></a>См. также

- [Authenticode](index.md)
