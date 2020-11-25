---
title: Метод IMetaDataEmit::Merge
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722015"
---
# <a name="imetadataemitmerge-method"></a>Метод IMetaDataEmit::Merge

Добавляет указанную импортированную область в список объединяемых областей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pImport`  
 окне Указатель на объект [IMetaDataImport](imetadataimport-interface.md) , определяющий импортируемую область для слияния.  
  
 `pIMap`  
 окне Указатель на объект [IMapToken](imaptoken-interface.md) , указывающий повторное отображение токена.  
  
 `pHandler`  
 окне Указатель на объект [IUnknown](/cpp/atl/iunknown) , указывающий ошибки.  
  
## <a name="remarks"></a>Комментарии  

 Вызовите метод [IMetaDataEmit:: мержеенд](imetadataemit-mergeend-method.md) , чтобы активировать слияние метаданных в одну область.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
