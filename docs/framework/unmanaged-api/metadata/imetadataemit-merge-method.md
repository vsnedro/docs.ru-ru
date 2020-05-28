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
ms.openlocfilehash: e7fe5cbe27c0771a71e4c03d14ab68ada7d0741a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004196"
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
  
## <a name="remarks"></a>Примечания  
 Вызовите метод [IMetaDataEmit:: мержеенд](imetadataemit-mergeend-method.md) , чтобы активировать слияние метаданных в одну область.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
