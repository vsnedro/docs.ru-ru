---
title: Метод IMetaDataImport::GetClassLayout
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type:
- apiref
ms.openlocfilehash: 5a442d8d0916b0e86f25c03507de66fc999f2159
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711264"
---
# <a name="imetadataimportgetclasslayout-method"></a>Метод IMetaDataImport::GetClassLayout

Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassLayout  (
   [in]  mdTypeDef          td,
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Токен TypeDef для класса с макетом, который должен быть возвращен.  
  
 `pdwPackSize`  
 заполняет Одно из значений 1, 2, 4, 8 или 16, представляющее размер пакета класса.  
  
 `rFieldOffset`  
 заполняет Массив значений [COR_FIELD_OFFSET](cor-field-offset-structure.md) .  
  
 `cMax`  
 [in] Максимальный размер массива `rFieldOffset`.  
  
 `pcFieldOffset`  
 заполняет Число элементов, возвращаемых в `rFieldOffset` .  
  
 `pulClassSize`  
 заполняет Размер в байтах класса, представленного параметром `td` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
