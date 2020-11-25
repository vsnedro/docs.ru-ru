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
ms.openlocfilehash: 0ceadf42ac49fd3fc89c78a6a26b2f529afeeaf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700566"
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
  
## <a name="remarks"></a>Комментарии  

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
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)
