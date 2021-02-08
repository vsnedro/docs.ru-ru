---
description: Дополнительные сведения о функции CertFreeAuthenticodeSignerInfo
title: Функция CertFreeAuthenticodeSignerInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
topic_type:
- apiref
ms.openlocfilehash: 6e8a97e8fee37d885c7d32102ed8cc7654992223
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772982"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>Функция CertFreeAuthenticodeSignerInfo

Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CertFreeAuthenticodeSignerInfo (
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);
```

## <a name="parameters"></a>Параметры

 `pSignerInfo`\
 [в, из] Информация о подписавшем, которую необходимо указывать. См. структуру [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) .

## <a name="return-value"></a>Возвращаемое значение

 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.

## <a name="requirements"></a>Требования

**Сборка**: clr.dll

## <a name="see-also"></a>См. также

- [Authenticode](index.md)
