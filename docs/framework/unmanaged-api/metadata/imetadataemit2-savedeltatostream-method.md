---
title: Метод IMetaDataEmit2::SaveDeltaToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: a8f46871dde4c664a502c261fc882f3badf0f362
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492763"
---
# <a name="imetadataemit2savedeltatostream-method"></a>Метод IMetaDataEmit2::SaveDeltaToStream
Сохраняет изменения из текущего сеанса "изменить и продолжить" в указанный поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIStream`  
 окне Указатель интерфейса на поток, доступный для записи, в который необходимо сохранить изменения.  
  
 `dwSaveFlags`  
 [in] Зарезервировано. Это значение должно быть равно нулю.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
