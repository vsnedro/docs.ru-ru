---
title: Метод IMetaDataDispenserEx::GetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
ms.openlocfilehash: 832adacac4a6df9ccf21578538a1c557150f3ba1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008785"
---
# <a name="imetadatadispenserexgetoption-method"></a>Метод IMetaDataDispenserEx::GetOption
Возвращает значение указанного параметра для текущей области метаданных. Параметр определяет, как обрабатываются вызовы к текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `optionId`  
 окне Указатель на идентификатор GUID, указывающий параметр, который необходимо получить. Список поддерживаемых идентификаторов GUID см. в разделе "Примечания".  
  
 `pValue`  
 заполняет Значение возвращаемого параметра. Тип этого значения будет представлять собой вариант типа указанного параметра.  
  
## <a name="remarks"></a>Примечания  
 В следующем списке показаны идентификаторы GUID, которые поддерживаются для этого метода. Описание см. в описании метода [IMetaDataDispenserEx:: SetOption](imetadatadispenserex-setoption-method.md) . Если `optionId` не находится в этом списке, этот метод возвращает значение HRESULT `E_INVALIDARG` , указывающее на неверный параметр.  
  
- метадатачеккдупликатесфор  
  
- метадатарефтодефчекк  
  
- метадатанотификатионфортокенмовемент  
  
- метадатасетенк  
  
- метадатаеррорифемитаутофордер  
  
- метадатаженератетцеадаптерс  
  
- метадаталинкероптионс  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)
