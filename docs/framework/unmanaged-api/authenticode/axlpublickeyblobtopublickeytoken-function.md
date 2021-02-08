---
description: Дополнительные сведения о функции _AxlPublicKeyBlobToPublicKeyToken
title: Функция _AxlPublicKeyBlobToPublicKeyToken
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
topic_type:
- apiref
ms.openlocfilehash: df0b484bad64051eb892d4898a6c90777cc2d5cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781939"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_Функция Акслпубликкэйблобтопубликкэйтокен

Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT _AxlPublicKeyBlobToPublicKeyToken (
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,
    [out] LPWSTR                 *ppwszPublicKeyToken
);
```

## <a name="parameters"></a>Параметры

 `pCspPublicKeyBlob`\
 [в] Большой двоичный объект открытого ключа CSP.

 `ppwszPublicKeyHash`\
 [из] Указатель на WCHAR * для получения шестнадцатеричного кодированного хэша открытого ключа.

## <a name="return-value"></a>Возвращаемое значение

 `S_OK`, если функция выполняется успешно. В противном случае — `S_FALSE`.

## <a name="requirements"></a>Требования

**Сборка**: clr.dll

## <a name="see-also"></a>См. также

- [Authenticode](index.md)
