---
description: Дополнительные сведения о функции Цертфриаусентикодетиместамперинфо
title: Функция CertFreeAuthenticodeTimestamperInfo
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
topic_type:
- apiref
ms.openlocfilehash: 5234a90ea1d0272a7409b1b0b4def2160b77a513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772943"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>Функция CertFreeAuthenticodeTimestamperInfo

Освобождает ресурсы, выделенные для структуры [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT CertFreeAuthenticodeTimestamperInfo (
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo
);
```

## <a name="parameters"></a>Параметры

 `pTimestamperInfo`\
 [в, из] Информация об отметке времени выпуска. См. структуру [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) .

## <a name="return-value"></a>Возвращаемое значение

 `S_OK`, если функция выполняется успешно. В противном случае возвращается код ошибки.

## <a name="requirements"></a>Требования

**Сборка**: clr.dll

## <a name="see-also"></a>См. также

- [Authenticode](index.md)
